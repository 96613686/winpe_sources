# _alloca_probe

- ea: `0x18000f680`
- end: `0x18000f6cd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180002564`
- `0x1800027cc`
- `0x180002a68`
- `0x180008ed8`
- `0x18000ccc0`
- `0x18000cde8`
- `0x18000e884`
- `0x18000eb70`
- `0x18000f324`

## callees

- `0x18000f680`

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
0x18000f680  sub     rsp, 10h
0x18000f684  mov     [rsp+10h+var_10], r10
0x18000f688  mov     [rsp+10h+var_8], r11
0x18000f68d  xor     r11, r11
0x18000f690  lea     r10, [rsp+10h+arg_0]
0x18000f695  sub     r10, rax
0x18000f698  cmovb   r10, r11
0x18000f69c  mov     r11, gs:10h
0x18000f6a5  cmp     r10, r11
0x18000f6a8  jnb     short loc_18000F6BF
0x18000f6aa  and     r10w, 0F000h
0x18000f6b0  lea     r11, [r11-1000h]
0x18000f6b7  test    [r11], r11b
0x18000f6ba  cmp     r10, r11
0x18000f6bd  jb      short loc_18000F6B0
0x18000f6bf  mov     r10, [rsp+10h+var_10]
0x18000f6c3  mov     r11, [rsp+10h+var_8]
0x18000f6c8  add     rsp, 10h
0x18000f6cc  retn
```
