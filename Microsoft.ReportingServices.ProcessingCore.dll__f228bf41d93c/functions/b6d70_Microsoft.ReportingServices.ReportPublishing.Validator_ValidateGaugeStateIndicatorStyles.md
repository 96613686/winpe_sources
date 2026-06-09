# Microsoft.ReportingServices.ReportPublishing.Validator::ValidateGaugeStateIndicatorStyles

- ea: `0xb6d70`
- end: `0xb70bf`
- name: `Microsoft.ReportingServices.ReportPublishing.Validator::ValidateGaugeStateIndicatorStyles`
- size: `847`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x96020`
- `0x96dc0`

## callees

- `0xb6d70`
- `0xb9aa0`
- `0xb9b10`

## string_xrefs

- `0xb6db1`: `ArrowSide`
- `0xb6e51`: `LightArrowSide`

## pseudocode

```c

```

## disassembly

```asm
0xb6d70  ldarg.0
0xb6d71  ldstr    aCircle// "Circle"
0xb6d76  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6d7b  brtrue   loc_B70B2
0xb6d80  ldarg.0
0xb6d81  ldstr    aFlag// "Flag"
0xb6d86  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6d8b  brtrue   loc_B70B2
0xb6d90  ldarg.0
0xb6d91  ldstr    aArrowdown// "ArrowDown"
0xb6d96  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6d9b  brtrue   loc_B70B2
0xb6da0  ldarg.0
0xb6da1  ldstr    aArrowdownincli// "ArrowDownIncline"
0xb6da6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6dab  brtrue   loc_B70B2
0xb6db0  ldarg.0
0xb6db1  ldstr    aArrowside// "ArrowSide"
0xb6db6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6dbb  brtrue   loc_B70B2
0xb6dc0  ldarg.0
0xb6dc1  ldstr    aArrowup// "ArrowUp"
0xb6dc6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6dcb  brtrue   loc_B70B2
0xb6dd0  ldarg.0
0xb6dd1  ldstr    aArrowupincline// "ArrowUpIncline"
0xb6dd6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6ddb  brtrue   loc_B70B2
0xb6de0  ldarg.0
0xb6de1  ldstr    aBoxesallfilled// "BoxesAllFilled"
0xb6de6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6deb  brtrue   loc_B70B2
0xb6df0  ldarg.0
0xb6df1  ldstr    aBoxesnonefille// "BoxesNoneFilled"
0xb6df6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6dfb  brtrue   loc_B70B2
0xb6e00  ldarg.0
0xb6e01  ldstr    aBoxesonefilled// "BoxesOneFilled"
0xb6e06  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6e0b  brtrue   loc_B70B2
0xb6e10  ldarg.0
0xb6e11  ldstr    aBoxestwofilled// "BoxesTwoFilled"
0xb6e16  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6e1b  brtrue   loc_B70B2
0xb6e20  ldarg.0
0xb6e21  ldstr    aBoxesthreefill// "BoxesThreeFilled"
0xb6e26  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6e2b  brtrue   loc_B70B2
0xb6e30  ldarg.0
0xb6e31  ldstr    aLightarrowdown// "LightArrowDown"
0xb6e36  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6e3b  brtrue   loc_B70B2
0xb6e40  ldarg.0
0xb6e41  ldstr    aLightarrowdown_0// "LightArrowDownIncline"
0xb6e46  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6e4b  brtrue   loc_B70B2
0xb6e50  ldarg.0
0xb6e51  ldstr    aLightarrowside// "LightArrowSide"
0xb6e56  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6e5b  brtrue   loc_B70B2
0xb6e60  ldarg.0
0xb6e61  ldstr    aLightarrowup// "LightArrowUp"
0xb6e66  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6e6b  brtrue   loc_B70B2
0xb6e70  ldarg.0
0xb6e71  ldstr    aLightarrowupin// "LightArrowUpIncline"
0xb6e76  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6e7b  brtrue   loc_B70B2
0xb6e80  ldarg.0
0xb6e81  ldstr    aQuartersallfil// "QuartersAllFilled"
0xb6e86  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6e8b  brtrue   loc_B70B2
0xb6e90  ldarg.0
0xb6e91  ldstr    aQuartersnonefi// "QuartersNoneFilled"
0xb6e96  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6e9b  brtrue   loc_B70B2
0xb6ea0  ldarg.0
0xb6ea1  ldstr    aQuartersonefil// "QuartersOneFilled"
0xb6ea6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6eab  brtrue   loc_B70B2
0xb6eb0  ldarg.0
0xb6eb1  ldstr    aQuarterstwofil// "QuartersTwoFilled"
0xb6eb6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6ebb  brtrue   loc_B70B2
0xb6ec0  ldarg.0
0xb6ec1  ldstr    aQuartersthreef// "QuartersThreeFilled"
0xb6ec6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6ecb  brtrue   loc_B70B2
0xb6ed0  ldarg.0
0xb6ed1  ldstr    aSignalmeterfou// "SignalMeterFourFilled"
0xb6ed6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6edb  brtrue   loc_B70B2
0xb6ee0  ldarg.0
0xb6ee1  ldstr    aSignalmeternon// "SignalMeterNoneFilled"
0xb6ee6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6eeb  brtrue   loc_B70B2
0xb6ef0  ldarg.0
0xb6ef1  ldstr    aSignalmeterone// "SignalMeterOneFilled"
0xb6ef6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6efb  brtrue   loc_B70B2
0xb6f00  ldarg.0
0xb6f01  ldstr    aSignalmeterthr// "SignalMeterThreeFilled"
0xb6f06  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6f0b  brtrue   loc_B70B2
0xb6f10  ldarg.0
0xb6f11  ldstr    aSignalmetertwo// "SignalMeterTwoFilled"
0xb6f16  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6f1b  brtrue   loc_B70B2
0xb6f20  ldarg.0
0xb6f21  ldstr    aStarquartersal// "StarQuartersAllFilled"
0xb6f26  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6f2b  brtrue   loc_B70B2
0xb6f30  ldarg.0
0xb6f31  ldstr    aStarquartersno// "StarQuartersNoneFilled"
0xb6f36  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6f3b  brtrue   loc_B70B2
0xb6f40  ldarg.0
0xb6f41  ldstr    aStarquarterson// "StarQuartersOneFilled"
0xb6f46  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6f4b  brtrue   loc_B70B2
0xb6f50  ldarg.0
0xb6f51  ldstr    aStarquarterstw// "StarQuartersTwoFilled"
0xb6f56  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6f5b  brtrue   loc_B70B2
0xb6f60  ldarg.0
0xb6f61  ldstr    aStarquartersth// "StarQuartersThreeFilled"
0xb6f66  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6f6b  brtrue   loc_B70B2
0xb6f70  ldarg.0
0xb6f71  ldstr    aThreesignscirc// "ThreeSignsCircle"
0xb6f76  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6f7b  brtrue   loc_B70B2
0xb6f80  ldarg.0
0xb6f81  ldstr    aThreesignsdiam// "ThreeSignsDiamond"
0xb6f86  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6f8b  brtrue   loc_B70B2
0xb6f90  ldarg.0
0xb6f91  ldstr    aThreesignstria// "ThreeSignsTriangle"
0xb6f96  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6f9b  brtrue   loc_B70B2
0xb6fa0  ldarg.0
0xb6fa1  ldstr    aThreesymbolche// "ThreeSymbolCheck"
0xb6fa6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6fab  brtrue   loc_B70B2
0xb6fb0  ldarg.0
0xb6fb1  ldstr    aThreesymbolcro// "ThreeSymbolCross"
0xb6fb6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6fbb  brtrue   loc_B70B2
0xb6fc0  ldarg.0
0xb6fc1  ldstr    aThreesymbolexc// "ThreeSymbolExclamation"
0xb6fc6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6fcb  brtrue   loc_B70B2
0xb6fd0  ldarg.0
0xb6fd1  ldstr    aThreesymbolunc// "ThreeSymbolUnCircledCheck"
0xb6fd6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6fdb  brtrue   loc_B70B2
0xb6fe0  ldarg.0
0xb6fe1  ldstr    aThreesymbolunc_0// "ThreeSymbolUnCircledCross"
0xb6fe6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6feb  brtrue   loc_B70B2
0xb6ff0  ldarg.0
0xb6ff1  ldstr    aThreesymbolunc_1// "ThreeSymbolUnCircledExclamation"
0xb6ff6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6ffb  brtrue   loc_B70B2
0xb7000  ldarg.0
0xb7001  ldstr    aTrafficlight// "TrafficLight"
0xb7006  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb700b  brtrue   loc_B70B2
0xb7010  ldarg.0
0xb7011  ldstr    aTrafficlightun// "TrafficLightUnrimmed"
0xb7016  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb701b  brtrue   loc_B70B2
0xb7020  ldarg.0
0xb7021  ldstr    aTriangledash// "TriangleDash"
0xb7026  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb702b  brtrue   loc_B70B2
0xb7030  ldarg.0
0xb7031  ldstr    aTriangledown// "TriangleDown"
0xb7036  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb703b  brtrue.s loc_B70B2
0xb703d  ldarg.0
0xb703e  ldstr    aTriangleup// "TriangleUp"
0xb7043  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb7048  brtrue.s loc_B70B2
0xb704a  ldarg.0
0xb704b  ldstr    aButtonstop// "ButtonStop"
0xb7050  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb7055  brtrue.s loc_B70B2
0xb7057  ldarg.0
0xb7058  ldstr    aButtonplay// "ButtonPlay"
0xb705d  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb7062  brtrue.s loc_B70B2
0xb7064  ldarg.0
0xb7065  ldstr    aButtonpause// "ButtonPause"
0xb706a  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb706f  brtrue.s loc_B70B2
0xb7071  ldarg.0
0xb7072  ldstr    aFacesmile// "FaceSmile"
0xb7077  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb707c  brtrue.s loc_B70B2
0xb707e  ldarg.0
0xb707f  ldstr    aFaceneutral// "FaceNeutral"
0xb7084  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb7089  brtrue.s loc_B70B2
0xb708b  ldarg.0
0xb708c  ldstr    aFacefrown// "FaceFrown"
0xb7091  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb7096  brtrue.s loc_B70B2
0xb7098  ldarg.0
0xb7099  ldstr    aImage// "Image"
0xb709e  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb70a3  brtrue.s loc_B70B2
0xb70a5  ldarg.0
0xb70a6  ldstr    aNone// "None"
0xb70ab  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb70b0  brfalse.s loc_B70B4
0xb70b2  ldc.i4.1
0xb70b3  ret
0xb70b4  ldarg.0
0xb70b5  ldarg.1
0xb70b6  ldarg.2
0xb70b7  ldarg.3
0xb70b8  call     void Microsoft.ReportingServices.ReportPublishing.Validator::RegisterInvalidEnumValueError(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0xb70bd  ldc.i4.0
0xb70be  ret
```
