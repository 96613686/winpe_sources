# _alloca_probe

- ea: `0x18000ca80`
- end: `0x18000cace`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a74`
- `0x180002cdc`
- `0x180002f78`
- `0x1800062e0`
- `0x180009bfc`
- `0x18000c030`
- `0x18000c158`

## callees

- `0x18000ca80`

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
0x18000ca80  sub     rsp, 10h
0x18000ca84  mov     [rsp+10h+var_10], r10
0x18000ca88  mov     [rsp+10h+var_8], r11
0x18000ca8d  xor     r11, r11
0x18000ca90  lea     r10, [rsp+10h+arg_0]
0x18000ca95  sub     r10, rax
0x18000ca98  cmovb   r10, r11
0x18000ca9c  mov     r11, gs:10h
0x18000caa5  cmp     r10, r11
0x18000caa8  jnb     short cs20
0x18000caaa  and     r10w, 0F000h
0x18000cab0  lea     r11, [r11-1000h]
0x18000cab7  mov     byte ptr [r11], 0
0x18000cabb  cmp     r10, r11
0x18000cabe  jnz     short cs10
0x18000cac0  mov     r10, [rsp+10h+var_10]
0x18000cac4  mov     r11, [rsp+10h+var_8]
0x18000cac9  add     rsp, 10h
0x18000cacd  retn
```
