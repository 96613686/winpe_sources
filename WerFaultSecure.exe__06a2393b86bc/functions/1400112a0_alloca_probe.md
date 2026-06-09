# _alloca_probe

- ea: `0x1400112a0`
- end: `0x1400112ee`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140004850`
- `0x140004b28`
- `0x140004c40`
- `0x1400080f4`
- `0x14000835c`
- `0x14000b804`
- `0x14000e2a8`

## callees

- `0x1400112a0`

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
0x1400112a0  sub     rsp, 10h
0x1400112a4  mov     [rsp+10h+var_10], r10
0x1400112a8  mov     [rsp+10h+var_8], r11
0x1400112ad  xor     r11, r11
0x1400112b0  lea     r10, [rsp+10h+arg_0]
0x1400112b5  sub     r10, rax
0x1400112b8  cmovb   r10, r11
0x1400112bc  mov     r11, gs:10h
0x1400112c5  cmp     r10, r11
0x1400112c8  jnb     short loc_1400112E0
0x1400112ca  and     r10w, 0F000h
0x1400112d0  lea     r11, [r11-1000h]
0x1400112d7  mov     byte ptr [r11], 0
0x1400112db  cmp     r10, r11
0x1400112de  jnz     short loc_1400112D0
0x1400112e0  mov     r10, [rsp+10h+var_10]
0x1400112e4  mov     r11, [rsp+10h+var_8]
0x1400112e9  add     rsp, 10h
0x1400112ed  retn
```
