# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180002448`
- end: `0x18000261b`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `467`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180002670`
- `0x180004bac`

## callees

- `0x18000117c`
- `0x180001188`
- `0x1800019d0`
- `0x180002448`
- `0x180003558`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800024f1`
- `msvcrt!memcpy_s` at `0x18000252b`
- `msvcrt!memcpy_s` at `0x1800024f1`
- `msvcrt!memcpy_s` at `0x18000252b`

## pseudocode

```c
_BOOL8 __fastcall ATL::CExpansionVector::Add(void **this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v6; // rax
  __int64 v7; // r12
  void *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // r15
  void *v11; // rax
  void *v12; // rbx
  errno_t v13; // eax
  errno_t v14; // eax
  void *v15; // rax
  void *v16; // rcx
  void *v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  int v21; // esi

  if ( a2 && a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v7 = 2 * v6 + 2;
    v8 = operator new[](saturated_mul(v7, 2u));
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = 2LL * ((int)v9 + 1);
    v11 = operator new[](saturated_mul(v10, 2u));
    v12 = v11;
    if ( !v8 || !v11 )
      goto LABEL_26;
    v13 = memcpy_s(v8, v7, a2, v7);
    if ( v13 )
    {
      if ( v13 == 12 )
        goto LABEL_29;
      if ( v13 == 22 || v13 == 34 )
        goto LABEL_31;
      if ( v13 != 80 )
        goto LABEL_30;
    }
    v14 = memcpy_s(v12, v10, a3, v10);
    if ( !v14 )
    {
LABEL_19:
      v15 = _recalloc(*this, *((_DWORD *)this + 4) + 1, 8u);
      if ( v15 )
      {
        v16 = this[1];
        *this = v15;
        v17 = _recalloc(v16, *((_DWORD *)this + 4) + 1, 8u);
        if ( v17 )
        {
          v18 = *((int *)this + 4);
          this[1] = v17;
          v19 = (char *)*this + 8 * v18;
          if ( v19 )
            *v19 = v8;
          v20 = (char *)this[1] + 8 * v18;
          if ( v20 )
            *v20 = v12;
          ++*((_DWORD *)this + 4);
          v8 = 0;
          v21 = 0;
          v12 = 0;
          goto LABEL_27;
        }
      }
LABEL_26:
      v21 = -2147024882;
LABEL_27:
      operator delete[](v12);
      operator delete[](v8);
      return v21 >= 0;
    }
    if ( v14 != 12 )
    {
      if ( v14 != 22 && v14 != 34 )
      {
        if ( v14 == 80 )
          goto LABEL_19;
LABEL_30:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_31:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_29:
    ATL::AtlThrowImpl(-2147024882);
  }
  return 0;
}

```

## disassembly

```asm
0x180002448  push    rbx
0x18000244a  push    rbp
0x18000244b  push    rsi
0x18000244c  push    rdi
0x18000244d  push    r12
0x18000244f  push    r13
0x180002451  push    r14
0x180002453  push    r15
0x180002455  sub     rsp, 28h
0x180002459  xor     r13d, r13d
0x18000245c  mov     r14, r8
0x18000245f  mov     rbp, rdx
0x180002462  mov     rsi, rcx
0x180002465  test    rdx, rdx
0x180002468  jz      loc_1800025E7
0x18000246e  test    r8, r8
0x180002471  jz      loc_1800025E7
0x180002477  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000247b  mov     rax, rbx
0x18000247e  inc     rax
0x180002481  cmp     [rdx+rax*2], r13w
0x180002486  jnz     short loc_18000247E
0x180002488  lea     r12, ds:2[rax*2]
0x180002490  mov     eax, 2
0x180002495  mul     r12
0x180002498  cmovb   rax, rbx
0x18000249c  mov     rcx, rax; unsigned __int64
0x18000249f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800024a4  mov     rdi, rax
0x1800024a7  mov     rcx, rbx
0x1800024aa  inc     rcx
0x1800024ad  cmp     [r14+rcx*2], r13w
0x1800024b2  jnz     short loc_1800024AA
0x1800024b4  inc     ecx
0x1800024b6  mov     eax, 2
0x1800024bb  movsxd  r15, ecx
0x1800024be  add     r15, r15
0x1800024c1  mul     r15
0x1800024c4  cmovb   rax, rbx
0x1800024c8  mov     rcx, rax; unsigned __int64
0x1800024cb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800024d0  mov     rbx, rax
0x1800024d3  test    rdi, rdi
0x1800024d6  jz      loc_1800025C9
0x1800024dc  test    rax, rax
0x1800024df  jz      loc_1800025C9
0x1800024e5  mov     r9, r12; SourceSize
0x1800024e8  mov     r8, rbp; Source
0x1800024eb  mov     rdx, r12; DestinationSize
0x1800024ee  mov     rcx, rdi; Destination
0x1800024f1  call    cs:__imp_memcpy_s
0x1800024f7  test    eax, eax
0x1800024f9  jz      short loc_18000251F
0x1800024fb  cmp     eax, 0Ch
0x1800024fe  jz      loc_1800025FA
0x180002504  cmp     eax, 16h
0x180002507  jz      loc_180002610
0x18000250d  cmp     eax, 22h ; '"'
0x180002510  jz      loc_180002610
0x180002516  cmp     eax, 50h ; 'P'
0x180002519  jnz     loc_180002605
0x18000251f  mov     r9, r15; SourceSize
0x180002522  mov     r8, r14; Source
0x180002525  mov     rdx, r15; DestinationSize
0x180002528  mov     rcx, rbx; Destination
0x18000252b  call    cs:__imp_memcpy_s
0x180002531  test    eax, eax
0x180002533  jz      short loc_180002559
0x180002535  cmp     eax, 0Ch
0x180002538  jz      loc_1800025FA
0x18000253e  cmp     eax, 16h
0x180002541  jz      loc_180002610
0x180002547  cmp     eax, 22h ; '"'
0x18000254a  jz      loc_180002610
0x180002550  cmp     eax, 50h ; 'P'
0x180002553  jnz     loc_180002605
0x180002559  mov     eax, [rsi+10h]
0x18000255c  mov     ebp, 8
0x180002561  mov     rcx, [rsi]; Block
0x180002564  inc     eax
0x180002566  movsxd  rdx, eax; Count
0x180002569  mov     r8d, ebp; Size
0x18000256c  call    cs:__imp__recalloc
0x180002572  test    rax, rax
0x180002575  jz      short loc_1800025C9
0x180002577  mov     rcx, [rsi+8]; Block
0x18000257b  mov     r8d, ebp; Size
0x18000257e  mov     [rsi], rax
0x180002581  mov     eax, [rsi+10h]
0x180002584  inc     eax
0x180002586  movsxd  rdx, eax; Count
0x180002589  call    cs:__imp__recalloc
0x18000258f  test    rax, rax
0x180002592  jz      short loc_1800025C9
0x180002594  movsxd  rdx, dword ptr [rsi+10h]
0x180002598  mov     [rsi+8], rax
0x18000259c  mov     rax, [rsi]
0x18000259f  lea     rcx, [rax+rdx*8]
0x1800025a3  test    rcx, rcx
0x1800025a6  jz      short loc_1800025AB
0x1800025a8  mov     [rcx], rdi
0x1800025ab  mov     rax, [rsi+8]
0x1800025af  lea     rcx, [rax+rdx*8]
0x1800025b3  test    rcx, rcx
0x1800025b6  jz      short loc_1800025BB
0x1800025b8  mov     [rcx], rbx
0x1800025bb  inc     dword ptr [rsi+10h]
0x1800025be  mov     rdi, r13
0x1800025c1  mov     esi, r13d
0x1800025c4  mov     rbx, r13
0x1800025c7  jmp     short loc_1800025CE
0x1800025c9  mov     esi, 8007000Eh
0x1800025ce  not     esi
0x1800025d0  mov     rcx, rbx; Block
0x1800025d3  shr     esi, 1Fh
0x1800025d6  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800025db  mov     rcx, rdi; Block
0x1800025de  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800025e3  mov     eax, esi
0x1800025e5  jmp     short loc_1800025E9
0x1800025e7  xor     eax, eax
0x1800025e9  add     rsp, 28h
0x1800025ed  pop     r15
0x1800025ef  pop     r14
0x1800025f1  pop     r13
0x1800025f3  pop     r12
0x1800025f5  pop     rdi
0x1800025f6  pop     rsi
0x1800025f7  pop     rbp
0x1800025f8  pop     rbx
0x1800025f9  retn
0x1800025fa  mov     ecx, 8007000Eh; int
0x1800025ff  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002605  mov     ecx, 80004005h; int
0x18000260a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002610  mov     ecx, 80070057h; int
0x180002615  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
