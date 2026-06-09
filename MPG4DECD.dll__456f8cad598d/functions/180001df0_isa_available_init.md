# __isa_available_init

- ea: `0x180001df0`
- end: `0x180002073`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a1c`
- `0x180001b58`

## callees

- `0x180001df0`

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
0x180001df0  push    rbx
0x180001df2  push    rbp
0x180001df3  push    rsi
0x180001df4  push    rdi
0x180001df5  sub     rsp, 18h
0x180001df9  xor     eax, eax
0x180001dfb  xor     ecx, ecx
0x180001dfd  cpuid
0x180001dff  xor     ecx, 6C65746Eh
0x180001e05  xor     edx, 49656E69h
0x180001e0b  or      edx, ecx
0x180001e0d  mov     ebp, eax
0x180001e0f  mov     eax, 1
0x180001e14  xor     ebx, 756E6547h
0x180001e1a  or      edx, ebx
0x180001e1c  lea     ecx, [rax-1]
0x180001e1f  cpuid
0x180001e21  mov     edi, ecx
0x180001e23  jnz     short loc_180001E83
0x180001e25  and     eax, 0FFF3FF0h
0x180001e2a  mov     cs:__memset_fast_string_threshold, 8000h
0x180001e35  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001e40  cmp     eax, 106C0h
0x180001e45  jz      short loc_180001E6F
0x180001e47  cmp     eax, 20660h
0x180001e4c  jz      short loc_180001E6F
0x180001e4e  cmp     eax, 20670h
0x180001e53  jz      short loc_180001E6F
0x180001e55  add     eax, 0FFFCF9B0h
0x180001e5a  cmp     eax, 20h ; ' '
0x180001e5d  ja      short loc_180001E83
0x180001e5f  mov     rcx, 100010001h
0x180001e69  bt      rcx, rax
0x180001e6d  jnb     short loc_180001E83
0x180001e6f  mov     r8d, cs:__favor
0x180001e76  or      r8d, 1
0x180001e7a  mov     cs:__favor, r8d
0x180001e81  jmp     short loc_180001E8A
0x180001e83  mov     r8d, cs:__favor
0x180001e8a  xor     r10d, r10d
0x180001e8d  xor     r11d, r11d
0x180001e90  cmp     ebp, 7
0x180001e93  jl      short loc_180001ED7
0x180001e95  xor     ecx, ecx
0x180001e97  lea     eax, [r10+7]
0x180001e9b  cpuid
0x180001e9d  mov     esi, edx
0x180001e9f  mov     r9d, ebx
0x180001ea2  bt      ebx, 9
0x180001ea6  jnb     short loc_180001EB3
0x180001ea8  or      r8d, 2
0x180001eac  mov     cs:__favor, r8d
0x180001eb3  cmp     eax, 1
0x180001eb6  jl      short loc_180001EC5
0x180001eb8  mov     eax, 7
0x180001ebd  lea     ecx, [rax-6]
0x180001ec0  cpuid
0x180001ec2  mov     r10d, edx
0x180001ec5  mov     eax, 24h ; '$'
0x180001eca  cmp     ebp, eax
0x180001ecc  jl      short loc_180001EDC
0x180001ece  xor     ecx, ecx
0x180001ed0  cpuid
0x180001ed2  mov     r11d, ebx
0x180001ed5  jmp     short loc_180001EDC
0x180001ed7  xor     r9d, r9d
0x180001eda  xor     esi, esi
0x180001edc  mov     rax, cs:__isa_inverted
0x180001ee3  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001ee7  mov     cs:__isa_available, 1
0x180001ef1  mov     cs:__isa_enabled, 2
0x180001efb  mov     cs:__isa_inverted, rax
0x180001f02  bt      edi, 14h
0x180001f06  jnb     short loc_180001F27
0x180001f08  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001f0c  mov     cs:__isa_available, 2
0x180001f16  mov     cs:__isa_inverted, rax
0x180001f1d  mov     cs:__isa_enabled, 6
0x180001f27  bt      edi, 1Bh
0x180001f2b  jnb     loc_180002068
0x180001f31  xor     ecx, ecx
0x180001f33  xgetbv
0x180001f36  shl     rdx, 20h
0x180001f3a  or      rdx, rax
0x180001f3d  mov     [rsp+38h+arg_0], rdx
0x180001f42  bt      edi, 1Ch
0x180001f46  jnb     loc_18000204C
0x180001f4c  mov     rax, [rsp+38h+arg_0]
0x180001f51  and     al, 6
0x180001f53  cmp     al, 6
0x180001f55  jnz     loc_18000204C
0x180001f5b  mov     eax, cs:__isa_enabled
0x180001f61  mov     dl, 0E0h
0x180001f63  or      eax, 8
0x180001f66  mov     cs:__isa_available, 3
0x180001f70  mov     cs:__isa_enabled, eax
0x180001f76  test    r9b, 20h
0x180001f7a  jz      short loc_180001FDE
0x180001f7c  or      eax, 20h
0x180001f7f  mov     cs:__isa_available, 5
0x180001f89  mov     cs:__isa_enabled, eax
0x180001f8f  mov     ecx, 0D0030000h
0x180001f94  mov     rax, cs:__isa_inverted
0x180001f9b  and     r9d, ecx
0x180001f9e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001fa2  mov     cs:__isa_inverted, rax
0x180001fa9  cmp     r9d, ecx
0x180001fac  jnz     short loc_180001FE5
0x180001fae  mov     rax, [rsp+38h+arg_0]
0x180001fb3  and     al, dl
0x180001fb5  cmp     al, dl
0x180001fb7  jnz     short loc_180001FDE
0x180001fb9  mov     rax, cs:__isa_inverted
0x180001fc0  or      cs:__isa_enabled, 40h
0x180001fc7  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001fcb  mov     cs:__isa_available, 6
0x180001fd5  mov     cs:__isa_inverted, rax
0x180001fdc  jmp     short loc_180001FE5
0x180001fde  mov     rax, cs:__isa_inverted
0x180001fe5  bt      esi, 17h
0x180001fe9  jnb     short loc_180001FF7
0x180001feb  btr     rax, 18h
0x180001ff0  mov     cs:__isa_inverted, rax
0x180001ff7  bt      r10d, 13h
0x180001ffc  jnb     short loc_18000204C
0x180001ffe  mov     rax, [rsp+38h+arg_0]
0x180002003  and     al, dl
0x180002005  cmp     al, dl
0x180002007  jnz     short loc_18000204C
0x180002009  mov     rdx, cs:__isa_inverted
0x180002010  mov     eax, r11d
0x180002013  shr     rax, 10h
0x180002017  mov     ecx, r11d
0x18000201a  and     eax, 6
0x18000201d  and     ecx, 400FFh
0x180002023  or      rax, 1000029h
0x180002029  mov     cs:__avx10_version, ecx
0x18000202f  not     rax
0x180002032  and     rdx, rax
0x180002035  mov     cs:__isa_inverted, rdx
0x18000203c  cmp     cl, 1
0x18000203f  jbe     short loc_18000204C
0x180002041  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180002045  mov     cs:__isa_inverted, rdx
0x18000204c  bt      r10d, 15h
0x180002051  jnb     short loc_180002068
0x180002053  mov     rax, [rsp+38h+arg_0]
0x180002058  bt      rax, 13h
0x18000205d  jnb     short loc_180002068
0x18000205f  btr     cs:__isa_inverted, 7
0x180002068  xor     eax, eax
0x18000206a  add     rsp, 18h
0x18000206e  pop     rdi
0x18000206f  pop     rsi
0x180002070  pop     rbp
0x180002071  pop     rbx
0x180002072  retn
```
