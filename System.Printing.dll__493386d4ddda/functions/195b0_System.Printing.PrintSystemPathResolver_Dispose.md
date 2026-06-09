# System.Printing.PrintSystemPathResolver::Dispose

- ea: `0x195b0`
- end: `0x195c2`
- name: `System.Printing.PrintSystemPathResolver::Dispose`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x195d0`

## callees

- `0x19560`
- `0x195b0`

## pseudocode

```c

```

## disassembly

```asm
0x195b0  ldarg.1
0x195b1  brfalse.s loc_195BB
0x195b3  ldarg.0
0x195b4  call     instance void System.Printing.PrintSystemPathResolver::~PrintSystemPathResolver()
0x195b9  br.s     loc_195C1
0x195bb  ldarg.0
0x195bc  call     instance void [mscorlib]System.Object::Finalize()
0x195c1  ret
```
