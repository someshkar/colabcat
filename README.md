# Colabcat

Run [Hashcat](https://hashcat.net) on [Google Colab](https://colab.research.google.com) with session restore capabilities with Google Drive.

## Usage

- Go to the link below to open a copy of the `colabcat.ipynb` file in Google Colab:
  colab.research.google.com/github/someshkar/colabcat/blob/master/colabcat.ipynb
- Click on `Runtime`, `Change runtime type`, and set `Hardware accelerator` to GPU.
- Go to your Google Drive and create a directory called `dothashcat`, with a `hashes` subdirectory where you can store hashes.
- Come back to Google Colab, click on `Runtime` and then `Run all`.
- When it asks for a Google Drive token, go to the link it provides and authenticate with your Google Account to get the token.
- You can edit the last few cells in the notebook to customize the wordlists it downloads and the type of hash it cracks. A full list of these can be found [here](https://hashcat.net/wiki/doku.php?id=example_hashes).
- If needed, simply type `!bash` in a new cell to get access to an interactive shell on the Google Colab instance.

## How it works

Colabcat creates a symbolic link between the `dothashcat` folder in your Google Drive and the `/root/.hashcat` folder on the Google Colab session.

This enables seamless session restore even if your Google Colab gets disconnected or you hit the time limit for a single session, by syncing the `.restore`, `.log` and the `.potfile` files across Google Colab sessions by storing them in your Google Drive.