# _alloca_probe

- ea: `0x18000aa90`
- end: `0x18000aadd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003280`
- `0x1800053f8`
- `0x180005764`
- `0x180006184`
- `0x1800086d4`

## callees

- `0x18000aa90`

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
0x18000aa90  sub     rsp, 10h
0x18000aa94  mov     [rsp+10h+var_10], r10
0x18000aa98  mov     [rsp+10h+var_8], r11
0x18000aa9d  xor     r11, r11
0x18000aaa0  lea     r10, [rsp+10h+arg_0]
0x18000aaa5  sub     r10, rax
0x18000aaa8  cmovb   r10, r11
0x18000aaac  mov     r11, gs:10h
0x18000aab5  cmp     r10, r11
0x18000aab8  jnb     short loc_18000AACF
0x18000aaba  and     r10w, 0F000h
0x18000aac0  lea     r11, [r11-1000h]
0x18000aac7  test    [r11], r11b
0x18000aaca  cmp     r10, r11
0x18000aacd  jb      short loc_18000AAC0
0x18000aacf  mov     r10, [rsp+10h+var_10]
0x18000aad3  mov     r11, [rsp+10h+var_8]
0x18000aad8  add     rsp, 10h
0x18000aadc  retn
```
