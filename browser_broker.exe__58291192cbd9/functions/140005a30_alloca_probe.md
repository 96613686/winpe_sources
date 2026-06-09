# _alloca_probe

- ea: `0x140005a30`
- end: `0x140005a7e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400022b4`
- `0x140002364`
- `0x140002600`

## callees

- `0x140005a30`

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
0x140005a30  sub     rsp, 10h
0x140005a34  mov     [rsp+10h+var_10], r10
0x140005a38  mov     [rsp+10h+var_8], r11
0x140005a3d  xor     r11, r11
0x140005a40  lea     r10, [rsp+10h+arg_0]
0x140005a45  sub     r10, rax
0x140005a48  cmovb   r10, r11
0x140005a4c  mov     r11, gs:10h
0x140005a55  cmp     r10, r11
0x140005a58  jnb     short loc_140005A70
0x140005a5a  and     r10w, 0F000h
0x140005a60  lea     r11, [r11-1000h]
0x140005a67  mov     byte ptr [r11], 0
0x140005a6b  cmp     r10, r11
0x140005a6e  jnz     short loc_140005A60
0x140005a70  mov     r10, [rsp+10h+var_10]
0x140005a74  mov     r11, [rsp+10h+var_8]
0x140005a79  add     rsp, 10h
0x140005a7d  retn
```
