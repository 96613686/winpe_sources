# _alloca_probe

- ea: `0x180009830`
- end: `0x18000987e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002580`
- `0x180004f04`
- `0x180006cb8`
- `0x1800070c0`
- `0x180007708`
- `0x180007830`

## callees

- `0x180009830`

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
0x180009830  sub     rsp, 10h
0x180009834  mov     [rsp+10h+var_10], r10
0x180009838  mov     [rsp+10h+var_8], r11
0x18000983d  xor     r11, r11
0x180009840  lea     r10, [rsp+10h+arg_0]
0x180009845  sub     r10, rax
0x180009848  cmovb   r10, r11
0x18000984c  mov     r11, gs:10h
0x180009855  cmp     r10, r11
0x180009858  jnb     short cs20
0x18000985a  and     r10w, 0F000h
0x180009860  lea     r11, [r11-1000h]
0x180009867  mov     byte ptr [r11], 0
0x18000986b  cmp     r10, r11
0x18000986e  jnz     short cs10
0x180009870  mov     r10, [rsp+10h+var_10]
0x180009874  mov     r11, [rsp+10h+var_8]
0x180009879  add     rsp, 10h
0x18000987d  retn
```
