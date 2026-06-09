# System.Windows.Input.StylusPlugIns.StylusPlugInCollection::SetItem

- ea: `0x5b5b0`
- end: `0x5b62a`
- name: `System.Windows.Input.StylusPlugIns.StylusPlugInCollection::SetItem`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x5b5b0`
- `0x5b9e0`
- `0x146e40`
- `0x14a840`

## string_xrefs

- `0x5b5de`: `plugIn`
- `0x5b60c`: `plugIn`
- `0x5b5e3`: `Stylus_PlugInIsNull`
- `0x5b602`: `Stylus_PlugInIsDuplicated`

## pseudocode

```c

```

## disassembly

```asm
0x5b5b0  newobj   instance void <>c__DisplayClass3_0::.ctor()
0x5b5b5  stloc.0
0x5b5b6  ldloc.0
0x5b5b7  ldarg.0
0x5b5b8  stfld    class System.Windows.Input.StylusPlugIns.StylusPlugInCollection <>c__DisplayClass3_0::<>4__this
0x5b5bd  ldloc.0
0x5b5be  ldarg.1
0x5b5bf  stfld    int32 <>c__DisplayClass3_0::index
0x5b5c4  ldloc.0
0x5b5c5  ldarg.2
0x5b5c6  stfld    class System.Windows.Input.StylusPlugIns.StylusPlugIn <>c__DisplayClass3_0::plugIn
0x5b5cb  ldarg.0
0x5b5cc  ldfld    class System.Windows.UIElement System.Windows.Input.StylusPlugIns.StylusPlugInCollection::_element
0x5b5d1  callvirt instance void [WindowsBase]System.Windows.Threading.DispatcherObject::VerifyAccess()
0x5b5d6  ldloc.0
0x5b5d7  ldfld    class System.Windows.Input.StylusPlugIns.StylusPlugIn <>c__DisplayClass3_0::plugIn
0x5b5dc  brtrue.s loc_5B5F3
0x5b5de  ldstr    aPlugin// "plugIn"
0x5b5e3  ldstr    aStylusPluginis// "Stylus_PlugInIsNull"
0x5b5e8  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x5b5ed  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x5b5f2  throw
0x5b5f3  ldarg.0
0x5b5f4  ldloc.0
0x5b5f5  ldfld    class System.Windows.Input.StylusPlugIns.StylusPlugIn <>c__DisplayClass3_0::plugIn
0x5b5fa  call     instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Input.StylusPlugIns.StylusPlugIn>::IndexOf(var<u1>)
0x5b5ff  ldc.i4.m1
0x5b600  beq.s    loc_5B617
0x5b602  ldstr    aStylusPluginis_0// "Stylus_PlugInIsDuplicated"
0x5b607  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x5b60c  ldstr    aPlugin// "plugIn"
0x5b611  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x5b616  throw
0x5b617  ldarg.0
0x5b618  ldloc.0
0x5b619  ldftn    instance void <>c__DisplayClass3_0::<SetItem>b__0()
0x5b61f  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x5b624  call     instance void System.Windows.Input.StylusPlugIns.StylusPlugInCollection::ExecuteWithPotentialDispatcherDisable(class [mscorlib]System.Action action)
0x5b629  ret
```
