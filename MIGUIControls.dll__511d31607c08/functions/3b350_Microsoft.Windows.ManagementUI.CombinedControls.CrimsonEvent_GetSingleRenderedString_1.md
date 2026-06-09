# Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetSingleRenderedString_1

- ea: `0x3b350`
- end: `0x3b706`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetSingleRenderedString_1`
- size: `950`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x3b310`
- `0x3b340`

## callees

- `0x12860`
- `0x12880`
- `0x12ed0`
- `0x13430`
- `0x13510`
- `0x32e90`
- `0x3af50`
- `0x3b0e0`
- `0x3b100`
- `0x3b350`
- `0x3ca40`
- `0x4d1e0`

## string_xrefs

- `0x3b536`: `EmptyTask`

## pseudocode

```c

```

## disassembly

```asm
0x3b350  ldsfld   string [mscorlib]System.String::Empty
0x3b355  stloc.0
0x3b356  ldc.i4.0
0x3b357  stloc.1
0x3b358  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::defaultMessageSize
0x3b35d  stloc.2
0x3b35e  ldloc.2
0x3b35f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x3b364  stloc.3
0x3b365  ldc.i4.0
0x3b366  stloc.s  4
0x3b368  ldarg.1
0x3b369  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b36e  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x3b373  brtrue.s loc_3B385
0x3b375  ldarg.0
0x3b376  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b37b  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x3b380  brfalse  loc_3B432
0x3b385  ldarg.1
0x3b386  ldarg.0
0x3b387  ldarg.2
0x3b388  ldc.i4.0
0x3b389  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b38e  ldarg.3
0x3b38f  ldloc.2
0x3b390  ldloc.3
0x3b391  ldloca.s 2
0x3b393  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::EventFormatMessage(native int publisherMetadata, native int eventHandle, int32 messageId, int32 valueCount, native int values, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventFormatMessageFlags flags, int32 bufferSize, [out] [hasfieldmarshal] class [mscorlib]System.Text.StringBuilder buffer, int32& bufferUsed)
0x3b398  stloc.s  5
0x3b39a  ldloc.s  5
0x3b39c  brtrue.s loc_3B3AA
0x3b39e  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3b3a3  stloc.1
0x3b3a4  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3b3a9  stloc.3
0x3b3aa  ldloc.s  5
0x3b3ac  brtrue.s loc_3B3F5
0x3b3ae  ldloc.2
0x3b3af  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::defaultMessageSize
0x3b3b4  ble.s    loc_3B3F5
0x3b3b6  ldloc.1
0x3b3b7  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::IsInsufficientBuffer(int32 error)
0x3b3bc  brfalse.s loc_3B3F5
0x3b3be  ldstr    aEvtformatmessa// "EvtFormatMessage failed because of insu"...
0x3b3c3  ldloc.1
0x3b3c4  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x3b3c9  ldloc.3
0x3b3ca  ldloc.2
0x3b3cb  callvirt instance void [mscorlib]System.Text.StringBuilder::set_Capacity(int32)
0x3b3d0  ldarg.1
0x3b3d1  ldarg.0
0x3b3d2  ldarg.2
0x3b3d3  ldc.i4.0
0x3b3d4  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b3d9  ldarg.3
0x3b3da  ldloc.2
0x3b3db  ldloc.3
0x3b3dc  ldloca.s 2
0x3b3de  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::EventFormatMessage(native int publisherMetadata, native int eventHandle, int32 messageId, int32 valueCount, native int values, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventFormatMessageFlags flags, int32 bufferSize, [out] [hasfieldmarshal] class [mscorlib]System.Text.StringBuilder buffer, int32& bufferUsed)
0x3b3e3  stloc.s  5
0x3b3e5  ldloc.s  5
0x3b3e7  brtrue.s loc_3B3F5
0x3b3e9  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3b3ee  stloc.1
0x3b3ef  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3b3f4  stloc.3
0x3b3f5  ldloc.s  5
0x3b3f7  brtrue.s loc_3B407
0x3b3f9  ldc.i4.1
0x3b3fa  stloc.s  4
0x3b3fc  ldloc.2
0x3b3fd  ldc.i4.0
0x3b3fe  ble.s    loc_3B407
0x3b400  ldloc.3
0x3b401  callvirt instance string [mscorlib]System.Object::ToString()
0x3b406  stloc.0
0x3b407  ldarg.3
0x3b408  ldc.i4.1
0x3b409  bne.un.s loc_3B423
0x3b40b  ldloc.1
0x3b40c  ldc.i4   0x3AB4
0x3b411  bne.un.s loc_3B423
0x3b413  ldstr    aNA// "N_A"
0x3b418  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3b41d  stloc.0
0x3b41e  ldc.i4.0
0x3b41f  stloc.s  4
0x3b421  br.s     loc_3B432
0x3b423  ldloc.s  5
0x3b425  brfalse.s loc_3B432
0x3b427  ldloc.2
0x3b428  ldc.i4.1
0x3b429  ble.s    loc_3B432
0x3b42b  ldloc.3
0x3b42c  callvirt instance string [mscorlib]System.Object::ToString()
0x3b431  stloc.0
0x3b432  ldloc.0
0x3b433  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3b438  brtrue.s loc_3B441
0x3b43a  ldloc.s  4
0x3b43c  brfalse  loc_3B704
0x3b441  ldarg.3
0x3b442  call     native int Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetRenderContext(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventFormatMessageFlags flag)
0x3b447  stloc.s  6
0x3b449  ldloc.s  6
0x3b44b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b450  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x3b455  brfalse  loc_3B58B
0x3b45a  ldarg.0
0x3b45b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b460  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x3b465  brfalse  loc_3B58B
0x3b46a  ldarg.0
0x3b46b  ldloc.s  6
0x3b46d  call     object Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetEventProperty(native int evtPtr, native int ctx)
0x3b472  stloc.s  7
0x3b474  ldloc.s  7
0x3b476  brfalse  loc_3B580
0x3b47b  ldc.i4.0
0x3b47c  conv.i8
0x3b47d  stloc.s  8
0x3b47f  ldloc.s  7
0x3b481  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b486  ldtoken  [mscorlib]System.UInt64
0x3b48b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3b490  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x3b495  castclass [mscorlib]System.IFormatProvider
0x3b49a  call     unsigned int64 [mscorlib]System.Convert::ToUInt64(object, class [mscorlib]System.IFormatProvider)
0x3b49f  stloc.s  8
0x3b4a1  leave.s  loc_3B4D1
0x3b4a3  pop
0x3b4a4  ldsfld   string [mscorlib]System.String::Empty
0x3b4a9  stloc.0
0x3b4aa  leave.s  loc_3B4D1
0x3b4ac  pop
0x3b4ad  ldsfld   string [mscorlib]System.String::Empty
0x3b4b2  stloc.0
0x3b4b3  ldstr    aNumberReturned// "Number returned is bigger than a ULONG "...
0x3b4b8  ldarga.s 3
0x3b4ba  constrained. Microsoft.Windows.ManagementUI.CombinedControls.EventFormatMessageFlags
0x3b4c0  callvirt instance string [mscorlib]System.Object::ToString()
0x3b4c5  call     string [mscorlib]System.String::Concat(string, string)
0x3b4ca  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x3b4cf  leave.s  loc_3B4D1
0x3b4d1  ldarg.3
0x3b4d2  ldc.i4.5
0x3b4d3  bne.un.s loc_3B52E
0x3b4d5  ldc.i8   0xFFFFFFFFFFFFFF
0x3b4de  ldloc.s  8
0x3b4e0  and
0x3b4e1  stloc.s  8
0x3b4e3  ldloc.s  8
0x3b4e5  ldc.i4.0
0x3b4e6  conv.i8
0x3b4e7  ble.un.s loc_3B523
0x3b4e9  ldnull
0x3b4ea  ldstr    a0_0// "({0})"
0x3b4ef  ldc.i4.1
0x3b4f0  newarr   [mscorlib]System.Object
0x3b4f5  dup
0x3b4f6  ldc.i4.0
0x3b4f7  ldloca.s 8
0x3b4f9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b4fe  ldtoken  [mscorlib]System.UInt32
0x3b503  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3b508  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x3b50d  castclass [mscorlib]System.IFormatProvider
0x3b512  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x3b517  stelem.ref
0x3b518  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3b51d  stloc.0
0x3b51e  br       loc_3B704
0x3b523  ldsfld   string [mscorlib]System.String::Empty
0x3b528  stloc.0
0x3b529  br       loc_3B704
0x3b52e  ldarg.3
0x3b52f  ldc.i4.3
0x3b530  bne.un.s loc_3B546
0x3b532  ldloc.s  8
0x3b534  brtrue.s loc_3B546
0x3b536  ldstr    aEmptytask// "EmptyTask"
0x3b53b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3b540  stloc.0
0x3b541  br       loc_3B704
0x3b546  ldnull
0x3b547  ldstr    a0_0// "({0})"
0x3b54c  ldc.i4.1
0x3b54d  newarr   [mscorlib]System.Object
0x3b552  dup
0x3b553  ldc.i4.0
0x3b554  ldloca.s 8
0x3b556  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b55b  ldtoken  [mscorlib]System.UInt32
0x3b560  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3b565  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x3b56a  castclass [mscorlib]System.IFormatProvider
0x3b56f  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x3b574  stelem.ref
0x3b575  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3b57a  stloc.0
0x3b57b  br       loc_3B704
0x3b580  ldsfld   string [mscorlib]System.String::Empty
0x3b585  stloc.0
0x3b586  br       loc_3B704
0x3b58b  ldarg.3
0x3b58c  ldc.i4.1
0x3b58d  bne.un   loc_3B704
0x3b592  ldsfld   string [mscorlib]System.String::Empty
0x3b597  stloc.s  9
0x3b599  ldloc.1
0x3b59a  brfalse.s loc_3B5A9
0x3b59c  ldloc.1
0x3b59d  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x3b5a2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3b5a7  stloc.s  9
0x3b5a9  ldloc.3
0x3b5aa  callvirt instance string [mscorlib]System.Object::ToString()
0x3b5af  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3b5b4  ldc.i4.0
0x3b5b5  ceq
0x3b5b7  ldloc.s  4
0x3b5b9  and
0x3b5ba  brfalse.s loc_3B626
0x3b5bc  ldloc.s  9
0x3b5be  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3b5c3  brtrue.s loc_3B61A
0x3b5c5  ldloc.3
0x3b5c6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x3b5cb  pop
0x3b5cc  ldloc.3
0x3b5cd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x3b5d2  pop
0x3b5d3  ldloc.1
0x3b5d4  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x3b5d9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3b5de  stloc.s  9
0x3b5e0  ldloc.3
0x3b5e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b5e6  ldtoken  [mscorlib]System.String
0x3b5eb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3b5f0  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x3b5f5  castclass [mscorlib]System.IFormatProvider
0x3b5fa  ldstr    aMessagerenderi// "MessageRenderingError"
0x3b5ff  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3b604  ldc.i4.1
0x3b605  newarr   [mscorlib]System.Object
0x3b60a  dup
0x3b60b  ldc.i4.0
0x3b60c  ldloc.s  9
0x3b60e  stelem.ref
0x3b60f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3b614  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3b619  pop
0x3b61a  ldloc.3
0x3b61b  callvirt instance string [mscorlib]System.Object::ToString()
0x3b620  stloc.0
0x3b621  br       loc_3B704
0x3b626  ldc.i4.2
0x3b627  newarr   [mscorlib]System.String
0x3b62c  dup
0x3b62d  ldc.i4.0
0x3b62e  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::SourcePath
0x3b633  stelem.ref
0x3b634  dup
0x3b635  ldc.i4.1
0x3b636  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::EventIdPath
0x3b63b  stelem.ref
0x3b63c  call     class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetRenderContext(string[] paths)
0x3b641  stloc.s  0xA
0x3b643  ldarg.0
0x3b644  ldloc.s  0xA
0x3b646  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x3b64b  ldc.i4.2
0x3b64c  call     object[] Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetEventProperties(native int evtPtr, native int ctx, int32 cProps)
0x3b651  stloc.s  0xB
0x3b653  ldloc.s  0xB
0x3b655  brfalse  loc_3B6F7
0x3b65a  ldloc.s  0xB
0x3b65c  ldc.i4.0
0x3b65d  ldelem.ref
0x3b65e  castclass [mscorlib]System.String
0x3b663  stloc.s  0xC
0x3b665  ldloc.s  0xB
0x3b667  ldc.i4.1
0x3b668  ldelem.ref
0x3b669  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b66e  ldtoken  [mscorlib]System.Int32
0x3b673  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3b678  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x3b67d  castclass [mscorlib]System.IFormatProvider
0x3b682  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x3b687  stloc.s  0xD
0x3b689  ldloc.1
0x3b68a  brfalse.s loc_3B699
0x3b68c  ldloc.1
0x3b68d  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x3b692  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3b697  stloc.s  9
0x3b699  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
  ... truncated ...
```
