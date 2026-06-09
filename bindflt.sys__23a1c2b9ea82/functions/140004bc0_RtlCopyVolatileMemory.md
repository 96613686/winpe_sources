# RtlCopyVolatileMemory

- ea: `0x140004bc0`
- end: `0x140004bc5`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400034c8`
- `0x14000f608`
- `0x140024a64`
- `0x140025c70`

## callees

- `0x140004cc0`

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
0x140004bc0  jmp     memmove
```
