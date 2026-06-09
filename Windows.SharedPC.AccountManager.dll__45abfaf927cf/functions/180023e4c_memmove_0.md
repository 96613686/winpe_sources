# memmove_0

- ea: `0x180023e4c`
- end: `0x180023e52`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000bc48`
- `0x180011a6c`
- `0x180011b80`
- `0x18001a6fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180023e4c`

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
0x180023e4c  jmp     cs:__imp_memmove
```
