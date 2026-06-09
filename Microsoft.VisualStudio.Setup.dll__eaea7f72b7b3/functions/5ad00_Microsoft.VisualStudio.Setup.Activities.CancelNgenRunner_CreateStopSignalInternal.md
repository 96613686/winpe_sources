# Microsoft.VisualStudio.Setup.Activities.CancelNgenRunner::CreateStopSignalInternal

- ea: `0x5ad00`
- end: `0x5ad72`
- name: `Microsoft.VisualStudio.Setup.Activities.CancelNgenRunner::CreateStopSignalInternal`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5ac70`

## callees

- `0x45480`
- `0x596d0`
- `0x596f0`
- `0x5ac90`
- `0x5ad00`

## string_xrefs

- `0x5ad47`: `Error occurred while opening existing StopSignal for Global\VS_NgenRunnerCancel`
- `0x5ad5d`: `InstallScheduler`
- `0x5ad62`: `Exception in OpenExisting StopSignal`

## pseudocode

```c

```

## disassembly

```asm
0x5ad00  ldstr    aGlobalVsNgenru// "Global\\VS_NgenRunnerCancel"
0x5ad05  ldc.i4.1
0x5ad06  call     class Microsoft.VisualStudio.Setup.Services.StopSignal Microsoft.VisualStudio.Setup.Services.StopSignal::OpenExisting(string syncEventName, [opt] bool executeOnlyOnce)
0x5ad0b  stloc.0
0x5ad0c  leave.s  loc_5AD70
0x5ad0e  stloc.1
0x5ad0f  ldarg.0
0x5ad10  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5ad15  dup
0x5ad16  brtrue.s loc_5AD1B
0x5ad18  pop
0x5ad19  br.s     loc_5AD35
0x5ad1b  ldstr    aExistingStopsi// "Existing StopSignal 'Global\\VS_NgenRun"...
0x5ad20  ldloc.1
0x5ad21  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5ad26  call     string [mscorlib]System.String::Concat(string, string)
0x5ad2b  call     T0x2B000003
0x5ad30  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5ad35  ldnull
0x5ad36  stloc.0
0x5ad37  leave.s  loc_5AD70
0x5ad39  stloc.2
0x5ad3a  ldarg.0
0x5ad3b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5ad40  dup
0x5ad41  brtrue.s loc_5AD46
0x5ad43  pop
0x5ad44  br.s     loc_5AD56
0x5ad46  ldloc.2
0x5ad47  ldstr    aErrorOccurredW_3// "Error occurred while opening existing S"...
0x5ad4c  call     T0x2B000003
0x5ad51  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x5ad56  ldarg.0
0x5ad57  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5ad5c  ldloc.2
0x5ad5d  ldstr    aInstallschedul// "InstallScheduler"
0x5ad62  ldstr    aExceptionInOpe// "Exception in OpenExisting StopSignal"
0x5ad67  call     void Microsoft.VisualStudio.Setup.Activities.CancelNgenRunner::WriteNgenRunnerFault(class [mscorlib]System.IServiceProvider services, class [mscorlib]System.Exception exception, string faultLocation, string faultDescription)
0x5ad6c  ldnull
0x5ad6d  stloc.0
0x5ad6e  leave.s  loc_5AD70
0x5ad70  ldloc.0
0x5ad71  ret
```
