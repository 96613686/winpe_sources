# _alloca_probe

- ea: `0x14000acc0`
- end: `0x14000ad0e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140002f98`
- `0x140003208`
- `0x14000349c`
- `0x1400063a0`
- `0x140006a9c`
- `0x140006b0c`
- `0x14000980c`

## callees

- `0x14000acc0`

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
0x14000acc0  sub     rsp, 10h
0x14000acc4  mov     [rsp+10h+var_10], r10
0x14000acc8  mov     [rsp+10h+var_8], r11
0x14000accd  xor     r11, r11
0x14000acd0  lea     r10, [rsp+10h+arg_0]
0x14000acd5  sub     r10, rax
0x14000acd8  cmovb   r10, r11
0x14000acdc  mov     r11, gs:10h
0x14000ace5  cmp     r10, r11
0x14000ace8  jnb     short loc_14000AD00
0x14000acea  and     r10w, 0F000h
0x14000acf0  lea     r11, [r11-1000h]
0x14000acf7  mov     byte ptr [r11], 0
0x14000acfb  cmp     r10, r11
0x14000acfe  jnz     short loc_14000ACF0
0x14000ad00  mov     r10, [rsp+10h+var_10]
0x14000ad04  mov     r11, [rsp+10h+var_8]
0x14000ad09  add     rsp, 10h
0x14000ad0d  retn
```
