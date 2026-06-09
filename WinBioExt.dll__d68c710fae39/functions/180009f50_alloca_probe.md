# _alloca_probe

- ea: `0x180009f50`
- end: `0x180009f9e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800026a8`
- `0x180002928`
- `0x180002bc4`
- `0x180005c50`
- `0x18000655c`
- `0x180008ce0`
- `0x180009b54`

## callees

- `0x180009f50`

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
0x180009f50  sub     rsp, 10h
0x180009f54  mov     [rsp+10h+var_10], r10
0x180009f58  mov     [rsp+10h+var_8], r11
0x180009f5d  xor     r11, r11
0x180009f60  lea     r10, [rsp+10h+arg_0]
0x180009f65  sub     r10, rax
0x180009f68  cmovb   r10, r11
0x180009f6c  mov     r11, gs:10h
0x180009f75  cmp     r10, r11
0x180009f78  jnb     short cs20
0x180009f7a  and     r10w, 0F000h
0x180009f80  lea     r11, [r11-1000h]
0x180009f87  mov     byte ptr [r11], 0
0x180009f8b  cmp     r10, r11
0x180009f8e  jnz     short cs10
0x180009f90  mov     r10, [rsp+10h+var_10]
0x180009f94  mov     r11, [rsp+10h+var_8]
0x180009f99  add     rsp, 10h
0x180009f9d  retn
```
