# _create_locale

- ea: `0x18002c9a0`
- end: `0x18002c9a6`
- name: `_create_locale`
- size: `6`
- prototype: `_locale_t __cdecl(int Category, const char *Locale)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180010c68`

## import_xrefs

- `api-ms-win-crt-locale-l1-1-0!_create_locale` at `0x18002c9a0`

## pseudocode

```c
// attributes: thunk
_locale_t __cdecl create_locale(int Category, const char *Locale)
{
  return _create_locale(Category, Locale);
}

```

## disassembly

```asm
0x18002c9a0  jmp     cs:__imp__create_locale
```
