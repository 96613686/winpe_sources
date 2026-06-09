# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::set_Mute

- ea: `0x900`
- end: `0x927`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::set_Mute`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x7a0`
- `0x900`
- `0xc00`

## pseudocode

```c

```

## disassembly

```asm
0x900  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x905  stloc.0
0x906  ldarg.1
0x907  ldc.i4.0
0x908  cgt.un
0x90a  stloc.1
0x90b  ldarg.0
0x90c  call     instance int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::InitializeAudioEndpoint()
0x911  pop
0x912  ldsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x917  brfalse.s loc_926
0x919  ldsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x91e  ldloc.1
0x91f  ldloc.0
0x920  callvirt instance int32 IAudioEndpointVolume::SetMute(int32 mute, valuetype [mscorlib]System.Guid context)
0x925  pop
0x926  ret
```
