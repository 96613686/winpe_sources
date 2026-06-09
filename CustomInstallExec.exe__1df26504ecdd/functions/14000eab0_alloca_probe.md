# _alloca_probe

- ea: `0x14000eab0`
- end: `0x14000eafe`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140004b34`
- `0x140004be4`
- `0x140004e90`
- `0x140007990`
- `0x140007c6c`
- `0x14000804c`
- `0x14000a4f0`
- `0x14000e0e8`

## callees

- `0x14000eab0`

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
0x14000eab0  sub     rsp, 10h
0x14000eab4  mov     [rsp+10h+var_10], r10
0x14000eab8  mov     [rsp+10h+var_8], r11
0x14000eabd  xor     r11, r11
0x14000eac0  lea     r10, [rsp+10h+arg_0]
0x14000eac5  sub     r10, rax
0x14000eac8  cmovb   r10, r11
0x14000eacc  mov     r11, gs:10h
0x14000ead5  cmp     r10, r11
0x14000ead8  jnb     short loc_14000EAF0
0x14000eada  and     r10w, 0F000h
0x14000eae0  lea     r11, [r11-1000h]
0x14000eae7  mov     byte ptr [r11], 0
0x14000eaeb  cmp     r10, r11
0x14000eaee  jnz     short loc_14000EAE0
0x14000eaf0  mov     r10, [rsp+10h+var_10]
0x14000eaf4  mov     r11, [rsp+10h+var_8]
0x14000eaf9  add     rsp, 10h
0x14000eafd  retn
```
