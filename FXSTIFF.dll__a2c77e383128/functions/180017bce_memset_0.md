# memset_0

- ea: `0x180017bce`
- end: `0x180017bd4`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `35`
- callee_count: `0`
- tags: ``

## callers

- `0x180001da8`
- `0x18000212c`
- `0x1800025e0`
- `0x180003b00`
- `0x180004344`
- `0x180004c48`
- `0x180004e70`
- `0x180005380`
- `0x180005d80`
- `0x1800069c0`
- `0x180007d60`
- `0x1800087a0`
- `0x180008f80`
- `0x1800091a0`
- `0x180009c84`
- `0x18000ac38`
- `0x18000b604`
- `0x18000cab0`
- `0x18000d4b0`
- `0x18000fc64`
- `0x18000fecc`
- `0x180010168`
- `0x180010f58`
- `0x180011324`
- `0x180012174`
- `0x18001485c`
- `0x180014c60`
- `0x1800159a0`
- `0x180015ea0`
- `0x1800165d0`
- `0x180016794`
- `0x180016a08`
- `0x180016f40`
- `0x1800174e0`
- `0x18001795c`

## import_xrefs

- `msvcrt!memset` at `0x180017bce`

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
0x180017bce  jmp     cs:__imp_memset
```
