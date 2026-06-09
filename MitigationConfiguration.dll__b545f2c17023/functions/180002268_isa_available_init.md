# __isa_available_init

- ea: `0x180002268`
- end: `0x1800024eb`
- name: `__isa_available_init`
- size: `643`
- prototype: `int __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001ca8`
- `0x180001de4`

## callees

- `0x180002268`

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
0x180002268  push    rbx
0x18000226a  push    rbp
0x18000226b  push    rsi
0x18000226c  push    rdi
0x18000226d  sub     rsp, 18h
0x180002271  xor     eax, eax
0x180002273  xor     ecx, ecx
0x180002275  cpuid
0x180002277  xor     ecx, 6C65746Eh
0x18000227d  xor     edx, 49656E69h
0x180002283  or      edx, ecx
0x180002285  mov     ebp, eax
0x180002287  mov     eax, 1
0x18000228c  xor     ebx, 756E6547h
0x180002292  or      edx, ebx
0x180002294  lea     ecx, [rax-1]
0x180002297  cpuid
0x180002299  mov     edi, ecx
0x18000229b  jnz     short loc_1800022FB
0x18000229d  and     eax, 0FFF3FF0h
0x1800022a2  mov     cs:__memset_fast_string_threshold, 8000h
0x1800022ad  mov     cs:__memset_nt_threshold, 0FFFFFFFFFFFFFFFFh
0x1800022b8  cmp     eax, 106C0h
0x1800022bd  jz      short loc_1800022E7
0x1800022bf  cmp     eax, 20660h
0x1800022c4  jz      short loc_1800022E7
0x1800022c6  cmp     eax, 20670h
0x1800022cb  jz      short loc_1800022E7
0x1800022cd  add     eax, 0FFFCF9B0h
0x1800022d2  cmp     eax, 20h ; ' '
0x1800022d5  ja      short loc_1800022FB
0x1800022d7  mov     rcx, 100010001h
0x1800022e1  bt      rcx, rax
0x1800022e5  jnb     short loc_1800022FB
0x1800022e7  mov     r8d, cs:__favor
0x1800022ee  or      r8d, 1
0x1800022f2  mov     cs:__favor, r8d
0x1800022f9  jmp     short loc_180002302
0x1800022fb  mov     r8d, cs:__favor
0x180002302  xor     r10d, r10d
0x180002305  xor     r11d, r11d
0x180002308  cmp     ebp, 7
0x18000230b  jl      short loc_18000234F
0x18000230d  xor     ecx, ecx
0x18000230f  lea     eax, [r10+7]
0x180002313  cpuid
0x180002315  mov     esi, edx
0x180002317  mov     r9d, ebx
0x18000231a  bt      ebx, 9
0x18000231e  jnb     short loc_18000232B
0x180002320  or      r8d, 2
0x180002324  mov     cs:__favor, r8d
0x18000232b  cmp     eax, 1
0x18000232e  jl      short loc_18000233D
0x180002330  mov     eax, 7
0x180002335  lea     ecx, [rax-6]
0x180002338  cpuid
0x18000233a  mov     r10d, edx
0x18000233d  mov     eax, 24h ; '$'
0x180002342  cmp     ebp, eax
0x180002344  jl      short loc_180002354
0x180002346  xor     ecx, ecx
0x180002348  cpuid
0x18000234a  mov     r11d, ebx
0x18000234d  jmp     short loc_180002354
0x18000234f  xor     r9d, r9d
0x180002352  xor     esi, esi
0x180002354  mov     rax, cs:__isa_inverted
0x18000235b  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000235f  mov     cs:__isa_available, 1
0x180002369  mov     cs:__isa_enabled, 2
0x180002373  mov     cs:__isa_inverted, rax
0x18000237a  bt      edi, 14h
0x18000237e  jnb     short loc_18000239F
0x180002380  and     rax, 0FFFFFFFFFFFFFFEFh
0x180002384  mov     cs:__isa_available, 2
0x18000238e  mov     cs:__isa_inverted, rax
0x180002395  mov     cs:__isa_enabled, 6
0x18000239f  bt      edi, 1Bh
0x1800023a3  jnb     loc_1800024E0
0x1800023a9  xor     ecx, ecx
0x1800023ab  xgetbv
0x1800023ae  shl     rdx, 20h
0x1800023b2  or      rdx, rax
0x1800023b5  mov     [rsp+38h+arg_0], rdx
0x1800023ba  bt      edi, 1Ch
0x1800023be  jnb     loc_1800024C4
0x1800023c4  mov     rax, [rsp+38h+arg_0]
0x1800023c9  and     al, 6
0x1800023cb  cmp     al, 6
0x1800023cd  jnz     loc_1800024C4
0x1800023d3  mov     eax, cs:__isa_enabled
0x1800023d9  mov     dl, 0E0h
0x1800023db  or      eax, 8
0x1800023de  mov     cs:__isa_available, 3
0x1800023e8  mov     cs:__isa_enabled, eax
0x1800023ee  test    r9b, 20h
0x1800023f2  jz      short loc_180002456
0x1800023f4  or      eax, 20h
0x1800023f7  mov     cs:__isa_available, 5
0x180002401  mov     cs:__isa_enabled, eax
0x180002407  mov     ecx, 0D0030000h
0x18000240c  mov     rax, cs:__isa_inverted
0x180002413  and     r9d, ecx
0x180002416  and     rax, 0FFFFFFFFFFFFFFFDh
0x18000241a  mov     cs:__isa_inverted, rax
0x180002421  cmp     r9d, ecx
0x180002424  jnz     short loc_18000245D
0x180002426  mov     rax, [rsp+38h+arg_0]
0x18000242b  and     al, dl
0x18000242d  cmp     al, dl
0x18000242f  jnz     short loc_180002456
0x180002431  mov     rax, cs:__isa_inverted
0x180002438  or      cs:__isa_enabled, 40h
0x18000243f  and     rax, 0FFFFFFFFFFFFFFDBh
0x180002443  mov     cs:__isa_available, 6
0x18000244d  mov     cs:__isa_inverted, rax
0x180002454  jmp     short loc_18000245D
0x180002456  mov     rax, cs:__isa_inverted
0x18000245d  bt      esi, 17h
0x180002461  jnb     short loc_18000246F
0x180002463  btr     rax, 18h
0x180002468  mov     cs:__isa_inverted, rax
0x18000246f  bt      r10d, 13h
0x180002474  jnb     short loc_1800024C4
0x180002476  mov     rax, [rsp+38h+arg_0]
0x18000247b  and     al, dl
0x18000247d  cmp     al, dl
0x18000247f  jnz     short loc_1800024C4
0x180002481  mov     rdx, cs:__isa_inverted
0x180002488  mov     eax, r11d
0x18000248b  shr     rax, 10h
0x18000248f  mov     ecx, r11d
0x180002492  and     eax, 6
0x180002495  and     ecx, 400FFh
0x18000249b  or      rax, 1000029h
0x1800024a1  mov     cs:__avx10_version, ecx
0x1800024a7  not     rax
0x1800024aa  and     rdx, rax
0x1800024ad  mov     cs:__isa_inverted, rdx
0x1800024b4  cmp     cl, 1
0x1800024b7  jbe     short loc_1800024C4
0x1800024b9  and     rdx, 0FFFFFFFFFFFFFFBFh
0x1800024bd  mov     cs:__isa_inverted, rdx
0x1800024c4  bt      r10d, 15h
0x1800024c9  jnb     short loc_1800024E0
0x1800024cb  mov     rax, [rsp+38h+arg_0]
0x1800024d0  bt      rax, 13h
0x1800024d5  jnb     short loc_1800024E0
0x1800024d7  btr     cs:__isa_inverted, 7
0x1800024e0  xor     eax, eax
0x1800024e2  add     rsp, 18h
0x1800024e6  pop     rdi
0x1800024e7  pop     rsi
0x1800024e8  pop     rbp
0x1800024e9  pop     rbx
0x1800024ea  retn
```
