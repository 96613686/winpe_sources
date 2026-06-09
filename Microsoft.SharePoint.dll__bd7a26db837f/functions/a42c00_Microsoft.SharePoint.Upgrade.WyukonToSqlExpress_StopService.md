# Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::StopService

- ea: `0xa42c00`
- end: `0xa42f6c`
- name: `Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::StopService`
- size: `876`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xa419d0`
- `0xa42800`

## callees

- `0xa418e0`
- `0xa42c00`
- `0xa4f180`
- `0xa4f2c0`

## string_xrefs

- `0xa42c59`: `serviceName`
- `0xa42c44`: `Must have a serviceName`
- `0xa42e96`: `Service status {0} for server {1} is unknown`
- `0xa42c10`: `Entering StopService`
- `0xa42c89`: `Trying to stop service {0} and waiting {1} sec to do so`
- `0xa42cf7`: `service {0} is ContinuePending, will wait until it is started, then stop it`
- `0xa42d3a`: `service {0} is Paused, will try to stop it now`
- `0xa42d75`: `service {0} is PausePending, will wait for it to get out of a pending state and stop it`
- `0xa42db8`: `service {0} is Running, so will stop it`
- `0xa42df3`: `service {0} is StartPending, so will wait for it to start, then will stop it`
- `0xa42e36`: `service {0} is already Stopped`
- `0xa42e66`: `service {0} is StopPending`
- `0xa42ed9`: `stopping service {0} (it may already be stopped)`
- `0xa42f12`: `An exception was encountered when trying to stop service {0}, {1}`
- `0xa42f54`: `Leaving StopService`

## pseudocode

```c

```

## disassembly

```asm
0xa42c00  ldarg.0
0xa42c01  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42c06  ldc.i4   0x25854E
0xa42c0b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42c10  ldstr    aEnteringStopse// "Entering StopService"
0xa42c15  ldc.i4.0
0xa42c16  newarr   [mscorlib]System.Object
0xa42c1b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42c20  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42c25  ldnull
0xa42c26  stloc.0
0xa42c27  ldc.i4.0
0xa42c28  stloc.1
0xa42c29  ldarg.1
0xa42c2a  brfalse.s loc_A42C34
0xa42c2c  ldarg.1
0xa42c2d  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa42c32  brtrue.s loc_A42C64
0xa42c34  ldarg.0
0xa42c35  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42c3a  ldc.i4   0x25854F
0xa42c3f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42c44  ldstr    aMustHaveAServi// "Must have a serviceName"
0xa42c49  ldc.i4.0
0xa42c4a  newarr   [mscorlib]System.Object
0xa42c4f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42c54  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42c59  ldstr    aServicename_0// "serviceName"
0xa42c5e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa42c63  throw
0xa42c64  ldarg.1
0xa42c65  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor(string)
0xa42c6a  stloc.0
0xa42c6b  ldloca.s 2
0xa42c6d  ldc.i4.0
0xa42c6e  ldc.i4.0
0xa42c6f  ldc.i4   0xB4
0xa42c74  call     instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xa42c79  ldarg.0
0xa42c7a  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42c7f  ldc.i4   0x258550
0xa42c84  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42c89  ldstr    aTryingToStopSe// "Trying to stop service {0} and waiting "...
0xa42c8e  ldc.i4.2
0xa42c8f  newarr   [mscorlib]System.Object
0xa42c94  stloc.s  4
0xa42c96  ldloc.s  4
0xa42c98  ldc.i4.0
0xa42c99  ldarg.1
0xa42c9a  stelem.ref
0xa42c9b  ldloc.s  4
0xa42c9d  ldc.i4.1
0xa42c9e  ldc.i4   0xB4
0xa42ca3  box      [mscorlib]System.Int32
0xa42ca8  stelem.ref
0xa42ca9  ldloc.s  4
0xa42cab  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42cb0  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42cb5  ldloc.0
0xa42cb6  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0xa42cbb  stloc.s  5
0xa42cbd  ldloc.s  5
0xa42cbf  ldc.i4.1
0xa42cc0  sub
0xa42cc1  switch   loc_A42E26, loc_A42DE3, loc_A42E56, loc_A42DA8, loc_A42CE7, loc_A42D65, loc_A42D2A
0xa42ce2  br       loc_A42E86
0xa42ce7  ldarg.0
0xa42ce8  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42ced  ldc.i4   0x258551
0xa42cf2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42cf7  ldstr    aService0IsCont_0// "service {0} is ContinuePending, will wa"...
0xa42cfc  ldc.i4.1
0xa42cfd  newarr   [mscorlib]System.Object
0xa42d02  stloc.s  6
0xa42d04  ldloc.s  6
0xa42d06  ldc.i4.0
0xa42d07  ldarg.1
0xa42d08  stelem.ref
0xa42d09  ldloc.s  6
0xa42d0b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42d10  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42d15  ldloc.0
0xa42d16  ldc.i4.4
0xa42d17  ldloc.2
0xa42d18  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0xa42d1d  ldloc.0
0xa42d1e  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Stop()
0xa42d23  ldc.i4.1
0xa42d24  stloc.1
0xa42d25  br       loc_A42EC9
0xa42d2a  ldarg.0
0xa42d2b  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42d30  ldc.i4   0x258552
0xa42d35  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42d3a  ldstr    aService0IsPaus_2// "service {0} is Paused, will try to stop"...
0xa42d3f  ldc.i4.1
0xa42d40  newarr   [mscorlib]System.Object
0xa42d45  stloc.s  7
0xa42d47  ldloc.s  7
0xa42d49  ldc.i4.0
0xa42d4a  ldarg.1
0xa42d4b  stelem.ref
0xa42d4c  ldloc.s  7
0xa42d4e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42d53  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42d58  ldloc.0
0xa42d59  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Stop()
0xa42d5e  ldc.i4.1
0xa42d5f  stloc.1
0xa42d60  br       loc_A42EC9
0xa42d65  ldarg.0
0xa42d66  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42d6b  ldc.i4   0x258553
0xa42d70  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42d75  ldstr    aService0IsPaus_3// "service {0} is PausePending, will wait "...
0xa42d7a  ldc.i4.1
0xa42d7b  newarr   [mscorlib]System.Object
0xa42d80  stloc.s  8
0xa42d82  ldloc.s  8
0xa42d84  ldc.i4.0
0xa42d85  ldarg.1
0xa42d86  stelem.ref
0xa42d87  ldloc.s  8
0xa42d89  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42d8e  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42d93  ldloc.0
0xa42d94  ldc.i4.7
0xa42d95  ldloc.2
0xa42d96  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0xa42d9b  ldloc.0
0xa42d9c  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Stop()
0xa42da1  ldc.i4.1
0xa42da2  stloc.1
0xa42da3  br       loc_A42EC9
0xa42da8  ldarg.0
0xa42da9  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42dae  ldc.i4   0x258554
0xa42db3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42db8  ldstr    aService0IsRunn_0// "service {0} is Running, so will stop it"
0xa42dbd  ldc.i4.1
0xa42dbe  newarr   [mscorlib]System.Object
0xa42dc3  stloc.s  9
0xa42dc5  ldloc.s  9
0xa42dc7  ldc.i4.0
0xa42dc8  ldarg.1
0xa42dc9  stelem.ref
0xa42dca  ldloc.s  9
0xa42dcc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42dd1  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42dd6  ldloc.0
0xa42dd7  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Stop()
0xa42ddc  ldc.i4.1
0xa42ddd  stloc.1
0xa42dde  br       loc_A42EC9
0xa42de3  ldarg.0
0xa42de4  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42de9  ldc.i4   0x258555
0xa42dee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42df3  ldstr    aService0IsStar_0// "service {0} is StartPending, so will wa"...
0xa42df8  ldc.i4.1
0xa42df9  newarr   [mscorlib]System.Object
0xa42dfe  stloc.s  0xA
0xa42e00  ldloc.s  0xA
0xa42e02  ldc.i4.0
0xa42e03  ldarg.1
0xa42e04  stelem.ref
0xa42e05  ldloc.s  0xA
0xa42e07  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42e0c  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42e11  ldloc.0
0xa42e12  ldc.i4.4
0xa42e13  ldloc.2
0xa42e14  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0xa42e19  ldloc.0
0xa42e1a  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Stop()
0xa42e1f  ldc.i4.1
0xa42e20  stloc.1
0xa42e21  br       loc_A42EC9
0xa42e26  ldarg.0
0xa42e27  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42e2c  ldc.i4   0x258556
0xa42e31  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42e36  ldstr    aService0IsAlre// "service {0} is already Stopped"
0xa42e3b  ldc.i4.1
0xa42e3c  newarr   [mscorlib]System.Object
0xa42e41  stloc.s  0xB
0xa42e43  ldloc.s  0xB
0xa42e45  ldc.i4.0
0xa42e46  ldarg.1
0xa42e47  stelem.ref
0xa42e48  ldloc.s  0xB
0xa42e4a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42e4f  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42e54  br.s     loc_A42EC9
0xa42e56  ldarg.0
0xa42e57  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42e5c  ldc.i4   0x258557
0xa42e61  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42e66  ldstr    aService0IsStop_2// "service {0} is StopPending"
0xa42e6b  ldc.i4.1
0xa42e6c  newarr   [mscorlib]System.Object
0xa42e71  stloc.s  0xC
0xa42e73  ldloc.s  0xC
0xa42e75  ldc.i4.0
0xa42e76  ldarg.1
0xa42e77  stelem.ref
0xa42e78  ldloc.s  0xC
0xa42e7a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42e7f  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42e84  br.s     loc_A42EC9
0xa42e86  ldarg.0
0xa42e87  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42e8c  ldc.i4   0x258558
0xa42e91  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42e96  ldstr    aServiceStatus0// "Service status {0} for server {1} is un"...
0xa42e9b  ldc.i4.2
0xa42e9c  newarr   [mscorlib]System.Object
0xa42ea1  stloc.s  0xD
0xa42ea3  ldloc.s  0xD
0xa42ea5  ldc.i4.0
0xa42ea6  ldloc.0
0xa42ea7  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0xa42eac  box      [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus
0xa42eb1  stelem.ref
0xa42eb2  ldloc.s  0xD
0xa42eb4  ldc.i4.1
0xa42eb5  ldarg.1
0xa42eb6  stelem.ref
0xa42eb7  ldloc.s  0xD
0xa42eb9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42ebe  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::ErrorTag(unsigned int32 tagID, string output)
0xa42ec3  newobj   instance void [mscorlib]System.ArgumentException::.ctor()
0xa42ec8  throw
0xa42ec9  ldarg.0
0xa42eca  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42ecf  ldc.i4   0x258559
0xa42ed4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42ed9  ldstr    aStoppingServic// "stopping service {0} (it may already be"...
0xa42ede  ldc.i4.1
0xa42edf  newarr   [mscorlib]System.Object
0xa42ee4  stloc.s  0xE
0xa42ee6  ldloc.s  0xE
0xa42ee8  ldc.i4.0
0xa42ee9  ldarg.1
0xa42eea  stelem.ref
0xa42eeb  ldloc.s  0xE
0xa42eed  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42ef2  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42ef7  ldloc.0
0xa42ef8  ldc.i4.1
0xa42ef9  ldloc.2
0xa42efa  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0xa42eff  leave.s  loc_A42F39
0xa42f01  stloc.3
0xa42f02  ldarg.0
0xa42f03  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42f08  ldc.i4   0x25855A
0xa42f0d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42f12  ldstr    aAnExceptionWas_14// "An exception was encountered when tryin"...
0xa42f17  ldc.i4.2
0xa42f18  newarr   [mscorlib]System.Object
0xa42f1d  stloc.s  0xF
0xa42f1f  ldloc.s  0xF
0xa42f21  ldc.i4.0
0xa42f22  ldarg.1
0xa42f23  stelem.ref
0xa42f24  ldloc.s  0xF
0xa42f26  ldc.i4.1
0xa42f27  ldloc.3
0xa42f28  stelem.ref
0xa42f29  ldloc.s  0xF
0xa42f2b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42f30  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::ErrorTag(unsigned int32 tagID, string output)
0xa42f35  ldc.i4.0
0xa42f36  stloc.1
0xa42f37  rethrow
0xa42f39  leave.s  loc_A42F6A
0xa42f3b  ldloc.0
0xa42f3c  brfalse.s loc_A42F44
0xa42f3e  ldloc.0
0xa42f3f  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0xa42f44  ldarg.0
0xa42f45  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.WyukonToSqlExpress::get_Log()
0xa42f4a  ldc.i4   0x25855B
0xa42f4f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42f54  ldstr    aLeavingStopser// "Leaving StopService"
0xa42f59  ldc.i4.0
0xa42f5a  newarr   [mscorlib]System.Object
0xa42f5f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa42f64  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa42f69  endfinally
0xa42f6a  ldloc.1
0xa42f6b  ret
```
