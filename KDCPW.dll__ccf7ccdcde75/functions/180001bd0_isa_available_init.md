# __isa_available_init

- ea: `0x180001bd0`
- end: `0x180001e53`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001694`
- `0x1800017d0`

## callees

- `0x180001bd0`

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
0x180001bd0  push    rbx
0x180001bd2  push    rbp
0x180001bd3  push    rsi
0x180001bd4  push    rdi
0x180001bd5  sub     rsp, 18h
0x180001bd9  xor     eax, eax
0x180001bdb  xor     ecx, ecx
0x180001bdd  cpuid
0x180001bdf  xor     ecx, 6C65746Eh
0x180001be5  xor     edx, 49656E69h
0x180001beb  or      edx, ecx
0x180001bed  mov     ebp, eax
0x180001bef  mov     eax, 1
0x180001bf4  xor     ebx, 756E6547h
0x180001bfa  or      edx, ebx
0x180001bfc  lea     ecx, [rax-1]
0x180001bff  cpuid
0x180001c01  mov     edi, ecx
0x180001c03  jnz     short loc_180001C63
0x180001c05  and     eax, 0FFF3FF0h
0x180001c0a  mov     cs:__memset_fast_string_threshold, 8000h
0x180001c15  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001c20  cmp     eax, 106C0h
0x180001c25  jz      short loc_180001C4F
0x180001c27  cmp     eax, 20660h
0x180001c2c  jz      short loc_180001C4F
0x180001c2e  cmp     eax, 20670h
0x180001c33  jz      short loc_180001C4F
0x180001c35  add     eax, 0FFFCF9B0h
0x180001c3a  cmp     eax, 20h ; ' '
0x180001c3d  ja      short loc_180001C63
0x180001c3f  mov     rcx, 100010001h
0x180001c49  bt      rcx, rax
0x180001c4d  jnb     short loc_180001C63
0x180001c4f  mov     r8d, cs:__favor
0x180001c56  or      r8d, 1
0x180001c5a  mov     cs:__favor, r8d
0x180001c61  jmp     short loc_180001C6A
0x180001c63  mov     r8d, cs:__favor
0x180001c6a  xor     r10d, r10d
0x180001c6d  xor     r11d, r11d
0x180001c70  cmp     ebp, 7
0x180001c73  jl      short loc_180001CB7
0x180001c75  xor     ecx, ecx
0x180001c77  lea     eax, [r10+7]
0x180001c7b  cpuid
0x180001c7d  mov     esi, edx
0x180001c7f  mov     r9d, ebx
0x180001c82  bt      ebx, 9
0x180001c86  jnb     short loc_180001C93
0x180001c88  or      r8d, 2
0x180001c8c  mov     cs:__favor, r8d
0x180001c93  cmp     eax, 1
0x180001c96  jl      short loc_180001CA5
0x180001c98  mov     eax, 7
0x180001c9d  lea     ecx, [rax-6]
0x180001ca0  cpuid
0x180001ca2  mov     r10d, edx
0x180001ca5  mov     eax, 24h ; '$'
0x180001caa  cmp     ebp, eax
0x180001cac  jl      short loc_180001CBC
0x180001cae  xor     ecx, ecx
0x180001cb0  cpuid
0x180001cb2  mov     r11d, ebx
0x180001cb5  jmp     short loc_180001CBC
0x180001cb7  xor     r9d, r9d
0x180001cba  xor     esi, esi
0x180001cbc  mov     rax, cs:__isa_inverted
0x180001cc3  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001cc7  mov     cs:__isa_available, 1
0x180001cd1  mov     cs:__isa_enabled, 2
0x180001cdb  mov     cs:__isa_inverted, rax
0x180001ce2  bt      edi, 14h
0x180001ce6  jnb     short loc_180001D07
0x180001ce8  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001cec  mov     cs:__isa_available, 2
0x180001cf6  mov     cs:__isa_inverted, rax
0x180001cfd  mov     cs:__isa_enabled, 6
0x180001d07  bt      edi, 1Bh
0x180001d0b  jnb     loc_180001E48
0x180001d11  xor     ecx, ecx
0x180001d13  xgetbv
0x180001d16  shl     rdx, 20h
0x180001d1a  or      rdx, rax
0x180001d1d  mov     [rsp+38h+arg_0], rdx
0x180001d22  bt      edi, 1Ch
0x180001d26  jnb     loc_180001E2C
0x180001d2c  mov     rax, [rsp+38h+arg_0]
0x180001d31  and     al, 6
0x180001d33  cmp     al, 6
0x180001d35  jnz     loc_180001E2C
0x180001d3b  mov     eax, cs:__isa_enabled
0x180001d41  mov     dl, 0E0h
0x180001d43  or      eax, 8
0x180001d46  mov     cs:__isa_available, 3
0x180001d50  mov     cs:__isa_enabled, eax
0x180001d56  test    r9b, 20h
0x180001d5a  jz      short loc_180001DBE
0x180001d5c  or      eax, 20h
0x180001d5f  mov     cs:__isa_available, 5
0x180001d69  mov     cs:__isa_enabled, eax
0x180001d6f  mov     ecx, 0D0030000h
0x180001d74  mov     rax, cs:__isa_inverted
0x180001d7b  and     r9d, ecx
0x180001d7e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001d82  mov     cs:__isa_inverted, rax
0x180001d89  cmp     r9d, ecx
0x180001d8c  jnz     short loc_180001DC5
0x180001d8e  mov     rax, [rsp+38h+arg_0]
0x180001d93  and     al, dl
0x180001d95  cmp     al, dl
0x180001d97  jnz     short loc_180001DBE
0x180001d99  mov     rax, cs:__isa_inverted
0x180001da0  or      cs:__isa_enabled, 40h
0x180001da7  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001dab  mov     cs:__isa_available, 6
0x180001db5  mov     cs:__isa_inverted, rax
0x180001dbc  jmp     short loc_180001DC5
0x180001dbe  mov     rax, cs:__isa_inverted
0x180001dc5  bt      esi, 17h
0x180001dc9  jnb     short loc_180001DD7
0x180001dcb  btr     rax, 18h
0x180001dd0  mov     cs:__isa_inverted, rax
0x180001dd7  bt      r10d, 13h
0x180001ddc  jnb     short loc_180001E2C
0x180001dde  mov     rax, [rsp+38h+arg_0]
0x180001de3  and     al, dl
0x180001de5  cmp     al, dl
0x180001de7  jnz     short loc_180001E2C
0x180001de9  mov     rdx, cs:__isa_inverted
0x180001df0  mov     eax, r11d
0x180001df3  shr     rax, 10h
0x180001df7  mov     ecx, r11d
0x180001dfa  and     eax, 6
0x180001dfd  and     ecx, 400FFh
0x180001e03  or      rax, 1000029h
0x180001e09  mov     cs:__avx10_version, ecx
0x180001e0f  not     rax
0x180001e12  and     rdx, rax
0x180001e15  mov     cs:__isa_inverted, rdx
0x180001e1c  cmp     cl, 1
0x180001e1f  jbe     short loc_180001E2C
0x180001e21  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001e25  mov     cs:__isa_inverted, rdx
0x180001e2c  bt      r10d, 15h
0x180001e31  jnb     short loc_180001E48
0x180001e33  mov     rax, [rsp+38h+arg_0]
0x180001e38  bt      rax, 13h
0x180001e3d  jnb     short loc_180001E48
0x180001e3f  btr     cs:__isa_inverted, 7
0x180001e48  xor     eax, eax
0x180001e4a  add     rsp, 18h
0x180001e4e  pop     rdi
0x180001e4f  pop     rsi
0x180001e50  pop     rbp
0x180001e51  pop     rbx
0x180001e52  retn
```
