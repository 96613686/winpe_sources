# Microsoft.ReportingServices.Common.XmlConvertEx::ToEnum

- ea: `0x1b70`
- end: `0x1b86`
- name: `Microsoft.ReportingServices.Common.XmlConvertEx::ToEnum`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1b70  ldtoken  mvar<u1>
0x1b75  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b7a  ldarg.0
0x1b7b  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x1b80  unbox.any mvar<u1>
0x1b85  ret
```
