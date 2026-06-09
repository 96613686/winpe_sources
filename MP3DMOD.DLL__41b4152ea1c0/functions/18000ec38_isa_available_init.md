# __isa_available_init

- ea: `0x18000ec38`
- end: `0x18000eebb`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e888`
- `0x18000e9c4`

## callees

- `0x18000ec38`

## pseudocode

```c
int __cdecl _isa_available_init()
{
  int v5; // ebp
  bool v7; // zf
  int v12; // edi
  int v13; // eax
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // r8d
  int v17; // r10d
  unsigned int v18; // r11d
  int v24; // esi
  int v25; // r9d
  unsigned __int64 v36; // rax
  int v37; // eax
  unsigned __int64 v38; // rax
  __int64 v39; // rdx
  int v41; // [rsp+40h] [rbp+8h]

  _RAX = 0;
  __asm { cpuid }
  v5 = _RAX;
  _RAX = 1;
  v7 = ((unsigned int)_RBX ^ 0x756E6547 | (unsigned int)_RCX ^ 0x6C65746E | (unsigned int)_RDX ^ 0x49656E69) == 0;
  __asm { cpuid }
  v12 = _RCX;
  if ( v7
    && ((v13 = _RAX & 0xFFF3FF0, _memset_fast_string_threshold = 0x8000, _memset_nt_threshold = -1, v13 == 67264)
     || v13 == 132704
     || v13 == 132720
     || (v14 = (unsigned int)(v13 - 198224), (unsigned int)v14 <= 0x20) && (v15 = 0x100010001LL, _bittest64(&v15, v14))) )
  {
    v16 = _favor | 1;
    _favor |= 1u;
  }
  else
  {
    v16 = _favor;
  }
  v17 = 0;
  v18 = 0;
  if ( v5 < 7 )
  {
    v25 = 0;
    v24 = 0;
  }
  else
  {
    _RAX = 7;
    __asm { cpuid }
    v24 = _RDX;
    v25 = _RBX;
    if ( (_RBX & 0x200) != 0 )
      _favor = v16 | 2;
    if ( (int)_RAX >= 1 )
    {
      _RAX = 7;
      __asm { cpuid }
      v17 = _RDX;
    }
    _RAX = 36;
    if ( v5 >= 36 )
    {
      __asm { cpuid }
      v18 = _RBX;
    }
  }
  v36 = _isa_inverted & 0xFFFFFFFFFFFFFFFEuLL;
  _isa_available = 1;
  _isa_enabled = 2;
  _isa_inverted &= ~1uLL;
  if ( (v12 & 0x100000) != 0 )
  {
    v36 &= ~0x10uLL;
    _isa_available = 2;
    _isa_inverted = v36;
    _isa_enabled = 6;
  }
  if ( (v12 & 0x8000000) != 0 )
  {
    __asm { xgetbv }
    v41 = v36;
    if ( (v12 & 0x10000000) == 0 || (v36 & 6) != 6 )
    {
LABEL_33:
      if ( (v17 & 0x200000) != 0 && (*(_QWORD *)&v41 & 0x80000LL) != 0 )
        _isa_inverted &= ~0x80uLL;
      return 0;
    }
    v37 = _isa_enabled | 8;
    _isa_available = 3;
    _isa_enabled |= 8u;
    if ( (v25 & 0x20) != 0 )
    {
      _isa_available = 5;
      _isa_enabled = v37 | 0x20;
      v38 = _isa_inverted & 0xFFFFFFFFFFFFFFFDuLL;
      _isa_inverted &= ~2uLL;
      if ( (v25 & 0xD0030000) != 0xD0030000 )
      {
LABEL_27:
        if ( (v24 & 0x800000) != 0 )
          _isa_inverted = v38 & 0xFFFFFFFFFEFFFFFFuLL;
        if ( (v17 & 0x80000) != 0 && (v41 & 0xE0) == 0xE0 )
        {
          _avx10_version = v18 & 0x400FF;
          v39 = ~(HIWORD(v18) & 6 | 0x1000029LL) & _isa_inverted;
          _isa_inverted = v39;
          if ( (unsigned __int8)v18 > 1u )
            _isa_inverted = v39 & 0xFFFFFFFFFFFFFFBFuLL;
        }
        goto LABEL_33;
      }
      if ( (v41 & 0xE0) == 0xE0 )
      {
        _isa_enabled |= 0x40u;
        v38 = _isa_inverted & 0xFFFFFFFFFFFFFFDBuLL;
        _isa_available = 6;
        _isa_inverted &= 0xFFFFFFFFFFFFFFDBuLL;
        goto LABEL_27;
      }
    }
    v38 = _isa_inverted;
    goto LABEL_27;
  }
  return 0;
}

```

## disassembly

```asm
0x18000ec38  push    rbx
0x18000ec3a  push    rbp
0x18000ec3b  push    rsi
0x18000ec3c  push    rdi
0x18000ec3d  sub     rsp, 18h
0x18000ec41  xor     eax, eax
0x18000ec43  xor     ecx, ecx
0x18000ec45  cpuid
0x18000ec47  xor     ecx, 6C65746Eh
0x18000ec4d  xor     edx, 49656E69h
0x18000ec53  or      edx, ecx
0x18000ec55  mov     ebp, eax
0x18000ec57  mov     eax, 1
0x18000ec5c  xor     ebx, 756E6547h
0x18000ec62  or      edx, ebx
0x18000ec64  lea     ecx, [rax-1]
0x18000ec67  cpuid
0x18000ec69  mov     edi, ecx
0x18000ec6b  jnz     short loc_18000ECCB
0x18000ec6d  and     eax, 0FFF3FF0h
0x18000ec72  mov     cs:__memset_fast_string_threshold, 8000h
0x18000ec7d  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x18000ec88  cmp     eax, 106C0h
0x18000ec8d  jz      short loc_18000ECB7
0x18000ec8f  cmp     eax, 20660h
0x18000ec94  jz      short loc_18000ECB7
0x18000ec96  cmp     eax, 20670h
0x18000ec9b  jz      short loc_18000ECB7
0x18000ec9d  add     eax, 0FFFCF9B0h
0x18000eca2  cmp     eax, 20h ; ' '
0x18000eca5  ja      short loc_18000ECCB
0x18000eca7  mov     rcx, 100010001h
0x18000ecb1  bt      rcx, rax
0x18000ecb5  jnb     short loc_18000ECCB
0x18000ecb7  mov     r8d, cs:__favor
0x18000ecbe  or      r8d, 1
0x18000ecc2  mov     cs:__favor, r8d
0x18000ecc9  jmp     short loc_18000ECD2
0x18000eccb  mov     r8d, cs:__favor
0x18000ecd2  xor     r10d, r10d
0x18000ecd5  xor     r11d, r11d
0x18000ecd8  cmp     ebp, 7
0x18000ecdb  jl      short loc_18000ED1F
0x18000ecdd  xor     ecx, ecx
0x18000ecdf  lea     eax, [r10+7]
0x18000ece3  cpuid
0x18000ece5  mov     esi, edx
0x18000ece7  mov     r9d, ebx
0x18000ecea  bt      ebx, 9
0x18000ecee  jnb     short loc_18000ECFB
0x18000ecf0  or      r8d, 2
0x18000ecf4  mov     cs:__favor, r8d
0x18000ecfb  cmp     eax, 1
0x18000ecfe  jl      short loc_18000ED0D
0x18000ed00  mov     eax, 7
0x18000ed05  lea     ecx, [rax-6]
0x18000ed08  cpuid
0x18000ed0a  mov     r10d, edx
0x18000ed0d  mov     eax, 24h ; '$'
0x18000ed12  cmp     ebp, eax
0x18000ed14  jl      short loc_18000ED24
0x18000ed16  xor     ecx, ecx
0x18000ed18  cpuid
0x18000ed1a  mov     r11d, ebx
0x18000ed1d  jmp     short loc_18000ED24
0x18000ed1f  xor     r9d, r9d
0x18000ed22  xor     esi, esi
0x18000ed24  mov     rax, cs:__isa_inverted
0x18000ed2b  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000ed2f  mov     cs:__isa_available, 1
0x18000ed39  mov     cs:__isa_enabled, 2
0x18000ed43  mov     cs:__isa_inverted, rax
0x18000ed4a  bt      edi, 14h
0x18000ed4e  jnb     short loc_18000ED6F
0x18000ed50  and     rax, 0FFFFFFFFFFFFFFEFh
0x18000ed54  mov     cs:__isa_available, 2
0x18000ed5e  mov     cs:__isa_inverted, rax
0x18000ed65  mov     cs:__isa_enabled, 6
0x18000ed6f  bt      edi, 1Bh
0x18000ed73  jnb     loc_18000EEB0
0x18000ed79  xor     ecx, ecx
0x18000ed7b  xgetbv
0x18000ed7e  shl     rdx, 20h
0x18000ed82  or      rdx, rax
0x18000ed85  mov     [rsp+38h+arg_0], rdx
0x18000ed8a  bt      edi, 1Ch
0x18000ed8e  jnb     loc_18000EE94
0x18000ed94  mov     rax, [rsp+38h+arg_0]
0x18000ed99  and     al, 6
0x18000ed9b  cmp     al, 6
0x18000ed9d  jnz     loc_18000EE94
0x18000eda3  mov     eax, cs:__isa_enabled
0x18000eda9  mov     dl, 0E0h
0x18000edab  or      eax, 8
0x18000edae  mov     cs:__isa_available, 3
0x18000edb8  mov     cs:__isa_enabled, eax
0x18000edbe  test    r9b, 20h
0x18000edc2  jz      short loc_18000EE26
0x18000edc4  or      eax, 20h
0x18000edc7  mov     cs:__isa_available, 5
0x18000edd1  mov     cs:__isa_enabled, eax
0x18000edd7  mov     ecx, 0D0030000h
0x18000eddc  mov     rax, cs:__isa_inverted
0x18000ede3  and     r9d, ecx
0x18000ede6  and     rax, 0FFFFFFFFFFFFFFFDh
0x18000edea  mov     cs:__isa_inverted, rax
0x18000edf1  cmp     r9d, ecx
0x18000edf4  jnz     short loc_18000EE2D
0x18000edf6  mov     rax, [rsp+38h+arg_0]
0x18000edfb  and     al, dl
0x18000edfd  cmp     al, dl
0x18000edff  jnz     short loc_18000EE26
0x18000ee01  mov     rax, cs:__isa_inverted
0x18000ee08  or      cs:__isa_enabled, 40h
0x18000ee0f  and     rax, 0FFFFFFFFFFFFFFDBh
0x18000ee13  mov     cs:__isa_available, 6
0x18000ee1d  mov     cs:__isa_inverted, rax
0x18000ee24  jmp     short loc_18000EE2D
0x18000ee26  mov     rax, cs:__isa_inverted
0x18000ee2d  bt      esi, 17h
0x18000ee31  jnb     short loc_18000EE3F
0x18000ee33  btr     rax, 18h
0x18000ee38  mov     cs:__isa_inverted, rax
0x18000ee3f  bt      r10d, 13h
0x18000ee44  jnb     short loc_18000EE94
0x18000ee46  mov     rax, [rsp+38h+arg_0]
0x18000ee4b  and     al, dl
0x18000ee4d  cmp     al, dl
0x18000ee4f  jnz     short loc_18000EE94
0x18000ee51  mov     rdx, cs:__isa_inverted
0x18000ee58  mov     eax, r11d
0x18000ee5b  shr     rax, 10h
0x18000ee5f  mov     ecx, r11d
0x18000ee62  and     eax, 6
0x18000ee65  and     ecx, 400FFh
0x18000ee6b  or      rax, 1000029h
0x18000ee71  mov     cs:__avx10_version, ecx
0x18000ee77  not     rax
0x18000ee7a  and     rdx, rax
0x18000ee7d  mov     cs:__isa_inverted, rdx
0x18000ee84  cmp     cl, 1
0x18000ee87  jbe     short loc_18000EE94
0x18000ee89  and     rdx, 0FFFFFFFFFFFFFFBFh
0x18000ee8d  mov     cs:__isa_inverted, rdx
0x18000ee94  bt      r10d, 15h
0x18000ee99  jnb     short loc_18000EEB0
0x18000ee9b  mov     rax, [rsp+38h+arg_0]
0x18000eea0  bt      rax, 13h
0x18000eea5  jnb     short loc_18000EEB0
0x18000eea7  btr     cs:__isa_inverted, 7
0x18000eeb0  xor     eax, eax
0x18000eeb2  add     rsp, 18h
0x18000eeb6  pop     rdi
0x18000eeb7  pop     rsi
0x18000eeb8  pop     rbp
0x18000eeb9  pop     rbx
0x18000eeba  retn
```
