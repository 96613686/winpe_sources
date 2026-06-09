# memset

- ea: `0x14000aa73`
- end: `0x14000aa79`
- name: `memset`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x14000a448`
- `0x14000cf78`
- `0x14000d194`
- `0x14000e7a4`
- `0x14000ea20`
- `0x140010ac0`
- `0x140012510`
- `0x140012688`
- `0x140015bc0`
- `0x140019810`
- `0x14001e28c`

## import_xrefs

- `msvcrt!memset` at `0x14000aa73`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  return __imp_memset(a1, Val, Size);
}

```

## disassembly

```asm
0x14000aa73  jmp     cs:__imp_memset
```
