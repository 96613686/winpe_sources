# _alloca_probe

- ea: `0x1400078d0`
- end: `0x14000791e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400036fc`
- `0x1400037ac`
- `0x1400038a0`
- `0x140005da4`
- `0x140007314`

## callees

- `0x1400078d0`

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
0x1400078d0  sub     rsp, 10h
0x1400078d4  mov     [rsp+10h+var_10], r10
0x1400078d8  mov     [rsp+10h+var_8], r11
0x1400078dd  xor     r11, r11
0x1400078e0  lea     r10, [rsp+10h+arg_0]
0x1400078e5  sub     r10, rax
0x1400078e8  cmovb   r10, r11
0x1400078ec  mov     r11, gs:10h
0x1400078f5  cmp     r10, r11
0x1400078f8  jnb     short loc_140007910
0x1400078fa  and     r10w, 0F000h
0x140007900  lea     r11, [r11-1000h]
0x140007907  mov     byte ptr [r11], 0
0x14000790b  cmp     r10, r11
0x14000790e  jnz     short loc_140007900
0x140007910  mov     r10, [rsp+10h+var_10]
0x140007914  mov     r11, [rsp+10h+var_8]
0x140007919  add     rsp, 10h
0x14000791d  retn
```
