# _alloca_probe

- ea: `0x180011d10`
- end: `0x180011d5e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ce4`
- `0x180002f64`
- `0x180003214`
- `0x1800061c0`
- `0x1800064bc`
- `0x1800065e8`
- `0x1800067fc`
- `0x1800114a0`

## callees

- `0x180011d10`

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
0x180011d10  sub     rsp, 10h
0x180011d14  mov     [rsp+10h+var_10], r10
0x180011d18  mov     [rsp+10h+var_8], r11
0x180011d1d  xor     r11, r11
0x180011d20  lea     r10, [rsp+10h+arg_0]
0x180011d25  sub     r10, rax
0x180011d28  cmovb   r10, r11
0x180011d2c  mov     r11, gs:10h
0x180011d35  cmp     r10, r11
0x180011d38  jnb     short cs20
0x180011d3a  and     r10w, 0F000h
0x180011d40  lea     r11, [r11-1000h]
0x180011d47  mov     byte ptr [r11], 0
0x180011d4b  cmp     r10, r11
0x180011d4e  jnz     short cs10
0x180011d50  mov     r10, [rsp+10h+var_10]
0x180011d54  mov     r11, [rsp+10h+var_8]
0x180011d59  add     rsp, 10h
0x180011d5d  retn
```
