# __local_stdio_printf_options

- ea: `0x140007238`
- end: `0x140007240`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1400012b0`
- `0x1400012f0`
- `0x1400019b4`
- `0x14000259c`
- `0x1400025ec`
- `0x140006cc0`
- `0x14000bbd8`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x140007238  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x14000723f  retn
```
