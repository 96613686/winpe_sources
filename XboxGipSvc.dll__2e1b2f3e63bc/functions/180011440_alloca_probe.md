# _alloca_probe

- ea: `0x180011440`
- end: `0x18001148e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f18`
- `0x1800041ac`
- `0x180006c68`
- `0x180009350`
- `0x18000bccc`
- `0x18000f5d4`

## callees

- `0x180011440`

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
0x180011440  sub     rsp, 10h
0x180011444  mov     [rsp+10h+var_10], r10
0x180011448  mov     [rsp+10h+var_8], r11
0x18001144d  xor     r11, r11
0x180011450  lea     r10, [rsp+10h+arg_0]
0x180011455  sub     r10, rax
0x180011458  cmovb   r10, r11
0x18001145c  mov     r11, gs:10h
0x180011465  cmp     r10, r11
0x180011468  jnb     short cs20
0x18001146a  and     r10w, 0F000h
0x180011470  lea     r11, [r11-1000h]
0x180011477  mov     byte ptr [r11], 0
0x18001147b  cmp     r10, r11
0x18001147e  jnz     short cs10
0x180011480  mov     r10, [rsp+10h+var_10]
0x180011484  mov     r11, [rsp+10h+var_8]
0x180011489  add     rsp, 10h
0x18001148d  retn
```
