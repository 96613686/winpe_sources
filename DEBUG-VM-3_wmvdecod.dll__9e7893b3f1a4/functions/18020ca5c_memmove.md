# memmove

- ea: `0x18020ca5c`
- end: `0x18020ca62`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800b2af4`
- `0x1800b4050`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18020ca5c`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  return __imp_memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x18020ca5c  jmp     cs:__imp_memmove
```
