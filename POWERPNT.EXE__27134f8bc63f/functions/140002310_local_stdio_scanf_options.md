# __local_stdio_scanf_options

- ea: `0x140002310`
- end: `0x140002318`
- name: `__local_stdio_scanf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400022f0`
- `0x140002360`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_scanf_options()
{
  return (unsigned __int64 *)&`__local_stdio_scanf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x140002310  lea     rax, ?_OptionsStorage@?1??__local_stdio_scanf_options@@9@4_KA; unsigned __int64 `__local_stdio_scanf_options'::`2'::_OptionsStorage
0x140002317  retn
```
