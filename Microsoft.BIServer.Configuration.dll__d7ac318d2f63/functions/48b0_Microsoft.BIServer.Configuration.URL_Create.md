# Microsoft.BIServer.Configuration.URL::Create

- ea: `0x48b0`
- end: `0x48ba`
- name: `Microsoft.BIServer.Configuration.URL::Create`
- size: `10`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x48c0`

## callees

- `0x4860`

## pseudocode

```c

```

## disassembly

```asm
0x48b0  ldarg.0
0x48b1  ldnull
0x48b2  ldnull
0x48b3  ldnull
0x48b4  newobj   instance void Microsoft.BIServer.Configuration.URL::.ctor(string urlString, string accountName, string accountSecurityIdentifier, string accountSecurityDescriptor)
0x48b9  ret
```
