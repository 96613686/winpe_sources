# __isa_available_init

- ea: `0x180001ef8`
- end: `0x18000217b`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800017d8`
- `0x180001914`

## callees

- `0x180001ef8`

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
0x180001ef8  push    rbx
0x180001efa  push    rbp
0x180001efb  push    rsi
0x180001efc  push    rdi
0x180001efd  sub     rsp, 18h
0x180001f01  xor     eax, eax
0x180001f03  xor     ecx, ecx
0x180001f05  cpuid
0x180001f07  xor     ecx, 6C65746Eh
0x180001f0d  xor     edx, 49656E69h
0x180001f13  or      edx, ecx
0x180001f15  mov     ebp, eax
0x180001f17  mov     eax, 1
0x180001f1c  xor     ebx, 756E6547h
0x180001f22  or      edx, ebx
0x180001f24  lea     ecx, [rax-1]
0x180001f27  cpuid
0x180001f29  mov     edi, ecx
0x180001f2b  jnz     short loc_180001F8B
0x180001f2d  and     eax, 0FFF3FF0h
0x180001f32  mov     cs:__memset_fast_string_threshold, 8000h
0x180001f3d  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001f48  cmp     eax, 106C0h
0x180001f4d  jz      short loc_180001F77
0x180001f4f  cmp     eax, 20660h
0x180001f54  jz      short loc_180001F77
0x180001f56  cmp     eax, 20670h
0x180001f5b  jz      short loc_180001F77
0x180001f5d  add     eax, 0FFFCF9B0h
0x180001f62  cmp     eax, 20h ; ' '
0x180001f65  ja      short loc_180001F8B
0x180001f67  mov     rcx, 100010001h
0x180001f71  bt      rcx, rax
0x180001f75  jnb     short loc_180001F8B
0x180001f77  mov     r8d, cs:__favor
0x180001f7e  or      r8d, 1
0x180001f82  mov     cs:__favor, r8d
0x180001f89  jmp     short loc_180001F92
0x180001f8b  mov     r8d, cs:__favor
0x180001f92  xor     r10d, r10d
0x180001f95  xor     r11d, r11d
0x180001f98  cmp     ebp, 7
0x180001f9b  jl      short loc_180001FDF
0x180001f9d  xor     ecx, ecx
0x180001f9f  lea     eax, [r10+7]
0x180001fa3  cpuid
0x180001fa5  mov     esi, edx
0x180001fa7  mov     r9d, ebx
0x180001faa  bt      ebx, 9
0x180001fae  jnb     short loc_180001FBB
0x180001fb0  or      r8d, 2
0x180001fb4  mov     cs:__favor, r8d
0x180001fbb  cmp     eax, 1
0x180001fbe  jl      short loc_180001FCD
0x180001fc0  mov     eax, 7
0x180001fc5  lea     ecx, [rax-6]
0x180001fc8  cpuid
0x180001fca  mov     r10d, edx
0x180001fcd  mov     eax, 24h ; '$'
0x180001fd2  cmp     ebp, eax
0x180001fd4  jl      short loc_180001FE4
0x180001fd6  xor     ecx, ecx
0x180001fd8  cpuid
0x180001fda  mov     r11d, ebx
0x180001fdd  jmp     short loc_180001FE4
0x180001fdf  xor     r9d, r9d
0x180001fe2  xor     esi, esi
0x180001fe4  mov     rax, cs:__isa_inverted
0x180001feb  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001fef  mov     cs:__isa_available, 1
0x180001ff9  mov     cs:__isa_enabled, 2
0x180002003  mov     cs:__isa_inverted, rax
0x18000200a  bt      edi, 14h
0x18000200e  jnb     short loc_18000202F
0x180002010  and     rax, 0FFFFFFFFFFFFFFEFh
0x180002014  mov     cs:__isa_available, 2
0x18000201e  mov     cs:__isa_inverted, rax
0x180002025  mov     cs:__isa_enabled, 6
0x18000202f  bt      edi, 1Bh
0x180002033  jnb     loc_180002170
0x180002039  xor     ecx, ecx
0x18000203b  xgetbv
0x18000203e  shl     rdx, 20h
0x180002042  or      rdx, rax
0x180002045  mov     [rsp+38h+arg_0], rdx
0x18000204a  bt      edi, 1Ch
0x18000204e  jnb     loc_180002154
0x180002054  mov     rax, [rsp+38h+arg_0]
0x180002059  and     al, 6
0x18000205b  cmp     al, 6
0x18000205d  jnz     loc_180002154
0x180002063  mov     eax, cs:__isa_enabled
0x180002069  mov     dl, 0E0h
0x18000206b  or      eax, 8
0x18000206e  mov     cs:__isa_available, 3
0x180002078  mov     cs:__isa_enabled, eax
0x18000207e  test    r9b, 20h
0x180002082  jz      short loc_1800020E6
0x180002084  or      eax, 20h
0x180002087  mov     cs:__isa_available, 5
0x180002091  mov     cs:__isa_enabled, eax
0x180002097  mov     ecx, 0D0030000h
0x18000209c  mov     rax, cs:__isa_inverted
0x1800020a3  and     r9d, ecx
0x1800020a6  and     rax, 0FFFFFFFFFFFFFFFDh
0x1800020aa  mov     cs:__isa_inverted, rax
0x1800020b1  cmp     r9d, ecx
0x1800020b4  jnz     short loc_1800020ED
0x1800020b6  mov     rax, [rsp+38h+arg_0]
0x1800020bb  and     al, dl
0x1800020bd  cmp     al, dl
0x1800020bf  jnz     short loc_1800020E6
0x1800020c1  mov     rax, cs:__isa_inverted
0x1800020c8  or      cs:__isa_enabled, 40h
0x1800020cf  and     rax, 0FFFFFFFFFFFFFFDBh
0x1800020d3  mov     cs:__isa_available, 6
0x1800020dd  mov     cs:__isa_inverted, rax
0x1800020e4  jmp     short loc_1800020ED
0x1800020e6  mov     rax, cs:__isa_inverted
0x1800020ed  bt      esi, 17h
0x1800020f1  jnb     short loc_1800020FF
0x1800020f3  btr     rax, 18h
0x1800020f8  mov     cs:__isa_inverted, rax
0x1800020ff  bt      r10d, 13h
0x180002104  jnb     short loc_180002154
0x180002106  mov     rax, [rsp+38h+arg_0]
0x18000210b  and     al, dl
0x18000210d  cmp     al, dl
0x18000210f  jnz     short loc_180002154
0x180002111  mov     rdx, cs:__isa_inverted
0x180002118  mov     eax, r11d
0x18000211b  shr     rax, 10h
0x18000211f  mov     ecx, r11d
0x180002122  and     eax, 6
0x180002125  and     ecx, 400FFh
0x18000212b  or      rax, 1000029h
0x180002131  mov     cs:__avx10_version, ecx
0x180002137  not     rax
0x18000213a  and     rdx, rax
0x18000213d  mov     cs:__isa_inverted, rdx
0x180002144  cmp     cl, 1
0x180002147  jbe     short loc_180002154
0x180002149  and     rdx, 0FFFFFFFFFFFFFFBFh
0x18000214d  mov     cs:__isa_inverted, rdx
0x180002154  bt      r10d, 15h
0x180002159  jnb     short loc_180002170
0x18000215b  mov     rax, [rsp+38h+arg_0]
0x180002160  bt      rax, 13h
0x180002165  jnb     short loc_180002170
0x180002167  btr     cs:__isa_inverted, 7
0x180002170  xor     eax, eax
0x180002172  add     rsp, 18h
0x180002176  pop     rdi
0x180002177  pop     rsi
0x180002178  pop     rbp
0x180002179  pop     rbx
0x18000217a  retn
```
