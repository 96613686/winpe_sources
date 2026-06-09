# _alloca_probe

- ea: `0x18000f160`
- end: `0x18000f1ad`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008218`
- `0x1800082cc`
- `0x180008560`
- `0x18000d980`

## callees

- `0x18000f160`

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
0x18000f160  sub     rsp, 10h
0x18000f164  mov     [rsp+10h+var_10], r10
0x18000f168  mov     [rsp+10h+var_8], r11
0x18000f16d  xor     r11, r11
0x18000f170  lea     r10, [rsp+10h+arg_0]
0x18000f175  sub     r10, rax
0x18000f178  cmovb   r10, r11
0x18000f17c  mov     r11, gs:10h
0x18000f185  cmp     r10, r11
0x18000f188  jnb     short loc_18000F19F
0x18000f18a  and     r10w, 0F000h
0x18000f190  lea     r11, [r11-1000h]
0x18000f197  test    [r11], r11b
0x18000f19a  cmp     r10, r11
0x18000f19d  jb      short loc_18000F190
0x18000f19f  mov     r10, [rsp+10h+var_10]
0x18000f1a3  mov     r11, [rsp+10h+var_8]
0x18000f1a8  add     rsp, 10h
0x18000f1ac  retn
```
