# _alloca_probe

- ea: `0x1800173f0`
- end: `0x18001743e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000443c`
- `0x1800047c0`
- `0x180004880`
- `0x18000498c`
- `0x180004c38`
- `0x180007740`
- `0x18000a198`
- `0x18000b564`
- `0x18000c688`

## callees

- `0x1800173f0`

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
0x1800173f0  sub     rsp, 10h
0x1800173f4  mov     [rsp+10h+var_10], r10
0x1800173f8  mov     [rsp+10h+var_8], r11
0x1800173fd  xor     r11, r11
0x180017400  lea     r10, [rsp+10h+arg_0]
0x180017405  sub     r10, rax
0x180017408  cmovb   r10, r11
0x18001740c  mov     r11, gs:10h
0x180017415  cmp     r10, r11
0x180017418  jnb     short cs20
0x18001741a  and     r10w, 0F000h
0x180017420  lea     r11, [r11-1000h]
0x180017427  mov     byte ptr [r11], 0
0x18001742b  cmp     r10, r11
0x18001742e  jnz     short cs10
0x180017430  mov     r10, [rsp+10h+var_10]
0x180017434  mov     r11, [rsp+10h+var_8]
0x180017439  add     rsp, 10h
0x18001743d  retn
```
