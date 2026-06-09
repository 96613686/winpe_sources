# System.Deployment.Application.CompatibleFrameworkMissingException::.ctor

- ea: `0x149c0`
- end: `0x149d1`
- name: `System.Deployment.Application.CompatibleFrameworkMissingException::.ctor`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x149e0`
- `0x23020`

## string_xrefs

- `0x149c1`: `Ex_CompatibleFrameworkMissingException`

## pseudocode

```c

```

## disassembly

```asm
0x149c0  ldarg.0
0x149c1  ldstr    aExCompatiblefr_0// "Ex_CompatibleFrameworkMissingException"
0x149c6  call     string System.Deployment.Application.Resources::GetString(string s)
0x149cb  call     instance void System.Deployment.Application.CompatibleFrameworkMissingException::.ctor(string message)
0x149d0  ret
```
