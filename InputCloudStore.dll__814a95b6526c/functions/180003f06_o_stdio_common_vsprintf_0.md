# _o___stdio_common_vsprintf_0

- ea: `0x180003f06`
- end: `0x180003f0c`
- name: `_o___stdio_common_vsprintf_0`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800040a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf` at `0x180003f06`

## pseudocode

```c
// attributes: thunk
int __cdecl o___stdio_common_vsprintf_0(
        unsigned __int64 Options,
        char *Buffer,
        size_t BufferCount,
        const char *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return __stdio_common_vsprintf(Options, Buffer, BufferCount, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x180003f06  jmp     cs:__imp___stdio_common_vsprintf
```
