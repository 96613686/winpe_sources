# __isa_available_init

- ea: `0x180001c10`
- end: `0x180001e93`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001674`
- `0x1800017b0`

## callees

- `0x180001c10`

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
0x180001c10  push    rbx
0x180001c12  push    rbp
0x180001c13  push    rsi
0x180001c14  push    rdi
0x180001c15  sub     rsp, 18h
0x180001c19  xor     eax, eax
0x180001c1b  xor     ecx, ecx
0x180001c1d  cpuid
0x180001c1f  xor     ecx, 6C65746Eh
0x180001c25  xor     edx, 49656E69h
0x180001c2b  or      edx, ecx
0x180001c2d  mov     ebp, eax
0x180001c2f  mov     eax, 1
0x180001c34  xor     ebx, 756E6547h
0x180001c3a  or      edx, ebx
0x180001c3c  lea     ecx, [rax-1]
0x180001c3f  cpuid
0x180001c41  mov     edi, ecx
0x180001c43  jnz     short loc_180001CA3
0x180001c45  and     eax, 0FFF3FF0h
0x180001c4a  mov     cs:__memset_fast_string_threshold, 8000h
0x180001c55  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001c60  cmp     eax, 106C0h
0x180001c65  jz      short loc_180001C8F
0x180001c67  cmp     eax, 20660h
0x180001c6c  jz      short loc_180001C8F
0x180001c6e  cmp     eax, 20670h
0x180001c73  jz      short loc_180001C8F
0x180001c75  add     eax, 0FFFCF9B0h
0x180001c7a  cmp     eax, 20h ; ' '
0x180001c7d  ja      short loc_180001CA3
0x180001c7f  mov     rcx, 100010001h
0x180001c89  bt      rcx, rax
0x180001c8d  jnb     short loc_180001CA3
0x180001c8f  mov     r8d, cs:__favor
0x180001c96  or      r8d, 1
0x180001c9a  mov     cs:__favor, r8d
0x180001ca1  jmp     short loc_180001CAA
0x180001ca3  mov     r8d, cs:__favor
0x180001caa  xor     r10d, r10d
0x180001cad  xor     r11d, r11d
0x180001cb0  cmp     ebp, 7
0x180001cb3  jl      short loc_180001CF7
0x180001cb5  xor     ecx, ecx
0x180001cb7  lea     eax, [r10+7]
0x180001cbb  cpuid
0x180001cbd  mov     esi, edx
0x180001cbf  mov     r9d, ebx
0x180001cc2  bt      ebx, 9
0x180001cc6  jnb     short loc_180001CD3
0x180001cc8  or      r8d, 2
0x180001ccc  mov     cs:__favor, r8d
0x180001cd3  cmp     eax, 1
0x180001cd6  jl      short loc_180001CE5
0x180001cd8  mov     eax, 7
0x180001cdd  lea     ecx, [rax-6]
0x180001ce0  cpuid
0x180001ce2  mov     r10d, edx
0x180001ce5  mov     eax, 24h ; '$'
0x180001cea  cmp     ebp, eax
0x180001cec  jl      short loc_180001CFC
0x180001cee  xor     ecx, ecx
0x180001cf0  cpuid
0x180001cf2  mov     r11d, ebx
0x180001cf5  jmp     short loc_180001CFC
0x180001cf7  xor     r9d, r9d
0x180001cfa  xor     esi, esi
0x180001cfc  mov     rax, cs:__isa_inverted
0x180001d03  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001d07  mov     cs:__isa_available, 1
0x180001d11  mov     cs:__isa_enabled, 2
0x180001d1b  mov     cs:__isa_inverted, rax
0x180001d22  bt      edi, 14h
0x180001d26  jnb     short loc_180001D47
0x180001d28  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001d2c  mov     cs:__isa_available, 2
0x180001d36  mov     cs:__isa_inverted, rax
0x180001d3d  mov     cs:__isa_enabled, 6
0x180001d47  bt      edi, 1Bh
0x180001d4b  jnb     loc_180001E88
0x180001d51  xor     ecx, ecx
0x180001d53  xgetbv
0x180001d56  shl     rdx, 20h
0x180001d5a  or      rdx, rax
0x180001d5d  mov     [rsp+38h+arg_0], rdx
0x180001d62  bt      edi, 1Ch
0x180001d66  jnb     loc_180001E6C
0x180001d6c  mov     rax, [rsp+38h+arg_0]
0x180001d71  and     al, 6
0x180001d73  cmp     al, 6
0x180001d75  jnz     loc_180001E6C
0x180001d7b  mov     eax, cs:__isa_enabled
0x180001d81  mov     dl, 0E0h
0x180001d83  or      eax, 8
0x180001d86  mov     cs:__isa_available, 3
0x180001d90  mov     cs:__isa_enabled, eax
0x180001d96  test    r9b, 20h
0x180001d9a  jz      short loc_180001DFE
0x180001d9c  or      eax, 20h
0x180001d9f  mov     cs:__isa_available, 5
0x180001da9  mov     cs:__isa_enabled, eax
0x180001daf  mov     ecx, 0D0030000h
0x180001db4  mov     rax, cs:__isa_inverted
0x180001dbb  and     r9d, ecx
0x180001dbe  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001dc2  mov     cs:__isa_inverted, rax
0x180001dc9  cmp     r9d, ecx
0x180001dcc  jnz     short loc_180001E05
0x180001dce  mov     rax, [rsp+38h+arg_0]
0x180001dd3  and     al, dl
0x180001dd5  cmp     al, dl
0x180001dd7  jnz     short loc_180001DFE
0x180001dd9  mov     rax, cs:__isa_inverted
0x180001de0  or      cs:__isa_enabled, 40h
0x180001de7  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001deb  mov     cs:__isa_available, 6
0x180001df5  mov     cs:__isa_inverted, rax
0x180001dfc  jmp     short loc_180001E05
0x180001dfe  mov     rax, cs:__isa_inverted
0x180001e05  bt      esi, 17h
0x180001e09  jnb     short loc_180001E17
0x180001e0b  btr     rax, 18h
0x180001e10  mov     cs:__isa_inverted, rax
0x180001e17  bt      r10d, 13h
0x180001e1c  jnb     short loc_180001E6C
0x180001e1e  mov     rax, [rsp+38h+arg_0]
0x180001e23  and     al, dl
0x180001e25  cmp     al, dl
0x180001e27  jnz     short loc_180001E6C
0x180001e29  mov     rdx, cs:__isa_inverted
0x180001e30  mov     eax, r11d
0x180001e33  shr     rax, 10h
0x180001e37  mov     ecx, r11d
0x180001e3a  and     eax, 6
0x180001e3d  and     ecx, 400FFh
0x180001e43  or      rax, 1000029h
0x180001e49  mov     cs:__avx10_version, ecx
0x180001e4f  not     rax
0x180001e52  and     rdx, rax
0x180001e55  mov     cs:__isa_inverted, rdx
0x180001e5c  cmp     cl, 1
0x180001e5f  jbe     short loc_180001E6C
0x180001e61  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001e65  mov     cs:__isa_inverted, rdx
0x180001e6c  bt      r10d, 15h
0x180001e71  jnb     short loc_180001E88
0x180001e73  mov     rax, [rsp+38h+arg_0]
0x180001e78  bt      rax, 13h
0x180001e7d  jnb     short loc_180001E88
0x180001e7f  btr     cs:__isa_inverted, 7
0x180001e88  xor     eax, eax
0x180001e8a  add     rsp, 18h
0x180001e8e  pop     rdi
0x180001e8f  pop     rsi
0x180001e90  pop     rbp
0x180001e91  pop     rbx
0x180001e92  retn
```
