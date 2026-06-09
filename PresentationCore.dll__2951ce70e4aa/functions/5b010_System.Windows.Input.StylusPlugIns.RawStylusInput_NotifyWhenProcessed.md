# System.Windows.Input.StylusPlugIns.RawStylusInput::NotifyWhenProcessed

- ea: `0x5b010`
- end: `0x5b053`
- name: `System.Windows.Input.StylusPlugIns.RawStylusInput::NotifyWhenProcessed`
- size: `67`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x5a180`
- `0x5a250`

## callees

- `0x5b010`
- `0x5b0f0`
- `0x5b140`
- `0x146e40`

## string_xrefs

- `0x5b018`: `Stylus_CanOnlyCallForDownMoveOrUp`

## pseudocode

```c

```

## disassembly

```asm
0x5b010  ldarg.0
0x5b011  ldfld    class System.Windows.Input.StylusPlugIns.StylusPlugIn System.Windows.Input.StylusPlugIns.RawStylusInput::_currentNotifyPlugIn
0x5b016  brtrue.s loc_5B028
0x5b018  ldstr    aStylusCanonlyc// "Stylus_CanOnlyCallForDownMoveOrUp"
0x5b01d  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x5b022  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5b027  throw
0x5b028  ldarg.0
0x5b029  ldfld    class System.Windows.Input.StylusPlugIns.RawStylusInputCustomDataList System.Windows.Input.StylusPlugIns.RawStylusInput::_customData
0x5b02e  brtrue.s loc_5B03B
0x5b030  ldarg.0
0x5b031  newobj   instance void System.Windows.Input.StylusPlugIns.RawStylusInputCustomDataList::.ctor()
0x5b036  stfld    class System.Windows.Input.StylusPlugIns.RawStylusInputCustomDataList System.Windows.Input.StylusPlugIns.RawStylusInput::_customData
0x5b03b  ldarg.0
0x5b03c  ldfld    class System.Windows.Input.StylusPlugIns.RawStylusInputCustomDataList System.Windows.Input.StylusPlugIns.RawStylusInput::_customData
0x5b041  ldarg.0
0x5b042  ldfld    class System.Windows.Input.StylusPlugIns.StylusPlugIn System.Windows.Input.StylusPlugIns.RawStylusInput::_currentNotifyPlugIn
0x5b047  ldarg.1
0x5b048  newobj   instance void System.Windows.Input.StylusPlugIns.RawStylusInputCustomData::.ctor(class System.Windows.Input.StylusPlugIns.StylusPlugIn owner, object data)
0x5b04d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Input.StylusPlugIns.RawStylusInputCustomData>::Add(var<u1>)
0x5b052  ret
```
