# __alloca_probe

- ea: `0x18008c610`
- end: `0x18008c65e`
- name: `__alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800220a0`
- `0x180024a0c`
- `0x180024e44`
- `0x1800251bc`
- `0x180025ab4`
- `0x180049cc0`
- `0x1800814a0`
- `0x180081850`
- `0x180085330`
- `0x180085d74`
- `0x180086314`
- `0x180086508`

## callees

- `0x18008c610`

## pseudocode

```c
unsigned __int64 __fastcall _alloca_probe()
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
0x18008c610  sub     rsp, 10h
0x18008c614  mov     [rsp+10h+var_10], r10
0x18008c618  mov     [rsp+10h+var_8], r11
0x18008c61d  xor     r11, r11
0x18008c620  lea     r10, [rsp+10h+arg_0]
0x18008c625  sub     r10, rax
0x18008c628  cmovb   r10, r11
0x18008c62c  mov     r11, gs:10h
0x18008c635  cmp     r10, r11
0x18008c638  jnb     short loc_18008C650
0x18008c63a  and     r10w, 0F000h
0x18008c640  lea     r11, [r11-1000h]
0x18008c647  mov     byte ptr [r11], 0
0x18008c64b  cmp     r10, r11
0x18008c64e  jnz     short loc_18008C640
0x18008c650  mov     r10, [rsp+10h+var_10]
0x18008c654  mov     r11, [rsp+10h+var_8]
0x18008c659  add     rsp, 10h
0x18008c65d  retn
```
