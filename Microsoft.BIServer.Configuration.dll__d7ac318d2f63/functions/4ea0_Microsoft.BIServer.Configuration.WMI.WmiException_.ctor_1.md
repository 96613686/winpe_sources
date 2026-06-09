# Microsoft.BIServer.Configuration.WMI.WmiException::.ctor_1

- ea: `0x4ea0`
- end: `0x4eb0`
- name: `Microsoft.BIServer.Configuration.WMI.WmiException::.ctor_1`
- size: `16`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x57c0`
- `0x5820`
- `0x5a60`

## pseudocode

```c

```

## disassembly

```asm
0x4ea0  ldarg.0
0x4ea1  ldc.i4.m1
0x4ea2  stfld    valuetype Microsoft.BIServer.Configuration.WMI.ErrorCodes Microsoft.BIServer.Configuration.WMI.WmiException::m_errorCode
0x4ea7  ldarg.0
0x4ea8  ldarg.1
0x4ea9  ldarg.2
0x4eaa  call     instance void [mscorlib]System.Exception::.ctor(string, class [mscorlib]System.Exception)
0x4eaf  ret
```
