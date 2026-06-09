# System.Windows.Media.Media3D.Viewport3DVisual::MS.Internal.IVisual3DContainer.RemoveChild

- ea: `0xba370`
- end: `0xba42c`
- name: `System.Windows.Media.Media3D.Viewport3DVisual::MS.Internal.IVisual3DContainer.RemoveChild`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x60930`
- `0x60a40`
- `0xa5560`
- `0xa78d0`
- `0xa81a0`
- `0xa8460`
- `0xba370`
- `0xbae10`
- `0xbb2e0`
- `0xbbb40`
- `0xbbb90`
- `0xbbbd0`
- `0x104c60`
- `0x104ee0`
- `0x146e40`
- `0x152be0`
- `0x152c10`

## string_xrefs

- `0xba380`: `CannotModifyVisualChildrenDuringTreeWalk`

## pseudocode

```c

```

## disassembly

```asm
0xba370  ldarg.1
0xba371  callvirt instance int32 System.Windows.Media.Media3D.Visual3D::get_ParentIndex()
0xba376  stloc.s  4
0xba378  ldarg.0
0xba379  call     instance bool System.Windows.Media.Visual::get_IsVisualChildrenIterationInProgress()
0xba37e  brfalse.s loc_BA390
0xba380  ldstr    aCannotmodifyvi// "CannotModifyVisualChildrenDuringTreeWal"...
0xba385  call     string MS.Internal.PresentationCore.SR::Get(string id)
0xba38a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xba38f  throw
0xba390  ldarg.0
0xba391  call     void System.Windows.Diagnostics.VisualDiagnostics::VerifyVisualTreeChange(class [WindowsBase]System.Windows.DependencyObject d)
0xba396  ldarg.0
0xba397  ldarg.1
0xba398  ldc.i4.0
0xba399  call     void System.Windows.Diagnostics.VisualDiagnostics::OnVisualChildChanged(class [WindowsBase]System.Windows.DependencyObject parent, class [WindowsBase]System.Windows.DependencyObject child, bool isAdded)
0xba39e  ldarg.1
0xba39f  ldnull
0xba3a0  callvirt instance void System.Windows.Media.Media3D.Visual3D::SetParent(class System.Windows.Media.Visual newParent)
0xba3a5  ldarg.0
0xba3a6  ldfld    class [WindowsBase]System.Windows.DependencyObject System.Windows.Media.Media3D.Viewport3DVisual::_inheritanceContextForChildren
0xba3ab  brfalse.s loc_BA3BB
0xba3ad  ldarg.0
0xba3ae  ldfld    class [WindowsBase]System.Windows.DependencyObject System.Windows.Media.Media3D.Viewport3DVisual::_inheritanceContextForChildren
0xba3b3  ldarg.1
0xba3b4  ldnull
0xba3b5  callvirt instance bool [WindowsBase]System.Windows.DependencyObject::RemoveSelfAsInheritanceContext(class [WindowsBase]System.Windows.DependencyObject, class [WindowsBase]System.Windows.DependencyProperty)
0xba3ba  pop
0xba3bb  ldc.i4.0
0xba3bc  stloc.1
0xba3bd  ldarg.0
0xba3be  ldflda   valuetype System.Windows.Media.Composition.VisualProxy System.Windows.Media.Media3D.Viewport3DVisual::_proxy3D
0xba3c3  call     instance int32 System.Windows.Media.Composition.VisualProxy::get_Count()
0xba3c8  stloc.3
0xba3c9  br.s     loc_BA408
0xba3cb  ldarg.0
0xba3cc  ldflda   valuetype System.Windows.Media.Composition.VisualProxy System.Windows.Media.Media3D.Viewport3DVisual::_proxy3D
0xba3d1  ldloc.1
0xba3d2  call     instance class Channel System.Windows.Media.Composition.VisualProxy::GetChannel(int32 index)
0xba3d7  stloc.0
0xba3d8  ldarg.1
0xba3d9  ldloc.0
0xba3da  ldc.i4   0x1000
0xba3df  callvirt instance bool System.Windows.Media.Media3D.Visual3D::CheckFlagsAnd(class Channel channel, valuetype System.Windows.Media.VisualProxyFlags flagsToCheck)
0xba3e4  brfalse.s loc_BA404
0xba3e6  ldarg.1
0xba3e7  ldloc.0
0xba3e8  ldc.i4.0
0xba3e9  ldc.i4   0x1000
0xba3ee  callvirt instance void System.Windows.Media.Media3D.Visual3D::SetFlags(class Channel channel, bool value, valuetype System.Windows.Media.VisualProxyFlags flagsToChange)
0xba3f3  ldarg.1
0xba3f4  stloc.2
0xba3f5  ldloc.2
0xba3f6  ldarg.0
0xba3f7  ldloc.0
0xba3f8  callvirt instance void IResource::RemoveChildFromParent(class IResource parent, class Channel channel)
0xba3fd  ldloc.2
0xba3fe  ldloc.0
0xba3ff  callvirt instance void IResource::ReleaseOnChannel(class Channel channel)
0xba404  ldloc.1
0xba405  ldc.i4.1
0xba406  add
0xba407  stloc.1
0xba408  ldloc.1
0xba409  ldloc.3
0xba40a  blt.s    loc_BA3CB
0xba40c  ldarg.0
0xba40d  ldc.i4.1
0xba40e  ldc.i4.8
0xba40f  call     instance void System.Windows.Media.Visual::SetFlagsOnAllChannels(bool value, valuetype System.Windows.Media.VisualProxyFlags flagsToChange)
0xba414  ldarg.0
0xba415  ldc.i4.1
0xba416  ldc.i4.1
0xba417  call     void System.Windows.Media.Visual::PropagateFlags(class System.Windows.Media.Visual e, valuetype System.Windows.Media.VisualFlags flags, valuetype System.Windows.Media.VisualProxyFlags proxyFlags)
0xba41c  ldarg.1
0xba41d  ldarg.0
0xba41e  callvirt instance void System.Windows.Media.Media3D.Visual3D::FireOnVisualParentChanged(class [WindowsBase]System.Windows.DependencyObject oldParent)
0xba423  ldarg.0
0xba424  ldnull
0xba425  ldarg.1
0xba426  callvirt instance void System.Windows.Media.Visual::OnVisualChildrenChanged(class [WindowsBase]System.Windows.DependencyObject visualAdded, class [WindowsBase]System.Windows.DependencyObject visualRemoved)
0xba42b  ret
```
