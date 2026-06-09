# _alloca_probe

- ea: `0x180010e00`
- end: `0x180010e4e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180003cf4`
- `0x180003d8c`
- `0x180004390`
- `0x180004418`
- `0x1800044d8`
- `0x1800045e0`
- `0x18000488c`
- `0x180008388`
- `0x18000ab60`
- `0x18000c154`

## callees

- `0x180010e00`

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
0x180010e00  sub     rsp, 10h
0x180010e04  mov     [rsp+10h+var_10], r10
0x180010e08  mov     [rsp+10h+var_8], r11
0x180010e0d  xor     r11, r11
0x180010e10  lea     r10, [rsp+10h+arg_0]
0x180010e15  sub     r10, rax
0x180010e18  cmovb   r10, r11
0x180010e1c  mov     r11, gs:10h
0x180010e25  cmp     r10, r11
0x180010e28  jnb     short cs20
0x180010e2a  and     r10w, 0F000h
0x180010e30  lea     r11, [r11-1000h]
0x180010e37  mov     byte ptr [r11], 0
0x180010e3b  cmp     r10, r11
0x180010e3e  jnz     short cs10
0x180010e40  mov     r10, [rsp+10h+var_10]
0x180010e44  mov     r11, [rsp+10h+var_8]
0x180010e49  add     rsp, 10h
0x180010e4d  retn
```
