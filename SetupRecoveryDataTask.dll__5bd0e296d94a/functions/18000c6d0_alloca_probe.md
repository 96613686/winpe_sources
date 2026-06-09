# _alloca_probe

- ea: `0x18000c6d0`
- end: `0x18000c71d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800026a4`
- `0x18000290c`
- `0x180002ba8`
- `0x180007f30`
- `0x18000b320`
- `0x18000b430`

## callees

- `0x18000c6d0`

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
0x18000c6d0  sub     rsp, 10h
0x18000c6d4  mov     [rsp+10h+var_10], r10
0x18000c6d8  mov     [rsp+10h+var_8], r11
0x18000c6dd  xor     r11, r11
0x18000c6e0  lea     r10, [rsp+10h+arg_0]
0x18000c6e5  sub     r10, rax
0x18000c6e8  cmovb   r10, r11
0x18000c6ec  mov     r11, gs:10h
0x18000c6f5  cmp     r10, r11
0x18000c6f8  jnb     short loc_18000C70F
0x18000c6fa  and     r10w, 0F000h
0x18000c700  lea     r11, [r11-1000h]
0x18000c707  test    [r11], r11b
0x18000c70a  cmp     r10, r11
0x18000c70d  jb      short loc_18000C700
0x18000c70f  mov     r10, [rsp+10h+var_10]
0x18000c713  mov     r11, [rsp+10h+var_8]
0x18000c718  add     rsp, 10h
0x18000c71c  retn
```
