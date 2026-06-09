# _alloca_probe

- ea: `0x18001a440`
- end: `0x18001a48d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a530`
- `0x18000f02c`
- `0x18000f0dc`
- `0x1800110fc`
- `0x180012b50`
- `0x180012d10`

## callees

- `0x18001a440`

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
0x18001a440  sub     rsp, 10h
0x18001a444  mov     [rsp+10h+var_10], r10
0x18001a448  mov     [rsp+10h+var_8], r11
0x18001a44d  xor     r11, r11
0x18001a450  lea     r10, [rsp+10h+arg_0]
0x18001a455  sub     r10, rax
0x18001a458  cmovb   r10, r11
0x18001a45c  mov     r11, gs:10h
0x18001a465  cmp     r10, r11
0x18001a468  jnb     short loc_18001A47F
0x18001a46a  and     r10w, 0F000h
0x18001a470  lea     r11, [r11-1000h]
0x18001a477  test    [r11], r11b
0x18001a47a  cmp     r10, r11
0x18001a47d  jb      short loc_18001A470
0x18001a47f  mov     r10, [rsp+10h+var_10]
0x18001a483  mov     r11, [rsp+10h+var_8]
0x18001a488  add     rsp, 10h
0x18001a48c  retn
```
