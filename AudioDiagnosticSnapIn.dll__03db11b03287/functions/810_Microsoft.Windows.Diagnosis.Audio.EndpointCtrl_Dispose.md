# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::Dispose

- ea: `0x810`
- end: `0x8d1`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::Dispose`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x810`

## pseudocode

```c

```

## disassembly

```asm
0x810  ldsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x815  brfalse.s loc_828
0x817  ldsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x81c  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x821  pop
0x822  ldnull
0x823  stsfld   class IAudioEndpointVolume Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iAudioEndpoint
0x828  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oEndPoint
0x82d  brfalse.s loc_840
0x82f  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oEndPoint
0x834  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x839  pop
0x83a  ldnull
0x83b  stsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oEndPoint
0x840  ldsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x845  brfalse.s loc_858
0x847  ldsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x84c  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x851  pop
0x852  ldnull
0x853  stsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x858  ldsfld   class IMMDevices Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceCollection
0x85d  brfalse.s loc_870
0x85f  ldsfld   class IMMDevices Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceCollection
0x864  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x869  pop
0x86a  ldnull
0x86b  stsfld   class IMMDevices Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceCollection
0x870  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oDevice
0x875  brfalse.s loc_888
0x877  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oDevice
0x87c  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x881  pop
0x882  ldnull
0x883  stsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oDevice
0x888  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oDevices
0x88d  brfalse.s loc_8A0
0x88f  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oDevices
0x894  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x899  pop
0x89a  ldnull
0x89b  stsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oDevices
0x8a0  ldsfld   class IMMDeviceEnumerator Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceEnumerator
0x8a5  brfalse.s loc_8B8
0x8a7  ldsfld   class IMMDeviceEnumerator Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceEnumerator
0x8ac  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x8b1  pop
0x8b2  ldnull
0x8b3  stsfld   class IMMDeviceEnumerator Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceEnumerator
0x8b8  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oEnumerator
0x8bd  brfalse.s loc_8D0
0x8bf  ldsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oEnumerator
0x8c4  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x8c9  pop
0x8ca  ldnull
0x8cb  stsfld   object Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::oEnumerator
0x8d0  ret
```
