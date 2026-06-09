# _alloca_probe

- ea: `0x18000ea50`
- end: `0x18000ea9d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003040`
- `0x180003184`
- `0x1800035fc`
- `0x18000387c`
- `0x180003b30`
- `0x180003ddc`
- `0x18000a2c0`

## callees

- `0x18000ea50`

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
0x18000ea50  sub     rsp, 10h
0x18000ea54  mov     [rsp+10h+var_10], r10
0x18000ea58  mov     [rsp+10h+var_8], r11
0x18000ea5d  xor     r11, r11
0x18000ea60  lea     r10, [rsp+10h+arg_0]
0x18000ea65  sub     r10, rax
0x18000ea68  cmovb   r10, r11
0x18000ea6c  mov     r11, gs:10h
0x18000ea75  cmp     r10, r11
0x18000ea78  jnb     short loc_18000EA8F
0x18000ea7a  and     r10w, 0F000h
0x18000ea80  lea     r11, [r11-1000h]
0x18000ea87  test    [r11], r11b
0x18000ea8a  cmp     r10, r11
0x18000ea8d  jb      short loc_18000EA80
0x18000ea8f  mov     r10, [rsp+10h+var_10]
0x18000ea93  mov     r11, [rsp+10h+var_8]
0x18000ea98  add     rsp, 10h
0x18000ea9c  retn
```
