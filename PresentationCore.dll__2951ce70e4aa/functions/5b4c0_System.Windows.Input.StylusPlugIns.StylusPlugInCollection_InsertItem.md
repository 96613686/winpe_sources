# System.Windows.Input.StylusPlugIns.StylusPlugInCollection::InsertItem

- ea: `0x5b4c0`
- end: `0x5b53a`
- name: `System.Windows.Input.StylusPlugIns.StylusPlugInCollection::InsertItem`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x5b4c0`
- `0x5b9e0`
- `0x146e40`
- `0x14a680`

## string_xrefs

- `0x5b4ee`: `plugIn`
- `0x5b51c`: `plugIn`
- `0x5b4f3`: `Stylus_PlugInIsNull`
- `0x5b512`: `Stylus_PlugInIsDuplicated`

## pseudocode

```c

```

## disassembly

```asm
0x5b4c0  newobj   instance void <>c__DisplayClass0_0::.ctor()
0x5b4c5  stloc.0
0x5b4c6  ldloc.0
0x5b4c7  ldarg.0
0x5b4c8  stfld    class System.Windows.Input.StylusPlugIns.StylusPlugInCollection <>c__DisplayClass0_0::<>4__this
0x5b4cd  ldloc.0
0x5b4ce  ldarg.1
0x5b4cf  stfld    int32 <>c__DisplayClass0_0::index
0x5b4d4  ldloc.0
0x5b4d5  ldarg.2
0x5b4d6  stfld    class System.Windows.Input.StylusPlugIns.StylusPlugIn <>c__DisplayClass0_0::plugIn
0x5b4db  ldarg.0
0x5b4dc  ldfld    class System.Windows.UIElement System.Windows.Input.StylusPlugIns.StylusPlugInCollection::_element
0x5b4e1  callvirt instance void [WindowsBase]System.Windows.Threading.DispatcherObject::VerifyAccess()
0x5b4e6  ldloc.0
0x5b4e7  ldfld    class System.Windows.Input.StylusPlugIns.StylusPlugIn <>c__DisplayClass0_0::plugIn
0x5b4ec  brtrue.s loc_5B503
0x5b4ee  ldstr    aPlugin// "plugIn"
0x5b4f3  ldstr    aStylusPluginis// "Stylus_PlugInIsNull"
0x5b4f8  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x5b4fd  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x5b502  throw
0x5b503  ldarg.0
0x5b504  ldloc.0
0x5b505  ldfld    class System.Windows.Input.StylusPlugIns.StylusPlugIn <>c__DisplayClass0_0::plugIn
0x5b50a  call     instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Input.StylusPlugIns.StylusPlugIn>::IndexOf(var<u1>)
0x5b50f  ldc.i4.m1
0x5b510  beq.s    loc_5B527
0x5b512  ldstr    aStylusPluginis_0// "Stylus_PlugInIsDuplicated"
0x5b517  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x5b51c  ldstr    aPlugin// "plugIn"
0x5b521  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x5b526  throw
0x5b527  ldarg.0
0x5b528  ldloc.0
0x5b529  ldftn    instance void <>c__DisplayClass0_0::<InsertItem>b__0()
0x5b52f  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x5b534  call     instance void System.Windows.Input.StylusPlugIns.StylusPlugInCollection::ExecuteWithPotentialDispatcherDisable(class [mscorlib]System.Action action)
0x5b539  ret
```
