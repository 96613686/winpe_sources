# _alloca_probe

- ea: `0x140012180`
- end: `0x1400121ce`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140004174`
- `0x140005778`
- `0x140005a0c`
- `0x1400079d0`
- `0x14000ab00`
- `0x14000c770`
- `0x14000c898`

## callees

- `0x140012180`

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
0x140012180  sub     rsp, 10h
0x140012184  mov     [rsp+10h+var_10], r10
0x140012188  mov     [rsp+10h+var_8], r11
0x14001218d  xor     r11, r11
0x140012190  lea     r10, [rsp+10h+arg_0]
0x140012195  sub     r10, rax
0x140012198  cmovb   r10, r11
0x14001219c  mov     r11, gs:10h
0x1400121a5  cmp     r10, r11
0x1400121a8  jnb     short loc_1400121C0
0x1400121aa  and     r10w, 0F000h
0x1400121b0  lea     r11, [r11-1000h]
0x1400121b7  mov     byte ptr [r11], 0
0x1400121bb  cmp     r10, r11
0x1400121be  jnz     short loc_1400121B0
0x1400121c0  mov     r10, [rsp+10h+var_10]
0x1400121c4  mov     r11, [rsp+10h+var_8]
0x1400121c9  add     rsp, 10h
0x1400121cd  retn
```
