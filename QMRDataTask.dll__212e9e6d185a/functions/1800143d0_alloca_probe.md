# _alloca_probe

- ea: `0x1800143d0`
- end: `0x18001441d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ae4`
- `0x180004d4c`
- `0x180004fe8`
- `0x18000b290`
- `0x18000d5a0`
- `0x180011fd0`
- `0x1800120e0`

## callees

- `0x1800143d0`

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
0x1800143d0  sub     rsp, 10h
0x1800143d4  mov     [rsp+10h+var_10], r10
0x1800143d8  mov     [rsp+10h+var_8], r11
0x1800143dd  xor     r11, r11
0x1800143e0  lea     r10, [rsp+10h+arg_0]
0x1800143e5  sub     r10, rax
0x1800143e8  cmovb   r10, r11
0x1800143ec  mov     r11, gs:10h
0x1800143f5  cmp     r10, r11
0x1800143f8  jnb     short loc_18001440F
0x1800143fa  and     r10w, 0F000h
0x180014400  lea     r11, [r11-1000h]
0x180014407  test    [r11], r11b
0x18001440a  cmp     r10, r11
0x18001440d  jb      short loc_180014400
0x18001440f  mov     r10, [rsp+10h+var_10]
0x180014413  mov     r11, [rsp+10h+var_8]
0x180014418  add     rsp, 10h
0x18001441c  retn
```
