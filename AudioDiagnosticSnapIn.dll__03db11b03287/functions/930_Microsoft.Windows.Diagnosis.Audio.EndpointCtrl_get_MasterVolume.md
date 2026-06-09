# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::get_MasterVolume

- ea: `0x930`
- end: `0x965`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::get_MasterVolume`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x7a0`
- `0x930`
- `0xbb0`

## pseudocode

```c

```

## disassembly

```asm
0x930  ldc.r4   0.0
0x935  stloc.0
0x936  ldarg.0
0x937  call     instance int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::InitializeAudioEndpoint()
0x93c  pop
0x93d  ldsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x942  brfalse.s loc_958
0x944  ldsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x949  ldloca.s 0
0x94b  callvirt instance int32 IAudioEndpointVolume::GetMasterVolumeLevelScalar(float32& level)
0x950  brfalse.s loc_958
0x952  ldc.r4   0.0
0x957  stloc.0
0x958  ldloc.0
0x959  ldc.r4   100.0
0x95e  mul
0x95f  call     int32 [mscorlib]System.Convert::ToInt32(float32)
0x964  ret
```
