# sub_40A8DB

- ea: `0x40a8db`
- end: `0x40a922`
- name: `sub_40A8DB`
- size: `71`
- prototype: `_DWORD *__thiscall(size_t Size)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x407fd4`
- `0x40a1ab`
- `0x40a581`
- `0x40a6a7`
- `0x40a75a`
- `0x40a7db`
- `0x40aab8`

## callees

- `0x407f0d`
- `0x40a8db`
- `0x40b5ee`
- `0x40de64`

## pseudocode

```c
_DWORD *__thiscall sub_40A8DB(size_t Size)
{
  void *v1; // eax
  void *v2; // ecx
  _DWORD *result; // eax
  size_t v4; // [esp-4h] [ebp-4h]

  if ( Size < 0x1000 )
  {
    if ( Size )
    {
      _mm_lfence();
      return operator new(Size);
    }
    else
    {
      return 0;
    }
  }
  else
  {
    if ( Size + 35 < Size )
      sub_407F0D();
    v4 = Size + 35;
    _mm_lfence();
    v1 = operator new(v4);
    v2 = v1;
    if ( !v1 )
      _invalid_parameter_noinfo_noreturn();
    result = (_DWORD *)(((unsigned int)v1 + 35) & 0xFFFFFFE0);
    _mm_lfence();
    *(result - 1) = v2;
  }
  return result;
}

```

## disassembly

```asm
0x40a8db  cmp     ecx, 1000h
0x40a8e1  jb      short loc_40A910
0x40a8e3  lea     eax, [ecx+23h]
0x40a8e6  cmp     eax, ecx
0x40a8e8  jbe     sub_407F0D
0x40a8ee  push    eax; Size
0x40a8ef  lfence
0x40a8f2  call    ??2@YAPAXI@Z; operator new(uint)
0x40a8f7  pop     ecx
0x40a8f8  mov     ecx, eax
0x40a8fa  test    ecx, ecx
0x40a8fc  jz      short loc_40A90B
0x40a8fe  lea     eax, [ecx+23h]
0x40a901  and     eax, 0FFFFFFE0h
0x40a904  lfence
0x40a907  mov     [eax-4], ecx
0x40a90a  retn
0x40a90b  jmp     __invalid_parameter_noinfo_noreturn
0x40a910  test    ecx, ecx
0x40a912  jz      short loc_40A91F
0x40a914  push    ecx; Size
0x40a915  lfence
0x40a918  call    ??2@YAPAXI@Z; operator new(uint)
0x40a91d  pop     ecx
0x40a91e  retn
0x40a91f  xor     eax, eax
0x40a921  retn
```
