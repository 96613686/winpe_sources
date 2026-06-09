# _alloca_probe

- ea: `0x180010ba0`
- end: `0x180010bee`
- name: `_alloca_probe`
- size: `78`
- prototype: `unsigned __int64 __fastcall()`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ae8`
- `0x180003d68`
- `0x180004014`
- `0x180007290`
- `0x1800077ec`
- `0x180007a10`
- `0x180007acc`
- `0x180007b9c`
- `0x18000a598`
- `0x18000b264`
- `0x18000cfcc`

## callees

- `0x180010ba0`

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
0x180010ba0  sub     rsp, 10h
0x180010ba4  mov     [rsp+10h+var_10], r10
0x180010ba8  mov     [rsp+10h+var_8], r11
0x180010bad  xor     r11, r11
0x180010bb0  lea     r10, [rsp+10h+arg_0]
0x180010bb5  sub     r10, rax
0x180010bb8  cmovb   r10, r11
0x180010bbc  mov     r11, gs:10h
0x180010bc5  cmp     r10, r11
0x180010bc8  jnb     short cs20
0x180010bca  and     r10w, 0F000h
0x180010bd0  lea     r11, [r11-1000h]
0x180010bd7  mov     byte ptr [r11], 0
0x180010bdb  cmp     r10, r11
0x180010bde  jnz     short cs10
0x180010be0  mov     r10, [rsp+10h+var_10]
0x180010be4  mov     r11, [rsp+10h+var_8]
0x180010be9  add     rsp, 10h
0x180010bed  retn
```
