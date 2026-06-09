# _alloca_probe

- ea: `0x18000b7a0`
- end: `0x18000b7ed`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004520`
- `0x1800045d4`
- `0x180004870`

## callees

- `0x18000b7a0`

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
0x18000b7a0  sub     rsp, 10h
0x18000b7a4  mov     [rsp+10h+var_10], r10
0x18000b7a8  mov     [rsp+10h+var_8], r11
0x18000b7ad  xor     r11, r11
0x18000b7b0  lea     r10, [rsp+10h+arg_0]
0x18000b7b5  sub     r10, rax
0x18000b7b8  cmovb   r10, r11
0x18000b7bc  mov     r11, gs:10h
0x18000b7c5  cmp     r10, r11
0x18000b7c8  jnb     short loc_18000B7DF
0x18000b7ca  and     r10w, 0F000h
0x18000b7d0  lea     r11, [r11-1000h]
0x18000b7d7  test    [r11], r11b
0x18000b7da  cmp     r10, r11
0x18000b7dd  jb      short loc_18000B7D0
0x18000b7df  mov     r10, [rsp+10h+var_10]
0x18000b7e3  mov     r11, [rsp+10h+var_8]
0x18000b7e8  add     rsp, 10h
0x18000b7ec  retn
```
