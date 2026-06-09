# Microsoft.ReportingServices.Common.XmlConvertEx::ToString_0

- ea: `0x1b90`
- end: `0x1ba5`
- name: `Microsoft.ReportingServices.Common.XmlConvertEx::ToString_0`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1b90`

## pseudocode

```c

```

## disassembly

```asm
0x1b90  ldarg.0
0x1b91  brtrue.s loc_1B9E
0x1b93  ldstr    aValue// "value"
0x1b98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1b9d  throw
0x1b9e  ldarg.0
0x1b9f  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x1ba4  ret
```
