# _alloca_probe

- ea: `0x18000cc00`
- end: `0x18000cc4e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d90`
- `0x180003000`
- `0x180003294`
- `0x1800041c0`
- `0x1800069ac`
- `0x180006d1c`
- `0x180008140`
- `0x180008b00`

## callees

- `0x18000cc00`

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
0x18000cc00  sub     rsp, 10h
0x18000cc04  mov     [rsp+10h+var_10], r10
0x18000cc08  mov     [rsp+10h+var_8], r11
0x18000cc0d  xor     r11, r11
0x18000cc10  lea     r10, [rsp+10h+arg_0]
0x18000cc15  sub     r10, rax
0x18000cc18  cmovb   r10, r11
0x18000cc1c  mov     r11, gs:10h
0x18000cc25  cmp     r10, r11
0x18000cc28  jnb     short cs20
0x18000cc2a  and     r10w, 0F000h
0x18000cc30  lea     r11, [r11-1000h]
0x18000cc37  mov     byte ptr [r11], 0
0x18000cc3b  cmp     r10, r11
0x18000cc3e  jnz     short cs10
0x18000cc40  mov     r10, [rsp+10h+var_10]
0x18000cc44  mov     r11, [rsp+10h+var_8]
0x18000cc49  add     rsp, 10h
0x18000cc4d  retn
```
