# __scrt_initialize_default_local_stdio_options

- ea: `0x180001580`
- end: `0x18000159b`
- name: `__scrt_initialize_default_local_stdio_options`
- size: `27`
- prototype: `unsigned __int64 *()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001128`

## callees

- `0x180001074`
- `0x180001084`

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
0x180001580  sub     rsp, 28h
0x180001584  call    __local_stdio_printf_options
0x180001589  or      qword ptr [rax], 24h
0x18000158d  call    __local_stdio_scanf_options
0x180001592  or      qword ptr [rax], 2
0x180001596  add     rsp, 28h
0x18000159a  retn
```
