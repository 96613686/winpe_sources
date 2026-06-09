# _alloca_probe

- ea: `0x14000fa20`
- end: `0x14000fa6e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000581c`
- `0x140005ab0`
- `0x140006c28`
- `0x140009e24`
- `0x14000bc80`
- `0x14000bd90`

## callees

- `0x14000fa20`

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
0x14000fa20  sub     rsp, 10h
0x14000fa24  mov     [rsp+10h+var_10], r10
0x14000fa28  mov     [rsp+10h+var_8], r11
0x14000fa2d  xor     r11, r11
0x14000fa30  lea     r10, [rsp+10h+arg_0]
0x14000fa35  sub     r10, rax
0x14000fa38  cmovb   r10, r11
0x14000fa3c  mov     r11, gs:10h
0x14000fa45  cmp     r10, r11
0x14000fa48  jnb     short loc_14000FA60
0x14000fa4a  and     r10w, 0F000h
0x14000fa50  lea     r11, [r11-1000h]
0x14000fa57  mov     byte ptr [r11], 0
0x14000fa5b  cmp     r10, r11
0x14000fa5e  jnz     short loc_14000FA50
0x14000fa60  mov     r10, [rsp+10h+var_10]
0x14000fa64  mov     r11, [rsp+10h+var_8]
0x14000fa69  add     rsp, 10h
0x14000fa6d  retn
```
