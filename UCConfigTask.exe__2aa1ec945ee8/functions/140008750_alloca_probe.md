# _alloca_probe

- ea: `0x140008750`
- end: `0x14000879e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400024e4`
- `0x140002594`
- `0x140002828`
- `0x140005c24`
- `0x140007610`
- `0x140007818`

## callees

- `0x140008750`

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
0x140008750  sub     rsp, 10h
0x140008754  mov     [rsp+10h+var_10], r10
0x140008758  mov     [rsp+10h+var_8], r11
0x14000875d  xor     r11, r11
0x140008760  lea     r10, [rsp+10h+arg_0]
0x140008765  sub     r10, rax
0x140008768  cmovb   r10, r11
0x14000876c  mov     r11, gs:10h
0x140008775  cmp     r10, r11
0x140008778  jnb     short loc_140008790
0x14000877a  and     r10w, 0F000h
0x140008780  lea     r11, [r11-1000h]
0x140008787  mov     byte ptr [r11], 0
0x14000878b  cmp     r10, r11
0x14000878e  jnz     short loc_140008780
0x140008790  mov     r10, [rsp+10h+var_10]
0x140008794  mov     r11, [rsp+10h+var_8]
0x140008799  add     rsp, 10h
0x14000879d  retn
```
