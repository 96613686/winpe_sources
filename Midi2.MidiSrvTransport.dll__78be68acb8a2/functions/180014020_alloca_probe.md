# _alloca_probe

- ea: `0x180014020`
- end: `0x18001406e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180003344`
- `0x1800035b4`
- `0x180003848`
- `0x180004770`
- `0x180006f6c`
- `0x1800072dc`
- `0x180008700`
- `0x180009100`
- `0x18000cdac`

## callees

- `0x180014020`

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
0x180014020  sub     rsp, 10h
0x180014024  mov     [rsp+10h+var_10], r10
0x180014028  mov     [rsp+10h+var_8], r11
0x18001402d  xor     r11, r11
0x180014030  lea     r10, [rsp+10h+arg_0]
0x180014035  sub     r10, rax
0x180014038  cmovb   r10, r11
0x18001403c  mov     r11, gs:10h
0x180014045  cmp     r10, r11
0x180014048  jnb     short cs20
0x18001404a  and     r10w, 0F000h
0x180014050  lea     r11, [r11-1000h]
0x180014057  mov     byte ptr [r11], 0
0x18001405b  cmp     r10, r11
0x18001405e  jnz     short cs10
0x180014060  mov     r10, [rsp+10h+var_10]
0x180014064  mov     r11, [rsp+10h+var_8]
0x180014069  add     rsp, 10h
0x18001406d  retn
```
