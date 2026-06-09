# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::.ctor

- ea: `0x610`
- end: `0x662`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::.ctor`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xaf0`

## callees

- `0x610`
- `0x670`
- `0x6c0`
- `0x7a0`

## pseudocode

```c

```

## disassembly

```asm
0x610  ldarg.0
0x611  call     instance void [mscorlib]System.Object::.ctor()
0x616  ldc.i4.0
0x617  stloc.0
0x618  call     int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::InitializedInstance()
0x61d  stloc.0
0x61e  ldloc.0
0x61f  brfalse.s loc_638
0x621  ldstr    aCanTObtainImmd// "Can't obtain IMMDeviceEnumerator: "
0x626  ldloca.s 0
0x628  call     instance string [mscorlib]System.Int32::ToString()
0x62d  call     string [mscorlib]System.String::Concat(string, string)
0x632  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(string)
0x637  throw
0x638  ldarg.0
0x639  ldarg.1
0x63a  call     instance int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetAudioDevice(string deviceId)
0x63f  stloc.0
0x640  ldloc.0
0x641  brfalse.s loc_65A
0x643  ldstr    aCanTObtainImmd_0// "Can't obtain IMMDevice: "
0x648  ldloca.s 0
0x64a  call     instance string [mscorlib]System.Int32::ToString()
0x64f  call     string [mscorlib]System.String::Concat(string, string)
0x654  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(string)
0x659  throw
0x65a  ldarg.0
0x65b  call     instance int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::InitializeAudioEndpoint()
0x660  pop
0x661  ret
```
