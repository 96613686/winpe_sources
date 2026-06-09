# _alloca_probe

- ea: `0x1800138d0`
- end: `0x18001391d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a84`
- `0x180002cec`
- `0x180002f88`
- `0x180006b98`
- `0x18000a270`

## callees

- `0x1800138d0`

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
0x1800138d0  sub     rsp, 10h
0x1800138d4  mov     [rsp+10h+var_10], r10
0x1800138d8  mov     [rsp+10h+var_8], r11
0x1800138dd  xor     r11, r11
0x1800138e0  lea     r10, [rsp+10h+arg_0]
0x1800138e5  sub     r10, rax
0x1800138e8  cmovb   r10, r11
0x1800138ec  mov     r11, gs:10h
0x1800138f5  cmp     r10, r11
0x1800138f8  jnb     short loc_18001390F
0x1800138fa  and     r10w, 0F000h
0x180013900  lea     r11, [r11-1000h]
0x180013907  test    [r11], r11b
0x18001390a  cmp     r10, r11
0x18001390d  jb      short loc_180013900
0x18001390f  mov     r10, [rsp+10h+var_10]
0x180013913  mov     r11, [rsp+10h+var_8]
0x180013918  add     rsp, 10h
0x18001391c  retn
```
