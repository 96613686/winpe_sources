# memset_0

- ea: `0x18001dfe2`
- end: `0x18001dfe8`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x18000278c`
- `0x18000284c`
- `0x180002ae8`
- `0x1800036b4`
- `0x1800043b4`
- `0x180004aac`
- `0x180004be8`
- `0x180005318`
- `0x180006fb0`
- `0x180009274`
- `0x18000c5d8`
- `0x180010798`
- `0x180012304`
- `0x1800160c8`
- `0x1800163b8`
- `0x18001c158`
- `0x18001cde4`
- `0x18001d684`
- `0x18001d9f0`

## import_xrefs

- `msvcrt!memset` at `0x18001dfe2`

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
0x18001dfe2  jmp     cs:__imp_memset
```
