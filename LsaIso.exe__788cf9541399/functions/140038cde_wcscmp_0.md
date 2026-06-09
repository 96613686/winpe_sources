# wcscmp_0

- ea: `0x140038cde`
- end: `0x140038ce4`
- name: `wcscmp_0`
- size: `6`
- prototype: `int __cdecl(const wchar_t *String1, const wchar_t *String2)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x140008538`
- `0x14000a650`
- `0x14000a7f0`
- `0x14000ea40`
- `0x14000f520`
- `0x1400106a0`
- `0x1400113a0`
- `0x140013aec`
- `0x140037a1c`

## import_xrefs

- `msvcrt!wcscmp` at `0x140038cde`

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
0x140038cde  jmp     cs:__imp_wcscmp
```
