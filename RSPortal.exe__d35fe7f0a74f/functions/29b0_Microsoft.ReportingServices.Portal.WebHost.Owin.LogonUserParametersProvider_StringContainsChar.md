# Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::StringContainsChar

- ea: `0x29b0`
- end: `0x29c8`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.LogonUserParametersProvider::StringContainsChar`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2990`
- `0x29a0`

## callees

- `0x29b0`

## pseudocode

```c

```

## disassembly

```asm
0x29b0  ldarg.0
0x29b1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x29b6  brtrue.s loc_29C6
0x29b8  ldarg.0
0x29b9  ldarg.1
0x29ba  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x29bf  ldc.i4.0
0x29c0  clt
0x29c2  ldc.i4.0
0x29c3  ceq
0x29c5  ret
0x29c6  ldc.i4.0
0x29c7  ret
```
