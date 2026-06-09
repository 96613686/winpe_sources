# __isa_available_init

- ea: `0x180002180`
- end: `0x180002403`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001900`
- `0x180001a3c`

## callees

- `0x180002180`

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
0x180002180  push    rbx
0x180002182  push    rbp
0x180002183  push    rsi
0x180002184  push    rdi
0x180002185  sub     rsp, 18h
0x180002189  xor     eax, eax
0x18000218b  xor     ecx, ecx
0x18000218d  cpuid
0x18000218f  xor     ecx, 6C65746Eh
0x180002195  xor     edx, 49656E69h
0x18000219b  or      edx, ecx
0x18000219d  mov     ebp, eax
0x18000219f  mov     eax, 1
0x1800021a4  xor     ebx, 756E6547h
0x1800021aa  or      edx, ebx
0x1800021ac  lea     ecx, [rax-1]
0x1800021af  cpuid
0x1800021b1  mov     edi, ecx
0x1800021b3  jnz     short loc_180002213
0x1800021b5  and     eax, 0FFF3FF0h
0x1800021ba  mov     cs:__memset_fast_string_threshold, 8000h
0x1800021c5  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1800021d0  cmp     eax, 106C0h
0x1800021d5  jz      short loc_1800021FF
0x1800021d7  cmp     eax, 20660h
0x1800021dc  jz      short loc_1800021FF
0x1800021de  cmp     eax, 20670h
0x1800021e3  jz      short loc_1800021FF
0x1800021e5  add     eax, 0FFFCF9B0h
0x1800021ea  cmp     eax, 20h ; ' '
0x1800021ed  ja      short loc_180002213
0x1800021ef  mov     rcx, 100010001h
0x1800021f9  bt      rcx, rax
0x1800021fd  jnb     short loc_180002213
0x1800021ff  mov     r8d, cs:__favor
0x180002206  or      r8d, 1
0x18000220a  mov     cs:__favor, r8d
0x180002211  jmp     short loc_18000221A
0x180002213  mov     r8d, cs:__favor
0x18000221a  xor     r10d, r10d
0x18000221d  xor     r11d, r11d
0x180002220  cmp     ebp, 7
0x180002223  jl      short loc_180002267
0x180002225  xor     ecx, ecx
0x180002227  lea     eax, [r10+7]
0x18000222b  cpuid
0x18000222d  mov     esi, edx
0x18000222f  mov     r9d, ebx
0x180002232  bt      ebx, 9
0x180002236  jnb     short loc_180002243
0x180002238  or      r8d, 2
0x18000223c  mov     cs:__favor, r8d
0x180002243  cmp     eax, 1
0x180002246  jl      short loc_180002255
0x180002248  mov     eax, 7
0x18000224d  lea     ecx, [rax-6]
0x180002250  cpuid
0x180002252  mov     r10d, edx
0x180002255  mov     eax, 24h ; '$'
0x18000225a  cmp     ebp, eax
0x18000225c  jl      short loc_18000226C
0x18000225e  xor     ecx, ecx
0x180002260  cpuid
0x180002262  mov     r11d, ebx
0x180002265  jmp     short loc_18000226C
0x180002267  xor     r9d, r9d
0x18000226a  xor     esi, esi
0x18000226c  mov     rax, cs:__isa_inverted
0x180002273  and     rax, 0FFFFFFFFFFFFFFFEh
0x180002277  mov     cs:__isa_available, 1
0x180002281  mov     cs:__isa_enabled, 2
0x18000228b  mov     cs:__isa_inverted, rax
0x180002292  bt      edi, 14h
0x180002296  jnb     short loc_1800022B7
0x180002298  and     rax, 0FFFFFFFFFFFFFFEFh
0x18000229c  mov     cs:__isa_available, 2
0x1800022a6  mov     cs:__isa_inverted, rax
0x1800022ad  mov     cs:__isa_enabled, 6
0x1800022b7  bt      edi, 1Bh
0x1800022bb  jnb     loc_1800023F8
0x1800022c1  xor     ecx, ecx
0x1800022c3  xgetbv
0x1800022c6  shl     rdx, 20h
0x1800022ca  or      rdx, rax
0x1800022cd  mov     [rsp+38h+arg_0], rdx
0x1800022d2  bt      edi, 1Ch
0x1800022d6  jnb     loc_1800023DC
0x1800022dc  mov     rax, [rsp+38h+arg_0]
0x1800022e1  and     al, 6
0x1800022e3  cmp     al, 6
0x1800022e5  jnz     loc_1800023DC
0x1800022eb  mov     eax, cs:__isa_enabled
0x1800022f1  mov     dl, 0E0h
0x1800022f3  or      eax, 8
0x1800022f6  mov     cs:__isa_available, 3
0x180002300  mov     cs:__isa_enabled, eax
0x180002306  test    r9b, 20h
0x18000230a  jz      short loc_18000236E
0x18000230c  or      eax, 20h
0x18000230f  mov     cs:__isa_available, 5
0x180002319  mov     cs:__isa_enabled, eax
0x18000231f  mov     ecx, 0D0030000h
0x180002324  mov     rax, cs:__isa_inverted
0x18000232b  and     r9d, ecx
0x18000232e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180002332  mov     cs:__isa_inverted, rax
0x180002339  cmp     r9d, ecx
0x18000233c  jnz     short loc_180002375
0x18000233e  mov     rax, [rsp+38h+arg_0]
0x180002343  and     al, dl
0x180002345  cmp     al, dl
0x180002347  jnz     short loc_18000236E
0x180002349  mov     rax, cs:__isa_inverted
0x180002350  or      cs:__isa_enabled, 40h
0x180002357  and     rax, 0FFFFFFFFFFFFFFDBh
0x18000235b  mov     cs:__isa_available, 6
0x180002365  mov     cs:__isa_inverted, rax
0x18000236c  jmp     short loc_180002375
0x18000236e  mov     rax, cs:__isa_inverted
0x180002375  bt      esi, 17h
0x180002379  jnb     short loc_180002387
0x18000237b  btr     rax, 18h
0x180002380  mov     cs:__isa_inverted, rax
0x180002387  bt      r10d, 13h
0x18000238c  jnb     short loc_1800023DC
0x18000238e  mov     rax, [rsp+38h+arg_0]
0x180002393  and     al, dl
0x180002395  cmp     al, dl
0x180002397  jnz     short loc_1800023DC
0x180002399  mov     rdx, cs:__isa_inverted
0x1800023a0  mov     eax, r11d
0x1800023a3  shr     rax, 10h
0x1800023a7  mov     ecx, r11d
0x1800023aa  and     eax, 6
0x1800023ad  and     ecx, 400FFh
0x1800023b3  or      rax, 1000029h
0x1800023b9  mov     cs:__avx10_version, ecx
0x1800023bf  not     rax
0x1800023c2  and     rdx, rax
0x1800023c5  mov     cs:__isa_inverted, rdx
0x1800023cc  cmp     cl, 1
0x1800023cf  jbe     short loc_1800023DC
0x1800023d1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x1800023d5  mov     cs:__isa_inverted, rdx
0x1800023dc  bt      r10d, 15h
0x1800023e1  jnb     short loc_1800023F8
0x1800023e3  mov     rax, [rsp+38h+arg_0]
0x1800023e8  bt      rax, 13h
0x1800023ed  jnb     short loc_1800023F8
0x1800023ef  btr     cs:__isa_inverted, 7
0x1800023f8  xor     eax, eax
0x1800023fa  add     rsp, 18h
0x1800023fe  pop     rdi
0x1800023ff  pop     rsi
0x180002400  pop     rbp
0x180002401  pop     rbx
0x180002402  retn
```
