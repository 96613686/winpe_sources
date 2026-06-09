# _alloca_probe

- ea: `0x1800118a0`
- end: `0x1800118ee`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d10`
- `0x18000f51c`
- `0x18000f5d0`
- `0x18000f86c`

## callees

- `0x1800118a0`

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
0x1800118a0  sub     rsp, 10h
0x1800118a4  mov     [rsp+10h+var_10], r10
0x1800118a8  mov     [rsp+10h+var_8], r11
0x1800118ad  xor     r11, r11
0x1800118b0  lea     r10, [rsp+10h+arg_0]
0x1800118b5  sub     r10, rax
0x1800118b8  cmovb   r10, r11
0x1800118bc  mov     r11, gs:10h
0x1800118c5  cmp     r10, r11
0x1800118c8  jnb     short cs20
0x1800118ca  and     r10w, 0F000h
0x1800118d0  lea     r11, [r11-1000h]
0x1800118d7  mov     byte ptr [r11], 0
0x1800118db  cmp     r10, r11
0x1800118de  jnz     short cs10
0x1800118e0  mov     r10, [rsp+10h+var_10]
0x1800118e4  mov     r11, [rsp+10h+var_8]
0x1800118e9  add     rsp, 10h
0x1800118ed  retn
```
