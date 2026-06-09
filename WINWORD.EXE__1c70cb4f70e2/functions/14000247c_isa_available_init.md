# __isa_available_init

- ea: `0x14000247c`
- end: `0x140002711`
- name: `__isa_available_init`
- size: `661`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001abc`

## callees

- `0x14000247c`

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
0x14000247c  mov     [rsp+arg_8], rbx
0x140002481  mov     [rsp+arg_10], rbp
0x140002486  mov     [rsp+arg_18], rsi
0x14000248b  push    rdi
0x14000248c  sub     rsp, 10h
0x140002490  xor     eax, eax
0x140002492  xor     ecx, ecx
0x140002494  cpuid
0x140002496  xor     ecx, 6C65746Eh
0x14000249c  xor     edx, 49656E69h
0x1400024a2  or      edx, ecx
0x1400024a4  mov     ebp, eax
0x1400024a6  mov     eax, 1
0x1400024ab  xor     ebx, 756E6547h
0x1400024b1  or      edx, ebx
0x1400024b3  lea     ecx, [rax-1]
0x1400024b6  cpuid
0x1400024b8  mov     edi, ecx
0x1400024ba  jnz     short loc_14000251A
0x1400024bc  and     eax, 0FFF3FF0h
0x1400024c1  mov     cs:__memset_fast_string_threshold, 8000h
0x1400024cc  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1400024d7  cmp     eax, 106C0h
0x1400024dc  jz      short loc_140002506
0x1400024de  cmp     eax, 20660h
0x1400024e3  jz      short loc_140002506
0x1400024e5  cmp     eax, 20670h
0x1400024ea  jz      short loc_140002506
0x1400024ec  add     eax, 0FFFCF9B0h
0x1400024f1  cmp     eax, 20h ; ' '
0x1400024f4  ja      short loc_14000251A
0x1400024f6  mov     rcx, 100010001h
0x140002500  bt      rcx, rax
0x140002504  jnb     short loc_14000251A
0x140002506  mov     r8d, cs:__favor
0x14000250d  or      r8d, 1
0x140002511  mov     cs:__favor, r8d
0x140002518  jmp     short loc_140002521
0x14000251a  mov     r8d, cs:__favor
0x140002521  xor     r9d, r9d
0x140002524  mov     esi, r9d
0x140002527  mov     r10d, r9d
0x14000252a  mov     r11d, r9d
0x14000252d  cmp     ebp, 7
0x140002530  jl      short loc_140002572
0x140002532  lea     eax, [r9+7]
0x140002536  xor     ecx, ecx
0x140002538  cpuid
0x14000253a  mov     esi, edx
0x14000253c  mov     r9d, ebx
0x14000253f  bt      ebx, 9
0x140002543  jnb     short loc_140002550
0x140002545  or      r8d, 2
0x140002549  mov     cs:__favor, r8d
0x140002550  cmp     eax, 1
0x140002553  jl      short loc_140002562
0x140002555  mov     eax, 7
0x14000255a  lea     ecx, [rax-6]
0x14000255d  cpuid
0x14000255f  mov     r10d, edx
0x140002562  mov     eax, 24h ; '$'
0x140002567  cmp     ebp, eax
0x140002569  jl      short loc_140002572
0x14000256b  xor     ecx, ecx
0x14000256d  cpuid
0x14000256f  mov     r11d, ebx
0x140002572  mov     rax, cs:__isa_inverted
0x140002579  and     rax, 0FFFFFFFFFFFFFFFEh
0x14000257d  mov     cs:__isa_available, 1
0x140002587  mov     cs:__isa_enabled, 2
0x140002591  mov     cs:__isa_inverted, rax
0x140002598  bt      edi, 14h
0x14000259c  jnb     short loc_1400025BD
0x14000259e  and     rax, 0FFFFFFFFFFFFFFEFh
0x1400025a2  mov     cs:__isa_available, 2
0x1400025ac  mov     cs:__isa_inverted, rax
0x1400025b3  mov     cs:__isa_enabled, 6
0x1400025bd  bt      edi, 1Bh
0x1400025c1  jnb     loc_1400026FA
0x1400025c7  xor     ecx, ecx
0x1400025c9  xgetbv
0x1400025cc  shl     rdx, 20h
0x1400025d0  or      rdx, rax
0x1400025d3  mov     [rsp+18h+arg_0], rdx
0x1400025d8  bt      edi, 1Ch
0x1400025dc  jnb     loc_1400026DE
0x1400025e2  mov     rax, [rsp+18h+arg_0]
0x1400025e7  and     al, 6
0x1400025e9  cmp     al, 6
0x1400025eb  jnz     loc_1400026DE
0x1400025f1  mov     eax, cs:__isa_enabled
0x1400025f7  mov     dl, 0E0h
0x1400025f9  or      eax, 8
0x1400025fc  mov     cs:__isa_available, 3
0x140002606  mov     cs:__isa_enabled, eax
0x14000260c  test    r9b, 20h
0x140002610  jz      short loc_140002674
0x140002612  or      eax, 20h
0x140002615  mov     cs:__isa_available, 5
0x14000261f  mov     cs:__isa_enabled, eax
0x140002625  mov     ecx, 0D0030000h
0x14000262a  mov     rax, cs:__isa_inverted
0x140002631  and     r9d, ecx
0x140002634  and     rax, 0FFFFFFFFFFFFFFFDh
0x140002638  mov     cs:__isa_inverted, rax
0x14000263f  cmp     r9d, ecx
0x140002642  jnz     short loc_14000267B
0x140002644  mov     rax, [rsp+18h+arg_0]
0x140002649  and     al, dl
0x14000264b  cmp     al, dl
0x14000264d  jnz     short loc_140002674
0x14000264f  mov     rax, cs:__isa_inverted
0x140002656  or      cs:__isa_enabled, 40h
0x14000265d  and     rax, 0FFFFFFFFFFFFFFDBh
0x140002661  mov     cs:__isa_available, 6
0x14000266b  mov     cs:__isa_inverted, rax
0x140002672  jmp     short loc_14000267B
0x140002674  mov     rax, cs:__isa_inverted
0x14000267b  bt      esi, 17h
0x14000267f  jnb     short loc_14000268D
0x140002681  btr     rax, 18h
0x140002686  mov     cs:__isa_inverted, rax
0x14000268d  bt      r10d, 13h
0x140002692  jnb     short loc_1400026DE
0x140002694  mov     rax, [rsp+18h+arg_0]
0x140002699  and     al, dl
0x14000269b  cmp     al, dl
0x14000269d  jnz     short loc_1400026DE
0x14000269f  mov     ecx, r11d
0x1400026a2  mov     eax, r11d
0x1400026a5  shr     rcx, 10h
0x1400026a9  and     eax, 400FFh
0x1400026ae  and     ecx, 6
0x1400026b1  mov     cs:__avx10_version, eax
0x1400026b7  or      rcx, 1000029h
0x1400026be  not     rcx
0x1400026c1  and     rcx, cs:__isa_inverted
0x1400026c8  mov     cs:__isa_inverted, rcx
0x1400026cf  cmp     al, 1
0x1400026d1  jbe     short loc_1400026DE
0x1400026d3  and     rcx, 0FFFFFFFFFFFFFFBFh
0x1400026d7  mov     cs:__isa_inverted, rcx
0x1400026de  bt      r10d, 15h
0x1400026e3  jnb     short loc_1400026FA
0x1400026e5  mov     rax, [rsp+18h+arg_0]
0x1400026ea  bt      rax, 13h
0x1400026ef  jnb     short loc_1400026FA
0x1400026f1  btr     cs:__isa_inverted, 7
0x1400026fa  mov     rbx, [rsp+18h+arg_8]
0x1400026ff  xor     eax, eax
0x140002701  mov     rbp, [rsp+18h+arg_10]
0x140002706  mov     rsi, [rsp+18h+arg_18]
0x14000270b  add     rsp, 10h
0x14000270f  pop     rdi
0x140002710  retn
```
