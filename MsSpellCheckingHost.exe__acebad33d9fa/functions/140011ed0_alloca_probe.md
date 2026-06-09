# _alloca_probe

- ea: `0x140011ed0`
- end: `0x140011f1d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140002bec`
- `0x140004d28`
- `0x140005098`
- `0x140005af0`
- `0x140007144`
- `0x1400073ac`
- `0x140007648`
- `0x14000cb30`
- `0x14000f660`
- `0x14000f770`

## callees

- `0x140011ed0`

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
0x140011ed0  sub     rsp, 10h
0x140011ed4  mov     [rsp+10h+var_10], r10
0x140011ed8  mov     [rsp+10h+var_8], r11
0x140011edd  xor     r11, r11
0x140011ee0  lea     r10, [rsp+10h+arg_0]
0x140011ee5  sub     r10, rax
0x140011ee8  cmovb   r10, r11
0x140011eec  mov     r11, gs:10h
0x140011ef5  cmp     r10, r11
0x140011ef8  jnb     short loc_140011F0F
0x140011efa  and     r10w, 0F000h
0x140011f00  lea     r11, [r11-1000h]
0x140011f07  test    [r11], r11b
0x140011f0a  cmp     r10, r11
0x140011f0d  jb      short loc_140011F00
0x140011f0f  mov     r10, [rsp+10h+var_10]
0x140011f13  mov     r11, [rsp+10h+var_8]
0x140011f18  add     rsp, 10h
0x140011f1c  retn
```
