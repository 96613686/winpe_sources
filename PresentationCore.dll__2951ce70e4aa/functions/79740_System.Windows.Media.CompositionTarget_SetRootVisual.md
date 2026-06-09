# System.Windows.Media.CompositionTarget::SetRootVisual

- ea: `0x79740`
- end: `0x797fc`
- name: `System.Windows.Media.CompositionTarget::SetRootVisual`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x79520`

## callees

- `0x750a0`
- `0x75c70`
- `0x79740`
- `0x79800`
- `0xa5580`
- `0xa5590`
- `0xa81a0`
- `0x146e40`
- `0x152180`
- `0x152be0`

## string_xrefs

- `0x79753`: `CompositionTarget_RootVisual_HasParent`

## pseudocode

```c

```

## disassembly

```asm
0x79740  ldarg.1
0x79741  brfalse.s loc_79763
0x79743  ldarg.1
0x79744  ldfld    class [WindowsBase]System.Windows.DependencyObject System.Windows.Media.Visual::_parent
0x79749  brtrue.s loc_79753
0x7974b  ldarg.1
0x7974c  callvirt instance bool System.Windows.Media.Visual::get_IsRootElement()
0x79751  brfalse.s loc_79763
0x79753  ldstr    aCompositiontar// "CompositionTarget_RootVisual_HasParent"
0x79758  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x7975d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x79762  throw
0x79763  ldarg.0
0x79764  call     instance class [WindowsBase]System.Windows.Threading.Dispatcher [WindowsBase]System.Windows.Threading.DispatcherObject::get_Dispatcher()
0x79769  call     class System.Windows.Media.MediaContext System.Windows.Media.MediaContext::From(class [WindowsBase]System.Windows.Threading.Dispatcher dispatcher)
0x7976e  callvirt instance valuetype ChannelSet System.Windows.Media.MediaContext::GetChannels()
0x79773  stloc.1
0x79774  ldloc.1
0x79775  ldfld    class Channel ChannelSet::Channel
0x7977a  stloc.0
0x7977b  ldarg.0
0x7977c  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual> System.Windows.Media.CompositionTarget::_rootVisual
0x79781  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual>::get_Value()
0x79786  brfalse.s loc_797BF
0x79788  ldarg.0
0x79789  ldflda   valuetype MultiChannelResource System.Windows.Media.CompositionTarget::_contentRoot
0x7978e  ldloc.0
0x7978f  call     instance bool MultiChannelResource::IsOnChannel(class Channel channel)
0x79794  brfalse.s loc_797BF
0x79796  ldarg.0
0x79797  ldloc.0
0x79798  call     instance void System.Windows.Media.CompositionTarget::ClearRootNode(class Channel channel)
0x7979d  ldarg.0
0x7979e  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual> System.Windows.Media.CompositionTarget::_rootVisual
0x797a3  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual>::get_Value()
0x797a8  ldloc.0
0x797a9  callvirt instance void IResource::ReleaseOnChannel(class Channel channel)
0x797ae  ldarg.0
0x797af  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual> System.Windows.Media.CompositionTarget::_rootVisual
0x797b4  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual>::get_Value()
0x797b9  ldc.i4.0
0x797ba  callvirt instance void System.Windows.Media.Visual::set_IsRootElement(bool value)
0x797bf  ldarg.0
0x797c0  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual> System.Windows.Media.CompositionTarget::_rootVisual
0x797c5  ldarg.1
0x797c6  call     instance void valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual>::set_Value(var<u1>)
0x797cb  ldarg.0
0x797cc  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual> System.Windows.Media.CompositionTarget::_rootVisual
0x797d1  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual>::get_Value()
0x797d6  brfalse.s loc_797FB
0x797d8  ldarg.0
0x797d9  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual> System.Windows.Media.CompositionTarget::_rootVisual
0x797de  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual>::get_Value()
0x797e3  ldc.i4.1
0x797e4  callvirt instance void System.Windows.Media.Visual::set_IsRootElement(bool value)
0x797e9  ldarg.0
0x797ea  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual> System.Windows.Media.CompositionTarget::_rootVisual
0x797ef  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<class System.Windows.Media.Visual>::get_Value()
0x797f4  ldc.i4.1
0x797f5  ldc.i4.1
0x797f6  callvirt instance void System.Windows.Media.Visual::SetFlagsOnAllChannels(bool value, valuetype System.Windows.Media.VisualProxyFlags flagsToChange)
0x797fb  ret
```
