# _alloca_probe

- ea: `0x180019820`
- end: `0x18001986d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000369c`
- `0x180005528`
- `0x18000589c`
- `0x180006164`
- `0x18000b810`
- `0x18000bbe0`
- `0x18000be48`
- `0x18000c0dc`
- `0x180010a28`
- `0x180014cec`
- `0x1800163a0`

## callees

- `0x180019820`

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
      StackLimit -= 4096;
    while ( v1 < StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x180019820  sub     rsp, 10h
0x180019824  mov     [rsp+10h+var_10], r10
0x180019828  mov     [rsp+10h+var_8], r11
0x18001982d  xor     r11, r11
0x180019830  lea     r10, [rsp+10h+arg_0]
0x180019835  sub     r10, rax
0x180019838  cmovb   r10, r11
0x18001983c  mov     r11, gs:10h
0x180019845  cmp     r10, r11
0x180019848  jnb     short loc_18001985F
0x18001984a  and     r10w, 0F000h
0x180019850  lea     r11, [r11-1000h]
0x180019857  test    [r11], r11b
0x18001985a  cmp     r10, r11
0x18001985d  jb      short loc_180019850
0x18001985f  mov     r10, [rsp+10h+var_10]
0x180019863  mov     r11, [rsp+10h+var_8]
0x180019868  add     rsp, 10h
0x18001986c  retn
```
