# Microsoft.BIServer.Configuration.WMI.WmiProvider::VerifyFullPath

- ea: `0x5560`
- end: `0x5574`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::VerifyFullPath`
- size: `20`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4f40`
- `0x4f50`

## callees

- `0x5560`

## string_xrefs

- `0x5568`: `[{0}] is not a full path`

## pseudocode

```c

```

## disassembly

```asm
0x5560  ldarg.1
0x5561  call     bool [mscorlib]System.IO.Path::IsPathRooted(string)
0x5566  brtrue.s loc_5573
0x5568  ldstr    a0IsNotAFullPat// "[{0}] is not a full path"
0x556d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x5572  throw
0x5573  ret
```
