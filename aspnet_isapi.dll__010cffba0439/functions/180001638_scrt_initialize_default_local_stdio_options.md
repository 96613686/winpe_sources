# __scrt_initialize_default_local_stdio_options

- ea: `0x180001638`
- end: `0x180001653`
- name: `__scrt_initialize_default_local_stdio_options`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011a0`

## callees

- `0x180001628`
- `0x180001630`

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
0x180001638  sub     rsp, 28h
0x18000163c  call    __local_stdio_printf_options
0x180001641  or      qword ptr [rax], 24h
0x180001645  call    __local_stdio_scanf_options
0x18000164a  or      qword ptr [rax], 2
0x18000164e  add     rsp, 28h
0x180001652  retn
```
