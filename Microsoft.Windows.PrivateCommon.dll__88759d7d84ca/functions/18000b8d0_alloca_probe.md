# _alloca_probe

- ea: `0x18000b8d0`
- end: `0x18000b91e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003580`
- `0x180004f10`
- `0x180005300`
- `0x1800053e0`

## callees

- `0x18000b8d0`

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
0x18000b8d0  sub     rsp, 10h
0x18000b8d4  mov     [rsp+10h+var_10], r10
0x18000b8d8  mov     [rsp+10h+var_8], r11
0x18000b8dd  xor     r11, r11
0x18000b8e0  lea     r10, [rsp+10h+arg_0]
0x18000b8e5  sub     r10, rax
0x18000b8e8  cmovb   r10, r11
0x18000b8ec  mov     r11, gs:10h
0x18000b8f5  cmp     r10, r11
0x18000b8f8  jnb     short cs20
0x18000b8fa  and     r10w, 0F000h
0x18000b900  lea     r11, [r11-1000h]
0x18000b907  mov     byte ptr [r11], 0
0x18000b90b  cmp     r10, r11
0x18000b90e  jnz     short cs10
0x18000b910  mov     r10, [rsp+10h+var_10]
0x18000b914  mov     r11, [rsp+10h+var_8]
0x18000b919  add     rsp, 10h
0x18000b91d  retn
```
