# __alloca_probe

- ea: `0x1800147a0`
- end: `0x1800147ee`
- name: `__alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000645c`
- `0x18000651c`
- `0x1800067c8`
- `0x1800091f0`
- `0x180009db4`
- `0x180009e4c`
- `0x18000a124`
- `0x18000d408`
- `0x18000ebd4`

## callees

- `0x1800147a0`

## pseudocode

```c
unsigned __int64 __fastcall _alloca_probe()
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
0x1800147a0  sub     rsp, 10h
0x1800147a4  mov     [rsp+10h+var_10], r10
0x1800147a8  mov     [rsp+10h+var_8], r11
0x1800147ad  xor     r11, r11
0x1800147b0  lea     r10, [rsp+10h+arg_0]
0x1800147b5  sub     r10, rax
0x1800147b8  cmovb   r10, r11
0x1800147bc  mov     r11, gs:10h
0x1800147c5  cmp     r10, r11
0x1800147c8  jnb     short cs20
0x1800147ca  and     r10w, 0F000h
0x1800147d0  lea     r11, [r11-1000h]
0x1800147d7  mov     byte ptr [r11], 0
0x1800147db  cmp     r10, r11
0x1800147de  jnz     short cs10
0x1800147e0  mov     r10, [rsp+10h+var_10]
0x1800147e4  mov     r11, [rsp+10h+var_8]
0x1800147e9  add     rsp, 10h
0x1800147ed  retn
```
