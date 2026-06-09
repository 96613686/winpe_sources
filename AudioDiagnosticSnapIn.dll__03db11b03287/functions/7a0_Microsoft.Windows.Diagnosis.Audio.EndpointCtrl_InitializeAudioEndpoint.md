# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::InitializeAudioEndpoint

- ea: `0x7a0`
- end: `0x80c`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::InitializeAudioEndpoint`
- size: `108`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x610`
- `0x8e0`
- `0x900`
- `0x930`
- `0x970`

## callees

- `0x7a0`
- `0xce0`

## pseudocode

```c

```

## disassembly

```asm
0x7a0  ldsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x7a5  brtrue.s loc_7A9
0x7a7  ldc.i4.1
0x7a8  ret
0x7a9  ldsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x7ae  brfalse.s loc_7B2
0x7b0  ldc.i4.0
0x7b1  ret
0x7b2  ldc.i4.s 0x17
0x7b4  stloc.0
0x7b5  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x7ba  stloc.1
0x7bb  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x7c0  stloc.2
0x7c1  ldc.i4.0
0x7c2  stloc.3
0x7c3  ldc.i4.1
0x7c4  ldarg.0
0x7c5  ldfld    int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::state
0x7ca  ldc.i4.1
0x7cb  and
0x7cc  bne.un.s loc_80A
0x7ce  ldsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x7d3  ldsflda  valuetype [mscorlib]System.Guid Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::IID_IAudioEndpointVolume
0x7d8  ldloc.0
0x7d9  ldloc.1
0x7da  ldloca.s 2
0x7dc  callvirt instance int32 IMMDevice::Activate(valuetype [mscorlib]System.Guid& guid, unsigned int32 context, native int parameters, native int& pointer)
0x7e1  stloc.3
0x7e2  ldloc.3
0x7e3  brfalse.s loc_7E7
0x7e5  ldloc.3
0x7e6  ret
0x7e7  ldloc.2
0x7e8  call     object [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectForIUnknown(native int)
0x7ed  stsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oEndPoint
0x7f2  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oEndPoint
0x7f7  isinst   IAudioEndpointVolume
0x7fc  stsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x801  ldsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x806  brtrue.s loc_80A
0x808  ldc.i4.1
0x809  ret
0x80a  ldloc.3
0x80b  ret
```
