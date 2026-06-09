# _alloca_probe

- ea: `0x18000bba0`
- end: `0x18000bbee`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005030`
- `0x180005298`
- `0x180005534`
- `0x180008e0c`
- `0x18000ad30`
- `0x18000ae40`

## callees

- `0x18000bba0`

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
0x18000bba0  sub     rsp, 10h
0x18000bba4  mov     [rsp+10h+var_10], r10
0x18000bba8  mov     [rsp+10h+var_8], r11
0x18000bbad  xor     r11, r11
0x18000bbb0  lea     r10, [rsp+10h+arg_0]
0x18000bbb5  sub     r10, rax
0x18000bbb8  cmovb   r10, r11
0x18000bbbc  mov     r11, gs:10h
0x18000bbc5  cmp     r10, r11
0x18000bbc8  jnb     short cs20
0x18000bbca  and     r10w, 0F000h
0x18000bbd0  lea     r11, [r11-1000h]
0x18000bbd7  mov     byte ptr [r11], 0
0x18000bbdb  cmp     r10, r11
0x18000bbde  jnz     short cs10
0x18000bbe0  mov     r10, [rsp+10h+var_10]
0x18000bbe4  mov     r11, [rsp+10h+var_8]
0x18000bbe9  add     rsp, 10h
0x18000bbed  retn
```
