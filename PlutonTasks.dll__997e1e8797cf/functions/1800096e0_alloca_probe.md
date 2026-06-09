# _alloca_probe

- ea: `0x1800096e0`
- end: `0x18000972e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ce0`
- `0x180002d90`
- `0x180002e84`
- `0x18000622c`
- `0x180006d98`
- `0x180007354`
- `0x180008ef0`
- `0x1800090f8`

## callees

- `0x1800096e0`

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
0x1800096e0  sub     rsp, 10h
0x1800096e4  mov     [rsp+10h+var_10], r10
0x1800096e8  mov     [rsp+10h+var_8], r11
0x1800096ed  xor     r11, r11
0x1800096f0  lea     r10, [rsp+10h+arg_0]
0x1800096f5  sub     r10, rax
0x1800096f8  cmovb   r10, r11
0x1800096fc  mov     r11, gs:10h
0x180009705  cmp     r10, r11
0x180009708  jnb     short cs20
0x18000970a  and     r10w, 0F000h
0x180009710  lea     r11, [r11-1000h]
0x180009717  mov     byte ptr [r11], 0
0x18000971b  cmp     r10, r11
0x18000971e  jnz     short cs10
0x180009720  mov     r10, [rsp+10h+var_10]
0x180009724  mov     r11, [rsp+10h+var_8]
0x180009729  add     rsp, 10h
0x18000972d  retn
```
