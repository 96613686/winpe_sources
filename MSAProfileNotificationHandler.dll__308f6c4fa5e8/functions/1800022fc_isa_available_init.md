# __isa_available_init

- ea: `0x1800022fc`
- end: `0x18000257f`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e70`
- `0x180001fac`

## callees

- `0x1800022fc`

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
0x1800022fc  push    rbx
0x1800022fe  push    rbp
0x1800022ff  push    rsi
0x180002300  push    rdi
0x180002301  sub     rsp, 18h
0x180002305  xor     eax, eax
0x180002307  xor     ecx, ecx
0x180002309  cpuid
0x18000230b  xor     ecx, 6C65746Eh
0x180002311  xor     edx, 49656E69h
0x180002317  or      edx, ecx
0x180002319  mov     ebp, eax
0x18000231b  mov     eax, 1
0x180002320  xor     ebx, 756E6547h
0x180002326  or      edx, ebx
0x180002328  lea     ecx, [rax-1]
0x18000232b  cpuid
0x18000232d  mov     edi, ecx
0x18000232f  jnz     short loc_18000238F
0x180002331  and     eax, 0FFF3FF0h
0x180002336  mov     cs:__memset_fast_string_threshold, 8000h
0x180002341  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x18000234c  cmp     eax, 106C0h
0x180002351  jz      short loc_18000237B
0x180002353  cmp     eax, 20660h
0x180002358  jz      short loc_18000237B
0x18000235a  cmp     eax, 20670h
0x18000235f  jz      short loc_18000237B
0x180002361  add     eax, 0FFFCF9B0h
0x180002366  cmp     eax, 20h ; ' '
0x180002369  ja      short loc_18000238F
0x18000236b  mov     rcx, 100010001h
0x180002375  bt      rcx, rax
0x180002379  jnb     short loc_18000238F
0x18000237b  mov     r8d, cs:__favor
0x180002382  or      r8d, 1
0x180002386  mov     cs:__favor, r8d
0x18000238d  jmp     short loc_180002396
0x18000238f  mov     r8d, cs:__favor
0x180002396  xor     r10d, r10d
0x180002399  xor     r11d, r11d
0x18000239c  cmp     ebp, 7
0x18000239f  jl      short loc_1800023E3
0x1800023a1  xor     ecx, ecx
0x1800023a3  lea     eax, [r10+7]
0x1800023a7  cpuid
0x1800023a9  mov     esi, edx
0x1800023ab  mov     r9d, ebx
0x1800023ae  bt      ebx, 9
0x1800023b2  jnb     short loc_1800023BF
0x1800023b4  or      r8d, 2
0x1800023b8  mov     cs:__favor, r8d
0x1800023bf  cmp     eax, 1
0x1800023c2  jl      short loc_1800023D1
0x1800023c4  mov     eax, 7
0x1800023c9  lea     ecx, [rax-6]
0x1800023cc  cpuid
0x1800023ce  mov     r10d, edx
0x1800023d1  mov     eax, 24h ; '$'
0x1800023d6  cmp     ebp, eax
0x1800023d8  jl      short loc_1800023E8
0x1800023da  xor     ecx, ecx
0x1800023dc  cpuid
0x1800023de  mov     r11d, ebx
0x1800023e1  jmp     short loc_1800023E8
0x1800023e3  xor     r9d, r9d
0x1800023e6  xor     esi, esi
0x1800023e8  mov     rax, cs:__isa_inverted
0x1800023ef  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800023f3  mov     cs:__isa_available, 1
0x1800023fd  mov     cs:__isa_enabled, 2
0x180002407  mov     cs:__isa_inverted, rax
0x18000240e  bt      edi, 14h
0x180002412  jnb     short loc_180002433
0x180002414  and     rax, 0FFFFFFFFFFFFFFEFh
0x180002418  mov     cs:__isa_available, 2
0x180002422  mov     cs:__isa_inverted, rax
0x180002429  mov     cs:__isa_enabled, 6
0x180002433  bt      edi, 1Bh
0x180002437  jnb     loc_180002574
0x18000243d  xor     ecx, ecx
0x18000243f  xgetbv
0x180002442  shl     rdx, 20h
0x180002446  or      rdx, rax
0x180002449  mov     [rsp+38h+arg_0], rdx
0x18000244e  bt      edi, 1Ch
0x180002452  jnb     loc_180002558
0x180002458  mov     rax, [rsp+38h+arg_0]
0x18000245d  and     al, 6
0x18000245f  cmp     al, 6
0x180002461  jnz     loc_180002558
0x180002467  mov     eax, cs:__isa_enabled
0x18000246d  mov     dl, 0E0h
0x18000246f  or      eax, 8
0x180002472  mov     cs:__isa_available, 3
0x18000247c  mov     cs:__isa_enabled, eax
0x180002482  test    r9b, 20h
0x180002486  jz      short loc_1800024EA
0x180002488  or      eax, 20h
0x18000248b  mov     cs:__isa_available, 5
0x180002495  mov     cs:__isa_enabled, eax
0x18000249b  mov     ecx, 0D0030000h
0x1800024a0  mov     rax, cs:__isa_inverted
0x1800024a7  and     r9d, ecx
0x1800024aa  and     rax, 0FFFFFFFFFFFFFFFDh
0x1800024ae  mov     cs:__isa_inverted, rax
0x1800024b5  cmp     r9d, ecx
0x1800024b8  jnz     short loc_1800024F1
0x1800024ba  mov     rax, [rsp+38h+arg_0]
0x1800024bf  and     al, dl
0x1800024c1  cmp     al, dl
0x1800024c3  jnz     short loc_1800024EA
0x1800024c5  mov     rax, cs:__isa_inverted
0x1800024cc  or      cs:__isa_enabled, 40h
0x1800024d3  and     rax, 0FFFFFFFFFFFFFFDBh
0x1800024d7  mov     cs:__isa_available, 6
0x1800024e1  mov     cs:__isa_inverted, rax
0x1800024e8  jmp     short loc_1800024F1
0x1800024ea  mov     rax, cs:__isa_inverted
0x1800024f1  bt      esi, 17h
0x1800024f5  jnb     short loc_180002503
0x1800024f7  btr     rax, 18h
0x1800024fc  mov     cs:__isa_inverted, rax
0x180002503  bt      r10d, 13h
0x180002508  jnb     short loc_180002558
0x18000250a  mov     rax, [rsp+38h+arg_0]
0x18000250f  and     al, dl
0x180002511  cmp     al, dl
0x180002513  jnz     short loc_180002558
0x180002515  mov     rdx, cs:__isa_inverted
0x18000251c  mov     eax, r11d
0x18000251f  shr     rax, 10h
0x180002523  mov     ecx, r11d
0x180002526  and     eax, 6
0x180002529  and     ecx, 400FFh
0x18000252f  or      rax, 1000029h
0x180002535  mov     cs:__avx10_version, ecx
0x18000253b  not     rax
0x18000253e  and     rdx, rax
0x180002541  mov     cs:__isa_inverted, rdx
0x180002548  cmp     cl, 1
0x18000254b  jbe     short loc_180002558
0x18000254d  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180002551  mov     cs:__isa_inverted, rdx
0x180002558  bt      r10d, 15h
0x18000255d  jnb     short loc_180002574
0x18000255f  mov     rax, [rsp+38h+arg_0]
0x180002564  bt      rax, 13h
0x180002569  jnb     short loc_180002574
0x18000256b  btr     cs:__isa_inverted, 7
0x180002574  xor     eax, eax
0x180002576  add     rsp, 18h
0x18000257a  pop     rdi
0x18000257b  pop     rsi
0x18000257c  pop     rbp
0x18000257d  pop     rbx
0x18000257e  retn
```
