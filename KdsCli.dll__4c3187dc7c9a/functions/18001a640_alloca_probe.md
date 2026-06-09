# _alloca_probe

- ea: `0x18001a640`
- end: `0x18001a68e`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180011500`
- `0x180011768`
- `0x180011a04`
- `0x180014f88`
- `0x18001664c`

## callees

- `0x18001a640`

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
0x18001a640  sub     rsp, 10h
0x18001a644  mov     [rsp+10h+var_10], r10
0x18001a648  mov     [rsp+10h+var_8], r11
0x18001a64d  xor     r11, r11
0x18001a650  lea     r10, [rsp+10h+arg_0]
0x18001a655  sub     r10, rax
0x18001a658  cmovb   r10, r11
0x18001a65c  mov     r11, gs:10h
0x18001a665  cmp     r10, r11
0x18001a668  jnb     short cs20
0x18001a66a  and     r10w, 0F000h
0x18001a670  lea     r11, [r11-1000h]
0x18001a677  mov     byte ptr [r11], 0
0x18001a67b  cmp     r10, r11
0x18001a67e  jnz     short cs10
0x18001a680  mov     r10, [rsp+10h+var_10]
0x18001a684  mov     r11, [rsp+10h+var_8]
0x18001a689  add     rsp, 10h
0x18001a68d  retn
```
