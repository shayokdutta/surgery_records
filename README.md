# Surgical Records & Protocols

This repository serves as the central archive for all surgical procedures, checklists, and completed animal logs. It hosts the [Surgical Records Website](https://shayokdutta.github.io/surgery_records/) for easy access to templates and guides.

I believe strongly in **Open Science**, and this project is one of many ways I demonstrate my commitment to transparency and reproducibility in research. If you find this approach useful, feel free to adapt these protocols and follow the workflow instructions below to build your own system.

## 🔄 The Surgical Workflow

This workflow ensures that handwritten logs from the iPad are automatically backed up to Google Drive and permanently archived in version control.

### 1. Preparation (Desktop/iPad)
1.  Navigate to the **[Surgical Record Template](./surgical_record_template.html)** on the website.
2.  **Export to PDF:** Use your browser's "Print" function ($\rightarrow$ Save as PDF) to generate a fresh, blank log sheet.
3.  **Save to Drive:** Save this blank PDF into your synced Google Drive folder (e.g., `Surgery_Logs/2026/`).

### 2. Intra-Operative Logging (iPad)
1.  Open the **Files App** on your iPad and navigate to the Google Drive folder.
2.  **Duplicate & Rename:** Long-press the blank template $\rightarrow$ Duplicate. Rename it using the convention: `YYYY-MM-DD_AnimalID_Procedure.pdf`.
3.  **Log:** Open the new file and use the **Markup tool** (Apple Pencil) to record data during the surgery.
4.  **Save:** Tap "Done" to save changes directly back to Google Drive.

### 3. Archiving & Security (Desktop)
*Since your Google Drive is synced to your desktop (via Insync), the new PDF will automatically appear in your local repository folder.*

**Optional: Password-Protect Logs**
If you need to secure the completed logs before committing them, navigate to your log directory and run this command to safely password-protect and overwrite the PDFs:
```bash
for f in *.pdf; do pdftk "$f" output "${f}.tmp" user_pw YOUR_PASSWORD_HERE && mv "${f}.tmp" "$f"; done
```

To permanently archive the record to GitHub:

1.  Open your terminal in the repository folder.
2.  Run the update commands:
    ```bash
    git pull                  # Ensure you have the latest changes
    git add .                 # Stage the new PDF logs
    git commit -m "Add surgical record: [Date/ID]"
    git push origin main      # Push to GitHub
    ```

---

## 📂 Repository Contents

* **`index.md`**: The repository homepage and quick reference guide.
* **`surgery_checklist.md`**: The master protocol merging Kemerelab, Wellelab, and personal workflows.
* **`surgical_record_template.html`**: The HTML source for generating the blank print-layout logs.
* **`logs/`**: (Optional) Directory containing completed PDF records.

## 🔗 Useful Links
* **[Live Website](https://shayokdutta.github.io/surgery_records/)**
* **[Autoclave Booking](https://github.com/kemerelab/Private/wiki/Autoclave)**

## 📜 Citation

If you use these protocols or templates in your research, please cite them as:

> Dutta, S. (2026). Surgical Records & Protocols: An Open Science Framework for Animal Logs. GitHub. https://github.com/shayokdutta/surgery_records
