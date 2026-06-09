# _alloca_probe

- ea: `0x180006a10`
- end: `0x180006a5d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800049dc`
- `0x180006050`
- `0x180006360`

## callees

- `0x180006a10`

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
0x180006a10  sub     rsp, 10h
0x180006a14  mov     [rsp+10h+var_10], r10
0x180006a18  mov     [rsp+10h+var_8], r11
0x180006a1d  xor     r11, r11
0x180006a20  lea     r10, [rsp+10h+arg_0]
0x180006a25  sub     r10, rax
0x180006a28  cmovb   r10, r11
0x180006a2c  mov     r11, gs:10h
0x180006a35  cmp     r10, r11
0x180006a38  jnb     short loc_180006A4F
0x180006a3a  and     r10w, 0F000h
0x180006a40  lea     r11, [r11-1000h]
0x180006a47  test    [r11], r11b
0x180006a4a  cmp     r10, r11
0x180006a4d  jb      short loc_180006A40
0x180006a4f  mov     r10, [rsp+10h+var_10]
0x180006a53  mov     r11, [rsp+10h+var_8]
0x180006a58  add     rsp, 10h
0x180006a5c  retn
```
