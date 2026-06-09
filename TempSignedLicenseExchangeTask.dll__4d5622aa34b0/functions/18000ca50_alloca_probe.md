# _alloca_probe

- ea: `0x18000ca50`
- end: `0x18000ca9e`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002008`

## callees

- `0x18000ca50`

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
0x18000ca50  sub     rsp, 10h
0x18000ca54  mov     [rsp+10h+var_10], r10
0x18000ca58  mov     [rsp+10h+var_8], r11
0x18000ca5d  xor     r11, r11
0x18000ca60  lea     r10, [rsp+10h+arg_0]
0x18000ca65  sub     r10, rax
0x18000ca68  cmovb   r10, r11
0x18000ca6c  mov     r11, gs:10h
0x18000ca75  cmp     r10, r11
0x18000ca78  jnb     short cs20
0x18000ca7a  and     r10w, 0F000h
0x18000ca80  lea     r11, [r11-1000h]
0x18000ca87  mov     byte ptr [r11], 0
0x18000ca8b  cmp     r10, r11
0x18000ca8e  jnz     short cs10
0x18000ca90  mov     r10, [rsp+10h+var_10]
0x18000ca94  mov     r11, [rsp+10h+var_8]
0x18000ca99  add     rsp, 10h
0x18000ca9d  retn
```
