# wcscmp_0

- ea: `0x140015ace`
- end: `0x140015ad4`
- name: `wcscmp_0`
- size: `6`
- prototype: `int __cdecl(const wchar_t *String1, const wchar_t *String2)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x14000b250`
- `0x14000cfd0`
- `0x14000d778`
- `0x14000e1dc`
- `0x14000f810`
- `0x140010244`
- `0x1400116c4`
- `0x140015644`

## import_xrefs

- `msvcrt!wcscmp` at `0x140015ace`

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
0x140015ace  jmp     cs:__imp_wcscmp
```
