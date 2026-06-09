# _alloca_probe

- ea: `0x180007d20`
- end: `0x180007d6d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800028b4`
- `0x180002b24`
- `0x180002db8`

## callees

- `0x180007d20`

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
0x180007d20  sub     rsp, 10h
0x180007d24  mov     [rsp+10h+var_10], r10
0x180007d28  mov     [rsp+10h+var_8], r11
0x180007d2d  xor     r11, r11
0x180007d30  lea     r10, [rsp+10h+arg_0]
0x180007d35  sub     r10, rax
0x180007d38  cmovb   r10, r11
0x180007d3c  mov     r11, gs:10h
0x180007d45  cmp     r10, r11
0x180007d48  jnb     short loc_180007D5F
0x180007d4a  and     r10w, 0F000h
0x180007d50  lea     r11, [r11-1000h]
0x180007d57  test    [r11], r11b
0x180007d5a  cmp     r10, r11
0x180007d5d  jb      short loc_180007D50
0x180007d5f  mov     r10, [rsp+10h+var_10]
0x180007d63  mov     r11, [rsp+10h+var_8]
0x180007d68  add     rsp, 10h
0x180007d6c  retn
```
