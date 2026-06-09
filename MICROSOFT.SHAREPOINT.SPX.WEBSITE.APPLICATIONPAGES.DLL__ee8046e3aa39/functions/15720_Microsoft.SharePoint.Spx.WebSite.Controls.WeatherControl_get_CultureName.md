# Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_CultureName

- ea: `0x15720`
- end: `0x15742`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::get_CultureName`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x15890`
- `0x15990`

## callees

- `0x15720`

## pseudocode

```c

```

## disassembly

```asm
0x15720  ldarg.0
0x15721  ldfld    string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::cultureName
0x15726  brfalse.s loc_1573C
0x15728  ldarg.0
0x15729  ldfld    string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::cultureName
0x1572e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15733  brfalse.s loc_1573C
0x15735  ldarg.0
0x15736  ldfld    string Microsoft.SharePoint.Spx.WebSite.Controls.WeatherControl::cultureName
0x1573b  ret
0x1573c  ldstr    aEnUs// "en-US"
0x15741  ret
```
