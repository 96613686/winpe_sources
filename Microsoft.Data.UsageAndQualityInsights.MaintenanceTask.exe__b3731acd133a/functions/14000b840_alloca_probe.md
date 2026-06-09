# _alloca_probe

- ea: `0x14000b840`
- end: `0x14000b88e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000280c`
- `0x140002a74`
- `0x140002d10`
- `0x140006c1c`
- `0x140008d20`
- `0x140008e48`

## callees

- `0x14000b840`

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
0x14000b840  sub     rsp, 10h
0x14000b844  mov     [rsp+10h+var_10], r10
0x14000b848  mov     [rsp+10h+var_8], r11
0x14000b84d  xor     r11, r11
0x14000b850  lea     r10, [rsp+10h+arg_0]
0x14000b855  sub     r10, rax
0x14000b858  cmovb   r10, r11
0x14000b85c  mov     r11, gs:10h
0x14000b865  cmp     r10, r11
0x14000b868  jnb     short loc_14000B880
0x14000b86a  and     r10w, 0F000h
0x14000b870  lea     r11, [r11-1000h]
0x14000b877  mov     byte ptr [r11], 0
0x14000b87b  cmp     r10, r11
0x14000b87e  jnz     short loc_14000B870
0x14000b880  mov     r10, [rsp+10h+var_10]
0x14000b884  mov     r11, [rsp+10h+var_8]
0x14000b889  add     rsp, 10h
0x14000b88d  retn
```
