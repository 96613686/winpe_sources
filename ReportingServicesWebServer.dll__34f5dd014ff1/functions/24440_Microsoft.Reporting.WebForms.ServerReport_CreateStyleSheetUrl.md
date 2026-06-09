# Microsoft.Reporting.WebForms.ServerReport::CreateStyleSheetUrl

- ea: `0x24440`
- end: `0x2447b`
- name: `Microsoft.Reporting.WebForms.ServerReport::CreateStyleSheetUrl`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x33c60`

## callees

- `0x24350`
- `0x24380`

## string_xrefs

- `0x24450`: `/Reserved.ReportServer?rs:command=StyleSheet&Name=`

## pseudocode

```c

```

## disassembly

```asm
0x24440  ldc.i4.5
0x24441  newarr   [mscorlib]System.String
0x24446  dup
0x24447  ldc.i4.0
0x24448  call     string Microsoft.Reporting.WebForms.ServerReport::get_RequestVirtualRoot()
0x2444d  stelem.ref
0x2444e  dup
0x2444f  ldc.i4.1
0x24450  ldstr    aReservedReport_0// "/Reserved.ReportServer?rs:command=Style"...
0x24455  stelem.ref
0x24456  dup
0x24457  ldc.i4.2
0x24458  ldarg.1
0x24459  call     string [System.Web]System.Web.HttpUtility::UrlEncode(string)
0x2445e  stelem.ref
0x2445f  dup
0x24460  ldc.i4.3
0x24461  ldstr    aVersion// "&Version="
0x24466  stelem.ref
0x24467  dup
0x24468  ldc.i4.4
0x24469  ldarg.0
0x2446a  call     instance string Microsoft.Reporting.WebForms.ServerReport::GetServerVersion()
0x2446f  call     string [System.Web]System.Web.HttpUtility::UrlEncode(string)
0x24474  stelem.ref
0x24475  call     string [mscorlib]System.String::Concat(string[])
0x2447a  ret
```
