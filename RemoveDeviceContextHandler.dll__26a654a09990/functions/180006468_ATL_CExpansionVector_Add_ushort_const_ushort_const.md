# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180006468`
- end: `0x18000663b`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `467`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180006750`
- `0x18000b2b0`

## callees

- `0x180001bec`
- `0x180001bf8`
- `0x180002210`
- `0x180006468`
- `0x180006df4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006511`
- `msvcrt!memcpy_s` at `0x18000654b`
- `msvcrt!memcpy_s` at `0x180006511`
- `msvcrt!memcpy_s` at `0x18000654b`

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
0x180006468  push    rbx
0x18000646a  push    rbp
0x18000646b  push    rsi
0x18000646c  push    rdi
0x18000646d  push    r12
0x18000646f  push    r13
0x180006471  push    r14
0x180006473  push    r15
0x180006475  sub     rsp, 28h
0x180006479  xor     r13d, r13d
0x18000647c  mov     r14, r8
0x18000647f  mov     rbp, rdx
0x180006482  mov     rsi, rcx
0x180006485  test    rdx, rdx
0x180006488  jz      loc_180006607
0x18000648e  test    r8, r8
0x180006491  jz      loc_180006607
0x180006497  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000649b  mov     rax, rbx
0x18000649e  inc     rax
0x1800064a1  cmp     [rdx+rax*2], r13w
0x1800064a6  jnz     short loc_18000649E
0x1800064a8  lea     r12, ds:2[rax*2]
0x1800064b0  mov     eax, 2
0x1800064b5  mul     r12
0x1800064b8  cmovb   rax, rbx
0x1800064bc  mov     rcx, rax; unsigned __int64
0x1800064bf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800064c4  mov     rdi, rax
0x1800064c7  mov     rcx, rbx
0x1800064ca  inc     rcx
0x1800064cd  cmp     [r14+rcx*2], r13w
0x1800064d2  jnz     short loc_1800064CA
0x1800064d4  inc     ecx
0x1800064d6  mov     eax, 2
0x1800064db  movsxd  r15, ecx
0x1800064de  add     r15, r15
0x1800064e1  mul     r15
0x1800064e4  cmovb   rax, rbx
0x1800064e8  mov     rcx, rax; unsigned __int64
0x1800064eb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800064f0  mov     rbx, rax
0x1800064f3  test    rdi, rdi
0x1800064f6  jz      loc_1800065E9
0x1800064fc  test    rax, rax
0x1800064ff  jz      loc_1800065E9
0x180006505  mov     r9, r12; SourceSize
0x180006508  mov     r8, rbp; Source
0x18000650b  mov     rdx, r12; DestinationSize
0x18000650e  mov     rcx, rdi; Destination
0x180006511  call    cs:__imp_memcpy_s
0x180006517  test    eax, eax
0x180006519  jz      short loc_18000653F
0x18000651b  cmp     eax, 0Ch
0x18000651e  jz      loc_18000661A
0x180006524  cmp     eax, 16h
0x180006527  jz      loc_180006630
0x18000652d  cmp     eax, 22h ; '"'
0x180006530  jz      loc_180006630
0x180006536  cmp     eax, 50h ; 'P'
0x180006539  jnz     loc_180006625
0x18000653f  mov     r9, r15; SourceSize
0x180006542  mov     r8, r14; Source
0x180006545  mov     rdx, r15; DestinationSize
0x180006548  mov     rcx, rbx; Destination
0x18000654b  call    cs:__imp_memcpy_s
0x180006551  test    eax, eax
0x180006553  jz      short loc_180006579
0x180006555  cmp     eax, 0Ch
0x180006558  jz      loc_18000661A
0x18000655e  cmp     eax, 16h
0x180006561  jz      loc_180006630
0x180006567  cmp     eax, 22h ; '"'
0x18000656a  jz      loc_180006630
0x180006570  cmp     eax, 50h ; 'P'
0x180006573  jnz     loc_180006625
0x180006579  mov     eax, [rsi+10h]
0x18000657c  mov     ebp, 8
0x180006581  mov     rcx, [rsi]; Block
0x180006584  inc     eax
0x180006586  movsxd  rdx, eax; Count
0x180006589  mov     r8d, ebp; Size
0x18000658c  call    cs:__imp__recalloc
0x180006592  test    rax, rax
0x180006595  jz      short loc_1800065E9
0x180006597  mov     rcx, [rsi+8]; Block
0x18000659b  mov     r8d, ebp; Size
0x18000659e  mov     [rsi], rax
0x1800065a1  mov     eax, [rsi+10h]
0x1800065a4  inc     eax
0x1800065a6  movsxd  rdx, eax; Count
0x1800065a9  call    cs:__imp__recalloc
0x1800065af  test    rax, rax
0x1800065b2  jz      short loc_1800065E9
0x1800065b4  movsxd  rdx, dword ptr [rsi+10h]
0x1800065b8  mov     [rsi+8], rax
0x1800065bc  mov     rax, [rsi]
0x1800065bf  lea     rcx, [rax+rdx*8]
0x1800065c3  test    rcx, rcx
0x1800065c6  jz      short loc_1800065CB
0x1800065c8  mov     [rcx], rdi
0x1800065cb  mov     rax, [rsi+8]
0x1800065cf  lea     rcx, [rax+rdx*8]
0x1800065d3  test    rcx, rcx
0x1800065d6  jz      short loc_1800065DB
0x1800065d8  mov     [rcx], rbx
0x1800065db  inc     dword ptr [rsi+10h]
0x1800065de  mov     rdi, r13
0x1800065e1  mov     esi, r13d
0x1800065e4  mov     rbx, r13
0x1800065e7  jmp     short loc_1800065EE
0x1800065e9  mov     esi, 8007000Eh
0x1800065ee  not     esi
0x1800065f0  mov     rcx, rbx; Block
0x1800065f3  shr     esi, 1Fh
0x1800065f6  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800065fb  mov     rcx, rdi; Block
0x1800065fe  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180006603  mov     eax, esi
0x180006605  jmp     short loc_180006609
0x180006607  xor     eax, eax
0x180006609  add     rsp, 28h
0x18000660d  pop     r15
0x18000660f  pop     r14
0x180006611  pop     r13
0x180006613  pop     r12
0x180006615  pop     rdi
0x180006616  pop     rsi
0x180006617  pop     rbp
0x180006618  pop     rbx
0x180006619  retn
0x18000661a  mov     ecx, 8007000Eh; int
0x18000661f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006625  mov     ecx, 80004005h; int
0x18000662a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006630  mov     ecx, 80070057h; int
0x180006635  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
