# _alloca_probe

- ea: `0x14000a3b0`
- end: `0x14000a3fe`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140004534`
- `0x1400045e4`
- `0x140004878`
- `0x140007ca0`
- `0x1400099c0`
- `0x140009bc8`

## callees

- `0x14000a3b0`

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
    {
      StackLimit -= 4096;
      *StackLimit = 0;
    }
    while ( v1 != StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x14000a3b0  sub     rsp, 10h
0x14000a3b4  mov     [rsp+10h+var_10], r10
0x14000a3b8  mov     [rsp+10h+var_8], r11
0x14000a3bd  xor     r11, r11
0x14000a3c0  lea     r10, [rsp+10h+arg_0]
0x14000a3c5  sub     r10, rax
0x14000a3c8  cmovb   r10, r11
0x14000a3cc  mov     r11, gs:10h
0x14000a3d5  cmp     r10, r11
0x14000a3d8  jnb     short loc_14000A3F0
0x14000a3da  and     r10w, 0F000h
0x14000a3e0  lea     r11, [r11-1000h]
0x14000a3e7  mov     byte ptr [r11], 0
0x14000a3eb  cmp     r10, r11
0x14000a3ee  jnz     short loc_14000A3E0
0x14000a3f0  mov     r10, [rsp+10h+var_10]
0x14000a3f4  mov     r11, [rsp+10h+var_8]
0x14000a3f9  add     rsp, 10h
0x14000a3fd  retn
```
