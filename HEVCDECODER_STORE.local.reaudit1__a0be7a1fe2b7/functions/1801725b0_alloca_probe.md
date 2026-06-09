# __alloca_probe

- ea: `0x1801725b0`
- end: `0x1801725fe`
- name: `__alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180004140`
- `0x180007090`
- `0x180007b60`
- `0x180007ca0`
- `0x180021ce0`
- `0x180027060`
- `0x18005bda0`
- `0x180062a80`
- `0x1800637d0`
- `0x180068bc0`
- `0x18006f6c0`
- `0x1800c68c0`
- `0x1800caf40`
- `0x1800cc2a0`
- `0x18014f1c4`
- `0x180162650`

## callees

- `0x1801725b0`

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
0x1801725b0  sub     rsp, 10h
0x1801725b4  mov     [rsp+10h+var_10], r10
0x1801725b8  mov     [rsp+10h+var_8], r11
0x1801725bd  xor     r11, r11
0x1801725c0  lea     r10, [rsp+10h+arg_0]
0x1801725c5  sub     r10, rax
0x1801725c8  cmovb   r10, r11
0x1801725cc  mov     r11, gs:10h
0x1801725d5  cmp     r10, r11
0x1801725d8  jnb     short cs20
0x1801725da  and     r10w, 0F000h
0x1801725e0  lea     r11, [r11-1000h]
0x1801725e7  mov     byte ptr [r11], 0
0x1801725eb  cmp     r10, r11
0x1801725ee  jnz     short cs10
0x1801725f0  mov     r10, [rsp+10h+var_10]
0x1801725f4  mov     r11, [rsp+10h+var_8]
0x1801725f9  add     rsp, 10h
0x1801725fd  retn
```
