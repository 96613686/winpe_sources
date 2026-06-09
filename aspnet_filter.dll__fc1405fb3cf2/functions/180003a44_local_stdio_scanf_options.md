# __local_stdio_scanf_options

- ea: `0x180003a44`
- end: `0x180003a4c`
- name: `__local_stdio_scanf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003a4c`
- `0x180004370`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_scanf_options()
{
  return (unsigned __int64 *)&`__local_stdio_scanf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x180003a44  lea     rax, ?_OptionsStorage@?1??__local_stdio_scanf_options@@9@4_KA
0x180003a4b  retn
```
