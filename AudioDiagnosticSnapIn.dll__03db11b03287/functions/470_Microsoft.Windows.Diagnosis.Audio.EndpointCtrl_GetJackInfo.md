# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetJackInfo

- ea: `0x470`
- end: `0x5ed`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetJackInfo`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x160`

## callees

- `0x470`
- `0xce0`
- `0xdd0`
- `0xe90`
- `0xf70`
- `0xfb0`
- `0xfc0`

## pseudocode

```c

```

## disassembly

```asm
0x470  ldnull
0x471  stloc.0
0x472  ldnull
0x473  stloc.1
0x474  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x479  stloc.2
0x47a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x47f  stloc.3
0x480  ldc.i4.0
0x481  stloc.s  4
0x483  ldc.i4.0
0x484  stloc.s  5
0x486  ldc.i4.m1
0x487  stloc.s  6
0x489  ldarg.0
0x48a  brtrue.s loc_497
0x48c  ldstr    aNoDeviceIsSpec// "No device is specified"
0x491  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x496  throw
0x497  ldarg.0
0x498  ldsflda  valuetype [mscorlib]System.Guid Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::IID_IDeviceTopology
0x49d  ldc.i4.s 0x17
0x49f  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4a4  ldloca.s 2
0x4a6  callvirt instance int32 IMMDevice::Activate(valuetype [mscorlib]System.Guid& guid, unsigned int32 context, native int parameters, native int& pointer)
0x4ab  stloc.s  5
0x4ad  ldloc.s  5
0x4af  brtrue.s loc_4BE
0x4b1  ldloc.2
0x4b2  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4b7  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x4bc  brfalse.s loc_4C4
0x4be  ldsfld   int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::jackErrorInfo
0x4c3  ret
0x4c4  ldloc.2
0x4c5  call     object [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectForIUnknown(native int)
0x4ca  isinst   IDeviceTopology
0x4cf  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4d4  stloc.2
0x4d5  ldc.i4.0
0x4d6  ldloca.s 2
0x4d8  callvirt instance int32 IDeviceTopology::GetConnector(unsigned int32 nIndex, native int& ppConnector)
0x4dd  stloc.s  5
0x4df  ldloc.s  5
0x4e1  brtrue.s loc_4F0
0x4e3  ldloc.2
0x4e4  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4e9  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x4ee  brfalse.s loc_4F6
0x4f0  ldsfld   int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::jackErrorInfo
0x4f5  ret
0x4f6  ldloc.2
0x4f7  call     object [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectForIUnknown(native int)
0x4fc  isinst   IConnector
0x501  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x506  stloc.2
0x507  ldloca.s 2
0x509  callvirt instance int32 IConnector::GetConnectedTo(native int& ppConTo)
0x50e  stloc.s  5
0x510  ldloc.s  5
0x512  brtrue.s loc_521
0x514  ldloc.2
0x515  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x51a  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x51f  brfalse.s loc_527
0x521  ldsfld   int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::jackErrorInfo
0x526  ret
0x527  ldloc.2
0x528  call     object [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectForIUnknown(native int)
0x52d  pop
0x52e  ldloc.2
0x52f  ldsflda  valuetype [mscorlib]System.Guid Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::IID_IPart
0x534  ldloca.s 3
0x536  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::QueryInterface(native int, valuetype [mscorlib]System.Guid&, native int&)
0x53b  stloc.s  5
0x53d  ldloc.s  5
0x53f  brtrue.s loc_54E
0x541  ldloc.3
0x542  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x547  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x54c  brfalse.s loc_554
0x54e  ldsfld   int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::jackErrorInfo
0x553  ret
0x554  ldloc.3
0x555  call     object [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectForIUnknown(native int)
0x55a  isinst   IPart
0x55f  stloc.0
0x560  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x565  stloc.2
0x566  ldloc.0
0x567  ldc.i4.1
0x568  ldsflda  valuetype [mscorlib]System.Guid Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::IID_IKsJackDescription
0x56d  ldloca.s 2
0x56f  callvirt instance int32 IPart::Activate(int32 dwClsContext, valuetype [mscorlib]System.Guid& refiid, native int& ppvObject)
0x574  stloc.s  5
0x576  leave.s  loc_582
0x578  pop
0x579  ldsfld   int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::jackErrorInfo
0x57e  stloc.s  7
0x580  leave.s  loc_5EA
0x582  ldloc.s  5
0x584  brtrue.s loc_593
0x586  ldloc.2
0x587  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x58c  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x591  brfalse.s loc_599
0x593  ldsfld   int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::jackErrorInfo
0x598  ret
0x599  ldloc.2
0x59a  call     object [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectForIUnknown(native int)
0x59f  isinst   IKsJackDescription
0x5a4  stloc.1
0x5a5  ldloc.1
0x5a6  ldloca.s 4
0x5a8  callvirt instance int32 IKsJackDescription::GetJackCount(unsigned int32& pcJacks)
0x5ad  stloc.s  5
0x5af  ldc.i4.0
0x5b0  stloc.s  8
0x5b2  br.s     loc_5E1
0x5b4  ldloca.s 9
0x5b6  initobj  KSJACK_DESCRIPTION
0x5bc  ldloc.1
0x5bd  ldloc.s  8
0x5bf  ldloca.s 9
0x5c1  callvirt instance int32 IKsJackDescription::GetJackDescription(unsigned int32 nJack, [out] valuetype KSJACK_DESCRIPTION& pDescription)
0x5c6  stloc.s  5
0x5c8  ldloc.s  5
0x5ca  brfalse.s loc_5D2
0x5cc  ldsfld   int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::jackErrorInfo
0x5d1  ret
0x5d2  ldloc.s  9
0x5d4  ldfld    unsigned int32 KSJACK_DESCRIPTION::GeoLocation
0x5d9  stloc.s  6
0x5db  ldloc.s  8
0x5dd  ldc.i4.1
0x5de  add
0x5df  stloc.s  8
0x5e1  ldloc.s  8
0x5e3  ldloc.s  4
0x5e5  blt.un.s loc_5B4
0x5e7  ldloc.s  6
0x5e9  ret
0x5ea  ldloc.s  7
0x5ec  ret
```
