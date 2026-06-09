# _alloca_probe

- ea: `0x14000f460`
- end: `0x14000f4ae`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002340`
- `0x140004778`
- `0x140004c6c`
- `0x140004d94`

## callees

- `0x14000f460`

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
0x14000f460  sub     rsp, 10h
0x14000f464  mov     [rsp+10h+var_10], r10
0x14000f468  mov     [rsp+10h+var_8], r11
0x14000f46d  xor     r11, r11
0x14000f470  lea     r10, [rsp+10h+arg_0]
0x14000f475  sub     r10, rax
0x14000f478  cmovb   r10, r11
0x14000f47c  mov     r11, gs:10h
0x14000f485  cmp     r10, r11
0x14000f488  jnb     short loc_14000F4A0
0x14000f48a  and     r10w, 0F000h
0x14000f490  lea     r11, [r11-1000h]
0x14000f497  mov     byte ptr [r11], 0
0x14000f49b  cmp     r10, r11
0x14000f49e  jnz     short loc_14000F490
0x14000f4a0  mov     r10, [rsp+10h+var_10]
0x14000f4a4  mov     r11, [rsp+10h+var_8]
0x14000f4a9  add     rsp, 10h
0x14000f4ad  retn
```
