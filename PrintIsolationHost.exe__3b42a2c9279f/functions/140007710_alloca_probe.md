# _alloca_probe

- ea: `0x140007710`
- end: `0x14000775e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400029f4`
- `0x140002c64`
- `0x140002f00`
- `0x14000634c`
- `0x140006454`
- `0x1400074d0`

## callees

- `0x140007710`

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
0x140007710  sub     rsp, 10h
0x140007714  mov     [rsp+10h+var_10], r10
0x140007718  mov     [rsp+10h+var_8], r11
0x14000771d  xor     r11, r11
0x140007720  lea     r10, [rsp+10h+arg_0]
0x140007725  sub     r10, rax
0x140007728  cmovb   r10, r11
0x14000772c  mov     r11, gs:10h
0x140007735  cmp     r10, r11
0x140007738  jnb     short loc_140007750
0x14000773a  and     r10w, 0F000h
0x140007740  lea     r11, [r11-1000h]
0x140007747  mov     byte ptr [r11], 0
0x14000774b  cmp     r10, r11
0x14000774e  jnz     short loc_140007740
0x140007750  mov     r10, [rsp+10h+var_10]
0x140007754  mov     r11, [rsp+10h+var_8]
0x140007759  add     rsp, 10h
0x14000775d  retn
```
