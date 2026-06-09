# System.Web.UI.Design.WebControls.DetailsViewAutoFormat::Initialize

- ea: `0x21ee0`
- end: `0x22127`
- name: `System.Web.UI.Design.WebControls.DetailsViewAutoFormat::Initialize`
- size: `583`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x21fd2`: `CommandRowForeColor`
- `0x21fe3`: `CommandRowBackColor`
- `0x21ff4`: `CommandRowFont`

## pseudocode

```c

```

## disassembly

```asm
0x21ee0  ldarg.0
0x21ee1  ldstr    aForecolor// "ForeColor"
0x21ee6  ldarg.1
0x21ee7  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x21eec  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::foreColor
0x21ef1  ldarg.0
0x21ef2  ldstr    aBackcolor// "BackColor"
0x21ef7  ldarg.1
0x21ef8  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x21efd  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::backColor
0x21f02  ldarg.0
0x21f03  ldstr    aBordercolor// "BorderColor"
0x21f08  ldarg.1
0x21f09  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x21f0e  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::borderColor
0x21f13  ldarg.0
0x21f14  ldstr    aBorderwidth// "BorderWidth"
0x21f19  ldarg.1
0x21f1a  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x21f1f  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::borderWidth
0x21f24  ldarg.0
0x21f25  ldstr    aBorderstyle// "BorderStyle"
0x21f2a  ldc.i4.m1
0x21f2b  ldarg.1
0x21f2c  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, int32, class [System.Data]System.Data.DataRow)
0x21f31  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::borderStyle
0x21f36  ldarg.0
0x21f37  ldstr    aCellspacing// "CellSpacing"
0x21f3c  ldarg.1
0x21f3d  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x21f42  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::cellSpacing
0x21f47  ldarg.0
0x21f48  ldstr    aCellpadding// "CellPadding"
0x21f4d  ldc.i4.m1
0x21f4e  ldarg.1
0x21f4f  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, int32, class [System.Data]System.Data.DataRow)
0x21f54  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::cellPadding
0x21f59  ldarg.0
0x21f5a  ldstr    aGridlines// "GridLines"
0x21f5f  ldc.i4.m1
0x21f60  ldarg.1
0x21f61  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, int32, class [System.Data]System.Data.DataRow)
0x21f66  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::gridLines
0x21f6b  ldarg.0
0x21f6c  ldstr    aRowforecolor// "RowForeColor"
0x21f71  ldarg.1
0x21f72  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x21f77  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::rowForeColor
0x21f7c  ldarg.0
0x21f7d  ldstr    aRowbackcolor// "RowBackColor"
0x21f82  ldarg.1
0x21f83  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x21f88  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::rowBackColor
0x21f8d  ldarg.0
0x21f8e  ldstr    aRowfont// "RowFont"
0x21f93  ldarg.1
0x21f94  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x21f99  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::itemFont
0x21f9e  ldarg.0
0x21f9f  ldstr    aAltrowforecolo// "AltRowForeColor"
0x21fa4  ldarg.1
0x21fa5  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x21faa  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::alternatingRowForeColor
0x21faf  ldarg.0
0x21fb0  ldstr    aAltrowbackcolo// "AltRowBackColor"
0x21fb5  ldarg.1
0x21fb6  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x21fbb  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::alternatingRowBackColor
0x21fc0  ldarg.0
0x21fc1  ldstr    aAltrowfont// "AltRowFont"
0x21fc6  ldarg.1
0x21fc7  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x21fcc  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::alternatingRowFont
0x21fd1  ldarg.0
0x21fd2  ldstr    aCommandrowfore// "CommandRowForeColor"
0x21fd7  ldarg.1
0x21fd8  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x21fdd  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::commandRowForeColor
0x21fe2  ldarg.0
0x21fe3  ldstr    aCommandrowback// "CommandRowBackColor"
0x21fe8  ldarg.1
0x21fe9  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x21fee  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::commandRowBackColor
0x21ff3  ldarg.0
0x21ff4  ldstr    aCommandrowfont// "CommandRowFont"
0x21ff9  ldarg.1
0x21ffa  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x21fff  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::commandRowFont
0x22004  ldarg.0
0x22005  ldstr    aFieldheaderfor// "FieldHeaderForeColor"
0x2200a  ldarg.1
0x2200b  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x22010  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::fieldHeaderForeColor
0x22015  ldarg.0
0x22016  ldstr    aFieldheaderbac// "FieldHeaderBackColor"
0x2201b  ldarg.1
0x2201c  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x22021  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::fieldHeaderBackColor
0x22026  ldarg.0
0x22027  ldstr    aFieldheaderfon// "FieldHeaderFont"
0x2202c  ldarg.1
0x2202d  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x22032  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::fieldHeaderFont
0x22037  ldarg.0
0x22038  ldstr    aEditrowforecol// "EditRowForeColor"
0x2203d  ldarg.1
0x2203e  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x22043  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::editRowForeColor
0x22048  ldarg.0
0x22049  ldstr    aEditrowbackcol// "EditRowBackColor"
0x2204e  ldarg.1
0x2204f  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x22054  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::editRowBackColor
0x22059  ldarg.0
0x2205a  ldstr    aEditrowfont// "EditRowFont"
0x2205f  ldarg.1
0x22060  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x22065  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::editRowFont
0x2206a  ldarg.0
0x2206b  ldstr    aHeaderforecolo// "HeaderForeColor"
0x22070  ldarg.1
0x22071  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x22076  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::headerForeColor
0x2207b  ldarg.0
0x2207c  ldstr    aHeaderbackcolo// "HeaderBackColor"
0x22081  ldarg.1
0x22082  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x22087  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::headerBackColor
0x2208c  ldarg.0
0x2208d  ldstr    aHeaderfont// "HeaderFont"
0x22092  ldarg.1
0x22093  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x22098  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::headerFont
0x2209d  ldarg.0
0x2209e  ldstr    aFooterforecolo// "FooterForeColor"
0x220a3  ldarg.1
0x220a4  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x220a9  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::footerForeColor
0x220ae  ldarg.0
0x220af  ldstr    aFooterbackcolo// "FooterBackColor"
0x220b4  ldarg.1
0x220b5  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x220ba  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::footerBackColor
0x220bf  ldarg.0
0x220c0  ldstr    aFooterfont// "FooterFont"
0x220c5  ldarg.1
0x220c6  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x220cb  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::footerFont
0x220d0  ldarg.0
0x220d1  ldstr    aPagerforecolor// "PagerForeColor"
0x220d6  ldarg.1
0x220d7  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x220dc  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::pagerForeColor
0x220e1  ldarg.0
0x220e2  ldstr    aPagerbackcolor// "PagerBackColor"
0x220e7  ldarg.1
0x220e8  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x220ed  stfld    string System.Web.UI.Design.WebControls.DetailsViewAutoFormat::pagerBackColor
0x220f2  ldarg.0
0x220f3  ldstr    aPagerfont// "PagerFont"
0x220f8  ldarg.1
0x220f9  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x220fe  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::pagerFont
0x22103  ldarg.0
0x22104  ldstr    aPageralign// "PagerAlign"
0x22109  ldarg.1
0x2210a  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, class [System.Data]System.Data.DataRow)
0x2210f  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::pagerAlign
0x22114  ldarg.0
0x22115  ldstr    aPagerbuttons// "PagerButtons"
0x2211a  ldc.i4.1
0x2211b  ldarg.1
0x2211c  call     int32 class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.DetailsView>::GetIntProperty(string, int32, class [System.Data]System.Data.DataRow)
0x22121  stfld    int32 System.Web.UI.Design.WebControls.DetailsViewAutoFormat::pagerButtons
0x22126  ret
```
