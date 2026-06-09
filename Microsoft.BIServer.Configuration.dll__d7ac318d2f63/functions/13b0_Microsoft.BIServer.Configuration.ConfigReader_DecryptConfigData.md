# Microsoft.BIServer.Configuration.ConfigReader::DecryptConfigData

- ea: `0x13b0`
- end: `0x13d5`
- name: `Microsoft.BIServer.Configuration.ConfigReader::DecryptConfigData`
- size: `37`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf40`
- `0xf80`
- `0xfc0`
- `0x1bb0`

## callees

- `0x13b0`

## string_xrefs

- `0x13c1`: `FailedToDecryptConfigInformation: `

## pseudocode

```c

```

## disassembly

```asm
0x13b0  ldnull
0x13b1  stloc.0
0x13b2  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.MachineKeyCrypto::get_Instance()
0x13b7  ldarg.1
0x13b8  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Cryptography.Crypto::DecryptToString(string)
0x13bd  stloc.0
0x13be  leave.s  loc_13D3
0x13c0  stloc.1
0x13c1  ldstr    aFailedtodecryp// "FailedToDecryptConfigInformation: "
0x13c6  ldarg.2
0x13c7  call     string [mscorlib]System.String::Concat(string, string)
0x13cc  ldloc.1
0x13cd  newobj   instance void [mscorlib]System.Exception::.ctor(string, class [mscorlib]System.Exception)
0x13d2  throw
0x13d3  ldloc.0
0x13d4  ret
```
