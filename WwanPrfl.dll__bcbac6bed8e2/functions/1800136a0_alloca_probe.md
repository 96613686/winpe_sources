# _alloca_probe

- ea: `0x1800136a0`
- end: `0x1800136ee`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002838`
- `0x180002aa0`
- `0x180002d3c`
- `0x18000701c`
- `0x18000d6e0`
- `0x18000d808`

## callees

- `0x1800136a0`

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
0x1800136a0  sub     rsp, 10h
0x1800136a4  mov     [rsp+10h+var_10], r10
0x1800136a8  mov     [rsp+10h+var_8], r11
0x1800136ad  xor     r11, r11
0x1800136b0  lea     r10, [rsp+10h+arg_0]
0x1800136b5  sub     r10, rax
0x1800136b8  cmovb   r10, r11
0x1800136bc  mov     r11, gs:10h
0x1800136c5  cmp     r10, r11
0x1800136c8  jnb     short cs20
0x1800136ca  and     r10w, 0F000h
0x1800136d0  lea     r11, [r11-1000h]
0x1800136d7  mov     byte ptr [r11], 0
0x1800136db  cmp     r10, r11
0x1800136de  jnz     short cs10
0x1800136e0  mov     r10, [rsp+10h+var_10]
0x1800136e4  mov     r11, [rsp+10h+var_8]
0x1800136e9  add     rsp, 10h
0x1800136ed  retn
```
