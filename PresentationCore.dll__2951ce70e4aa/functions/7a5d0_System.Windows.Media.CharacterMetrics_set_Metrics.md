# System.Windows.Media.CharacterMetrics::set_Metrics

- ea: `0x7a5d0`
- end: `0x7a6de`
- name: `System.Windows.Media.CharacterMetrics::set_Metrics`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x7a510`

## callees

- `0x7a5d0`
- `0x7a710`
- `0x128bf0`
- `0x128cc0`
- `0x146e40`

## string_xrefs

- `0x7a60a`: `LeftSideBearing`
- `0x7a61b`: `RightSideBearing`
- `0x7a62c`: `TopSideBearing`
- `0x7a63d`: `BottomSideBearing`

## pseudocode

```c

```

## disassembly

```asm
0x7a5d0  ldarg.1
0x7a5d1  call     float64[] System.Windows.Media.CharacterMetrics::ParseMetrics(string s)
0x7a5d6  stloc.0
0x7a5d7  ldstr    aBlackboxwidth// "BlackBoxWidth"
0x7a5dc  ldloc.0
0x7a5dd  ldc.i4.0
0x7a5de  ldelema  [mscorlib]System.Double
0x7a5e3  call     void MS.Internal.FontFace.CompositeFontParser::VerifyNonNegativeMultiplierOfEm(string propertyName, float64& value)
0x7a5e8  ldstr    aBlackboxheight// "BlackBoxHeight"
0x7a5ed  ldloc.0
0x7a5ee  ldc.i4.1
0x7a5ef  ldelema  [mscorlib]System.Double
0x7a5f4  call     void MS.Internal.FontFace.CompositeFontParser::VerifyNonNegativeMultiplierOfEm(string propertyName, float64& value)
0x7a5f9  ldstr    aBaseline_0// "Baseline"
0x7a5fe  ldloc.0
0x7a5ff  ldc.i4.2
0x7a600  ldelema  [mscorlib]System.Double
0x7a605  call     void MS.Internal.FontFace.CompositeFontParser::VerifyMultiplierOfEm(string propertyName, float64& value)
0x7a60a  ldstr    aLeftsidebearin// "LeftSideBearing"
0x7a60f  ldloc.0
0x7a610  ldc.i4.3
0x7a611  ldelema  [mscorlib]System.Double
0x7a616  call     void MS.Internal.FontFace.CompositeFontParser::VerifyMultiplierOfEm(string propertyName, float64& value)
0x7a61b  ldstr    aRightsidebeari// "RightSideBearing"
0x7a620  ldloc.0
0x7a621  ldc.i4.4
0x7a622  ldelema  [mscorlib]System.Double
0x7a627  call     void MS.Internal.FontFace.CompositeFontParser::VerifyMultiplierOfEm(string propertyName, float64& value)
0x7a62c  ldstr    aTopsidebearing// "TopSideBearing"
0x7a631  ldloc.0
0x7a632  ldc.i4.5
0x7a633  ldelema  [mscorlib]System.Double
0x7a638  call     void MS.Internal.FontFace.CompositeFontParser::VerifyMultiplierOfEm(string propertyName, float64& value)
0x7a63d  ldstr    aBottomsidebear// "BottomSideBearing"
0x7a642  ldloc.0
0x7a643  ldc.i4.6
0x7a644  ldelema  [mscorlib]System.Double
0x7a649  call     void MS.Internal.FontFace.CompositeFontParser::VerifyMultiplierOfEm(string propertyName, float64& value)
0x7a64e  ldloc.0
0x7a64f  ldc.i4.0
0x7a650  ldelem.r8
0x7a651  ldloc.0
0x7a652  ldc.i4.3
0x7a653  ldelem.r8
0x7a654  add
0x7a655  ldloc.0
0x7a656  ldc.i4.4
0x7a657  ldelem.r8
0x7a658  add
0x7a659  stloc.2
0x7a65a  ldloc.2
0x7a65b  ldc.r8   0.0
0x7a664  bge.un.s loc_7A676
0x7a666  ldstr    aCharactermetri// "CharacterMetrics_NegativeHorizontalAdva"...
0x7a66b  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x7a670  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7a675  throw
0x7a676  ldloc.0
0x7a677  ldc.i4.1
0x7a678  ldelem.r8
0x7a679  ldloc.0
0x7a67a  ldc.i4.5
0x7a67b  ldelem.r8
0x7a67c  add
0x7a67d  ldloc.0
0x7a67e  ldc.i4.6
0x7a67f  ldelem.r8
0x7a680  add
0x7a681  stloc.1
0x7a682  ldloc.1
0x7a683  ldc.r8   0.0
0x7a68c  bge.un.s loc_7A69E
0x7a68e  ldstr    aCharactermetri_0// "CharacterMetrics_NegativeVerticalAdvanc"...
0x7a693  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x7a698  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7a69d  throw
0x7a69e  ldarg.0
0x7a69f  ldloc.0
0x7a6a0  ldc.i4.0
0x7a6a1  ldelem.r8
0x7a6a2  stfld    float64 System.Windows.Media.CharacterMetrics::_blackBoxWidth
0x7a6a7  ldarg.0
0x7a6a8  ldloc.0
0x7a6a9  ldc.i4.1
0x7a6aa  ldelem.r8
0x7a6ab  stfld    float64 System.Windows.Media.CharacterMetrics::_blackBoxHeight
0x7a6b0  ldarg.0
0x7a6b1  ldloc.0
0x7a6b2  ldc.i4.2
0x7a6b3  ldelem.r8
0x7a6b4  stfld    float64 System.Windows.Media.CharacterMetrics::_baseline
0x7a6b9  ldarg.0
0x7a6ba  ldloc.0
0x7a6bb  ldc.i4.3
0x7a6bc  ldelem.r8
0x7a6bd  stfld    float64 System.Windows.Media.CharacterMetrics::_leftSideBearing
0x7a6c2  ldarg.0
0x7a6c3  ldloc.0
0x7a6c4  ldc.i4.4
0x7a6c5  ldelem.r8
0x7a6c6  stfld    float64 System.Windows.Media.CharacterMetrics::_rightSideBearing
0x7a6cb  ldarg.0
0x7a6cc  ldloc.0
0x7a6cd  ldc.i4.5
0x7a6ce  ldelem.r8
0x7a6cf  stfld    float64 System.Windows.Media.CharacterMetrics::_topSideBearing
0x7a6d4  ldarg.0
0x7a6d5  ldloc.0
0x7a6d6  ldc.i4.6
0x7a6d7  ldelem.r8
0x7a6d8  stfld    float64 System.Windows.Media.CharacterMetrics::_bottomSideBearing
0x7a6dd  ret
```
