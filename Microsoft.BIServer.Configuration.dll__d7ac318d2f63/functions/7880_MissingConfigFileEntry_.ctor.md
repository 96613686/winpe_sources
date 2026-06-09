# MissingConfigFileEntry::.ctor

- ea: `0x7880`
- end: `0x7888`
- name: `MissingConfigFileEntry::.ctor`
- size: `8`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1610`
- `0x1650`
- `0x1840`

## callees

- `0x67b0`

## pseudocode

```c

```

## disassembly

```asm
0x7880  ldarg.0
0x7881  ldarg.1
0x7882  call     instance void Microsoft.BIServer.Configuration.Exceptions.ConfigException::.ctor(string message)
0x7887  ret
```
