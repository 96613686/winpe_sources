# System.Web.UI.Design.WebControls.SiteMapPathAutoFormat::Initialize

- ea: `0x354d0`
- end: `0x3559d`
- name: `System.Web.UI.Design.WebControls.SiteMapPathAutoFormat::Initialize`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x354d0`

## string_xrefs

- `0x35501`: `PathSeparator`
- `0x35576`: `PathSeparatorStyleFontBold`
- `0x35587`: `PathSeparatorStyleForeColor`

## pseudocode

```c

```

## disassembly

```asm
0x354d0  ldarg.1
0x354d1  brtrue.s loc_354D4
0x354d3  ret
0x354d4  ldarg.0
0x354d5  ldstr    aFontname// "FontName"
0x354da  ldarg.1
0x354db  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.SiteMapPath>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x354e0  stfld    string System.Web.UI.Design.WebControls.SiteMapPathAutoFormat::_fontName
0x354e5  ldarg.0
0x354e6  ldstr    aFontsize_0// "FontSize"
0x354eb  ldarg.1
0x354ec  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.SiteMapPath>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x354f1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x354f6  newobj   instance void [System.Web]System.Web.UI.WebControls.FontUnit::.ctor(string, class [mscorlib]System.Globalization.CultureInfo)
0x354fb  stfld    valuetype [System.Web]System.Web.UI.WebControls.FontUnit System.Web.UI.Design.WebControls.SiteMapPathAutoFormat::_fontSize
0x35500  ldarg.0
0x35501  ldstr    aPathseparator// "PathSeparator"
0x35506  ldarg.1
0x35507  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.SiteMapPath>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x3550c  stfld    string System.Web.UI.Design.WebControls.SiteMapPathAutoFormat::_pathSeparator
0x35511  ldarg.0
0x35512  ldstr    aNodestylefontb// "NodeStyleFontBold"
0x35517  ldarg.1
0x35518  call     bool class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.SiteMapPath>::GetBooleanProperty(string, class [System.Data]System.Data.DataRow)
0x3551d  stfld    bool System.Web.UI.Design.WebControls.SiteMapPathAutoFormat::_nodeStyleFontBold
0x35522  ldarg.0
0x35523  ldstr    aNodestyleforec// "NodeStyleForeColor"
0x35528  ldarg.1
0x35529  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.SiteMapPath>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x3552e  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x35533  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.SiteMapPathAutoFormat::_nodeStyleForeColor
0x35538  ldarg.0
0x35539  ldstr    aRootnodestylef// "RootNodeStyleFontBold"
0x3553e  ldarg.1
0x3553f  call     bool class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.SiteMapPath>::GetBooleanProperty(string, class [System.Data]System.Data.DataRow)
0x35544  stfld    bool System.Web.UI.Design.WebControls.SiteMapPathAutoFormat::_rootNodeStyleFontBold
0x35549  ldarg.0
0x3554a  ldstr    aRootnodestylef_0// "RootNodeStyleForeColor"
0x3554f  ldarg.1
0x35550  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.SiteMapPath>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x35555  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x3555a  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.SiteMapPathAutoFormat::_rootNodeStyleForeColor
0x3555f  ldarg.0
0x35560  ldstr    aCurrentnodesty// "CurrentNodeStyleForeColor"
0x35565  ldarg.1
0x35566  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.SiteMapPath>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x3556b  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x35570  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.SiteMapPathAutoFormat::_currentNodeStyleForeColor
0x35575  ldarg.0
0x35576  ldstr    aPathseparators// "PathSeparatorStyleFontBold"
0x3557b  ldarg.1
0x3557c  call     bool class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.SiteMapPath>::GetBooleanProperty(string, class [System.Data]System.Data.DataRow)
0x35581  stfld    bool System.Web.UI.Design.WebControls.SiteMapPathAutoFormat::_pathSeparatorStyleFontBold
0x35586  ldarg.0
0x35587  ldstr    aPathseparators_0// "PathSeparatorStyleForeColor"
0x3558c  ldarg.1
0x3558d  call     string class System.Web.UI.Design.WebControls.BaseAutoFormat`1<class [System.Web]System.Web.UI.WebControls.SiteMapPath>::GetStringProperty(string, class [System.Data]System.Data.DataRow)
0x35592  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.ColorTranslator::FromHtml(string)
0x35597  stfld    valuetype [System.Drawing]System.Drawing.Color System.Web.UI.Design.WebControls.SiteMapPathAutoFormat::_pathSeparatorStyleForeColor
0x3559c  ret
```
