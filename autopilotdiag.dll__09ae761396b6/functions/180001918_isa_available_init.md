# __isa_available_init

- ea: `0x180001918`
- end: `0x180001b9b`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001568`
- `0x1800016a4`

## callees

- `0x180001918`

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
0x180001918  push    rbx
0x18000191a  push    rbp
0x18000191b  push    rsi
0x18000191c  push    rdi
0x18000191d  sub     rsp, 18h
0x180001921  xor     eax, eax
0x180001923  xor     ecx, ecx
0x180001925  cpuid
0x180001927  xor     ecx, 6C65746Eh
0x18000192d  xor     edx, 49656E69h
0x180001933  or      edx, ecx
0x180001935  mov     ebp, eax
0x180001937  mov     eax, 1
0x18000193c  xor     ebx, 756E6547h
0x180001942  or      edx, ebx
0x180001944  lea     ecx, [rax-1]
0x180001947  cpuid
0x180001949  mov     edi, ecx
0x18000194b  jnz     short loc_1800019AB
0x18000194d  and     eax, 0FFF3FF0h
0x180001952  mov     cs:__memset_fast_string_threshold, 8000h
0x18000195d  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001968  cmp     eax, 106C0h
0x18000196d  jz      short loc_180001997
0x18000196f  cmp     eax, 20660h
0x180001974  jz      short loc_180001997
0x180001976  cmp     eax, 20670h
0x18000197b  jz      short loc_180001997
0x18000197d  add     eax, 0FFFCF9B0h
0x180001982  cmp     eax, 20h ; ' '
0x180001985  ja      short loc_1800019AB
0x180001987  mov     rcx, 100010001h
0x180001991  bt      rcx, rax
0x180001995  jnb     short loc_1800019AB
0x180001997  mov     r8d, cs:__favor
0x18000199e  or      r8d, 1
0x1800019a2  mov     cs:__favor, r8d
0x1800019a9  jmp     short loc_1800019B2
0x1800019ab  mov     r8d, cs:__favor
0x1800019b2  xor     r10d, r10d
0x1800019b5  xor     r11d, r11d
0x1800019b8  cmp     ebp, 7
0x1800019bb  jl      short loc_1800019FF
0x1800019bd  xor     ecx, ecx
0x1800019bf  lea     eax, [r10+7]
0x1800019c3  cpuid
0x1800019c5  mov     esi, edx
0x1800019c7  mov     r9d, ebx
0x1800019ca  bt      ebx, 9
0x1800019ce  jnb     short loc_1800019DB
0x1800019d0  or      r8d, 2
0x1800019d4  mov     cs:__favor, r8d
0x1800019db  cmp     eax, 1
0x1800019de  jl      short loc_1800019ED
0x1800019e0  mov     eax, 7
0x1800019e5  lea     ecx, [rax-6]
0x1800019e8  cpuid
0x1800019ea  mov     r10d, edx
0x1800019ed  mov     eax, 24h ; '$'
0x1800019f2  cmp     ebp, eax
0x1800019f4  jl      short loc_180001A04
0x1800019f6  xor     ecx, ecx
0x1800019f8  cpuid
0x1800019fa  mov     r11d, ebx
0x1800019fd  jmp     short loc_180001A04
0x1800019ff  xor     r9d, r9d
0x180001a02  xor     esi, esi
0x180001a04  mov     rax, cs:__isa_inverted
0x180001a0b  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001a0f  mov     cs:__isa_available, 1
0x180001a19  mov     cs:__isa_enabled, 2
0x180001a23  mov     cs:__isa_inverted, rax
0x180001a2a  bt      edi, 14h
0x180001a2e  jnb     short loc_180001A4F
0x180001a30  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001a34  mov     cs:__isa_available, 2
0x180001a3e  mov     cs:__isa_inverted, rax
0x180001a45  mov     cs:__isa_enabled, 6
0x180001a4f  bt      edi, 1Bh
0x180001a53  jnb     loc_180001B90
0x180001a59  xor     ecx, ecx
0x180001a5b  xgetbv
0x180001a5e  shl     rdx, 20h
0x180001a62  or      rdx, rax
0x180001a65  mov     [rsp+38h+arg_0], rdx
0x180001a6a  bt      edi, 1Ch
0x180001a6e  jnb     loc_180001B74
0x180001a74  mov     rax, [rsp+38h+arg_0]
0x180001a79  and     al, 6
0x180001a7b  cmp     al, 6
0x180001a7d  jnz     loc_180001B74
0x180001a83  mov     eax, cs:__isa_enabled
0x180001a89  mov     dl, 0E0h
0x180001a8b  or      eax, 8
0x180001a8e  mov     cs:__isa_available, 3
0x180001a98  mov     cs:__isa_enabled, eax
0x180001a9e  test    r9b, 20h
0x180001aa2  jz      short loc_180001B06
0x180001aa4  or      eax, 20h
0x180001aa7  mov     cs:__isa_available, 5
0x180001ab1  mov     cs:__isa_enabled, eax
0x180001ab7  mov     ecx, 0D0030000h
0x180001abc  mov     rax, cs:__isa_inverted
0x180001ac3  and     r9d, ecx
0x180001ac6  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001aca  mov     cs:__isa_inverted, rax
0x180001ad1  cmp     r9d, ecx
0x180001ad4  jnz     short loc_180001B0D
0x180001ad6  mov     rax, [rsp+38h+arg_0]
0x180001adb  and     al, dl
0x180001add  cmp     al, dl
0x180001adf  jnz     short loc_180001B06
0x180001ae1  mov     rax, cs:__isa_inverted
0x180001ae8  or      cs:__isa_enabled, 40h
0x180001aef  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001af3  mov     cs:__isa_available, 6
0x180001afd  mov     cs:__isa_inverted, rax
0x180001b04  jmp     short loc_180001B0D
0x180001b06  mov     rax, cs:__isa_inverted
0x180001b0d  bt      esi, 17h
0x180001b11  jnb     short loc_180001B1F
0x180001b13  btr     rax, 18h
0x180001b18  mov     cs:__isa_inverted, rax
0x180001b1f  bt      r10d, 13h
0x180001b24  jnb     short loc_180001B74
0x180001b26  mov     rax, [rsp+38h+arg_0]
0x180001b2b  and     al, dl
0x180001b2d  cmp     al, dl
0x180001b2f  jnz     short loc_180001B74
0x180001b31  mov     rdx, cs:__isa_inverted
0x180001b38  mov     eax, r11d
0x180001b3b  shr     rax, 10h
0x180001b3f  mov     ecx, r11d
0x180001b42  and     eax, 6
0x180001b45  and     ecx, 400FFh
0x180001b4b  or      rax, 1000029h
0x180001b51  mov     cs:__avx10_version, ecx
0x180001b57  not     rax
0x180001b5a  and     rdx, rax
0x180001b5d  mov     cs:__isa_inverted, rdx
0x180001b64  cmp     cl, 1
0x180001b67  jbe     short loc_180001B74
0x180001b69  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001b6d  mov     cs:__isa_inverted, rdx
0x180001b74  bt      r10d, 15h
0x180001b79  jnb     short loc_180001B90
0x180001b7b  mov     rax, [rsp+38h+arg_0]
0x180001b80  bt      rax, 13h
0x180001b85  jnb     short loc_180001B90
0x180001b87  btr     cs:__isa_inverted, 7
0x180001b90  xor     eax, eax
0x180001b92  add     rsp, 18h
0x180001b96  pop     rdi
0x180001b97  pop     rsi
0x180001b98  pop     rbp
0x180001b99  pop     rbx
0x180001b9a  retn
```
