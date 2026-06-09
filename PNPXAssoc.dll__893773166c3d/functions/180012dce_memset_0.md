# memset_0

- ea: `0x180012dce`
- end: `0x180012dd4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x1800029d0`
- `0x180002c38`
- `0x180002ed4`
- `0x18000314c`
- `0x180003af4`
- `0x180004c28`
- `0x180005260`
- `0x180005b14`
- `0x18000a9e8`
- `0x18000ccec`
- `0x18000f95c`
- `0x18001085c`
- `0x180012ac0`

## import_xrefs

- `msvcrt!memset` at `0x180012dce`

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
0x180012dce  jmp     cs:__imp_memset
```
