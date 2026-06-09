# _alloca_probe

- ea: `0x18000a810`
- end: `0x18000a85e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003640`
- `0x1800038d4`
- `0x1800069a0`
- `0x180009638`

## callees

- `0x18000a810`

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
0x18000a810  sub     rsp, 10h
0x18000a814  mov     [rsp+10h+var_10], r10
0x18000a818  mov     [rsp+10h+var_8], r11
0x18000a81d  xor     r11, r11
0x18000a820  lea     r10, [rsp+10h+arg_0]
0x18000a825  sub     r10, rax
0x18000a828  cmovb   r10, r11
0x18000a82c  mov     r11, gs:10h
0x18000a835  cmp     r10, r11
0x18000a838  jnb     short cs20
0x18000a83a  and     r10w, 0F000h
0x18000a840  lea     r11, [r11-1000h]
0x18000a847  mov     byte ptr [r11], 0
0x18000a84b  cmp     r10, r11
0x18000a84e  jnz     short cs10
0x18000a850  mov     r10, [rsp+10h+var_10]
0x18000a854  mov     r11, [rsp+10h+var_8]
0x18000a859  add     rsp, 10h
0x18000a85d  retn
```
