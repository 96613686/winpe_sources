# SymCryptFdefDivisorCreate

- ea: `0x180017d58`
- end: `0x180017db9`
- name: `SymCryptFdefDivisorCreate`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011eec`

## callees

- `0x180014df8`
- `0x180017d58`

## pseudocode

```c
_DWORD *SymCryptFdefDivisorCreate()
{
  unsigned int v0; // eax
  unsigned __int64 v1; // rdx
  _DWORD *v2; // r8
  _DWORD *v3; // r10
  int v4; // r11d
  unsigned int v5; // ecx

  v0 = SymCryptFdefSizeofIntFromDigits(1);
  v5 = v0 + 32;
  if ( v0 != -32 && v1 >= v5 )
  {
    *v2 = 1732509696;
    v3 = v2;
    v2[1] = v4;
    v2[2] = v5;
    if ( v0 )
    {
      if ( v1 - 32 >= v0 )
      {
        v2[8] = 1732837376;
        v2[9] = v4;
        v2[10] = v0;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180017d58  sub     rsp, 28h
0x180017d5c  mov     r8, rcx
0x180017d5f  xor     r10d, r10d
0x180017d62  lea     r11d, [r10+1]
0x180017d66  mov     ecx, r11d
0x180017d69  call    SymCryptFdefSizeofIntFromDigits
0x180017d6e  mov     r9d, eax
0x180017d71  lea     ecx, [r9+20h]
0x180017d75  test    ecx, ecx
0x180017d77  jz      short loc_180017DB0
0x180017d79  mov     eax, ecx
0x180017d7b  cmp     rdx, rax
0x180017d7e  jb      short loc_180017DB0
0x180017d80  mov     dword ptr [r8], 67440000h
0x180017d87  mov     r10, r8
0x180017d8a  mov     [r8+4], r11d
0x180017d8e  mov     [r8+8], ecx
0x180017d92  test    r9d, r9d
0x180017d95  jz      short loc_180017DB0
0x180017d97  add     rdx, 0FFFFFFFFFFFFFFE0h
0x180017d9b  cmp     rdx, r9
0x180017d9e  jb      short loc_180017DB0
0x180017da0  mov     dword ptr [r8+20h], 67490000h
0x180017da8  mov     [r8+24h], r11d
0x180017dac  mov     [r8+28h], r9d
0x180017db0  mov     rax, r10
0x180017db3  add     rsp, 28h
0x180017db7  retn
```
