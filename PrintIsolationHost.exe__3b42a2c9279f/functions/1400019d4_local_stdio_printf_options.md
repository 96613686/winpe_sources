# __local_stdio_printf_options

- ea: `0x1400019d4`
- end: `0x1400019dc`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400019b0`
- `0x140001a00`
- `0x140002064`
- `0x14000269c`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x1400019d4  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x1400019db  retn
```
