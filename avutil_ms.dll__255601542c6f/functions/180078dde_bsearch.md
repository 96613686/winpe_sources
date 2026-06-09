# bsearch

- ea: `0x180078dde`
- end: `0x180078de4`
- name: `bsearch`
- size: `6`
- prototype: `void *__cdecl(const void *Key, const void *Base, size_t NumOfElements, size_t SizeOfElements, _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18004b170`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!bsearch` at `0x180078dde`

## pseudocode

```c
// attributes: thunk
void *__cdecl bsearch(
        const void *Key,
        const void *Base,
        size_t NumOfElements,
        size_t SizeOfElements,
        _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)
{
  return __imp_bsearch(Key, Base, NumOfElements, SizeOfElements, CompareFunction);
}

```

## disassembly

```asm
0x180078dde  jmp     cs:__imp_bsearch
```
