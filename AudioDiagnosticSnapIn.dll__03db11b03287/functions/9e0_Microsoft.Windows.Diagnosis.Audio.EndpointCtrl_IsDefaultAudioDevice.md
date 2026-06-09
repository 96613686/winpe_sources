# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::IsDefaultAudioDevice

- ea: `0x9e0`
- end: `0xa0b`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::IsDefaultAudioDevice`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x730`
- `0x9b0`
- `0x9e0`

## pseudocode

```c

```

## disassembly

```asm
0x9e0  ldarg.0
0x9e1  call     instance string Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::get_EndpointId()
0x9e6  ldarg.1
0x9e7  ldc.i4.0
0x9e8  ldarg.2
0x9e9  call     string Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetDefaultAudioDeviceId(string type, valuetype ERole role, string datatype)
0x9ee  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9f3  brfalse.s loc_A09
0x9f5  ldarg.0
0x9f6  call     instance string Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::get_EndpointId()
0x9fb  ldarg.1
0x9fc  ldc.i4.1
0x9fd  ldarg.2
0x9fe  call     string Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetDefaultAudioDeviceId(string type, valuetype ERole role, string datatype)
0xa03  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa08  ret
0xa09  ldc.i4.0
0xa0a  ret
```
