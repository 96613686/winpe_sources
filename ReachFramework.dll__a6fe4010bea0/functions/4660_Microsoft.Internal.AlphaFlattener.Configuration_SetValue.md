# Microsoft.Internal.AlphaFlattener.Configuration::SetValue

- ea: `0x4660`
- end: `0x4791`
- name: `Microsoft.Internal.AlphaFlattener.Configuration::SetValue`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x39530`

## callees

- `0x4660`
- `0x3e7f0`

## string_xrefs

- `0x46f6`: `GradientDecompositionDensity`

## pseudocode

```c

```

## disassembly

```asm
0x4660  ldarg.0
0x4661  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x4666  stloc.0
0x4667  ldloc.0
0x4668  ldc.i4   0x6FC9C4D8
0x466d  bgt.un.s loc_468F
0x466f  ldloc.0
0x4670  ldc.i4   0x5881A9D2
0x4675  beq      loc_4725
0x467a  ldloc.0
0x467b  ldc.i4   0x679D3941
0x4680  beq.s    loc_46E3
0x4682  ldloc.0
0x4683  ldc.i4   0x6FC9C4D8
0x4688  beq.s    loc_46F5
0x468a  br       loc_478F
0x468f  ldloc.0
0x4690  ldc.i4   0x94315CAB
0x4695  bgt.un.s loc_46AC
0x4697  ldloc.0
0x4698  ldc.i4   0x94314167
0x469d  beq.s    loc_4716
0x469f  ldloc.0
0x46a0  ldc.i4   0x94315CAB
0x46a5  beq.s    loc_46D1
0x46a7  br       loc_478F
0x46ac  ldloc.0
0x46ad  ldc.i4   0xAD507A4C
0x46b2  beq.s    loc_4707
0x46b4  ldloc.0
0x46b5  ldc.i4   0xEC992304
0x46ba  bne.un   loc_478F
0x46bf  ldarg.0
0x46c0  ldstr    aDisplaypagedeb// "DisplayPageDebugHeader"
0x46c5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x46ca  brtrue.s loc_4734
0x46cc  br       loc_478F
0x46d1  ldarg.0
0x46d2  ldstr    aForcealphaopaq// "ForceAlphaOpaque"
0x46d7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x46dc  brtrue.s loc_4741
0x46de  br       loc_478F
0x46e3  ldarg.0
0x46e4  ldstr    aBlendalphawith// "BlendAlphaWithWhite"
0x46e9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x46ee  brtrue.s loc_474E
0x46f0  br       loc_478F
0x46f5  ldarg.0
0x46f6  ldstr    aGradientdecomp// "GradientDecompositionDensity"
0x46fb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4700  brtrue.s loc_475B
0x4702  br       loc_478F
0x4707  ldarg.0
0x4708  ldstr    aMaximumtranspa// "MaximumTransparencyLayer"
0x470d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4712  brtrue.s loc_4768
0x4714  br.s     loc_478F
0x4716  ldarg.0
0x4717  ldstr    aRasterizationd// "RasterizationDPI"
0x471c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4721  brtrue.s loc_4775
0x4723  br.s     loc_478F
0x4725  ldarg.0
0x4726  ldstr    aOutputfile// "OutputFile"
0x472b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4730  brtrue.s loc_4782
0x4732  br.s     loc_478F
0x4734  ldarg.1
0x4735  unbox.any [mscorlib]System.Boolean
0x473a  stsfld   bool Microsoft.Internal.AlphaFlattener.Configuration::DisplayPageDebugHeader
0x473f  ldc.i4.1
0x4740  ret
0x4741  ldarg.1
0x4742  unbox.any [mscorlib]System.Boolean
0x4747  stsfld   bool Microsoft.Internal.AlphaFlattener.Configuration::ForceAlphaOpaque
0x474c  ldc.i4.1
0x474d  ret
0x474e  ldarg.1
0x474f  unbox.any [mscorlib]System.Boolean
0x4754  stsfld   bool Microsoft.Internal.AlphaFlattener.Configuration::BlendAlphaWithWhite
0x4759  ldc.i4.1
0x475a  ret
0x475b  ldarg.1
0x475c  unbox.any [mscorlib]System.Double
0x4761  stsfld   float64 Microsoft.Internal.AlphaFlattener.Configuration::GradientDecompositionDensity
0x4766  ldc.i4.1
0x4767  ret
0x4768  ldarg.1
0x4769  unbox.any [mscorlib]System.Int32
0x476e  stsfld   int32 Microsoft.Internal.AlphaFlattener.Configuration::MaximumTransparencyLayer
0x4773  ldc.i4.1
0x4774  ret
0x4775  ldarg.1
0x4776  unbox.any [mscorlib]System.Int32
0x477b  stsfld   int32 Microsoft.Internal.AlphaFlattener.Configuration::RasterizationDPI
0x4780  ldc.i4.1
0x4781  ret
0x4782  ldarg.1
0x4783  castclass [mscorlib]System.String
0x4788  stsfld   string Microsoft.Internal.AlphaFlattener.Configuration::OutputFile
0x478d  ldc.i4.1
0x478e  ret
0x478f  ldc.i4.0
0x4790  ret
```
