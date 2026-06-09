# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::.cctor

- ea: `0xa10`
- end: `0xab0`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::.cctor`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1070`

## pseudocode

```c

```

## disassembly

```asm
0xa10  ldstr    aA45c254eDf1c4e// "A45C254E-DF1C-4EFD-8020-67D146A850E0"
0xa15  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa1a  ldc.i4.2
0xa1b  newobj   instance void PropertyKey::.ctor(valuetype [mscorlib]System.Guid initId, unsigned int32 initPid)
0xa20  stsfld   valuetype PropertyKey Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::PKEY_Device_DeviceDesc
0xa25  ldstr    a1da5d803D4924e// "1DA5D803-D492-4EDD-8C23-E0C0FFEE7F0E"
0xa2a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa2f  ldc.i4.0
0xa30  newobj   instance void PropertyKey::.ctor(valuetype [mscorlib]System.Guid initId, unsigned int32 initPid)
0xa35  stsfld   valuetype PropertyKey Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::PKEY_AudioEndpoint_FormFactor
0xa3a  ldstr    a026e516eB81441// "026e516e-b814-414b-83cd-856d6fef4822"
0xa3f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa44  ldc.i4.2
0xa45  newobj   instance void PropertyKey::.ctor(valuetype [mscorlib]System.Guid initId, unsigned int32 initPid)
0xa4a  stsfld   valuetype PropertyKey Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::PKEY_DeviceInterface_FriendlyName
0xa4f  ldstr    aBcde0395E52f46// "BCDE0395-E52F-467C-8E3D-C4579291692E"
0xa54  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa59  stsfld   valuetype [mscorlib]System.Guid Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::CLSID_MMDeviceEnumerator
0xa5e  ldstr    a00000000000000// "00000000-0000-0000-C000-000000000046"
0xa63  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa68  stsfld   valuetype [mscorlib]System.Guid Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::IID_IUnknown
0xa6d  ldstr    a5cdf2c82841e45// "5CDF2C82-841E-4546-9722-0CF74078229A"
0xa72  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa77  stsfld   valuetype [mscorlib]System.Guid Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::IID_IAudioEndpointVolume
0xa7c  ldstr    a2a07407e64974a// "2A07407E-6497-4A18-9787-32F79BD0D98F"
0xa81  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa86  stsfld   valuetype [mscorlib]System.Guid Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::IID_IDeviceTopology
0xa8b  ldstr    aAe2de0e45bca4f// "AE2DE0E4-5BCA-4F2D-AA46-5D13F8FDB3A9"
0xa90  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa95  stsfld   valuetype [mscorlib]System.Guid Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::IID_IPart
0xa9a  ldstr    a4509f7572d4646// "4509F757-2D46-4637-8E62-CE7DB944F57B"
0xa9f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xaa4  stsfld   valuetype [mscorlib]System.Guid Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::IID_IKsJackDescription
0xaa9  ldc.i4.0
0xaaa  stsfld   int32 Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::jackErrorInfo
0xaaf  ret
```
