# __isa_available_init

- ea: `0x180009050`
- end: `0x1800092d3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008ae4`
- `0x180008c20`

## callees

- `0x180009050`

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
0x180009050  push    rbx
0x180009052  push    rbp
0x180009053  push    rsi
0x180009054  push    rdi
0x180009055  sub     rsp, 18h
0x180009059  xor     eax, eax
0x18000905b  xor     ecx, ecx
0x18000905d  cpuid
0x18000905f  xor     ecx, 6C65746Eh
0x180009065  xor     edx, 49656E69h
0x18000906b  or      edx, ecx
0x18000906d  mov     ebp, eax
0x18000906f  mov     eax, 1
0x180009074  xor     ebx, 756E6547h
0x18000907a  or      edx, ebx
0x18000907c  lea     ecx, [rax-1]
0x18000907f  cpuid
0x180009081  mov     edi, ecx
0x180009083  jnz     short loc_1800090E3
0x180009085  and     eax, 0FFF3FF0h
0x18000908a  mov     cs:__memset_fast_string_threshold, 8000h
0x180009095  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1800090a0  cmp     eax, 106C0h
0x1800090a5  jz      short loc_1800090CF
0x1800090a7  cmp     eax, 20660h
0x1800090ac  jz      short loc_1800090CF
0x1800090ae  cmp     eax, 20670h
0x1800090b3  jz      short loc_1800090CF
0x1800090b5  add     eax, 0FFFCF9B0h
0x1800090ba  cmp     eax, 20h ; ' '
0x1800090bd  ja      short loc_1800090E3
0x1800090bf  mov     rcx, 100010001h
0x1800090c9  bt      rcx, rax
0x1800090cd  jnb     short loc_1800090E3
0x1800090cf  mov     r8d, cs:__favor
0x1800090d6  or      r8d, 1
0x1800090da  mov     cs:__favor, r8d
0x1800090e1  jmp     short loc_1800090EA
0x1800090e3  mov     r8d, cs:__favor
0x1800090ea  xor     r10d, r10d
0x1800090ed  xor     r11d, r11d
0x1800090f0  cmp     ebp, 7
0x1800090f3  jl      short loc_180009137
0x1800090f5  xor     ecx, ecx
0x1800090f7  lea     eax, [r10+7]
0x1800090fb  cpuid
0x1800090fd  mov     esi, edx
0x1800090ff  mov     r9d, ebx
0x180009102  bt      ebx, 9
0x180009106  jnb     short loc_180009113
0x180009108  or      r8d, 2
0x18000910c  mov     cs:__favor, r8d
0x180009113  cmp     eax, 1
0x180009116  jl      short loc_180009125
0x180009118  mov     eax, 7
0x18000911d  lea     ecx, [rax-6]
0x180009120  cpuid
0x180009122  mov     r10d, edx
0x180009125  mov     eax, 24h ; '$'
0x18000912a  cmp     ebp, eax
0x18000912c  jl      short loc_18000913C
0x18000912e  xor     ecx, ecx
0x180009130  cpuid
0x180009132  mov     r11d, ebx
0x180009135  jmp     short loc_18000913C
0x180009137  xor     r9d, r9d
0x18000913a  xor     esi, esi
0x18000913c  mov     rax, cs:__isa_inverted
0x180009143  and     rax, 0FFFFFFFFFFFFFFFEh
0x180009147  mov     cs:__isa_available, 1
0x180009151  mov     cs:__isa_enabled, 2
0x18000915b  mov     cs:__isa_inverted, rax
0x180009162  bt      edi, 14h
0x180009166  jnb     short loc_180009187
0x180009168  and     rax, 0FFFFFFFFFFFFFFEFh
0x18000916c  mov     cs:__isa_available, 2
0x180009176  mov     cs:__isa_inverted, rax
0x18000917d  mov     cs:__isa_enabled, 6
0x180009187  bt      edi, 1Bh
0x18000918b  jnb     loc_1800092C8
0x180009191  xor     ecx, ecx
0x180009193  xgetbv
0x180009196  shl     rdx, 20h
0x18000919a  or      rdx, rax
0x18000919d  mov     [rsp+38h+arg_0], rdx
0x1800091a2  bt      edi, 1Ch
0x1800091a6  jnb     loc_1800092AC
0x1800091ac  mov     rax, [rsp+38h+arg_0]
0x1800091b1  and     al, 6
0x1800091b3  cmp     al, 6
0x1800091b5  jnz     loc_1800092AC
0x1800091bb  mov     eax, cs:__isa_enabled
0x1800091c1  mov     dl, 0E0h
0x1800091c3  or      eax, 8
0x1800091c6  mov     cs:__isa_available, 3
0x1800091d0  mov     cs:__isa_enabled, eax
0x1800091d6  test    r9b, 20h
0x1800091da  jz      short loc_18000923E
0x1800091dc  or      eax, 20h
0x1800091df  mov     cs:__isa_available, 5
0x1800091e9  mov     cs:__isa_enabled, eax
0x1800091ef  mov     ecx, 0D0030000h
0x1800091f4  mov     rax, cs:__isa_inverted
0x1800091fb  and     r9d, ecx
0x1800091fe  and     rax, 0FFFFFFFFFFFFFFFDh
0x180009202  mov     cs:__isa_inverted, rax
0x180009209  cmp     r9d, ecx
0x18000920c  jnz     short loc_180009245
0x18000920e  mov     rax, [rsp+38h+arg_0]
0x180009213  and     al, dl
0x180009215  cmp     al, dl
0x180009217  jnz     short loc_18000923E
0x180009219  mov     rax, cs:__isa_inverted
0x180009220  or      cs:__isa_enabled, 40h
0x180009227  and     rax, 0FFFFFFFFFFFFFFDBh
0x18000922b  mov     cs:__isa_available, 6
0x180009235  mov     cs:__isa_inverted, rax
0x18000923c  jmp     short loc_180009245
0x18000923e  mov     rax, cs:__isa_inverted
0x180009245  bt      esi, 17h
0x180009249  jnb     short loc_180009257
0x18000924b  btr     rax, 18h
0x180009250  mov     cs:__isa_inverted, rax
0x180009257  bt      r10d, 13h
0x18000925c  jnb     short loc_1800092AC
0x18000925e  mov     rax, [rsp+38h+arg_0]
0x180009263  and     al, dl
0x180009265  cmp     al, dl
0x180009267  jnz     short loc_1800092AC
0x180009269  mov     rdx, cs:__isa_inverted
0x180009270  mov     eax, r11d
0x180009273  shr     rax, 10h
0x180009277  mov     ecx, r11d
0x18000927a  and     eax, 6
0x18000927d  and     ecx, 400FFh
0x180009283  or      rax, 1000029h
0x180009289  mov     cs:__avx10_version, ecx
0x18000928f  not     rax
0x180009292  and     rdx, rax
0x180009295  mov     cs:__isa_inverted, rdx
0x18000929c  cmp     cl, 1
0x18000929f  jbe     short loc_1800092AC
0x1800092a1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x1800092a5  mov     cs:__isa_inverted, rdx
0x1800092ac  bt      r10d, 15h
0x1800092b1  jnb     short loc_1800092C8
0x1800092b3  mov     rax, [rsp+38h+arg_0]
0x1800092b8  bt      rax, 13h
0x1800092bd  jnb     short loc_1800092C8
0x1800092bf  btr     cs:__isa_inverted, 7
0x1800092c8  xor     eax, eax
0x1800092ca  add     rsp, 18h
0x1800092ce  pop     rdi
0x1800092cf  pop     rsi
0x1800092d0  pop     rbp
0x1800092d1  pop     rbx
0x1800092d2  retn
```
