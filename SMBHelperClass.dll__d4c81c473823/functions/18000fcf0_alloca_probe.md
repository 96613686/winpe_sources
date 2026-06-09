# _alloca_probe

- ea: `0x18000fcf0`
- end: `0x18000fd3d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f3c`
- `0x1800074dc`
- `0x18000784c`
- `0x180008a98`

## callees

- `0x18000fcf0`

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
0x18000fcf0  sub     rsp, 10h
0x18000fcf4  mov     [rsp+10h+var_10], r10
0x18000fcf8  mov     [rsp+10h+var_8], r11
0x18000fcfd  xor     r11, r11
0x18000fd00  lea     r10, [rsp+10h+arg_0]
0x18000fd05  sub     r10, rax
0x18000fd08  cmovb   r10, r11
0x18000fd0c  mov     r11, gs:10h
0x18000fd15  cmp     r10, r11
0x18000fd18  jnb     short loc_18000FD2F
0x18000fd1a  and     r10w, 0F000h
0x18000fd20  lea     r11, [r11-1000h]
0x18000fd27  test    [r11], r11b
0x18000fd2a  cmp     r10, r11
0x18000fd2d  jb      short loc_18000FD20
0x18000fd2f  mov     r10, [rsp+10h+var_10]
0x18000fd33  mov     r11, [rsp+10h+var_8]
0x18000fd38  add     rsp, 10h
0x18000fd3c  retn
```
