# __alloca_probe

- ea: `0x18006cbe0`
- end: `0x18006cc2e`
- name: `__alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180021e58`
- `0x180036288`
- `0x18003650c`
- `0x1800367c4`
- `0x180040b54`
- `0x180043f60`
- `0x18004407c`
- `0x1800578ec`
- `0x180058360`
- `0x180058ed0`
- `0x18005926c`
- `0x180059618`
- `0x180059e54`

## callees

- `0x18006cbe0`

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
0x18006cbe0  sub     rsp, 10h
0x18006cbe4  mov     [rsp+10h+var_10], r10
0x18006cbe8  mov     [rsp+10h+var_8], r11
0x18006cbed  xor     r11, r11
0x18006cbf0  lea     r10, [rsp+10h+arg_0]
0x18006cbf5  sub     r10, rax
0x18006cbf8  cmovb   r10, r11
0x18006cbfc  mov     r11, gs:10h
0x18006cc05  cmp     r10, r11
0x18006cc08  jnb     short loc_18006CC20
0x18006cc0a  and     r10w, 0F000h
0x18006cc10  lea     r11, [r11-1000h]
0x18006cc17  mov     byte ptr [r11], 0
0x18006cc1b  cmp     r10, r11
0x18006cc1e  jnz     short loc_18006CC10
0x18006cc20  mov     r10, [rsp+10h+var_10]
0x18006cc24  mov     r11, [rsp+10h+var_8]
0x18006cc29  add     rsp, 10h
0x18006cc2d  retn
```
