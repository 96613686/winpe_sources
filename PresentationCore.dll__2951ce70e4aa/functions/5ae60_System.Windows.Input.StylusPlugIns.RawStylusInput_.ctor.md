# System.Windows.Input.StylusPlugIns.RawStylusInput::.ctor

- ea: `0x5ae60`
- end: `0x5aeb5`
- name: `System.Windows.Input.StylusPlugIns.RawStylusInput::.ctor`
- size: `85`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x4b970`
- `0x4ba80`
- `0x51ad0`
- `0x58a80`
- `0x58d00`
- `0x58df0`

## callees

- `0x5ae60`
- `0x82d10`
- `0x146e40`

## string_xrefs

- `0x5ae94`: `targetPlugInCollection`

## pseudocode

```c

```

## disassembly

```asm
0x5ae60  ldarg.0
0x5ae61  call     instance void [mscorlib]System.Object::.ctor()
0x5ae66  ldarg.1
0x5ae67  brtrue.s loc_5AE74
0x5ae69  ldstr    aReport// "report"
0x5ae6e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5ae73  throw
0x5ae74  ldarg.2
0x5ae75  callvirt instance class System.Windows.Media.GeneralTransform System.Windows.Media.GeneralTransform::get_Inverse()
0x5ae7a  brtrue.s loc_5AE91
0x5ae7c  ldstr    aStylusMatrixno// "Stylus_MatrixNotInvertable"
0x5ae81  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x5ae86  ldstr    aTablettoelemen// "tabletToElementTransform"
0x5ae8b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x5ae90  throw
0x5ae91  ldarg.3
0x5ae92  brtrue.s loc_5AE9F
0x5ae94  ldstr    aTargetpluginco// "targetPlugInCollection"
0x5ae99  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5ae9e  throw
0x5ae9f  ldarg.0
0x5aea0  ldarg.1
0x5aea1  stfld    class System.Windows.Input.RawStylusInputReport System.Windows.Input.StylusPlugIns.RawStylusInput::_report
0x5aea6  ldarg.0
0x5aea7  ldarg.2
0x5aea8  stfld    class System.Windows.Media.GeneralTransform System.Windows.Input.StylusPlugIns.RawStylusInput::_tabletToElementTransform
0x5aead  ldarg.0
0x5aeae  ldarg.3
0x5aeaf  stfld    class System.Windows.Input.StylusPlugIns.StylusPlugInCollection System.Windows.Input.StylusPlugIns.RawStylusInput::_targetPlugInCollection
0x5aeb4  ret
```
