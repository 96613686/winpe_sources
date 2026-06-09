# _alloca_probe

- ea: `0x18000b120`
- end: `0x18000b16e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ef8`
- `0x180005fdc`
- `0x180006410`
- `0x1800064d0`
- `0x18000677c`
- `0x180009f40`

## callees

- `0x18000b120`

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
0x18000b120  sub     rsp, 10h
0x18000b124  mov     [rsp+10h+var_10], r10
0x18000b128  mov     [rsp+10h+var_8], r11
0x18000b12d  xor     r11, r11
0x18000b130  lea     r10, [rsp+10h+arg_0]
0x18000b135  sub     r10, rax
0x18000b138  cmovb   r10, r11
0x18000b13c  mov     r11, gs:10h
0x18000b145  cmp     r10, r11
0x18000b148  jnb     short cs20
0x18000b14a  and     r10w, 0F000h
0x18000b150  lea     r11, [r11-1000h]
0x18000b157  mov     byte ptr [r11], 0
0x18000b15b  cmp     r10, r11
0x18000b15e  jnz     short cs10
0x18000b160  mov     r10, [rsp+10h+var_10]
0x18000b164  mov     r11, [rsp+10h+var_8]
0x18000b169  add     rsp, 10h
0x18000b16d  retn
```
