# Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataPathRewriteHelper::UrlEncodeComponent

- ea: `0x780`
- end: `0x812`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataPathRewriteHelper::UrlEncodeComponent`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x750`

## callees

- `0x780`

## pseudocode

```c

```

## disassembly

```asm
0x780  ldarg.0
0x781  ldarg.1
0x782  callvirt instance class [System]System.Text.RegularExpressions.MatchCollection [System]System.Text.RegularExpressions.Regex::Matches(string)
0x787  stloc.0
0x788  ldloc.0
0x789  callvirt instance int32 [System]System.Text.RegularExpressions.MatchCollection::get_Count()
0x78e  ldc.i4.0
0x78f  ble.s    loc_810
0x791  ldloc.0
0x792  ldc.i4.0
0x793  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.MatchCollection::get_Item(int32)
0x798  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x79d  ldstr    aVal// "val"
0x7a2  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x7a7  stloc.1
0x7a8  ldarg.1
0x7a9  ldc.i4.0
0x7aa  ldloc.1
0x7ab  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x7b0  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x7b5  ldarg.1
0x7b6  ldloc.1
0x7b7  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x7bc  ldloc.1
0x7bd  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x7c2  add
0x7c3  callvirt instance string [mscorlib]System.String::Substring(int32)
0x7c8  stloc.2
0x7c9  ldloc.1
0x7ca  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x7cf  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x7d4  brtrue.s loc_7DE
0x7d6  ldloc.1
0x7d7  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x7dc  br.s     loc_7DF
0x7de  ldarg.2
0x7df  ldstr    asc_1043E// "'"
0x7e4  ldstr    asc_10442// "''"
0x7e9  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x7ee  call     string [System]System.Net.WebUtility::UrlDecode(string)
0x7f3  call     string [System]System.Net.WebUtility::UrlEncode(string)
0x7f8  ldstr    asc_10448// "+"
0x7fd  ldstr    a20// "%20"
0x802  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x807  stloc.3
0x808  ldloc.3
0x809  ldloc.2
0x80a  call     string [mscorlib]System.String::Concat(string, string, string)
0x80f  ret
0x810  ldarg.1
0x811  ret
```
