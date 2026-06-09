# memmove_0

- ea: `0x180003bbc`
- end: `0x180003bc2`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180008a28`
- `0x18001d850`
- `0x18001e1e0`
- `0x1800200c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180003bbc`

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
0x180003bbc  jmp     cs:__imp_memmove
```
