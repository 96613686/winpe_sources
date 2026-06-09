# Microsoft.BIServer.BIService.ManagedProcess::GetProcessIdSafe

- ea: `0x1ff0`
- end: `0x2000`
- name: `Microsoft.BIServer.BIService.ManagedProcess::GetProcessIdSafe`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x3bc0`

## callees

- `0x1ff0`

## pseudocode

```c

```

## disassembly

```asm
0x1ff0  ldarg.0
0x1ff1  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x1ff6  stloc.0
0x1ff7  leave.s  loc_1FFE
0x1ff9  pop
0x1ffa  leave.s  loc_1FFC
0x1ffc  ldc.i4.m1
0x1ffd  ret
0x1ffe  ldloc.0
0x1fff  ret
```
