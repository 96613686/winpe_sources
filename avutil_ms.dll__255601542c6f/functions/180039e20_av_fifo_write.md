# av_fifo_write

- ea: `0x180039e20`
- end: `0x180039e44`
- name: `av_fifo_write`
- size: `36`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18002abf0`
- `0x180033970`
- `0x180051cf0`

## callees

- `0x180039f88`

## pseudocode

```c
__int64 __fastcall av_fifo_write(int a1, int a2, __int64 a3)
{
  __int64 v4; // [rsp+50h] [rbp+18h] BYREF

  v4 = a3;
  return sub_180039F88(a1, a2, (unsigned int)&v4, 0, 0);
}

```

## disassembly

```asm
0x180039e20  mov     [rsp+arg_10], r8
0x180039e25  sub     rsp, 38h
0x180039e29  xor     r9d, r9d
0x180039e2c  mov     [rsp+38h+var_18], 0
0x180039e35  lea     r8, [rsp+38h+arg_10]
0x180039e3a  call    sub_180039F88
0x180039e3f  add     rsp, 38h
0x180039e43  retn
```
