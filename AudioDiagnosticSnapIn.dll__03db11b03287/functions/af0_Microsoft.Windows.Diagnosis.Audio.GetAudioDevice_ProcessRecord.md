# Microsoft.Windows.Diagnosis.Audio.GetAudioDevice::ProcessRecord

- ea: `0xaf0`
- end: `0xb2b`
- name: `Microsoft.Windows.Diagnosis.Audio.GetAudioDevice::ProcessRecord`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x160`
- `0x610`
- `0xaf0`

## pseudocode

```c

```

## disassembly

```asm
0xaf0  ldarg.0
0xaf1  ldfld    string Microsoft.Windows.Diagnosis.Audio.GetAudioDevice::typeName
0xaf6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xafb  brtrue.s loc_B17
0xafd  ldarg.0
0xafe  ldfld    string Microsoft.Windows.Diagnosis.Audio.GetAudioDevice::typeName
0xb03  ldarg.0
0xb04  ldfld    string Microsoft.Windows.Diagnosis.Audio.GetAudioDevice::dataType
0xb09  call     class Microsoft.Windows.Diagnosis.Audio.EndpointList[] Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetAllDeviceByType(string type, string datatype)
0xb0e  stloc.0
0xb0f  ldarg.0
0xb10  ldloc.0
0xb11  call     instance void [System.Management.Automation]System.Management.Automation.Cmdlet::WriteObject(object)
0xb16  ret
0xb17  ldarg.0
0xb18  ldfld    string Microsoft.Windows.Diagnosis.Audio.GetAudioDevice::id
0xb1d  newobj   instance void Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::.ctor(string deviceId)
0xb22  stloc.1
0xb23  ldarg.0
0xb24  ldloc.1
0xb25  call     instance void [System.Management.Automation]System.Management.Automation.Cmdlet::WriteObject(object)
0xb2a  ret
```
