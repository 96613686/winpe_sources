# _alloca_probe

- ea: `0x18000c5f0`
- end: `0x18000c63d`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180003220`
- `0x1800034a0`
- `0x18000374c`
- `0x180007780`
- `0x180007b68`
- `0x180007cbc`
- `0x180007eec`

## callees

- `0x18000c5f0`

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
      StackLimit -= 4096;
    while ( v1 < StackLimit );
  }
  return result;
}

```

## disassembly

```asm
0x18000c5f0  sub     rsp, 10h
0x18000c5f4  mov     [rsp+10h+var_10], r10
0x18000c5f8  mov     [rsp+10h+var_8], r11
0x18000c5fd  xor     r11, r11
0x18000c600  lea     r10, [rsp+10h+arg_0]
0x18000c605  sub     r10, rax
0x18000c608  cmovb   r10, r11
0x18000c60c  mov     r11, gs:10h
0x18000c615  cmp     r10, r11
0x18000c618  jnb     short loc_18000C62F
0x18000c61a  and     r10w, 0F000h
0x18000c620  lea     r11, [r11-1000h]
0x18000c627  test    [r11], r11b
0x18000c62a  cmp     r10, r11
0x18000c62d  jb      short loc_18000C620
0x18000c62f  mov     r10, [rsp+10h+var_10]
0x18000c633  mov     r11, [rsp+10h+var_8]
0x18000c638  add     rsp, 10h
0x18000c63c  retn
```
