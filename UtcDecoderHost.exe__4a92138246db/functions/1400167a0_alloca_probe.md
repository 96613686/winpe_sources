# _alloca_probe

- ea: `0x1400167a0`
- end: `0x1400167ee`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140009624`
- `0x1400099c0`
- `0x140009c40`
- `0x140009eec`
- `0x14000d4e0`
- `0x14000e318`
- `0x14000e5cc`
- `0x14000e864`
- `0x140015230`
- `0x14001638c`

## callees

- `0x1400167a0`

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
    {
      StackLimit -= 4096;
      *StackLimit = 0;
    }
    while ( v1 != StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x1400167a0  sub     rsp, 10h
0x1400167a4  mov     [rsp+10h+var_10], r10
0x1400167a8  mov     [rsp+10h+var_8], r11
0x1400167ad  xor     r11, r11
0x1400167b0  lea     r10, [rsp+10h+arg_0]
0x1400167b5  sub     r10, rax
0x1400167b8  cmovb   r10, r11
0x1400167bc  mov     r11, gs:10h
0x1400167c5  cmp     r10, r11
0x1400167c8  jnb     short loc_1400167E0
0x1400167ca  and     r10w, 0F000h
0x1400167d0  lea     r11, [r11-1000h]
0x1400167d7  mov     byte ptr [r11], 0
0x1400167db  cmp     r10, r11
0x1400167de  jnz     short loc_1400167D0
0x1400167e0  mov     r10, [rsp+10h+var_10]
0x1400167e4  mov     r11, [rsp+10h+var_8]
0x1400167e9  add     rsp, 10h
0x1400167ed  retn
```
