# __isa_available_init

- ea: `0x1400011c0`
- end: `0x140001455`
- name: `__isa_available_init`
- size: `661`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001cf8`

## callees

- `0x1400011c0`

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
  int v17; // r9d
  int v18; // esi
  int v19; // r10d
  unsigned int v20; // r11d
  unsigned __int64 v36; // rax
  int v37; // eax
  unsigned __int64 v38; // rax
  __int64 v39; // rcx
  int v41; // [rsp+20h] [rbp+8h]

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
  v19 = 0;
  v20 = 0;
  if ( v5 >= 7 )
  {
    _RAX = 7;
    __asm { cpuid }
    v18 = _RDX;
    v17 = _RBX;
    if ( (_RBX & 0x200) != 0 )
      _favor = v16 | 2;
    if ( (int)_RAX >= 1 )
    {
      _RAX = 7;
      __asm { cpuid }
      v19 = _RDX;
    }
    _RAX = 36;
    if ( v5 >= 36 )
    {
      __asm { cpuid }
      v20 = _RBX;
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
LABEL_32:
      if ( (v19 & 0x200000) != 0 && (*(_QWORD *)&v41 & 0x80000LL) != 0 )
        _isa_inverted &= ~0x80uLL;
      return 0;
    }
    v37 = _isa_enabled | 8;
    _isa_available = 3;
    _isa_enabled |= 8u;
    if ( (v17 & 0x20) != 0 )
    {
      _isa_available = 5;
      _isa_enabled = v37 | 0x20;
      v38 = _isa_inverted & 0xFFFFFFFFFFFFFFFDuLL;
      _isa_inverted &= ~2uLL;
      if ( (v17 & 0xD0030000) != 0xD0030000 )
      {
LABEL_26:
        if ( (v18 & 0x800000) != 0 )
          _isa_inverted = v38 & 0xFFFFFFFFFEFFFFFFuLL;
        if ( (v19 & 0x80000) != 0 && (v41 & 0xE0) == 0xE0 )
        {
          _avx10_version = v20 & 0x400FF;
          v39 = _isa_inverted & ~(HIWORD(v20) & 6 | 0x1000029LL);
          _isa_inverted = v39;
          if ( (unsigned __int8)v20 > 1u )
            _isa_inverted = v39 & 0xFFFFFFFFFFFFFFBFuLL;
        }
        goto LABEL_32;
      }
      if ( (v41 & 0xE0) == 0xE0 )
      {
        _isa_enabled |= 0x40u;
        v38 = _isa_inverted & 0xFFFFFFFFFFFFFFDBuLL;
        _isa_available = 6;
        _isa_inverted &= 0xFFFFFFFFFFFFFFDBuLL;
        goto LABEL_26;
      }
    }
    v38 = _isa_inverted;
    goto LABEL_26;
  }
  return 0;
}

```

## disassembly

```asm
0x1400011c0  mov     [rsp+arg_8], rbx
0x1400011c5  mov     [rsp+arg_10], rbp
0x1400011ca  mov     [rsp+arg_18], rsi
0x1400011cf  push    rdi
0x1400011d0  sub     rsp, 10h
0x1400011d4  xor     eax, eax
0x1400011d6  xor     ecx, ecx
0x1400011d8  cpuid
0x1400011da  xor     ecx, 6C65746Eh
0x1400011e0  xor     edx, 49656E69h
0x1400011e6  or      edx, ecx
0x1400011e8  mov     ebp, eax
0x1400011ea  mov     eax, 1
0x1400011ef  xor     ebx, 756E6547h
0x1400011f5  or      edx, ebx
0x1400011f7  lea     ecx, [rax-1]
0x1400011fa  cpuid
0x1400011fc  mov     edi, ecx
0x1400011fe  jnz     short loc_14000125E
0x140001200  and     eax, 0FFF3FF0h
0x140001205  mov     cs:__memset_fast_string_threshold, 8000h
0x140001210  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x14000121b  cmp     eax, 106C0h
0x140001220  jz      short loc_14000124A
0x140001222  cmp     eax, 20660h
0x140001227  jz      short loc_14000124A
0x140001229  cmp     eax, 20670h
0x14000122e  jz      short loc_14000124A
0x140001230  add     eax, 0FFFCF9B0h
0x140001235  cmp     eax, 20h ; ' '
0x140001238  ja      short loc_14000125E
0x14000123a  mov     rcx, 100010001h
0x140001244  bt      rcx, rax
0x140001248  jnb     short loc_14000125E
0x14000124a  mov     r8d, cs:__favor
0x140001251  or      r8d, 1
0x140001255  mov     cs:__favor, r8d
0x14000125c  jmp     short loc_140001265
0x14000125e  mov     r8d, cs:__favor
0x140001265  xor     r9d, r9d
0x140001268  mov     esi, r9d
0x14000126b  mov     r10d, r9d
0x14000126e  mov     r11d, r9d
0x140001271  cmp     ebp, 7
0x140001274  jl      short loc_1400012B6
0x140001276  lea     eax, [r9+7]
0x14000127a  xor     ecx, ecx
0x14000127c  cpuid
0x14000127e  mov     esi, edx
0x140001280  mov     r9d, ebx
0x140001283  bt      ebx, 9
0x140001287  jnb     short loc_140001294
0x140001289  or      r8d, 2
0x14000128d  mov     cs:__favor, r8d
0x140001294  cmp     eax, 1
0x140001297  jl      short loc_1400012A6
0x140001299  mov     eax, 7
0x14000129e  lea     ecx, [rax-6]
0x1400012a1  cpuid
0x1400012a3  mov     r10d, edx
0x1400012a6  mov     eax, 24h ; '$'
0x1400012ab  cmp     ebp, eax
0x1400012ad  jl      short loc_1400012B6
0x1400012af  xor     ecx, ecx
0x1400012b1  cpuid
0x1400012b3  mov     r11d, ebx
0x1400012b6  mov     rax, cs:__isa_inverted
0x1400012bd  and     rax, 0FFFFFFFFFFFFFFFEh
0x1400012c1  mov     cs:__isa_available, 1
0x1400012cb  mov     cs:__isa_enabled, 2
0x1400012d5  mov     cs:__isa_inverted, rax
0x1400012dc  bt      edi, 14h
0x1400012e0  jnb     short loc_140001301
0x1400012e2  and     rax, 0FFFFFFFFFFFFFFEFh
0x1400012e6  mov     cs:__isa_available, 2
0x1400012f0  mov     cs:__isa_inverted, rax
0x1400012f7  mov     cs:__isa_enabled, 6
0x140001301  bt      edi, 1Bh
0x140001305  jnb     loc_14000143E
0x14000130b  xor     ecx, ecx
0x14000130d  xgetbv
0x140001310  shl     rdx, 20h
0x140001314  or      rdx, rax
0x140001317  mov     [rsp+18h+arg_0], rdx
0x14000131c  bt      edi, 1Ch
0x140001320  jnb     loc_140001422
0x140001326  mov     rax, [rsp+18h+arg_0]
0x14000132b  and     al, 6
0x14000132d  cmp     al, 6
0x14000132f  jnz     loc_140001422
0x140001335  mov     eax, cs:__isa_enabled
0x14000133b  mov     dl, 0E0h
0x14000133d  or      eax, 8
0x140001340  mov     cs:__isa_available, 3
0x14000134a  mov     cs:__isa_enabled, eax
0x140001350  test    r9b, 20h
0x140001354  jz      short loc_1400013B8
0x140001356  or      eax, 20h
0x140001359  mov     cs:__isa_available, 5
0x140001363  mov     cs:__isa_enabled, eax
0x140001369  mov     ecx, 0D0030000h
0x14000136e  mov     rax, cs:__isa_inverted
0x140001375  and     r9d, ecx
0x140001378  and     rax, 0FFFFFFFFFFFFFFFDh
0x14000137c  mov     cs:__isa_inverted, rax
0x140001383  cmp     r9d, ecx
0x140001386  jnz     short loc_1400013BF
0x140001388  mov     rax, [rsp+18h+arg_0]
0x14000138d  and     al, dl
0x14000138f  cmp     al, dl
0x140001391  jnz     short loc_1400013B8
0x140001393  mov     rax, cs:__isa_inverted
0x14000139a  or      cs:__isa_enabled, 40h
0x1400013a1  and     rax, 0FFFFFFFFFFFFFFDBh
0x1400013a5  mov     cs:__isa_available, 6
0x1400013af  mov     cs:__isa_inverted, rax
0x1400013b6  jmp     short loc_1400013BF
0x1400013b8  mov     rax, cs:__isa_inverted
0x1400013bf  bt      esi, 17h
0x1400013c3  jnb     short loc_1400013D1
0x1400013c5  btr     rax, 18h
0x1400013ca  mov     cs:__isa_inverted, rax
0x1400013d1  bt      r10d, 13h
0x1400013d6  jnb     short loc_140001422
0x1400013d8  mov     rax, [rsp+18h+arg_0]
0x1400013dd  and     al, dl
0x1400013df  cmp     al, dl
0x1400013e1  jnz     short loc_140001422
0x1400013e3  mov     ecx, r11d
0x1400013e6  mov     eax, r11d
0x1400013e9  shr     rcx, 10h
0x1400013ed  and     eax, 400FFh
0x1400013f2  and     ecx, 6
0x1400013f5  mov     cs:__avx10_version, eax
0x1400013fb  or      rcx, 1000029h
0x140001402  not     rcx
0x140001405  and     rcx, cs:__isa_inverted
0x14000140c  mov     cs:__isa_inverted, rcx
0x140001413  cmp     al, 1
0x140001415  jbe     short loc_140001422
0x140001417  and     rcx, 0FFFFFFFFFFFFFFBFh
0x14000141b  mov     cs:__isa_inverted, rcx
0x140001422  bt      r10d, 15h
0x140001427  jnb     short loc_14000143E
0x140001429  mov     rax, [rsp+18h+arg_0]
0x14000142e  bt      rax, 13h
0x140001433  jnb     short loc_14000143E
0x140001435  btr     cs:__isa_inverted, 7
0x14000143e  mov     rbx, [rsp+18h+arg_8]
0x140001443  xor     eax, eax
0x140001445  mov     rbp, [rsp+18h+arg_10]
0x14000144a  mov     rsi, [rsp+18h+arg_18]
0x14000144f  add     rsp, 10h
0x140001453  pop     rdi
0x140001454  retn
```
