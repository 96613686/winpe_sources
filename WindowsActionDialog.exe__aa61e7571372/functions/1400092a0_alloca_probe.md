# _alloca_probe

- ea: `0x1400092a0`
- end: `0x1400092ee`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400020a8`
- `0x14000249c`
- `0x1400027a4`
- `0x140002a48`
- `0x1400078c0`

## callees

- `0x1400092a0`

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
0x1400092a0  sub     rsp, 10h
0x1400092a4  mov     [rsp+10h+var_10], r10
0x1400092a8  mov     [rsp+10h+var_8], r11
0x1400092ad  xor     r11, r11
0x1400092b0  lea     r10, [rsp+10h+arg_0]
0x1400092b5  sub     r10, rax
0x1400092b8  cmovb   r10, r11
0x1400092bc  mov     r11, gs:10h
0x1400092c5  cmp     r10, r11
0x1400092c8  jnb     short loc_1400092E0
0x1400092ca  and     r10w, 0F000h
0x1400092d0  lea     r11, [r11-1000h]
0x1400092d7  mov     byte ptr [r11], 0
0x1400092db  cmp     r10, r11
0x1400092de  jnz     short loc_1400092D0
0x1400092e0  mov     r10, [rsp+10h+var_10]
0x1400092e4  mov     r11, [rsp+10h+var_8]
0x1400092e9  add     rsp, 10h
0x1400092ed  retn
```
