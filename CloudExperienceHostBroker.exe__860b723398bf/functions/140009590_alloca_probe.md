# _alloca_probe

- ea: `0x140009590`
- end: `0x1400095dd`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a5c`
- `0x140002b1c`
- `0x140002dc8`
- `0x140006000`
- `0x140006e78`
- `0x140007050`

## callees

- `0x140009590`

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
0x140009590  sub     rsp, 10h
0x140009594  mov     [rsp+10h+var_10], r10
0x140009598  mov     [rsp+10h+var_8], r11
0x14000959d  xor     r11, r11
0x1400095a0  lea     r10, [rsp+10h+arg_0]
0x1400095a5  sub     r10, rax
0x1400095a8  cmovb   r10, r11
0x1400095ac  mov     r11, gs:10h
0x1400095b5  cmp     r10, r11
0x1400095b8  jnb     short loc_1400095CF
0x1400095ba  and     r10w, 0F000h
0x1400095c0  lea     r11, [r11-1000h]
0x1400095c7  test    [r11], r11b
0x1400095ca  cmp     r10, r11
0x1400095cd  jb      short loc_1400095C0
0x1400095cf  mov     r10, [rsp+10h+var_10]
0x1400095d3  mov     r11, [rsp+10h+var_8]
0x1400095d8  add     rsp, 10h
0x1400095dc  retn
```
