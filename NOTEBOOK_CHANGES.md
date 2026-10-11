# Notebook changes

Changes to `ST_GCN_Implementation.ipynb` from the initial pull at
`d8e76680416d0fdf067694f55e5b08e665bc7aed`. Cell numbers below refer to that
original notebook. Its original headings, prose, comments, docstrings, and cell
order are retained. Change annotations live here to keep the notebook clear.

[Open this review branch in Colab](https://colab.research.google.com/github/yonatantussa/ST-GCN/blob/notebook-training-fixes/ST_GCN_Implementation.ipynb).
The notebook's original badge points to `main`; use this branch link before the PR is merged.
Run the dependency cell, mount Drive, and verify the data paths. No companion
Python files are needed. Outputs go to `MyDrive/content/st_gcn_runs/pose_baseline`.
For a fresh run after that folder already contains results, choose a new `RUN_NAME`;
set `RESUME=True` only to continue a matching checkpoint.

> **ADDED — dependency setup:** Install the notebook dependencies before the first imports. The original tqdm installation cell remains in its original position.

> **CHANGE — original cell 3:** Split by infant ID (all visits stay together), use an explicit seed, validate binary labels, and expose the split information for checkpoint checks.

> **CHANGE — original cell 4:** Keep the original Drive mount in Colab; allow the same notebook to run in a local kernel.

> **CHANGE — original cell 5:** Correct COP and scale subject indexing, initialize dataset length, use positional label indexing, validate recording bounds, and retain recording IDs for pooled metrics.

> **CHANGE — original cell 8:** Fix the appended COP node index (18), make the default layout valid, and make the string representation return text.

> **CHANGE — original cell 14:** Import the functional pooling helper in the model cell. The original model architecture is retained; age is not added.

> **CHANGE — original cell 17:** Retain the original MyDrive filenames; add local data discovery, fail early for missing files, and set the split seed before loading.

> **CHANGE — original cell 18:** Keep the original pose-only model setup. Add explicit resume, a separate run directory, checkpoint/data fingerprints, and reproducible shuffling. Age stays on hold.

> **CHANGE — original cell 20:** Print and save test loss every epoch, verify checkpoint metadata before resuming, restore epoch-boundary seeds, and save loss history. The original Markdown above is preserved; the code uses two-class CrossEntropyLoss.

> **CHANGE — original cell 21:** Retain the original window-level evaluation; add recording-level metrics, save results, and display/save the train-versus-test loss plot.

### ADDED — age experiment on hold

Clarification has been requested from Francis; awaiting his response on whether `Month` is age at recording in months, whether to use chronological or corrected age, and which spreadsheet column provides it. No age input is added to this notebook.

**ADDED — evaluation notes:** Test curves are diagnostic; use a separate subject-disjoint validation set before selecting epochs or tuning models. The original Aim 3 test fraction (0.001) is retained and holds out only one infant in the current data.

**CHANGED — saved outputs:** Previous execution counts and outputs were cleared because they used the old split. Original Markdown, comments, docstrings, and cell order are preserved; changed code cells are marked above.
