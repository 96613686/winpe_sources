# Microsoft.BIServer.Configuration.WMI.NativeMethods::ConvertStringSDtoSD

- ea: `0x4a30`
- end: `0x4a47`
- name: `Microsoft.BIServer.Configuration.WMI.NativeMethods::ConvertStringSDtoSD`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4fa0`
- `0x4fd0`

## callees

- `0x4a20`
- `0x4a30`

## pseudocode

```c

```

## disassembly

```asm
0x4a30  ldarg.0
0x4a31  ldc.i4.1
0x4a32  ldarg.1
0x4a33  ldarg.2
0x4a34  call     bool Microsoft.BIServer.Configuration.WMI.NativeMethods::ConvertStringSecurityDescriptorToSecurityDescriptor([in] string StringSecurityDescriptor, [in] unsigned int32 StringSDRevision, [out] native int& SecurityDescriptor, [out] int32& SecurityDescriptorSize)
0x4a39  brtrue.s loc_4A46
0x4a3b  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4a40  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x4a45  throw
0x4a46  ret
```
