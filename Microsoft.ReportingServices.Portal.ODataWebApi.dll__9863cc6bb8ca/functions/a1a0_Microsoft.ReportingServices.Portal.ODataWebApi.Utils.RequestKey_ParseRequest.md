# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::ParseRequest

- ea: `0xa1a0`
- end: `0xa262`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::ParseRequest`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa170`

## callees

- `0xa1a0`

## string_xrefs

- `0xa1a1`: `Path='`

## pseudocode

```c

```

## disassembly

```asm
0xa1a0  ldarg.0
0xa1a1  ldstr    aPath_1// "Path='"
0xa1a6  stfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_path
0xa1ab  ldarg.0
0xa1ac  ldc.i4.0
0xa1ad  stfld    bool Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_isPath
0xa1b2  ldarg.1
0xa1b3  ldarg.0
0xa1b4  ldfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_path
0xa1b9  ldc.i4.5
0xa1ba  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xa1bf  brfalse.s loc_A20F
0xa1c1  ldarg.0
0xa1c2  ldc.i4.1
0xa1c3  stfld    bool Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_isPath
0xa1c8  ldarg.0
0xa1c9  ldarg.1
0xa1ca  ldarg.0
0xa1cb  ldfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_path
0xa1d0  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa1d5  ldarg.1
0xa1d6  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa1db  ldarg.0
0xa1dc  ldfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_path
0xa1e1  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa1e6  sub
0xa1e7  ldc.i4.1
0xa1e8  sub
0xa1e9  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xa1ee  stfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_path
0xa1f3  ldarg.0
0xa1f4  ldarg.0
0xa1f5  ldfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_path
0xa1fa  ldstr    asc_10442// "''"
0xa1ff  ldstr    asc_1043E// "'"
0xa204  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xa209  stfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_path
0xa20e  ret
0xa20f  ldarg.1
0xa210  ldarg.0
0xa211  ldflda   valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_id
0xa216  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xa21b  brtrue.s loc_A261
0xa21d  ldarg.1
0xa21e  ldstr    asc_12644// "'/"
0xa223  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0xa228  brfalse.s loc_A261
0xa22a  ldarg.0
0xa22b  ldarg.1
0xa22c  ldc.i4.1
0xa22d  ldarg.1
0xa22e  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa233  ldc.i4.2
0xa234  sub
0xa235  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xa23a  stfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_path
0xa23f  ldarg.0
0xa240  ldc.i4.1
0xa241  stfld    bool Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_isPath
0xa246  ldarg.0
0xa247  ldarg.0
0xa248  ldfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_path
0xa24d  ldstr    asc_10442// "''"
0xa252  ldstr    asc_1043E// "'"
0xa257  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xa25c  stfld    string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.RequestKey::_path
0xa261  ret
```
