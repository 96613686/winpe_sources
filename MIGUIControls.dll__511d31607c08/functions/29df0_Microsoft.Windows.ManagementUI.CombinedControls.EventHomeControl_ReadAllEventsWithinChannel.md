# Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::ReadAllEventsWithinChannel

- ea: `0x29df0`
- end: `0x2a2b3`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::ReadAllEventsWithinChannel`
- size: `1219`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x29a00`

## callees

- `0x1cd50`
- `0x1ce20`
- `0x29df0`
- `0x2ac50`
- `0x32e90`
- `0x33e70`
- `0x35250`
- `0x36630`
- `0x394a0`
- `0x4d110`
- `0x4d140`
- `0x4d1c0`
- `0x4d1d0`
- `0xa1df0`

## string_xrefs

- `0x2a2a7`: `User cancelled reading data.`
- `0x29df1`: `ReadAllEventsWithinChannel`
- `0x2a293`: `ReadAllEventsWithinChannel`
- `0x29e66`: `Event/System/TimeCreated/@SystemTime`
- `0x29e8e`: `Event/System/TimeCreated/@SystemTime`

## pseudocode

```c

```

## disassembly

```asm
0x29df0  ldarg.0
0x29df1  ldstr    aReadalleventsw// "ReadAllEventsWithinChannel"
0x29df6  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x29dfb  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x29e00  stloc.0
0x29e01  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x29e06  stloc.1
0x29e07  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x29e0c  stloc.2
0x29e0d  ldarg.2
0x29e0e  call     bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::IsSecurityChannel(string channelPath)
0x29e13  stloc.s  4
0x29e15  ldarg.1
0x29e16  ldarg.2
0x29e17  ldstr    asc_AB580// "*"
0x29e1c  ldc.i4   0x201
0x29e21  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::QueryLog(native int session, [hasfieldmarshal] string path, [hasfieldmarshal] string query, int32 flags)
0x29e26  stloc.0
0x29e27  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x29e2c  stloc.3
0x29e2d  ldloc.0
0x29e2e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x29e33  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x29e38  brfalse.s loc_29E46
0x29e3a  ldarg.0
0x29e3b  ldc.i4.1
0x29e3c  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::partialData
0x29e41  leave    loc_2A2B2
0x29e46  ldc.i4.4
0x29e47  newarr   [mscorlib]System.String
0x29e4c  dup
0x29e4d  ldc.i4.0
0x29e4e  ldstr    aEventSystemLev// "Event/System/Level"
0x29e53  stelem.ref
0x29e54  dup
0x29e55  ldc.i4.1
0x29e56  ldstr    aEventSystemEve// "Event/System/EventID"
0x29e5b  stelem.ref
0x29e5c  dup
0x29e5d  ldc.i4.2
0x29e5e  ldstr    aEventSystemPro// "Event/System/Provider/@Name"
0x29e63  stelem.ref
0x29e64  dup
0x29e65  ldc.i4.3
0x29e66  ldstr    aEventSystemTim// "Event/System/TimeCreated/@SystemTime"
0x29e6b  stelem.ref
0x29e6c  stloc.s  6
0x29e6e  ldc.i4.5
0x29e6f  newarr   [mscorlib]System.String
0x29e74  dup
0x29e75  ldc.i4.0
0x29e76  ldstr    aEventSystemLev// "Event/System/Level"
0x29e7b  stelem.ref
0x29e7c  dup
0x29e7d  ldc.i4.1
0x29e7e  ldstr    aEventSystemEve// "Event/System/EventID"
0x29e83  stelem.ref
0x29e84  dup
0x29e85  ldc.i4.2
0x29e86  ldstr    aEventSystemPro// "Event/System/Provider/@Name"
0x29e8b  stelem.ref
0x29e8c  dup
0x29e8d  ldc.i4.3
0x29e8e  ldstr    aEventSystemTim// "Event/System/TimeCreated/@SystemTime"
0x29e93  stelem.ref
0x29e94  dup
0x29e95  ldc.i4.4
0x29e96  ldstr    aEventSystemKey// "Event/System/Keywords"
0x29e9b  stelem.ref
0x29e9c  stloc.s  7
0x29e9e  ldloc.s  4
0x29ea0  brtrue.s loc_29EA8
0x29ea2  ldloc.s  6
0x29ea4  ldlen
0x29ea5  conv.i4
0x29ea6  br.s     loc_29EAC
0x29ea8  ldloc.s  7
0x29eaa  ldlen
0x29eab  conv.i4
0x29eac  stloc.s  8
0x29eae  ldloc.s  8
0x29eb0  ldloc.s  4
0x29eb2  brtrue.s loc_29EB8
0x29eb4  ldloc.s  6
0x29eb6  br.s     loc_29EBA
0x29eb8  ldloc.s  7
0x29eba  ldc.i4.0
0x29ebb  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CreateRenderContext(int32 countOfValues, string[] valuePaths, int32 flags)
0x29ec0  stloc.1
0x29ec1  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x29ec6  stloc.3
0x29ec7  ldloc.1
0x29ec8  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x29ecd  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x29ed2  brfalse.s loc_29EE0
0x29ed4  ldarg.0
0x29ed5  ldc.i4.1
0x29ed6  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::partialData
0x29edb  leave    loc_2A2B2
0x29ee0  ldloc.s  8
0x29ee2  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x29ee8  mul
0x29ee9  stloc.s  9
0x29eeb  ldloc.s  9
0x29eed  ldc.i4   0x200
0x29ef2  add
0x29ef3  stloc.s  9
0x29ef5  ldloc.s  9
0x29ef7  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x29efc  stloc.2
0x29efd  ldc.i4.0
0x29efe  stloc.s  0xA
0x29f00  ldc.i4.0
0x29f01  stloc.s  0xB
0x29f03  ldc.i4   0x100
0x29f08  newarr   [mscorlib]System.IntPtr
0x29f0d  stloc.s  0xC
0x29f0f  ldc.i4.0
0x29f10  stloc.s  0xD
0x29f12  ldc.i4.0
0x29f13  stloc.s  0xF
0x29f15  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x29f1a  stloc.s  0x10
0x29f1c  ldc.i4.0
0x29f1d  stloc.s  0x16
0x29f1f  br       loc_2A235
0x29f24  ldc.i4.1
0x29f25  stloc.s  0x16
0x29f27  ldc.i4.0
0x29f28  conv.i8
0x29f29  stloc.s  0x15
0x29f2b  ldc.i4.0
0x29f2c  stloc.s  0xD
0x29f2e  ldloc.0
0x29f2f  ldc.i4   0x100
0x29f34  ldloc.s  0xC
0x29f36  ldc.i4.m1
0x29f37  ldloca.s 0xD
0x29f39  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::GetNextBatchOfEvents(native int qryHandle, int32 numberOfEventsToFetch, native int[] eventHandles, int32 fetchDirection, int32& returnedEventsCount)
0x29f3e  stloc.3
0x29f3f  ldloc.3
0x29f40  brfalse.s loc_29F55
0x29f42  ldloc.3
0x29f43  ldc.i4   0x103
0x29f48  bne.un   loc_2A21F
0x29f4d  ldloc.s  0xD
0x29f4f  ldc.i4.0
0x29f50  ble      loc_2A21F
0x29f55  ldc.i4.0
0x29f56  stloc.s  0x17
0x29f58  br       loc_2A214
0x29f5d  ldloc.1
0x29f5e  ldloc.s  0xC
0x29f60  ldloc.s  0x17
0x29f62  ldelem.i
0x29f63  ldc.i4.0
0x29f64  ldloc.s  9
0x29f66  ldloc.2
0x29f67  ldloca.s 0xB
0x29f69  ldloca.s 0xA
0x29f6b  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::RenderEventToBuffer(native int context, native int eventHandle, int32 flags, int32 buffSize, native int buff, int32& buffUsed, int32& propCount)
0x29f70  stloc.s  5
0x29f72  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x29f77  stloc.3
0x29f78  ldloc.s  5
0x29f7a  brtrue.s loc_29FB7
0x29f7c  ldloc.s  0xB
0x29f7e  ldloc.s  9
0x29f80  ble.s    loc_29FB7
0x29f82  ldloc.3
0x29f83  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::IsInsufficientBuffer(int32 error)
0x29f88  brfalse.s loc_29FB7
0x29f8a  ldloc.s  0xB
0x29f8c  stloc.s  9
0x29f8e  ldloc.2
0x29f8f  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x29f94  ldloc.s  9
0x29f96  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x29f9b  stloc.2
0x29f9c  ldloc.1
0x29f9d  ldloc.s  0xC
0x29f9f  ldloc.s  0x17
0x29fa1  ldelem.i
0x29fa2  ldc.i4.0
0x29fa3  ldloc.s  9
0x29fa5  ldloc.2
0x29fa6  ldloca.s 0xB
0x29fa8  ldloca.s 0xA
0x29faa  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::RenderEventToBuffer(native int context, native int eventHandle, int32 flags, int32 buffSize, native int buff, int32& buffUsed, int32& propCount)
0x29faf  stloc.s  5
0x29fb1  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x29fb6  stloc.3
0x29fb7  nop
0x29fb8  ldloc.s  5
0x29fba  brtrue.s loc_29FC8
0x29fbc  ldarg.0
0x29fbd  ldc.i4.1
0x29fbe  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::partialData
0x29fc3  leave    loc_2A2B2
0x29fc8  leave.s  loc_29FE0
0x29fca  ldloc.s  0xC
0x29fcc  ldloc.s  0x17
0x29fce  ldelem.i
0x29fcf  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CloseHandle(native int eventHandle)
0x29fd4  stloc.s  5
0x29fd6  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x29fdb  stloc.3
0x29fdc  ldloc.s  5
0x29fde  pop
0x29fdf  endfinally
0x29fe0  ldloc.s  0xA
0x29fe2  ldloc.s  8
0x29fe4  beq.s    loc_29FF2
0x29fe6  ldarg.0
0x29fe7  ldc.i4.1
0x29fe8  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::partialData
0x29fed  leave    loc_2A2B2
0x29ff2  ldloc.2
0x29ff3  stloc.s  0x10
0x29ff5  ldloc.s  0x10
0x29ff7  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x29ffc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a001  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x2a006  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x2a00b  stloc.s  0xE
0x2a00d  ldloc.s  0xE
0x2a00f  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x2a014  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2a019  ldtoken  [mscorlib]System.Int32
0x2a01e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a023  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x2a028  castclass [mscorlib]System.IFormatProvider
0x2a02d  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x2a032  stloc.s  0x11
0x2a034  ldloc.s  0x11
0x2a036  brtrue.s loc_2A03B
0x2a038  ldc.i4.4
0x2a039  stloc.s  0x11
0x2a03b  ldloc.s  0x10
0x2a03d  ldloc.s  0xE
0x2a03f  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x2a044  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x2a049  call     native int Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AddOffset(native int ptr, int32 offset)
0x2a04e  stloc.s  0x10
0x2a050  ldloc.s  0x10
0x2a052  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x2a057  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a05c  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x2a061  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x2a066  stloc.s  0xE
0x2a068  ldloc.s  0xE
0x2a06a  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x2a06f  unbox.any [mscorlib]System.UInt16
0x2a074  stloc.s  0xF
0x2a076  ldloc.s  0x10
0x2a078  ldloc.s  0xE
0x2a07a  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x2a07f  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x2a084  call     native int Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AddOffset(native int ptr, int32 offset)
0x2a089  stloc.s  0x10
0x2a08b  ldloc.s  0x10
0x2a08d  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x2a092  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a097  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x2a09c  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x2a0a1  stloc.s  0xE
0x2a0a3  ldloc.s  0xE
0x2a0a5  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x2a0aa  castclass [mscorlib]System.String
0x2a0af  stloc.s  0x12
0x2a0b1  ldloc.s  0x10
0x2a0b3  ldloc.s  0xE
0x2a0b5  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x2a0ba  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x2a0bf  call     native int Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AddOffset(native int ptr, int32 offset)
0x2a0c4  stloc.s  0x10
0x2a0c6  ldloc.s  0x10
0x2a0c8  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x2a0cd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2a0d2  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x2a0d7  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x2a0dc  stloc.s  0xE
0x2a0de  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x2a0e3  stloc.s  0x13
0x2a0e5  ldloc.s  0xE
0x2a0e7  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x2a0ec  stloc.s  0x18
0x2a0ee  ldloc.s  0x18
0x2a0f0  brfalse.s loc_2A0FB
0x2a0f2  ldloc.s  0x18
0x2a0f4  unbox.any [mscorlib]System.DateTime
0x2a0f9  stloc.s  0x13
0x2a0fb  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x2a100  stloc.s  0x19
0x2a102  ldloca.s 0x19
0x2a104  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x2a109  ldloca.s 0x13
0x2a10b  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x2a110  sub
0x2a111  ldc.i8   0x58028E44000
  ... truncated ...
```
