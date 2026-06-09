# __local_stdio_printf_options

- ea: `0x180001244`
- end: `0x18000124c`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001220`
- `0x180001270`
- `0x180001b24`
- `0x18000209c`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x180001244  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x18000124b  retn
```
