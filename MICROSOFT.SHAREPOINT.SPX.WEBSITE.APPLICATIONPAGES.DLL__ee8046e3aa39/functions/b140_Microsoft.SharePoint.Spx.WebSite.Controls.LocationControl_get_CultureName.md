# Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_CultureName

- ea: `0xb140`
- end: `0xb162`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::get_CultureName`
- size: `34`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb0c0`
- `0xb180`
- `0xba60`
- `0xc060`
- `0xc4b0`

## callees

- `0xb140`

## pseudocode

```c

```

## disassembly

```asm
0xb140  ldarg.0
0xb141  ldfld    string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::cultureName
0xb146  brfalse.s loc_B15C
0xb148  ldarg.0
0xb149  ldfld    string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::cultureName
0xb14e  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb153  brfalse.s loc_B15C
0xb155  ldarg.0
0xb156  ldfld    string Microsoft.SharePoint.Spx.WebSite.Controls.LocationControl::cultureName
0xb15b  ret
0xb15c  ldstr    aEnUs// "en-US"
0xb161  ret
```
