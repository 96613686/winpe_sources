# Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::GetControllerKey

- ea: `0x2b0`
- end: `0x2e1`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::GetControllerKey`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa0`
- `0x150`

## callees

- `0x2b0`

## pseudocode

```c

```

## disassembly

```asm
0x2b0  ldarg.1
0x2b1  ldstr    aController_0// "Controller"
0x2b6  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x2bb  brfalse.s loc_2CF
0x2bd  ldarg.1
0x2be  ldc.i4.0
0x2bf  ldarg.1
0x2c0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2c5  ldc.i4.s 0xA
0x2c7  sub
0x2c8  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2cd  starg.s  1
0x2cf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2d4  ldstr    a01// "{0}.{1}"
0x2d9  ldarg.0
0x2da  ldarg.1
0x2db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x2e0  ret
```
