# _alloca_probe

- ea: `0x1400070a0`
- end: `0x1400070ee`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002278`
- `0x1400024e0`
- `0x14000278c`
- `0x140005830`
- `0x140005a64`
- `0x140006194`

## callees

- `0x1400070a0`

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
0x1400070a0  sub     rsp, 10h
0x1400070a4  mov     [rsp+10h+var_10], r10
0x1400070a8  mov     [rsp+10h+var_8], r11
0x1400070ad  xor     r11, r11
0x1400070b0  lea     r10, [rsp+10h+arg_0]
0x1400070b5  sub     r10, rax
0x1400070b8  cmovb   r10, r11
0x1400070bc  mov     r11, gs:10h
0x1400070c5  cmp     r10, r11
0x1400070c8  jnb     short loc_1400070E0
0x1400070ca  and     r10w, 0F000h
0x1400070d0  lea     r11, [r11-1000h]
0x1400070d7  mov     byte ptr [r11], 0
0x1400070db  cmp     r10, r11
0x1400070de  jnz     short loc_1400070D0
0x1400070e0  mov     r10, [rsp+10h+var_10]
0x1400070e4  mov     r11, [rsp+10h+var_8]
0x1400070e9  add     rsp, 10h
0x1400070ed  retn
```
