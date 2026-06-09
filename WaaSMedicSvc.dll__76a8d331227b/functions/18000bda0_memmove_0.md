# memmove_0

- ea: `0x18000bda0`
- end: `0x18000bda6`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180008794`
- `0x180009508`
- `0x18000aa84`
- `0x18000ae6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18000bda0`

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
0x18000bda0  jmp     cs:__imp_memmove
```
