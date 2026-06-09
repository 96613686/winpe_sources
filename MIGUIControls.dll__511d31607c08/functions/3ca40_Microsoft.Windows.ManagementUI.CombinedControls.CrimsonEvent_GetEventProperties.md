# Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetEventProperties

- ea: `0x3ca40`
- end: `0x3cbfb`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetEventProperties`
- size: `443`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3b0e0`
- `0x3b350`
- `0x3d6f0`
- `0x3d790`
- `0x3dc50`
- `0x3dd10`

## callees

- `0x12ed0`
- `0x13510`
- `0x32e90`
- `0x33e70`
- `0x35250`
- `0x3ca40`
- `0x4d1d0`

## string_xrefs

- `0x3cbca`: `EventXmlGenericError`

## pseudocode

```c

```

## disassembly

```asm
0x3ca40  ldc.i4.0
0x3ca41  stloc.0
0x3ca42  ldc.i4.0
0x3ca43  stloc.1
0x3ca44  ldarg.0
0x3ca45  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3ca4a  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x3ca4f  brfalse  loc_3CBF9
0x3ca54  ldarg.2
0x3ca55  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x3ca5b  ldc.i4   0x80
0x3ca60  add
0x3ca61  mul
0x3ca62  stloc.2
0x3ca63  ldc.i4.0
0x3ca64  stloc.3
0x3ca65  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3ca6a  stloc.s  4
0x3ca6c  ldloc.2
0x3ca6d  stloc.s  5
0x3ca6f  ldc.i4.0
0x3ca70  stloc.s  6
0x3ca72  ldarg.1
0x3ca73  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3ca78  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x3ca7d  brfalse.s loc_3CA94
0x3ca7f  ldc.i4.1
0x3ca80  stloc.0
0x3ca81  ldc.i4.1
0x3ca82  stloc.s  6
0x3ca84  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x3ca8a  ldc.i4   0x5DC
0x3ca8f  add
0x3ca90  stloc.2
0x3ca91  ldloc.2
0x3ca92  stloc.s  5
0x3ca94  ldloc.2
0x3ca95  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x3ca9a  stloc.s  4
0x3ca9c  ldarg.1
0x3ca9d  ldarg.0
0x3ca9e  ldloc.s  6
0x3caa0  ldloc.2
0x3caa1  ldloc.s  4
0x3caa3  ldloca.s 2
0x3caa5  ldloca.s 3
0x3caa7  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::RenderEventToBuffer(native int context, native int eventHandle, int32 flags, int32 buffSize, native int buff, int32& buffUsed, int32& propCount)
0x3caac  stloc.s  7
0x3caae  ldloc.s  7
0x3cab0  brtrue.s loc_3CB18
0x3cab2  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3cab7  stloc.1
0x3cab8  ldloc.2
0x3cab9  ldloc.s  5
0x3cabb  ble.s    loc_3CB09
0x3cabd  ldloc.1
0x3cabe  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::IsInsufficientBuffer(int32 error)
0x3cac3  brfalse.s loc_3CB09
0x3cac5  ldstr    aRendereventtob// "RenderEventToBuffer failed because of i"...
0x3caca  ldloc.1
0x3cacb  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x3cad0  ldloc.s  4
0x3cad2  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x3cad7  ldloc.2
0x3cad8  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x3cadd  stloc.s  4
0x3cadf  ldloc.s  4
0x3cae1  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3cae6  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x3caeb  brfalse.s loc_3CB09
0x3caed  ldarg.1
0x3caee  ldarg.0
0x3caef  ldloc.s  6
0x3caf1  ldloc.2
0x3caf2  ldloc.s  4
0x3caf4  ldloca.s 2
0x3caf6  ldloca.s 3
0x3caf8  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::RenderEventToBuffer(native int context, native int eventHandle, int32 flags, int32 buffSize, native int buff, int32& buffUsed, int32& propCount)
0x3cafd  stloc.s  7
0x3caff  ldloc.s  7
0x3cb01  brtrue.s loc_3CB09
0x3cb03  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3cb08  stloc.1
0x3cb09  ldloc.s  7
0x3cb0b  brtrue.s loc_3CB18
0x3cb0d  ldstr    aErrorInRendere// "Error in RenderEvent"
0x3cb12  ldloc.1
0x3cb13  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x3cb18  ldloc.s  7
0x3cb1a  brfalse  loc_3CBF2
0x3cb1f  ldloc.s  4
0x3cb21  stloc.s  8
0x3cb23  ldloc.0
0x3cb24  brtrue.s loc_3CB81
0x3cb26  ldarg.2
0x3cb27  newarr   [mscorlib]System.Object
0x3cb2c  stloc.s  9
0x3cb2e  ldc.i4.0
0x3cb2f  stloc.s  0xB
0x3cb31  br.s     loc_3CB72
0x3cb33  ldloc.s  8
0x3cb35  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x3cb3a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cb3f  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x3cb44  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x3cb49  stloc.s  0xA
0x3cb4b  ldloc.s  9
0x3cb4d  ldloc.s  0xB
0x3cb4f  ldloc.s  0xA
0x3cb51  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x3cb56  stelem.ref
0x3cb57  ldloc.s  8
0x3cb59  ldloc.s  0xA
0x3cb5b  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x3cb60  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x3cb65  call     native int Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::AddOffset(native int ptr, int32 offset)
0x3cb6a  stloc.s  8
0x3cb6c  ldloc.s  0xB
0x3cb6e  ldc.i4.1
0x3cb6f  add
0x3cb70  stloc.s  0xB
0x3cb72  ldloc.s  0xB
0x3cb74  ldarg.2
0x3cb75  blt.s    loc_3CB33
0x3cb77  ldloc.s  4
0x3cb79  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x3cb7e  ldloc.s  9
0x3cb80  ret
0x3cb81  ldloc.s  4
0x3cb83  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAuto(native int)
0x3cb88  stloc.s  0xC
0x3cb8a  ldloc.s  4
0x3cb8c  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x3cb91  ldloc.s  0xC
0x3cb93  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3cb98  brfalse.s loc_3CBE6
0x3cb9a  ldsfld   string [mscorlib]System.String::Empty
0x3cb9f  stloc.s  0xD
0x3cba1  ldloc.1
0x3cba2  brfalse.s loc_3CBB1
0x3cba4  ldloc.1
0x3cba5  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x3cbaa  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3cbaf  stloc.s  0xD
0x3cbb1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3cbb6  ldtoken  [mscorlib]System.String
0x3cbbb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3cbc0  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x3cbc5  castclass [mscorlib]System.IFormatProvider
0x3cbca  ldstr    aEventxmlgeneri// "EventXmlGenericError"
0x3cbcf  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3cbd4  ldc.i4.1
0x3cbd5  newarr   [mscorlib]System.Object
0x3cbda  dup
0x3cbdb  ldc.i4.0
0x3cbdc  ldloc.s  0xD
0x3cbde  stelem.ref
0x3cbdf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3cbe4  stloc.s  0xC
0x3cbe6  ldc.i4.1
0x3cbe7  newarr   [mscorlib]System.Object
0x3cbec  dup
0x3cbed  ldc.i4.0
0x3cbee  ldloc.s  0xC
0x3cbf0  stelem.ref
0x3cbf1  ret
0x3cbf2  ldloc.s  4
0x3cbf4  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x3cbf9  ldnull
0x3cbfa  ret
```
