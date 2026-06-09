# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.WebHostingDialogBase::GetCultureName

- ea: `0x3400`
- end: `0x342b`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.WebHostingDialogBase::GetCultureName`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3380`
- `0x5a90`

## callees

- `0x3400`

## pseudocode

```c

```

## disassembly

```asm
0x3400  ldarg.0
0x3401  ldfld    string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.WebHostingDialogBase::cultureName
0x3406  brtrue.s loc_3424
0x3408  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x340d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x3412  stloc.0
0x3413  ldarg.0
0x3414  ldloc.0
0x3415  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Locale()
0x341a  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x341f  stfld    string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.WebHostingDialogBase::cultureName
0x3424  ldarg.0
0x3425  ldfld    string Microsoft.SharePoint.Spx.WebSite.ApplicationPages.WebHostingDialogBase::cultureName
0x342a  ret
```
