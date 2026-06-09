# __isa_available_init

- ea: `0x180001b30`
- end: `0x180001db3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015c4`
- `0x180001700`

## callees

- `0x180001b30`

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
0x180001b30  push    rbx
0x180001b32  push    rbp
0x180001b33  push    rsi
0x180001b34  push    rdi
0x180001b35  sub     rsp, 18h
0x180001b39  xor     eax, eax
0x180001b3b  xor     ecx, ecx
0x180001b3d  cpuid
0x180001b3f  xor     ecx, 6C65746Eh
0x180001b45  xor     edx, 49656E69h
0x180001b4b  or      edx, ecx
0x180001b4d  mov     ebp, eax
0x180001b4f  mov     eax, 1
0x180001b54  xor     ebx, 756E6547h
0x180001b5a  or      edx, ebx
0x180001b5c  lea     ecx, [rax-1]
0x180001b5f  cpuid
0x180001b61  mov     edi, ecx
0x180001b63  jnz     short loc_180001BC3
0x180001b65  and     eax, 0FFF3FF0h
0x180001b6a  mov     cs:__memset_fast_string_threshold, 8000h
0x180001b75  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001b80  cmp     eax, 106C0h
0x180001b85  jz      short loc_180001BAF
0x180001b87  cmp     eax, 20660h
0x180001b8c  jz      short loc_180001BAF
0x180001b8e  cmp     eax, 20670h
0x180001b93  jz      short loc_180001BAF
0x180001b95  add     eax, 0FFFCF9B0h
0x180001b9a  cmp     eax, 20h ; ' '
0x180001b9d  ja      short loc_180001BC3
0x180001b9f  mov     rcx, 100010001h
0x180001ba9  bt      rcx, rax
0x180001bad  jnb     short loc_180001BC3
0x180001baf  mov     r8d, cs:__favor
0x180001bb6  or      r8d, 1
0x180001bba  mov     cs:__favor, r8d
0x180001bc1  jmp     short loc_180001BCA
0x180001bc3  mov     r8d, cs:__favor
0x180001bca  xor     r10d, r10d
0x180001bcd  xor     r11d, r11d
0x180001bd0  cmp     ebp, 7
0x180001bd3  jl      short loc_180001C17
0x180001bd5  xor     ecx, ecx
0x180001bd7  lea     eax, [r10+7]
0x180001bdb  cpuid
0x180001bdd  mov     esi, edx
0x180001bdf  mov     r9d, ebx
0x180001be2  bt      ebx, 9
0x180001be6  jnb     short loc_180001BF3
0x180001be8  or      r8d, 2
0x180001bec  mov     cs:__favor, r8d
0x180001bf3  cmp     eax, 1
0x180001bf6  jl      short loc_180001C05
0x180001bf8  mov     eax, 7
0x180001bfd  lea     ecx, [rax-6]
0x180001c00  cpuid
0x180001c02  mov     r10d, edx
0x180001c05  mov     eax, 24h ; '$'
0x180001c0a  cmp     ebp, eax
0x180001c0c  jl      short loc_180001C1C
0x180001c0e  xor     ecx, ecx
0x180001c10  cpuid
0x180001c12  mov     r11d, ebx
0x180001c15  jmp     short loc_180001C1C
0x180001c17  xor     r9d, r9d
0x180001c1a  xor     esi, esi
0x180001c1c  mov     rax, cs:__isa_inverted
0x180001c23  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001c27  mov     cs:__isa_available, 1
0x180001c31  mov     cs:__isa_enabled, 2
0x180001c3b  mov     cs:__isa_inverted, rax
0x180001c42  bt      edi, 14h
0x180001c46  jnb     short loc_180001C67
0x180001c48  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001c4c  mov     cs:__isa_available, 2
0x180001c56  mov     cs:__isa_inverted, rax
0x180001c5d  mov     cs:__isa_enabled, 6
0x180001c67  bt      edi, 1Bh
0x180001c6b  jnb     loc_180001DA8
0x180001c71  xor     ecx, ecx
0x180001c73  xgetbv
0x180001c76  shl     rdx, 20h
0x180001c7a  or      rdx, rax
0x180001c7d  mov     [rsp+38h+arg_0], rdx
0x180001c82  bt      edi, 1Ch
0x180001c86  jnb     loc_180001D8C
0x180001c8c  mov     rax, [rsp+38h+arg_0]
0x180001c91  and     al, 6
0x180001c93  cmp     al, 6
0x180001c95  jnz     loc_180001D8C
0x180001c9b  mov     eax, cs:__isa_enabled
0x180001ca1  mov     dl, 0E0h
0x180001ca3  or      eax, 8
0x180001ca6  mov     cs:__isa_available, 3
0x180001cb0  mov     cs:__isa_enabled, eax
0x180001cb6  test    r9b, 20h
0x180001cba  jz      short loc_180001D1E
0x180001cbc  or      eax, 20h
0x180001cbf  mov     cs:__isa_available, 5
0x180001cc9  mov     cs:__isa_enabled, eax
0x180001ccf  mov     ecx, 0D0030000h
0x180001cd4  mov     rax, cs:__isa_inverted
0x180001cdb  and     r9d, ecx
0x180001cde  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001ce2  mov     cs:__isa_inverted, rax
0x180001ce9  cmp     r9d, ecx
0x180001cec  jnz     short loc_180001D25
0x180001cee  mov     rax, [rsp+38h+arg_0]
0x180001cf3  and     al, dl
0x180001cf5  cmp     al, dl
0x180001cf7  jnz     short loc_180001D1E
0x180001cf9  mov     rax, cs:__isa_inverted
0x180001d00  or      cs:__isa_enabled, 40h
0x180001d07  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001d0b  mov     cs:__isa_available, 6
0x180001d15  mov     cs:__isa_inverted, rax
0x180001d1c  jmp     short loc_180001D25
0x180001d1e  mov     rax, cs:__isa_inverted
0x180001d25  bt      esi, 17h
0x180001d29  jnb     short loc_180001D37
0x180001d2b  btr     rax, 18h
0x180001d30  mov     cs:__isa_inverted, rax
0x180001d37  bt      r10d, 13h
0x180001d3c  jnb     short loc_180001D8C
0x180001d3e  mov     rax, [rsp+38h+arg_0]
0x180001d43  and     al, dl
0x180001d45  cmp     al, dl
0x180001d47  jnz     short loc_180001D8C
0x180001d49  mov     rdx, cs:__isa_inverted
0x180001d50  mov     eax, r11d
0x180001d53  shr     rax, 10h
0x180001d57  mov     ecx, r11d
0x180001d5a  and     eax, 6
0x180001d5d  and     ecx, 400FFh
0x180001d63  or      rax, 1000029h
0x180001d69  mov     cs:__avx10_version, ecx
0x180001d6f  not     rax
0x180001d72  and     rdx, rax
0x180001d75  mov     cs:__isa_inverted, rdx
0x180001d7c  cmp     cl, 1
0x180001d7f  jbe     short loc_180001D8C
0x180001d81  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001d85  mov     cs:__isa_inverted, rdx
0x180001d8c  bt      r10d, 15h
0x180001d91  jnb     short loc_180001DA8
0x180001d93  mov     rax, [rsp+38h+arg_0]
0x180001d98  bt      rax, 13h
0x180001d9d  jnb     short loc_180001DA8
0x180001d9f  btr     cs:__isa_inverted, 7
0x180001da8  xor     eax, eax
0x180001daa  add     rsp, 18h
0x180001dae  pop     rdi
0x180001daf  pop     rsi
0x180001db0  pop     rbp
0x180001db1  pop     rbx
0x180001db2  retn
```
