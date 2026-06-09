# _alloca_probe

- ea: `0x180017c90`
- end: `0x180017cdd`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180009c84`
- `0x18000ac38`
- `0x18000b604`
- `0x18000cab0`
- `0x18000d4b0`
- `0x18000fc64`
- `0x18000fecc`
- `0x180010168`
- `0x180013f90`
- `0x180015d90`
- `0x180015ea0`
- `0x1800174e0`

## callees

- `0x180017c90`

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
0x180017c90  sub     rsp, 10h
0x180017c94  mov     [rsp+10h+var_10], r10
0x180017c98  mov     [rsp+10h+var_8], r11
0x180017c9d  xor     r11, r11
0x180017ca0  lea     r10, [rsp+10h+arg_0]
0x180017ca5  sub     r10, rax
0x180017ca8  cmovb   r10, r11
0x180017cac  mov     r11, gs:10h
0x180017cb5  cmp     r10, r11
0x180017cb8  jnb     short loc_180017CCF
0x180017cba  and     r10w, 0F000h
0x180017cc0  lea     r11, [r11-1000h]
0x180017cc7  test    [r11], r11b
0x180017cca  cmp     r10, r11
0x180017ccd  jb      short loc_180017CC0
0x180017ccf  mov     r10, [rsp+10h+var_10]
0x180017cd3  mov     r11, [rsp+10h+var_8]
0x180017cd8  add     rsp, 10h
0x180017cdc  retn
```
