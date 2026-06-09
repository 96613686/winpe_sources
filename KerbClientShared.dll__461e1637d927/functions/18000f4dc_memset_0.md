# memset_0

- ea: `0x18000f4dc`
- end: `0x18000f4e2`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a920`
- `0x18000aed0`
- `0x18000c2d0`
- `0x18000dbd8`
- `0x18000fd38`
- `0x18000fde8`
- `0x18001007c`
- `0x180011174`
- `0x1800122b8`
- `0x1800123dc`
- `0x1800131a4`
- `0x180014018`
- `0x1800144f4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x18000f4dc`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset_0(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x18000f4dc  jmp     cs:__imp_memset
```
