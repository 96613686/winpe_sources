# __stdio_common_vsnwprintf_s

- ea: `0x180004fda`
- end: `0x180004fe0`
- name: `__stdio_common_vsnwprintf_s`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, size_t MaxCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000517c`
- `0x180005230`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsnwprintf_s` at `0x180004fda`

## pseudocode

```c
// attributes: thunk
int __cdecl _stdio_common_vsnwprintf_s(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        size_t MaxCount,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return _o___stdio_common_vsnwprintf_s(Options, Buffer, BufferCount, MaxCount, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x180004fda  jmp     cs:__imp__o___stdio_common_vsnwprintf_s
```
