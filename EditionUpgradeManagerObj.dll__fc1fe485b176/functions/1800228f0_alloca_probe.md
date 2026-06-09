# _alloca_probe

- ea: `0x1800228f0`
- end: `0x18002293e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002cfc`
- `0x180002f64`
- `0x1800031f8`
- `0x180006d88`
- `0x180008854`
- `0x180013b8c`

## callees

- `0x1800228f0`

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
0x1800228f0  sub     rsp, 10h
0x1800228f4  mov     [rsp+10h+var_10], r10
0x1800228f8  mov     [rsp+10h+var_8], r11
0x1800228fd  xor     r11, r11
0x180022900  lea     r10, [rsp+10h+arg_0]
0x180022905  sub     r10, rax
0x180022908  cmovb   r10, r11
0x18002290c  mov     r11, gs:10h
0x180022915  cmp     r10, r11
0x180022918  jnb     short cs20
0x18002291a  and     r10w, 0F000h
0x180022920  lea     r11, [r11-1000h]
0x180022927  mov     byte ptr [r11], 0
0x18002292b  cmp     r10, r11
0x18002292e  jnz     short cs10
0x180022930  mov     r10, [rsp+10h+var_10]
0x180022934  mov     r11, [rsp+10h+var_8]
0x180022939  add     rsp, 10h
0x18002293d  retn
```
