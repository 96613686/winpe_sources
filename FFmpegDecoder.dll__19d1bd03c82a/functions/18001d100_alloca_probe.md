# __alloca_probe

- ea: `0x18001d100`
- end: `0x18001d14e`
- name: `__alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f20`
- `0x180003154`
- `0x1800031e8`
- `0x180003fb8`
- `0x180004910`
- `0x180011b28`
- `0x180011dd0`
- `0x180011f2c`
- `0x180015b80`

## callees

- `0x18001d100`

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
0x18001d100  sub     rsp, 10h
0x18001d104  mov     [rsp+10h+var_10], r10
0x18001d108  mov     [rsp+10h+var_8], r11
0x18001d10d  xor     r11, r11
0x18001d110  lea     r10, [rsp+10h+arg_0]
0x18001d115  sub     r10, rax
0x18001d118  cmovb   r10, r11
0x18001d11c  mov     r11, gs:10h
0x18001d125  cmp     r10, r11
0x18001d128  jnb     short cs20
0x18001d12a  and     r10w, 0F000h
0x18001d130  lea     r11, [r11-1000h]
0x18001d137  mov     byte ptr [r11], 0
0x18001d13b  cmp     r10, r11
0x18001d13e  jnz     short cs10
0x18001d140  mov     r10, [rsp+10h+var_10]
0x18001d144  mov     r11, [rsp+10h+var_8]
0x18001d149  add     rsp, 10h
0x18001d14d  retn
```
