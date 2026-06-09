# __stdio_common_vsprintf

- ea: `0x1800229ba`
- end: `0x1800229c0`
- name: `__stdio_common_vsprintf`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800114d8`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsprintf` at `0x1800229ba`

## pseudocode

```c
// attributes: thunk
int __cdecl _stdio_common_vsprintf(
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
0x1800229ba  jmp     cs:__imp___stdio_common_vsprintf
```
