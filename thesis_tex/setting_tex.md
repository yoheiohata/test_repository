# vscodeからtexの設定方法
- texとvscodeは入っていることが前提
1. tex workshopをインストール<br>
<img src=./Figure/setting_tex01.png width=50%>
<br>
2. setting-JSONに設定を書き込む．(JSONは設定をjavascriptのオブジェクト形式でかけるようにしたもの) settingJSONは`Shift+Command+p`で開く
以下のコードを開く <br>
```
{ 
    //設定　
    // LaTeX Setup 
    "latex-workshop.latex.recipes": [ 
        { 
            "name": "toolchain", 
            "tools": [  
                "ptex2pdf" 
            ]
        },
    ],
    "latex-workshop.latex.tools": [
        {
            "name": "ptex2pdf",
            "command": "ptex2pdf",
            "args": [
                "-l",
                "-ot",
                "-kanji=utf -synctex=1 -interaction=nonstopmode -half-on-error -file-line-error",
                "%DOCFILE%.tex"
            ]
        },
    ],
    "latex-workshop.latex.clean.fileTypes": [
        "*.aux", "*.bbl", "*.blg", "*.idx", "*.ind", "*.lof", 
        "*.lot", "*.out", "*.toc", "*.acn", "*.acr", "*.alg", 
        "*.glg", "*.glo", "*.gls", "*.ist", "*.fls", "*.log", 
        "*.fdb_latexmk", "*.synctex.gz","_minted*", "*.nav", 
        "*.snm", "*.vrb","*.run.xml","*.dvi","*.bcf"
    ],
    "latex-workshop.view.pdf.viewer": "tab",
    "latex-workshop.latex.autoClean.run": "onFailed",
    "editor.renderControlCharacters": true
}
```
3. 文字を入力している最中にbuildされてカーソルが消えるので，環境設定から設定を変える．`Command+,`で設定を開く<br>
<img src=./Figure/setting_tex02.png width=50%><br>
そのあとauto buildのプルダウンメニューから`never`を選択する
