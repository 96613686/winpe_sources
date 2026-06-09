# Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::StartService

- ea: `0xa42820`
- end: `0xa42bf7`
- name: `Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::StartService`
- size: `983`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xa42800`

## callees

- `0xa418e0`
- `0xa42820`
- `0xa4f180`
- `0xa4f2c0`

## string_xrefs

- `0xa42879`: `serviceName`
- `0xa42830`: `Entering StartService`
- `0xa42864`: `Must have a serviceName`
- `0xa428a9`: `Trying to start service {0} and waiting {1} sec to do so`
- `0xa42917`: `service {0} is ContinuePending`
- `0xa4294a`: `service {0} is Paused, will continue it`
- `0xa42985`: `service {0} is PausePending, will wait {1} for it to become paused`
- `0xa429c9`: `service {0} is paused, will continue it`
- `0xa42a04`: `service {0} is Running, nothing to do `
- `0xa42a37`: `service {0} is StartPending`
- `0xa42a6a`: `service {0} is Stopped, will try to start it`
- `0xa42aa5`: `service {0} is StopPending, will wait {1} for it to stop`
- `0xa42ae9`: `service {0} is stopped, will start it`
- `0xa42b21`: `Service status {0} for server {1} is unknown`
- `0xa42b64`: `starting service {0} (it may already be started)`
- `0xa42b9d`: `An exception was encountered when trying to start service {0}, {1}`
- `0xa42bdf`: `Leaving StartService`

## pseudocode

```c

```

## disassembly

```asm
0xa42820  ldarg.0
0xa42821  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42826  ldc.i4   0x258522
0xa4282b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42830  ldstr    aEnteringStarts// "Entering StartService"
0xa42835  ldc.i4.0
0xa42836  newarr   [mscorlib]System.Object
0xa4283b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42840  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42845  ldnull
0xa42846  stloc.0
0xa42847  ldc.i4.0
0xa42848  stloc.1
0xa42849  ldarg.1
0xa4284a  brfalse.s loc_A42854
0xa4284c  ldarg.1
0xa4284d  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa42852  brtrue.s loc_A42884
0xa42854  ldarg.0
0xa42855  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa4285a  ldc.i4   0x258523
0xa4285f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42864  ldstr    aMustHaveAServi// "Must have a serviceName"
0xa42869  ldc.i4.0
0xa4286a  newarr   [mscorlib]System.Object
0xa4286f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42874  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42879  ldstr    aServicename_0// "serviceName"
0xa4287e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa42883  throw
0xa42884  ldarg.1
0xa42885  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor(string)
0xa4288a  stloc.0
0xa4288b  ldloca.s 2
0xa4288d  ldc.i4.0
0xa4288e  ldc.i4.0
0xa4288f  ldc.i4   0xB4
0xa42894  call     instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xa42899  ldarg.0
0xa4289a  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa4289f  ldc.i4   0x258540
0xa428a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa428a9  ldstr    aTryingToStartS// "Trying to start service {0} and waiting"...
0xa428ae  ldc.i4.2
0xa428af  newarr   [mscorlib]System.Object
0xa428b4  stloc.s  4
0xa428b6  ldloc.s  4
0xa428b8  ldc.i4.0
0xa428b9  ldarg.1
0xa428ba  stelem.ref
0xa428bb  ldloc.s  4
0xa428bd  ldc.i4.1
0xa428be  ldc.i4   0xB4
0xa428c3  box      [mscorlib]System.Int32
0xa428c8  stelem.ref
0xa428c9  ldloc.s  4
0xa428cb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa428d0  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa428d5  ldloc.0
0xa428d6  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0xa428db  stloc.s  5
0xa428dd  ldloc.s  5
0xa428df  ldc.i4.1
0xa428e0  sub
0xa428e1  switch   loc_A42A5A, loc_A42A27, loc_A42A95, loc_A429F4, loc_A42907, loc_A42975, loc_A4293A
0xa42902  br       loc_A42B11
0xa42907  ldarg.0
0xa42908  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa4290d  ldc.i4   0x258541
0xa42912  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42917  ldstr    aService0IsCont// "service {0} is ContinuePending"
0xa4291c  ldc.i4.1
0xa4291d  newarr   [mscorlib]System.Object
0xa42922  stloc.s  6
0xa42924  ldloc.s  6
0xa42926  ldc.i4.0
0xa42927  ldarg.1
0xa42928  stelem.ref
0xa42929  ldloc.s  6
0xa4292b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42930  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42935  br       loc_A42B54
0xa4293a  ldarg.0
0xa4293b  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42940  ldc.i4   0x258542
0xa42945  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa4294a  ldstr    aService0IsPaus// "service {0} is Paused, will continue it"
0xa4294f  ldc.i4.1
0xa42950  newarr   [mscorlib]System.Object
0xa42955  stloc.s  7
0xa42957  ldloc.s  7
0xa42959  ldc.i4.0
0xa4295a  ldarg.1
0xa4295b  stelem.ref
0xa4295c  ldloc.s  7
0xa4295e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42963  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42968  ldloc.0
0xa42969  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Continue()
0xa4296e  ldc.i4.1
0xa4296f  stloc.1
0xa42970  br       loc_A42B54
0xa42975  ldarg.0
0xa42976  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa4297b  ldc.i4   0x258543
0xa42980  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42985  ldstr    aService0IsPaus_0// "service {0} is PausePending, will wait "...
0xa4298a  ldc.i4.2
0xa4298b  newarr   [mscorlib]System.Object
0xa42990  stloc.s  8
0xa42992  ldloc.s  8
0xa42994  ldc.i4.0
0xa42995  ldarg.1
0xa42996  stelem.ref
0xa42997  ldloc.s  8
0xa42999  ldc.i4.1
0xa4299a  ldc.i4   0xB4
0xa4299f  box      [mscorlib]System.Int32
0xa429a4  stelem.ref
0xa429a5  ldloc.s  8
0xa429a7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa429ac  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa429b1  ldloc.0
0xa429b2  ldc.i4.7
0xa429b3  ldloc.2
0xa429b4  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0xa429b9  ldarg.0
0xa429ba  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa429bf  ldc.i4   0x258544
0xa429c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa429c9  ldstr    aService0IsPaus_1// "service {0} is paused, will continue it"
0xa429ce  ldc.i4.1
0xa429cf  newarr   [mscorlib]System.Object
0xa429d4  stloc.s  9
0xa429d6  ldloc.s  9
0xa429d8  ldc.i4.0
0xa429d9  ldarg.1
0xa429da  stelem.ref
0xa429db  ldloc.s  9
0xa429dd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa429e2  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa429e7  ldloc.0
0xa429e8  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Continue()
0xa429ed  ldc.i4.1
0xa429ee  stloc.1
0xa429ef  br       loc_A42B54
0xa429f4  ldarg.0
0xa429f5  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa429fa  ldc.i4   0x258545
0xa429ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42a04  ldstr    aService0IsRunn// "service {0} is Running, nothing to do "
0xa42a09  ldc.i4.1
0xa42a0a  newarr   [mscorlib]System.Object
0xa42a0f  stloc.s  0xA
0xa42a11  ldloc.s  0xA
0xa42a13  ldc.i4.0
0xa42a14  ldarg.1
0xa42a15  stelem.ref
0xa42a16  ldloc.s  0xA
0xa42a18  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42a1d  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42a22  br       loc_A42B54
0xa42a27  ldarg.0
0xa42a28  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42a2d  ldc.i4   0x258546
0xa42a32  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42a37  ldstr    aService0IsStar// "service {0} is StartPending"
0xa42a3c  ldc.i4.1
0xa42a3d  newarr   [mscorlib]System.Object
0xa42a42  stloc.s  0xB
0xa42a44  ldloc.s  0xB
0xa42a46  ldc.i4.0
0xa42a47  ldarg.1
0xa42a48  stelem.ref
0xa42a49  ldloc.s  0xB
0xa42a4b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42a50  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42a55  br       loc_A42B54
0xa42a5a  ldarg.0
0xa42a5b  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42a60  ldc.i4   0x258547
0xa42a65  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42a6a  ldstr    aService0IsStop// "service {0} is Stopped, will try to sta"...
0xa42a6f  ldc.i4.1
0xa42a70  newarr   [mscorlib]System.Object
0xa42a75  stloc.s  0xC
0xa42a77  ldloc.s  0xC
0xa42a79  ldc.i4.0
0xa42a7a  ldarg.1
0xa42a7b  stelem.ref
0xa42a7c  ldloc.s  0xC
0xa42a7e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42a83  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42a88  ldloc.0
0xa42a89  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Start()
0xa42a8e  ldc.i4.1
0xa42a8f  stloc.1
0xa42a90  br       loc_A42B54
0xa42a95  ldarg.0
0xa42a96  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42a9b  ldc.i4   0x258548
0xa42aa0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42aa5  ldstr    aService0IsStop_0// "service {0} is StopPending, will wait {"...
0xa42aaa  ldc.i4.2
0xa42aab  newarr   [mscorlib]System.Object
0xa42ab0  stloc.s  0xD
0xa42ab2  ldloc.s  0xD
0xa42ab4  ldc.i4.0
0xa42ab5  ldarg.1
0xa42ab6  stelem.ref
0xa42ab7  ldloc.s  0xD
0xa42ab9  ldc.i4.1
0xa42aba  ldc.i4   0xB4
0xa42abf  box      [mscorlib]System.Int32
0xa42ac4  stelem.ref
0xa42ac5  ldloc.s  0xD
0xa42ac7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42acc  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42ad1  ldloc.0
0xa42ad2  ldc.i4.1
0xa42ad3  ldloc.2
0xa42ad4  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0xa42ad9  ldarg.0
0xa42ada  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42adf  ldc.i4   0x258549
0xa42ae4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42ae9  ldstr    aService0IsStop_1// "service {0} is stopped, will start it"
0xa42aee  ldc.i4.1
0xa42aef  newarr   [mscorlib]System.Object
0xa42af4  stloc.s  0xE
0xa42af6  ldloc.s  0xE
0xa42af8  ldc.i4.0
0xa42af9  ldarg.1
0xa42afa  stelem.ref
0xa42afb  ldloc.s  0xE
0xa42afd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42b02  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42b07  ldloc.0
0xa42b08  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Start()
0xa42b0d  ldc.i4.1
0xa42b0e  stloc.1
0xa42b0f  br.s     loc_A42B54
0xa42b11  ldarg.0
0xa42b12  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42b17  ldc.i4   0x25854A
0xa42b1c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42b21  ldstr    aServiceStatus0// "Service status {0} for server {1} is un"...
0xa42b26  ldc.i4.2
0xa42b27  newarr   [mscorlib]System.Object
0xa42b2c  stloc.s  0xF
0xa42b2e  ldloc.s  0xF
0xa42b30  ldc.i4.0
0xa42b31  ldloc.0
0xa42b32  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0xa42b37  box      [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus
0xa42b3c  stelem.ref
0xa42b3d  ldloc.s  0xF
0xa42b3f  ldc.i4.1
0xa42b40  ldarg.1
0xa42b41  stelem.ref
0xa42b42  ldloc.s  0xF
0xa42b44  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42b49  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::ErrorTag(unsigned int32 tagID, string output)
0xa42b4e  newobj   instance void [mscorlib]System.ArgumentException::.ctor()
0xa42b53  throw
0xa42b54  ldarg.0
0xa42b55  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42b5a  ldc.i4   0x25854B
0xa42b5f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42b64  ldstr    aStartingServic// "starting service {0} (it may already be"...
0xa42b69  ldc.i4.1
0xa42b6a  newarr   [mscorlib]System.Object
0xa42b6f  stloc.s  0x10
0xa42b71  ldloc.s  0x10
0xa42b73  ldc.i4.0
0xa42b74  ldarg.1
0xa42b75  stelem.ref
0xa42b76  ldloc.s  0x10
0xa42b78  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42b7d  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42b82  ldloc.0
0xa42b83  ldc.i4.4
0xa42b84  ldloc.2
0xa42b85  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0xa42b8a  leave.s  loc_A42BC4
0xa42b8c  stloc.3
0xa42b8d  ldarg.0
0xa42b8e  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42b93  ldc.i4   0x25854C
0xa42b98  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42b9d  ldstr    aAnExceptionWas_13// "An exception was encountered when tryin"...
0xa42ba2  ldc.i4.2
0xa42ba3  newarr   [mscorlib]System.Object
0xa42ba8  stloc.s  0x11
0xa42baa  ldloc.s  0x11
0xa42bac  ldc.i4.0
0xa42bad  ldarg.1
0xa42bae  stelem.ref
0xa42baf  ldloc.s  0x11
0xa42bb1  ldc.i4.1
  ... truncated ...
```
