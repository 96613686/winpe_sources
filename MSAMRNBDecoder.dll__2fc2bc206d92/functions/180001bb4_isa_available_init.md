# __isa_available_init

- ea: `0x180001bb4`
- end: `0x180001e37`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015e0`
- `0x18000171c`

## callees

- `0x180001bb4`

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
0x180001bb4  push    rbx
0x180001bb6  push    rbp
0x180001bb7  push    rsi
0x180001bb8  push    rdi
0x180001bb9  sub     rsp, 18h
0x180001bbd  xor     eax, eax
0x180001bbf  xor     ecx, ecx
0x180001bc1  cpuid
0x180001bc3  xor     ecx, 6C65746Eh
0x180001bc9  xor     edx, 49656E69h
0x180001bcf  or      edx, ecx
0x180001bd1  mov     ebp, eax
0x180001bd3  mov     eax, 1
0x180001bd8  xor     ebx, 756E6547h
0x180001bde  or      edx, ebx
0x180001be0  lea     ecx, [rax-1]
0x180001be3  cpuid
0x180001be5  mov     edi, ecx
0x180001be7  jnz     short loc_180001C47
0x180001be9  and     eax, 0FFF3FF0h
0x180001bee  mov     cs:__memset_fast_string_threshold, 8000h
0x180001bf9  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001c04  cmp     eax, 106C0h
0x180001c09  jz      short loc_180001C33
0x180001c0b  cmp     eax, 20660h
0x180001c10  jz      short loc_180001C33
0x180001c12  cmp     eax, 20670h
0x180001c17  jz      short loc_180001C33
0x180001c19  add     eax, 0FFFCF9B0h
0x180001c1e  cmp     eax, 20h ; ' '
0x180001c21  ja      short loc_180001C47
0x180001c23  mov     rcx, 100010001h
0x180001c2d  bt      rcx, rax
0x180001c31  jnb     short loc_180001C47
0x180001c33  mov     r8d, cs:__favor
0x180001c3a  or      r8d, 1
0x180001c3e  mov     cs:__favor, r8d
0x180001c45  jmp     short loc_180001C4E
0x180001c47  mov     r8d, cs:__favor
0x180001c4e  xor     r10d, r10d
0x180001c51  xor     r11d, r11d
0x180001c54  cmp     ebp, 7
0x180001c57  jl      short loc_180001C9B
0x180001c59  xor     ecx, ecx
0x180001c5b  lea     eax, [r10+7]
0x180001c5f  cpuid
0x180001c61  mov     esi, edx
0x180001c63  mov     r9d, ebx
0x180001c66  bt      ebx, 9
0x180001c6a  jnb     short loc_180001C77
0x180001c6c  or      r8d, 2
0x180001c70  mov     cs:__favor, r8d
0x180001c77  cmp     eax, 1
0x180001c7a  jl      short loc_180001C89
0x180001c7c  mov     eax, 7
0x180001c81  lea     ecx, [rax-6]
0x180001c84  cpuid
0x180001c86  mov     r10d, edx
0x180001c89  mov     eax, 24h ; '$'
0x180001c8e  cmp     ebp, eax
0x180001c90  jl      short loc_180001CA0
0x180001c92  xor     ecx, ecx
0x180001c94  cpuid
0x180001c96  mov     r11d, ebx
0x180001c99  jmp     short loc_180001CA0
0x180001c9b  xor     r9d, r9d
0x180001c9e  xor     esi, esi
0x180001ca0  mov     rax, cs:__isa_inverted
0x180001ca7  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001cab  mov     cs:__isa_available, 1
0x180001cb5  mov     cs:__isa_enabled, 2
0x180001cbf  mov     cs:__isa_inverted, rax
0x180001cc6  bt      edi, 14h
0x180001cca  jnb     short loc_180001CEB
0x180001ccc  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001cd0  mov     cs:__isa_available, 2
0x180001cda  mov     cs:__isa_inverted, rax
0x180001ce1  mov     cs:__isa_enabled, 6
0x180001ceb  bt      edi, 1Bh
0x180001cef  jnb     loc_180001E2C
0x180001cf5  xor     ecx, ecx
0x180001cf7  xgetbv
0x180001cfa  shl     rdx, 20h
0x180001cfe  or      rdx, rax
0x180001d01  mov     [rsp+38h+arg_0], rdx
0x180001d06  bt      edi, 1Ch
0x180001d0a  jnb     loc_180001E10
0x180001d10  mov     rax, [rsp+38h+arg_0]
0x180001d15  and     al, 6
0x180001d17  cmp     al, 6
0x180001d19  jnz     loc_180001E10
0x180001d1f  mov     eax, cs:__isa_enabled
0x180001d25  mov     dl, 0E0h
0x180001d27  or      eax, 8
0x180001d2a  mov     cs:__isa_available, 3
0x180001d34  mov     cs:__isa_enabled, eax
0x180001d3a  test    r9b, 20h
0x180001d3e  jz      short loc_180001DA2
0x180001d40  or      eax, 20h
0x180001d43  mov     cs:__isa_available, 5
0x180001d4d  mov     cs:__isa_enabled, eax
0x180001d53  mov     ecx, 0D0030000h
0x180001d58  mov     rax, cs:__isa_inverted
0x180001d5f  and     r9d, ecx
0x180001d62  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001d66  mov     cs:__isa_inverted, rax
0x180001d6d  cmp     r9d, ecx
0x180001d70  jnz     short loc_180001DA9
0x180001d72  mov     rax, [rsp+38h+arg_0]
0x180001d77  and     al, dl
0x180001d79  cmp     al, dl
0x180001d7b  jnz     short loc_180001DA2
0x180001d7d  mov     rax, cs:__isa_inverted
0x180001d84  or      cs:__isa_enabled, 40h
0x180001d8b  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001d8f  mov     cs:__isa_available, 6
0x180001d99  mov     cs:__isa_inverted, rax
0x180001da0  jmp     short loc_180001DA9
0x180001da2  mov     rax, cs:__isa_inverted
0x180001da9  bt      esi, 17h
0x180001dad  jnb     short loc_180001DBB
0x180001daf  btr     rax, 18h
0x180001db4  mov     cs:__isa_inverted, rax
0x180001dbb  bt      r10d, 13h
0x180001dc0  jnb     short loc_180001E10
0x180001dc2  mov     rax, [rsp+38h+arg_0]
0x180001dc7  and     al, dl
0x180001dc9  cmp     al, dl
0x180001dcb  jnz     short loc_180001E10
0x180001dcd  mov     rdx, cs:__isa_inverted
0x180001dd4  mov     eax, r11d
0x180001dd7  shr     rax, 10h
0x180001ddb  mov     ecx, r11d
0x180001dde  and     eax, 6
0x180001de1  and     ecx, 400FFh
0x180001de7  or      rax, 1000029h
0x180001ded  mov     cs:__avx10_version, ecx
0x180001df3  not     rax
0x180001df6  and     rdx, rax
0x180001df9  mov     cs:__isa_inverted, rdx
0x180001e00  cmp     cl, 1
0x180001e03  jbe     short loc_180001E10
0x180001e05  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001e09  mov     cs:__isa_inverted, rdx
0x180001e10  bt      r10d, 15h
0x180001e15  jnb     short loc_180001E2C
0x180001e17  mov     rax, [rsp+38h+arg_0]
0x180001e1c  bt      rax, 13h
0x180001e21  jnb     short loc_180001E2C
0x180001e23  btr     cs:__isa_inverted, 7
0x180001e2c  xor     eax, eax
0x180001e2e  add     rsp, 18h
0x180001e32  pop     rdi
0x180001e33  pop     rsi
0x180001e34  pop     rbp
0x180001e35  pop     rbx
0x180001e36  retn
```
