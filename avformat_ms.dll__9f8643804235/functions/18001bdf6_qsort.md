# qsort

- ea: `0x18001bdf6`
- end: `0x18001bdfc`
- name: `qsort`
- size: `6`
- prototype: `void __cdecl(void *Base, size_t NumOfElements, size_t SizeOfElements, _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180006390`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!qsort` at `0x18001bdf6`

## pseudocode

```c
// attributes: thunk
void __cdecl qsort(
        void *Base,
        size_t NumOfElements,
        size_t SizeOfElements,
        _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)
{
  __imp_qsort(Base, NumOfElements, SizeOfElements, CompareFunction);
}

```

## disassembly

```asm
0x18001bdf6  jmp     cs:__imp_qsort
```
