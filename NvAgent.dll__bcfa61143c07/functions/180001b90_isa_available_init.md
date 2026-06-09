# __isa_available_init

- ea: `0x180001b90`
- end: `0x180001e13`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015f4`
- `0x180001730`

## callees

- `0x180001b90`

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
0x180001b90  push    rbx
0x180001b92  push    rbp
0x180001b93  push    rsi
0x180001b94  push    rdi
0x180001b95  sub     rsp, 18h
0x180001b99  xor     eax, eax
0x180001b9b  xor     ecx, ecx
0x180001b9d  cpuid
0x180001b9f  xor     ecx, 6C65746Eh
0x180001ba5  xor     edx, 49656E69h
0x180001bab  or      edx, ecx
0x180001bad  mov     ebp, eax
0x180001baf  mov     eax, 1
0x180001bb4  xor     ebx, 756E6547h
0x180001bba  or      edx, ebx
0x180001bbc  lea     ecx, [rax-1]
0x180001bbf  cpuid
0x180001bc1  mov     edi, ecx
0x180001bc3  jnz     short loc_180001C23
0x180001bc5  and     eax, 0FFF3FF0h
0x180001bca  mov     cs:__memset_fast_string_threshold, 8000h
0x180001bd5  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001be0  cmp     eax, 106C0h
0x180001be5  jz      short loc_180001C0F
0x180001be7  cmp     eax, 20660h
0x180001bec  jz      short loc_180001C0F
0x180001bee  cmp     eax, 20670h
0x180001bf3  jz      short loc_180001C0F
0x180001bf5  add     eax, 0FFFCF9B0h
0x180001bfa  cmp     eax, 20h ; ' '
0x180001bfd  ja      short loc_180001C23
0x180001bff  mov     rcx, 100010001h
0x180001c09  bt      rcx, rax
0x180001c0d  jnb     short loc_180001C23
0x180001c0f  mov     r8d, cs:__favor
0x180001c16  or      r8d, 1
0x180001c1a  mov     cs:__favor, r8d
0x180001c21  jmp     short loc_180001C2A
0x180001c23  mov     r8d, cs:__favor
0x180001c2a  xor     r10d, r10d
0x180001c2d  xor     r11d, r11d
0x180001c30  cmp     ebp, 7
0x180001c33  jl      short loc_180001C77
0x180001c35  xor     ecx, ecx
0x180001c37  lea     eax, [r10+7]
0x180001c3b  cpuid
0x180001c3d  mov     esi, edx
0x180001c3f  mov     r9d, ebx
0x180001c42  bt      ebx, 9
0x180001c46  jnb     short loc_180001C53
0x180001c48  or      r8d, 2
0x180001c4c  mov     cs:__favor, r8d
0x180001c53  cmp     eax, 1
0x180001c56  jl      short loc_180001C65
0x180001c58  mov     eax, 7
0x180001c5d  lea     ecx, [rax-6]
0x180001c60  cpuid
0x180001c62  mov     r10d, edx
0x180001c65  mov     eax, 24h ; '$'
0x180001c6a  cmp     ebp, eax
0x180001c6c  jl      short loc_180001C7C
0x180001c6e  xor     ecx, ecx
0x180001c70  cpuid
0x180001c72  mov     r11d, ebx
0x180001c75  jmp     short loc_180001C7C
0x180001c77  xor     r9d, r9d
0x180001c7a  xor     esi, esi
0x180001c7c  mov     rax, cs:__isa_inverted
0x180001c83  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001c87  mov     cs:__isa_available, 1
0x180001c91  mov     cs:__isa_enabled, 2
0x180001c9b  mov     cs:__isa_inverted, rax
0x180001ca2  bt      edi, 14h
0x180001ca6  jnb     short loc_180001CC7
0x180001ca8  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001cac  mov     cs:__isa_available, 2
0x180001cb6  mov     cs:__isa_inverted, rax
0x180001cbd  mov     cs:__isa_enabled, 6
0x180001cc7  bt      edi, 1Bh
0x180001ccb  jnb     loc_180001E08
0x180001cd1  xor     ecx, ecx
0x180001cd3  xgetbv
0x180001cd6  shl     rdx, 20h
0x180001cda  or      rdx, rax
0x180001cdd  mov     [rsp+38h+arg_0], rdx
0x180001ce2  bt      edi, 1Ch
0x180001ce6  jnb     loc_180001DEC
0x180001cec  mov     rax, [rsp+38h+arg_0]
0x180001cf1  and     al, 6
0x180001cf3  cmp     al, 6
0x180001cf5  jnz     loc_180001DEC
0x180001cfb  mov     eax, cs:__isa_enabled
0x180001d01  mov     dl, 0E0h
0x180001d03  or      eax, 8
0x180001d06  mov     cs:__isa_available, 3
0x180001d10  mov     cs:__isa_enabled, eax
0x180001d16  test    r9b, 20h
0x180001d1a  jz      short loc_180001D7E
0x180001d1c  or      eax, 20h
0x180001d1f  mov     cs:__isa_available, 5
0x180001d29  mov     cs:__isa_enabled, eax
0x180001d2f  mov     ecx, 0D0030000h
0x180001d34  mov     rax, cs:__isa_inverted
0x180001d3b  and     r9d, ecx
0x180001d3e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001d42  mov     cs:__isa_inverted, rax
0x180001d49  cmp     r9d, ecx
0x180001d4c  jnz     short loc_180001D85
0x180001d4e  mov     rax, [rsp+38h+arg_0]
0x180001d53  and     al, dl
0x180001d55  cmp     al, dl
0x180001d57  jnz     short loc_180001D7E
0x180001d59  mov     rax, cs:__isa_inverted
0x180001d60  or      cs:__isa_enabled, 40h
0x180001d67  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001d6b  mov     cs:__isa_available, 6
0x180001d75  mov     cs:__isa_inverted, rax
0x180001d7c  jmp     short loc_180001D85
0x180001d7e  mov     rax, cs:__isa_inverted
0x180001d85  bt      esi, 17h
0x180001d89  jnb     short loc_180001D97
0x180001d8b  btr     rax, 18h
0x180001d90  mov     cs:__isa_inverted, rax
0x180001d97  bt      r10d, 13h
0x180001d9c  jnb     short loc_180001DEC
0x180001d9e  mov     rax, [rsp+38h+arg_0]
0x180001da3  and     al, dl
0x180001da5  cmp     al, dl
0x180001da7  jnz     short loc_180001DEC
0x180001da9  mov     rdx, cs:__isa_inverted
0x180001db0  mov     eax, r11d
0x180001db3  shr     rax, 10h
0x180001db7  mov     ecx, r11d
0x180001dba  and     eax, 6
0x180001dbd  and     ecx, 400FFh
0x180001dc3  or      rax, 1000029h
0x180001dc9  mov     cs:__avx10_version, ecx
0x180001dcf  not     rax
0x180001dd2  and     rdx, rax
0x180001dd5  mov     cs:__isa_inverted, rdx
0x180001ddc  cmp     cl, 1
0x180001ddf  jbe     short loc_180001DEC
0x180001de1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001de5  mov     cs:__isa_inverted, rdx
0x180001dec  bt      r10d, 15h
0x180001df1  jnb     short loc_180001E08
0x180001df3  mov     rax, [rsp+38h+arg_0]
0x180001df8  bt      rax, 13h
0x180001dfd  jnb     short loc_180001E08
0x180001dff  btr     cs:__isa_inverted, 7
0x180001e08  xor     eax, eax
0x180001e0a  add     rsp, 18h
0x180001e0e  pop     rdi
0x180001e0f  pop     rsi
0x180001e10  pop     rbp
0x180001e11  pop     rbx
0x180001e12  retn
```
