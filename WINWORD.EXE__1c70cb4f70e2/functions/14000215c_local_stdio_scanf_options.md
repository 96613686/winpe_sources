# __local_stdio_scanf_options

- ea: `0x14000215c`
- end: `0x140002164`
- name: `__local_stdio_scanf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140002164`
- `0x140002760`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_scanf_options()
{
  return (unsigned __int64 *)&`__local_stdio_scanf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x14000215c  lea     rax, ?_OptionsStorage@?1??__local_stdio_scanf_options@@9@4_KA
0x140002163  retn
```
