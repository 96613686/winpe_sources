# __isa_available_init

- ea: `0x180001960`
- end: `0x180001be3`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001598`
- `0x1800016d4`

## callees

- `0x180001960`

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
0x180001960  push    rbx
0x180001962  push    rbp
0x180001963  push    rsi
0x180001964  push    rdi
0x180001965  sub     rsp, 18h
0x180001969  xor     eax, eax
0x18000196b  xor     ecx, ecx
0x18000196d  cpuid
0x18000196f  xor     ecx, 6C65746Eh
0x180001975  xor     edx, 49656E69h
0x18000197b  or      edx, ecx
0x18000197d  mov     ebp, eax
0x18000197f  mov     eax, 1
0x180001984  xor     ebx, 756E6547h
0x18000198a  or      edx, ebx
0x18000198c  lea     ecx, [rax-1]
0x18000198f  cpuid
0x180001991  mov     edi, ecx
0x180001993  jnz     short loc_1800019F3
0x180001995  and     eax, 0FFF3FF0h
0x18000199a  mov     cs:__memset_fast_string_threshold, 8000h
0x1800019a5  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1800019b0  cmp     eax, 106C0h
0x1800019b5  jz      short loc_1800019DF
0x1800019b7  cmp     eax, 20660h
0x1800019bc  jz      short loc_1800019DF
0x1800019be  cmp     eax, 20670h
0x1800019c3  jz      short loc_1800019DF
0x1800019c5  add     eax, 0FFFCF9B0h
0x1800019ca  cmp     eax, 20h ; ' '
0x1800019cd  ja      short loc_1800019F3
0x1800019cf  mov     rcx, 100010001h
0x1800019d9  bt      rcx, rax
0x1800019dd  jnb     short loc_1800019F3
0x1800019df  mov     r8d, cs:__favor
0x1800019e6  or      r8d, 1
0x1800019ea  mov     cs:__favor, r8d
0x1800019f1  jmp     short loc_1800019FA
0x1800019f3  mov     r8d, cs:__favor
0x1800019fa  xor     r10d, r10d
0x1800019fd  xor     r11d, r11d
0x180001a00  cmp     ebp, 7
0x180001a03  jl      short loc_180001A47
0x180001a05  xor     ecx, ecx
0x180001a07  lea     eax, [r10+7]
0x180001a0b  cpuid
0x180001a0d  mov     esi, edx
0x180001a0f  mov     r9d, ebx
0x180001a12  bt      ebx, 9
0x180001a16  jnb     short loc_180001A23
0x180001a18  or      r8d, 2
0x180001a1c  mov     cs:__favor, r8d
0x180001a23  cmp     eax, 1
0x180001a26  jl      short loc_180001A35
0x180001a28  mov     eax, 7
0x180001a2d  lea     ecx, [rax-6]
0x180001a30  cpuid
0x180001a32  mov     r10d, edx
0x180001a35  mov     eax, 24h ; '$'
0x180001a3a  cmp     ebp, eax
0x180001a3c  jl      short loc_180001A4C
0x180001a3e  xor     ecx, ecx
0x180001a40  cpuid
0x180001a42  mov     r11d, ebx
0x180001a45  jmp     short loc_180001A4C
0x180001a47  xor     r9d, r9d
0x180001a4a  xor     esi, esi
0x180001a4c  mov     rax, cs:__isa_inverted
0x180001a53  and     rax, 0FFFFFFFFFFFFFFFEh
0x180001a57  mov     cs:__isa_available, 1
0x180001a61  mov     cs:__isa_enabled, 2
0x180001a6b  mov     cs:__isa_inverted, rax
0x180001a72  bt      edi, 14h
0x180001a76  jnb     short loc_180001A97
0x180001a78  and     rax, 0FFFFFFFFFFFFFFEFh
0x180001a7c  mov     cs:__isa_available, 2
0x180001a86  mov     cs:__isa_inverted, rax
0x180001a8d  mov     cs:__isa_enabled, 6
0x180001a97  bt      edi, 1Bh
0x180001a9b  jnb     loc_180001BD8
0x180001aa1  xor     ecx, ecx
0x180001aa3  xgetbv
0x180001aa6  shl     rdx, 20h
0x180001aaa  or      rdx, rax
0x180001aad  mov     [rsp+38h+arg_0], rdx
0x180001ab2  bt      edi, 1Ch
0x180001ab6  jnb     loc_180001BBC
0x180001abc  mov     rax, [rsp+38h+arg_0]
0x180001ac1  and     al, 6
0x180001ac3  cmp     al, 6
0x180001ac5  jnz     loc_180001BBC
0x180001acb  mov     eax, cs:__isa_enabled
0x180001ad1  mov     dl, 0E0h
0x180001ad3  or      eax, 8
0x180001ad6  mov     cs:__isa_available, 3
0x180001ae0  mov     cs:__isa_enabled, eax
0x180001ae6  test    r9b, 20h
0x180001aea  jz      short loc_180001B4E
0x180001aec  or      eax, 20h
0x180001aef  mov     cs:__isa_available, 5
0x180001af9  mov     cs:__isa_enabled, eax
0x180001aff  mov     ecx, 0D0030000h
0x180001b04  mov     rax, cs:__isa_inverted
0x180001b0b  and     r9d, ecx
0x180001b0e  and     rax, 0FFFFFFFFFFFFFFFDh
0x180001b12  mov     cs:__isa_inverted, rax
0x180001b19  cmp     r9d, ecx
0x180001b1c  jnz     short loc_180001B55
0x180001b1e  mov     rax, [rsp+38h+arg_0]
0x180001b23  and     al, dl
0x180001b25  cmp     al, dl
0x180001b27  jnz     short loc_180001B4E
0x180001b29  mov     rax, cs:__isa_inverted
0x180001b30  or      cs:__isa_enabled, 40h
0x180001b37  and     rax, 0FFFFFFFFFFFFFFDBh
0x180001b3b  mov     cs:__isa_available, 6
0x180001b45  mov     cs:__isa_inverted, rax
0x180001b4c  jmp     short loc_180001B55
0x180001b4e  mov     rax, cs:__isa_inverted
0x180001b55  bt      esi, 17h
0x180001b59  jnb     short loc_180001B67
0x180001b5b  btr     rax, 18h
0x180001b60  mov     cs:__isa_inverted, rax
0x180001b67  bt      r10d, 13h
0x180001b6c  jnb     short loc_180001BBC
0x180001b6e  mov     rax, [rsp+38h+arg_0]
0x180001b73  and     al, dl
0x180001b75  cmp     al, dl
0x180001b77  jnz     short loc_180001BBC
0x180001b79  mov     rdx, cs:__isa_inverted
0x180001b80  mov     eax, r11d
0x180001b83  shr     rax, 10h
0x180001b87  mov     ecx, r11d
0x180001b8a  and     eax, 6
0x180001b8d  and     ecx, 400FFh
0x180001b93  or      rax, 1000029h
0x180001b99  mov     cs:__avx10_version, ecx
0x180001b9f  not     rax
0x180001ba2  and     rdx, rax
0x180001ba5  mov     cs:__isa_inverted, rdx
0x180001bac  cmp     cl, 1
0x180001baf  jbe     short loc_180001BBC
0x180001bb1  and     rdx, 0FFFFFFFFFFFFFFBFh
0x180001bb5  mov     cs:__isa_inverted, rdx
0x180001bbc  bt      r10d, 15h
0x180001bc1  jnb     short loc_180001BD8
0x180001bc3  mov     rax, [rsp+38h+arg_0]
0x180001bc8  bt      rax, 13h
0x180001bcd  jnb     short loc_180001BD8
0x180001bcf  btr     cs:__isa_inverted, 7
0x180001bd8  xor     eax, eax
0x180001bda  add     rsp, 18h
0x180001bde  pop     rdi
0x180001bdf  pop     rsi
0x180001be0  pop     rbp
0x180001be1  pop     rbx
0x180001be2  retn
```
