# _alloca_probe

- ea: `0x18003d5a0`
- end: `0x18003d5ed`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024bc`
- `0x180002738`
- `0x1800029e8`
- `0x180007350`
- `0x1800098a0`
- `0x1800099bc`
- `0x180028ef0`

## callees

- `0x18003d5a0`

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
0x18003d5a0  sub     rsp, 10h
0x18003d5a4  mov     [rsp+10h+var_10], r10
0x18003d5a8  mov     [rsp+10h+var_8], r11
0x18003d5ad  xor     r11, r11
0x18003d5b0  lea     r10, [rsp+10h+arg_0]
0x18003d5b5  sub     r10, rax
0x18003d5b8  cmovb   r10, r11
0x18003d5bc  mov     r11, gs:10h
0x18003d5c5  cmp     r10, r11
0x18003d5c8  jnb     short loc_18003D5DF
0x18003d5ca  and     r10w, 0F000h
0x18003d5d0  lea     r11, [r11-1000h]
0x18003d5d7  test    [r11], r11b
0x18003d5da  cmp     r10, r11
0x18003d5dd  jb      short loc_18003D5D0
0x18003d5df  mov     r10, [rsp+10h+var_10]
0x18003d5e3  mov     r11, [rsp+10h+var_8]
0x18003d5e8  add     rsp, 10h
0x18003d5ec  retn
```
