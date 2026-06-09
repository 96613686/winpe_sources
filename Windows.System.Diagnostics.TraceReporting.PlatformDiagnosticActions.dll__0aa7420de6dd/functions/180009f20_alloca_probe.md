# _alloca_probe

- ea: `0x180009f20`
- end: `0x180009f6e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002554`
- `0x1800027d4`
- `0x180002a80`
- `0x180005ad0`
- `0x180006b50`

## callees

- `0x180009f20`

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
0x180009f20  sub     rsp, 10h
0x180009f24  mov     [rsp+10h+var_10], r10
0x180009f28  mov     [rsp+10h+var_8], r11
0x180009f2d  xor     r11, r11
0x180009f30  lea     r10, [rsp+10h+arg_0]
0x180009f35  sub     r10, rax
0x180009f38  cmovb   r10, r11
0x180009f3c  mov     r11, gs:10h
0x180009f45  cmp     r10, r11
0x180009f48  jnb     short cs20
0x180009f4a  and     r10w, 0F000h
0x180009f50  lea     r11, [r11-1000h]
0x180009f57  mov     byte ptr [r11], 0
0x180009f5b  cmp     r10, r11
0x180009f5e  jnz     short cs10
0x180009f60  mov     r10, [rsp+10h+var_10]
0x180009f64  mov     r11, [rsp+10h+var_8]
0x180009f69  add     rsp, 10h
0x180009f6d  retn
```
