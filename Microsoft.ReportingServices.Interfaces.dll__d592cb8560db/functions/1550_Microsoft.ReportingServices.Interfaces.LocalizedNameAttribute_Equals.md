# Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::Equals

- ea: `0x1550`
- end: `0x1577`
- name: `Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::Equals`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1520`
- `0x1550`

## pseudocode

```c

```

## disassembly

```asm
0x1550  ldarg.1
0x1551  ldarg.0
0x1552  bne.un.s loc_1556
0x1554  ldc.i4.1
0x1555  ret
0x1556  ldarg.1
0x1557  isinst   Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute
0x155c  brfalse.s loc_1575
0x155e  ldarg.0
0x155f  call     instance string Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::get_Name()
0x1564  ldarg.1
0x1565  castclass Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute
0x156a  callvirt instance string Microsoft.ReportingServices.Interfaces.LocalizedNameAttribute::get_Name()
0x156f  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1574  ret
0x1575  ldc.i4.0
0x1576  ret
```
