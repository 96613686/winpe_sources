# _alloca_probe

- ea: `0x140004c30`
- end: `0x140004c7d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001d70`
- `0x140001fe0`
- `0x14000227c`

## callees

- `0x140004c30`

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
0x140004c30  sub     rsp, 10h
0x140004c34  mov     [rsp+10h+var_10], r10
0x140004c38  mov     [rsp+10h+var_8], r11
0x140004c3d  xor     r11, r11
0x140004c40  lea     r10, [rsp+10h+arg_0]
0x140004c45  sub     r10, rax
0x140004c48  cmovb   r10, r11
0x140004c4c  mov     r11, gs:10h
0x140004c55  cmp     r10, r11
0x140004c58  jnb     short loc_140004C6F
0x140004c5a  and     r10w, 0F000h
0x140004c60  lea     r11, [r11-1000h]
0x140004c67  test    [r11], r11b
0x140004c6a  cmp     r10, r11
0x140004c6d  jb      short loc_140004C60
0x140004c6f  mov     r10, [rsp+10h+var_10]
0x140004c73  mov     r11, [rsp+10h+var_8]
0x140004c78  add     rsp, 10h
0x140004c7c  retn
```
