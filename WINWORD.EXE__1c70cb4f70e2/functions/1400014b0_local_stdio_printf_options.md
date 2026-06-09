# __local_stdio_printf_options

- ea: `0x1400014b0`
- end: `0x1400014b8`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001440`
- `0x140002164`
- `0x140002760`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x1400014b0  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA
0x1400014b7  retn
```
