# __isa_available_init

- ea: `0x180002508`
- end: `0x18000278b`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001f34`
- `0x180002070`

## callees

- `0x180002508`

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
0x180002508  push    rbx
0x18000250a  push    rbp
0x18000250b  push    rsi
0x18000250c  push    rdi
0x18000250d  sub     rsp, 18h
0x180002511  xor     eax, eax
0x180002513  xor     ecx, ecx
0x180002515  cpuid
0x180002517  xor     ecx, 6C65746Eh
0x18000251d  xor     edx, 49656E69h
0x180002523  or      edx, ecx
0x180002525  mov     ebp, eax
0x180002527  mov     eax, 1
0x18000252c  xor     ebx, 756E6547h
0x180002532  or      edx, ebx
0x180002534  lea     ecx, [rax-1]
0x180002537  cpuid
0x180002539  mov     edi, ecx
0x18000253b  jnz     short loc_18000259B
0x18000253d  and     eax, 0FFF3FF0h
0x180002542  mov     cs:__memset_fast_string_threshold, 8000h
0x18000254d  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180002558  cmp     eax, 106C0h
0x18000255d  jz      short loc_180002587
0x18000255f  cmp     eax, 20660h
0x180002564  jz      short loc_180002587
0x180002566  cmp     eax, 20670h
0x18000256b  jz      short loc_180002587
0x18000256d  add     eax, 0FFFCF9B0h
0x180002572  cmp     eax, 20h ; ' '
0x180002575  ja      short loc_18000259B
0x180002577  mov     rcx, 100010001h
0x180002581  bt      rcx, rax
0x180002585  jnb     short loc_18000259B
0x180002587  mov     r8d, cs:__favor
0x18000258e  or      r8d, 1
0x180002592  mov     cs:__favor, r8d
0x180002599  jmp     short loc_1800025A2
0x18000259b  mov     r8d, cs:__favor
0x1800025a2  xor     r10d, r10d
0x1800025a5  xor     r11d, r11d
0x1800025a8  cmp     ebp, 7
0x1800025ab  jl      short loc_1800025EF
0x1800025ad  xor     ecx, ecx
0x1800025af  lea     eax, [r10+7]
0x1800025b3  cpuid
0x1800025b5  mov     esi, edx
0x1800025b7  mov     r9d, ebx
0x1800025ba  bt      ebx, 9
0x1800025be  jnb     short loc_1800025CB
0x1800025c0  or      r8d, 2
0x1800025c4  mov     cs:__favor, r8d
0x1800025cb  cmp     eax, 1
0x1800025ce  jl      short loc_1800025DD
0x1800025d0  mov     eax, 7
0x1800025d5  lea     ecx, [rax-6]
0x1800025d8  cpuid
0x1800025da  mov     r10d, edx
0x1800025dd  mov     eax, 24h ; '$'
0x1800025e2  cmp     ebp, eax
0x1800025e4  jl      short loc_1800025F4
0x1800025e6  xor     ecx, ecx
0x1800025e8  cpuid
0x1800025ea  mov     r11d, ebx
0x1800025ed  jmp     short loc_1800025F4
0x1800025ef  xor     r9d, r9d
0x1800025f2  xor     esi, esi
0x1800025f4  mov     rax, cs:__isa_inverted
0x1800025fb  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800025ff  mov     cs:__isa_available, 1
0x180002609  mov     cs:__isa_enabled, 2
0x180002613  mov     cs:__isa_inverted, rax
0x18000261a  bt      edi, 14h
0x18000261e  jnb     short loc_18000263F
0x180002620  and     rax, 0FFFFFFFFFFFFFFEFh
0x180002624  mov     cs:__isa_available, 2
0x18000262e  mov     cs:__isa_inverted, rax
0x180002635  mov     cs:__isa_enabled, 6
0x18000263f  bt      edi, 1Bh
0x180002643  jnb     loc_180002780
0x180002649  xor     ecx, ecx
0x18000264b  xgetbv
0x18000264e  shl     rdx, 20h
0x180002652  or      rdx, rax
0x180002655  mov     [rsp+38h+arg_0], rdx
0x18000265a  bt      edi, 1Ch
0x18000265e  jnb     loc_180002764
0x180002664  mov     rax, [rsp+38h+arg_0]
0x180002669  and     al, 6
0x18000266b  cmp     al, 6
0x18000266d  jnz     loc_180002764
0x180002673  mov     eax, cs:__isa_enabled
0x180002679  mov     dl, 0E0h
0x18000267b  or      eax, 8
0x18000267e  mov     cs:__isa_available, 3
0x180002688  mov     cs:__isa_enabled, eax
0x18000268e  test    r9b, 20h
0x180002692  jz      short loc_1800026F6
0x180002694  or      eax, 20h
0x180002697  mov     cs:__isa_available, 5
0x1800026a1  mov     cs:__isa_enabled, eax
0x1800026a7  mov     ecx, 0D0030000h
0x1800026ac  mov     rax, cs:__isa_inverted
0x1800026b3  and     r9d, ecx
0x1800026b6  and     rax, 0FFFFFFFFFFFFFFFDh
0x1800026ba  mov     cs:__isa_inverted, rax
0x1800026c1  cmp     r9d, ecx
0x1800026c4  jnz     short loc_1800026FD
0x1800026c6  mov     rax, [rsp+38h+arg_0]
0x1800026cb  and     al, dl
0x1800026cd  cmp     al, dl
0x1800026cf  jnz     short loc_1800026F6
0x1800026d1  mov     rax, cs:__isa_inverted
0x1800026d8  or      cs:__isa_enabled, 40h
0x1800026df  and     rax, 0FFFFFFFFFFFFFFDBh
0x1800026e3  mov     cs:__isa_available, 6
0x1800026ed  mov     cs:__isa_inverted, rax
0x1800026f4  jmp     short loc_1800026FD
0x1800026f6  mov     rax, cs:__isa_inverted
0x1800026fd  bt      esi, 17h
0x180002701  jnb     short loc_18000270F
0x180002703  btr     rax, 18h
0x180002708  mov     cs:__isa_inverted, rax
0x18000270f  bt      r10d, 13h
0x180002714  jnb     short loc_180002764
0x180002716  mov     rax, [rsp+38h+arg_0]
0x18000271b  and     al, dl
0x18000271d  cmp     al, dl
0x18000271f  jnz     short loc_180002764
0x180002721  mov     rdx, cs:__isa_inverted
0x180002728  mov     eax, r11d
0x18000272b  shr     rax, 10h
0x18000272f  mov     ecx, r11d
0x180002732  and     eax, 6
0x180002735  and     ecx, 400FFh
0x18000273b  or      rax, 1000029h
0x180002741  mov     cs:__avx10_version, ecx
0x180002747  not     rax
0x18000274a  and     rdx, rax
0x18000274d  mov     cs:__isa_inverted, rdx
0x180002754  cmp     cl, 1
0x180002757  jbe     short loc_180002764
0x180002759  and     rdx, 0FFFFFFFFFFFFFFBFh
0x18000275d  mov     cs:__isa_inverted, rdx
0x180002764  bt      r10d, 15h
0x180002769  jnb     short loc_180002780
0x18000276b  mov     rax, [rsp+38h+arg_0]
0x180002770  bt      rax, 13h
0x180002775  jnb     short loc_180002780
0x180002777  btr     cs:__isa_inverted, 7
0x180002780  xor     eax, eax
0x180002782  add     rsp, 18h
0x180002786  pop     rdi
0x180002787  pop     rsi
0x180002788  pop     rbp
0x180002789  pop     rbx
0x18000278a  retn
```
