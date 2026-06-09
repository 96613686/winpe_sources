# _alloca_probe

- ea: `0x180011f90`
- end: `0x180011fde`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800044a4`
- `0x180004714`
- `0x1800049a8`
- `0x1800058d0`
- `0x1800080bc`
- `0x18000842c`
- `0x180009840`
- `0x18000a200`

## callees

- `0x180011f90`

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
0x180011f90  sub     rsp, 10h
0x180011f94  mov     [rsp+10h+var_10], r10
0x180011f98  mov     [rsp+10h+var_8], r11
0x180011f9d  xor     r11, r11
0x180011fa0  lea     r10, [rsp+10h+arg_0]
0x180011fa5  sub     r10, rax
0x180011fa8  cmovb   r10, r11
0x180011fac  mov     r11, gs:10h
0x180011fb5  cmp     r10, r11
0x180011fb8  jnb     short cs20
0x180011fba  and     r10w, 0F000h
0x180011fc0  lea     r11, [r11-1000h]
0x180011fc7  mov     byte ptr [r11], 0
0x180011fcb  cmp     r10, r11
0x180011fce  jnz     short cs10
0x180011fd0  mov     r10, [rsp+10h+var_10]
0x180011fd4  mov     r11, [rsp+10h+var_8]
0x180011fd9  add     rsp, 10h
0x180011fdd  retn
```
