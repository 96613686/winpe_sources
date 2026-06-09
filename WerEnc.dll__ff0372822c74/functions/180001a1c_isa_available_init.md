# __isa_available_init

- ea: `0x180001a1c`
- end: `0x180001c9f`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800015ec`
- `0x180001728`

## callees

- `0x180001a1c`

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
0x180001a1c  push    rbx
0x180001a1e  push    rbp
0x180001a1f  push    rsi
0x180001a20  push    rdi
0x180001a21  sub     rsp, 18h
0x180001a25  xor     eax, eax
0x180001a27  xor     ecx, ecx
0x180001a29  cpuid
0x180001a2b  xor     ecx, 6C65746Eh
0x180001a31  xor     edx, 49656E69h
0x180001a37  or      edx, ecx
0x180001a39  mov     ebp, eax
0x180001a3b  mov     eax, 1
0x180001a40  xor     ebx, 756E6547h
0x180001a46  or      edx, ebx
0x180001a48  lea     ecx, [rax-1]
0x180001a4b  cpuid
0x180001a4d  mov     edi, ecx
0x180001a4f  jnz     short loc_180001AAF
0x180001a51  and     eax, 0FFF3FF0h
0x180001a56  mov     cs:__memset_fast_string_threshold, 8000h
0x180001a61  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001a6c  cmp     eax, 106C0h
0x180001a71  jz      short loc_180001A9B
0x180001a73  cmp     eax, 20660h
0x180001a78  jz      short loc_180001A9B
0x180001a7a  cmp     eax, 20670h
0x180001a7f  jz      short loc_180001A9B
0x180001a81  add     eax, 0FFFCF9B0h
0x180001a86  cmp     eax, 20h ; ' '
0x180001a89  ja      short loc_180001AAF
0x180001a8b  mov     rcx, 100010001h
0x180001a95  bt      rcx, rax
0x180001a99  jnb     short loc_180001AAF
0x180001a9b  mov     r8d, cs:__favor
0x180001aa2  or      r8d, 1
0x180001aa6  mov     cs:__favor, r8d
0x180001aad  jmp     short loc_180001AB6
0x180001aaf  mov     r8d, cs:__favor
0x180001ab6  xor     r10d, r10d
0x180001ab9  xor     r11d, r11d
0x180001abc  cmp     ebp, 7
0x180001abf  jl      short loc_180001B03
0x180001ac1  xor     ecx, ecx
0x180001ac3  lea     eax, [r10+7]
0x180001ac7  cpuid
0x180001ac9  mov     esi, edx
0x180001acb  mov     r9d, ebx
0x180001ace  bt      ebx, 9
0x180001ad2  jnb     short loc_180001ADF
0x180001ad4  or      r8d, 2
0x180001ad8  mov     cs:__favor, r8d
0x180001adf  cmp     eax, 1
0x180001ae2  jl      short loc_180001AF1
0x180001ae4  mov     eax, 7
0x180001ae9  lea     ecx, [rax-6]
0x180001aec  cpuid
0x180001aee  mov     r10d, edx
0x180001af1  mov     eax, 24h ; '$'
0x180001af6  cmp     ebp, eax
0x180001af8  jl      short loc_180001B08
0x180001afa  xor     ecx, ecx
0x180001afc  cpuid
0x180001afe  mov     r11d, ebx
0x180001b01  jmp     short loc_180001B08
0x180001b03  xor     r9d, r9d
0x180001b06  xor     esi, esi
0x180001b08  mov     rax, cs:__isa_inverted
0x180001b0f  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001b13  mov     cs:__isa_available, 1
0x180001b1d  mov     cs:__isa_enabled, 2
0x180001b27  mov     cs:__isa_inverted, rax
0x180001b2e  bt      edi, 14h
0x180001b32  jnb     short loc_180001B53
0x180001b34  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001b38  mov     cs:__isa_available, 2
0x180001b42  mov     cs:__isa_inverted, rax
0x180001b49  mov     cs:__isa_enabled, 6
0x180001b53  bt      edi, 1Bh
0x180001b57  jnb     loc_180001C94
0x180001b5d  xor     ecx, ecx
0x180001b5f  xgetbv
0x180001b62  shl     rdx, 20h
0x180001b66  or      rdx, rax
0x180001b69  mov     [rsp+38h+arg_0], rdx
0x180001b6e  bt      edi, 1Ch
0x180001b72  jnb     loc_180001C78
0x180001b78  mov     rax, [rsp+38h+arg_0]
0x180001b7d  and     al, 6
0x180001b7f  cmp     al, 6
0x180001b81  jnz     loc_180001C78
0x180001b87  mov     eax, cs:__isa_enabled
0x180001b8d  mov     dl, 0E0h
0x180001b8f  or      eax, 8
0x180001b92  mov     cs:__isa_available, 3
0x180001b9c  mov     cs:__isa_enabled, eax
0x180001ba2  test    r9b, 20h
0x180001ba6  jz      short loc_180001C0A
0x180001ba8  or      eax, 20h
0x180001bab  mov     cs:__isa_available, 5
0x180001bb5  mov     cs:__isa_enabled, eax
0x180001bbb  mov     ecx, 0D0030000h
0x180001bc0  mov     rax, cs:__isa_inverted
0x180001bc7  and     r9d, ecx
0x180001bca  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001bce  mov     cs:__isa_inverted, rax
0x180001bd5  cmp     r9d, ecx
0x180001bd8  jnz     short loc_180001C11
0x180001bda  mov     rax, [rsp+38h+arg_0]
0x180001bdf  and     al, dl
0x180001be1  cmp     al, dl
0x180001be3  jnz     short loc_180001C0A
0x180001be5  mov     rax, cs:__isa_inverted
0x180001bec  or      cs:__isa_enabled, 40h
0x180001bf3  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001bf7  mov     cs:__isa_available, 6
0x180001c01  mov     cs:__isa_inverted, rax
0x180001c08  jmp     short loc_180001C11
0x180001c0a  mov     rax, cs:__isa_inverted
0x180001c11  bt      esi, 17h
0x180001c15  jnb     short loc_180001C23
0x180001c17  btr     rax, 18h
0x180001c1c  mov     cs:__isa_inverted, rax
0x180001c23  bt      r10d, 13h
0x180001c28  jnb     short loc_180001C78
0x180001c2a  mov     rax, [rsp+38h+arg_0]
0x180001c2f  and     al, dl
0x180001c31  cmp     al, dl
0x180001c33  jnz     short loc_180001C78
0x180001c35  mov     rdx, cs:__isa_inverted
0x180001c3c  mov     eax, r11d
0x180001c3f  shr     rax, 10h
0x180001c43  mov     ecx, r11d
0x180001c46  and     eax, 6
0x180001c49  and     ecx, 400FFh
0x180001c4f  or      rax, 1000029h
0x180001c55  mov     cs:__avx10_version, ecx
0x180001c5b  not     rax
0x180001c5e  and     rdx, rax
0x180001c61  mov     cs:__isa_inverted, rdx
0x180001c68  cmp     cl, 1
0x180001c6b  jbe     short loc_180001C78
0x180001c6d  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001c71  mov     cs:__isa_inverted, rdx
0x180001c78  bt      r10d, 15h
0x180001c7d  jnb     short loc_180001C94
0x180001c7f  mov     rax, [rsp+38h+arg_0]
0x180001c84  bt      rax, 13h
0x180001c89  jnb     short loc_180001C94
0x180001c8b  btr     cs:__isa_inverted, 7
0x180001c94  xor     eax, eax
0x180001c96  add     rsp, 18h
0x180001c9a  pop     rdi
0x180001c9b  pop     rsi
0x180001c9c  pop     rbp
0x180001c9d  pop     rbx
0x180001c9e  retn
```
