# _alloca_probe

- ea: `0x180006170`
- end: `0x1800061be`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000226c`
- `0x1800024dc`
- `0x180002778`
- `0x1800055f0`
- `0x180005824`

## callees

- `0x180006170`

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
0x180006170  sub     rsp, 10h
0x180006174  mov     [rsp+10h+var_10], r10
0x180006178  mov     [rsp+10h+var_8], r11
0x18000617d  xor     r11, r11
0x180006180  lea     r10, [rsp+10h+arg_0]
0x180006185  sub     r10, rax
0x180006188  cmovb   r10, r11
0x18000618c  mov     r11, gs:10h
0x180006195  cmp     r10, r11
0x180006198  jnb     short cs20
0x18000619a  and     r10w, 0F000h
0x1800061a0  lea     r11, [r11-1000h]
0x1800061a7  mov     byte ptr [r11], 0
0x1800061ab  cmp     r10, r11
0x1800061ae  jnz     short cs10
0x1800061b0  mov     r10, [rsp+10h+var_10]
0x1800061b4  mov     r11, [rsp+10h+var_8]
0x1800061b9  add     rsp, 10h
0x1800061bd  retn
```
