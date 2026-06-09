# System.Windows.Media.CompositionTarget::VerifyAPIReadOnly

- ea: `0x79820`
- end: `0x7983a`
- name: `System.Windows.Media.CompositionTarget::VerifyAPIReadOnly`
- size: `26`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x64430`
- `0x64460`
- `0x644a0`
- `0x64510`
- `0x79500`
- `0xa93c0`
- `0xa93e0`

## callees

- `0x79820`

## string_xrefs

- `0x7982e`: `CompositionTarget`

## pseudocode

```c

```

## disassembly

```asm
0x79820  ldarg.0
0x79821  call     instance void [WindowsBase]System.Windows.Threading.DispatcherObject::VerifyAccess()
0x79826  ldarg.0
0x79827  ldfld    bool System.Windows.Media.CompositionTarget::_isDisposed
0x7982c  brfalse.s loc_79839
0x7982e  ldstr    aCompositiontar_0// "CompositionTarget"
0x79833  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x79838  throw
0x79839  ret
```
