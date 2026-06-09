# Microsoft.BIServer.Configuration.RegistryStoreMemory::GetKey

- ea: `0x2870`
- end: `0x287d`
- name: `Microsoft.BIServer.Configuration.RegistryStoreMemory::GetKey`
- size: `13`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x28f0`
- `0x2930`
- `0x2990`

## pseudocode

```c

```

## disassembly

```asm
0x2870  ldarg.1
0x2871  ldstr    asc_94A2// "$"
0x2876  ldarg.2
0x2877  call     string [mscorlib]System.String::Concat(string, string, string)
0x287c  ret
```
