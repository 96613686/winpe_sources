# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::set_MasterVolume

- ea: `0x970`
- end: `0x99b`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::set_MasterVolume`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x7a0`
- `0x970`
- `0xb90`

## pseudocode

```c

```

## disassembly

```asm
0x970  ldarg.1
0x971  conv.r4
0x972  ldc.r4   100.0
0x977  div
0x978  stloc.0
0x979  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x97e  stloc.1
0x97f  ldarg.0
0x980  call     instance int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::InitializeAudioEndpoint()
0x985  pop
0x986  ldsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x98b  brfalse.s loc_99A
0x98d  ldsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x992  ldloc.0
0x993  ldloc.1
0x994  callvirt instance int32 IAudioEndpointVolume::SetMasterVolumeLevelScalar(float32 level, valuetype [mscorlib]System.Guid context)
0x999  pop
0x99a  ret
```
