# __alloca_probe

- ea: `0x14000ce70`
- end: `0x14000cebe`
- name: `__alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140008e18`
- `0x14000ade8`
- `0x14000bb10`
- `0x14000bc18`
- `0x14000bd34`

## callees

- `0x14000ce70`

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
0x14000ce70  sub     rsp, 10h
0x14000ce74  mov     [rsp+10h+var_10], r10
0x14000ce78  mov     [rsp+10h+var_8], r11
0x14000ce7d  xor     r11, r11
0x14000ce80  lea     r10, [rsp+10h+arg_0]
0x14000ce85  sub     r10, rax
0x14000ce88  cmovb   r10, r11
0x14000ce8c  mov     r11, gs:10h
0x14000ce95  cmp     r10, r11
0x14000ce98  jnb     short cs20
0x14000ce9a  and     r10w, 0F000h
0x14000cea0  lea     r11, [r11-1000h]
0x14000cea7  mov     byte ptr [r11], 0
0x14000ceab  cmp     r10, r11
0x14000ceae  jnz     short cs10
0x14000ceb0  mov     r10, [rsp+10h+var_10]
0x14000ceb4  mov     r11, [rsp+10h+var_8]
0x14000ceb9  add     rsp, 10h
0x14000cebd  retn
```
