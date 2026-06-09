# __stdio_common_vsprintf_0

- ea: `0x180005d33`
- end: `0x180005d39`
- name: `__stdio_common_vsprintf_0`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000d000`
- `0x180027e20`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsprintf` at `0x180005d33`

## pseudocode

```c
// attributes: thunk
int __cdecl _stdio_common_vsprintf_0(
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
0x180005d33  jmp     cs:__imp___stdio_common_vsprintf
```
