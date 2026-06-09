# _alloca_probe

- ea: `0x140013530`
- end: `0x14001357d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140002934`
- `0x140002b9c`
- `0x140002e38`
- `0x140010a9c`
- `0x1400120a8`

## callees

- `0x140013530`

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
0x140013530  sub     rsp, 10h
0x140013534  mov     [rsp+10h+var_10], r10
0x140013538  mov     [rsp+10h+var_8], r11
0x14001353d  xor     r11, r11
0x140013540  lea     r10, [rsp+10h+arg_0]
0x140013545  sub     r10, rax
0x140013548  cmovb   r10, r11
0x14001354c  mov     r11, gs:10h
0x140013555  cmp     r10, r11
0x140013558  jnb     short loc_14001356F
0x14001355a  and     r10w, 0F000h
0x140013560  lea     r11, [r11-1000h]
0x140013567  test    [r11], r11b
0x14001356a  cmp     r10, r11
0x14001356d  jb      short loc_140013560
0x14001356f  mov     r10, [rsp+10h+var_10]
0x140013573  mov     r11, [rsp+10h+var_8]
0x140013578  add     rsp, 10h
0x14001357c  retn
```
