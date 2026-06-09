# _alloca_probe

- ea: `0x18000ee80`
- end: `0x18000eece`
- name: `_alloca_probe`
- size: `78`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b08`
- `0x180002bb8`
- `0x180002cac`
- `0x1800057e0`
- `0x180005f98`
- `0x180006064`
- `0x18000bafc`

## callees

- `0x18000ee80`

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
0x18000ee80  sub     rsp, 10h
0x18000ee84  mov     [rsp+10h+var_10], r10
0x18000ee88  mov     [rsp+10h+var_8], r11
0x18000ee8d  xor     r11, r11
0x18000ee90  lea     r10, [rsp+10h+arg_0]
0x18000ee95  sub     r10, rax
0x18000ee98  cmovb   r10, r11
0x18000ee9c  mov     r11, gs:10h
0x18000eea5  cmp     r10, r11
0x18000eea8  jnb     short cs20
0x18000eeaa  and     r10w, 0F000h
0x18000eeb0  lea     r11, [r11-1000h]
0x18000eeb7  mov     byte ptr [r11], 0
0x18000eebb  cmp     r10, r11
0x18000eebe  jnz     short cs10
0x18000eec0  mov     r10, [rsp+10h+var_10]
0x18000eec4  mov     r11, [rsp+10h+var_8]
0x18000eec9  add     rsp, 10h
0x18000eecd  retn
```
