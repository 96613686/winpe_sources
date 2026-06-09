# System.Printing.PrintSystemDefaultPathResolver::Dispose

- ea: `0x19620`
- end: `0x19632`
- name: `System.Printing.PrintSystemDefaultPathResolver::Dispose`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x19640`

## callees

- `0x19600`
- `0x19620`

## pseudocode

```c

```

## disassembly

```asm
0x19620  ldarg.1
0x19621  brfalse.s loc_1962B
0x19623  ldarg.0
0x19624  call     instance void System.Printing.PrintSystemDefaultPathResolver::~PrintSystemDefaultPathResolver()
0x19629  br.s     loc_19631
0x1962b  ldarg.0
0x1962c  call     instance void [mscorlib]System.Object::Finalize()
0x19631  ret
```
