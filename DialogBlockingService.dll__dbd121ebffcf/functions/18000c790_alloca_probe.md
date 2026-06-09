# _alloca_probe

- ea: `0x18000c790`
- end: `0x18000c7de`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f6c`
- `0x180003318`
- `0x180003598`
- `0x180003844`
- `0x180007e70`
- `0x180008278`

## callees

- `0x18000c790`

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
0x18000c790  sub     rsp, 10h
0x18000c794  mov     [rsp+10h+var_10], r10
0x18000c798  mov     [rsp+10h+var_8], r11
0x18000c79d  xor     r11, r11
0x18000c7a0  lea     r10, [rsp+10h+arg_0]
0x18000c7a5  sub     r10, rax
0x18000c7a8  cmovb   r10, r11
0x18000c7ac  mov     r11, gs:10h
0x18000c7b5  cmp     r10, r11
0x18000c7b8  jnb     short cs20
0x18000c7ba  and     r10w, 0F000h
0x18000c7c0  lea     r11, [r11-1000h]
0x18000c7c7  mov     byte ptr [r11], 0
0x18000c7cb  cmp     r10, r11
0x18000c7ce  jnz     short cs10
0x18000c7d0  mov     r10, [rsp+10h+var_10]
0x18000c7d4  mov     r11, [rsp+10h+var_8]
0x18000c7d9  add     rsp, 10h
0x18000c7dd  retn
```
