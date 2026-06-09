# Microsoft.Windows.Diagnosis.Audio.EndpointList::.ctor

- ea: `0xc0`
- end: `0xe4`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointList::.ctor`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x160`

## pseudocode

```c

```

## disassembly

```asm
0xc0  ldarg.0
0xc1  call     instance void [mscorlib]System.Object::.ctor()
0xc6  ldarg.0
0xc7  ldarg.1
0xc8  stfld    string Microsoft.Windows.Diagnosis.Audio.EndpointList::deviceDes
0xcd  ldarg.0
0xce  ldarg.2
0xcf  stfld    string Microsoft.Windows.Diagnosis.Audio.EndpointList::deviceId
0xd4  ldarg.0
0xd5  ldarg.s  4
0xd7  stfld    int32 Microsoft.Windows.Diagnosis.Audio.EndpointList::jackInfo
0xdc  ldarg.0
0xdd  ldarg.3
0xde  stfld    string Microsoft.Windows.Diagnosis.Audio.EndpointList::adapterName
0xe3  ret
```
