# _alloca_probe

- ea: `0x18000dd00`
- end: `0x18000dd4e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180002efc`
- `0x180003298`
- `0x180003518`
- `0x1800037c4`
- `0x180006e10`
- `0x18000728c`
- `0x180009790`
- `0x18000ab88`

## callees

- `0x18000dd00`

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
0x18000dd00  sub     rsp, 10h
0x18000dd04  mov     [rsp+10h+var_10], r10
0x18000dd08  mov     [rsp+10h+var_8], r11
0x18000dd0d  xor     r11, r11
0x18000dd10  lea     r10, [rsp+10h+arg_0]
0x18000dd15  sub     r10, rax
0x18000dd18  cmovb   r10, r11
0x18000dd1c  mov     r11, gs:10h
0x18000dd25  cmp     r10, r11
0x18000dd28  jnb     short cs20
0x18000dd2a  and     r10w, 0F000h
0x18000dd30  lea     r11, [r11-1000h]
0x18000dd37  mov     byte ptr [r11], 0
0x18000dd3b  cmp     r10, r11
0x18000dd3e  jnz     short cs10
0x18000dd40  mov     r10, [rsp+10h+var_10]
0x18000dd44  mov     r11, [rsp+10h+var_8]
0x18000dd49  add     rsp, 10h
0x18000dd4d  retn
```
