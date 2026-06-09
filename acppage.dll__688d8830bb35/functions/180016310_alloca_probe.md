# _alloca_probe

- ea: `0x180016310`
- end: `0x18001635d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800028f4`
- `0x180002b5c`
- `0x180002df8`
- `0x180006bcc`
- `0x180008438`
- `0x18000a0e4`

## callees

- `0x180016310`

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
0x180016310  sub     rsp, 10h
0x180016314  mov     [rsp+10h+var_10], r10
0x180016318  mov     [rsp+10h+var_8], r11
0x18001631d  xor     r11, r11
0x180016320  lea     r10, [rsp+10h+arg_0]
0x180016325  sub     r10, rax
0x180016328  cmovb   r10, r11
0x18001632c  mov     r11, gs:10h
0x180016335  cmp     r10, r11
0x180016338  jnb     short loc_18001634F
0x18001633a  and     r10w, 0F000h
0x180016340  lea     r11, [r11-1000h]
0x180016347  test    [r11], r11b
0x18001634a  cmp     r10, r11
0x18001634d  jb      short loc_180016340
0x18001634f  mov     r10, [rsp+10h+var_10]
0x180016353  mov     r11, [rsp+10h+var_8]
0x180016358  add     rsp, 10h
0x18001635c  retn
```
