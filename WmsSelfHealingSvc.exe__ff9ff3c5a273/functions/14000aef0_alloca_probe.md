# _alloca_probe

- ea: `0x14000aef0`
- end: `0x14000af3d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400036d8`
- `0x140003948`

## callees

- `0x14000aef0`

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
0x14000aef0  sub     rsp, 10h
0x14000aef4  mov     [rsp+10h+var_10], r10
0x14000aef8  mov     [rsp+10h+var_8], r11
0x14000aefd  xor     r11, r11
0x14000af00  lea     r10, [rsp+10h+arg_0]
0x14000af05  sub     r10, rax
0x14000af08  cmovb   r10, r11
0x14000af0c  mov     r11, gs:10h
0x14000af15  cmp     r10, r11
0x14000af18  jnb     short loc_14000AF2F
0x14000af1a  and     r10w, 0F000h
0x14000af20  lea     r11, [r11-1000h]
0x14000af27  test    [r11], r11b
0x14000af2a  cmp     r10, r11
0x14000af2d  jb      short loc_14000AF20
0x14000af2f  mov     r10, [rsp+10h+var_10]
0x14000af33  mov     r11, [rsp+10h+var_8]
0x14000af38  add     rsp, 10h
0x14000af3c  retn
```
