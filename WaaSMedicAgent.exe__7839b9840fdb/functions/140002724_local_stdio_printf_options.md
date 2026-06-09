# __local_stdio_printf_options

- ea: `0x140002724`
- end: `0x14000272c`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140002700`
- `0x140002750`
- `0x140002e40`
- `0x140002fa4`
- `0x1400036b4`
- `0x140003708`
- `0x14000376c`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x140002724  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x14000272b  retn
```
