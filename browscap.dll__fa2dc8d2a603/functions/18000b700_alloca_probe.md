# _alloca_probe

- ea: `0x18000b700`
- end: `0x18000b74d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b10`
- `0x180002cc8`
- `0x180002e4c`
- `0x180003f7c`
- `0x180004f3c`
- `0x1800050c0`
- `0x180005408`
- `0x180005eb0`
- `0x1800061ec`
- `0x18000640c`
- `0x18000672c`
- `0x180006b14`
- `0x180007034`
- `0x1800076e8`
- `0x180007a70`
- `0x1800081b0`
- `0x1800085c0`
- `0x180008940`
- `0x180008fa8`

## callees

- `0x18000b700`

## pseudocode

```c
unsigned __int64 __fastcall alloca_probe()
{
  unsigned __int64 result; // rax
  char *v1; // r10
  char *StackLimit; // r11
  char v3; // [rsp+18h] [rbp+8h] BYREF

  v1 = &v3 - result;
  if ( (unsigned __int64)&v3 < result )
    v1 = 0;
  StackLimit = (char *)NtCurrentTeb()->NtTib.StackLimit;
  if ( v1 < StackLimit )
  {
    LOWORD(v1) = (unsigned __int16)v1 & 0xF000;
    do
      StackLimit -= 4096;
    while ( v1 < StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x18000b700  sub     rsp, 10h
0x18000b704  mov     [rsp+10h+var_10], r10
0x18000b708  mov     [rsp+10h+var_8], r11
0x18000b70d  xor     r11, r11
0x18000b710  lea     r10, [rsp+10h+arg_0]
0x18000b715  sub     r10, rax
0x18000b718  cmovb   r10, r11
0x18000b71c  mov     r11, gs:10h
0x18000b725  cmp     r10, r11
0x18000b728  jnb     short loc_18000B73F
0x18000b72a  and     r10w, 0F000h
0x18000b730  lea     r11, [r11-1000h]
0x18000b737  test    [r11], r11b
0x18000b73a  cmp     r10, r11
0x18000b73d  jb      short loc_18000B730
0x18000b73f  mov     r10, [rsp+10h+var_10]
0x18000b743  mov     r11, [rsp+10h+var_8]
0x18000b748  add     rsp, 10h
0x18000b74c  retn
```
