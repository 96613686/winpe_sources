# HSTRING_UserFree_0

- ea: `0x180001880`
- end: `0x180001886`
- name: `HSTRING_UserFree_0`
- size: `6`
- prototype: `void __stdcall(unsigned int *, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!HSTRING_UserFree` at `0x180001880`

## pseudocode

```c
// attributes: thunk
void __stdcall HSTRING_UserFree_0(unsigned int *a1, HSTRING *a2)
{
  HSTRING_UserFree(a1, a2);
}

```

## disassembly

```asm
0x180001880  jmp     cs:__imp_HSTRING_UserFree
```
