# memmove_0

- ea: `0x18000dc5b`
- end: `0x18000dc61`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `20`
- callee_count: `0`
- tags: ``

## callers

- `0x180008ce0`
- `0x180008e40`
- `0x18000a190`
- `0x18000c210`
- `0x1800142c4`
- `0x18002d5f8`
- `0x180030878`
- `0x180034e24`
- `0x1800354bc`
- `0x180036b80`
- `0x180036bfc`
- `0x180037d70`
- `0x180042480`
- `0x1800437d0`
- `0x180044974`
- `0x180046020`
- `0x1800467fc`
- `0x180046eac`
- `0x180047988`
- `0x18004b17c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18000dc5b`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove_0(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x18000dc5b  jmp     cs:__imp_memmove
```
