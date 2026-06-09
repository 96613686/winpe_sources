# Microsoft.ReportingServices.Interfaces.Setting::get_ValidValues

- ea: `0xd20`
- end: `0xd3b`
- name: `Microsoft.ReportingServices.Interfaces.Setting::get_ValidValues`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xd20  ldarg.0
0xd21  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Interfaces.Setting::m_validValues
0xd26  ldtoken  Microsoft.ReportingServices.Interfaces.ValidValue
0xd2b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd30  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0xd35  isinst   class Microsoft.ReportingServices.Interfaces.ValidValue[]
0xd3a  ret
```
