# Microsoft.VisualStudio.Setup.Services.OperatingSystem::GetShutdownPrivileges

- ea: `0x41370`
- end: `0x415ad`
- name: `Microsoft.VisualStudio.Setup.Services.OperatingSystem::GetShutdownPrivileges`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x412b0`

## callees

- `0x3ff10`
- `0x400c0`
- `0x400d0`
- `0x406f0`
- `0x40710`
- `0x40740`
- `0x40760`
- `0x41370`

## string_xrefs

- `0x413b2`: `Failed to get the process token privileges`
- `0x413cc`: `Failed to get the process token privileges with error: {0}`
- `0x41409`: `Failed to lookup shutdown privilege value`
- `0x41423`: `Failed to lookup shutdown privilege value with error: {0}`
- `0x41499`: `Failed to enable shutdown privileges to the current process`
- `0x414b1`: `Failed to adjust process privileges with error code: {0}`
- `0x4153c`: `GetShutdownPrivileges`

## pseudocode

```c

```

## disassembly

```asm
0x41370  ldarg.0
0x41371  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Services.OperatingSystem::services
0x41376  dup
0x41377  brtrue.s loc_4137D
0x41379  pop
0x4137a  ldnull
0x4137b  br.s     loc_41383
0x4137d  ldc.i4.0
0x4137e  call     T0x2B000051
0x41383  dup
0x41384  brtrue.s loc_4138C
0x41386  pop
0x41387  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.Services.ProcessService::Default
0x4138c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService::GetCurrentProcess()
0x41391  callvirt instance native int [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::get_Handle()
0x41396  stloc.0
0x41397  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4139c  stloc.1
0x4139d  ldloc.0
0x4139e  ldc.i4.s 0x28
0x413a0  ldloca.s 1
0x413a2  call     bool Microsoft.VisualStudio.Setup.Services.NativeMethods::OpenProcessToken([hasfieldmarshal] native int, valuetype Microsoft.VisualStudio.Setup.Services.AccessMask ProcessHandle, [hasfieldmarshal] native int& DesiredAccess)
0x413a7  brtrue.s loc_413E9
0x413a9  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x413ae  stloc.s  6
0x413b0  ldloc.s  6
0x413b2  ldstr    aFailedToGetThe_1// "Failed to get the process token privile"...
0x413b7  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32, string)
0x413bc  stloc.s  7
0x413be  ldarg.0
0x413bf  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.OperatingSystem::logger
0x413c4  dup
0x413c5  brtrue.s loc_413CA
0x413c7  pop
0x413c8  br.s     loc_413E6
0x413ca  ldloc.s  7
0x413cc  ldstr    aFailedToGetThe_2// "Failed to get the process token privile"...
0x413d1  ldc.i4.1
0x413d2  newarr   [mscorlib]System.Object
0x413d7  dup
0x413d8  ldc.i4.0
0x413d9  ldloc.s  6
0x413db  box      [mscorlib]System.Int32
0x413e0  stelem.ref
0x413e1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x413e6  ldloc.s  7
0x413e8  throw
0x413e9  ldloca.s 2
0x413eb  initobj  Microsoft.VisualStudio.Setup.Services.LUID
0x413f1  ldnull
0x413f2  ldsfld   string Microsoft.VisualStudio.Setup.Services.Privileges::SE_SHUTDOWN_NAME
0x413f7  ldloca.s 2
0x413f9  call     bool Microsoft.VisualStudio.Setup.Services.NativeMethods::LookupPrivilegeValue(string systemName, string privilegeName, valuetype Microsoft.VisualStudio.Setup.Services.LUID& luid)
0x413fe  brtrue.s loc_41440
0x41400  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x41405  stloc.s  8
0x41407  ldloc.s  8
0x41409  ldstr    aFailedToLookup// "Failed to lookup shutdown privilege val"...
0x4140e  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32, string)
0x41413  stloc.s  9
0x41415  ldarg.0
0x41416  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.OperatingSystem::logger
0x4141b  dup
0x4141c  brtrue.s loc_41421
0x4141e  pop
0x4141f  br.s     loc_4143D
0x41421  ldloc.s  9
0x41423  ldstr    aFailedToLookup_0// "Failed to lookup shutdown privilege val"...
0x41428  ldc.i4.1
0x41429  newarr   [mscorlib]System.Object
0x4142e  dup
0x4142f  ldc.i4.0
0x41430  ldloc.s  8
0x41432  box      [mscorlib]System.Int32
0x41437  stelem.ref
0x41438  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x4143d  ldloc.s  9
0x4143f  throw
0x41440  ldloca.s 0xA
0x41442  initobj  Microsoft.VisualStudio.Setup.Services.LUID_AND_ATTRIBUTES
0x41448  ldloca.s 0xA
0x4144a  ldc.i4.2
0x4144b  call     instance void Microsoft.VisualStudio.Setup.Services.LUID_AND_ATTRIBUTES::set_Attributes(unsigned int32 value)
0x41450  ldloca.s 0xA
0x41452  ldloc.2
0x41453  call     instance void Microsoft.VisualStudio.Setup.Services.LUID_AND_ATTRIBUTES::set_Luid(valuetype Microsoft.VisualStudio.Setup.Services.LUID value)
0x41458  ldloc.s  0xA
0x4145a  stloc.3
0x4145b  ldloca.s 0xB
0x4145d  initobj  Microsoft.VisualStudio.Setup.Services.TOKEN_PRIVILEGES
0x41463  ldloca.s 0xB
0x41465  ldc.i4.1
0x41466  call     instance void Microsoft.VisualStudio.Setup.Services.TOKEN_PRIVILEGES::set_PrivilegeCount(unsigned int32 value)
0x4146b  ldloca.s 0xB
0x4146d  ldloc.3
0x4146e  call     instance void Microsoft.VisualStudio.Setup.Services.TOKEN_PRIVILEGES::set_Privileges(valuetype Microsoft.VisualStudio.Setup.Services.LUID_AND_ATTRIBUTES value)
0x41473  ldloc.s  0xB
0x41475  stloc.s  4
0x41477  ldloc.1
0x41478  ldc.i4.0
0x41479  ldloca.s 4
0x4147b  ldc.i4.0
0x4147c  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x41481  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x41486  call     bool Microsoft.VisualStudio.Setup.Services.NativeMethods::AdjustTokenPrivileges(native int tokenHandle, bool disableAllPrivileges, valuetype Microsoft.VisualStudio.Setup.Services.TOKEN_PRIVILEGES& newState, unsigned int32 bufferLength, native int previousState, native int returnLength)
0x4148b  pop
0x4148c  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x41491  stloc.s  5
0x41493  ldloc.s  5
0x41495  brfalse.s loc_414CE
0x41497  ldloc.s  5
0x41499  ldstr    aFailedToEnable// "Failed to enable shutdown privileges to"...
0x4149e  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32, string)
0x414a3  stloc.s  0xC
0x414a5  ldarg.0
0x414a6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.OperatingSystem::logger
0x414ab  dup
0x414ac  brtrue.s loc_414B1
0x414ae  pop
0x414af  br.s     loc_414CB
0x414b1  ldstr    aFailedToAdjust// "Failed to adjust process privileges wit"...
0x414b6  ldc.i4.1
0x414b7  newarr   [mscorlib]System.Object
0x414bc  dup
0x414bd  ldc.i4.0
0x414be  ldloc.s  5
0x414c0  box      [mscorlib]System.Int32
0x414c5  stelem.ref
0x414c6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x414cb  ldloc.s  0xC
0x414cd  throw
0x414ce  ldc.i4.1
0x414cf  stloc.s  0xD
0x414d1  leave    loc_415AA
0x414d6  stloc.s  0xE
0x414d8  ldarg.0
0x414d9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.OperatingSystem::logger
0x414de  dup
0x414df  brtrue.s loc_41500
0x414e1  pop
0x414e2  ldarg.0
0x414e3  ldarg.0
0x414e4  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Services.OperatingSystem::services
0x414e9  dup
0x414ea  brtrue.s loc_414F0
0x414ec  pop
0x414ed  ldnull
0x414ee  br.s     loc_414F6
0x414f0  ldc.i4.0
0x414f1  call     T0x2B000001
0x414f6  dup
0x414f7  stloc.s  0x10
0x414f9  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.OperatingSystem::logger
0x414fe  ldloc.s  0x10
0x41500  dup
0x41501  brtrue.s loc_41506
0x41503  pop
0x41504  br.s     loc_41519
0x41506  ldloc.s  0xE
0x41508  ldloc.s  0xE
0x4150a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4150f  call     T0x2B000003
0x41514  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x41519  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x4151e  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x41523  stloc.s  0x11
0x41525  dup
0x41526  ldloc.s  0x11
0x41528  ldstr    aOperatingsyste// "OperatingSystem"
0x4152d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x41532  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x41537  stloc.s  0x12
0x41539  dup
0x4153a  ldloc.s  0x12
0x4153c  ldstr    aGetshutdownpri// "GetShutdownPrivileges"
0x41541  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x41546  stloc.s  0xF
0x41548  ldarg.0
0x41549  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Services.OperatingSystem::services
0x4154e  dup
0x4154f  brtrue.s loc_41555
0x41551  pop
0x41552  ldnull
0x41553  br.s     loc_4155B
0x41555  ldc.i4.0
0x41556  call     T0x2B000039
0x4155b  dup
0x4155c  brtrue.s loc_41561
0x4155e  pop
0x4155f  br.s     loc_4157C
0x41561  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x41566  ldloc.s  0xE
0x41568  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4156d  ldloc.s  0xF
0x4156f  ldloc.s  0xE
0x41571  ldnull
0x41572  ldc.i4.0
0x41573  ldnull
0x41574  ldc.i4.0
0x41575  ldnull
0x41576  ldc.i4.0
0x41577  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x4157c  ldc.i4.0
0x4157d  stloc.s  0xD
0x4157f  leave.s  loc_415AA
0x41581  ldloc.0
0x41582  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x41587  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x4158c  brfalse.s loc_41595
0x4158e  ldloc.0
0x4158f  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::Release(native int)
0x41594  pop
0x41595  ldloc.1
0x41596  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4159b  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x415a0  brfalse.s loc_415A9
0x415a2  ldloc.1
0x415a3  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::Release(native int)
0x415a8  pop
0x415a9  endfinally
0x415aa  ldloc.s  0xD
0x415ac  ret
```
