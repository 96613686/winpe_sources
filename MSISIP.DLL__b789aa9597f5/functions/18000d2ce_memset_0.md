# memset_0

- ea: `0x18000d2ce`
- end: `0x18000d2d4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180003a70`
- `0x1800051d0`
- `0x180005a30`
- `0x1800080dc`
- `0x180008914`
- `0x1800089c4`
- `0x180008fc4`
- `0x18000983c`
- `0x180009990`
- `0x18000a780`
- `0x18000aa28`
- `0x18000b0c4`
- `0x18000c39c`
- `0x18000c4d8`

## import_xrefs

- `msvcrt!memset` at `0x18000d2ce`

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
0x18000d2ce  jmp     cs:__imp_memset
```
