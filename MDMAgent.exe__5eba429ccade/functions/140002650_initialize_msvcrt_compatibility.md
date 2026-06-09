# initialize_msvcrt_compatibility

- ea: `0x140002650`
- end: `0x14000266d`
- name: `initialize_msvcrt_compatibility`
- size: `29`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002624`
- `0x140002634`

## pseudocode

```c
__int64 initialize_msvcrt_compatibility()
{
  unsigned __int64 *v0; // rax
  unsigned __int64 *v1; // rax

  v0 = _local_stdio_printf_options();
  *v0 |= 0x18u;
  v1 = _local_stdio_scanf_options();
  *v1 |= 4u;
  return 0;
}

```

## disassembly

```asm
0x140002650  sub     rsp, 28h
0x140002654  call    __local_stdio_printf_options
0x140002659  or      qword ptr [rax], 18h
0x14000265d  call    __local_stdio_scanf_options
0x140002662  or      qword ptr [rax], 4
0x140002666  xor     eax, eax
0x140002668  add     rsp, 28h
0x14000266c  retn
```
