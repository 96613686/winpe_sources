# _alloca_probe

- ea: `0x180009ff0`
- end: `0x18000a03d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022f4`
- `0x180002698`
- `0x180002758`
- `0x180002a18`
- `0x180006600`

## callees

- `0x180009ff0`

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
0x180009ff0  sub     rsp, 10h
0x180009ff4  mov     [rsp+10h+var_10], r10
0x180009ff8  mov     [rsp+10h+var_8], r11
0x180009ffd  xor     r11, r11
0x18000a000  lea     r10, [rsp+10h+arg_0]
0x18000a005  sub     r10, rax
0x18000a008  cmovb   r10, r11
0x18000a00c  mov     r11, gs:10h
0x18000a015  cmp     r10, r11
0x18000a018  jnb     short loc_18000A02F
0x18000a01a  and     r10w, 0F000h
0x18000a020  lea     r11, [r11-1000h]
0x18000a027  test    [r11], r11b
0x18000a02a  cmp     r10, r11
0x18000a02d  jb      short loc_18000A020
0x18000a02f  mov     r10, [rsp+10h+var_10]
0x18000a033  mov     r11, [rsp+10h+var_8]
0x18000a038  add     rsp, 10h
0x18000a03c  retn
```
