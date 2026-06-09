# __isa_available_init

- ea: `0x180001f00`
- end: `0x180002183`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001944`
- `0x180001a80`

## callees

- `0x180001f00`

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
0x180001f00  push    rbx
0x180001f02  push    rbp
0x180001f03  push    rsi
0x180001f04  push    rdi
0x180001f05  sub     rsp, 18h
0x180001f09  xor     eax, eax
0x180001f0b  xor     ecx, ecx
0x180001f0d  cpuid
0x180001f0f  xor     ecx, 6C65746Eh
0x180001f15  xor     edx, 49656E69h
0x180001f1b  or      edx, ecx
0x180001f1d  mov     ebp, eax
0x180001f1f  mov     eax, 1
0x180001f24  xor     ebx, 756E6547h
0x180001f2a  or      edx, ebx
0x180001f2c  lea     ecx, [rax-1]
0x180001f2f  cpuid
0x180001f31  mov     edi, ecx
0x180001f33  jnz     short loc_180001F93
0x180001f35  and     eax, 0FFF3FF0h
0x180001f3a  mov     cs:__memset_fast_string_threshold, 8000h
0x180001f45  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001f50  cmp     eax, 106C0h
0x180001f55  jz      short loc_180001F7F
0x180001f57  cmp     eax, 20660h
0x180001f5c  jz      short loc_180001F7F
0x180001f5e  cmp     eax, 20670h
0x180001f63  jz      short loc_180001F7F
0x180001f65  add     eax, 0FFFCF9B0h
0x180001f6a  cmp     eax, 20h ; ' '
0x180001f6d  ja      short loc_180001F93
0x180001f6f  mov     rcx, 100010001h
0x180001f79  bt      rcx, rax
0x180001f7d  jnb     short loc_180001F93
0x180001f7f  mov     r8d, cs:__favor
0x180001f86  or      r8d, 1
0x180001f8a  mov     cs:__favor, r8d
0x180001f91  jmp     short loc_180001F9A
0x180001f93  mov     r8d, cs:__favor
0x180001f9a  xor     r10d, r10d
0x180001f9d  xor     r11d, r11d
0x180001fa0  cmp     ebp, 7
0x180001fa3  jl      short loc_180001FE7
0x180001fa5  xor     ecx, ecx
0x180001fa7  lea     eax, [r10+7]
0x180001fab  cpuid
0x180001fad  mov     esi, edx
0x180001faf  mov     r9d, ebx
0x180001fb2  bt      ebx, 9
0x180001fb6  jnb     short loc_180001FC3
0x180001fb8  or      r8d, 2
0x180001fbc  mov     cs:__favor, r8d
0x180001fc3  cmp     eax, 1
0x180001fc6  jl      short loc_180001FD5
0x180001fc8  mov     eax, 7
0x180001fcd  lea     ecx, [rax-6]
0x180001fd0  cpuid
0x180001fd2  mov     r10d, edx
0x180001fd5  mov     eax, 24h ; '$'
0x180001fda  cmp     ebp, eax
0x180001fdc  jl      short loc_180001FEC
0x180001fde  xor     ecx, ecx
0x180001fe0  cpuid
0x180001fe2  mov     r11d, ebx
0x180001fe5  jmp     short loc_180001FEC
0x180001fe7  xor     r9d, r9d
0x180001fea  xor     esi, esi
0x180001fec  mov     rax, cs:__isa_inverted
0x180001ff3  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001ff7  mov     cs:__isa_available, 1
0x180002001  mov     cs:__isa_enabled, 2
0x18000200b  mov     cs:__isa_inverted, rax
0x180002012  bt      edi, 14h
0x180002016  jnb     short loc_180002037
0x180002018  and     rax, 0FFFFFFFFFFFFFFEFh
0x18000201c  mov     cs:__isa_available, 2
0x180002026  mov     cs:__isa_inverted, rax
0x18000202d  mov     cs:__isa_enabled, 6
0x180002037  bt      edi, 1Bh
0x18000203b  jnb     loc_180002178
0x180002041  xor     ecx, ecx
0x180002043  xgetbv
0x180002046  shl     rdx, 20h
0x18000204a  or      rdx, rax
0x18000204d  mov     [rsp+38h+arg_0], rdx
0x180002052  bt      edi, 1Ch
0x180002056  jnb     loc_18000215C
0x18000205c  mov     rax, [rsp+38h+arg_0]
0x180002061  and     al, 6
0x180002063  cmp     al, 6
0x180002065  jnz     loc_18000215C
0x18000206b  mov     eax, cs:__isa_enabled
0x180002071  mov     dl, 0E0h
0x180002073  or      eax, 8
0x180002076  mov     cs:__isa_available, 3
0x180002080  mov     cs:__isa_enabled, eax
0x180002086  test    r9b, 20h
0x18000208a  jz      short loc_1800020EE
0x18000208c  or      eax, 20h
0x18000208f  mov     cs:__isa_available, 5
0x180002099  mov     cs:__isa_enabled, eax
0x18000209f  mov     ecx, 0D0030000h
0x1800020a4  mov     rax, cs:__isa_inverted
0x1800020ab  and     r9d, ecx
0x1800020ae  and     rax, 0FFFFFFFFFFFFFFFDh
0x1800020b2  mov     cs:__isa_inverted, rax
0x1800020b9  cmp     r9d, ecx
0x1800020bc  jnz     short loc_1800020F5
0x1800020be  mov     rax, [rsp+38h+arg_0]
0x1800020c3  and     al, dl
0x1800020c5  cmp     al, dl
0x1800020c7  jnz     short loc_1800020EE
0x1800020c9  mov     rax, cs:__isa_inverted
0x1800020d0  or      cs:__isa_enabled, 40h
0x1800020d7  and     rax, 0FFFFFFFFFFFFFFDBh
0x1800020db  mov     cs:__isa_available, 6
0x1800020e5  mov     cs:__isa_inverted, rax
0x1800020ec  jmp     short loc_1800020F5
0x1800020ee  mov     rax, cs:__isa_inverted
0x1800020f5  bt      esi, 17h
0x1800020f9  jnb     short loc_180002107
0x1800020fb  btr     rax, 18h
0x180002100  mov     cs:__isa_inverted, rax
0x180002107  bt      r10d, 13h
0x18000210c  jnb     short loc_18000215C
0x18000210e  mov     rax, [rsp+38h+arg_0]
0x180002113  and     al, dl
0x180002115  cmp     al, dl
0x180002117  jnz     short loc_18000215C
0x180002119  mov     rdx, cs:__isa_inverted
0x180002120  mov     eax, r11d
0x180002123  shr     rax, 10h
0x180002127  mov     ecx, r11d
0x18000212a  and     eax, 6
0x18000212d  and     ecx, 400FFh
0x180002133  or      rax, 1000029h
0x180002139  mov     cs:__avx10_version, ecx
0x18000213f  not     rax
0x180002142  and     rdx, rax
0x180002145  mov     cs:__isa_inverted, rdx
0x18000214c  cmp     cl, 1
0x18000214f  jbe     short loc_18000215C
0x180002151  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180002155  mov     cs:__isa_inverted, rdx
0x18000215c  bt      r10d, 15h
0x180002161  jnb     short loc_180002178
0x180002163  mov     rax, [rsp+38h+arg_0]
0x180002168  bt      rax, 13h
0x18000216d  jnb     short loc_180002178
0x18000216f  btr     cs:__isa_inverted, 7
0x180002178  xor     eax, eax
0x18000217a  add     rsp, 18h
0x18000217e  pop     rdi
0x18000217f  pop     rsi
0x180002180  pop     rbp
0x180002181  pop     rbx
0x180002182  retn
```
