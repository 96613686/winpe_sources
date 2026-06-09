# _alloca_probe

- ea: `0x180010880`
- end: `0x1800108cd`
- name: `_alloca_probe`
- size: `77`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002914`
- `0x180002b7c`
- `0x180002e18`
- `0x180008020`
- `0x18000c2f0`
- `0x18000c400`

## callees

- `0x180010880`

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
0x180010880  sub     rsp, 10h
0x180010884  mov     [rsp+10h+var_10], r10
0x180010888  mov     [rsp+10h+var_8], r11
0x18001088d  xor     r11, r11
0x180010890  lea     r10, [rsp+10h+arg_0]
0x180010895  sub     r10, rax
0x180010898  cmovb   r10, r11
0x18001089c  mov     r11, gs:10h
0x1800108a5  cmp     r10, r11
0x1800108a8  jnb     short loc_1800108BF
0x1800108aa  and     r10w, 0F000h
0x1800108b0  lea     r11, [r11-1000h]
0x1800108b7  test    [r11], r11b
0x1800108ba  cmp     r10, r11
0x1800108bd  jb      short loc_1800108B0
0x1800108bf  mov     r10, [rsp+10h+var_10]
0x1800108c3  mov     r11, [rsp+10h+var_8]
0x1800108c8  add     rsp, 10h
0x1800108cc  retn
```
