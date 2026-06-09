# System.Printing.PrintSystemUNCPathResolver::Dispose

- ea: `0x19b60`
- end: `0x19b72`
- name: `System.Printing.PrintSystemUNCPathResolver::Dispose`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x19b80`

## callees

- `0x196c0`
- `0x19b60`

## pseudocode

```c

```

## disassembly

```asm
0x19b60  ldarg.1
0x19b61  brfalse.s loc_19B6B
0x19b63  ldarg.0
0x19b64  call     instance void System.Printing.PrintSystemUNCPathResolver::~PrintSystemUNCPathResolver()
0x19b69  br.s     loc_19B71
0x19b6b  ldarg.0
0x19b6c  call     instance void [mscorlib]System.Object::Finalize()
0x19b71  ret
```
