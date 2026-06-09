# Microsoft.BIServer.Configuration.WMI.WmiException::.ctor_0

- ea: `0x4e90`
- end: `0x4e9f`
- name: `Microsoft.BIServer.Configuration.WMI.WmiException::.ctor_0`
- size: `15`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4fd0`
- `0x5170`
- `0x5280`
- `0x53a0`

## pseudocode

```c

```

## disassembly

```asm
0x4e90  ldarg.0
0x4e91  ldc.i4.m1
0x4e92  stfld    valuetype Microsoft.BIServer.Configuration.WMI.ErrorCodes Microsoft.BIServer.Configuration.WMI.WmiException::m_errorCode
0x4e97  ldarg.0
0x4e98  ldarg.1
0x4e99  call     instance void [mscorlib]System.Exception::.ctor(string)
0x4e9e  ret
```
