# _alloca_probe

- ea: `0x18001aff0`
- end: `0x18001b03e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000421c`
- `0x18000483c`
- `0x180004bb4`
- `0x180005394`
- `0x180016c18`
- `0x180017a54`
- `0x1800184e4`
- `0x1800185e8`
- `0x180018704`

## callees

- `0x18001aff0`

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
0x18001aff0  sub     rsp, 10h
0x18001aff4  mov     [rsp+10h+var_10], r10
0x18001aff8  mov     [rsp+10h+var_8], r11
0x18001affd  xor     r11, r11
0x18001b000  lea     r10, [rsp+10h+arg_0]
0x18001b005  sub     r10, rax
0x18001b008  cmovb   r10, r11
0x18001b00c  mov     r11, gs:10h
0x18001b015  cmp     r10, r11
0x18001b018  jnb     short cs20
0x18001b01a  and     r10w, 0F000h
0x18001b020  lea     r11, [r11-1000h]
0x18001b027  mov     byte ptr [r11], 0
0x18001b02b  cmp     r10, r11
0x18001b02e  jnz     short cs10
0x18001b030  mov     r10, [rsp+10h+var_10]
0x18001b034  mov     r11, [rsp+10h+var_8]
0x18001b039  add     rsp, 10h
0x18001b03d  retn
```
