# _alloca_probe

- ea: `0x1400114d0`
- end: `0x14001151e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140002798`
- `0x140002a18`
- `0x140002cb4`
- `0x140005cb0`
- `0x140006588`

## callees

- `0x1400114d0`

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
0x1400114d0  sub     rsp, 10h
0x1400114d4  mov     [rsp+10h+var_10], r10
0x1400114d8  mov     [rsp+10h+var_8], r11
0x1400114dd  xor     r11, r11
0x1400114e0  lea     r10, [rsp+10h+arg_0]
0x1400114e5  sub     r10, rax
0x1400114e8  cmovb   r10, r11
0x1400114ec  mov     r11, gs:10h
0x1400114f5  cmp     r10, r11
0x1400114f8  jnb     short loc_140011510
0x1400114fa  and     r10w, 0F000h
0x140011500  lea     r11, [r11-1000h]
0x140011507  mov     byte ptr [r11], 0
0x14001150b  cmp     r10, r11
0x14001150e  jnz     short loc_140011500
0x140011510  mov     r10, [rsp+10h+var_10]
0x140011514  mov     r11, [rsp+10h+var_8]
0x140011519  add     rsp, 10h
0x14001151d  retn
```
