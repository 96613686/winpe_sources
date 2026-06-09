# _alloca_probe

- ea: `0x14000a430`
- end: `0x14000a47d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002438`
- `0x1400027dc`
- `0x140002a5c`
- `0x140002d10`
- `0x140002fbc`
- `0x140006820`

## callees

- `0x14000a430`

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
0x14000a430  sub     rsp, 10h
0x14000a434  mov     [rsp+10h+var_10], r10
0x14000a438  mov     [rsp+10h+var_8], r11
0x14000a43d  xor     r11, r11
0x14000a440  lea     r10, [rsp+10h+arg_0]
0x14000a445  sub     r10, rax
0x14000a448  cmovb   r10, r11
0x14000a44c  mov     r11, gs:10h
0x14000a455  cmp     r10, r11
0x14000a458  jnb     short loc_14000A46F
0x14000a45a  and     r10w, 0F000h
0x14000a460  lea     r11, [r11-1000h]
0x14000a467  test    [r11], r11b
0x14000a46a  cmp     r10, r11
0x14000a46d  jb      short loc_14000A460
0x14000a46f  mov     r10, [rsp+10h+var_10]
0x14000a473  mov     r11, [rsp+10h+var_8]
0x14000a478  add     rsp, 10h
0x14000a47c  retn
```
