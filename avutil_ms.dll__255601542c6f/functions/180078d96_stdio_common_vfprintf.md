# __stdio_common_vfprintf

- ea: `0x180078d96`
- end: `0x180078d9c`
- name: `__stdio_common_vfprintf`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800432f8`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vfprintf` at `0x180078d96`

## pseudocode

```c
// attributes: thunk
int __cdecl _stdio_common_vfprintf(
        unsigned __int64 Options,
        FILE *Stream,
        const char *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return __stdio_common_vfprintf(Options, Stream, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x180078d96  jmp     cs:__imp___stdio_common_vfprintf
```
