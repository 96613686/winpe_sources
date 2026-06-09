# __isa_available_init

- ea: `0x180001970`
- end: `0x180001bf3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001598`
- `0x1800016d4`

## callees

- `0x180001970`

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
0x180001970  push    rbx
0x180001972  push    rbp
0x180001973  push    rsi
0x180001974  push    rdi
0x180001975  sub     rsp, 18h
0x180001979  xor     eax, eax
0x18000197b  xor     ecx, ecx
0x18000197d  cpuid
0x18000197f  xor     ecx, 6C65746Eh
0x180001985  xor     edx, 49656E69h
0x18000198b  or      edx, ecx
0x18000198d  mov     ebp, eax
0x18000198f  mov     eax, 1
0x180001994  xor     ebx, 756E6547h
0x18000199a  or      edx, ebx
0x18000199c  lea     ecx, [rax-1]
0x18000199f  cpuid
0x1800019a1  mov     edi, ecx
0x1800019a3  jnz     short loc_180001A03
0x1800019a5  and     eax, 0FFF3FF0h
0x1800019aa  mov     cs:__memset_fast_string_threshold, 8000h
0x1800019b5  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1800019c0  cmp     eax, 106C0h
0x1800019c5  jz      short loc_1800019EF
0x1800019c7  cmp     eax, 20660h
0x1800019cc  jz      short loc_1800019EF
0x1800019ce  cmp     eax, 20670h
0x1800019d3  jz      short loc_1800019EF
0x1800019d5  add     eax, 0FFFCF9B0h
0x1800019da  cmp     eax, 20h ; ' '
0x1800019dd  ja      short loc_180001A03
0x1800019df  mov     rcx, 100010001h
0x1800019e9  bt      rcx, rax
0x1800019ed  jnb     short loc_180001A03
0x1800019ef  mov     r8d, cs:__favor
0x1800019f6  or      r8d, 1
0x1800019fa  mov     cs:__favor, r8d
0x180001a01  jmp     short loc_180001A0A
0x180001a03  mov     r8d, cs:__favor
0x180001a0a  xor     r10d, r10d
0x180001a0d  xor     r11d, r11d
0x180001a10  cmp     ebp, 7
0x180001a13  jl      short loc_180001A57
0x180001a15  xor     ecx, ecx
0x180001a17  lea     eax, [r10+7]
0x180001a1b  cpuid
0x180001a1d  mov     esi, edx
0x180001a1f  mov     r9d, ebx
0x180001a22  bt      ebx, 9
0x180001a26  jnb     short loc_180001A33
0x180001a28  or      r8d, 2
0x180001a2c  mov     cs:__favor, r8d
0x180001a33  cmp     eax, 1
0x180001a36  jl      short loc_180001A45
0x180001a38  mov     eax, 7
0x180001a3d  lea     ecx, [rax-6]
0x180001a40  cpuid
0x180001a42  mov     r10d, edx
0x180001a45  mov     eax, 24h ; '$'
0x180001a4a  cmp     ebp, eax
0x180001a4c  jl      short loc_180001A5C
0x180001a4e  xor     ecx, ecx
0x180001a50  cpuid
0x180001a52  mov     r11d, ebx
0x180001a55  jmp     short loc_180001A5C
0x180001a57  xor     r9d, r9d
0x180001a5a  xor     esi, esi
0x180001a5c  mov     rax, cs:__isa_inverted
0x180001a63  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001a67  mov     cs:__isa_available, 1
0x180001a71  mov     cs:__isa_enabled, 2
0x180001a7b  mov     cs:__isa_inverted, rax
0x180001a82  bt      edi, 14h
0x180001a86  jnb     short loc_180001AA7
0x180001a88  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001a8c  mov     cs:__isa_available, 2
0x180001a96  mov     cs:__isa_inverted, rax
0x180001a9d  mov     cs:__isa_enabled, 6
0x180001aa7  bt      edi, 1Bh
0x180001aab  jnb     loc_180001BE8
0x180001ab1  xor     ecx, ecx
0x180001ab3  xgetbv
0x180001ab6  shl     rdx, 20h
0x180001aba  or      rdx, rax
0x180001abd  mov     [rsp+38h+arg_0], rdx
0x180001ac2  bt      edi, 1Ch
0x180001ac6  jnb     loc_180001BCC
0x180001acc  mov     rax, [rsp+38h+arg_0]
0x180001ad1  and     al, 6
0x180001ad3  cmp     al, 6
0x180001ad5  jnz     loc_180001BCC
0x180001adb  mov     eax, cs:__isa_enabled
0x180001ae1  mov     dl, 0E0h
0x180001ae3  or      eax, 8
0x180001ae6  mov     cs:__isa_available, 3
0x180001af0  mov     cs:__isa_enabled, eax
0x180001af6  test    r9b, 20h
0x180001afa  jz      short loc_180001B5E
0x180001afc  or      eax, 20h
0x180001aff  mov     cs:__isa_available, 5
0x180001b09  mov     cs:__isa_enabled, eax
0x180001b0f  mov     ecx, 0D0030000h
0x180001b14  mov     rax, cs:__isa_inverted
0x180001b1b  and     r9d, ecx
0x180001b1e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001b22  mov     cs:__isa_inverted, rax
0x180001b29  cmp     r9d, ecx
0x180001b2c  jnz     short loc_180001B65
0x180001b2e  mov     rax, [rsp+38h+arg_0]
0x180001b33  and     al, dl
0x180001b35  cmp     al, dl
0x180001b37  jnz     short loc_180001B5E
0x180001b39  mov     rax, cs:__isa_inverted
0x180001b40  or      cs:__isa_enabled, 40h
0x180001b47  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001b4b  mov     cs:__isa_available, 6
0x180001b55  mov     cs:__isa_inverted, rax
0x180001b5c  jmp     short loc_180001B65
0x180001b5e  mov     rax, cs:__isa_inverted
0x180001b65  bt      esi, 17h
0x180001b69  jnb     short loc_180001B77
0x180001b6b  btr     rax, 18h
0x180001b70  mov     cs:__isa_inverted, rax
0x180001b77  bt      r10d, 13h
0x180001b7c  jnb     short loc_180001BCC
0x180001b7e  mov     rax, [rsp+38h+arg_0]
0x180001b83  and     al, dl
0x180001b85  cmp     al, dl
0x180001b87  jnz     short loc_180001BCC
0x180001b89  mov     rdx, cs:__isa_inverted
0x180001b90  mov     eax, r11d
0x180001b93  shr     rax, 10h
0x180001b97  mov     ecx, r11d
0x180001b9a  and     eax, 6
0x180001b9d  and     ecx, 400FFh
0x180001ba3  or      rax, 1000029h
0x180001ba9  mov     cs:__avx10_version, ecx
0x180001baf  not     rax
0x180001bb2  and     rdx, rax
0x180001bb5  mov     cs:__isa_inverted, rdx
0x180001bbc  cmp     cl, 1
0x180001bbf  jbe     short loc_180001BCC
0x180001bc1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001bc5  mov     cs:__isa_inverted, rdx
0x180001bcc  bt      r10d, 15h
0x180001bd1  jnb     short loc_180001BE8
0x180001bd3  mov     rax, [rsp+38h+arg_0]
0x180001bd8  bt      rax, 13h
0x180001bdd  jnb     short loc_180001BE8
0x180001bdf  btr     cs:__isa_inverted, 7
0x180001be8  xor     eax, eax
0x180001bea  add     rsp, 18h
0x180001bee  pop     rdi
0x180001bef  pop     rsi
0x180001bf0  pop     rbp
0x180001bf1  pop     rbx
0x180001bf2  retn
```
