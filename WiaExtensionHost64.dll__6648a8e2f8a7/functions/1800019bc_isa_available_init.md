# __isa_available_init

- ea: `0x1800019bc`
- end: `0x180001c3f`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015e4`
- `0x180001720`

## callees

- `0x1800019bc`

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
0x1800019bc  push    rbx
0x1800019be  push    rbp
0x1800019bf  push    rsi
0x1800019c0  push    rdi
0x1800019c1  sub     rsp, 18h
0x1800019c5  xor     eax, eax
0x1800019c7  xor     ecx, ecx
0x1800019c9  cpuid
0x1800019cb  xor     ecx, 6C65746Eh
0x1800019d1  xor     edx, 49656E69h
0x1800019d7  or      edx, ecx
0x1800019d9  mov     ebp, eax
0x1800019db  mov     eax, 1
0x1800019e0  xor     ebx, 756E6547h
0x1800019e6  or      edx, ebx
0x1800019e8  lea     ecx, [rax-1]
0x1800019eb  cpuid
0x1800019ed  mov     edi, ecx
0x1800019ef  jnz     short loc_180001A4F
0x1800019f1  and     eax, 0FFF3FF0h
0x1800019f6  mov     cs:__memset_fast_string_threshold, 8000h
0x180001a01  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001a0c  cmp     eax, 106C0h
0x180001a11  jz      short loc_180001A3B
0x180001a13  cmp     eax, 20660h
0x180001a18  jz      short loc_180001A3B
0x180001a1a  cmp     eax, 20670h
0x180001a1f  jz      short loc_180001A3B
0x180001a21  add     eax, 0FFFCF9B0h
0x180001a26  cmp     eax, 20h ; ' '
0x180001a29  ja      short loc_180001A4F
0x180001a2b  mov     rcx, 100010001h
0x180001a35  bt      rcx, rax
0x180001a39  jnb     short loc_180001A4F
0x180001a3b  mov     r8d, cs:__favor
0x180001a42  or      r8d, 1
0x180001a46  mov     cs:__favor, r8d
0x180001a4d  jmp     short loc_180001A56
0x180001a4f  mov     r8d, cs:__favor
0x180001a56  xor     r10d, r10d
0x180001a59  xor     r11d, r11d
0x180001a5c  cmp     ebp, 7
0x180001a5f  jl      short loc_180001AA3
0x180001a61  xor     ecx, ecx
0x180001a63  lea     eax, [r10+7]
0x180001a67  cpuid
0x180001a69  mov     esi, edx
0x180001a6b  mov     r9d, ebx
0x180001a6e  bt      ebx, 9
0x180001a72  jnb     short loc_180001A7F
0x180001a74  or      r8d, 2
0x180001a78  mov     cs:__favor, r8d
0x180001a7f  cmp     eax, 1
0x180001a82  jl      short loc_180001A91
0x180001a84  mov     eax, 7
0x180001a89  lea     ecx, [rax-6]
0x180001a8c  cpuid
0x180001a8e  mov     r10d, edx
0x180001a91  mov     eax, 24h ; '$'
0x180001a96  cmp     ebp, eax
0x180001a98  jl      short loc_180001AA8
0x180001a9a  xor     ecx, ecx
0x180001a9c  cpuid
0x180001a9e  mov     r11d, ebx
0x180001aa1  jmp     short loc_180001AA8
0x180001aa3  xor     r9d, r9d
0x180001aa6  xor     esi, esi
0x180001aa8  mov     rax, cs:__isa_inverted
0x180001aaf  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001ab3  mov     cs:__isa_available, 1
0x180001abd  mov     cs:__isa_enabled, 2
0x180001ac7  mov     cs:__isa_inverted, rax
0x180001ace  bt      edi, 14h
0x180001ad2  jnb     short loc_180001AF3
0x180001ad4  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001ad8  mov     cs:__isa_available, 2
0x180001ae2  mov     cs:__isa_inverted, rax
0x180001ae9  mov     cs:__isa_enabled, 6
0x180001af3  bt      edi, 1Bh
0x180001af7  jnb     loc_180001C34
0x180001afd  xor     ecx, ecx
0x180001aff  xgetbv
0x180001b02  shl     rdx, 20h
0x180001b06  or      rdx, rax
0x180001b09  mov     [rsp+38h+arg_0], rdx
0x180001b0e  bt      edi, 1Ch
0x180001b12  jnb     loc_180001C18
0x180001b18  mov     rax, [rsp+38h+arg_0]
0x180001b1d  and     al, 6
0x180001b1f  cmp     al, 6
0x180001b21  jnz     loc_180001C18
0x180001b27  mov     eax, cs:__isa_enabled
0x180001b2d  mov     dl, 0E0h
0x180001b2f  or      eax, 8
0x180001b32  mov     cs:__isa_available, 3
0x180001b3c  mov     cs:__isa_enabled, eax
0x180001b42  test    r9b, 20h
0x180001b46  jz      short loc_180001BAA
0x180001b48  or      eax, 20h
0x180001b4b  mov     cs:__isa_available, 5
0x180001b55  mov     cs:__isa_enabled, eax
0x180001b5b  mov     ecx, 0D0030000h
0x180001b60  mov     rax, cs:__isa_inverted
0x180001b67  and     r9d, ecx
0x180001b6a  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001b6e  mov     cs:__isa_inverted, rax
0x180001b75  cmp     r9d, ecx
0x180001b78  jnz     short loc_180001BB1
0x180001b7a  mov     rax, [rsp+38h+arg_0]
0x180001b7f  and     al, dl
0x180001b81  cmp     al, dl
0x180001b83  jnz     short loc_180001BAA
0x180001b85  mov     rax, cs:__isa_inverted
0x180001b8c  or      cs:__isa_enabled, 40h
0x180001b93  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001b97  mov     cs:__isa_available, 6
0x180001ba1  mov     cs:__isa_inverted, rax
0x180001ba8  jmp     short loc_180001BB1
0x180001baa  mov     rax, cs:__isa_inverted
0x180001bb1  bt      esi, 17h
0x180001bb5  jnb     short loc_180001BC3
0x180001bb7  btr     rax, 18h
0x180001bbc  mov     cs:__isa_inverted, rax
0x180001bc3  bt      r10d, 13h
0x180001bc8  jnb     short loc_180001C18
0x180001bca  mov     rax, [rsp+38h+arg_0]
0x180001bcf  and     al, dl
0x180001bd1  cmp     al, dl
0x180001bd3  jnz     short loc_180001C18
0x180001bd5  mov     rdx, cs:__isa_inverted
0x180001bdc  mov     eax, r11d
0x180001bdf  shr     rax, 10h
0x180001be3  mov     ecx, r11d
0x180001be6  and     eax, 6
0x180001be9  and     ecx, 400FFh
0x180001bef  or      rax, 1000029h
0x180001bf5  mov     cs:__avx10_version, ecx
0x180001bfb  not     rax
0x180001bfe  and     rdx, rax
0x180001c01  mov     cs:__isa_inverted, rdx
0x180001c08  cmp     cl, 1
0x180001c0b  jbe     short loc_180001C18
0x180001c0d  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001c11  mov     cs:__isa_inverted, rdx
0x180001c18  bt      r10d, 15h
0x180001c1d  jnb     short loc_180001C34
0x180001c1f  mov     rax, [rsp+38h+arg_0]
0x180001c24  bt      rax, 13h
0x180001c29  jnb     short loc_180001C34
0x180001c2b  btr     cs:__isa_inverted, 7
0x180001c34  xor     eax, eax
0x180001c36  add     rsp, 18h
0x180001c3a  pop     rdi
0x180001c3b  pop     rsi
0x180001c3c  pop     rbp
0x180001c3d  pop     rbx
0x180001c3e  retn
```
