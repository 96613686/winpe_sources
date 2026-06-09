# initialize_legacy_wide_specifiers

- ea: `0x180001010`
- end: `0x18000102d`
- name: `initialize_legacy_wide_specifiers`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001034`
- `0x180001044`

## pseudocode

```c
__int64 initialize_legacy_wide_specifiers()
{
  unsigned __int64 *v0; // rax
  unsigned __int64 *v1; // rax

  v0 = _local_stdio_printf_options();
  *v0 |= 4u;
  v1 = _local_stdio_scanf_options();
  *v1 |= 2u;
  return 0;
}

```

## disassembly

```asm
0x180001010  sub     rsp, 28h
0x180001014  call    __local_stdio_printf_options
0x180001019  or      qword ptr [rax], 4
0x18000101d  call    __local_stdio_scanf_options
0x180001022  or      qword ptr [rax], 2
0x180001026  xor     eax, eax
0x180001028  add     rsp, 28h
0x18000102c  retn
```
