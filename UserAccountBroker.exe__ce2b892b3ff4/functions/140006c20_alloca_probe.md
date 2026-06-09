# _alloca_probe

- ea: `0x140006c20`
- end: `0x140006c6d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004254`
- `0x1400044c4`
- `0x140004758`

## callees

- `0x140006c20`

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
0x140006c20  sub     rsp, 10h
0x140006c24  mov     [rsp+10h+var_10], r10
0x140006c28  mov     [rsp+10h+var_8], r11
0x140006c2d  xor     r11, r11
0x140006c30  lea     r10, [rsp+10h+arg_0]
0x140006c35  sub     r10, rax
0x140006c38  cmovb   r10, r11
0x140006c3c  mov     r11, gs:10h
0x140006c45  cmp     r10, r11
0x140006c48  jnb     short loc_140006C5F
0x140006c4a  and     r10w, 0F000h
0x140006c50  lea     r11, [r11-1000h]
0x140006c57  test    [r11], r11b
0x140006c5a  cmp     r10, r11
0x140006c5d  jb      short loc_140006C50
0x140006c5f  mov     r10, [rsp+10h+var_10]
0x140006c63  mov     r11, [rsp+10h+var_8]
0x140006c68  add     rsp, 10h
0x140006c6c  retn
```
