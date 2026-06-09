# _alloca_probe

- ea: `0x180011520`
- end: `0x18001156d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800025ec`
- `0x180002854`
- `0x180002ae8`
- `0x180005e70`
- `0x18000b830`
- `0x18000bb10`
- `0x18000d7f0`
- `0x18000eb7c`

## callees

- `0x180011520`

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
0x180011520  sub     rsp, 10h
0x180011524  mov     [rsp+10h+var_10], r10
0x180011528  mov     [rsp+10h+var_8], r11
0x18001152d  xor     r11, r11
0x180011530  lea     r10, [rsp+10h+arg_0]
0x180011535  sub     r10, rax
0x180011538  cmovb   r10, r11
0x18001153c  mov     r11, gs:10h
0x180011545  cmp     r10, r11
0x180011548  jnb     short loc_18001155F
0x18001154a  and     r10w, 0F000h
0x180011550  lea     r11, [r11-1000h]
0x180011557  test    [r11], r11b
0x18001155a  cmp     r10, r11
0x18001155d  jb      short loc_180011550
0x18001155f  mov     r10, [rsp+10h+var_10]
0x180011563  mov     r11, [rsp+10h+var_8]
0x180011568  add     rsp, 10h
0x18001156c  retn
```
