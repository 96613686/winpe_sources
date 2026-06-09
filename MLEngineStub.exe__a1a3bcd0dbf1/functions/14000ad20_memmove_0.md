# memmove_0

- ea: `0x14000ad20`
- end: `0x14000ad26`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140008058`
- `0x140008c48`
- `0x140009d9c`
- `0x14000a678`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x14000ad20`

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
0x14000ad20  jmp     cs:__imp_memmove
```
