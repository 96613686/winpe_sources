# initialize_msvcrt_compatibility

- ea: `0x140001310`
- end: `0x14000132d`
- name: `initialize_msvcrt_compatibility`
- size: `29`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400012f4`
- `0x1400068fc`

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
0x140001310  sub     rsp, 28h
0x140001314  call    __local_stdio_printf_options
0x140001319  or      qword ptr [rax], 18h
0x14000131d  call    __local_stdio_scanf_options
0x140001322  or      qword ptr [rax], 4
0x140001326  xor     eax, eax
0x140001328  add     rsp, 28h
0x14000132c  retn
```
