# __alloca_probe

- ea: `0x18004cc20`
- end: `0x18004cc6e`
- name: `__alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `87`
- callee_count: `1`
- tags: ``

## callers

- `0x1800050e0`
- `0x180005524`
- `0x18000681c`
- `0x180007200`
- `0x180008d24`
- `0x18000c15c`
- `0x18000c890`
- `0x18000cf40`
- `0x18000d134`
- `0x18000d2b4`
- `0x18000d450`
- `0x18000f104`
- `0x18000f1f0`
- `0x18000f89c`
- `0x18000f9bc`
- `0x1800118ac`
- `0x180011bb8`
- `0x180013cc8`
- `0x1800151e0`
- `0x1800167e4`
- `0x1800174b0`
- `0x1800222d4`
- `0x1800248b4`
- `0x180024bd8`
- `0x1800282c8`
- `0x18002f3d0`
- `0x180030d90`
- `0x1800352f0`
- `0x180036700`
- `0x180039440`
- `0x18003c500`
- `0x18003cf48`
- `0x18003e040`
- `0x18003e310`
- `0x18003f58c`
- `0x18003f8a0`
- `0x18004293c`
- `0x180043400`
- `0x1800489f0`
- `0x18006f388`
- `0x18006f640`
- `0x180075318`
- `0x180075a04`
- `0x18007ad00`
- `0x18007b0b0`
- `0x18007cdd8`
- `0x18007d900`
- `0x18007e880`
- `0x180080d74`
- `0x180080f9c`

## callees

- `0x18004cc20`

## pseudocode

```c
unsigned __int64 __fastcall _alloca_probe()
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
0x18004cc20  sub     rsp, 10h
0x18004cc24  mov     [rsp+10h+var_10], r10
0x18004cc28  mov     [rsp+10h+var_8], r11
0x18004cc2d  xor     r11, r11
0x18004cc30  lea     r10, [rsp+10h+arg_0]
0x18004cc35  sub     r10, rax
0x18004cc38  cmovb   r10, r11
0x18004cc3c  mov     r11, gs:10h
0x18004cc45  cmp     r10, r11
0x18004cc48  jnb     short cs20
0x18004cc4a  and     r10w, 0F000h
0x18004cc50  lea     r11, [r11-1000h]
0x18004cc57  mov     byte ptr [r11], 0
0x18004cc5b  cmp     r10, r11
0x18004cc5e  jnz     short cs10
0x18004cc60  mov     r10, [rsp+10h+var_10]
0x18004cc64  mov     r11, [rsp+10h+var_8]
0x18004cc69  add     rsp, 10h
0x18004cc6d  retn
```
