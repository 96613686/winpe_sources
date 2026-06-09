# Microsoft.Windows.Diagnosis.Network.FirewallApi.DiagnosticAppInfo::.ctor

- ea: `0x1f0`
- end: `0x205`
- name: `Microsoft.Windows.Diagnosis.Network.FirewallApi.DiagnosticAppInfo::.ctor`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3a0`

## callees

- `0x220`
- `0x240`

## pseudocode

```c

```

## disassembly

```asm
0x1f0  ldarg.0
0x1f1  call     instance void [mscorlib]System.Object::.ctor()
0x1f6  ldarg.0
0x1f7  ldarg.1
0x1f8  call     instance void Microsoft.Windows.Diagnosis.Network.FirewallApi.DiagnosticAppInfo::set_FriendlyName(string value)
0x1fd  ldarg.0
0x1fe  ldarg.2
0x1ff  call     instance void Microsoft.Windows.Diagnosis.Network.FirewallApi.DiagnosticAppInfo::set_Path(string value)
0x204  ret
```
