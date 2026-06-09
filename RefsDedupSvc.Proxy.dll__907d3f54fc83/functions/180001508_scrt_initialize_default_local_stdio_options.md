# __scrt_initialize_default_local_stdio_options

- ea: `0x180001508`
- end: `0x180001523`
- name: `__scrt_initialize_default_local_stdio_options`
- size: `27`
- prototype: `unsigned __int64 *()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x180001034`
- `0x180001044`

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
0x180001508  sub     rsp, 28h
0x18000150c  call    __local_stdio_printf_options
0x180001511  or      qword ptr [rax], 24h
0x180001515  call    __local_stdio_scanf_options
0x18000151a  or      qword ptr [rax], 2
0x18000151e  add     rsp, 28h
0x180001522  retn
```
