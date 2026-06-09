# __scrt_initialize_default_local_stdio_options

- ea: `0x180001574`
- end: `0x18000158f`
- name: `__scrt_initialize_default_local_stdio_options`
- size: `27`
- prototype: `unsigned __int64 *()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001148`

## callees

- `0x180001094`
- `0x1800010a4`

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
0x180001574  sub     rsp, 28h
0x180001578  call    __local_stdio_printf_options
0x18000157d  or      qword ptr [rax], 24h
0x180001581  call    __local_stdio_scanf_options
0x180001586  or      qword ptr [rax], 2
0x18000158a  add     rsp, 28h
0x18000158e  retn
```
