# _alloca_probe

- ea: `0x18000e3e0`
- end: `0x18000e42e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002adc`
- `0x180002d44`
- `0x180002fd8`
- `0x18000693c`
- `0x180008860`
- `0x180008988`

## callees

- `0x18000e3e0`

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
0x18000e3e0  sub     rsp, 10h
0x18000e3e4  mov     [rsp+10h+var_10], r10
0x18000e3e8  mov     [rsp+10h+var_8], r11
0x18000e3ed  xor     r11, r11
0x18000e3f0  lea     r10, [rsp+10h+arg_0]
0x18000e3f5  sub     r10, rax
0x18000e3f8  cmovb   r10, r11
0x18000e3fc  mov     r11, gs:10h
0x18000e405  cmp     r10, r11
0x18000e408  jnb     short cs20
0x18000e40a  and     r10w, 0F000h
0x18000e410  lea     r11, [r11-1000h]
0x18000e417  mov     byte ptr [r11], 0
0x18000e41b  cmp     r10, r11
0x18000e41e  jnz     short cs10
0x18000e420  mov     r10, [rsp+10h+var_10]
0x18000e424  mov     r11, [rsp+10h+var_8]
0x18000e429  add     rsp, 10h
0x18000e42d  retn
```
