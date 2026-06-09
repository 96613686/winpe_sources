# RtlCopyVolatileMemory

- ea: `0x140011590`
- end: `0x140011595`
- name: `RtlCopyVolatileMemory`
- size: `5`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x14000da78`
- `0x140022220`
- `0x140022fcc`
- `0x14002378c`
- `0x14002382c`
- `0x140024078`
- `0x140032ee4`
- `0x1400376f0`
- `0x140037d20`
- `0x14003ba5c`
- `0x14003bf4c`
- `0x14003e0b8`

## callees

- `0x1400116c0`

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
0x140011590  jmp     memmove
```
