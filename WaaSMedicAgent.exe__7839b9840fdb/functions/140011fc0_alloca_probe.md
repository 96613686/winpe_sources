# _alloca_probe

- ea: `0x140011fc0`
- end: `0x14001200e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140003bc8`
- `0x140003e3c`
- `0x1400040f0`
- `0x1400074f0`
- `0x140007728`
- `0x140007838`
- `0x1400087ac`
- `0x14000dcc4`
- `0x14000eb6c`

## callees

- `0x140011fc0`

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
0x140011fc0  sub     rsp, 10h
0x140011fc4  mov     [rsp+10h+var_10], r10
0x140011fc8  mov     [rsp+10h+var_8], r11
0x140011fcd  xor     r11, r11
0x140011fd0  lea     r10, [rsp+10h+arg_0]
0x140011fd5  sub     r10, rax
0x140011fd8  cmovb   r10, r11
0x140011fdc  mov     r11, gs:10h
0x140011fe5  cmp     r10, r11
0x140011fe8  jnb     short loc_140012000
0x140011fea  and     r10w, 0F000h
0x140011ff0  lea     r11, [r11-1000h]
0x140011ff7  mov     byte ptr [r11], 0
0x140011ffb  cmp     r10, r11
0x140011ffe  jnz     short loc_140011FF0
0x140012000  mov     r10, [rsp+10h+var_10]
0x140012004  mov     r11, [rsp+10h+var_8]
0x140012009  add     rsp, 10h
0x14001200d  retn
```
