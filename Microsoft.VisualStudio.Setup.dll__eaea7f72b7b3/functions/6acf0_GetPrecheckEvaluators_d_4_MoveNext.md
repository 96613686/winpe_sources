# <GetPrecheckEvaluators>d__4::MoveNext

- ea: `0x6acf0`
- end: `0x6b205`
- name: `<GetPrecheckEvaluators>d__4::MoveNext`
- size: `1301`
- prototype: ``
- caller_count: `0`
- callee_count: `40`
- tags: `service_task, installer_update`

## callees

- `0x1e990`
- `0x1e9b0`
- `0x1eaa0`
- `0x1eac0`
- `0x1ec10`
- `0x1ec20`
- `0x1eea0`
- `0x1eef0`
- `0x1ef00`
- `0x1f300`
- `0x1f320`
- `0x1f4f0`
- `0x1f510`
- `0x1f8d0`
- `0x1f8f0`
- `0x1fe90`
- `0x1feb0`
- `0x20200`
- `0x20220`
- `0x20470`
- `0x20490`
- `0x207d0`
- `0x208b0`
- `0x208d0`
- `0x20ca0`
- `0x20d00`
- `0x20eb0`
- `0x20ed0`
- `0x21300`
- `0x21320`
- `0x215e0`
- `0x21600`
- `0x21780`
- `0x217a0`
- `0x21d80`
- `0x21da0`
- `0x22110`
- `0x22130`
- `0x6acf0`
- `0x6b590`

## string_xrefs

- `0x6ad5b`: `services`
- `0x6adb0`: `Precheck Evaluation does not support Install and Hotload set at the same time.`

## pseudocode

```c

```

## disassembly

```asm
0x6acf0  ldarg.0
0x6acf1  ldfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6acf6  stloc.0
0x6acf7  ldarg.0
0x6acf8  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckEvaluatorFactory <GetPrecheckEvaluators>d__4::<>4__this
0x6acfd  stloc.1
0x6acfe  ldloc.0
0x6acff  switch   loc_6AD4E, loc_6AE25, loc_6AE5F, loc_6AEBA, loc_6AEF4, loc_6AF34, loc_6AF68, loc_6AFA2, loc_6AFDC, loc_6B024, loc_6B05F, loc_6B09A, loc_6B0D5, loc_6B110, loc_6B14B, loc_6B186, loc_6B1C1, loc_6B1FC
0x6ad4c  ldc.i4.0
0x6ad4d  ret
0x6ad4e  ldarg.0
0x6ad4f  ldc.i4.m1
0x6ad50  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6ad55  ldarg.0
0x6ad56  ldfld    class [mscorlib]System.IServiceProvider <GetPrecheckEvaluators>d__4::services
0x6ad5b  ldstr    aServices// "services"
0x6ad60  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x6ad65  ldarg.0
0x6ad66  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6ad6b  ldstr    aPrecheckparams// "precheckParams"
0x6ad70  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x6ad75  ldarg.0
0x6ad76  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6ad7b  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_PrecheckSupport()
0x6ad80  box      Microsoft.VisualStudio.Setup.Validation.PrecheckSupport
0x6ad85  ldc.i4.2
0x6ad86  box      Microsoft.VisualStudio.Setup.Validation.PrecheckSupport
0x6ad8b  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x6ad90  brfalse.s loc_6ADBB
0x6ad92  ldarg.0
0x6ad93  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6ad98  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_PrecheckSupport()
0x6ad9d  box      Microsoft.VisualStudio.Setup.Validation.PrecheckSupport
0x6ada2  ldc.i4.s 0x20
0x6ada4  box      Microsoft.VisualStudio.Setup.Validation.PrecheckSupport
0x6ada9  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x6adae  brfalse.s loc_6ADBB
0x6adb0  ldstr    aPrecheckEvalua// "Precheck Evaluation does not support In"...
0x6adb5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6adba  throw
0x6adbb  ldarg.0
0x6adbc  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6adc1  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_PrecheckSupport()
0x6adc6  call     valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.BackgroundDownloadPrecheck::get_PrecheckSupport()
0x6adcb  and
0x6adcc  brfalse.s loc_6AE2C
0x6adce  ldarg.0
0x6adcf  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6add4  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.BackgroundDownloadPrecheckMode Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_BackgroundDownloadMode()
0x6add9  brfalse.s loc_6AE2C
0x6addb  ldloc.1
0x6addc  ldfld    class Microsoft.VisualStudio.Setup.Validation.BackgroundDownloadPrecheck Microsoft.VisualStudio.Setup.Validation.PrecheckEvaluatorFactory::backgroundDownloadPrecheck
0x6ade1  brtrue.s loc_6ADFA
0x6ade3  ldloc.1
0x6ade4  ldarg.0
0x6ade5  ldfld    class [mscorlib]System.IServiceProvider <GetPrecheckEvaluators>d__4::services
0x6adea  ldarg.0
0x6adeb  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6adf0  newobj   instance void Microsoft.VisualStudio.Setup.Validation.BackgroundDownloadPrecheck::.ctor(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters precheckParameters)
0x6adf5  stfld    class Microsoft.VisualStudio.Setup.Validation.BackgroundDownloadPrecheck Microsoft.VisualStudio.Setup.Validation.PrecheckEvaluatorFactory::backgroundDownloadPrecheck
0x6adfa  ldloc.1
0x6adfb  ldfld    class Microsoft.VisualStudio.Setup.Validation.BackgroundDownloadPrecheck Microsoft.VisualStudio.Setup.Validation.PrecheckEvaluatorFactory::backgroundDownloadPrecheck
0x6ae00  ldarg.0
0x6ae01  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6ae06  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.BackgroundDownloadPrecheckMode Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_BackgroundDownloadMode()
0x6ae0b  callvirt instance void Microsoft.VisualStudio.Setup.Validation.BackgroundDownloadPrecheck::set_Mode(valuetype Microsoft.VisualStudio.Setup.Validation.BackgroundDownloadPrecheckMode value)
0x6ae10  ldarg.0
0x6ae11  ldloc.1
0x6ae12  ldfld    class Microsoft.VisualStudio.Setup.Validation.BackgroundDownloadPrecheck Microsoft.VisualStudio.Setup.Validation.PrecheckEvaluatorFactory::backgroundDownloadPrecheck
0x6ae17  stfld    class Microsoft.VisualStudio.Setup.Validation.IPrecheckEvaluator <GetPrecheckEvaluators>d__4::<>2__current
0x6ae1c  ldarg.0
0x6ae1d  ldc.i4.1
0x6ae1e  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6ae23  ldc.i4.1
0x6ae24  ret
0x6ae25  ldarg.0
0x6ae26  ldc.i4.m1
0x6ae27  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6ae2c  ldarg.0
0x6ae2d  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6ae32  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_PrecheckSupport()
0x6ae37  call     valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.UnsupportedOSCheck::get_PrecheckSupport()
0x6ae3c  and
0x6ae3d  brfalse.s loc_6AE66
0x6ae3f  ldarg.0
0x6ae40  ldarg.0
0x6ae41  ldfld    class [mscorlib]System.IServiceProvider <GetPrecheckEvaluators>d__4::services
0x6ae46  ldarg.0
0x6ae47  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6ae4c  newobj   instance void Microsoft.VisualStudio.Setup.Validation.UnsupportedOSCheck::.ctor(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters precheckParameters)
0x6ae51  stfld    class Microsoft.VisualStudio.Setup.Validation.IPrecheckEvaluator <GetPrecheckEvaluators>d__4::<>2__current
0x6ae56  ldarg.0
0x6ae57  ldc.i4.2
0x6ae58  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6ae5d  ldc.i4.1
0x6ae5e  ret
0x6ae5f  ldarg.0
0x6ae60  ldc.i4.m1
0x6ae61  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6ae66  ldarg.0
0x6ae67  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6ae6c  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_PrecheckSupport()
0x6ae71  call     valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.Connectivity::get_PrecheckSupport()
0x6ae76  and
0x6ae77  brfalse.s loc_6AEC1
0x6ae79  ldsfld   class IsConnected <>c::<>9__4_0
0x6ae7e  dup
0x6ae7f  brtrue.s loc_6AE98
0x6ae81  pop
0x6ae82  ldsfld   class <>c <>c::<>9
0x6ae87  ldftn    instance bool <>c::<GetPrecheckEvaluators>b__4_0()
0x6ae8d  newobj   instance void IsConnected::.ctor(object object, native int method)
0x6ae92  dup
0x6ae93  stsfld   class IsConnected <>c::<>9__4_0
0x6ae98  stloc.2
0x6ae99  ldarg.0
0x6ae9a  ldarg.0
0x6ae9b  ldfld    class [mscorlib]System.IServiceProvider <GetPrecheckEvaluators>d__4::services
0x6aea0  ldarg.0
0x6aea1  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6aea6  ldloc.2
0x6aea7  newobj   instance void Microsoft.VisualStudio.Setup.Validation.Connectivity::.ctor(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters precheckParameters, class IsConnected d)
0x6aeac  stfld    class Microsoft.VisualStudio.Setup.Validation.IPrecheckEvaluator <GetPrecheckEvaluators>d__4::<>2__current
0x6aeb1  ldarg.0
0x6aeb2  ldc.i4.3
0x6aeb3  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6aeb8  ldc.i4.1
0x6aeb9  ret
0x6aeba  ldarg.0
0x6aebb  ldc.i4.m1
0x6aebc  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6aec1  ldarg.0
0x6aec2  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6aec7  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_PrecheckSupport()
0x6aecc  call     valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.TargetDirCheck::get_PrecheckSupport()
0x6aed1  and
0x6aed2  brfalse.s loc_6AEFB
0x6aed4  ldarg.0
0x6aed5  ldarg.0
0x6aed6  ldfld    class [mscorlib]System.IServiceProvider <GetPrecheckEvaluators>d__4::services
0x6aedb  ldarg.0
0x6aedc  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6aee1  newobj   instance void Microsoft.VisualStudio.Setup.Validation.TargetDirCheck::.ctor(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters precheckParameters)
0x6aee6  stfld    class Microsoft.VisualStudio.Setup.Validation.IPrecheckEvaluator <GetPrecheckEvaluators>d__4::<>2__current
0x6aeeb  ldarg.0
0x6aeec  ldc.i4.4
0x6aeed  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6aef2  ldc.i4.1
0x6aef3  ret
0x6aef4  ldarg.0
0x6aef5  ldc.i4.m1
0x6aef6  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6aefb  ldarg.0
0x6aefc  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6af01  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_PrecheckSupport()
0x6af06  call     valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.SizePreCheckEvaluator::get_PrecheckSupport()
0x6af0b  and
0x6af0c  brfalse.s loc_6AF3B
0x6af0e  ldarg.0
0x6af0f  ldarg.0
0x6af10  ldfld    class [mscorlib]System.IServiceProvider <GetPrecheckEvaluators>d__4::services
0x6af15  ldarg.0
0x6af16  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6af1b  ldarg.0
0x6af1c  ldfld    class Microsoft.VisualStudio.Setup.VariableCollection <GetPrecheckEvaluators>d__4::properties
0x6af21  newobj   instance void Microsoft.VisualStudio.Setup.Validation.SizePreCheckEvaluator::.ctor(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters precheckParameters, class Microsoft.VisualStudio.Setup.VariableCollection properties)
0x6af26  stfld    class Microsoft.VisualStudio.Setup.Validation.IPrecheckEvaluator <GetPrecheckEvaluators>d__4::<>2__current
0x6af2b  ldarg.0
0x6af2c  ldc.i4.5
0x6af2d  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6af32  ldc.i4.1
0x6af33  ret
0x6af34  ldarg.0
0x6af35  ldc.i4.m1
0x6af36  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6af3b  ldarg.0
0x6af3c  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6af41  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_PrecheckSupport()
0x6af46  call     valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.Elevation::get_PrecheckSupport()
0x6af4b  and
0x6af4c  brfalse.s loc_6AF6F
0x6af4e  ldarg.0
0x6af4f  ldarg.0
0x6af50  ldfld    class [mscorlib]System.IServiceProvider <GetPrecheckEvaluators>d__4::services
0x6af55  newobj   instance void Microsoft.VisualStudio.Setup.Validation.Elevation::.ctor(class [mscorlib]System.IServiceProvider services)
0x6af5a  stfld    class Microsoft.VisualStudio.Setup.Validation.IPrecheckEvaluator <GetPrecheckEvaluators>d__4::<>2__current
0x6af5f  ldarg.0
0x6af60  ldc.i4.6
0x6af61  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6af66  ldc.i4.1
0x6af67  ret
0x6af68  ldarg.0
0x6af69  ldc.i4.m1
0x6af6a  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6af6f  ldarg.0
0x6af70  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6af75  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_PrecheckSupport()
0x6af7a  call     valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.VSProcessesRunning::get_PrecheckSupport()
0x6af7f  and
0x6af80  brfalse.s loc_6AFA9
0x6af82  ldarg.0
0x6af83  ldarg.0
0x6af84  ldfld    class [mscorlib]System.IServiceProvider <GetPrecheckEvaluators>d__4::services
0x6af89  ldarg.0
0x6af8a  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6af8f  newobj   instance void Microsoft.VisualStudio.Setup.Validation.VSProcessesRunning::.ctor(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters precheckParameters)
0x6af94  stfld    class Microsoft.VisualStudio.Setup.Validation.IPrecheckEvaluator <GetPrecheckEvaluators>d__4::<>2__current
0x6af99  ldarg.0
0x6af9a  ldc.i4.7
0x6af9b  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6afa0  ldc.i4.1
0x6afa1  ret
0x6afa2  ldarg.0
0x6afa3  ldc.i4.m1
0x6afa4  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6afa9  ldarg.0
0x6afaa  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6afaf  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_PrecheckSupport()
0x6afb4  call     valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.AnotherInstallationRunning::get_PrecheckSupport()
0x6afb9  and
0x6afba  brfalse.s loc_6AFE3
0x6afbc  ldarg.0
0x6afbd  ldarg.0
0x6afbe  ldfld    class [mscorlib]System.IServiceProvider <GetPrecheckEvaluators>d__4::services
0x6afc3  ldarg.0
0x6afc4  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6afc9  newobj   instance void Microsoft.VisualStudio.Setup.Validation.AnotherInstallationRunning::.ctor(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters precheckParameters)
0x6afce  stfld    class Microsoft.VisualStudio.Setup.Validation.IPrecheckEvaluator <GetPrecheckEvaluators>d__4::<>2__current
0x6afd3  ldarg.0
0x6afd4  ldc.i4.8
0x6afd5  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6afda  ldc.i4.1
0x6afdb  ret
0x6afdc  ldarg.0
0x6afdd  ldc.i4.m1
0x6afde  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6afe3  ldarg.0
0x6afe4  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6afe9  callvirt instance bool Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_IsLayoutSet()
0x6afee  brfalse.s loc_6B02B
0x6aff0  ldarg.0
0x6aff1  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6aff6  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_PrecheckSupport()
0x6affb  call     valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::get_PrecheckSupport()
0x6b000  and
0x6b001  brfalse.s loc_6B02B
0x6b003  ldarg.0
0x6b004  ldarg.0
0x6b005  ldfld    class [mscorlib]System.IServiceProvider <GetPrecheckEvaluators>d__4::services
0x6b00a  ldarg.0
0x6b00b  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6b010  newobj   instance void Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::.ctor(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters precheckParameters)
0x6b015  stfld    class Microsoft.VisualStudio.Setup.Validation.IPrecheckEvaluator <GetPrecheckEvaluators>d__4::<>2__current
0x6b01a  ldarg.0
0x6b01b  ldc.i4.s 9
0x6b01d  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6b022  ldc.i4.1
0x6b023  ret
0x6b024  ldarg.0
0x6b025  ldc.i4.m1
0x6b026  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6b02b  ldarg.0
0x6b02c  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6b031  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_PrecheckSupport()
0x6b036  call     valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.OutOfSupportSelectablesCheck::get_PrecheckSupport()
0x6b03b  and
0x6b03c  brfalse.s loc_6B066
0x6b03e  ldarg.0
0x6b03f  ldarg.0
0x6b040  ldfld    class [mscorlib]System.IServiceProvider <GetPrecheckEvaluators>d__4::services
0x6b045  ldarg.0
0x6b046  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6b04b  newobj   instance void Microsoft.VisualStudio.Setup.Validation.OutOfSupportSelectablesCheck::.ctor(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters precheckParameters)
0x6b050  stfld    class Microsoft.VisualStudio.Setup.Validation.IPrecheckEvaluator <GetPrecheckEvaluators>d__4::<>2__current
0x6b055  ldarg.0
0x6b056  ldc.i4.s 0xA
0x6b058  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6b05d  ldc.i4.1
0x6b05e  ret
0x6b05f  ldarg.0
0x6b060  ldc.i4.m1
0x6b061  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6b066  ldarg.0
0x6b067  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6b06c  callvirt instance valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.PrecheckParameters::get_PrecheckSupport()
0x6b071  call     valuetype Microsoft.VisualStudio.Setup.Validation.PrecheckSupport Microsoft.VisualStudio.Setup.Validation.ArmMachineCheck::get_PrecheckSupport()
0x6b076  and
0x6b077  brfalse.s loc_6B0A1
0x6b079  ldarg.0
0x6b07a  ldarg.0
0x6b07b  ldfld    class [mscorlib]System.IServiceProvider <GetPrecheckEvaluators>d__4::services
0x6b080  ldarg.0
0x6b081  ldfld    class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters <GetPrecheckEvaluators>d__4::precheckParams
0x6b086  newobj   instance void Microsoft.VisualStudio.Setup.Validation.ArmMachineCheck::.ctor(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.Validation.PrecheckParameters precheckParameters)
0x6b08b  stfld    class Microsoft.VisualStudio.Setup.Validation.IPrecheckEvaluator <GetPrecheckEvaluators>d__4::<>2__current
0x6b090  ldarg.0
0x6b091  ldc.i4.s 0xB
0x6b093  stfld    int32 <GetPrecheckEvaluators>d__4::<>1__state
0x6b098  ldc.i4.1
0x6b099  ret
  ... truncated ...
```
