# Microsoft.ReportingServices.OnDemandReportRendering.EnumTranslator::TranslateGaugeStateIndicatorStyles

- ea: `0x2aad0`
- end: `0x2ae47`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.EnumTranslator::TranslateGaugeStateIndicatorStyles`
- size: `887`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x3bc80`
- `0x3c0f0`
- `0xd54b0`
- `0xd5db0`

## callees

- `0x2aad0`
- `0xb9aa0`
- `0x17c2a0`

## string_xrefs

- `0x2ab12`: `ArrowSide`
- `0x2abad`: `LightArrowSide`

## pseudocode

```c

```

## disassembly

```asm
0x2aad0  ldarg.0
0x2aad1  brtrue.s loc_2AAD5
0x2aad3  ldc.i4.0
0x2aad4  ret
0x2aad5  ldarg.0
0x2aad6  ldstr    aCircle// "Circle"
0x2aadb  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2aae0  brfalse.s loc_2AAE4
0x2aae2  ldc.i4.0
0x2aae3  ret
0x2aae4  ldarg.0
0x2aae5  ldstr    aFlag// "Flag"
0x2aaea  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2aaef  brfalse.s loc_2AAF3
0x2aaf1  ldc.i4.1
0x2aaf2  ret
0x2aaf3  ldarg.0
0x2aaf4  ldstr    aArrowdown// "ArrowDown"
0x2aaf9  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2aafe  brfalse.s loc_2AB02
0x2ab00  ldc.i4.2
0x2ab01  ret
0x2ab02  ldarg.0
0x2ab03  ldstr    aArrowdownincli// "ArrowDownIncline"
0x2ab08  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ab0d  brfalse.s loc_2AB11
0x2ab0f  ldc.i4.3
0x2ab10  ret
0x2ab11  ldarg.0
0x2ab12  ldstr    aArrowside// "ArrowSide"
0x2ab17  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ab1c  brfalse.s loc_2AB20
0x2ab1e  ldc.i4.4
0x2ab1f  ret
0x2ab20  ldarg.0
0x2ab21  ldstr    aArrowup// "ArrowUp"
0x2ab26  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ab2b  brfalse.s loc_2AB2F
0x2ab2d  ldc.i4.5
0x2ab2e  ret
0x2ab2f  ldarg.0
0x2ab30  ldstr    aArrowupincline// "ArrowUpIncline"
0x2ab35  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ab3a  brfalse.s loc_2AB3E
0x2ab3c  ldc.i4.6
0x2ab3d  ret
0x2ab3e  ldarg.0
0x2ab3f  ldstr    aBoxesallfilled// "BoxesAllFilled"
0x2ab44  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ab49  brfalse.s loc_2AB4D
0x2ab4b  ldc.i4.7
0x2ab4c  ret
0x2ab4d  ldarg.0
0x2ab4e  ldstr    aBoxesnonefille// "BoxesNoneFilled"
0x2ab53  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ab58  brfalse.s loc_2AB5C
0x2ab5a  ldc.i4.8
0x2ab5b  ret
0x2ab5c  ldarg.0
0x2ab5d  ldstr    aBoxesonefilled// "BoxesOneFilled"
0x2ab62  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ab67  brfalse.s loc_2AB6C
0x2ab69  ldc.i4.s 9
0x2ab6b  ret
0x2ab6c  ldarg.0
0x2ab6d  ldstr    aBoxestwofilled// "BoxesTwoFilled"
0x2ab72  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ab77  brfalse.s loc_2AB7C
0x2ab79  ldc.i4.s 0xA
0x2ab7b  ret
0x2ab7c  ldarg.0
0x2ab7d  ldstr    aBoxesthreefill// "BoxesThreeFilled"
0x2ab82  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ab87  brfalse.s loc_2AB8C
0x2ab89  ldc.i4.s 0xB
0x2ab8b  ret
0x2ab8c  ldarg.0
0x2ab8d  ldstr    aLightarrowdown// "LightArrowDown"
0x2ab92  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ab97  brfalse.s loc_2AB9C
0x2ab99  ldc.i4.s 0xC
0x2ab9b  ret
0x2ab9c  ldarg.0
0x2ab9d  ldstr    aLightarrowdown_0// "LightArrowDownIncline"
0x2aba2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2aba7  brfalse.s loc_2ABAC
0x2aba9  ldc.i4.s 0xD
0x2abab  ret
0x2abac  ldarg.0
0x2abad  ldstr    aLightarrowside// "LightArrowSide"
0x2abb2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2abb7  brfalse.s loc_2ABBC
0x2abb9  ldc.i4.s 0xE
0x2abbb  ret
0x2abbc  ldarg.0
0x2abbd  ldstr    aLightarrowup// "LightArrowUp"
0x2abc2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2abc7  brfalse.s loc_2ABCC
0x2abc9  ldc.i4.s 0xF
0x2abcb  ret
0x2abcc  ldarg.0
0x2abcd  ldstr    aLightarrowupin// "LightArrowUpIncline"
0x2abd2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2abd7  brfalse.s loc_2ABDC
0x2abd9  ldc.i4.s 0x10
0x2abdb  ret
0x2abdc  ldarg.0
0x2abdd  ldstr    aQuartersallfil// "QuartersAllFilled"
0x2abe2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2abe7  brfalse.s loc_2ABEC
0x2abe9  ldc.i4.s 0x11
0x2abeb  ret
0x2abec  ldarg.0
0x2abed  ldstr    aQuartersnonefi// "QuartersNoneFilled"
0x2abf2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2abf7  brfalse.s loc_2ABFC
0x2abf9  ldc.i4.s 0x12
0x2abfb  ret
0x2abfc  ldarg.0
0x2abfd  ldstr    aQuartersonefil// "QuartersOneFilled"
0x2ac02  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ac07  brfalse.s loc_2AC0C
0x2ac09  ldc.i4.s 0x13
0x2ac0b  ret
0x2ac0c  ldarg.0
0x2ac0d  ldstr    aQuarterstwofil// "QuartersTwoFilled"
0x2ac12  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ac17  brfalse.s loc_2AC1C
0x2ac19  ldc.i4.s 0x14
0x2ac1b  ret
0x2ac1c  ldarg.0
0x2ac1d  ldstr    aQuartersthreef// "QuartersThreeFilled"
0x2ac22  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ac27  brfalse.s loc_2AC2C
0x2ac29  ldc.i4.s 0x15
0x2ac2b  ret
0x2ac2c  ldarg.0
0x2ac2d  ldstr    aSignalmeterfou// "SignalMeterFourFilled"
0x2ac32  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ac37  brfalse.s loc_2AC3C
0x2ac39  ldc.i4.s 0x16
0x2ac3b  ret
0x2ac3c  ldarg.0
0x2ac3d  ldstr    aSignalmeternon// "SignalMeterNoneFilled"
0x2ac42  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ac47  brfalse.s loc_2AC4C
0x2ac49  ldc.i4.s 0x17
0x2ac4b  ret
0x2ac4c  ldarg.0
0x2ac4d  ldstr    aSignalmeterone// "SignalMeterOneFilled"
0x2ac52  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ac57  brfalse.s loc_2AC5C
0x2ac59  ldc.i4.s 0x18
0x2ac5b  ret
0x2ac5c  ldarg.0
0x2ac5d  ldstr    aSignalmeterthr// "SignalMeterThreeFilled"
0x2ac62  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ac67  brfalse.s loc_2AC6C
0x2ac69  ldc.i4.s 0x19
0x2ac6b  ret
0x2ac6c  ldarg.0
0x2ac6d  ldstr    aSignalmetertwo// "SignalMeterTwoFilled"
0x2ac72  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ac77  brfalse.s loc_2AC7C
0x2ac79  ldc.i4.s 0x1A
0x2ac7b  ret
0x2ac7c  ldarg.0
0x2ac7d  ldstr    aStarquartersal// "StarQuartersAllFilled"
0x2ac82  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ac87  brfalse.s loc_2AC8C
0x2ac89  ldc.i4.s 0x1B
0x2ac8b  ret
0x2ac8c  ldarg.0
0x2ac8d  ldstr    aStarquartersno// "StarQuartersNoneFilled"
0x2ac92  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ac97  brfalse.s loc_2AC9C
0x2ac99  ldc.i4.s 0x1C
0x2ac9b  ret
0x2ac9c  ldarg.0
0x2ac9d  ldstr    aStarquarterson// "StarQuartersOneFilled"
0x2aca2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2aca7  brfalse.s loc_2ACAC
0x2aca9  ldc.i4.s 0x1D
0x2acab  ret
0x2acac  ldarg.0
0x2acad  ldstr    aStarquarterstw// "StarQuartersTwoFilled"
0x2acb2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2acb7  brfalse.s loc_2ACBC
0x2acb9  ldc.i4.s 0x1E
0x2acbb  ret
0x2acbc  ldarg.0
0x2acbd  ldstr    aStarquartersth// "StarQuartersThreeFilled"
0x2acc2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2acc7  brfalse.s loc_2ACCC
0x2acc9  ldc.i4.s 0x1F
0x2accb  ret
0x2accc  ldarg.0
0x2accd  ldstr    aThreesignscirc// "ThreeSignsCircle"
0x2acd2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2acd7  brfalse.s loc_2ACDC
0x2acd9  ldc.i4.s 0x20
0x2acdb  ret
0x2acdc  ldarg.0
0x2acdd  ldstr    aThreesignsdiam// "ThreeSignsDiamond"
0x2ace2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ace7  brfalse.s loc_2ACEC
0x2ace9  ldc.i4.s 0x21
0x2aceb  ret
0x2acec  ldarg.0
0x2aced  ldstr    aThreesignstria// "ThreeSignsTriangle"
0x2acf2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2acf7  brfalse.s loc_2ACFC
0x2acf9  ldc.i4.s 0x22
0x2acfb  ret
0x2acfc  ldarg.0
0x2acfd  ldstr    aThreesymbolche// "ThreeSymbolCheck"
0x2ad02  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ad07  brfalse.s loc_2AD0C
0x2ad09  ldc.i4.s 0x23
0x2ad0b  ret
0x2ad0c  ldarg.0
0x2ad0d  ldstr    aThreesymbolcro// "ThreeSymbolCross"
0x2ad12  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ad17  brfalse.s loc_2AD1C
0x2ad19  ldc.i4.s 0x24
0x2ad1b  ret
0x2ad1c  ldarg.0
0x2ad1d  ldstr    aThreesymbolexc// "ThreeSymbolExclamation"
0x2ad22  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ad27  brfalse.s loc_2AD2C
0x2ad29  ldc.i4.s 0x25
0x2ad2b  ret
0x2ad2c  ldarg.0
0x2ad2d  ldstr    aThreesymbolunc// "ThreeSymbolUnCircledCheck"
0x2ad32  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ad37  brfalse.s loc_2AD3C
0x2ad39  ldc.i4.s 0x26
0x2ad3b  ret
0x2ad3c  ldarg.0
0x2ad3d  ldstr    aThreesymbolunc_0// "ThreeSymbolUnCircledCross"
0x2ad42  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ad47  brfalse.s loc_2AD4C
0x2ad49  ldc.i4.s 0x27
0x2ad4b  ret
0x2ad4c  ldarg.0
0x2ad4d  ldstr    aThreesymbolunc_1// "ThreeSymbolUnCircledExclamation"
0x2ad52  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ad57  brfalse.s loc_2AD5C
0x2ad59  ldc.i4.s 0x28
0x2ad5b  ret
0x2ad5c  ldarg.0
0x2ad5d  ldstr    aTrafficlight// "TrafficLight"
0x2ad62  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ad67  brfalse.s loc_2AD6C
0x2ad69  ldc.i4.s 0x29
0x2ad6b  ret
0x2ad6c  ldarg.0
0x2ad6d  ldstr    aTrafficlightun// "TrafficLightUnrimmed"
0x2ad72  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ad77  brfalse.s loc_2AD7C
0x2ad79  ldc.i4.s 0x2A
0x2ad7b  ret
0x2ad7c  ldarg.0
0x2ad7d  ldstr    aTriangledash// "TriangleDash"
0x2ad82  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ad87  brfalse.s loc_2AD8C
0x2ad89  ldc.i4.s 0x2B
0x2ad8b  ret
0x2ad8c  ldarg.0
0x2ad8d  ldstr    aTriangledown// "TriangleDown"
0x2ad92  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ad97  brfalse.s loc_2AD9C
0x2ad99  ldc.i4.s 0x2C
0x2ad9b  ret
0x2ad9c  ldarg.0
0x2ad9d  ldstr    aTriangleup// "TriangleUp"
0x2ada2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2ada7  brfalse.s loc_2ADAC
0x2ada9  ldc.i4.s 0x2D
0x2adab  ret
0x2adac  ldarg.0
0x2adad  ldstr    aButtonstop// "ButtonStop"
0x2adb2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2adb7  brfalse.s loc_2ADBC
0x2adb9  ldc.i4.s 0x2E
0x2adbb  ret
0x2adbc  ldarg.0
0x2adbd  ldstr    aButtonplay// "ButtonPlay"
0x2adc2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2adc7  brfalse.s loc_2ADCC
0x2adc9  ldc.i4.s 0x2F
0x2adcb  ret
0x2adcc  ldarg.0
0x2adcd  ldstr    aButtonpause// "ButtonPause"
0x2add2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2add7  brfalse.s loc_2ADDC
0x2add9  ldc.i4.s 0x30
0x2addb  ret
0x2addc  ldarg.0
0x2addd  ldstr    aFacesmile// "FaceSmile"
  ... truncated ...
```
