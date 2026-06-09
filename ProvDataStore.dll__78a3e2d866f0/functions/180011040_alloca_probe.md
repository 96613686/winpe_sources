# _alloca_probe

- ea: `0x180011040`
- end: `0x18001108d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a3c`
- `0x180002cbc`
- `0x180002f68`
- `0x180006890`
- `0x180007e18`
- `0x180007fa4`
- `0x1800080b4`
- `0x180009750`
- `0x18000fe94`

## callees

- `0x180011040`

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
0x180011040  sub     rsp, 10h
0x180011044  mov     [rsp+10h+var_10], r10
0x180011048  mov     [rsp+10h+var_8], r11
0x18001104d  xor     r11, r11
0x180011050  lea     r10, [rsp+10h+arg_0]
0x180011055  sub     r10, rax
0x180011058  cmovb   r10, r11
0x18001105c  mov     r11, gs:10h
0x180011065  cmp     r10, r11
0x180011068  jnb     short loc_18001107F
0x18001106a  and     r10w, 0F000h
0x180011070  lea     r11, [r11-1000h]
0x180011077  test    [r11], r11b
0x18001107a  cmp     r10, r11
0x18001107d  jb      short loc_180011070
0x18001107f  mov     r10, [rsp+10h+var_10]
0x180011083  mov     r11, [rsp+10h+var_8]
0x180011088  add     rsp, 10h
0x18001108c  retn
```
