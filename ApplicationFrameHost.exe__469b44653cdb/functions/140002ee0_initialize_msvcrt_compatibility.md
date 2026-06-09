# initialize_msvcrt_compatibility

- ea: `0x140002ee0`
- end: `0x140002efd`
- name: `initialize_msvcrt_compatibility`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002eb4`
- `0x140002ec4`

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
0x140002ee0  sub     rsp, 28h
0x140002ee4  call    __local_stdio_printf_options
0x140002ee9  or      qword ptr [rax], 18h
0x140002eed  call    __local_stdio_scanf_options
0x140002ef2  or      qword ptr [rax], 4
0x140002ef6  xor     eax, eax
0x140002ef8  add     rsp, 28h
0x140002efc  retn
```
