# _alloca_probe

- ea: `0x18000caf0`
- end: `0x18000cb3e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023dc`
- `0x180002780`
- `0x180002a00`
- `0x180002cac`
- `0x18000683c`
- `0x180008b60`
- `0x180008c88`
- `0x180009158`
- `0x1800091c8`
- `0x18000a384`
- `0x18000bc98`

## callees

- `0x18000caf0`

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
0x18000caf0  sub     rsp, 10h
0x18000caf4  mov     [rsp+10h+var_10], r10
0x18000caf8  mov     [rsp+10h+var_8], r11
0x18000cafd  xor     r11, r11
0x18000cb00  lea     r10, [rsp+10h+arg_0]
0x18000cb05  sub     r10, rax
0x18000cb08  cmovb   r10, r11
0x18000cb0c  mov     r11, gs:10h
0x18000cb15  cmp     r10, r11
0x18000cb18  jnb     short cs20
0x18000cb1a  and     r10w, 0F000h
0x18000cb20  lea     r11, [r11-1000h]
0x18000cb27  mov     byte ptr [r11], 0
0x18000cb2b  cmp     r10, r11
0x18000cb2e  jnz     short cs10
0x18000cb30  mov     r10, [rsp+10h+var_10]
0x18000cb34  mov     r11, [rsp+10h+var_8]
0x18000cb39  add     rsp, 10h
0x18000cb3d  retn
```
