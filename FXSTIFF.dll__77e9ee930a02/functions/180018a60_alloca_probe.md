# _alloca_probe

- ea: `0x180018a60`
- end: `0x180018aad`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a130`
- `0x18000b120`
- `0x18000bb50`
- `0x18000d060`
- `0x18000da70`
- `0x18001040c`
- `0x180010688`
- `0x180010938`
- `0x180014820`
- `0x1800169e0`
- `0x180016afc`
- `0x180018270`

## callees

- `0x180018a60`

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
0x180018a60  sub     rsp, 10h
0x180018a64  mov     [rsp+10h+var_10], r10
0x180018a68  mov     [rsp+10h+var_8], r11
0x180018a6d  xor     r11, r11
0x180018a70  lea     r10, [rsp+10h+arg_0]
0x180018a75  sub     r10, rax
0x180018a78  cmovb   r10, r11
0x180018a7c  mov     r11, gs:10h
0x180018a85  cmp     r10, r11
0x180018a88  jnb     short loc_180018A9F
0x180018a8a  and     r10w, 0F000h
0x180018a90  lea     r11, [r11-1000h]
0x180018a97  test    [r11], r11b
0x180018a9a  cmp     r10, r11
0x180018a9d  jb      short loc_180018A90
0x180018a9f  mov     r10, [rsp+10h+var_10]
0x180018aa3  mov     r11, [rsp+10h+var_8]
0x180018aa8  add     rsp, 10h
0x180018aac  retn
```
