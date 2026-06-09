# _alloca_probe

- ea: `0x14000f260`
- end: `0x14000f2ae`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400049f0`
- `0x14000a530`
- `0x14000a648`
- `0x14000a8dc`
- `0x14000cf50`
- `0x14000f00c`

## callees

- `0x14000f260`

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
0x14000f260  sub     rsp, 10h
0x14000f264  mov     [rsp+10h+var_10], r10
0x14000f268  mov     [rsp+10h+var_8], r11
0x14000f26d  xor     r11, r11
0x14000f270  lea     r10, [rsp+10h+arg_0]
0x14000f275  sub     r10, rax
0x14000f278  cmovb   r10, r11
0x14000f27c  mov     r11, gs:10h
0x14000f285  cmp     r10, r11
0x14000f288  jnb     short loc_14000F2A0
0x14000f28a  and     r10w, 0F000h
0x14000f290  lea     r11, [r11-1000h]
0x14000f297  mov     byte ptr [r11], 0
0x14000f29b  cmp     r10, r11
0x14000f29e  jnz     short loc_14000F290
0x14000f2a0  mov     r10, [rsp+10h+var_10]
0x14000f2a4  mov     r11, [rsp+10h+var_8]
0x14000f2a9  add     rsp, 10h
0x14000f2ad  retn
```
