# _alloca_probe

- ea: `0x180010010`
- end: `0x18001005e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003060`
- `0x1800032d0`
- `0x180003564`
- `0x180006490`

## callees

- `0x180010010`

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
0x180010010  sub     rsp, 10h
0x180010014  mov     [rsp+10h+var_10], r10
0x180010018  mov     [rsp+10h+var_8], r11
0x18001001d  xor     r11, r11
0x180010020  lea     r10, [rsp+10h+arg_0]
0x180010025  sub     r10, rax
0x180010028  cmovb   r10, r11
0x18001002c  mov     r11, gs:10h
0x180010035  cmp     r10, r11
0x180010038  jnb     short cs20
0x18001003a  and     r10w, 0F000h
0x180010040  lea     r11, [r11-1000h]
0x180010047  mov     byte ptr [r11], 0
0x18001004b  cmp     r10, r11
0x18001004e  jnz     short cs10
0x180010050  mov     r10, [rsp+10h+var_10]
0x180010054  mov     r11, [rsp+10h+var_8]
0x180010059  add     rsp, 10h
0x18001005d  retn
```
