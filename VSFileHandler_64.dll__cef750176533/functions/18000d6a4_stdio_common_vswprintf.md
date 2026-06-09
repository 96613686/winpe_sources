# __stdio_common_vswprintf

- ea: `0x18000d6a4`
- end: `0x18000d6a9`
- name: `__stdio_common_vswprintf`
- size: `5`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002498`

## callees

- `0x18000c07c`

## pseudocode

```c
// attributes: thunk
int __cdecl _stdio_common_vswprintf(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return common_vsprintf___crt_stdio_output::standard_base_wchar_t_(
           Options,
           (int)Buffer,
           BufferCount,
           (int)Format,
           Locale,
           (__int64)ArgList);
}

```

## disassembly

```asm
0x18000d6a4  jmp     common_vsprintf___crt_stdio_output__standard_base_wchar_t_
```
