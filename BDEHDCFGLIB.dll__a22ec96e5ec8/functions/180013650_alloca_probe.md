# _alloca_probe

- ea: `0x180013650`
- end: `0x18001369d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007210`
- `0x180010c58`
- `0x180010ec8`
- `0x180011164`

## callees

- `0x180013650`

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
0x180013650  sub     rsp, 10h
0x180013654  mov     [rsp+10h+var_10], r10
0x180013658  mov     [rsp+10h+var_8], r11
0x18001365d  xor     r11, r11
0x180013660  lea     r10, [rsp+10h+arg_0]
0x180013665  sub     r10, rax
0x180013668  cmovb   r10, r11
0x18001366c  mov     r11, gs:10h
0x180013675  cmp     r10, r11
0x180013678  jnb     short loc_18001368F
0x18001367a  and     r10w, 0F000h
0x180013680  lea     r11, [r11-1000h]
0x180013687  test    [r11], r11b
0x18001368a  cmp     r10, r11
0x18001368d  jb      short loc_180013680
0x18001368f  mov     r10, [rsp+10h+var_10]
0x180013693  mov     r11, [rsp+10h+var_8]
0x180013698  add     rsp, 10h
0x18001369c  retn
```
