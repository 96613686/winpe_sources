# _alloca_probe

- ea: `0x1400064c0`
- end: `0x14000650e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400022b4`
- `0x140002524`
- `0x1400027b8`
- `0x140005640`

## callees

- `0x1400064c0`

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
0x1400064c0  sub     rsp, 10h
0x1400064c4  mov     [rsp+10h+var_10], r10
0x1400064c8  mov     [rsp+10h+var_8], r11
0x1400064cd  xor     r11, r11
0x1400064d0  lea     r10, [rsp+10h+arg_0]
0x1400064d5  sub     r10, rax
0x1400064d8  cmovb   r10, r11
0x1400064dc  mov     r11, gs:10h
0x1400064e5  cmp     r10, r11
0x1400064e8  jnb     short loc_140006500
0x1400064ea  and     r10w, 0F000h
0x1400064f0  lea     r11, [r11-1000h]
0x1400064f7  mov     byte ptr [r11], 0
0x1400064fb  cmp     r10, r11
0x1400064fe  jnz     short loc_1400064F0
0x140006500  mov     r10, [rsp+10h+var_10]
0x140006504  mov     r11, [rsp+10h+var_8]
0x140006509  add     rsp, 10h
0x14000650d  retn
```
