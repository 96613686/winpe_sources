# System.Windows.Media.FormattedText::ValidateFontSize

- ea: `0x817d0`
- end: `0x81847`
- name: `System.Windows.Media.FormattedText::ValidateFontSize`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x816c0`
- `0x81b50`

## callees

- `0x817d0`
- `0x146e40`
- `0x146e70`

## string_xrefs

- `0x817dc`: `emSize`
- `0x817fd`: `emSize`
- `0x81831`: `emSize`

## pseudocode

```c

```

## disassembly

```asm
0x817d0  ldarg.0
0x817d1  ldc.r8   0.0
0x817da  bgt.un.s loc_817F1
0x817dc  ldstr    aEmsize// "emSize"
0x817e1  ldstr    aParametermustb_0// "ParameterMustBeGreaterThanZero"
0x817e6  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x817eb  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x817f0  throw
0x817f1  ldarg.0
0x817f2  ldc.r8   35791.39406666667
0x817fb  ble.un.s loc_81829
0x817fd  ldstr    aEmsize// "emSize"
0x81802  ldstr    aParametercanno// "ParameterCannotBeGreaterThan"
0x81807  ldc.i4.1
0x81808  newarr   [mscorlib]System.Object
0x8180d  dup
0x8180e  ldc.i4.0
0x8180f  ldc.r8   35791.39406666667
0x81818  box      [mscorlib]System.Double
0x8181d  stelem.ref
0x8181e  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x81823  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x81828  throw
0x81829  ldarg.0
0x8182a  call     bool [WindowsBase]MS.Internal.DoubleUtil::IsNaN(float64)
0x8182f  brfalse.s loc_81846
0x81831  ldstr    aEmsize// "emSize"
0x81836  ldstr    aParametervalue// "ParameterValueCannotBeNaN"
0x8183b  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x81840  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x81845  throw
0x81846  ret
```
