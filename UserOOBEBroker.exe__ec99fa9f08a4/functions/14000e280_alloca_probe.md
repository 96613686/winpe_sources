# _alloca_probe

- ea: `0x14000e280`
- end: `0x14000e2cd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140002e74`
- `0x1400030f4`
- `0x1400033a0`
- `0x1400068d0`
- `0x140007690`
- `0x14000783c`
- `0x14000ba10`
- `0x14000d8b0`

## callees

- `0x14000e280`

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
0x14000e280  sub     rsp, 10h
0x14000e284  mov     [rsp+10h+var_10], r10
0x14000e288  mov     [rsp+10h+var_8], r11
0x14000e28d  xor     r11, r11
0x14000e290  lea     r10, [rsp+10h+arg_0]
0x14000e295  sub     r10, rax
0x14000e298  cmovb   r10, r11
0x14000e29c  mov     r11, gs:10h
0x14000e2a5  cmp     r10, r11
0x14000e2a8  jnb     short loc_14000E2BF
0x14000e2aa  and     r10w, 0F000h
0x14000e2b0  lea     r11, [r11-1000h]
0x14000e2b7  test    [r11], r11b
0x14000e2ba  cmp     r10, r11
0x14000e2bd  jb      short loc_14000E2B0
0x14000e2bf  mov     r10, [rsp+10h+var_10]
0x14000e2c3  mov     r11, [rsp+10h+var_8]
0x14000e2c8  add     rsp, 10h
0x14000e2cc  retn
```
