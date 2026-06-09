# __isa_available_init

- ea: `0x180001dc0`
- end: `0x180002043`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800019ec`
- `0x180001b28`

## callees

- `0x180001dc0`

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
0x180001dc0  push    rbx
0x180001dc2  push    rbp
0x180001dc3  push    rsi
0x180001dc4  push    rdi
0x180001dc5  sub     rsp, 18h
0x180001dc9  xor     eax, eax
0x180001dcb  xor     ecx, ecx
0x180001dcd  cpuid
0x180001dcf  xor     ecx, 6C65746Eh
0x180001dd5  xor     edx, 49656E69h
0x180001ddb  or      edx, ecx
0x180001ddd  mov     ebp, eax
0x180001ddf  mov     eax, 1
0x180001de4  xor     ebx, 756E6547h
0x180001dea  or      edx, ebx
0x180001dec  lea     ecx, [rax-1]
0x180001def  cpuid
0x180001df1  mov     edi, ecx
0x180001df3  jnz     short loc_180001E53
0x180001df5  and     eax, 0FFF3FF0h
0x180001dfa  mov     cs:__memset_fast_string_threshold, 8000h
0x180001e05  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001e10  cmp     eax, 106C0h
0x180001e15  jz      short loc_180001E3F
0x180001e17  cmp     eax, 20660h
0x180001e1c  jz      short loc_180001E3F
0x180001e1e  cmp     eax, 20670h
0x180001e23  jz      short loc_180001E3F
0x180001e25  add     eax, 0FFFCF9B0h
0x180001e2a  cmp     eax, 20h ; ' '
0x180001e2d  ja      short loc_180001E53
0x180001e2f  mov     rcx, 100010001h
0x180001e39  bt      rcx, rax
0x180001e3d  jnb     short loc_180001E53
0x180001e3f  mov     r8d, cs:__favor
0x180001e46  or      r8d, 1
0x180001e4a  mov     cs:__favor, r8d
0x180001e51  jmp     short loc_180001E5A
0x180001e53  mov     r8d, cs:__favor
0x180001e5a  xor     r10d, r10d
0x180001e5d  xor     r11d, r11d
0x180001e60  cmp     ebp, 7
0x180001e63  jl      short loc_180001EA7
0x180001e65  xor     ecx, ecx
0x180001e67  lea     eax, [r10+7]
0x180001e6b  cpuid
0x180001e6d  mov     esi, edx
0x180001e6f  mov     r9d, ebx
0x180001e72  bt      ebx, 9
0x180001e76  jnb     short loc_180001E83
0x180001e78  or      r8d, 2
0x180001e7c  mov     cs:__favor, r8d
0x180001e83  cmp     eax, 1
0x180001e86  jl      short loc_180001E95
0x180001e88  mov     eax, 7
0x180001e8d  lea     ecx, [rax-6]
0x180001e90  cpuid
0x180001e92  mov     r10d, edx
0x180001e95  mov     eax, 24h ; '$'
0x180001e9a  cmp     ebp, eax
0x180001e9c  jl      short loc_180001EAC
0x180001e9e  xor     ecx, ecx
0x180001ea0  cpuid
0x180001ea2  mov     r11d, ebx
0x180001ea5  jmp     short loc_180001EAC
0x180001ea7  xor     r9d, r9d
0x180001eaa  xor     esi, esi
0x180001eac  mov     rax, cs:__isa_inverted
0x180001eb3  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001eb7  mov     cs:__isa_available, 1
0x180001ec1  mov     cs:__isa_enabled, 2
0x180001ecb  mov     cs:__isa_inverted, rax
0x180001ed2  bt      edi, 14h
0x180001ed6  jnb     short loc_180001EF7
0x180001ed8  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001edc  mov     cs:__isa_available, 2
0x180001ee6  mov     cs:__isa_inverted, rax
0x180001eed  mov     cs:__isa_enabled, 6
0x180001ef7  bt      edi, 1Bh
0x180001efb  jnb     loc_180002038
0x180001f01  xor     ecx, ecx
0x180001f03  xgetbv
0x180001f06  shl     rdx, 20h
0x180001f0a  or      rdx, rax
0x180001f0d  mov     [rsp+38h+arg_0], rdx
0x180001f12  bt      edi, 1Ch
0x180001f16  jnb     loc_18000201C
0x180001f1c  mov     rax, [rsp+38h+arg_0]
0x180001f21  and     al, 6
0x180001f23  cmp     al, 6
0x180001f25  jnz     loc_18000201C
0x180001f2b  mov     eax, cs:__isa_enabled
0x180001f31  mov     dl, 0E0h
0x180001f33  or      eax, 8
0x180001f36  mov     cs:__isa_available, 3
0x180001f40  mov     cs:__isa_enabled, eax
0x180001f46  test    r9b, 20h
0x180001f4a  jz      short loc_180001FAE
0x180001f4c  or      eax, 20h
0x180001f4f  mov     cs:__isa_available, 5
0x180001f59  mov     cs:__isa_enabled, eax
0x180001f5f  mov     ecx, 0D0030000h
0x180001f64  mov     rax, cs:__isa_inverted
0x180001f6b  and     r9d, ecx
0x180001f6e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001f72  mov     cs:__isa_inverted, rax
0x180001f79  cmp     r9d, ecx
0x180001f7c  jnz     short loc_180001FB5
0x180001f7e  mov     rax, [rsp+38h+arg_0]
0x180001f83  and     al, dl
0x180001f85  cmp     al, dl
0x180001f87  jnz     short loc_180001FAE
0x180001f89  mov     rax, cs:__isa_inverted
0x180001f90  or      cs:__isa_enabled, 40h
0x180001f97  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001f9b  mov     cs:__isa_available, 6
0x180001fa5  mov     cs:__isa_inverted, rax
0x180001fac  jmp     short loc_180001FB5
0x180001fae  mov     rax, cs:__isa_inverted
0x180001fb5  bt      esi, 17h
0x180001fb9  jnb     short loc_180001FC7
0x180001fbb  btr     rax, 18h
0x180001fc0  mov     cs:__isa_inverted, rax
0x180001fc7  bt      r10d, 13h
0x180001fcc  jnb     short loc_18000201C
0x180001fce  mov     rax, [rsp+38h+arg_0]
0x180001fd3  and     al, dl
0x180001fd5  cmp     al, dl
0x180001fd7  jnz     short loc_18000201C
0x180001fd9  mov     rdx, cs:__isa_inverted
0x180001fe0  mov     eax, r11d
0x180001fe3  shr     rax, 10h
0x180001fe7  mov     ecx, r11d
0x180001fea  and     eax, 6
0x180001fed  and     ecx, 400FFh
0x180001ff3  or      rax, 1000029h
0x180001ff9  mov     cs:__avx10_version, ecx
0x180001fff  not     rax
0x180002002  and     rdx, rax
0x180002005  mov     cs:__isa_inverted, rdx
0x18000200c  cmp     cl, 1
0x18000200f  jbe     short loc_18000201C
0x180002011  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180002015  mov     cs:__isa_inverted, rdx
0x18000201c  bt      r10d, 15h
0x180002021  jnb     short loc_180002038
0x180002023  mov     rax, [rsp+38h+arg_0]
0x180002028  bt      rax, 13h
0x18000202d  jnb     short loc_180002038
0x18000202f  btr     cs:__isa_inverted, 7
0x180002038  xor     eax, eax
0x18000203a  add     rsp, 18h
0x18000203e  pop     rdi
0x18000203f  pop     rsi
0x180002040  pop     rbp
0x180002041  pop     rbx
0x180002042  retn
```
