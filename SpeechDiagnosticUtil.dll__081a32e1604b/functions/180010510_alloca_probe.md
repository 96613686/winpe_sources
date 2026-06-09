# _alloca_probe

- ea: `0x180010510`
- end: `0x18001055e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003860`
- `0x180003ae0`
- `0x180003da0`
- `0x1800071fc`

## callees

- `0x180010510`

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
0x180010510  sub     rsp, 10h
0x180010514  mov     [rsp+10h+var_10], r10
0x180010518  mov     [rsp+10h+var_8], r11
0x18001051d  xor     r11, r11
0x180010520  lea     r10, [rsp+10h+arg_0]
0x180010525  sub     r10, rax
0x180010528  cmovb   r10, r11
0x18001052c  mov     r11, gs:10h
0x180010535  cmp     r10, r11
0x180010538  jnb     short cs20
0x18001053a  and     r10w, 0F000h
0x180010540  lea     r11, [r11-1000h]
0x180010547  mov     byte ptr [r11], 0
0x18001054b  cmp     r10, r11
0x18001054e  jnz     short cs10
0x180010550  mov     r10, [rsp+10h+var_10]
0x180010554  mov     r11, [rsp+10h+var_8]
0x180010559  add     rsp, 10h
0x18001055d  retn
```
