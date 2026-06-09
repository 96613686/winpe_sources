# Microsoft.BIServer.Configuration.WMI.WmiProvider::GetFlagsFromDescriptor

- ea: `0x4fa0`
- end: `0x4fc5`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::GetFlagsFromDescriptor`
- size: `37`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4fd0`
- `0x5170`
- `0x5c30`

## callees

- `0x4a30`
- `0x4a60`
- `0x4fa0`

## string_xrefs

- `0x4fb8`: `Could not get security description control`

## pseudocode

```c

```

## disassembly

```asm
0x4fa0  ldc.i4.0
0x4fa1  stloc.0
0x4fa2  ldarg.1
0x4fa3  ldarg.2
0x4fa4  ldloca.s 0
0x4fa6  call     void Microsoft.BIServer.Configuration.WMI.NativeMethods::ConvertStringSDtoSD(string stringSecurityDescriptor, [out] native int& securityDescriptorPtr, [out] int32& securityDescriptorSize)
0x4fab  ldarg.2
0x4fac  ldind.i
0x4fad  ldloca.s 2
0x4faf  ldloca.s 1
0x4fb1  call     bool Microsoft.BIServer.Configuration.WMI.NativeMethods::GetSecurityDescriptorControl([hasfieldmarshal] native int, unsigned int16& pSecurityDescriptor, [out] unsigned int32& pControl)
0x4fb6  brtrue.s loc_4FC3
0x4fb8  ldstr    aCouldNotGetSec// "Could not get security description cont"...
0x4fbd  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(string)
0x4fc2  throw
0x4fc3  ldloc.2
0x4fc4  ret
```
