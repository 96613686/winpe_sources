# System.Windows.Media.Media3D.Visual3D::RemoveVisual3DChild

- ea: `0xbac40`
- end: `0xbacdf`
- name: `System.Windows.Media.Media3D.Visual3D::RemoveVisual3DChild`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0xbb360`

## callees

- `0x60930`
- `0x60a40`
- `0xbac40`
- `0xbae10`
- `0xbaf90`
- `0xbb300`
- `0xbbb60`
- `0xbbb90`
- `0xbbbd0`
- `0xbbcb0`
- `0x104c60`
- `0x104ee0`
- `0x146e40`
- `0x152be0`
- `0x152c10`

## string_xrefs

- `0xbac48`: `CannotModifyVisualChildrenDuringTreeWalk`

## pseudocode

```c

```

## disassembly

```asm
0xbac40  ldarg.0
0xbac41  call     instance bool System.Windows.Media.Media3D.Visual3D::get_IsVisualChildrenIterationInProgress()
0xbac46  brfalse.s loc_BAC58
0xbac48  ldstr    aCannotmodifyvi// "CannotModifyVisualChildrenDuringTreeWal"...
0xbac4d  call     string MS.Internal.PresentationCore.SR::Get(string id)
0xbac52  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xbac57  throw
0xbac58  ldarg.0
0xbac59  call     void System.Windows.Diagnostics.VisualDiagnostics::VerifyVisualTreeChange(class [WindowsBase]System.Windows.DependencyObject d)
0xbac5e  ldarg.0
0xbac5f  ldarg.1
0xbac60  ldc.i4.0
0xbac61  call     void System.Windows.Diagnostics.VisualDiagnostics::OnVisualChildChanged(class [WindowsBase]System.Windows.DependencyObject parent, class [WindowsBase]System.Windows.DependencyObject child, bool isAdded)
0xbac66  ldarg.1
0xbac67  ldnull
0xbac68  callvirt instance void System.Windows.Media.Media3D.Visual3D::SetParent(class System.Windows.Media.Media3D.Visual3D newParent)
0xbac6d  ldarg.0
0xbac6e  ldarg.1
0xbac6f  ldnull
0xbac70  call     instance bool [WindowsBase]System.Windows.DependencyObject::RemoveSelfAsInheritanceContext(class [WindowsBase]System.Windows.DependencyObject, class [WindowsBase]System.Windows.DependencyProperty)
0xbac75  pop
0xbac76  ldc.i4.0
0xbac77  stloc.1
0xbac78  ldarg.0
0xbac79  ldflda   valuetype System.Windows.Media.Composition.VisualProxy System.Windows.Media.Media3D.Visual3D::_proxy
0xbac7e  call     instance int32 System.Windows.Media.Composition.VisualProxy::get_Count()
0xbac83  stloc.3
0xbac84  br.s     loc_BACC3
0xbac86  ldarg.0
0xbac87  ldflda   valuetype System.Windows.Media.Composition.VisualProxy System.Windows.Media.Media3D.Visual3D::_proxy
0xbac8c  ldloc.1
0xbac8d  call     instance class Channel System.Windows.Media.Composition.VisualProxy::GetChannel(int32 index)
0xbac92  stloc.0
0xbac93  ldarg.1
0xbac94  ldloc.0
0xbac95  ldc.i4   0x1000
0xbac9a  callvirt instance bool System.Windows.Media.Media3D.Visual3D::CheckFlagsAnd(class Channel channel, valuetype System.Windows.Media.VisualProxyFlags flagsToCheck)
0xbac9f  brfalse.s loc_BACBF
0xbaca1  ldarg.1
0xbaca2  ldloc.0
0xbaca3  ldc.i4.0
0xbaca4  ldc.i4   0x1000
0xbaca9  callvirt instance void System.Windows.Media.Media3D.Visual3D::SetFlags(class Channel channel, bool value, valuetype System.Windows.Media.VisualProxyFlags flagsToChange)
0xbacae  ldarg.1
0xbacaf  stloc.2
0xbacb0  ldloc.2
0xbacb1  ldarg.0
0xbacb2  ldloc.0
0xbacb3  callvirt instance void IResource::RemoveChildFromParent(class IResource parent, class Channel channel)
0xbacb8  ldloc.2
0xbacb9  ldloc.0
0xbacba  callvirt instance void IResource::ReleaseOnChannel(class Channel channel)
0xbacbf  ldloc.1
0xbacc0  ldc.i4.1
0xbacc1  add
0xbacc2  stloc.1
0xbacc3  ldloc.1
0xbacc4  ldloc.3
0xbacc5  blt.s    loc_BAC86
0xbacc7  ldarg.0
0xbacc8  ldc.i4.1
0xbacc9  ldc.i4.1
0xbacca  call     void System.Windows.Media.Media3D.Visual3D::PropagateFlags(class System.Windows.Media.Media3D.Visual3D e, valuetype System.Windows.Media.VisualFlags flags, valuetype System.Windows.Media.VisualProxyFlags proxyFlags)
0xbaccf  ldarg.1
0xbacd0  ldarg.0
0xbacd1  callvirt instance void System.Windows.Media.Media3D.Visual3D::FireOnVisualParentChanged(class [WindowsBase]System.Windows.DependencyObject oldParent)
0xbacd6  ldarg.0
0xbacd7  ldnull
0xbacd8  ldarg.1
0xbacd9  callvirt instance void System.Windows.Media.Media3D.Visual3D::OnVisualChildrenChanged(class [WindowsBase]System.Windows.DependencyObject visualAdded, class [WindowsBase]System.Windows.DependencyObject visualRemoved)
0xbacde  ret
```
