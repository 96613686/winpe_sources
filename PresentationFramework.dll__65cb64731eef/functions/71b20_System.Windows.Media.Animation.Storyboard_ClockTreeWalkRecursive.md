# System.Windows.Media.Animation.Storyboard::ClockTreeWalkRecursive

- ea: `0x71b20`
- end: `0x71d2d`
- name: `System.Windows.Media.Animation.Storyboard::ClockTreeWalkRecursive`
- size: `525`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x71b20`
- `0x72440`

## callees

- `0x18bf0`
- `0x18c30`
- `0x18d40`
- `0x18d60`
- `0x38c40`
- `0x38c70`
- `0x71970`
- `0x71b20`
- `0x71d30`
- `0x71da0`
- `0x71e80`
- `0x720d0`
- `0x72110`
- `0x1d9cc0`
- `0x2624b0`

## string_xrefs

- `0x71c41`: `Storyboard_PropertyPathEmpty`
- `0x71c72`: `Storyboard_PropertyPathMustPointToDependencyProperty`

## pseudocode

```c

```

## disassembly

```asm
0x71b20  ldarg.1
0x71b21  callvirt instance class [PresentationCore]System.Windows.Media.Animation.Timeline [PresentationCore]System.Windows.Media.Animation.Clock::get_Timeline()
0x71b26  stloc.0
0x71b27  ldarg.s  4
0x71b29  stloc.1
0x71b2a  ldarg.s  5
0x71b2c  stloc.2
0x71b2d  ldarg.s  6
0x71b2f  stloc.3
0x71b30  ldloc.0
0x71b31  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Storyboard::TargetNameProperty
0x71b36  callvirt instance object [WindowsBase]System.Windows.DependencyObject::GetValue(class [WindowsBase]System.Windows.DependencyProperty)
0x71b3b  castclass [mscorlib]System.String
0x71b40  stloc.s  4
0x71b42  ldloc.s  4
0x71b44  brfalse.s loc_71B6C
0x71b46  ldarg.3
0x71b47  isinst   System.Windows.Style
0x71b4c  brfalse.s loc_71B69
0x71b4e  ldstr    aStoryboardTarg_0// "Storyboard_TargetNameNotAllowedInStyle"
0x71b53  ldc.i4.1
0x71b54  newarr   [mscorlib]System.Object
0x71b59  dup
0x71b5a  ldc.i4.0
0x71b5b  ldloc.s  4
0x71b5d  stelem.ref
0x71b5e  call     string System.Windows.SR::Get(string id, object[] args)
0x71b63  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71b68  throw
0x71b69  ldloc.s  4
0x71b6b  stloc.2
0x71b6c  ldloc.0
0x71b6d  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Storyboard::TargetProperty
0x71b72  callvirt instance object [WindowsBase]System.Windows.DependencyObject::GetValue(class [WindowsBase]System.Windows.DependencyProperty)
0x71b77  castclass [WindowsBase]System.Windows.DependencyObject
0x71b7c  stloc.s  5
0x71b7e  ldloc.s  5
0x71b80  brfalse.s loc_71B87
0x71b82  ldloc.s  5
0x71b84  stloc.1
0x71b85  ldnull
0x71b86  stloc.2
0x71b87  ldloc.0
0x71b88  ldsfld   class [WindowsBase]System.Windows.DependencyProperty System.Windows.Media.Animation.Storyboard::TargetPropertyProperty
0x71b8d  callvirt instance object [WindowsBase]System.Windows.DependencyObject::GetValue(class [WindowsBase]System.Windows.DependencyProperty)
0x71b92  castclass System.Windows.PropertyPath
0x71b97  stloc.s  6
0x71b99  ldloc.s  6
0x71b9b  brfalse.s loc_71BA0
0x71b9d  ldloc.s  6
0x71b9f  stloc.3
0x71ba0  ldarg.1
0x71ba1  isinst   [PresentationCore]System.Windows.Media.Animation.AnimationClock
0x71ba6  brfalse  loc_71CCF
0x71bab  ldnull
0x71bac  stloc.s  7
0x71bae  ldarg.1
0x71baf  castclass [PresentationCore]System.Windows.Media.Animation.AnimationClock
0x71bb4  stloc.s  8
0x71bb6  ldloc.1
0x71bb7  brtrue.s loc_71C08
0x71bb9  ldloc.2
0x71bba  brfalse.s loc_71BD0
0x71bbc  ldarg.2
0x71bbd  call     class [WindowsBase]System.Windows.DependencyObject MS.Internal.Helper::FindMentor(class [WindowsBase]System.Windows.DependencyObject d)
0x71bc2  stloc.s  9
0x71bc4  ldloc.2
0x71bc5  ldarg.3
0x71bc6  ldloc.s  9
0x71bc8  call     class [WindowsBase]System.Windows.DependencyObject System.Windows.Media.Animation.Storyboard::ResolveTargetName(string targetName, class [System.Xaml]System.Windows.Markup.INameScope nameScope, class [WindowsBase]System.Windows.DependencyObject element)
0x71bcd  stloc.1
0x71bce  br.s     loc_71C08
0x71bd0  ldarg.2
0x71bd1  isinst   System.Windows.FrameworkElement
0x71bd6  stloc.1
0x71bd7  ldloc.1
0x71bd8  brtrue.s loc_71BE1
0x71bda  ldarg.2
0x71bdb  isinst   System.Windows.FrameworkContentElement
0x71be0  stloc.1
0x71be1  ldloc.1
0x71be2  brtrue.s loc_71C08
0x71be4  ldstr    aStoryboardNota// "Storyboard_NoTarget"
0x71be9  ldc.i4.1
0x71bea  newarr   [mscorlib]System.Object
0x71bef  dup
0x71bf0  ldc.i4.0
0x71bf1  ldloc.0
0x71bf2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x71bf7  callvirt instance string [mscorlib]System.Object::ToString()
0x71bfc  stelem.ref
0x71bfd  call     string System.Windows.SR::Get(string id, object[] args)
0x71c02  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71c07  throw
0x71c08  ldloc.3
0x71c09  brtrue.s loc_71C2F
0x71c0b  ldstr    aStoryboardTarg_1// "Storyboard_TargetPropertyRequired"
0x71c10  ldc.i4.1
0x71c11  newarr   [mscorlib]System.Object
0x71c16  dup
0x71c17  ldc.i4.0
0x71c18  ldloc.0
0x71c19  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x71c1e  callvirt instance string [mscorlib]System.Object::ToString()
0x71c23  stelem.ref
0x71c24  call     string System.Windows.SR::Get(string id, object[] args)
0x71c29  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71c2e  throw
0x71c2f  ldloc.3
0x71c30  ldloc.1
0x71c31  callvirt instance class [mscorlib]System.IDisposable System.Windows.PropertyPath::SetContext(object rootItem)
0x71c36  stloc.s  0xA
0x71c38  ldloc.3
0x71c39  callvirt instance int32 System.Windows.PropertyPath::get_Length()
0x71c3e  ldc.i4.1
0x71c3f  bge.s    loc_71C51
0x71c41  ldstr    aStoryboardProp// "Storyboard_PropertyPathEmpty"
0x71c46  call     string System.Windows.SR::Get(string id)
0x71c4b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71c50  throw
0x71c51  ldloc.3
0x71c52  call     void System.Windows.Media.Animation.Storyboard::VerifyPathIsAnimatable(class System.Windows.PropertyPath path)
0x71c57  ldloc.3
0x71c58  callvirt instance int32 System.Windows.PropertyPath::get_Length()
0x71c5d  ldc.i4.1
0x71c5e  bne.un.s loc_71CB1
0x71c60  ldloc.3
0x71c61  ldc.i4.0
0x71c62  callvirt instance object System.Windows.PropertyPath::GetAccessor(int32 k)
0x71c67  isinst   [WindowsBase]System.Windows.DependencyProperty
0x71c6c  stloc.s  7
0x71c6e  ldloc.s  7
0x71c70  brtrue.s loc_71C91
0x71c72  ldstr    aStoryboardProp_0// "Storyboard_PropertyPathMustPointToDepen"...
0x71c77  ldc.i4.1
0x71c78  newarr   [mscorlib]System.Object
0x71c7d  dup
0x71c7e  ldc.i4.0
0x71c7f  ldloc.3
0x71c80  callvirt instance string System.Windows.PropertyPath::get_Path()
0x71c85  stelem.ref
0x71c86  call     string System.Windows.SR::Get(string id, object[] args)
0x71c8b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x71c90  throw
0x71c91  ldloc.s  7
0x71c93  ldloc.s  8
0x71c95  call     void System.Windows.Media.Animation.Storyboard::VerifyAnimationIsValid(class [WindowsBase]System.Windows.DependencyProperty targetProperty, class [PresentationCore]System.Windows.Media.Animation.AnimationClock animationClock)
0x71c9a  ldloc.1
0x71c9b  ldloc.s  7
0x71c9d  newobj   instance void ObjectPropertyPair::.ctor(class [WindowsBase]System.Windows.DependencyObject o, class [WindowsBase]System.Windows.DependencyProperty p)
0x71ca2  stloc.s  0xB
0x71ca4  ldarg.s  8
0x71ca6  ldloc.s  0xB
0x71ca8  ldloc.s  8
0x71caa  call     void System.Windows.Media.Animation.Storyboard::UpdateMappings(class [System]System.Collections.Specialized.HybridDictionary clockMappings, class ObjectPropertyPair mappingKey, class [PresentationCore]System.Windows.Media.Animation.AnimationClock animationClock)
0x71caf  leave.s  loc_71D2C
0x71cb1  ldarg.0
0x71cb2  ldarg.s  8
0x71cb4  ldloc.1
0x71cb5  ldloc.3
0x71cb6  ldloc.s  8
0x71cb8  ldarg.s  7
0x71cba  ldarg.s  9
0x71cbc  call     instance void System.Windows.Media.Animation.Storyboard::ProcessComplexPath(class [System]System.Collections.Specialized.HybridDictionary clockMappings, class [WindowsBase]System.Windows.DependencyObject targetObject, class System.Windows.PropertyPath path, class [PresentationCore]System.Windows.Media.Animation.AnimationClock animationClock, valuetype [PresentationCore]System.Windows.Media.Animation.HandoffBehavior handoffBehavior, int64 layer)
0x71cc1  leave.s  loc_71D2C
0x71cc3  ldloc.s  0xA
0x71cc5  brfalse.s loc_71CCE
0x71cc7  ldloc.s  0xA
0x71cc9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x71cce  endfinally
0x71ccf  ldarg.1
0x71cd0  isinst   [PresentationCore]System.Windows.Media.MediaClock
0x71cd5  brfalse.s loc_71CE7
0x71cd7  ldarg.3
0x71cd8  ldarg.2
0x71cd9  ldloc.1
0x71cda  ldloc.2
0x71cdb  ldarg.1
0x71cdc  castclass [PresentationCore]System.Windows.Media.MediaClock
0x71ce1  call     void System.Windows.Media.Animation.Storyboard::ApplyMediaClock(class [System.Xaml]System.Windows.Markup.INameScope nameScope, class [WindowsBase]System.Windows.DependencyObject containingObject, class [WindowsBase]System.Windows.DependencyObject currentObject, string currentObjectName, class [PresentationCore]System.Windows.Media.MediaClock mediaClock)
0x71ce6  ret
0x71ce7  ldarg.1
0x71ce8  isinst   [PresentationCore]System.Windows.Media.Animation.ClockGroup
0x71ced  stloc.s  0xC
0x71cef  ldloc.s  0xC
0x71cf1  brfalse.s loc_71D2C
0x71cf3  ldloc.s  0xC
0x71cf5  callvirt instance class [PresentationCore]System.Windows.Media.Animation.ClockCollection [PresentationCore]System.Windows.Media.Animation.ClockGroup::get_Children()
0x71cfa  stloc.s  0xD
0x71cfc  ldc.i4.0
0x71cfd  stloc.s  0xE
0x71cff  br.s     loc_71D21
0x71d01  ldarg.0
0x71d02  ldloc.s  0xD
0x71d04  ldloc.s  0xE
0x71d06  callvirt instance class [PresentationCore]System.Windows.Media.Animation.Clock [PresentationCore]System.Windows.Media.Animation.ClockCollection::get_Item(int32)
0x71d0b  ldarg.2
0x71d0c  ldarg.3
0x71d0d  ldloc.1
0x71d0e  ldloc.2
0x71d0f  ldloc.3
0x71d10  ldarg.s  7
0x71d12  ldarg.s  8
0x71d14  ldarg.s  9
0x71d16  call     instance void System.Windows.Media.Animation.Storyboard::ClockTreeWalkRecursive(class [PresentationCore]System.Windows.Media.Animation.Clock currentClock, class [WindowsBase]System.Windows.DependencyObject containingObject, class [System.Xaml]System.Windows.Markup.INameScope nameScope, class [WindowsBase]System.Windows.DependencyObject parentObject, string parentObjectName, class System.Windows.PropertyPath parentPropertyPath, valuetype [PresentationCore]System.Windows.Media.Animation.HandoffBehavior handoffBehavior, class [System]System.Collections.Specialized.HybridDictionary clockMappings, int64 layer)
0x71d1b  ldloc.s  0xE
0x71d1d  ldc.i4.1
0x71d1e  add
0x71d1f  stloc.s  0xE
0x71d21  ldloc.s  0xE
0x71d23  ldloc.s  0xD
0x71d25  callvirt instance int32 [PresentationCore]System.Windows.Media.Animation.ClockCollection::get_Count()
0x71d2a  blt.s    loc_71D01
0x71d2c  ret
```
