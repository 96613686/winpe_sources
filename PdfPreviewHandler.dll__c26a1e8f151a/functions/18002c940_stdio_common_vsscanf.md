# __stdio_common_vsscanf

- ea: `0x18002c940`
- end: `0x18002c946`
- name: `__stdio_common_vsscanf`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, const char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000fd02`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsscanf` at `0x18002c940`

## pseudocode

```c
// attributes: thunk
int __cdecl _stdio_common_vsscanf(
        unsigned __int64 Options,
        const char *Buffer,
        size_t BufferCount,
        const char *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return __stdio_common_vsscanf(Options, Buffer, BufferCount, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x18002c940  jmp     cs:__imp___stdio_common_vsscanf
```
