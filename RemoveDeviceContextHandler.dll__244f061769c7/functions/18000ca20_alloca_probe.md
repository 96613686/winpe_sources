# _alloca_probe

- ea: `0x18000ca20`
- end: `0x18000ca6d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d7c`
- `0x180002fec`
- `0x180003288`
- `0x180006784`
- `0x180009538`
- `0x180009884`
- `0x18000abe0`

## callees

- `0x18000ca20`

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
0x18000ca20  sub     rsp, 10h
0x18000ca24  mov     [rsp+10h+var_10], r10
0x18000ca28  mov     [rsp+10h+var_8], r11
0x18000ca2d  xor     r11, r11
0x18000ca30  lea     r10, [rsp+10h+arg_0]
0x18000ca35  sub     r10, rax
0x18000ca38  cmovb   r10, r11
0x18000ca3c  mov     r11, gs:10h
0x18000ca45  cmp     r10, r11
0x18000ca48  jnb     short loc_18000CA5F
0x18000ca4a  and     r10w, 0F000h
0x18000ca50  lea     r11, [r11-1000h]
0x18000ca57  test    [r11], r11b
0x18000ca5a  cmp     r10, r11
0x18000ca5d  jb      short loc_18000CA50
0x18000ca5f  mov     r10, [rsp+10h+var_10]
0x18000ca63  mov     r11, [rsp+10h+var_8]
0x18000ca68  add     rsp, 10h
0x18000ca6c  retn
```
