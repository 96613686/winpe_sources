# _alloca_probe

- ea: `0x140015b90`
- end: `0x140015bdd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000303c`
- `0x1400032a4`
- `0x140003538`
- `0x1400086cc`
- `0x14000a958`
- `0x14000ee8c`
- `0x140011518`

## callees

- `0x140015b90`

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
0x140015b90  sub     rsp, 10h
0x140015b94  mov     [rsp+10h+var_10], r10
0x140015b98  mov     [rsp+10h+var_8], r11
0x140015b9d  xor     r11, r11
0x140015ba0  lea     r10, [rsp+10h+arg_0]
0x140015ba5  sub     r10, rax
0x140015ba8  cmovb   r10, r11
0x140015bac  mov     r11, gs:10h
0x140015bb5  cmp     r10, r11
0x140015bb8  jnb     short loc_140015BCF
0x140015bba  and     r10w, 0F000h
0x140015bc0  lea     r11, [r11-1000h]
0x140015bc7  test    [r11], r11b
0x140015bca  cmp     r10, r11
0x140015bcd  jb      short loc_140015BC0
0x140015bcf  mov     r10, [rsp+10h+var_10]
0x140015bd3  mov     r11, [rsp+10h+var_8]
0x140015bd8  add     rsp, 10h
0x140015bdc  retn
```
