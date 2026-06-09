# initialize_msvcrt_compatibility

- ea: `0x18000a7f0`
- end: `0x18000a80d`
- name: `initialize_msvcrt_compatibility`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a7c4`
- `0x18000a7d4`

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
0x18000a7f0  sub     rsp, 28h
0x18000a7f4  call    __local_stdio_printf_options
0x18000a7f9  or      qword ptr [rax], 18h
0x18000a7fd  call    __local_stdio_scanf_options
0x18000a802  or      qword ptr [rax], 4
0x18000a806  xor     eax, eax
0x18000a808  add     rsp, 28h
0x18000a80c  retn
```
