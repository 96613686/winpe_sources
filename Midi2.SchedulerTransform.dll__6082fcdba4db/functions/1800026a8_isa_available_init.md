# __isa_available_init

- ea: `0x1800026a8`
- end: `0x18000292b`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020d4`
- `0x180002210`

## callees

- `0x1800026a8`

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
0x1800026a8  push    rbx
0x1800026aa  push    rbp
0x1800026ab  push    rsi
0x1800026ac  push    rdi
0x1800026ad  sub     rsp, 18h
0x1800026b1  xor     eax, eax
0x1800026b3  xor     ecx, ecx
0x1800026b5  cpuid
0x1800026b7  xor     ecx, 6C65746Eh
0x1800026bd  xor     edx, 49656E69h
0x1800026c3  or      edx, ecx
0x1800026c5  mov     ebp, eax
0x1800026c7  mov     eax, 1
0x1800026cc  xor     ebx, 756E6547h
0x1800026d2  or      edx, ebx
0x1800026d4  lea     ecx, [rax-1]
0x1800026d7  cpuid
0x1800026d9  mov     edi, ecx
0x1800026db  jnz     short loc_18000273B
0x1800026dd  and     eax, 0FFF3FF0h
0x1800026e2  mov     cs:__memset_fast_string_threshold, 8000h
0x1800026ed  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1800026f8  cmp     eax, 106C0h
0x1800026fd  jz      short loc_180002727
0x1800026ff  cmp     eax, 20660h
0x180002704  jz      short loc_180002727
0x180002706  cmp     eax, 20670h
0x18000270b  jz      short loc_180002727
0x18000270d  add     eax, 0FFFCF9B0h
0x180002712  cmp     eax, 20h ; ' '
0x180002715  ja      short loc_18000273B
0x180002717  mov     rcx, 100010001h
0x180002721  bt      rcx, rax
0x180002725  jnb     short loc_18000273B
0x180002727  mov     r8d, cs:__favor
0x18000272e  or      r8d, 1
0x180002732  mov     cs:__favor, r8d
0x180002739  jmp     short loc_180002742
0x18000273b  mov     r8d, cs:__favor
0x180002742  xor     r10d, r10d
0x180002745  xor     r11d, r11d
0x180002748  cmp     ebp, 7
0x18000274b  jl      short loc_18000278F
0x18000274d  xor     ecx, ecx
0x18000274f  lea     eax, [r10+7]
0x180002753  cpuid
0x180002755  mov     esi, edx
0x180002757  mov     r9d, ebx
0x18000275a  bt      ebx, 9
0x18000275e  jnb     short loc_18000276B
0x180002760  or      r8d, 2
0x180002764  mov     cs:__favor, r8d
0x18000276b  cmp     eax, 1
0x18000276e  jl      short loc_18000277D
0x180002770  mov     eax, 7
0x180002775  lea     ecx, [rax-6]
0x180002778  cpuid
0x18000277a  mov     r10d, edx
0x18000277d  mov     eax, 24h ; '$'
0x180002782  cmp     ebp, eax
0x180002784  jl      short loc_180002794
0x180002786  xor     ecx, ecx
0x180002788  cpuid
0x18000278a  mov     r11d, ebx
0x18000278d  jmp     short loc_180002794
0x18000278f  xor     r9d, r9d
0x180002792  xor     esi, esi
0x180002794  mov     rax, cs:__isa_inverted
0x18000279b  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000279f  mov     cs:__isa_available, 1
0x1800027a9  mov     cs:__isa_enabled, 2
0x1800027b3  mov     cs:__isa_inverted, rax
0x1800027ba  bt      edi, 14h
0x1800027be  jnb     short loc_1800027DF
0x1800027c0  and     rax, 0FFFFFFFFFFFFFFEFh
0x1800027c4  mov     cs:__isa_available, 2
0x1800027ce  mov     cs:__isa_inverted, rax
0x1800027d5  mov     cs:__isa_enabled, 6
0x1800027df  bt      edi, 1Bh
0x1800027e3  jnb     loc_180002920
0x1800027e9  xor     ecx, ecx
0x1800027eb  xgetbv
0x1800027ee  shl     rdx, 20h
0x1800027f2  or      rdx, rax
0x1800027f5  mov     [rsp+38h+arg_0], rdx
0x1800027fa  bt      edi, 1Ch
0x1800027fe  jnb     loc_180002904
0x180002804  mov     rax, [rsp+38h+arg_0]
0x180002809  and     al, 6
0x18000280b  cmp     al, 6
0x18000280d  jnz     loc_180002904
0x180002813  mov     eax, cs:__isa_enabled
0x180002819  mov     dl, 0E0h
0x18000281b  or      eax, 8
0x18000281e  mov     cs:__isa_available, 3
0x180002828  mov     cs:__isa_enabled, eax
0x18000282e  test    r9b, 20h
0x180002832  jz      short loc_180002896
0x180002834  or      eax, 20h
0x180002837  mov     cs:__isa_available, 5
0x180002841  mov     cs:__isa_enabled, eax
0x180002847  mov     ecx, 0D0030000h
0x18000284c  mov     rax, cs:__isa_inverted
0x180002853  and     r9d, ecx
0x180002856  and     rax, 0FFFFFFFFFFFFFFFDh
0x18000285a  mov     cs:__isa_inverted, rax
0x180002861  cmp     r9d, ecx
0x180002864  jnz     short loc_18000289D
0x180002866  mov     rax, [rsp+38h+arg_0]
0x18000286b  and     al, dl
0x18000286d  cmp     al, dl
0x18000286f  jnz     short loc_180002896
0x180002871  mov     rax, cs:__isa_inverted
0x180002878  or      cs:__isa_enabled, 40h
0x18000287f  and     rax, 0FFFFFFFFFFFFFFDBh
0x180002883  mov     cs:__isa_available, 6
0x18000288d  mov     cs:__isa_inverted, rax
0x180002894  jmp     short loc_18000289D
0x180002896  mov     rax, cs:__isa_inverted
0x18000289d  bt      esi, 17h
0x1800028a1  jnb     short loc_1800028AF
0x1800028a3  btr     rax, 18h
0x1800028a8  mov     cs:__isa_inverted, rax
0x1800028af  bt      r10d, 13h
0x1800028b4  jnb     short loc_180002904
0x1800028b6  mov     rax, [rsp+38h+arg_0]
0x1800028bb  and     al, dl
0x1800028bd  cmp     al, dl
0x1800028bf  jnz     short loc_180002904
0x1800028c1  mov     rdx, cs:__isa_inverted
0x1800028c8  mov     eax, r11d
0x1800028cb  shr     rax, 10h
0x1800028cf  mov     ecx, r11d
0x1800028d2  and     eax, 6
0x1800028d5  and     ecx, 400FFh
0x1800028db  or      rax, 1000029h
0x1800028e1  mov     cs:__avx10_version, ecx
0x1800028e7  not     rax
0x1800028ea  and     rdx, rax
0x1800028ed  mov     cs:__isa_inverted, rdx
0x1800028f4  cmp     cl, 1
0x1800028f7  jbe     short loc_180002904
0x1800028f9  and     rdx, 0FFFFFFFFFFFFFFBFh
0x1800028fd  mov     cs:__isa_inverted, rdx
0x180002904  bt      r10d, 15h
0x180002909  jnb     short loc_180002920
0x18000290b  mov     rax, [rsp+38h+arg_0]
0x180002910  bt      rax, 13h
0x180002915  jnb     short loc_180002920
0x180002917  btr     cs:__isa_inverted, 7
0x180002920  xor     eax, eax
0x180002922  add     rsp, 18h
0x180002926  pop     rdi
0x180002927  pop     rsi
0x180002928  pop     rbp
0x180002929  pop     rbx
0x18000292a  retn
```
