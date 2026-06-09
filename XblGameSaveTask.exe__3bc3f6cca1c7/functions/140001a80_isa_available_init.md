# __isa_available_init

- ea: `0x140001a80`
- end: `0x140001d03`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400014e4`

## callees

- `0x140001a80`

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
0x140001a80  push    rbx
0x140001a82  push    rbp
0x140001a83  push    rsi
0x140001a84  push    rdi
0x140001a85  sub     rsp, 18h
0x140001a89  xor     eax, eax
0x140001a8b  xor     ecx, ecx
0x140001a8d  cpuid
0x140001a8f  xor     ecx, 6C65746Eh
0x140001a95  xor     edx, 49656E69h
0x140001a9b  or      edx, ecx
0x140001a9d  mov     ebp, eax
0x140001a9f  mov     eax, 1
0x140001aa4  xor     ebx, 756E6547h
0x140001aaa  or      edx, ebx
0x140001aac  lea     ecx, [rax-1]
0x140001aaf  cpuid
0x140001ab1  mov     edi, ecx
0x140001ab3  jnz     short loc_140001B13
0x140001ab5  and     eax, 0FFF3FF0h
0x140001aba  mov     cs:__memset_fast_string_threshold, 8000h
0x140001ac5  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x140001ad0  cmp     eax, 106C0h
0x140001ad5  jz      short loc_140001AFF
0x140001ad7  cmp     eax, 20660h
0x140001adc  jz      short loc_140001AFF
0x140001ade  cmp     eax, 20670h
0x140001ae3  jz      short loc_140001AFF
0x140001ae5  add     eax, 0FFFCF9B0h
0x140001aea  cmp     eax, 20h ; ' '
0x140001aed  ja      short loc_140001B13
0x140001aef  mov     rcx, 100010001h
0x140001af9  bt      rcx, rax
0x140001afd  jnb     short loc_140001B13
0x140001aff  mov     r8d, cs:__favor
0x140001b06  or      r8d, 1
0x140001b0a  mov     cs:__favor, r8d
0x140001b11  jmp     short loc_140001B1A
0x140001b13  mov     r8d, cs:__favor
0x140001b1a  xor     r10d, r10d
0x140001b1d  xor     r11d, r11d
0x140001b20  cmp     ebp, 7
0x140001b23  jl      short loc_140001B67
0x140001b25  xor     ecx, ecx
0x140001b27  lea     eax, [r10+7]
0x140001b2b  cpuid
0x140001b2d  mov     esi, edx
0x140001b2f  mov     r9d, ebx
0x140001b32  bt      ebx, 9
0x140001b36  jnb     short loc_140001B43
0x140001b38  or      r8d, 2
0x140001b3c  mov     cs:__favor, r8d
0x140001b43  cmp     eax, 1
0x140001b46  jl      short loc_140001B55
0x140001b48  mov     eax, 7
0x140001b4d  lea     ecx, [rax-6]
0x140001b50  cpuid
0x140001b52  mov     r10d, edx
0x140001b55  mov     eax, 24h ; '$'
0x140001b5a  cmp     ebp, eax
0x140001b5c  jl      short loc_140001B6C
0x140001b5e  xor     ecx, ecx
0x140001b60  cpuid
0x140001b62  mov     r11d, ebx
0x140001b65  jmp     short loc_140001B6C
0x140001b67  xor     r9d, r9d
0x140001b6a  xor     esi, esi
0x140001b6c  mov     rax, cs:__isa_inverted
0x140001b73  and     rax, 0FFFFFFFFFFFFFFFEh
0x140001b77  mov     cs:__isa_available, 1
0x140001b81  mov     cs:__isa_enabled, 2
0x140001b8b  mov     cs:__isa_inverted, rax
0x140001b92  bt      edi, 14h
0x140001b96  jnb     short loc_140001BB7
0x140001b98  and     rax, 0FFFFFFFFFFFFFFEFh
0x140001b9c  mov     cs:__isa_available, 2
0x140001ba6  mov     cs:__isa_inverted, rax
0x140001bad  mov     cs:__isa_enabled, 6
0x140001bb7  bt      edi, 1Bh
0x140001bbb  jnb     loc_140001CF8
0x140001bc1  xor     ecx, ecx
0x140001bc3  xgetbv
0x140001bc6  shl     rdx, 20h
0x140001bca  or      rdx, rax
0x140001bcd  mov     [rsp+38h+arg_0], rdx
0x140001bd2  bt      edi, 1Ch
0x140001bd6  jnb     loc_140001CDC
0x140001bdc  mov     rax, [rsp+38h+arg_0]
0x140001be1  and     al, 6
0x140001be3  cmp     al, 6
0x140001be5  jnz     loc_140001CDC
0x140001beb  mov     eax, cs:__isa_enabled
0x140001bf1  mov     dl, 0E0h
0x140001bf3  or      eax, 8
0x140001bf6  mov     cs:__isa_available, 3
0x140001c00  mov     cs:__isa_enabled, eax
0x140001c06  test    r9b, 20h
0x140001c0a  jz      short loc_140001C6E
0x140001c0c  or      eax, 20h
0x140001c0f  mov     cs:__isa_available, 5
0x140001c19  mov     cs:__isa_enabled, eax
0x140001c1f  mov     ecx, 0D0030000h
0x140001c24  mov     rax, cs:__isa_inverted
0x140001c2b  and     r9d, ecx
0x140001c2e  and     rax, 0FFFFFFFFFFFFFFFDh
0x140001c32  mov     cs:__isa_inverted, rax
0x140001c39  cmp     r9d, ecx
0x140001c3c  jnz     short loc_140001C75
0x140001c3e  mov     rax, [rsp+38h+arg_0]
0x140001c43  and     al, dl
0x140001c45  cmp     al, dl
0x140001c47  jnz     short loc_140001C6E
0x140001c49  mov     rax, cs:__isa_inverted
0x140001c50  or      cs:__isa_enabled, 40h
0x140001c57  and     rax, 0FFFFFFFFFFFFFFDBh
0x140001c5b  mov     cs:__isa_available, 6
0x140001c65  mov     cs:__isa_inverted, rax
0x140001c6c  jmp     short loc_140001C75
0x140001c6e  mov     rax, cs:__isa_inverted
0x140001c75  bt      esi, 17h
0x140001c79  jnb     short loc_140001C87
0x140001c7b  btr     rax, 18h
0x140001c80  mov     cs:__isa_inverted, rax
0x140001c87  bt      r10d, 13h
0x140001c8c  jnb     short loc_140001CDC
0x140001c8e  mov     rax, [rsp+38h+arg_0]
0x140001c93  and     al, dl
0x140001c95  cmp     al, dl
0x140001c97  jnz     short loc_140001CDC
0x140001c99  mov     rdx, cs:__isa_inverted
0x140001ca0  mov     eax, r11d
0x140001ca3  shr     rax, 10h
0x140001ca7  mov     ecx, r11d
0x140001caa  and     eax, 6
0x140001cad  and     ecx, 400FFh
0x140001cb3  or      rax, 1000029h
0x140001cb9  mov     cs:__avx10_version, ecx
0x140001cbf  not     rax
0x140001cc2  and     rdx, rax
0x140001cc5  mov     cs:__isa_inverted, rdx
0x140001ccc  cmp     cl, 1
0x140001ccf  jbe     short loc_140001CDC
0x140001cd1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x140001cd5  mov     cs:__isa_inverted, rdx
0x140001cdc  bt      r10d, 15h
0x140001ce1  jnb     short loc_140001CF8
0x140001ce3  mov     rax, [rsp+38h+arg_0]
0x140001ce8  bt      rax, 13h
0x140001ced  jnb     short loc_140001CF8
0x140001cef  btr     cs:__isa_inverted, 7
0x140001cf8  xor     eax, eax
0x140001cfa  add     rsp, 18h
0x140001cfe  pop     rdi
0x140001cff  pop     rsi
0x140001d00  pop     rbp
0x140001d01  pop     rbx
0x140001d02  retn
```
