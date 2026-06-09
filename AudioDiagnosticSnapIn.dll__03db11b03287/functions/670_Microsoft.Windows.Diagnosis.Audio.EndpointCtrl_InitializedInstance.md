# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::InitializedInstance

- ea: `0x670`
- end: `0x6be`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::InitializedInstance`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x160`
- `0x610`

## callees

- `0xa0`
- `0x670`

## pseudocode

```c

```

## disassembly

```asm
0x670  ldsfld   bool Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::comInitialized
0x675  brfalse.s loc_679
0x677  ldc.i4.0
0x678  ret
0x679  ldsflda  valuetype [mscorlib]System.Guid Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::CLSID_MMDeviceEnumerator
0x67e  ldnull
0x67f  ldc.i4.1
0x680  ldsflda  valuetype [mscorlib]System.Guid Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::IID_IUnknown
0x685  ldsflda  object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oEnumerator
0x68a  call     int32 Microsoft.Windows.Diagnosis.Audio.NativeMethods::CoCreateInstance(valuetype [mscorlib]System.Guid& guid, [hasfieldmarshal] object inner, unsigned int32 context, valuetype [mscorlib]System.Guid& id, [out] [hasfieldmarshal] object& pointer)
0x68f  stloc.0
0x690  ldloc.0
0x691  brfalse.s loc_695
0x693  ldloc.0
0x694  ret
0x695  ldc.i4.1
0x696  stsfld   bool Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::comInitialized
0x69b  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oEnumerator
0x6a0  brtrue.s loc_6A4
0x6a2  ldc.i4.1
0x6a3  ret
0x6a4  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oEnumerator
0x6a9  isinst   IMMDeviceEnumerator
0x6ae  stsfld   class IMMDeviceEnumerator Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceEnumerator
0x6b3  ldsfld   class IMMDeviceEnumerator Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceEnumerator
0x6b8  brtrue.s loc_6BC
0x6ba  ldc.i4.1
0x6bb  ret
0x6bc  ldloc.0
0x6bd  ret
```
