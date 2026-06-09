# MS.Internal.Printing.Configuration.DevMode::get_ByteData

- ea: `0x18de0`
- end: `0x18ded`
- name: `MS.Internal.Printing.Configuration.DevMode::get_ByteData`
- size: `13`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0xd8a0`
- `0xdbe0`
- `0xdd00`
- `0x140f0`
- `0x19570`
- `0x19630`
- `0x19650`
- `0x19680`
- `0x196a0`
- `0x19870`
- `0x1a0d0`

## callees

- `0x19270`

## pseudocode

```c

```

## disassembly

```asm
0x18de0  ldarg.0
0x18de1  call     instance void MS.Internal.Printing.Configuration.DevMode::EnsureInitialized()
0x18de6  ldarg.0
0x18de7  ldfld    unsigned int8[] MS.Internal.Printing.Configuration.DevMode::_byteData
0x18dec  ret
```
