# memmove_0

- ea: `0x180002db8`
- end: `0x180002dbe`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x180007368`
- `0x180008770`
- `0x1800088e4`
- `0x180008d90`
- `0x1800092f0`
- `0x18000937c`
- `0x18000a0e8`
- `0x18000b554`
- `0x18000b640`
- `0x18000ba9c`
- `0x18000f5c8`
- `0x1800101d0`
- `0x180010a80`
- `0x180015e20`
- `0x180016ba0`
- `0x18001724c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180002db8`

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
0x180002db8  jmp     cs:__imp_memmove
```
