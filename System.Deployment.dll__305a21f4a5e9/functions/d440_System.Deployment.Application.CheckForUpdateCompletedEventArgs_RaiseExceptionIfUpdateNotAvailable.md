# System.Deployment.Application.CheckForUpdateCompletedEventArgs::RaiseExceptionIfUpdateNotAvailable

- ea: `0xd440`
- end: `0xd459`
- name: `System.Deployment.Application.CheckForUpdateCompletedEventArgs::RaiseExceptionIfUpdateNotAvailable`
- size: `25`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd400`
- `0xd410`
- `0xd420`
- `0xd430`

## callees

- `0xd3f0`
- `0xd440`
- `0x23020`

## string_xrefs

- `0xd448`: `Ex_UpdateNotAvailable`

## pseudocode

```c

```

## disassembly

```asm
0xd440  ldarg.0
0xd441  call     instance bool System.Deployment.Application.CheckForUpdateCompletedEventArgs::get_UpdateAvailable()
0xd446  brtrue.s loc_D458
0xd448  ldstr    aExUpdatenotava// "Ex_UpdateNotAvailable"
0xd44d  call     string System.Deployment.Application.Resources::GetString(string s)
0xd452  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xd457  throw
0xd458  ret
```
