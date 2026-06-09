# _alloca_probe

- ea: `0x18000b550`
- end: `0x18000b59e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000240c`
- `0x180002674`
- `0x180002920`
- `0x1800057f0`
- `0x180005a10`

## callees

- `0x18000b550`

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
0x18000b550  sub     rsp, 10h
0x18000b554  mov     [rsp+10h+var_10], r10
0x18000b558  mov     [rsp+10h+var_8], r11
0x18000b55d  xor     r11, r11
0x18000b560  lea     r10, [rsp+10h+arg_0]
0x18000b565  sub     r10, rax
0x18000b568  cmovb   r10, r11
0x18000b56c  mov     r11, gs:10h
0x18000b575  cmp     r10, r11
0x18000b578  jnb     short cs20
0x18000b57a  and     r10w, 0F000h
0x18000b580  lea     r11, [r11-1000h]
0x18000b587  mov     byte ptr [r11], 0
0x18000b58b  cmp     r10, r11
0x18000b58e  jnz     short cs10
0x18000b590  mov     r10, [rsp+10h+var_10]
0x18000b594  mov     r11, [rsp+10h+var_8]
0x18000b599  add     rsp, 10h
0x18000b59d  retn
```
