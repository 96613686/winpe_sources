# __local_stdio_printf_options

- ea: `0x140002a70`
- end: `0x140002a78`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400028b4`
- `0x140005e70`
- `0x140006550`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x140002a70  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA
0x140002a77  retn
```
