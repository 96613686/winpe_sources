# _alloca_probe

- ea: `0x140009790`
- end: `0x1400097dd`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140002684`
- `0x140002734`
- `0x140002840`
- `0x140002ad4`
- `0x140007fa0`

## callees

- `0x140009790`

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
0x140009790  sub     rsp, 10h
0x140009794  mov     [rsp+10h+var_10], r10
0x140009798  mov     [rsp+10h+var_8], r11
0x14000979d  xor     r11, r11
0x1400097a0  lea     r10, [rsp+10h+arg_0]
0x1400097a5  sub     r10, rax
0x1400097a8  cmovb   r10, r11
0x1400097ac  mov     r11, gs:10h
0x1400097b5  cmp     r10, r11
0x1400097b8  jnb     short loc_1400097CF
0x1400097ba  and     r10w, 0F000h
0x1400097c0  lea     r11, [r11-1000h]
0x1400097c7  test    [r11], r11b
0x1400097ca  cmp     r10, r11
0x1400097cd  jb      short loc_1400097C0
0x1400097cf  mov     r10, [rsp+10h+var_10]
0x1400097d3  mov     r11, [rsp+10h+var_8]
0x1400097d8  add     rsp, 10h
0x1400097dc  retn
```
