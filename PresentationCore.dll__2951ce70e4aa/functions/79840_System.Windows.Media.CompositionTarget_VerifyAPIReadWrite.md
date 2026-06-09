# System.Windows.Media.CompositionTarget::VerifyAPIReadWrite

- ea: `0x79840`
- end: `0x7986a`
- name: `System.Windows.Media.CompositionTarget::VerifyAPIReadWrite`
- size: `42`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x644b0`
- `0x64520`
- `0x79520`

## callees

- `0x750a0`
- `0x75a30`
- `0x79840`

## string_xrefs

- `0x7984e`: `CompositionTarget`

## pseudocode

```c

```

## disassembly

```asm
0x79840  ldarg.0
0x79841  call     instance void [WindowsBase]System.Windows.Threading.DispatcherObject::VerifyAccess()
0x79846  ldarg.0
0x79847  ldfld    bool System.Windows.Media.CompositionTarget::_isDisposed
0x7984c  brfalse.s loc_79859
0x7984e  ldstr    aCompositiontar_0// "CompositionTarget"
0x79853  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x79858  throw
0x79859  ldarg.0
0x7985a  call     instance class [WindowsBase]System.Windows.Threading.Dispatcher [WindowsBase]System.Windows.Threading.DispatcherObject::get_Dispatcher()
0x7985f  call     class System.Windows.Media.MediaContext System.Windows.Media.MediaContext::From(class [WindowsBase]System.Windows.Threading.Dispatcher dispatcher)
0x79864  callvirt instance void System.Windows.Media.MediaContext::VerifyWriteAccess()
0x79869  ret
```
