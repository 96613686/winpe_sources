# Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataPathRewriteHelper::.cctor

- ea: `0x820`
- end: `0x843`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataPathRewriteHelper::.cctor`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x820`: `\((?:%20)*Path(?:%20)*=(?:%20)*'(?<val>.*?)'(?:%20)*\)`

## pseudocode

```c

```

## disassembly

```asm
0x820  ldstr    a20Path2020Val2// "\\((?:%20)*Path(?:%20)*=(?:%20)*'(?<val"...
0x825  ldc.i4.s 9
0x827  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x82c  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataPathRewriteHelper::PathComponent
0x831  ldstr    aSearchtextVal// "(?<=\\(searchText=')(?<val>.*?)(?='\\))"
0x836  ldc.i4.s 9
0x838  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x83d  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataPathRewriteHelper::SearchComponent
0x842  ret
```
