# wcscmp_0

- ea: `0x18000d2da`
- end: `0x18000d2e0`
- name: `wcscmp_0`
- size: `6`
- prototype: `int __cdecl(const wchar_t *String1, const wchar_t *String2)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001be0`
- `0x1800022b0`
- `0x180006b40`

## import_xrefs

- `msvcrt!wcscmp` at `0x18000d2da`

## pseudocode

```c
// attributes: thunk
int __cdecl wcscmp_0(const wchar_t *String1, const wchar_t *String2)
{
  return wcscmp(String1, String2);
}

```

## disassembly

```asm
0x18000d2da  jmp     cs:__imp_wcscmp
```
