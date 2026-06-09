# _alloca_probe

- ea: `0x18000d390`
- end: `0x18000d3dd`
- name: `_alloca_probe`
- size: `77`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180007450`
- `0x180008914`
- `0x180008fc4`
- `0x18000a780`
- `0x18000aa28`
- `0x18000bff0`

## callees

- `0x18000d390`

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
0x18000d390  sub     rsp, 10h
0x18000d394  mov     [rsp+10h+var_10], r10
0x18000d398  mov     [rsp+10h+var_8], r11
0x18000d39d  xor     r11, r11
0x18000d3a0  lea     r10, [rsp+10h+arg_0]
0x18000d3a5  sub     r10, rax
0x18000d3a8  cmovb   r10, r11
0x18000d3ac  mov     r11, gs:10h
0x18000d3b5  cmp     r10, r11
0x18000d3b8  jnb     short loc_18000D3CF
0x18000d3ba  and     r10w, 0F000h
0x18000d3c0  lea     r11, [r11-1000h]
0x18000d3c7  test    [r11], r11b
0x18000d3ca  cmp     r10, r11
0x18000d3cd  jb      short loc_18000D3C0
0x18000d3cf  mov     r10, [rsp+10h+var_10]
0x18000d3d3  mov     r11, [rsp+10h+var_8]
0x18000d3d8  add     rsp, 10h
0x18000d3dc  retn
```
