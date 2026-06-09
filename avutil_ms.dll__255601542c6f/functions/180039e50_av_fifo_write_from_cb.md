# av_fifo_write_from_cb

- ea: `0x180039e50`
- end: `0x180039e6e`
- name: `av_fifo_write_from_cb`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180039f88`

## pseudocode

```c
__int64 __fastcall av_fifo_write_from_cb(int a1, int a2, __int64 a3, int a4)
{
  return sub_180039F88(a1, 0, a4, a2, a3);
}

```

## disassembly

```asm
0x180039e50  sub     rsp, 38h
0x180039e54  mov     rax, r9
0x180039e57  mov     [rsp+38h+var_18], r8
0x180039e5c  mov     r9, rdx
0x180039e5f  mov     r8, rax
0x180039e62  xor     edx, edx
0x180039e64  call    sub_180039F88
0x180039e69  add     rsp, 38h
0x180039e6d  retn
```
