# memmove_0

- ea: `0x1800045cc`
- end: `0x1800045d2`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180006734`
- `0x1800067a4`
- `0x180008f84`
- `0x18000ee4c`
- `0x180010c20`
- `0x180011030`
- `0x180011358`
- `0x1800114cc`
- `0x18001dee0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800045cc`

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
0x1800045cc  jmp     cs:__imp_memmove
```
