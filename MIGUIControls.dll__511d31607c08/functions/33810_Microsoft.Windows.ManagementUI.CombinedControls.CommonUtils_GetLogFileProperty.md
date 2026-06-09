# Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetLogFileProperty

- ea: `0x33810`
- end: `0x3396f`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetLogFileProperty`
- size: `351`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x2d7e0`
- `0x33800`
- `0x42ac0`

## callees

- `0x12670`
- `0x126b0`
- `0x12830`
- `0x12840`
- `0x12880`
- `0x12ed0`
- `0x13510`
- `0x32e90`
- `0x33120`
- `0x33810`
- `0x33e70`
- `0x45d60`
- `0x4d1f0`
- `0x4d200`
- `0x4d210`

## string_xrefs

- `0x33848`: `ERR_UNABLE_TO_OPEN_LOG`
- `0x33949`: `ERR_UNABLE_TO_OPEN_LOG`

## pseudocode

```c

```

## disassembly

```asm
0x33810  ldc.i4.0
0x33811  stloc.0
0x33812  ldnull
0x33813  stloc.1
0x33814  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x33819  leave    loc_3396D
0x3381e  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::.ctor()
0x33823  stloc.2
0x33824  ldarg.1
0x33825  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetChannelPathWithoutFilePrefix(string channelPath)
0x3382a  starg.s  1
0x3382c  ldarg.0
0x3382d  ldarg.1
0x3382e  ldarg.2
0x3382f  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::OpenLog(native int session, [hasfieldmarshal] string channelPath, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.LogOpenFlags flags)
0x33834  stloc.3
0x33835  ldloc.3
0x33836  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3383b  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x33840  brfalse.s loc_3386A
0x33842  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x33847  stloc.0
0x33848  ldstr    aErrUnableToOpe// "ERR_UNABLE_TO_OPEN_LOG"
0x3384d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x33852  ldstr    asc_AAAB6// " "
0x33857  ldarg.1
0x33858  call     string [mscorlib]System.String::Concat(string, string, string)
0x3385d  ldloc.0
0x3385e  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x33863  ldloc.0
0x33864  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.CrimsonException::.ctor(int32 error)
0x33869  throw
0x3386a  ldloc.2
0x3386b  ldloc.3
0x3386c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::InitHandle(native int crimsonHandle)
0x33871  ldc.i4.0
0x33872  stloc.s  4
0x33874  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x33879  stloc.s  5
0x3387b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeGlobalHandle::.ctor()
0x33880  stloc.s  6
0x33882  ldloca.s 7
0x33884  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x3388a  ldloc.s  7
0x3388c  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x33891  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x33896  stloc.s  8
0x33898  ldc.i4.0
0x33899  stloc.s  9
0x3389b  ldloc.3
0x3389c  ldarg.3
0x3389d  ldloc.s  8
0x3389f  ldloca.s 7
0x338a1  ldloca.s 4
0x338a3  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetLogInfo(native int log, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.LogPropertyIdentifier propertyId, int32 propertyValueBufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& propertyValueBuffer, int32& propertyValueBufferUsed)
0x338a8  stloc.s  9
0x338aa  ldloc.s  9
0x338ac  brtrue.s loc_338B4
0x338ae  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x338b3  stloc.0
0x338b4  ldloc.s  9
0x338b6  brtrue.s loc_33931
0x338b8  ldloc.s  4
0x338ba  ldloc.s  8
0x338bc  ble.s    loc_33931
0x338be  ldloc.0
0x338bf  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::IsInsufficientBuffer(int32 error)
0x338c4  brfalse.s loc_33931
0x338c6  ldloc.s  4
0x338c8  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x338cd  stloc.s  5
0x338cf  ldloc.s  5
0x338d1  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x338d6  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x338db  brfalse.s loc_33931
0x338dd  ldloc.s  6
0x338df  ldloc.s  5
0x338e1  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeGlobalHandle::InitHandle(native int inHandle)
0x338e6  ldloc.3
0x338e7  ldarg.3
0x338e8  ldloc.s  4
0x338ea  ldloc.s  5
0x338ec  ldloca.s 4
0x338ee  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetLogInfoB(native int log, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.LogPropertyIdentifier propertyId, int32 propertyValueBufferSize, native int propertyValueBuffer, int32& propertyValueBufferUsed)
0x338f3  stloc.s  9
0x338f5  ldloc.s  9
0x338f7  brtrue.s loc_33912
0x338f9  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x338fe  stloc.0
0x338ff  ldstr    aUnableToGetLog// "Unable to Get log property "
0x33904  ldarg.1
0x33905  call     string [mscorlib]System.String::Concat(string, string)
0x3390a  ldloc.0
0x3390b  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x33910  br.s     loc_3392A
0x33912  ldloc.s  5
0x33914  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x33919  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3391e  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x33923  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x33928  stloc.s  7
0x3392a  ldloc.s  6
0x3392c  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x33931  ldloc.s  9
0x33933  brfalse.s loc_33949
0x33935  ldloc.s  7
0x33937  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x3393c  stloc.1
0x3393d  ldloc.1
0x3393e  brtrue.s loc_33966
0x33940  ldc.i4.0
0x33941  box      [mscorlib]System.Int32
0x33946  stloc.1
0x33947  br.s     loc_33966
0x33949  ldstr    aErrUnableToOpe// "ERR_UNABLE_TO_OPEN_LOG"
0x3394e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x33953  ldstr    asc_AAAB6// " "
0x33958  ldarg.1
0x33959  call     string [mscorlib]System.String::Concat(string, string, string)
0x3395e  ldloc.0
0x3395f  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x33964  ldnull
0x33965  stloc.1
0x33966  ldloc.2
0x33967  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::Reset()
0x3396c  endfinally
0x3396d  ldloc.1
0x3396e  ret
```
