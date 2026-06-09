# _alloca_probe

- ea: `0x180013a60`
- end: `0x180013aae`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d38`
- `0x180002fa8`
- `0x18000323c`
- `0x180006f30`
- `0x180009f70`
- `0x1800127a8`

## callees

- `0x180013a60`

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
0x180013a60  sub     rsp, 10h
0x180013a64  mov     [rsp+10h+var_10], r10
0x180013a68  mov     [rsp+10h+var_8], r11
0x180013a6d  xor     r11, r11
0x180013a70  lea     r10, [rsp+10h+arg_0]
0x180013a75  sub     r10, rax
0x180013a78  cmovb   r10, r11
0x180013a7c  mov     r11, gs:10h
0x180013a85  cmp     r10, r11
0x180013a88  jnb     short cs20
0x180013a8a  and     r10w, 0F000h
0x180013a90  lea     r11, [r11-1000h]
0x180013a97  mov     byte ptr [r11], 0
0x180013a9b  cmp     r10, r11
0x180013a9e  jnz     short cs10
0x180013aa0  mov     r10, [rsp+10h+var_10]
0x180013aa4  mov     r11, [rsp+10h+var_8]
0x180013aa9  add     rsp, 10h
0x180013aad  retn
```
