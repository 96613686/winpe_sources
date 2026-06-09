# wcslen

- ea: `0x18002cc50`
- end: `0x18002cc56`
- name: `wcslen`
- size: `6`
- prototype: `size_t __cdecl(const wchar_t *String)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18000128e`
- `0x18000157d`
- `0x180002c96`
- `0x180002ebf`
- `0x180003898`
- `0x180003a7f`
- `0x180004086`
- `0x180005340`
- `0x180007206`
- `0x18000e148`
- `0x180011f52`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002cc50`

## pseudocode

```c
// attributes: thunk
size_t __cdecl wcslen(const wchar_t *String)
{
  return __imp_wcslen(String);
}

```

## disassembly

```asm
0x18002cc50  jmp     cs:__imp_wcslen
```
