# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::get_Mute

- ea: `0x8e0`
- end: `0x8ff`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::get_Mute`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x7a0`
- `0x8e0`
- `0xc10`

## pseudocode

```c

```

## disassembly

```asm
0x8e0  ldc.i4.0
0x8e1  stloc.0
0x8e2  ldarg.0
0x8e3  call     instance int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::InitializeAudioEndpoint()
0x8e8  pop
0x8e9  ldsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x8ee  brfalse.s loc_8FD
0x8f0  ldsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x8f5  ldloca.s 0
0x8f7  callvirt instance int32 IAudioEndpointVolume::GetMute(bool& mute)
0x8fc  pop
0x8fd  ldloc.0
0x8fe  ret
```
