# _alloca_probe

- ea: `0x140010a10`
- end: `0x140010a5d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140007f20`
- `0x140008188`
- `0x140008424`
- `0x14000b888`
- `0x14000ce3c`

## callees

- `0x140010a10`

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
0x140010a10  sub     rsp, 10h
0x140010a14  mov     [rsp+10h+var_10], r10
0x140010a18  mov     [rsp+10h+var_8], r11
0x140010a1d  xor     r11, r11
0x140010a20  lea     r10, [rsp+10h+arg_0]
0x140010a25  sub     r10, rax
0x140010a28  cmovb   r10, r11
0x140010a2c  mov     r11, gs:10h
0x140010a35  cmp     r10, r11
0x140010a38  jnb     short loc_140010A4F
0x140010a3a  and     r10w, 0F000h
0x140010a40  lea     r11, [r11-1000h]
0x140010a47  test    [r11], r11b
0x140010a4a  cmp     r10, r11
0x140010a4d  jb      short loc_140010A40
0x140010a4f  mov     r10, [rsp+10h+var_10]
0x140010a53  mov     r11, [rsp+10h+var_8]
0x140010a58  add     rsp, 10h
0x140010a5c  retn
```
