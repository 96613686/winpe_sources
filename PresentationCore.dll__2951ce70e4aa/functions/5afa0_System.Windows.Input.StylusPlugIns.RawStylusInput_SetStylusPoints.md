# System.Windows.Input.StylusPlugIns.RawStylusInput::SetStylusPoints

- ea: `0x5afa0`
- end: `0x5b00a`
- name: `System.Windows.Input.StylusPlugIns.RawStylusInput::SetStylusPoints`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x45780`
- `0x47a80`
- `0x47bb0`
- `0x48540`
- `0x5afa0`
- `0x107600`
- `0x146e40`

## string_xrefs

- `0x5afcb`: `IncompatibleStylusPointDescriptions`

## pseudocode

```c

```

## disassembly

```asm
0x5afa0  call     void MS.Internal.SecurityHelper::DemandUnmanagedCode()
0x5afa5  ldarg.1
0x5afa6  brtrue.s loc_5AFB3
0x5afa8  ldstr    aStyluspoints// "stylusPoints"
0x5afad  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5afb2  throw
0x5afb3  ldarg.1
0x5afb4  callvirt instance class System.Windows.Input.StylusPointDescription System.Windows.Input.StylusPointCollection::get_Description()
0x5afb9  ldarg.0
0x5afba  ldfld    class System.Windows.Input.RawStylusInputReport System.Windows.Input.StylusPlugIns.RawStylusInput::_report
0x5afbf  callvirt instance class System.Windows.Input.StylusPointDescription System.Windows.Input.RawStylusInputReport::get_StylusPointDescription()
0x5afc4  call     bool System.Windows.Input.StylusPointDescription::AreCompatible(class System.Windows.Input.StylusPointDescription stylusPointDescription1, class System.Windows.Input.StylusPointDescription stylusPointDescription2)
0x5afc9  brtrue.s loc_5AFE0
0x5afcb  ldstr    aIncompatiblest// "IncompatibleStylusPointDescriptions"
0x5afd0  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x5afd5  ldstr    aStyluspoints// "stylusPoints"
0x5afda  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x5afdf  throw
0x5afe0  ldarg.1
0x5afe1  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype System.Windows.Input.StylusPoint>::get_Count()
0x5afe6  brtrue.s loc_5AFFD
0x5afe8  ldstr    aStylusStyluspo// "Stylus_StylusPointsCantBeEmpty"
0x5afed  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x5aff2  ldstr    aStyluspoints// "stylusPoints"
0x5aff7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x5affc  throw
0x5affd  ldarg.0
0x5affe  ldarg.1
0x5afff  callvirt instance class System.Windows.Input.StylusPointCollection System.Windows.Input.StylusPointCollection::Clone()
0x5b004  stfld    class System.Windows.Input.StylusPointCollection System.Windows.Input.StylusPlugIns.RawStylusInput::_stylusPoints
0x5b009  ret
```
