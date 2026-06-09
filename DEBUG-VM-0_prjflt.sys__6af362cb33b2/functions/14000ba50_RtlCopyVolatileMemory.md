# RtlCopyVolatileMemory

- ea: `0x14000ba50`
- end: `0x14000ba55`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140001514`
- `0x140021008`
- `0x1400260a4`
- `0x1400266ec`
- `0x140026d94`
- `0x140027144`
- `0x1400277f4`
- `0x140027ca0`
- `0x140027f64`
- `0x140028048`
- `0x140031a00`

## callees

- `0x14000bb80`

## pseudocode

```c
// attributes: thunk
void *__cdecl RtlCopyVolatileMemory(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x14000ba50  jmp     memmove
```
