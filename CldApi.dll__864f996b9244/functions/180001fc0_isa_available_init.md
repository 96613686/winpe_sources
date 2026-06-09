# __isa_available_init

- ea: `0x180001fc0`
- end: `0x180002243`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001bec`
- `0x180001d28`

## callees

- `0x180001fc0`

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
0x180001fc0  push    rbx
0x180001fc2  push    rbp
0x180001fc3  push    rsi
0x180001fc4  push    rdi
0x180001fc5  sub     rsp, 18h
0x180001fc9  xor     eax, eax
0x180001fcb  xor     ecx, ecx
0x180001fcd  cpuid
0x180001fcf  xor     ecx, 6C65746Eh
0x180001fd5  xor     edx, 49656E69h
0x180001fdb  or      edx, ecx
0x180001fdd  mov     ebp, eax
0x180001fdf  mov     eax, 1
0x180001fe4  xor     ebx, 756E6547h
0x180001fea  or      edx, ebx
0x180001fec  lea     ecx, [rax-1]
0x180001fef  cpuid
0x180001ff1  mov     edi, ecx
0x180001ff3  jnz     short loc_180002053
0x180001ff5  and     eax, 0FFF3FF0h
0x180001ffa  mov     cs:__memset_fast_string_threshold, 8000h
0x180002005  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180002010  cmp     eax, 106C0h
0x180002015  jz      short loc_18000203F
0x180002017  cmp     eax, 20660h
0x18000201c  jz      short loc_18000203F
0x18000201e  cmp     eax, 20670h
0x180002023  jz      short loc_18000203F
0x180002025  add     eax, 0FFFCF9B0h
0x18000202a  cmp     eax, 20h ; ' '
0x18000202d  ja      short loc_180002053
0x18000202f  mov     rcx, 100010001h
0x180002039  bt      rcx, rax
0x18000203d  jnb     short loc_180002053
0x18000203f  mov     r8d, cs:__favor
0x180002046  or      r8d, 1
0x18000204a  mov     cs:__favor, r8d
0x180002051  jmp     short loc_18000205A
0x180002053  mov     r8d, cs:__favor
0x18000205a  xor     r10d, r10d
0x18000205d  xor     r11d, r11d
0x180002060  cmp     ebp, 7
0x180002063  jl      short loc_1800020A7
0x180002065  xor     ecx, ecx
0x180002067  lea     eax, [r10+7]
0x18000206b  cpuid
0x18000206d  mov     esi, edx
0x18000206f  mov     r9d, ebx
0x180002072  bt      ebx, 9
0x180002076  jnb     short loc_180002083
0x180002078  or      r8d, 2
0x18000207c  mov     cs:__favor, r8d
0x180002083  cmp     eax, 1
0x180002086  jl      short loc_180002095
0x180002088  mov     eax, 7
0x18000208d  lea     ecx, [rax-6]
0x180002090  cpuid
0x180002092  mov     r10d, edx
0x180002095  mov     eax, 24h ; '$'
0x18000209a  cmp     ebp, eax
0x18000209c  jl      short loc_1800020AC
0x18000209e  xor     ecx, ecx
0x1800020a0  cpuid
0x1800020a2  mov     r11d, ebx
0x1800020a5  jmp     short loc_1800020AC
0x1800020a7  xor     r9d, r9d
0x1800020aa  xor     esi, esi
0x1800020ac  mov     rax, cs:__isa_inverted
0x1800020b3  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800020b7  mov     cs:__isa_available, 1
0x1800020c1  mov     cs:__isa_enabled, 2
0x1800020cb  mov     cs:__isa_inverted, rax
0x1800020d2  bt      edi, 14h
0x1800020d6  jnb     short loc_1800020F7
0x1800020d8  and     rax, 0FFFFFFFFFFFFFFEFh
0x1800020dc  mov     cs:__isa_available, 2
0x1800020e6  mov     cs:__isa_inverted, rax
0x1800020ed  mov     cs:__isa_enabled, 6
0x1800020f7  bt      edi, 1Bh
0x1800020fb  jnb     loc_180002238
0x180002101  xor     ecx, ecx
0x180002103  xgetbv
0x180002106  shl     rdx, 20h
0x18000210a  or      rdx, rax
0x18000210d  mov     [rsp+38h+arg_0], rdx
0x180002112  bt      edi, 1Ch
0x180002116  jnb     loc_18000221C
0x18000211c  mov     rax, [rsp+38h+arg_0]
0x180002121  and     al, 6
0x180002123  cmp     al, 6
0x180002125  jnz     loc_18000221C
0x18000212b  mov     eax, cs:__isa_enabled
0x180002131  mov     dl, 0E0h
0x180002133  or      eax, 8
0x180002136  mov     cs:__isa_available, 3
0x180002140  mov     cs:__isa_enabled, eax
0x180002146  test    r9b, 20h
0x18000214a  jz      short loc_1800021AE
0x18000214c  or      eax, 20h
0x18000214f  mov     cs:__isa_available, 5
0x180002159  mov     cs:__isa_enabled, eax
0x18000215f  mov     ecx, 0D0030000h
0x180002164  mov     rax, cs:__isa_inverted
0x18000216b  and     r9d, ecx
0x18000216e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180002172  mov     cs:__isa_inverted, rax
0x180002179  cmp     r9d, ecx
0x18000217c  jnz     short loc_1800021B5
0x18000217e  mov     rax, [rsp+38h+arg_0]
0x180002183  and     al, dl
0x180002185  cmp     al, dl
0x180002187  jnz     short loc_1800021AE
0x180002189  mov     rax, cs:__isa_inverted
0x180002190  or      cs:__isa_enabled, 40h
0x180002197  and     rax, 0FFFFFFFFFFFFFFDBh
0x18000219b  mov     cs:__isa_available, 6
0x1800021a5  mov     cs:__isa_inverted, rax
0x1800021ac  jmp     short loc_1800021B5
0x1800021ae  mov     rax, cs:__isa_inverted
0x1800021b5  bt      esi, 17h
0x1800021b9  jnb     short loc_1800021C7
0x1800021bb  btr     rax, 18h
0x1800021c0  mov     cs:__isa_inverted, rax
0x1800021c7  bt      r10d, 13h
0x1800021cc  jnb     short loc_18000221C
0x1800021ce  mov     rax, [rsp+38h+arg_0]
0x1800021d3  and     al, dl
0x1800021d5  cmp     al, dl
0x1800021d7  jnz     short loc_18000221C
0x1800021d9  mov     rdx, cs:__isa_inverted
0x1800021e0  mov     eax, r11d
0x1800021e3  shr     rax, 10h
0x1800021e7  mov     ecx, r11d
0x1800021ea  and     eax, 6
0x1800021ed  and     ecx, 400FFh
0x1800021f3  or      rax, 1000029h
0x1800021f9  mov     cs:__avx10_version, ecx
0x1800021ff  not     rax
0x180002202  and     rdx, rax
0x180002205  mov     cs:__isa_inverted, rdx
0x18000220c  cmp     cl, 1
0x18000220f  jbe     short loc_18000221C
0x180002211  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180002215  mov     cs:__isa_inverted, rdx
0x18000221c  bt      r10d, 15h
0x180002221  jnb     short loc_180002238
0x180002223  mov     rax, [rsp+38h+arg_0]
0x180002228  bt      rax, 13h
0x18000222d  jnb     short loc_180002238
0x18000222f  btr     cs:__isa_inverted, 7
0x180002238  xor     eax, eax
0x18000223a  add     rsp, 18h
0x18000223e  pop     rdi
0x18000223f  pop     rsi
0x180002240  pop     rbp
0x180002241  pop     rbx
0x180002242  retn
```
