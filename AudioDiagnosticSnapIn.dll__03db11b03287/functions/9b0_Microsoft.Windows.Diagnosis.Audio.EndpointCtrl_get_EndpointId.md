# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::get_EndpointId

- ea: `0x9b0`
- end: `0x9d1`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::get_EndpointId`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x9e0`

## callees

- `0x9b0`
- `0xd00`

## pseudocode

```c

```

## disassembly

```asm
0x9b0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9b5  stloc.0
0x9b6  ldsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x9bb  brfalse.s loc_9CA
0x9bd  ldsfld   class IMMDevice Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::iDevice
0x9c2  ldloca.s 0
0x9c4  callvirt instance int32 IMMDevice::GetId(native int& id)
0x9c9  pop
0x9ca  ldloc.0
0x9cb  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAuto(native int)
0x9d0  ret
```
