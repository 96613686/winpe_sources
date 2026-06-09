# _alloca_probe

- ea: `0x180008b80`
- end: `0x180008bce`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000335c`
- `0x1800035cc`
- `0x180003868`

## callees

- `0x180008b80`

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
0x180008b80  sub     rsp, 10h
0x180008b84  mov     [rsp+10h+var_10], r10
0x180008b88  mov     [rsp+10h+var_8], r11
0x180008b8d  xor     r11, r11
0x180008b90  lea     r10, [rsp+10h+arg_0]
0x180008b95  sub     r10, rax
0x180008b98  cmovb   r10, r11
0x180008b9c  mov     r11, gs:10h
0x180008ba5  cmp     r10, r11
0x180008ba8  jnb     short cs20
0x180008baa  and     r10w, 0F000h
0x180008bb0  lea     r11, [r11-1000h]
0x180008bb7  mov     byte ptr [r11], 0
0x180008bbb  cmp     r10, r11
0x180008bbe  jnz     short cs10
0x180008bc0  mov     r10, [rsp+10h+var_10]
0x180008bc4  mov     r11, [rsp+10h+var_8]
0x180008bc9  add     rsp, 10h
0x180008bcd  retn
```
