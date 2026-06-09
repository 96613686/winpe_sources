# __isa_available_init

- ea: `0x180002598`
- end: `0x18000281b`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001fc4`
- `0x180002100`

## callees

- `0x180002598`

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
0x180002598  push    rbx
0x18000259a  push    rbp
0x18000259b  push    rsi
0x18000259c  push    rdi
0x18000259d  sub     rsp, 18h
0x1800025a1  xor     eax, eax
0x1800025a3  xor     ecx, ecx
0x1800025a5  cpuid
0x1800025a7  xor     ecx, 6C65746Eh
0x1800025ad  xor     edx, 49656E69h
0x1800025b3  or      edx, ecx
0x1800025b5  mov     ebp, eax
0x1800025b7  mov     eax, 1
0x1800025bc  xor     ebx, 756E6547h
0x1800025c2  or      edx, ebx
0x1800025c4  lea     ecx, [rax-1]
0x1800025c7  cpuid
0x1800025c9  mov     edi, ecx
0x1800025cb  jnz     short loc_18000262B
0x1800025cd  and     eax, 0FFF3FF0h
0x1800025d2  mov     cs:__memset_fast_string_threshold, 8000h
0x1800025dd  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1800025e8  cmp     eax, 106C0h
0x1800025ed  jz      short loc_180002617
0x1800025ef  cmp     eax, 20660h
0x1800025f4  jz      short loc_180002617
0x1800025f6  cmp     eax, 20670h
0x1800025fb  jz      short loc_180002617
0x1800025fd  add     eax, 0FFFCF9B0h
0x180002602  cmp     eax, 20h ; ' '
0x180002605  ja      short loc_18000262B
0x180002607  mov     rcx, 100010001h
0x180002611  bt      rcx, rax
0x180002615  jnb     short loc_18000262B
0x180002617  mov     r8d, cs:__favor
0x18000261e  or      r8d, 1
0x180002622  mov     cs:__favor, r8d
0x180002629  jmp     short loc_180002632
0x18000262b  mov     r8d, cs:__favor
0x180002632  xor     r10d, r10d
0x180002635  xor     r11d, r11d
0x180002638  cmp     ebp, 7
0x18000263b  jl      short loc_18000267F
0x18000263d  xor     ecx, ecx
0x18000263f  lea     eax, [r10+7]
0x180002643  cpuid
0x180002645  mov     esi, edx
0x180002647  mov     r9d, ebx
0x18000264a  bt      ebx, 9
0x18000264e  jnb     short loc_18000265B
0x180002650  or      r8d, 2
0x180002654  mov     cs:__favor, r8d
0x18000265b  cmp     eax, 1
0x18000265e  jl      short loc_18000266D
0x180002660  mov     eax, 7
0x180002665  lea     ecx, [rax-6]
0x180002668  cpuid
0x18000266a  mov     r10d, edx
0x18000266d  mov     eax, 24h ; '$'
0x180002672  cmp     ebp, eax
0x180002674  jl      short loc_180002684
0x180002676  xor     ecx, ecx
0x180002678  cpuid
0x18000267a  mov     r11d, ebx
0x18000267d  jmp     short loc_180002684
0x18000267f  xor     r9d, r9d
0x180002682  xor     esi, esi
0x180002684  mov     rax, cs:__isa_inverted
0x18000268b  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000268f  mov     cs:__isa_available, 1
0x180002699  mov     cs:__isa_enabled, 2
0x1800026a3  mov     cs:__isa_inverted, rax
0x1800026aa  bt      edi, 14h
0x1800026ae  jnb     short loc_1800026CF
0x1800026b0  and     rax, 0FFFFFFFFFFFFFFEFh
0x1800026b4  mov     cs:__isa_available, 2
0x1800026be  mov     cs:__isa_inverted, rax
0x1800026c5  mov     cs:__isa_enabled, 6
0x1800026cf  bt      edi, 1Bh
0x1800026d3  jnb     loc_180002810
0x1800026d9  xor     ecx, ecx
0x1800026db  xgetbv
0x1800026de  shl     rdx, 20h
0x1800026e2  or      rdx, rax
0x1800026e5  mov     [rsp+38h+arg_0], rdx
0x1800026ea  bt      edi, 1Ch
0x1800026ee  jnb     loc_1800027F4
0x1800026f4  mov     rax, [rsp+38h+arg_0]
0x1800026f9  and     al, 6
0x1800026fb  cmp     al, 6
0x1800026fd  jnz     loc_1800027F4
0x180002703  mov     eax, cs:__isa_enabled
0x180002709  mov     dl, 0E0h
0x18000270b  or      eax, 8
0x18000270e  mov     cs:__isa_available, 3
0x180002718  mov     cs:__isa_enabled, eax
0x18000271e  test    r9b, 20h
0x180002722  jz      short loc_180002786
0x180002724  or      eax, 20h
0x180002727  mov     cs:__isa_available, 5
0x180002731  mov     cs:__isa_enabled, eax
0x180002737  mov     ecx, 0D0030000h
0x18000273c  mov     rax, cs:__isa_inverted
0x180002743  and     r9d, ecx
0x180002746  and     rax, 0FFFFFFFFFFFFFFFDh
0x18000274a  mov     cs:__isa_inverted, rax
0x180002751  cmp     r9d, ecx
0x180002754  jnz     short loc_18000278D
0x180002756  mov     rax, [rsp+38h+arg_0]
0x18000275b  and     al, dl
0x18000275d  cmp     al, dl
0x18000275f  jnz     short loc_180002786
0x180002761  mov     rax, cs:__isa_inverted
0x180002768  or      cs:__isa_enabled, 40h
0x18000276f  and     rax, 0FFFFFFFFFFFFFFDBh
0x180002773  mov     cs:__isa_available, 6
0x18000277d  mov     cs:__isa_inverted, rax
0x180002784  jmp     short loc_18000278D
0x180002786  mov     rax, cs:__isa_inverted
0x18000278d  bt      esi, 17h
0x180002791  jnb     short loc_18000279F
0x180002793  btr     rax, 18h
0x180002798  mov     cs:__isa_inverted, rax
0x18000279f  bt      r10d, 13h
0x1800027a4  jnb     short loc_1800027F4
0x1800027a6  mov     rax, [rsp+38h+arg_0]
0x1800027ab  and     al, dl
0x1800027ad  cmp     al, dl
0x1800027af  jnz     short loc_1800027F4
0x1800027b1  mov     rdx, cs:__isa_inverted
0x1800027b8  mov     eax, r11d
0x1800027bb  shr     rax, 10h
0x1800027bf  mov     ecx, r11d
0x1800027c2  and     eax, 6
0x1800027c5  and     ecx, 400FFh
0x1800027cb  or      rax, 1000029h
0x1800027d1  mov     cs:__avx10_version, ecx
0x1800027d7  not     rax
0x1800027da  and     rdx, rax
0x1800027dd  mov     cs:__isa_inverted, rdx
0x1800027e4  cmp     cl, 1
0x1800027e7  jbe     short loc_1800027F4
0x1800027e9  and     rdx, 0FFFFFFFFFFFFFFBFh
0x1800027ed  mov     cs:__isa_inverted, rdx
0x1800027f4  bt      r10d, 15h
0x1800027f9  jnb     short loc_180002810
0x1800027fb  mov     rax, [rsp+38h+arg_0]
0x180002800  bt      rax, 13h
0x180002805  jnb     short loc_180002810
0x180002807  btr     cs:__isa_inverted, 7
0x180002810  xor     eax, eax
0x180002812  add     rsp, 18h
0x180002816  pop     rdi
0x180002817  pop     rsi
0x180002818  pop     rbp
0x180002819  pop     rbx
0x18000281a  retn
```
