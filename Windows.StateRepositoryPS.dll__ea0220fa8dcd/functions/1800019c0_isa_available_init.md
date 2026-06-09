# __isa_available_init

- ea: `0x1800019c0`
- end: `0x180001c43`
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

- `0x1800019c0`

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
0x1800019c0  push    rbx
0x1800019c2  push    rbp
0x1800019c3  push    rsi
0x1800019c4  push    rdi
0x1800019c5  sub     rsp, 18h
0x1800019c9  xor     eax, eax
0x1800019cb  xor     ecx, ecx
0x1800019cd  cpuid
0x1800019cf  xor     ecx, 6C65746Eh
0x1800019d5  xor     edx, 49656E69h
0x1800019db  or      edx, ecx
0x1800019dd  mov     ebp, eax
0x1800019df  mov     eax, 1
0x1800019e4  xor     ebx, 756E6547h
0x1800019ea  or      edx, ebx
0x1800019ec  lea     ecx, [rax-1]
0x1800019ef  cpuid
0x1800019f1  mov     edi, ecx
0x1800019f3  jnz     short loc_180001A53
0x1800019f5  and     eax, 0FFF3FF0h
0x1800019fa  mov     cs:__memset_fast_string_threshold, 8000h
0x180001a05  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x180001a10  cmp     eax, 106C0h
0x180001a15  jz      short loc_180001A3F
0x180001a17  cmp     eax, 20660h
0x180001a1c  jz      short loc_180001A3F
0x180001a1e  cmp     eax, 20670h
0x180001a23  jz      short loc_180001A3F
0x180001a25  add     eax, 0FFFCF9B0h
0x180001a2a  cmp     eax, 20h ; ' '
0x180001a2d  ja      short loc_180001A53
0x180001a2f  mov     rcx, 100010001h
0x180001a39  bt      rcx, rax
0x180001a3d  jnb     short loc_180001A53
0x180001a3f  mov     r8d, cs:__favor
0x180001a46  or      r8d, 1
0x180001a4a  mov     cs:__favor, r8d
0x180001a51  jmp     short loc_180001A5A
0x180001a53  mov     r8d, cs:__favor
0x180001a5a  xor     r10d, r10d
0x180001a5d  xor     r11d, r11d
0x180001a60  cmp     ebp, 7
0x180001a63  jl      short loc_180001AA7
0x180001a65  xor     ecx, ecx
0x180001a67  lea     eax, [r10+7]
0x180001a6b  cpuid
0x180001a6d  mov     esi, edx
0x180001a6f  mov     r9d, ebx
0x180001a72  bt      ebx, 9
0x180001a76  jnb     short loc_180001A83
0x180001a78  or      r8d, 2
0x180001a7c  mov     cs:__favor, r8d
0x180001a83  cmp     eax, 1
0x180001a86  jl      short loc_180001A95
0x180001a88  mov     eax, 7
0x180001a8d  lea     ecx, [rax-6]
0x180001a90  cpuid
0x180001a92  mov     r10d, edx
0x180001a95  mov     eax, 24h ; '$'
0x180001a9a  cmp     ebp, eax
0x180001a9c  jl      short loc_180001AAC
0x180001a9e  xor     ecx, ecx
0x180001aa0  cpuid
0x180001aa2  mov     r11d, ebx
0x180001aa5  jmp     short loc_180001AAC
0x180001aa7  xor     r9d, r9d
0x180001aaa  xor     esi, esi
0x180001aac  mov     rax, cs:__isa_inverted
0x180001ab3  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001ab7  mov     cs:__isa_available, 1
0x180001ac1  mov     cs:__isa_enabled, 2
0x180001acb  mov     cs:__isa_inverted, rax
0x180001ad2  bt      edi, 14h
0x180001ad6  jnb     short loc_180001AF7
0x180001ad8  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001adc  mov     cs:__isa_available, 2
0x180001ae6  mov     cs:__isa_inverted, rax
0x180001aed  mov     cs:__isa_enabled, 6
0x180001af7  bt      edi, 1Bh
0x180001afb  jnb     loc_180001C38
0x180001b01  xor     ecx, ecx
0x180001b03  xgetbv
0x180001b06  shl     rdx, 20h
0x180001b0a  or      rdx, rax
0x180001b0d  mov     [rsp+38h+arg_0], rdx
0x180001b12  bt      edi, 1Ch
0x180001b16  jnb     loc_180001C1C
0x180001b1c  mov     rax, [rsp+38h+arg_0]
0x180001b21  and     al, 6
0x180001b23  cmp     al, 6
0x180001b25  jnz     loc_180001C1C
0x180001b2b  mov     eax, cs:__isa_enabled
0x180001b31  mov     dl, 0E0h
0x180001b33  or      eax, 8
0x180001b36  mov     cs:__isa_available, 3
0x180001b40  mov     cs:__isa_enabled, eax
0x180001b46  test    r9b, 20h
0x180001b4a  jz      short loc_180001BAE
0x180001b4c  or      eax, 20h
0x180001b4f  mov     cs:__isa_available, 5
0x180001b59  mov     cs:__isa_enabled, eax
0x180001b5f  mov     ecx, 0D0030000h
0x180001b64  mov     rax, cs:__isa_inverted
0x180001b6b  and     r9d, ecx
0x180001b6e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001b72  mov     cs:__isa_inverted, rax
0x180001b79  cmp     r9d, ecx
0x180001b7c  jnz     short loc_180001BB5
0x180001b7e  mov     rax, [rsp+38h+arg_0]
0x180001b83  and     al, dl
0x180001b85  cmp     al, dl
0x180001b87  jnz     short loc_180001BAE
0x180001b89  mov     rax, cs:__isa_inverted
0x180001b90  or      cs:__isa_enabled, 40h
0x180001b97  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001b9b  mov     cs:__isa_available, 6
0x180001ba5  mov     cs:__isa_inverted, rax
0x180001bac  jmp     short loc_180001BB5
0x180001bae  mov     rax, cs:__isa_inverted
0x180001bb5  bt      esi, 17h
0x180001bb9  jnb     short loc_180001BC7
0x180001bbb  btr     rax, 18h
0x180001bc0  mov     cs:__isa_inverted, rax
0x180001bc7  bt      r10d, 13h
0x180001bcc  jnb     short loc_180001C1C
0x180001bce  mov     rax, [rsp+38h+arg_0]
0x180001bd3  and     al, dl
0x180001bd5  cmp     al, dl
0x180001bd7  jnz     short loc_180001C1C
0x180001bd9  mov     rdx, cs:__isa_inverted
0x180001be0  mov     eax, r11d
0x180001be3  shr     rax, 10h
0x180001be7  mov     ecx, r11d
0x180001bea  and     eax, 6
0x180001bed  and     ecx, 400FFh
0x180001bf3  or      rax, 1000029h
0x180001bf9  mov     cs:__avx10_version, ecx
0x180001bff  not     rax
0x180001c02  and     rdx, rax
0x180001c05  mov     cs:__isa_inverted, rdx
0x180001c0c  cmp     cl, 1
0x180001c0f  jbe     short loc_180001C1C
0x180001c11  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001c15  mov     cs:__isa_inverted, rdx
0x180001c1c  bt      r10d, 15h
0x180001c21  jnb     short loc_180001C38
0x180001c23  mov     rax, [rsp+38h+arg_0]
0x180001c28  bt      rax, 13h
0x180001c2d  jnb     short loc_180001C38
0x180001c2f  btr     cs:__isa_inverted, 7
0x180001c38  xor     eax, eax
0x180001c3a  add     rsp, 18h
0x180001c3e  pop     rdi
0x180001c3f  pop     rsi
0x180001c40  pop     rbp
0x180001c41  pop     rbx
0x180001c42  retn
```
