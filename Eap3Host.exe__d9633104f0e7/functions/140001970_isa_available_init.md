# __isa_available_init

- ea: `0x140001970`
- end: `0x140001bf3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400013c4`

## callees

- `0x140001970`

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
0x140001970  push    rbx
0x140001972  push    rbp
0x140001973  push    rsi
0x140001974  push    rdi
0x140001975  sub     rsp, 18h
0x140001979  xor     eax, eax
0x14000197b  xor     ecx, ecx
0x14000197d  cpuid
0x14000197f  xor     ecx, 6C65746Eh
0x140001985  xor     edx, 49656E69h
0x14000198b  or      edx, ecx
0x14000198d  mov     ebp, eax
0x14000198f  mov     eax, 1
0x140001994  xor     ebx, 756E6547h
0x14000199a  or      edx, ebx
0x14000199c  lea     ecx, [rax-1]
0x14000199f  cpuid
0x1400019a1  mov     edi, ecx
0x1400019a3  jnz     short loc_140001A03
0x1400019a5  and     eax, 0FFF3FF0h
0x1400019aa  mov     cs:__memset_fast_string_threshold, 8000h
0x1400019b5  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1400019c0  cmp     eax, 106C0h
0x1400019c5  jz      short loc_1400019EF
0x1400019c7  cmp     eax, 20660h
0x1400019cc  jz      short loc_1400019EF
0x1400019ce  cmp     eax, 20670h
0x1400019d3  jz      short loc_1400019EF
0x1400019d5  add     eax, 0FFFCF9B0h
0x1400019da  cmp     eax, 20h ; ' '
0x1400019dd  ja      short loc_140001A03
0x1400019df  mov     rcx, 100010001h
0x1400019e9  bt      rcx, rax
0x1400019ed  jnb     short loc_140001A03
0x1400019ef  mov     r8d, cs:__favor
0x1400019f6  or      r8d, 1
0x1400019fa  mov     cs:__favor, r8d
0x140001a01  jmp     short loc_140001A0A
0x140001a03  mov     r8d, cs:__favor
0x140001a0a  xor     r10d, r10d
0x140001a0d  xor     r11d, r11d
0x140001a10  cmp     ebp, 7
0x140001a13  jl      short loc_140001A57
0x140001a15  xor     ecx, ecx
0x140001a17  lea     eax, [r10+7]
0x140001a1b  cpuid
0x140001a1d  mov     esi, edx
0x140001a1f  mov     r9d, ebx
0x140001a22  bt      ebx, 9
0x140001a26  jnb     short loc_140001A33
0x140001a28  or      r8d, 2
0x140001a2c  mov     cs:__favor, r8d
0x140001a33  cmp     eax, 1
0x140001a36  jl      short loc_140001A45
0x140001a38  mov     eax, 7
0x140001a3d  lea     ecx, [rax-6]
0x140001a40  cpuid
0x140001a42  mov     r10d, edx
0x140001a45  mov     eax, 24h ; '$'
0x140001a4a  cmp     ebp, eax
0x140001a4c  jl      short loc_140001A5C
0x140001a4e  xor     ecx, ecx
0x140001a50  cpuid
0x140001a52  mov     r11d, ebx
0x140001a55  jmp     short loc_140001A5C
0x140001a57  xor     r9d, r9d
0x140001a5a  xor     esi, esi
0x140001a5c  mov     rax, cs:__isa_inverted
0x140001a63  and     rax, 0FFFFFFFFFFFFFFFEh
0x140001a67  mov     cs:__isa_available, 1
0x140001a71  mov     cs:__isa_enabled, 2
0x140001a7b  mov     cs:__isa_inverted, rax
0x140001a82  bt      edi, 14h
0x140001a86  jnb     short loc_140001AA7
0x140001a88  and     rax, 0FFFFFFFFFFFFFFEFh
0x140001a8c  mov     cs:__isa_available, 2
0x140001a96  mov     cs:__isa_inverted, rax
0x140001a9d  mov     cs:__isa_enabled, 6
0x140001aa7  bt      edi, 1Bh
0x140001aab  jnb     loc_140001BE8
0x140001ab1  xor     ecx, ecx
0x140001ab3  xgetbv
0x140001ab6  shl     rdx, 20h
0x140001aba  or      rdx, rax
0x140001abd  mov     [rsp+38h+arg_0], rdx
0x140001ac2  bt      edi, 1Ch
0x140001ac6  jnb     loc_140001BCC
0x140001acc  mov     rax, [rsp+38h+arg_0]
0x140001ad1  and     al, 6
0x140001ad3  cmp     al, 6
0x140001ad5  jnz     loc_140001BCC
0x140001adb  mov     eax, cs:__isa_enabled
0x140001ae1  mov     dl, 0E0h
0x140001ae3  or      eax, 8
0x140001ae6  mov     cs:__isa_available, 3
0x140001af0  mov     cs:__isa_enabled, eax
0x140001af6  test    r9b, 20h
0x140001afa  jz      short loc_140001B5E
0x140001afc  or      eax, 20h
0x140001aff  mov     cs:__isa_available, 5
0x140001b09  mov     cs:__isa_enabled, eax
0x140001b0f  mov     ecx, 0D0030000h
0x140001b14  mov     rax, cs:__isa_inverted
0x140001b1b  and     r9d, ecx
0x140001b1e  and     rax, 0FFFFFFFFFFFFFFFDh
0x140001b22  mov     cs:__isa_inverted, rax
0x140001b29  cmp     r9d, ecx
0x140001b2c  jnz     short loc_140001B65
0x140001b2e  mov     rax, [rsp+38h+arg_0]
0x140001b33  and     al, dl
0x140001b35  cmp     al, dl
0x140001b37  jnz     short loc_140001B5E
0x140001b39  mov     rax, cs:__isa_inverted
0x140001b40  or      cs:__isa_enabled, 40h
0x140001b47  and     rax, 0FFFFFFFFFFFFFFDBh
0x140001b4b  mov     cs:__isa_available, 6
0x140001b55  mov     cs:__isa_inverted, rax
0x140001b5c  jmp     short loc_140001B65
0x140001b5e  mov     rax, cs:__isa_inverted
0x140001b65  bt      esi, 17h
0x140001b69  jnb     short loc_140001B77
0x140001b6b  btr     rax, 18h
0x140001b70  mov     cs:__isa_inverted, rax
0x140001b77  bt      r10d, 13h
0x140001b7c  jnb     short loc_140001BCC
0x140001b7e  mov     rax, [rsp+38h+arg_0]
0x140001b83  and     al, dl
0x140001b85  cmp     al, dl
0x140001b87  jnz     short loc_140001BCC
0x140001b89  mov     rdx, cs:__isa_inverted
0x140001b90  mov     eax, r11d
0x140001b93  shr     rax, 10h
0x140001b97  mov     ecx, r11d
0x140001b9a  and     eax, 6
0x140001b9d  and     ecx, 400FFh
0x140001ba3  or      rax, 1000029h
0x140001ba9  mov     cs:__avx10_version, ecx
0x140001baf  not     rax
0x140001bb2  and     rdx, rax
0x140001bb5  mov     cs:__isa_inverted, rdx
0x140001bbc  cmp     cl, 1
0x140001bbf  jbe     short loc_140001BCC
0x140001bc1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x140001bc5  mov     cs:__isa_inverted, rdx
0x140001bcc  bt      r10d, 15h
0x140001bd1  jnb     short loc_140001BE8
0x140001bd3  mov     rax, [rsp+38h+arg_0]
0x140001bd8  bt      rax, 13h
0x140001bdd  jnb     short loc_140001BE8
0x140001bdf  btr     cs:__isa_inverted, 7
0x140001be8  xor     eax, eax
0x140001bea  add     rsp, 18h
0x140001bee  pop     rdi
0x140001bef  pop     rsi
0x140001bf0  pop     rbp
0x140001bf1  pop     rbx
0x140001bf2  retn
```
