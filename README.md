# RocketBookPages
Generates RocketBook QR Numerated Pages in a PDF depending on the quantity of pages, the template type and the page size.

## Installation
It has been tested in python3 only.
```bash
git clone https://github.com/FranciscodeMaussion/RocketBookPages
cd RocketBookPages
pip install -r requirements.txt
```

## Usage
You must be placed in the program folder.

- Create a new PDF file 
    ```bash
    rocketqr create
    ```
    - Parameters:
        - --quantity, -q: The number of pages that will contain the document
        - --frame, -f: The page size(A4, Mini, Letter)
        - --type_of_page, -t: The page type(DotGrid:0, Graph:1, Lined:2, Music:3)
        - --numbered, -n: Define if the pages will be numbered or not
    - Note: if a parameter is no provided, it will be asked for.
- Delete all generated files
    ```bash
    rocketqr delete
    ```
- Templates section
    ```bash
    rocketqr templates menu
    rocketqr templates show
    rocketqr templates create
    ```
- Open menu
    ```bash
    rocketqr menu
    ```
  
## Template json files
To share a template file just send your .json located in Source/templates.json and the pdf file needed by it.
To use a template file, put it in Sources/templates.json

## Example
Will generate an A4 sized file with 5 pages and with DotGrid template with numbered pages.
```bash
python rocketqr.py create -q 5 -f A4 -t 0 -n True
```

## Make use of
- [Click](https://click.palletsprojects.com)
- [console-menu](https://github.com/aegirhall/console-menu)
- [Pillow](https://pillow.readthedocs.io/en/stable/)
- [PyPDF2](https://pythonhosted.org/PyPDF2/)
- [qrcode](https://github.com/lincolnloop/python-qrcode)
- [reportlab](https://www.reportlab.com/)
- [six](https://github.com/benjaminp/six)



## Cairo can't be installed
This is a depedency graph requirement, avoiding installing `pycairo` would be a plus.

To ensure `pycairo` can be installed, follow the installation instructions from [https://pycairo.readthedocs.io/en/latest/getting_started.html#getting-started]()
which is likely just installing some OS packages.

- Ubuntu/Debian: `sudo apt install libcairo2-dev pkg-config python3-dev`
- macOS/Homebrew: `brew install cairo pkg-config`
- Arch Linux: `sudo pacman -S cairo pkgconf`
- Fedora: `sudo dnf install cairo-devel pkg-config python3-devel`
- openSUSE: `sudo zypper install cairo-devel pkg-config python3-devel`