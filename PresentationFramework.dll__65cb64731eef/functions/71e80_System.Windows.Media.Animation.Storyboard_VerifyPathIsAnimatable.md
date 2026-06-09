# System.Windows.Media.Animation.Storyboard::VerifyPathIsAnimatable

- ea: `0x71e80`
- end: `0x72075`
- name: `System.Windows.Media.Animation.Storyboard::VerifyPathIsAnimatable`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x71b20`

## callees

- `0x18bf0`
- `0x18c30`
- `0x18d50`
- `0x18d60`
- `0x38c70`
- `0x71e80`
- `0x72080`

## string_xrefs

- `0x71fd4`: `Storyboard_PropertyPathMustPointToDependencyProperty`
- `0x71ea5`: `Storyboard_PropertyPathObjectNotFound`
- `0x71ed4`: `Storyboard_PropertyPathPropertyNotFound`
- `0x71f28`: `Storyboard_PropertyPathFrozenCheckFailed`
- `0x71fa4`: `Storyboard_PropertyPathMustPointToDependencyObject`
- `0x71fff`: `Storyboard_PropertyPathSealedCheckFailed`
- `0x72038`: `Storyboard_PropertyPathIncludesNonAnimatableProperty`

## pseudocode

```c

```

## disassembly

```asm
0x71e80  ldnull
0x71e81  stloc.0
0x71e82  ldnull
0x71e83  stloc.1
0x71e84  ldc.i4.1
0x71e85  stloc.2
0x71e86  ldnull
0x71e87  stloc.3
0x71e88  ldc.i4.0
0x71e89  stloc.s  4
0x71e8b  br       loc_72067
0x71e90  ldarg.0
0x71e91  ldloc.s  4
0x71e93  callvirt instance object System.Windows.PropertyPath::GetItem(int32 k)
0x71e98  stloc.0
0x71e99  ldarg.0
0x71e9a  ldloc.s  4
0x71e9c  callvirt instance object System.Windows.PropertyPath::GetAccessor(int32 k)
0x71ea1  stloc.1
0x71ea2  ldloc.0
0x71ea3  brtrue.s loc_71ED1
0x71ea5  ldstr    aStoryboardProp_1// "Storyboard_PropertyPathObjectNotFound"
0x71eaa  ldc.i4.2
0x71eab  newarr   [mscorlib]System.Object
0x71eb0  dup
0x71eb1  ldc.i4.0
0x71eb2  ldarg.0
0x71eb3  ldloc.s  4
0x71eb5  ldc.i4.1
0x71eb6  sub
0x71eb7  call     string System.Windows.Media.Animation.Storyboard::AccessorName(class System.Windows.PropertyPath path, int32 index)
0x71ebc  stelem.ref
0x71ebd  dup
0x71ebe  ldc.i4.1
0x71ebf  ldarg.0
0x71ec0  callvirt instance string System.Windows.PropertyPath::get_Path()
0x71ec5  stelem.ref
0x71ec6  call     string System.Windows.SR::Get(string id, object[] args)
0x71ecb  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71ed0  throw
0x71ed1  ldloc.1
0x71ed2  brtrue.s loc_71EF3
0x71ed4  ldstr    aStoryboardProp_2// "Storyboard_PropertyPathPropertyNotFound"
0x71ed9  ldc.i4.1
0x71eda  newarr   [mscorlib]System.Object
0x71edf  dup
0x71ee0  ldc.i4.0
0x71ee1  ldarg.0
0x71ee2  callvirt instance string System.Windows.PropertyPath::get_Path()
0x71ee7  stelem.ref
0x71ee8  call     string System.Windows.SR::Get(string id, object[] args)
0x71eed  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71ef2  throw
0x71ef3  ldloc.s  4
0x71ef5  ldc.i4.1
0x71ef6  bne.un.s loc_71F0E
0x71ef8  ldloc.0
0x71ef9  isinst   [WindowsBase]System.Windows.Freezable
0x71efe  stloc.3
0x71eff  ldloc.3
0x71f00  brfalse.s loc_71F81
0x71f02  ldloc.3
0x71f03  callvirt instance bool [WindowsBase]System.Windows.Freezable::get_IsFrozen()
0x71f08  brfalse.s loc_71F81
0x71f0a  ldc.i4.0
0x71f0b  stloc.2
0x71f0c  br.s     loc_71F81
0x71f0e  ldloc.2
0x71f0f  brfalse.s loc_71F81
0x71f11  ldloc.0
0x71f12  isinst   [WindowsBase]System.Windows.Freezable
0x71f17  stloc.3
0x71f18  ldloc.3
0x71f19  brfalse.s loc_71F81
0x71f1b  ldloc.3
0x71f1c  callvirt instance bool [WindowsBase]System.Windows.Freezable::get_IsFrozen()
0x71f21  brfalse.s loc_71F81
0x71f23  ldloc.s  4
0x71f25  ldc.i4.0
0x71f26  ble.s    loc_71F62
0x71f28  ldstr    aStoryboardProp_3// "Storyboard_PropertyPathFrozenCheckFaile"...
0x71f2d  ldc.i4.3
0x71f2e  newarr   [mscorlib]System.Object
0x71f33  dup
0x71f34  ldc.i4.0
0x71f35  ldarg.0
0x71f36  ldloc.s  4
0x71f38  ldc.i4.1
0x71f39  sub
0x71f3a  call     string System.Windows.Media.Animation.Storyboard::AccessorName(class System.Windows.PropertyPath path, int32 index)
0x71f3f  stelem.ref
0x71f40  dup
0x71f41  ldc.i4.1
0x71f42  ldarg.0
0x71f43  callvirt instance string System.Windows.PropertyPath::get_Path()
0x71f48  stelem.ref
0x71f49  dup
0x71f4a  ldc.i4.2
0x71f4b  ldloc.3
0x71f4c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x71f51  callvirt instance string [mscorlib]System.Object::ToString()
0x71f56  stelem.ref
0x71f57  call     string System.Windows.SR::Get(string id, object[] args)
0x71f5c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71f61  throw
0x71f62  ldstr    aStoryboardImmu// "Storyboard_ImmutableTargetNotSupported"
0x71f67  ldc.i4.1
0x71f68  newarr   [mscorlib]System.Object
0x71f6d  dup
0x71f6e  ldc.i4.0
0x71f6f  ldarg.0
0x71f70  callvirt instance string System.Windows.PropertyPath::get_Path()
0x71f75  stelem.ref
0x71f76  call     string System.Windows.SR::Get(string id, object[] args)
0x71f7b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71f80  throw
0x71f81  ldloc.s  4
0x71f83  ldarg.0
0x71f84  callvirt instance int32 System.Windows.PropertyPath::get_Length()
0x71f89  ldc.i4.1
0x71f8a  sub
0x71f8b  bne.un   loc_72061
0x71f90  ldloc.0
0x71f91  isinst   [WindowsBase]System.Windows.DependencyObject
0x71f96  stloc.s  5
0x71f98  ldloc.1
0x71f99  isinst   [WindowsBase]System.Windows.DependencyProperty
0x71f9e  stloc.s  6
0x71fa0  ldloc.s  5
0x71fa2  brtrue.s loc_71FD0
0x71fa4  ldstr    aStoryboardProp_4// "Storyboard_PropertyPathMustPointToDepen"...
0x71fa9  ldc.i4.2
0x71faa  newarr   [mscorlib]System.Object
0x71faf  dup
0x71fb0  ldc.i4.0
0x71fb1  ldarg.0
0x71fb2  ldloc.s  4
0x71fb4  ldc.i4.1
0x71fb5  sub
0x71fb6  call     string System.Windows.Media.Animation.Storyboard::AccessorName(class System.Windows.PropertyPath path, int32 index)
0x71fbb  stelem.ref
0x71fbc  dup
0x71fbd  ldc.i4.1
0x71fbe  ldarg.0
0x71fbf  callvirt instance string System.Windows.PropertyPath::get_Path()
0x71fc4  stelem.ref
0x71fc5  call     string System.Windows.SR::Get(string id, object[] args)
0x71fca  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71fcf  throw
0x71fd0  ldloc.s  6
0x71fd2  brtrue.s loc_71FF3
0x71fd4  ldstr    aStoryboardProp_0// "Storyboard_PropertyPathMustPointToDepen"...
0x71fd9  ldc.i4.1
0x71fda  newarr   [mscorlib]System.Object
0x71fdf  dup
0x71fe0  ldc.i4.0
0x71fe1  ldarg.0
0x71fe2  callvirt instance string System.Windows.PropertyPath::get_Path()
0x71fe7  stelem.ref
0x71fe8  call     string System.Windows.SR::Get(string id, object[] args)
0x71fed  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71ff2  throw
0x71ff3  ldloc.2
0x71ff4  brfalse.s loc_7202D
0x71ff6  ldloc.s  5
0x71ff8  callvirt instance bool [WindowsBase]System.Windows.DependencyObject::get_IsSealed()
0x71ffd  brfalse.s loc_7202D
0x71fff  ldstr    aStoryboardProp_5// "Storyboard_PropertyPathSealedCheckFaile"...
0x72004  ldc.i4.3
0x72005  newarr   [mscorlib]System.Object
0x7200a  dup
0x7200b  ldc.i4.0
0x7200c  ldloc.s  6
0x7200e  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x72013  stelem.ref
0x72014  dup
0x72015  ldc.i4.1
0x72016  ldarg.0
0x72017  callvirt instance string System.Windows.PropertyPath::get_Path()
0x7201c  stelem.ref
0x7201d  dup
0x7201e  ldc.i4.2
0x7201f  ldloc.s  5
0x72021  stelem.ref
0x72022  call     string System.Windows.SR::Get(string id, object[] args)
0x72027  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7202c  throw
0x7202d  ldloc.s  5
0x7202f  ldloc.s  6
0x72031  call     bool [PresentationCore]System.Windows.Media.Animation.AnimationStorage::IsPropertyAnimatable(class [WindowsBase]System.Windows.DependencyObject, class [WindowsBase]System.Windows.DependencyProperty)
0x72036  brtrue.s loc_72061
0x72038  ldstr    aStoryboardProp_6// "Storyboard_PropertyPathIncludesNonAnima"...
0x7203d  ldc.i4.2
0x7203e  newarr   [mscorlib]System.Object
0x72043  dup
0x72044  ldc.i4.0
0x72045  ldarg.0
0x72046  callvirt instance string System.Windows.PropertyPath::get_Path()
0x7204b  stelem.ref
0x7204c  dup
0x7204d  ldc.i4.1
0x7204e  ldloc.s  6
0x72050  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x72055  stelem.ref
0x72056  call     string System.Windows.SR::Get(string id, object[] args)
0x7205b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x72060  throw
0x72061  ldloc.s  4
0x72063  ldc.i4.1
0x72064  add
0x72065  stloc.s  4
0x72067  ldloc.s  4
0x72069  ldarg.0
0x7206a  callvirt instance int32 System.Windows.PropertyPath::get_Length()
0x7206f  blt      loc_71E90
0x72074  ret
```
