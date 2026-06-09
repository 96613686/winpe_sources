# __isa_available_init

- ea: `0x1800023a4`
- end: `0x180002627`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001de8`
- `0x180001f24`

## callees

- `0x1800023a4`

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
0x1800023a4  push    rbx
0x1800023a6  push    rbp
0x1800023a7  push    rsi
0x1800023a8  push    rdi
0x1800023a9  sub     rsp, 18h
0x1800023ad  xor     eax, eax
0x1800023af  xor     ecx, ecx
0x1800023b1  cpuid
0x1800023b3  xor     ecx, 6C65746Eh
0x1800023b9  xor     edx, 49656E69h
0x1800023bf  or      edx, ecx
0x1800023c1  mov     ebp, eax
0x1800023c3  mov     eax, 1
0x1800023c8  xor     ebx, 756E6547h
0x1800023ce  or      edx, ebx
0x1800023d0  lea     ecx, [rax-1]
0x1800023d3  cpuid
0x1800023d5  mov     edi, ecx
0x1800023d7  jnz     short loc_180002437
0x1800023d9  and     eax, 0FFF3FF0h
0x1800023de  mov     cs:__memset_fast_string_threshold, 8000h
0x1800023e9  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1800023f4  cmp     eax, 106C0h
0x1800023f9  jz      short loc_180002423
0x1800023fb  cmp     eax, 20660h
0x180002400  jz      short loc_180002423
0x180002402  cmp     eax, 20670h
0x180002407  jz      short loc_180002423
0x180002409  add     eax, 0FFFCF9B0h
0x18000240e  cmp     eax, 20h ; ' '
0x180002411  ja      short loc_180002437
0x180002413  mov     rcx, 100010001h
0x18000241d  bt      rcx, rax
0x180002421  jnb     short loc_180002437
0x180002423  mov     r8d, cs:__favor
0x18000242a  or      r8d, 1
0x18000242e  mov     cs:__favor, r8d
0x180002435  jmp     short loc_18000243E
0x180002437  mov     r8d, cs:__favor
0x18000243e  xor     r10d, r10d
0x180002441  xor     r11d, r11d
0x180002444  cmp     ebp, 7
0x180002447  jl      short loc_18000248B
0x180002449  xor     ecx, ecx
0x18000244b  lea     eax, [r10+7]
0x18000244f  cpuid
0x180002451  mov     esi, edx
0x180002453  mov     r9d, ebx
0x180002456  bt      ebx, 9
0x18000245a  jnb     short loc_180002467
0x18000245c  or      r8d, 2
0x180002460  mov     cs:__favor, r8d
0x180002467  cmp     eax, 1
0x18000246a  jl      short loc_180002479
0x18000246c  mov     eax, 7
0x180002471  lea     ecx, [rax-6]
0x180002474  cpuid
0x180002476  mov     r10d, edx
0x180002479  mov     eax, 24h ; '$'
0x18000247e  cmp     ebp, eax
0x180002480  jl      short loc_180002490
0x180002482  xor     ecx, ecx
0x180002484  cpuid
0x180002486  mov     r11d, ebx
0x180002489  jmp     short loc_180002490
0x18000248b  xor     r9d, r9d
0x18000248e  xor     esi, esi
0x180002490  mov     rax, cs:__isa_inverted
0x180002497  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000249b  mov     cs:__isa_available, 1
0x1800024a5  mov     cs:__isa_enabled, 2
0x1800024af  mov     cs:__isa_inverted, rax
0x1800024b6  bt      edi, 14h
0x1800024ba  jnb     short loc_1800024DB
0x1800024bc  and     rax, 0FFFFFFFFFFFFFFEFh
0x1800024c0  mov     cs:__isa_available, 2
0x1800024ca  mov     cs:__isa_inverted, rax
0x1800024d1  mov     cs:__isa_enabled, 6
0x1800024db  bt      edi, 1Bh
0x1800024df  jnb     loc_18000261C
0x1800024e5  xor     ecx, ecx
0x1800024e7  xgetbv
0x1800024ea  shl     rdx, 20h
0x1800024ee  or      rdx, rax
0x1800024f1  mov     [rsp+38h+arg_0], rdx
0x1800024f6  bt      edi, 1Ch
0x1800024fa  jnb     loc_180002600
0x180002500  mov     rax, [rsp+38h+arg_0]
0x180002505  and     al, 6
0x180002507  cmp     al, 6
0x180002509  jnz     loc_180002600
0x18000250f  mov     eax, cs:__isa_enabled
0x180002515  mov     dl, 0E0h
0x180002517  or      eax, 8
0x18000251a  mov     cs:__isa_available, 3
0x180002524  mov     cs:__isa_enabled, eax
0x18000252a  test    r9b, 20h
0x18000252e  jz      short loc_180002592
0x180002530  or      eax, 20h
0x180002533  mov     cs:__isa_available, 5
0x18000253d  mov     cs:__isa_enabled, eax
0x180002543  mov     ecx, 0D0030000h
0x180002548  mov     rax, cs:__isa_inverted
0x18000254f  and     r9d, ecx
0x180002552  and     rax, 0FFFFFFFFFFFFFFFDh
0x180002556  mov     cs:__isa_inverted, rax
0x18000255d  cmp     r9d, ecx
0x180002560  jnz     short loc_180002599
0x180002562  mov     rax, [rsp+38h+arg_0]
0x180002567  and     al, dl
0x180002569  cmp     al, dl
0x18000256b  jnz     short loc_180002592
0x18000256d  mov     rax, cs:__isa_inverted
0x180002574  or      cs:__isa_enabled, 40h
0x18000257b  and     rax, 0FFFFFFFFFFFFFFDBh
0x18000257f  mov     cs:__isa_available, 6
0x180002589  mov     cs:__isa_inverted, rax
0x180002590  jmp     short loc_180002599
0x180002592  mov     rax, cs:__isa_inverted
0x180002599  bt      esi, 17h
0x18000259d  jnb     short loc_1800025AB
0x18000259f  btr     rax, 18h
0x1800025a4  mov     cs:__isa_inverted, rax
0x1800025ab  bt      r10d, 13h
0x1800025b0  jnb     short loc_180002600
0x1800025b2  mov     rax, [rsp+38h+arg_0]
0x1800025b7  and     al, dl
0x1800025b9  cmp     al, dl
0x1800025bb  jnz     short loc_180002600
0x1800025bd  mov     rdx, cs:__isa_inverted
0x1800025c4  mov     eax, r11d
0x1800025c7  shr     rax, 10h
0x1800025cb  mov     ecx, r11d
0x1800025ce  and     eax, 6
0x1800025d1  and     ecx, 400FFh
0x1800025d7  or      rax, 1000029h
0x1800025dd  mov     cs:__avx10_version, ecx
0x1800025e3  not     rax
0x1800025e6  and     rdx, rax
0x1800025e9  mov     cs:__isa_inverted, rdx
0x1800025f0  cmp     cl, 1
0x1800025f3  jbe     short loc_180002600
0x1800025f5  and     rdx, 0FFFFFFFFFFFFFFBFh
0x1800025f9  mov     cs:__isa_inverted, rdx
0x180002600  bt      r10d, 15h
0x180002605  jnb     short loc_18000261C
0x180002607  mov     rax, [rsp+38h+arg_0]
0x18000260c  bt      rax, 13h
0x180002611  jnb     short loc_18000261C
0x180002613  btr     cs:__isa_inverted, 7
0x18000261c  xor     eax, eax
0x18000261e  add     rsp, 18h
0x180002622  pop     rdi
0x180002623  pop     rsi
0x180002624  pop     rbp
0x180002625  pop     rbx
0x180002626  retn
```
