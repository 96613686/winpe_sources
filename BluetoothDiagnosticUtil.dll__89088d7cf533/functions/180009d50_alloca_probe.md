# _alloca_probe

- ea: `0x180009d50`
- end: `0x180009d9d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001df8`
- `0x180002208`
- `0x18000249c`
- `0x180002768`
- `0x180002a28`
- `0x180008670`

## callees

- `0x180009d50`

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
0x180009d50  sub     rsp, 10h
0x180009d54  mov     [rsp+10h+var_10], r10
0x180009d58  mov     [rsp+10h+var_8], r11
0x180009d5d  xor     r11, r11
0x180009d60  lea     r10, [rsp+10h+arg_0]
0x180009d65  sub     r10, rax
0x180009d68  cmovb   r10, r11
0x180009d6c  mov     r11, gs:10h
0x180009d75  cmp     r10, r11
0x180009d78  jnb     short loc_180009D8F
0x180009d7a  and     r10w, 0F000h
0x180009d80  lea     r11, [r11-1000h]
0x180009d87  test    [r11], r11b
0x180009d8a  cmp     r10, r11
0x180009d8d  jb      short loc_180009D80
0x180009d8f  mov     r10, [rsp+10h+var_10]
0x180009d93  mov     r11, [rsp+10h+var_8]
0x180009d98  add     rsp, 10h
0x180009d9c  retn
```
