# __stdio_common_vsscanf_0

- ea: `0x18000636f`
- end: `0x180006375`
- name: `__stdio_common_vsscanf_0`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, const char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180042570`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsscanf` at `0x18000636f`

## pseudocode

```c
// attributes: thunk
int __cdecl _stdio_common_vsscanf_0(
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
0x18000636f  jmp     cs:__imp___stdio_common_vsscanf
```
