# _alloca_probe

- ea: `0x180007f10`
- end: `0x180007f5e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002464`
- `0x1800026d4`
- `0x180002968`
- `0x180005830`

## callees

- `0x180007f10`

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
0x180007f10  sub     rsp, 10h
0x180007f14  mov     [rsp+10h+var_10], r10
0x180007f18  mov     [rsp+10h+var_8], r11
0x180007f1d  xor     r11, r11
0x180007f20  lea     r10, [rsp+10h+arg_0]
0x180007f25  sub     r10, rax
0x180007f28  cmovb   r10, r11
0x180007f2c  mov     r11, gs:10h
0x180007f35  cmp     r10, r11
0x180007f38  jnb     short cs20
0x180007f3a  and     r10w, 0F000h
0x180007f40  lea     r11, [r11-1000h]
0x180007f47  mov     byte ptr [r11], 0
0x180007f4b  cmp     r10, r11
0x180007f4e  jnz     short cs10
0x180007f50  mov     r10, [rsp+10h+var_10]
0x180007f54  mov     r11, [rsp+10h+var_8]
0x180007f59  add     rsp, 10h
0x180007f5d  retn
```
