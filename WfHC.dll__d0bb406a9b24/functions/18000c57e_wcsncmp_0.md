# wcsncmp_0

- ea: `0x18000c57e`
- end: `0x18000c584`
- name: `wcsncmp_0`
- size: `6`
- prototype: `int __cdecl(const wchar_t *String1, const wchar_t *String2, size_t MaxCount)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002c10`
- `0x1800043a0`
- `0x180004500`
- `0x1800049d0`

## import_xrefs

- `msvcrt!wcsncmp` at `0x18000c57e`

## pseudocode

```c
// attributes: thunk
int __cdecl wcsncmp_0(const wchar_t *String1, const wchar_t *String2, size_t MaxCount)
{
  return wcsncmp(String1, String2, MaxCount);
}

```

## disassembly

```asm
0x18000c57e  jmp     cs:__imp_wcsncmp
```
