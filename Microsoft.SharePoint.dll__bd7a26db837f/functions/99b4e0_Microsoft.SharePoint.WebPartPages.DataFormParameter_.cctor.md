# Microsoft.SharePoint.WebPartPages.DataFormParameter::.cctor

- ea: `0x99b4e0`
- end: `0x99d085`
- name: `Microsoft.SharePoint.WebPartPages.DataFormParameter::.cctor`
- size: `7077`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x29ced0`
- `0x29d0f0`

## string_xrefs

- `0x99b9c7`: `data-localpath`
- `0x99b5cb`: `aria-autocomplete`
- `0x99b8cb`: `data-accessibility-nocheck`
- `0x99b9af`: `data-language-token`
- `0x99c663`: `PathSeparator-CssClass`
- `0x99c66f`: `PathSeparatorStyle.BackColor`
- `0x99c67b`: `PathSeparatorStyle.BorderColor`
- `0x99c687`: `PathSeparatorStyle.BorderWidth`
- `0x99c693`: `PathSeparatorStyle.CssClass`
- `0x99c69f`: `PathSeparatorStyle.Font.Bold`
- `0x99c6ab`: `PathSeparatorStyle.Font.Italic`
- `0x99c6b7`: `PathSeparatorStyle.Font.Name`
- `0x99c6c3`: `PathSeparatorStyle.Font.Names`
- `0x99c6cf`: `PathSeparatorStyle.Font.Overline`
- `0x99c6db`: `PathSeparatorStyle.Font.Size`
- `0x99c6e7`: `PathSeparatorStyle.Font.Strikeout`
- `0x99c6f3`: `PathSeparatorStyle.Font.Underline`
- `0x99c6ff`: `PathSeparatorStyle.ForeColor`
- `0x99c70b`: `PathSeparatorStyle.Height`
- `0x99c717`: `PathSeparatorStyle.HorizontalAlign`
- `0x99c723`: `PathSeparatorStyle.HorizontalPadding`
- `0x99c72f`: `PathSeparatorStyle.VerticalPadding`
- `0x99c73b`: `PathSeparatorStyle.Width`
- `0x99c753`: `PortalProvider.IncludeAuthoredLinks`

## pseudocode

```c

```

## disassembly

```asm
0x99b4e0  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x99b4e5  stloc.0
0x99b4e6  ldloc.0
0x99b4e7  ldstr    aActualImage// "actual-image"
0x99b4ec  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b4f1  pop
0x99b4f2  ldloc.0
0x99b4f3  ldstr    aAlternatingrow// "AlternatingRowStyle.BackColor"
0x99b4f8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b4fd  pop
0x99b4fe  ldloc.0
0x99b4ff  ldstr    aAlternatingrow_0// "AlternatingRowStyle.BorderColor"
0x99b504  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b509  pop
0x99b50a  ldloc.0
0x99b50b  ldstr    aAlternatingrow_1// "AlternatingRowStyle.BorderWidth"
0x99b510  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b515  pop
0x99b516  ldloc.0
0x99b517  ldstr    aAlternatingrow_2// "AlternatingRowStyle.CssClass"
0x99b51c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b521  pop
0x99b522  ldloc.0
0x99b523  ldstr    aAlternatingrow_3// "AlternatingRowStyle.Font.Bold"
0x99b528  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b52d  pop
0x99b52e  ldloc.0
0x99b52f  ldstr    aAlternatingrow_4// "AlternatingRowStyle.Font.Italic"
0x99b534  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b539  pop
0x99b53a  ldloc.0
0x99b53b  ldstr    aAlternatingrow_5// "AlternatingRowStyle.Font.Name"
0x99b540  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b545  pop
0x99b546  ldloc.0
0x99b547  ldstr    aAlternatingrow_6// "AlternatingRowStyle.Font.Names"
0x99b54c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b551  pop
0x99b552  ldloc.0
0x99b553  ldstr    aAlternatingrow_7// "AlternatingRowStyle.Font.Overline"
0x99b558  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b55d  pop
0x99b55e  ldloc.0
0x99b55f  ldstr    aAlternatingrow_8// "AlternatingRowStyle.Font.Size"
0x99b564  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b569  pop
0x99b56a  ldloc.0
0x99b56b  ldstr    aAlternatingrow_9// "AlternatingRowStyle.Font.Strikeout"
0x99b570  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b575  pop
0x99b576  ldloc.0
0x99b577  ldstr    aAlternatingrow_10// "AlternatingRowStyle.Font.Underline"
0x99b57c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b581  pop
0x99b582  ldloc.0
0x99b583  ldstr    aAlternatingrow_11// "AlternatingRowStyle.ForeColor"
0x99b588  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b58d  pop
0x99b58e  ldloc.0
0x99b58f  ldstr    aAlternatingrow_12// "AlternatingRowStyle.Height"
0x99b594  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b599  pop
0x99b59a  ldloc.0
0x99b59b  ldstr    aAlternatingrow_13// "AlternatingRowStyle.HorizontalAlign"
0x99b5a0  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b5a5  pop
0x99b5a6  ldloc.0
0x99b5a7  ldstr    aAlternatingrow_14// "AlternatingRowStyle.HorizontalPadding"
0x99b5ac  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b5b1  pop
0x99b5b2  ldloc.0
0x99b5b3  ldstr    aAlternatingrow_15// "AlternatingRowStyle.VerticalPadding"
0x99b5b8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b5bd  pop
0x99b5be  ldloc.0
0x99b5bf  ldstr    aAlternatingrow_16// "AlternatingRowStyle.Width"
0x99b5c4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b5c9  pop
0x99b5ca  ldloc.0
0x99b5cb  ldstr    aAriaAutocomple// "aria-autocomplete"
0x99b5d0  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b5d5  pop
0x99b5d6  ldloc.0
0x99b5d7  ldstr    aAriaCurrent// "aria-current"
0x99b5dc  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b5e1  pop
0x99b5e2  ldloc.0
0x99b5e3  ldstr    aAriaDropeffect// "aria-dropeffect"
0x99b5e8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b5ed  pop
0x99b5ee  ldloc.0
0x99b5ef  ldstr    aAriaExpanded// "aria-expanded"
0x99b5f4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b5f9  pop
0x99b5fa  ldloc.0
0x99b5fb  ldstr    aAriaHaspopup// "aria-haspopup"
0x99b600  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b605  pop
0x99b606  ldloc.0
0x99b607  ldstr    aAriaHidden// "aria-hidden"
0x99b60c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b611  pop
0x99b612  ldloc.0
0x99b613  ldstr    aAriaLabel// "aria-label"
0x99b618  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b61d  pop
0x99b61e  ldloc.0
0x99b61f  ldstr    aAriaMultiline// "aria-multiline"
0x99b624  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b629  pop
0x99b62a  ldloc.0
0x99b62b  ldstr    aAriaRole// "aria-role"
0x99b630  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b635  pop
0x99b636  ldloc.0
0x99b637  ldstr    aContainerFluid// "container-fluid"
0x99b63c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b641  pop
0x99b642  ldloc.0
0x99b643  ldstr    aCurrentnodesty// "CurrentNodeStyle.BackColor"
0x99b648  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b64d  pop
0x99b64e  ldloc.0
0x99b64f  ldstr    aCurrentnodesty_0// "CurrentNodeStyle.BorderColor"
0x99b654  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b659  pop
0x99b65a  ldloc.0
0x99b65b  ldstr    aCurrentnodesty_1// "CurrentNodeStyle.BorderWidth"
0x99b660  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b665  pop
0x99b666  ldloc.0
0x99b667  ldstr    aCurrentnodesty_2// "CurrentNodeStyle.CssClass"
0x99b66c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b671  pop
0x99b672  ldloc.0
0x99b673  ldstr    aCurrentnodesty_3// "CurrentNodeStyle.Font.Bold"
0x99b678  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b67d  pop
0x99b67e  ldloc.0
0x99b67f  ldstr    aCurrentnodesty_4// "CurrentNodeStyle.Font.Italic"
0x99b684  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b689  pop
0x99b68a  ldloc.0
0x99b68b  ldstr    aCurrentnodesty_5// "CurrentNodeStyle.Font.Name"
0x99b690  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b695  pop
0x99b696  ldloc.0
0x99b697  ldstr    aCurrentnodesty_6// "CurrentNodeStyle.Font.Names"
0x99b69c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b6a1  pop
0x99b6a2  ldloc.0
0x99b6a3  ldstr    aCurrentnodesty_7// "CurrentNodeStyle.Font.Overline"
0x99b6a8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b6ad  pop
0x99b6ae  ldloc.0
0x99b6af  ldstr    aCurrentnodesty_8// "CurrentNodeStyle.Font.Size"
0x99b6b4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b6b9  pop
0x99b6ba  ldloc.0
0x99b6bb  ldstr    aCurrentnodesty_9// "CurrentNodeStyle.Font.Strikeout"
0x99b6c0  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b6c5  pop
0x99b6c6  ldloc.0
0x99b6c7  ldstr    aCurrentnodesty_10// "CurrentNodeStyle.Font.Underline"
0x99b6cc  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b6d1  pop
0x99b6d2  ldloc.0
0x99b6d3  ldstr    aCurrentnodesty_11// "CurrentNodeStyle.ForeColor"
0x99b6d8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b6dd  pop
0x99b6de  ldloc.0
0x99b6df  ldstr    aCurrentnodesty_12// "CurrentNodeStyle.Height"
0x99b6e4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b6e9  pop
0x99b6ea  ldloc.0
0x99b6eb  ldstr    aCurrentnodesty_13// "CurrentNodeStyle.HorizontalAlign"
0x99b6f0  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b6f5  pop
0x99b6f6  ldloc.0
0x99b6f7  ldstr    aCurrentnodesty_14// "CurrentNodeStyle.HorizontalPadding"
0x99b6fc  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b701  pop
0x99b702  ldloc.0
0x99b703  ldstr    aCurrentnodesty_15// "CurrentNodeStyle.VerticalPadding"
0x99b708  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b70d  pop
0x99b70e  ldloc.0
0x99b70f  ldstr    aCurrentnodesty_16// "CurrentNodeStyle.Width"
0x99b714  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b719  pop
0x99b71a  ldloc.0
0x99b71b  ldstr    aDayheaderstyle// "DayHeaderStyle.BackColor"
0x99b720  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b725  pop
0x99b726  ldloc.0
0x99b727  ldstr    aDayheaderstyle_0// "DayHeaderStyle.BorderColor"
0x99b72c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b731  pop
0x99b732  ldloc.0
0x99b733  ldstr    aDayheaderstyle_1// "DayHeaderStyle.BorderWidth"
0x99b738  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b73d  pop
0x99b73e  ldloc.0
0x99b73f  ldstr    aDayheaderstyle_2// "DayHeaderStyle.CssClass"
0x99b744  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b749  pop
0x99b74a  ldloc.0
0x99b74b  ldstr    aDayheaderstyle_3// "DayHeaderStyle.Font.Bold"
0x99b750  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b755  pop
0x99b756  ldloc.0
0x99b757  ldstr    aDayheaderstyle_4// "DayHeaderStyle.Font.Italic"
0x99b75c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b761  pop
0x99b762  ldloc.0
0x99b763  ldstr    aDayheaderstyle_5// "DayHeaderStyle.Font.Name"
0x99b768  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b76d  pop
0x99b76e  ldloc.0
0x99b76f  ldstr    aDayheaderstyle_6// "DayHeaderStyle.Font.Names"
0x99b774  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b779  pop
0x99b77a  ldloc.0
0x99b77b  ldstr    aDayheaderstyle_7// "DayHeaderStyle.Font.Overline"
0x99b780  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b785  pop
0x99b786  ldloc.0
0x99b787  ldstr    aDayheaderstyle_8// "DayHeaderStyle.Font.Size"
0x99b78c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b791  pop
0x99b792  ldloc.0
0x99b793  ldstr    aDayheaderstyle_9// "DayHeaderStyle.Font.Strikeout"
0x99b798  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b79d  pop
0x99b79e  ldloc.0
0x99b79f  ldstr    aDayheaderstyle_10// "DayHeaderStyle.Font.Underline"
0x99b7a4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b7a9  pop
0x99b7aa  ldloc.0
0x99b7ab  ldstr    aDayheaderstyle_11// "DayHeaderStyle.ForeColor"
0x99b7b0  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b7b5  pop
0x99b7b6  ldloc.0
0x99b7b7  ldstr    aDayheaderstyle_12// "DayHeaderStyle.Height"
0x99b7bc  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b7c1  pop
0x99b7c2  ldloc.0
0x99b7c3  ldstr    aDayheaderstyle_13// "DayHeaderStyle.HorizontalAlign"
0x99b7c8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b7cd  pop
0x99b7ce  ldloc.0
0x99b7cf  ldstr    aDayheaderstyle_14// "DayHeaderStyle.HorizontalPadding"
0x99b7d4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b7d9  pop
0x99b7da  ldloc.0
0x99b7db  ldstr    aDayheaderstyle_15// "DayHeaderStyle.VerticalPadding"
0x99b7e0  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b7e5  pop
0x99b7e6  ldloc.0
0x99b7e7  ldstr    aDayheaderstyle_16// "DayHeaderStyle.Width"
0x99b7ec  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b7f1  pop
0x99b7f2  ldloc.0
0x99b7f3  ldstr    aDaystyleBackco// "DayStyle.BackColor"
0x99b7f8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b7fd  pop
0x99b7fe  ldloc.0
0x99b7ff  ldstr    aDaystyleBorder// "DayStyle.BorderColor"
0x99b804  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b809  pop
0x99b80a  ldloc.0
0x99b80b  ldstr    aDaystyleBorder_0// "DayStyle.BorderWidth"
0x99b810  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b815  pop
0x99b816  ldloc.0
0x99b817  ldstr    aDaystyleCsscla// "DayStyle.CssClass"
0x99b81c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b821  pop
0x99b822  ldloc.0
0x99b823  ldstr    aDaystyleFontBo// "DayStyle.Font.Bold"
0x99b828  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b82d  pop
0x99b82e  ldloc.0
0x99b82f  ldstr    aDaystyleFontIt// "DayStyle.Font.Italic"
0x99b834  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b839  pop
0x99b83a  ldloc.0
0x99b83b  ldstr    aDaystyleFontNa// "DayStyle.Font.Name"
0x99b840  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b845  pop
0x99b846  ldloc.0
0x99b847  ldstr    aDaystyleFontNa_0// "DayStyle.Font.Names"
0x99b84c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b851  pop
0x99b852  ldloc.0
0x99b853  ldstr    aDaystyleFontOv// "DayStyle.Font.Overline"
0x99b858  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x99b85d  pop
0x99b85e  ldloc.0
0x99b85f  ldstr    aDaystyleFontSi// "DayStyle.Font.Size"
  ... truncated ...
```
