# System.Printing.PrintSystemUNCPathCracker::Dispose

- ea: `0x19c70`
- end: `0x19c82`
- name: `System.Printing.PrintSystemUNCPathCracker::Dispose`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x19c90`

## callees

- `0x19c40`
- `0x19c70`

## pseudocode

```c

```

## disassembly

```asm
0x19c70  ldarg.1
0x19c71  brfalse.s loc_19C7B
0x19c73  ldarg.0
0x19c74  call     instance void System.Printing.PrintSystemUNCPathCracker::~PrintSystemUNCPathCracker()
0x19c79  br.s     loc_19C81
0x19c7b  ldarg.0
0x19c7c  call     instance void [mscorlib]System.Object::Finalize()
0x19c81  ret
```
