# _alloca_probe

- ea: `0x18000b6f0`
- end: `0x18000b73d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004fb8`
- `0x18000662c`
- `0x180007f20`
- `0x180008e9c`

## callees

- `0x18000b6f0`

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
0x18000b6f0  sub     rsp, 10h
0x18000b6f4  mov     [rsp+10h+var_10], r10
0x18000b6f8  mov     [rsp+10h+var_8], r11
0x18000b6fd  xor     r11, r11
0x18000b700  lea     r10, [rsp+10h+arg_0]
0x18000b705  sub     r10, rax
0x18000b708  cmovb   r10, r11
0x18000b70c  mov     r11, gs:10h
0x18000b715  cmp     r10, r11
0x18000b718  jnb     short loc_18000B72F
0x18000b71a  and     r10w, 0F000h
0x18000b720  lea     r11, [r11-1000h]
0x18000b727  test    [r11], r11b
0x18000b72a  cmp     r10, r11
0x18000b72d  jb      short loc_18000B720
0x18000b72f  mov     r10, [rsp+10h+var_10]
0x18000b733  mov     r11, [rsp+10h+var_8]
0x18000b738  add     rsp, 10h
0x18000b73c  retn
```
