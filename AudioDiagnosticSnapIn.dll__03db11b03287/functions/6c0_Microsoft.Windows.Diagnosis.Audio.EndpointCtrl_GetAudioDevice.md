# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetAudioDevice

- ea: `0x6c0`
- end: `0x726`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetAudioDevice`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x610`

## callees

- `0x6c0`
- `0xd10`
- `0xd80`

## pseudocode

```c

```

## disassembly

```asm
0x6c0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x6c5  stloc.0
0x6c6  ldc.i4.0
0x6c7  stloc.1
0x6c8  ldsfld   class IMMDeviceEnumerator Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceEnumerator
0x6cd  brtrue.s loc_6D1
0x6cf  ldc.i4.1
0x6d0  ret
0x6d1  ldsfld   class IMMDeviceEnumerator Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceEnumerator
0x6d6  ldarg.1
0x6d7  ldloca.s 0
0x6d9  callvirt instance int32 IMMDeviceEnumerator::GetDevice(string id, native int& device)
0x6de  stloc.1
0x6df  ldloc.1
0x6e0  brfalse.s loc_6F9
0x6e2  ldstr    aCanTObtainImmd_0// "Can't obtain IMMDevice: "
0x6e7  ldloca.s 1
0x6e9  call     instance string [mscorlib]System.Int32::ToString()
0x6ee  call     string [mscorlib]System.String::Concat(string, string)
0x6f3  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(string)
0x6f8  throw
0x6f9  ldloc.0
0x6fa  call     object [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectForIUnknown(native int)
0x6ff  stsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oDevice
0x704  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oDevice
0x709  isinst   IMMDevice
0x70e  stsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x713  ldsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x718  ldarg.0
0x719  ldflda   int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::state
0x71e  callvirt instance int32 IMMDevice::GetState(int32& state)
0x723  pop
0x724  ldloc.1
0x725  ret
```
