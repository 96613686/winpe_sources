# System.Deployment.Application.UpdateCheckInfo::RaiseExceptionIfUpdateNotAvailable

- ea: `0xd330`
- end: `0xd349`
- name: `System.Deployment.Application.UpdateCheckInfo::RaiseExceptionIfUpdateNotAvailable`
- size: `25`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0xd2f0`
- `0xd300`
- `0xd310`
- `0xd320`

## callees

- `0xd2e0`
- `0xd330`
- `0x23020`

## string_xrefs

- `0xd338`: `Ex_UpdateNotAvailable`

## pseudocode

```c

```

## disassembly

```asm
0xd330  ldarg.0
0xd331  call     instance bool System.Deployment.Application.UpdateCheckInfo::get_UpdateAvailable()
0xd336  brtrue.s loc_D348
0xd338  ldstr    aExUpdatenotava// "Ex_UpdateNotAvailable"
0xd33d  call     string System.Deployment.Application.Resources::GetString(string s)
0xd342  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xd347  throw
0xd348  ret
```
