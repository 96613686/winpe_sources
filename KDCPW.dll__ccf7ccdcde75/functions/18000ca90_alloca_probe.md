# _alloca_probe

- ea: `0x18000ca90`
- end: `0x18000cade`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b14`
- `0x180002d7c`
- `0x180003018`
- `0x180007248`
- `0x180009014`

## callees

- `0x18000ca90`

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
0x18000ca90  sub     rsp, 10h
0x18000ca94  mov     [rsp+10h+var_10], r10
0x18000ca98  mov     [rsp+10h+var_8], r11
0x18000ca9d  xor     r11, r11
0x18000caa0  lea     r10, [rsp+10h+arg_0]
0x18000caa5  sub     r10, rax
0x18000caa8  cmovb   r10, r11
0x18000caac  mov     r11, gs:10h
0x18000cab5  cmp     r10, r11
0x18000cab8  jnb     short cs20
0x18000caba  and     r10w, 0F000h
0x18000cac0  lea     r11, [r11-1000h]
0x18000cac7  mov     byte ptr [r11], 0
0x18000cacb  cmp     r10, r11
0x18000cace  jnz     short cs10
0x18000cad0  mov     r10, [rsp+10h+var_10]
0x18000cad4  mov     r11, [rsp+10h+var_8]
0x18000cad9  add     rsp, 10h
0x18000cadd  retn
```
