# __isa_available_init

- ea: `0x180001c70`
- end: `0x180001ef3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001704`
- `0x180001840`

## callees

- `0x180001c70`

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
0x180001c70  push    rbx
0x180001c72  push    rbp
0x180001c73  push    rsi
0x180001c74  push    rdi
0x180001c75  sub     rsp, 18h
0x180001c79  xor     eax, eax
0x180001c7b  xor     ecx, ecx
0x180001c7d  cpuid
0x180001c7f  xor     ecx, 6C65746Eh
0x180001c85  xor     edx, 49656E69h
0x180001c8b  or      edx, ecx
0x180001c8d  mov     ebp, eax
0x180001c8f  mov     eax, 1
0x180001c94  xor     ebx, 756E6547h
0x180001c9a  or      edx, ebx
0x180001c9c  lea     ecx, [rax-1]
0x180001c9f  cpuid
0x180001ca1  mov     edi, ecx
0x180001ca3  jnz     short loc_180001D03
0x180001ca5  and     eax, 0FFF3FF0h
0x180001caa  mov     cs:__memset_fast_string_threshold, 8000h
0x180001cb5  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001cc0  cmp     eax, 106C0h
0x180001cc5  jz      short loc_180001CEF
0x180001cc7  cmp     eax, 20660h
0x180001ccc  jz      short loc_180001CEF
0x180001cce  cmp     eax, 20670h
0x180001cd3  jz      short loc_180001CEF
0x180001cd5  add     eax, 0FFFCF9B0h
0x180001cda  cmp     eax, 20h ; ' '
0x180001cdd  ja      short loc_180001D03
0x180001cdf  mov     rcx, 100010001h
0x180001ce9  bt      rcx, rax
0x180001ced  jnb     short loc_180001D03
0x180001cef  mov     r8d, cs:__favor
0x180001cf6  or      r8d, 1
0x180001cfa  mov     cs:__favor, r8d
0x180001d01  jmp     short loc_180001D0A
0x180001d03  mov     r8d, cs:__favor
0x180001d0a  xor     r10d, r10d
0x180001d0d  xor     r11d, r11d
0x180001d10  cmp     ebp, 7
0x180001d13  jl      short loc_180001D57
0x180001d15  xor     ecx, ecx
0x180001d17  lea     eax, [r10+7]
0x180001d1b  cpuid
0x180001d1d  mov     esi, edx
0x180001d1f  mov     r9d, ebx
0x180001d22  bt      ebx, 9
0x180001d26  jnb     short loc_180001D33
0x180001d28  or      r8d, 2
0x180001d2c  mov     cs:__favor, r8d
0x180001d33  cmp     eax, 1
0x180001d36  jl      short loc_180001D45
0x180001d38  mov     eax, 7
0x180001d3d  lea     ecx, [rax-6]
0x180001d40  cpuid
0x180001d42  mov     r10d, edx
0x180001d45  mov     eax, 24h ; '$'
0x180001d4a  cmp     ebp, eax
0x180001d4c  jl      short loc_180001D5C
0x180001d4e  xor     ecx, ecx
0x180001d50  cpuid
0x180001d52  mov     r11d, ebx
0x180001d55  jmp     short loc_180001D5C
0x180001d57  xor     r9d, r9d
0x180001d5a  xor     esi, esi
0x180001d5c  mov     rax, cs:__isa_inverted
0x180001d63  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001d67  mov     cs:__isa_available, 1
0x180001d71  mov     cs:__isa_enabled, 2
0x180001d7b  mov     cs:__isa_inverted, rax
0x180001d82  bt      edi, 14h
0x180001d86  jnb     short loc_180001DA7
0x180001d88  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001d8c  mov     cs:__isa_available, 2
0x180001d96  mov     cs:__isa_inverted, rax
0x180001d9d  mov     cs:__isa_enabled, 6
0x180001da7  bt      edi, 1Bh
0x180001dab  jnb     loc_180001EE8
0x180001db1  xor     ecx, ecx
0x180001db3  xgetbv
0x180001db6  shl     rdx, 20h
0x180001dba  or      rdx, rax
0x180001dbd  mov     [rsp+38h+arg_0], rdx
0x180001dc2  bt      edi, 1Ch
0x180001dc6  jnb     loc_180001ECC
0x180001dcc  mov     rax, [rsp+38h+arg_0]
0x180001dd1  and     al, 6
0x180001dd3  cmp     al, 6
0x180001dd5  jnz     loc_180001ECC
0x180001ddb  mov     eax, cs:__isa_enabled
0x180001de1  mov     dl, 0E0h
0x180001de3  or      eax, 8
0x180001de6  mov     cs:__isa_available, 3
0x180001df0  mov     cs:__isa_enabled, eax
0x180001df6  test    r9b, 20h
0x180001dfa  jz      short loc_180001E5E
0x180001dfc  or      eax, 20h
0x180001dff  mov     cs:__isa_available, 5
0x180001e09  mov     cs:__isa_enabled, eax
0x180001e0f  mov     ecx, 0D0030000h
0x180001e14  mov     rax, cs:__isa_inverted
0x180001e1b  and     r9d, ecx
0x180001e1e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001e22  mov     cs:__isa_inverted, rax
0x180001e29  cmp     r9d, ecx
0x180001e2c  jnz     short loc_180001E65
0x180001e2e  mov     rax, [rsp+38h+arg_0]
0x180001e33  and     al, dl
0x180001e35  cmp     al, dl
0x180001e37  jnz     short loc_180001E5E
0x180001e39  mov     rax, cs:__isa_inverted
0x180001e40  or      cs:__isa_enabled, 40h
0x180001e47  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001e4b  mov     cs:__isa_available, 6
0x180001e55  mov     cs:__isa_inverted, rax
0x180001e5c  jmp     short loc_180001E65
0x180001e5e  mov     rax, cs:__isa_inverted
0x180001e65  bt      esi, 17h
0x180001e69  jnb     short loc_180001E77
0x180001e6b  btr     rax, 18h
0x180001e70  mov     cs:__isa_inverted, rax
0x180001e77  bt      r10d, 13h
0x180001e7c  jnb     short loc_180001ECC
0x180001e7e  mov     rax, [rsp+38h+arg_0]
0x180001e83  and     al, dl
0x180001e85  cmp     al, dl
0x180001e87  jnz     short loc_180001ECC
0x180001e89  mov     rdx, cs:__isa_inverted
0x180001e90  mov     eax, r11d
0x180001e93  shr     rax, 10h
0x180001e97  mov     ecx, r11d
0x180001e9a  and     eax, 6
0x180001e9d  and     ecx, 400FFh
0x180001ea3  or      rax, 1000029h
0x180001ea9  mov     cs:__avx10_version, ecx
0x180001eaf  not     rax
0x180001eb2  and     rdx, rax
0x180001eb5  mov     cs:__isa_inverted, rdx
0x180001ebc  cmp     cl, 1
0x180001ebf  jbe     short loc_180001ECC
0x180001ec1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001ec5  mov     cs:__isa_inverted, rdx
0x180001ecc  bt      r10d, 15h
0x180001ed1  jnb     short loc_180001EE8
0x180001ed3  mov     rax, [rsp+38h+arg_0]
0x180001ed8  bt      rax, 13h
0x180001edd  jnb     short loc_180001EE8
0x180001edf  btr     cs:__isa_inverted, 7
0x180001ee8  xor     eax, eax
0x180001eea  add     rsp, 18h
0x180001eee  pop     rdi
0x180001eef  pop     rsi
0x180001ef0  pop     rbp
0x180001ef1  pop     rbx
0x180001ef2  retn
```
