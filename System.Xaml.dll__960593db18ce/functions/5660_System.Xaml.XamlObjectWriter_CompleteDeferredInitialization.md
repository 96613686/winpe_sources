# System.Xaml.XamlObjectWriter::CompleteDeferredInitialization

- ea: `0x5660`
- end: `0x56c6`
- name: `System.Xaml.XamlObjectWriter::CompleteDeferredInitialization`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x5280`
- `0x5500`

## callees

- `0x27a0`
- `0x2870`
- `0x5660`
- `0x5a20`
- `0x201e0`
- `0x201f0`
- `0x20360`
- `0x20a40`
- `0x20a80`
- `0x20b40`

## pseudocode

```c

```

## disassembly

```asm
0x5660  ldarg.0
0x5661  ldarg.1
0x5662  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.FixupTarget::get_InstanceType()
0x5667  ldarg.1
0x5668  callvirt instance object MS.Internal.Xaml.Context.FixupTarget::get_Instance()
0x566d  call     instance void System.Xaml.XamlObjectWriter::ExecutePendingAdds(class System.Xaml.XamlType instanceType, object instance)
0x5672  ldarg.1
0x5673  callvirt instance bool MS.Internal.Xaml.Context.FixupTarget::get_InstanceWasGotten()
0x5678  brtrue.s loc_56C5
0x567a  ldarg.0
0x567b  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x5680  callvirt instance class MS.Internal.Xaml.Runtime.IAddLineInfo MS.Internal.Xaml.Runtime.XamlRuntime::get_LineInfo()
0x5685  stloc.0
0x5686  ldarg.0
0x5687  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x568c  ldarg.1
0x568d  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::set_LineInfo(class MS.Internal.Xaml.Runtime.IAddLineInfo value)
0x5692  ldarg.0
0x5693  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x5698  ldarg.1
0x5699  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.FixupTarget::get_InstanceType()
0x569e  ldarg.1
0x569f  callvirt instance object MS.Internal.Xaml.Context.FixupTarget::get_Instance()
0x56a4  ldc.i4.0
0x56a5  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::InitializationGuard(class System.Xaml.XamlType xamlType, object obj, bool begin)
0x56aa  leave.s  loc_56B9
0x56ac  ldarg.0
0x56ad  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x56b2  ldloc.0
0x56b3  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::set_LineInfo(class MS.Internal.Xaml.Runtime.IAddLineInfo value)
0x56b8  endfinally
0x56b9  ldarg.0
0x56ba  ldarg.1
0x56bb  callvirt instance object MS.Internal.Xaml.Context.FixupTarget::get_Instance()
0x56c0  callvirt instance void System.Xaml.XamlObjectWriter::OnAfterEndInit(object value)
0x56c5  ret
```
