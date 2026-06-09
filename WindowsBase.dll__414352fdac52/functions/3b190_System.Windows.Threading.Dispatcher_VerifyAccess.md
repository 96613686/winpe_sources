# System.Windows.Threading.Dispatcher::VerifyAccess

- ea: `0x3b190`
- end: `0x3b1a9`
- name: `System.Windows.Threading.Dispatcher::VerifyAccess`
- size: `25`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x3bba0`
- `0x3d3c0`
- `0x3d510`

## callees

- `0x2c100`
- `0x3b180`
- `0x3b190`

## string_xrefs

- `0x3b198`: `VerifyAccess`

## pseudocode

```c

```

## disassembly

```asm
0x3b190  ldarg.0
0x3b191  call     instance bool System.Windows.Threading.Dispatcher::CheckAccess()
0x3b196  brtrue.s loc_3B1A8
0x3b198  ldstr    aVerifyaccess// "VerifyAccess"
0x3b19d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x3b1a2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3b1a7  throw
0x3b1a8  ret
```
