# MissingConfigFile::.ctor

- ea: `0x78a0`
- end: `0x78a8`
- name: `MissingConfigFile::.ctor`
- size: `8`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1100`
- `0x1180`
- `0x3db0`

## callees

- `0x67b0`

## pseudocode

```c

```

## disassembly

```asm
0x78a0  ldarg.0
0x78a1  ldarg.1
0x78a2  call     instance void Microsoft.BIServer.Configuration.Exceptions.ConfigException::.ctor(string message)
0x78a7  ret
```
