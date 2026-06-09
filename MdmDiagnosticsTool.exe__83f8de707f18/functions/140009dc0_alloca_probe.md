# _alloca_probe

- ea: `0x140009dc0`
- end: `0x140009e0d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400026e0`
- `0x140002790`
- `0x14000289c`
- `0x140002b44`
- `0x140008480`

## callees

- `0x140009dc0`

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
0x140009dc0  sub     rsp, 10h
0x140009dc4  mov     [rsp+10h+var_10], r10
0x140009dc8  mov     [rsp+10h+var_8], r11
0x140009dcd  xor     r11, r11
0x140009dd0  lea     r10, [rsp+10h+arg_0]
0x140009dd5  sub     r10, rax
0x140009dd8  cmovb   r10, r11
0x140009ddc  mov     r11, gs:10h
0x140009de5  cmp     r10, r11
0x140009de8  jnb     short loc_140009DFF
0x140009dea  and     r10w, 0F000h
0x140009df0  lea     r11, [r11-1000h]
0x140009df7  test    [r11], r11b
0x140009dfa  cmp     r10, r11
0x140009dfd  jb      short loc_140009DF0
0x140009dff  mov     r10, [rsp+10h+var_10]
0x140009e03  mov     r11, [rsp+10h+var_8]
0x140009e08  add     rsp, 10h
0x140009e0c  retn
```
