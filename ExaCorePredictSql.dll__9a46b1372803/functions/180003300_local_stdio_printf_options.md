# __local_stdio_printf_options

- ea: `0x180003300`
- end: `0x180003308`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800032a0`
- `0x180004894`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x180003300  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA
0x180003307  retn
```
