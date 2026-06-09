# Microsoft.BIServer.Configuration.URL::Create_1

- ea: `0x48f0`
- end: `0x48fa`
- name: `Microsoft.BIServer.Configuration.URL::Create_1`
- size: `10`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6fc0`

## callees

- `0x4860`

## pseudocode

```c

```

## disassembly

```asm
0x48f0  ldarg.0
0x48f1  ldarg.1
0x48f2  ldarg.2
0x48f3  ldnull
0x48f4  newobj   instance void Microsoft.BIServer.Configuration.URL::.ctor(string urlString, string accountName, string accountSecurityIdentifier, string accountSecurityDescriptor)
0x48f9  ret
```
