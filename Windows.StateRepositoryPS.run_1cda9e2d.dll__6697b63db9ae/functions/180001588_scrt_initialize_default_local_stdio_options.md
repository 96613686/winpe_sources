# __scrt_initialize_default_local_stdio_options

- ea: `0x180001588`
- end: `0x1800015a3`
- name: `__scrt_initialize_default_local_stdio_options`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001168`

## callees

- `0x1800010b4`
- `0x1800010c4`

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
0x180001588  sub     rsp, 28h
0x18000158c  call    __local_stdio_printf_options
0x180001591  or      qword ptr [rax], 24h
0x180001595  call    __local_stdio_scanf_options
0x18000159a  or      qword ptr [rax], 2
0x18000159e  add     rsp, 28h
0x1800015a2  retn
```
