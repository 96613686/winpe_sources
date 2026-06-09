# __isa_available_init

- ea: `0x180001b88`
- end: `0x180001e0b`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015bc`
- `0x1800016f8`

## callees

- `0x180001b88`

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
0x180001b88  push    rbx
0x180001b8a  push    rbp
0x180001b8b  push    rsi
0x180001b8c  push    rdi
0x180001b8d  sub     rsp, 18h
0x180001b91  xor     eax, eax
0x180001b93  xor     ecx, ecx
0x180001b95  cpuid
0x180001b97  xor     ecx, 6C65746Eh
0x180001b9d  xor     edx, 49656E69h
0x180001ba3  or      edx, ecx
0x180001ba5  mov     ebp, eax
0x180001ba7  mov     eax, 1
0x180001bac  xor     ebx, 756E6547h
0x180001bb2  or      edx, ebx
0x180001bb4  lea     ecx, [rax-1]
0x180001bb7  cpuid
0x180001bb9  mov     edi, ecx
0x180001bbb  jnz     short loc_180001C1B
0x180001bbd  and     eax, 0FFF3FF0h
0x180001bc2  mov     cs:__memset_fast_string_threshold, 8000h
0x180001bcd  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001bd8  cmp     eax, 106C0h
0x180001bdd  jz      short loc_180001C07
0x180001bdf  cmp     eax, 20660h
0x180001be4  jz      short loc_180001C07
0x180001be6  cmp     eax, 20670h
0x180001beb  jz      short loc_180001C07
0x180001bed  add     eax, 0FFFCF9B0h
0x180001bf2  cmp     eax, 20h ; ' '
0x180001bf5  ja      short loc_180001C1B
0x180001bf7  mov     rcx, 100010001h
0x180001c01  bt      rcx, rax
0x180001c05  jnb     short loc_180001C1B
0x180001c07  mov     r8d, cs:__favor
0x180001c0e  or      r8d, 1
0x180001c12  mov     cs:__favor, r8d
0x180001c19  jmp     short loc_180001C22
0x180001c1b  mov     r8d, cs:__favor
0x180001c22  xor     r10d, r10d
0x180001c25  xor     r11d, r11d
0x180001c28  cmp     ebp, 7
0x180001c2b  jl      short loc_180001C6F
0x180001c2d  xor     ecx, ecx
0x180001c2f  lea     eax, [r10+7]
0x180001c33  cpuid
0x180001c35  mov     esi, edx
0x180001c37  mov     r9d, ebx
0x180001c3a  bt      ebx, 9
0x180001c3e  jnb     short loc_180001C4B
0x180001c40  or      r8d, 2
0x180001c44  mov     cs:__favor, r8d
0x180001c4b  cmp     eax, 1
0x180001c4e  jl      short loc_180001C5D
0x180001c50  mov     eax, 7
0x180001c55  lea     ecx, [rax-6]
0x180001c58  cpuid
0x180001c5a  mov     r10d, edx
0x180001c5d  mov     eax, 24h ; '$'
0x180001c62  cmp     ebp, eax
0x180001c64  jl      short loc_180001C74
0x180001c66  xor     ecx, ecx
0x180001c68  cpuid
0x180001c6a  mov     r11d, ebx
0x180001c6d  jmp     short loc_180001C74
0x180001c6f  xor     r9d, r9d
0x180001c72  xor     esi, esi
0x180001c74  mov     rax, cs:__isa_inverted
0x180001c7b  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001c7f  mov     cs:__isa_available, 1
0x180001c89  mov     cs:__isa_enabled, 2
0x180001c93  mov     cs:__isa_inverted, rax
0x180001c9a  bt      edi, 14h
0x180001c9e  jnb     short loc_180001CBF
0x180001ca0  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001ca4  mov     cs:__isa_available, 2
0x180001cae  mov     cs:__isa_inverted, rax
0x180001cb5  mov     cs:__isa_enabled, 6
0x180001cbf  bt      edi, 1Bh
0x180001cc3  jnb     loc_180001E00
0x180001cc9  xor     ecx, ecx
0x180001ccb  xgetbv
0x180001cce  shl     rdx, 20h
0x180001cd2  or      rdx, rax
0x180001cd5  mov     [rsp+38h+arg_0], rdx
0x180001cda  bt      edi, 1Ch
0x180001cde  jnb     loc_180001DE4
0x180001ce4  mov     rax, [rsp+38h+arg_0]
0x180001ce9  and     al, 6
0x180001ceb  cmp     al, 6
0x180001ced  jnz     loc_180001DE4
0x180001cf3  mov     eax, cs:__isa_enabled
0x180001cf9  mov     dl, 0E0h
0x180001cfb  or      eax, 8
0x180001cfe  mov     cs:__isa_available, 3
0x180001d08  mov     cs:__isa_enabled, eax
0x180001d0e  test    r9b, 20h
0x180001d12  jz      short loc_180001D76
0x180001d14  or      eax, 20h
0x180001d17  mov     cs:__isa_available, 5
0x180001d21  mov     cs:__isa_enabled, eax
0x180001d27  mov     ecx, 0D0030000h
0x180001d2c  mov     rax, cs:__isa_inverted
0x180001d33  and     r9d, ecx
0x180001d36  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001d3a  mov     cs:__isa_inverted, rax
0x180001d41  cmp     r9d, ecx
0x180001d44  jnz     short loc_180001D7D
0x180001d46  mov     rax, [rsp+38h+arg_0]
0x180001d4b  and     al, dl
0x180001d4d  cmp     al, dl
0x180001d4f  jnz     short loc_180001D76
0x180001d51  mov     rax, cs:__isa_inverted
0x180001d58  or      cs:__isa_enabled, 40h
0x180001d5f  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001d63  mov     cs:__isa_available, 6
0x180001d6d  mov     cs:__isa_inverted, rax
0x180001d74  jmp     short loc_180001D7D
0x180001d76  mov     rax, cs:__isa_inverted
0x180001d7d  bt      esi, 17h
0x180001d81  jnb     short loc_180001D8F
0x180001d83  btr     rax, 18h
0x180001d88  mov     cs:__isa_inverted, rax
0x180001d8f  bt      r10d, 13h
0x180001d94  jnb     short loc_180001DE4
0x180001d96  mov     rax, [rsp+38h+arg_0]
0x180001d9b  and     al, dl
0x180001d9d  cmp     al, dl
0x180001d9f  jnz     short loc_180001DE4
0x180001da1  mov     rdx, cs:__isa_inverted
0x180001da8  mov     eax, r11d
0x180001dab  shr     rax, 10h
0x180001daf  mov     ecx, r11d
0x180001db2  and     eax, 6
0x180001db5  and     ecx, 400FFh
0x180001dbb  or      rax, 1000029h
0x180001dc1  mov     cs:__avx10_version, ecx
0x180001dc7  not     rax
0x180001dca  and     rdx, rax
0x180001dcd  mov     cs:__isa_inverted, rdx
0x180001dd4  cmp     cl, 1
0x180001dd7  jbe     short loc_180001DE4
0x180001dd9  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001ddd  mov     cs:__isa_inverted, rdx
0x180001de4  bt      r10d, 15h
0x180001de9  jnb     short loc_180001E00
0x180001deb  mov     rax, [rsp+38h+arg_0]
0x180001df0  bt      rax, 13h
0x180001df5  jnb     short loc_180001E00
0x180001df7  btr     cs:__isa_inverted, 7
0x180001e00  xor     eax, eax
0x180001e02  add     rsp, 18h
0x180001e06  pop     rdi
0x180001e07  pop     rsi
0x180001e08  pop     rbp
0x180001e09  pop     rbx
0x180001e0a  retn
```
