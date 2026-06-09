# __scrt_initialize_default_local_stdio_options

- ea: `0x1400016fc`
- end: `0x140001717`
- name: `__scrt_initialize_default_local_stdio_options`
- size: `27`
- prototype: `unsigned __int64 *()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001140`

## callees

- `0x140001034`
- `0x140001044`

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
0x1400016fc  sub     rsp, 28h
0x140001700  call    __local_stdio_printf_options
0x140001705  or      qword ptr [rax], 24h
0x140001709  call    __local_stdio_scanf_options
0x14000170e  or      qword ptr [rax], 2
0x140001712  add     rsp, 28h
0x140001716  retn
```
