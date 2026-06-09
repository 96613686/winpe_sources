# initialize_legacy_wide_specifiers

- ea: `0x180001090`
- end: `0x1800010ad`
- name: `initialize_legacy_wide_specifiers`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800010b4`
- `0x1800010c4`

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
0x180001090  sub     rsp, 28h
0x180001094  call    __local_stdio_printf_options
0x180001099  or      qword ptr [rax], 4
0x18000109d  call    __local_stdio_scanf_options
0x1800010a2  or      qword ptr [rax], 2
0x1800010a6  xor     eax, eax
0x1800010a8  add     rsp, 28h
0x1800010ac  retn
```
