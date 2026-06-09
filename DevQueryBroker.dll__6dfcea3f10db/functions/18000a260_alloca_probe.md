# _alloca_probe

- ea: `0x18000a260`
- end: `0x18000a2ad`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004c30`
- `0x180004e98`
- `0x180005134`
- `0x180008648`
- `0x180009e08`

## callees

- `0x18000a260`

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
0x18000a260  sub     rsp, 10h
0x18000a264  mov     [rsp+10h+var_10], r10
0x18000a268  mov     [rsp+10h+var_8], r11
0x18000a26d  xor     r11, r11
0x18000a270  lea     r10, [rsp+10h+arg_0]
0x18000a275  sub     r10, rax
0x18000a278  cmovb   r10, r11
0x18000a27c  mov     r11, gs:10h
0x18000a285  cmp     r10, r11
0x18000a288  jnb     short loc_18000A29F
0x18000a28a  and     r10w, 0F000h
0x18000a290  lea     r11, [r11-1000h]
0x18000a297  test    [r11], r11b
0x18000a29a  cmp     r10, r11
0x18000a29d  jb      short loc_18000A290
0x18000a29f  mov     r10, [rsp+10h+var_10]
0x18000a2a3  mov     r11, [rsp+10h+var_8]
0x18000a2a8  add     rsp, 10h
0x18000a2ac  retn
```
