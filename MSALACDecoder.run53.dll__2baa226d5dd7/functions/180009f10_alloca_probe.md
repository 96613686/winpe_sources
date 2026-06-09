# _alloca_probe

- ea: `0x180009f10`
- end: `0x180009f5e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000462c`
- `0x180005d08`
- `0x18000607c`
- `0x180006a18`

## callees

- `0x180009f10`

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
0x180009f10  sub     rsp, 10h
0x180009f14  mov     [rsp+10h+var_10], r10
0x180009f18  mov     [rsp+10h+var_8], r11
0x180009f1d  xor     r11, r11
0x180009f20  lea     r10, [rsp+10h+arg_0]
0x180009f25  sub     r10, rax
0x180009f28  cmovb   r10, r11
0x180009f2c  mov     r11, gs:10h
0x180009f35  cmp     r10, r11
0x180009f38  jnb     short cs20
0x180009f3a  and     r10w, 0F000h
0x180009f40  lea     r11, [r11-1000h]
0x180009f47  mov     byte ptr [r11], 0
0x180009f4b  cmp     r10, r11
0x180009f4e  jnz     short cs10
0x180009f50  mov     r10, [rsp+10h+var_10]
0x180009f54  mov     r11, [rsp+10h+var_8]
0x180009f59  add     rsp, 10h
0x180009f5d  retn
```
