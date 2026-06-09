# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetAllDeviceByType

- ea: `0x160`
- end: `0x38c`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetAllDeviceByType`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0xaf0`

## callees

- `0xc0`
- `0x160`
- `0x390`
- `0x470`
- `0x5f0`
- `0x670`
- `0xca0`
- `0xcf0`
- `0xd00`
- `0xd10`
- `0xd30`
- `0xd40`
- `0xd60`
- `0x1030`
- `0x1050`

## pseudocode

```c

```

## disassembly

```asm
0x160  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x165  stloc.0
0x166  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x16b  stloc.1
0x16c  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x171  stloc.2
0x172  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.Diagnosis.Audio.EndpointList>::.ctor()
0x177  stloc.3
0x178  ldstr    asc_2064// ""
0x17d  stloc.s  4
0x17f  ldstr    asc_2064// ""
0x184  stloc.s  5
0x186  ldstr    asc_2064// ""
0x18b  stloc.s  6
0x18d  ldc.i4.0
0x18e  stloc.s  7
0x190  ldc.i4.0
0x191  stloc.s  8
0x193  call     int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::InitializedInstance()
0x198  stloc.s  8
0x19a  ldloc.s  8
0x19c  brtrue.s loc_1A5
0x19e  ldsfld   class IMMDeviceEnumerator Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceEnumerator
0x1a3  brtrue.s loc_1BC
0x1a5  ldstr    aCanTObtainImmd// "Can't obtain IMMDeviceEnumerator: "
0x1aa  ldloca.s 8
0x1ac  call     instance string [mscorlib]System.Int32::ToString()
0x1b1  call     string [mscorlib]System.String::Concat(string, string)
0x1b6  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(string)
0x1bb  throw
0x1bc  ldsfld   class IMMDeviceEnumerator Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceEnumerator
0x1c1  brtrue.s loc_1C5
0x1c3  ldnull
0x1c4  ret
0x1c5  ldsfld   class IMMDeviceEnumerator Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceEnumerator
0x1ca  ldarg.0
0x1cb  ldarg.1
0x1cc  call     valuetype EDataFlow Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetDataFlowByType(string type, string datatype)
0x1d1  ldc.i4.s 0xF
0x1d3  ldloca.s 0
0x1d5  callvirt instance int32 IMMDeviceEnumerator::EnumAudioEndpoints(valuetype EDataFlow dataflow, int32 mask, native int& devices)
0x1da  stloc.s  8
0x1dc  ldloc.s  8
0x1de  brfalse.s loc_1E2
0x1e0  ldnull
0x1e1  ret
0x1e2  ldloc.0
0x1e3  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1e8  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x1ed  brfalse.s loc_1F1
0x1ef  ldnull
0x1f0  ret
0x1f1  ldloc.0
0x1f2  call     object [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectForIUnknown(native int)
0x1f7  stsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oDevices
0x1fc  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oDevices
0x201  isinst   IMMDevices
0x206  stsfld   class IMMDevices Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceCollection
0x20b  ldc.i4.0
0x20c  stloc.s  9
0x20e  ldsfld   class IMMDevices Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceCollection
0x213  ldloca.s 9
0x215  callvirt instance int32 IMMDevices::GetCount(unsigned int32& pcDevices)
0x21a  stloc.s  8
0x21c  ldloc.s  8
0x21e  brfalse.s loc_222
0x220  ldnull
0x221  ret
0x222  ldloca.s 0xA
0x224  initobj  PROPVARIANT
0x22a  ldc.i4.0
0x22b  stloc.s  0xB
0x22d  br       loc_37C
0x232  ldsfld   class IMMDevices Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceCollection
0x237  ldloc.s  0xB
0x239  ldloca.s 1
0x23b  callvirt instance int32 IMMDevices::Item(unsigned int32 deviceId, native int& ppDevice)
0x240  stloc.s  8
0x242  ldloc.s  8
0x244  brfalse.s loc_248
0x246  ldnull
0x247  ret
0x248  ldloc.1
0x249  call     object [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectForIUnknown(native int)
0x24e  stsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oDevice
0x253  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oDevice
0x258  isinst   IMMDevice
0x25d  stsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x262  ldsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x267  ldloca.s 7
0x269  callvirt instance int32 IMMDevice::GetState(int32& state)
0x26e  stloc.s  8
0x270  ldloc.s  8
0x272  brtrue   loc_376
0x277  ldloc.s  7
0x279  ldc.i4.4
0x27a  and
0x27b  brtrue   loc_376
0x280  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x285  stloc.s  0xC
0x287  ldsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x28c  ldc.i4.0
0x28d  ldloca.s 0xC
0x28f  callvirt instance int32 IMMDevice::OpenPropertyStore(unsigned int32 access, native int& properties)
0x294  stloc.s  8
0x296  ldloc.s  8
0x298  brtrue   loc_376
0x29d  ldloc.s  0xC
0x29f  call     object [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectForIUnknown(native int)
0x2a4  stsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oProperty
0x2a9  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oProperty
0x2ae  isinst   IPropertyStore
0x2b3  stsfld   class IPropertyStore Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iProperty
0x2b8  ldsfld   class IPropertyStore Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iProperty
0x2bd  ldsflda  valuetype PropertyKey Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::PKEY_AudioEndpoint_FormFactor
0x2c2  ldloca.s 0xA
0x2c4  callvirt instance int32 IPropertyStore::GetValue(valuetype PropertyKey& key, valuetype PROPVARIANT& variant)
0x2c9  stloc.s  8
0x2cb  ldloc.s  8
0x2cd  brtrue   loc_376
0x2d2  ldloca.s 0xA
0x2d4  call     instance unsigned int32 PROPVARIANT::get_DeviceTypeValue()
0x2d9  conv.u8
0x2da  ldarg.0
0x2db  call     int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetDeviceTypeValue(string type)
0x2e0  conv.i8
0x2e1  bne.un   loc_376
0x2e6  ldsfld   class IPropertyStore Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iProperty
0x2eb  ldsflda  valuetype PropertyKey Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::PKEY_Device_DeviceDesc
0x2f0  ldloca.s 0xA
0x2f2  callvirt instance int32 IPropertyStore::GetValue(valuetype PropertyKey& key, valuetype PROPVARIANT& variant)
0x2f7  stloc.s  8
0x2f9  ldloc.s  8
0x2fb  brtrue.s loc_376
0x2fd  ldloca.s 0xA
0x2ff  call     instance string PROPVARIANT::get_DeviceName()
0x304  stloc.s  4
0x306  ldsfld   class IPropertyStore Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iProperty
0x30b  ldsflda  valuetype PropertyKey Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::PKEY_DeviceInterface_FriendlyName
0x310  ldloca.s 0xA
0x312  callvirt instance int32 IPropertyStore::GetValue(valuetype PropertyKey& key, valuetype PROPVARIANT& variant)
0x317  stloc.s  8
0x319  ldloc.s  8
0x31b  brtrue.s loc_376
0x31d  ldloca.s 0xA
0x31f  call     instance string PROPVARIANT::get_DeviceName()
0x324  stloc.s  5
0x326  ldsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x32b  ldloca.s 2
0x32d  callvirt instance int32 IMMDevice::GetId(native int& id)
0x332  pop
0x333  ldloc.2
0x334  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x339  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x33e  brtrue.s loc_376
0x340  ldc.i4.m1
0x341  stloc.s  0xD
0x343  ldsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x348  call     int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetJackInfo(class IMMDevice iDevice)
0x34d  stloc.s  0xD
0x34f  leave.s  loc_35B
0x351  pop
0x352  ldsfld   int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::jackErrorInfo
0x357  stloc.s  0xD
0x359  leave.s  loc_35B
0x35b  ldloc.2
0x35c  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAuto(native int)
0x361  stloc.s  6
0x363  ldloc.3
0x364  ldloc.s  4
0x366  ldloc.s  6
0x368  ldloc.s  5
0x36a  ldloc.s  0xD
0x36c  newobj   instance void Microsoft.Windows.Diagnosis.Audio.EndpointList::.ctor(string deviceDes, string deviceId, string adapterName, int32 jackInfo)
0x371  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.Diagnosis.Audio.EndpointList>::Add(var<u1>)
0x376  ldloc.s  0xB
0x378  ldc.i4.1
0x379  add
0x37a  stloc.s  0xB
0x37c  ldloc.s  0xB
0x37e  ldloc.s  9
0x380  blt.un   loc_232
0x385  ldloc.3
0x386  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.Diagnosis.Audio.EndpointList>::ToArray()
0x38b  ret
```
