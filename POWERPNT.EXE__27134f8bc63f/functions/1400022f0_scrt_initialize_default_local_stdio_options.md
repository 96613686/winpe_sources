# __scrt_initialize_default_local_stdio_options

- ea: `0x1400022f0`
- end: `0x14000230b`
- name: `__scrt_initialize_default_local_stdio_options`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400022e0`

## callees

- `0x140002310`
- `0x140002380`

## pseudocode

```c
unsigned __int64 *_scrt_initialize_default_local_stdio_options()
{
  unsigned __int64 *v0; // rax
  unsigned __int64 *result; // rax

  v0 = _local_stdio_printf_options();
  *v0 |= 0x24u;
  result = _local_stdio_scanf_options();
  *result |= 2u;
  return result;
}

```

## disassembly

```asm
0x1400022f0  sub     rsp, 28h
0x1400022f4  call    __local_stdio_printf_options
0x1400022f9  or      qword ptr [rax], 24h
0x1400022fd  call    __local_stdio_scanf_options
0x140002302  or      qword ptr [rax], 2
0x140002306  add     rsp, 28h
0x14000230a  retn
```
