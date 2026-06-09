# _alloca_probe

- ea: `0x180013050`
- end: `0x18001309d`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180006ac0`
- `0x180006e30`
- `0x18000c570`
- `0x18000e4e0`
- `0x18000ec70`
- `0x18000ed40`
- `0x18000ee10`
- `0x18000ef50`
- `0x18000f0c0`
- `0x18000f6f0`

## callees

- `0x180013050`

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
0x180013050  sub     rsp, 10h
0x180013054  mov     [rsp+10h+var_10], r10
0x180013058  mov     [rsp+10h+var_8], r11
0x18001305d  xor     r11, r11
0x180013060  lea     r10, [rsp+10h+arg_0]
0x180013065  sub     r10, rax
0x180013068  cmovb   r10, r11
0x18001306c  mov     r11, gs:10h
0x180013075  cmp     r10, r11
0x180013078  jnb     short loc_18001308F
0x18001307a  and     r10w, 0F000h
0x180013080  lea     r11, [r11-1000h]
0x180013087  test    [r11], r11b
0x18001308a  cmp     r10, r11
0x18001308d  jb      short loc_180013080
0x18001308f  mov     r10, [rsp+10h+var_10]
0x180013093  mov     r11, [rsp+10h+var_8]
0x180013098  add     rsp, 10h
0x18001309c  retn
```
