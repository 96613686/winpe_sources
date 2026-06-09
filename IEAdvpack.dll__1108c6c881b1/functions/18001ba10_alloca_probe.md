# _alloca_probe

- ea: `0x18001ba10`
- end: `0x18001ba5d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a428`
- `0x180018314`
- `0x1800183c8`
- `0x180018664`

## callees

- `0x18001ba10`

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
0x18001ba10  sub     rsp, 10h
0x18001ba14  mov     [rsp+10h+var_10], r10
0x18001ba18  mov     [rsp+10h+var_8], r11
0x18001ba1d  xor     r11, r11
0x18001ba20  lea     r10, [rsp+10h+arg_0]
0x18001ba25  sub     r10, rax
0x18001ba28  cmovb   r10, r11
0x18001ba2c  mov     r11, gs:10h
0x18001ba35  cmp     r10, r11
0x18001ba38  jnb     short loc_18001BA4F
0x18001ba3a  and     r10w, 0F000h
0x18001ba40  lea     r11, [r11-1000h]
0x18001ba47  test    [r11], r11b
0x18001ba4a  cmp     r10, r11
0x18001ba4d  jb      short loc_18001BA40
0x18001ba4f  mov     r10, [rsp+10h+var_10]
0x18001ba53  mov     r11, [rsp+10h+var_8]
0x18001ba58  add     rsp, 10h
0x18001ba5c  retn
```
