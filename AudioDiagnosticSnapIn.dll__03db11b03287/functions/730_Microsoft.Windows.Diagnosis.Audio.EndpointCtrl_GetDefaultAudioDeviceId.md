# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetDefaultAudioDeviceId

- ea: `0x730`
- end: `0x799`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetDefaultAudioDeviceId`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x9e0`

## callees

- `0x5f0`
- `0x730`
- `0xd00`
- `0xd70`

## pseudocode

```c

```

## disassembly

```asm
0x730  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x735  stloc.0
0x736  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x73b  stloc.1
0x73c  ldc.i4.0
0x73d  stloc.2
0x73e  ldsfld   class IMMDeviceEnumerator Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceEnumerator
0x743  brtrue.s loc_74B
0x745  ldstr    asc_2064// ""
0x74a  ret
0x74b  ldsfld   class IMMDeviceEnumerator Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDeviceEnumerator
0x750  ldarg.0
0x751  ldarg.2
0x752  call     valuetype EDataFlow Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetDataFlowByType(string type, string datatype)
0x757  ldarg.1
0x758  ldloca.s 0
0x75a  callvirt instance int32 IMMDeviceEnumerator::GetDefaultAudioEndpoint(valuetype EDataFlow dataflow, valuetype ERole role, native int& endpoint)
0x75f  stloc.2
0x760  ldloc.2
0x761  brfalse.s loc_77A
0x763  ldstr    aCanTObtainImmd_0// "Can't obtain IMMDevice: "
0x768  ldloca.s 2
0x76a  call     instance string [mscorlib]System.Int32::ToString()
0x76f  call     string [mscorlib]System.String::Concat(string, string)
0x774  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(string)
0x779  throw
0x77a  ldloc.0
0x77b  call     object [mscorlib]System.Runtime.InteropServices.Marshal::GetObjectForIUnknown(native int)
0x780  isinst   IMMDevice
0x785  stloc.3
0x786  ldloc.3
0x787  brfalse.s loc_792
0x789  ldloc.3
0x78a  ldloca.s 1
0x78c  callvirt instance int32 IMMDevice::GetId(native int& id)
0x791  pop
0x792  ldloc.1
0x793  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAuto(native int)
0x798  ret
```
