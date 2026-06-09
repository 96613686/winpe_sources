# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)

- ea: `0x180021f6c`
- end: `0x180022562`
- name: `?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z`
- size: `1526`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *this, struct IQueryRecentWinSATAssessment *, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002, char, OLECHAR *psz, union _LARGE_INTEGER, unsigned int, __int16)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022568`

## callees

- `0x180001870`
- `0x1800023d8`
- `0x1800023e4`
- `0x180002420`
- `0x1800027b1`
- `0x180003bb8`
- `0x180007da8`
- `0x180021f6c`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180021ffb`
- `OLEAUT32!__imp_SysAllocString` at `0x180021ffb`
- `OLEAUT32!__imp_SysFreeString` at `0x18002202f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800221cf`
- `OLEAUT32!__imp_SysFreeString` at `0x180022258`
- `OLEAUT32!__imp_SysFreeString` at `0x18002202f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800221cf`
- `OLEAUT32!__imp_SysFreeString` at `0x180022258`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this,
        struct IQueryRecentWinSATAssessment *a2,
        enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 a3,
        char a4,
        OLECHAR *psz,
        union _LARGE_INTEGER a6,
        unsigned int a7,
        __int16 a8)
{
  void *v12; // rdi
  struct IQueryRecentWinSATAssessmentVtbl *lpVtbl; // r13
  OLECHAR *v14; // rbx
  BSTR v15; // rdx
  BSTR v16; // rax
  int v17; // r12d
  __int64 v18; // rcx
  int v19; // ebx
  int v20; // ebx
  __int64 v21; // r8
  volatile signed __int32 *v22; // rbx
  unsigned int v23; // edi
  void *v24; // rax
  unsigned int (__fastcall *v25)(__int64, volatile signed __int32 *, _QWORD, __int64, unsigned int, int, unsigned int *, _QWORD); // rax
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *v26; // rax
  unsigned int v27; // edi
  __int64 v28; // r12
  unsigned int v29; // r12d
  void *v30; // rax
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *v31; // rcx
  unsigned int v32; // [rsp+50h] [rbp-E8h] BYREF
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v33; // [rsp+54h] [rbp-E4h]
  __int64 v34; // [rsp+58h] [rbp-E0h] BYREF
  _QWORD *v35; // [rsp+60h] [rbp-D8h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-D0h] BYREF
  void *Src; // [rsp+70h] [rbp-C8h] BYREF
  BSTR v38; // [rsp+78h] [rbp-C0h]
  _WORD v39[2]; // [rsp+90h] [rbp-A8h] BYREF
  char v40; // [rsp+94h] [rbp-A4h]
  char v41; // [rsp+95h] [rbp-A3h]
  __int16 v42; // [rsp+96h] [rbp-A2h]
  union _LARGE_INTEGER v43; // [rsp+A0h] [rbp-98h]
  __int128 v44; // [rsp+A8h] [rbp-90h]
  __int64 v45; // [rsp+D8h] [rbp-60h]
  unsigned int v46; // [rsp+E0h] [rbp-58h]
  unsigned int v47; // [rsp+E4h] [rbp-54h]

  v33 = a3;
  if ( !a2 )
    return 2147500035LL;
  v12 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  Src = v12;
  v34 = 0;
  v35 = 0;
  lpVtbl = a2->lpVtbl;
  if ( psz )
  {
    v16 = SysAllocString(psz);
    v14 = v16;
    v38 = v16;
    if ( !v16 )
      ATL::AtlThrowImpl(-2147024882);
    v15 = v16;
  }
  else
  {
    v14 = 0;
    v38 = 0;
    v15 = 0;
  }
  v17 = ((__int64 (__fastcall *)(struct IQueryRecentWinSATAssessment *, BSTR, _QWORD, __int64 *))lpVtbl->get_XML)(
          a2,
          v15,
          0,
          &v34);
  SysFreeString(v14);
  if ( v17 < 0 )
  {
    if ( v35 )
      (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return (unsigned int)v17;
  }
  v18 = v34;
  if ( !v34 )
  {
    if ( v35 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
      v18 = v34;
    }
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return 1;
  }
  v19 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v34 + 72LL))(v34, &v35);
  if ( v19 < 0 )
  {
    if ( v35 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v35 + 16LL))(v35, *v35);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return (unsigned int)v19;
  }
  if ( !v35 )
  {
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return 1;
  }
  bstrString = 0;
  v20 = (*(__int64 (__fastcall **)(_QWORD *, BSTR *))(*v35 + 272LL))(v35, &bstrString);
  if ( v20 < 0 )
  {
    SysFreeString(bstrString);
    if ( v35 )
      (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return (unsigned int)v20;
  }
  if ( bstrString )
  {
    v21 = -1;
    do
      ++v21;
    while ( bstrString[v21] );
  }
  else
  {
    v21 = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&Src, bstrString, v21);
  SysFreeString(bstrString);
  if ( v35 )
    (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  v22 = (volatile signed __int32 *)Src;
  v23 = 2 * *((_DWORD *)Src - 4) + 2;
  v32 = 0;
  if ( v23 < 8 || *((_BYTE *)this + 33) )
    goto LABEL_71;
  if ( *((_DWORD *)this + 20) < v23 - 8 )
  {
    free(*((void **)this + 9));
    *((_QWORD *)this + 9) = 0;
    *((_DWORD *)this + 20) = 0;
    v24 = o_malloc_0(v23);
    *((_QWORD *)this + 9) = v24;
    if ( !v24 )
    {
LABEL_73:
      if ( _InterlockedExchangeAdd(v22 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
      return 2147942414LL;
    }
    *((_DWORD *)this + 20) = v23;
  }
  v25 = (unsigned int (__fastcall *)(__int64, volatile signed __int32 *, _QWORD, __int64, unsigned int, int, unsigned int *, _QWORD))*((_QWORD *)this + 5);
  if ( !v25
    || v25(258, v22, v23, *((_QWORD *)this + 9) + 8LL, v23 - 8, 4096, &v32, *((_QWORD *)this + 7))
    || v32 > v23 - 8 )
  {
LABEL_71:
    v29 = v23 + 4;
    if ( *((_DWORD *)this + 24) < v23 + 4 )
    {
      free(*((void **)this + 11));
      *((_QWORD *)this + 11) = 0;
      *((_DWORD *)this + 24) = 0;
      v30 = o_malloc_0(v29);
      *((_QWORD *)this + 11) = v30;
      if ( !v30 )
        goto LABEL_73;
      *((_DWORD *)this + 24) = v29;
    }
    v31 = (enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *)*((_QWORD *)this + 11);
    *v31 = v33;
    memcpy_0(v31 + 1, (const void *)v22, v23);
    v28 = *((_QWORD *)this + 11);
    v27 = *((_DWORD *)this + 24);
LABEL_78:
    if ( v27 < 0xFFFF )
    {
      memset_0(v39, 0, 0x58u);
      v39[0] = a8;
      v43 = a6;
      v44 = *(_OWORD *)WinSATAssessmentGuid;
      v40 = a4;
      v42 = 0;
      v41 = 0;
      v45 = v28;
      v46 = v27;
      v47 = a7;
      (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
        *((_QWORD *)this + 2),
        v39,
        0,
        0);
      if ( _InterlockedExchangeAdd(v22 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
      return 0;
    }
    else
    {
      if ( _InterlockedExchangeAdd(v22 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
      return 1;
    }
  }
  v32 += 8;
  switch ( a4 )
  {
    case ' ':
      a4 = 33;
      goto LABEL_70;
    case '"':
      a4 = 35;
      goto LABEL_70;
    case '$':
      a4 = 37;
LABEL_70:
      v26 = (enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *)*((_QWORD *)this + 9);
      *v26 = v33;
      *((_DWORD *)v26 + 1) = v23;
      v27 = v32;
      v28 = *((_QWORD *)this + 9);
      goto LABEL_78;
  }
  if ( _InterlockedExchangeAdd(v22 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
  return 2147500033LL;
}

```

## disassembly

```asm
0x180021f6c  push    rbx
0x180021f6e  push    rsi
0x180021f6f  push    rdi
0x180021f70  push    r12
0x180021f72  push    r13
0x180021f74  push    r14
0x180021f76  push    r15
0x180021f78  sub     rsp, 100h
0x180021f7f  mov     rax, cs:__security_cookie
0x180021f86  xor     rax, rsp
0x180021f89  mov     [rsp+138h+var_48], rax
0x180021f91  mov     r15b, r9b
0x180021f94  mov     [rsp+138h+var_E4], r8d
0x180021f99  mov     r12, rdx
0x180021f9c  mov     r14, rcx
0x180021f9f  mov     rbx, [rsp+138h+psz]
0x180021fa7  xor     esi, esi
0x180021fa9  test    rdx, rdx
0x180021fac  jnz     short loc_180021FB8
0x180021fae  mov     eax, 80004003h
0x180021fb3  jmp     loc_180022533
0x180021fb8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180021fbf  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180021fc6  mov     rax, [rax+18h]
0x180021fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fcf  lea     rdi, [rax+18h]
0x180021fd3  mov     [rsp+138h+Src], rdi
0x180021fd8  mov     [rsp+138h+var_E0], rsi
0x180021fdd  mov     [rsp+138h+var_D8], rsi
0x180021fe2  mov     r13, [r12]
0x180021fe6  test    rbx, rbx
0x180021fe9  jnz     short loc_180021FF8
0x180021feb  mov     rbx, rsi
0x180021fee  mov     [rsp+138h+var_C0], rbx
0x180021ff3  mov     rdx, rsi
0x180021ff6  jmp     short loc_180022015
0x180021ff8  mov     rcx, rbx; psz
0x180021ffb  call    cs:__imp_SysAllocString
0x180022001  mov     rbx, rax
0x180022004  mov     [rsp+138h+var_C0], rax
0x180022009  test    rax, rax
0x18002200c  jz      loc_180022556
0x180022012  mov     rdx, rax
0x180022015  lea     r9, [rsp+138h+var_E0]
0x18002201a  xor     r8d, r8d
0x18002201d  mov     rcx, r12
0x180022020  mov     rax, [r13+38h]
0x180022024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022029  mov     r12d, eax
0x18002202c  mov     rcx, rbx; bstrString
0x18002202f  call    cs:__imp_SysFreeString
0x180022035  test    r12d, r12d
0x180022038  jns     short loc_180022090
0x18002203a  mov     rcx, [rsp+138h+var_D8]
0x18002203f  test    rcx, rcx
0x180022042  jz      short loc_180022051
0x180022044  mov     rax, [rcx]
0x180022047  mov     rax, [rax+10h]
0x18002204b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022050  nop
0x180022051  mov     rcx, [rsp+138h+var_E0]
0x180022056  test    rcx, rcx
0x180022059  jz      short loc_180022068
0x18002205b  mov     rax, [rcx]
0x18002205e  mov     rax, [rax+10h]
0x180022062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022067  nop
0x180022068  lea     rdx, [rdi-18h]
0x18002206c  or      eax, 0FFFFFFFFh
0x18002206f  lock xadd [rdx+10h], eax
0x180022074  sub     eax, 1
0x180022077  jg      short loc_180022088
0x180022079  mov     rcx, [rdx]
0x18002207c  mov     rax, [rcx]
0x18002207f  mov     rax, [rax+8]
0x180022083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022088  mov     eax, r12d
0x18002208b  jmp     loc_180022533
0x180022090  mov     rcx, [rsp+138h+var_E0]
0x180022095  test    rcx, rcx
0x180022098  jnz     short loc_1800220F4
0x18002209a  mov     rdx, [rsp+138h+var_D8]
0x18002209f  test    rdx, rdx
0x1800220a2  jz      short loc_1800220B8
0x1800220a4  mov     rax, [rdx]
0x1800220a7  mov     rcx, rdx
0x1800220aa  mov     rax, [rax+10h]
0x1800220ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220b3  mov     rcx, [rsp+138h+var_E0]
0x1800220b8  test    rcx, rcx
0x1800220bb  jz      short loc_1800220CA
0x1800220bd  mov     rax, [rcx]
0x1800220c0  mov     rax, [rax+10h]
0x1800220c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220c9  nop
0x1800220ca  lea     rdx, [rdi-18h]
0x1800220ce  or      eax, 0FFFFFFFFh
0x1800220d1  lock xadd [rdx+10h], eax
0x1800220d6  sub     eax, 1
0x1800220d9  jg      short loc_1800220EA
0x1800220db  mov     rcx, [rdx]
0x1800220de  mov     rax, [rcx]
0x1800220e1  mov     rax, [rax+8]
0x1800220e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220ea  mov     eax, 1
0x1800220ef  jmp     loc_180022533
0x1800220f4  mov     rax, [rcx]
0x1800220f7  lea     rdx, [rsp+138h+var_D8]
0x1800220fc  mov     rax, [rax+48h]
0x180022100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022105  mov     ebx, eax
0x180022107  test    eax, eax
0x180022109  jns     short loc_180022160
0x18002210b  mov     rcx, [rsp+138h+var_D8]
0x180022110  test    rcx, rcx
0x180022113  jz      short loc_180022122
0x180022115  mov     rdx, [rcx]
0x180022118  mov     rax, [rdx+10h]
0x18002211c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022121  nop
0x180022122  mov     rcx, [rsp+138h+var_E0]
0x180022127  test    rcx, rcx
0x18002212a  jz      short loc_180022139
0x18002212c  mov     rax, [rcx]
0x18002212f  mov     rax, [rax+10h]
0x180022133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022138  nop
0x180022139  lea     rdx, [rdi-18h]
0x18002213d  or      eax, 0FFFFFFFFh
0x180022140  lock xadd [rdx+10h], eax
0x180022145  sub     eax, 1
0x180022148  jg      short loc_180022159
0x18002214a  mov     rcx, [rdx]
0x18002214d  mov     rax, [rcx]
0x180022150  mov     rax, [rax+8]
0x180022154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022159  mov     eax, ebx
0x18002215b  jmp     loc_180022533
0x180022160  mov     rcx, [rsp+138h+var_D8]
0x180022165  test    rcx, rcx
0x180022168  jnz     short loc_1800221AB
0x18002216a  mov     rcx, [rsp+138h+var_E0]
0x18002216f  test    rcx, rcx
0x180022172  jz      short loc_180022181
0x180022174  mov     rax, [rcx]
0x180022177  mov     rax, [rax+10h]
0x18002217b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022180  nop
0x180022181  lea     rdx, [rdi-18h]
0x180022185  or      eax, 0FFFFFFFFh
0x180022188  lock xadd [rdx+10h], eax
0x18002218d  sub     eax, 1
0x180022190  jg      short loc_1800221A1
0x180022192  mov     rcx, [rdx]
0x180022195  mov     rax, [rcx]
0x180022198  mov     rax, [rax+8]
0x18002219c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221a1  mov     eax, 1
0x1800221a6  jmp     loc_180022533
0x1800221ab  mov     [rsp+138h+bstrString], rsi
0x1800221b0  mov     rax, [rcx]
0x1800221b3  lea     rdx, [rsp+138h+bstrString]
0x1800221b8  mov     rax, [rax+110h]
0x1800221bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221c4  mov     ebx, eax
0x1800221c6  test    eax, eax
0x1800221c8  jns     short loc_18002222B
0x1800221ca  mov     rcx, [rsp+138h+bstrString]; bstrString
0x1800221cf  call    cs:__imp_SysFreeString
0x1800221d5  nop
0x1800221d6  mov     rcx, [rsp+138h+var_D8]
0x1800221db  test    rcx, rcx
0x1800221de  jz      short loc_1800221ED
0x1800221e0  mov     rax, [rcx]
0x1800221e3  mov     rax, [rax+10h]
0x1800221e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221ec  nop
0x1800221ed  mov     rcx, [rsp+138h+var_E0]
0x1800221f2  test    rcx, rcx
0x1800221f5  jz      short loc_180022204
0x1800221f7  mov     rax, [rcx]
0x1800221fa  mov     rax, [rax+10h]
0x1800221fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022203  nop
0x180022204  lea     rdx, [rdi-18h]
0x180022208  or      eax, 0FFFFFFFFh
0x18002220b  lock xadd [rdx+10h], eax
0x180022210  sub     eax, 1
0x180022213  jg      short loc_180022224
0x180022215  mov     rcx, [rdx]
0x180022218  mov     rax, [rcx]
0x18002221b  mov     rax, [rax+8]
0x18002221f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022224  mov     eax, ebx
0x180022226  jmp     loc_180022533
0x18002222b  mov     rdx, [rsp+138h+bstrString]
0x180022230  test    rdx, rdx
0x180022233  jnz     short loc_18002223A
0x180022235  mov     r8d, esi
0x180022238  jmp     short loc_180022248
0x18002223a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002223e  inc     r8
0x180022241  cmp     [rdx+r8*2], si
0x180022246  jnz     short loc_18002223E
0x180022248  lea     rcx, [rsp+138h+Src]
0x18002224d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180022252  nop
0x180022253  mov     rcx, [rsp+138h+bstrString]; bstrString
0x180022258  call    cs:__imp_SysFreeString
0x18002225e  nop
0x18002225f  mov     rcx, [rsp+138h+var_D8]
0x180022264  test    rcx, rcx
0x180022267  jz      short loc_180022276
0x180022269  mov     rax, [rcx]
0x18002226c  mov     rax, [rax+10h]
0x180022270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022275  nop
0x180022276  mov     rcx, [rsp+138h+var_E0]
0x18002227b  test    rcx, rcx
0x18002227e  jz      short loc_18002228D
0x180022280  mov     rax, [rcx]
0x180022283  mov     rax, [rax+10h]
0x180022287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002228c  nop
0x18002228d  mov     rbx, [rsp+138h+Src]
0x180022292  mov     eax, [rbx-10h]
0x180022295  lea     edi, ds:2[rax*2]
0x18002229c  mov     [rsp+138h+var_E8], esi
0x1800222a0  cmp     edi, 8
0x1800222a3  jb      loc_18002239F
0x1800222a9  cmp     [r14+21h], sil
0x1800222ad  jnz     loc_18002239F
0x1800222b3  lea     r12d, [rdi-8]
0x1800222b7  cmp     [r14+50h], r12d
0x1800222bb  jnb     short loc_1800222E6
0x1800222bd  mov     rcx, [r14+48h]; Block
0x1800222c1  call    free
0x1800222c6  mov     [r14+48h], rsi
0x1800222ca  mov     [r14+50h], esi
0x1800222ce  mov     ecx, edi; Size
0x1800222d0  call    _o_malloc_0
0x1800222d5  mov     [r14+48h], rax
0x1800222d9  test    rax, rax
0x1800222dc  jz      loc_1800223CB
0x1800222e2  mov     [r14+50h], edi
0x1800222e6  mov     rax, [r14+28h]
0x1800222ea  test    rax, rax
0x1800222ed  jz      loc_18002239F
0x1800222f3  mov     r9, [r14+48h]
0x1800222f7  add     r9, 8
0x1800222fb  mov     ecx, 102h
0x180022300  mov     rdx, [r14+38h]
0x180022304  mov     [rsp+138h+var_100], rdx
0x180022309  lea     rdx, [rsp+138h+var_E8]
0x18002230e  mov     [rsp+138h+var_108], rdx
0x180022313  mov     [rsp+138h+var_110], 1000h
0x18002231b  mov     [rsp+138h+var_118], r12d
0x180022320  mov     r8d, edi
0x180022323  mov     rdx, rbx
0x180022326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002232b  test    eax, eax
0x18002232d  jnz     short loc_18002239F
0x18002232f  mov     eax, [rsp+138h+var_E8]
0x180022333  cmp     eax, r12d
0x180022336  ja      short loc_18002239F
0x180022338  add     eax, 8
0x18002233b  mov     [rsp+138h+var_E8], eax
0x18002233f  cmp     r15b, 20h ; ' '
0x180022343  jz      short loc_180022385
0x180022345  cmp     r15b, 22h ; '"'
0x180022349  jz      short loc_180022380
0x18002234b  cmp     r15b, 24h ; '$'
0x18002234f  jnz     short loc_180022356
0x180022351  mov     r15b, 25h ; '%'
0x180022354  jmp     short loc_180022388
0x180022356  lea     rdx, [rbx-18h]
0x18002235a  or      eax, 0FFFFFFFFh
0x18002235d  lock xadd [rdx+10h], eax
0x180022362  sub     eax, 1
0x180022365  jg      short loc_180022376
0x180022367  mov     rcx, [rdx]
0x18002236a  mov     rax, [rcx]
0x18002236d  mov     rax, [rax+8]
0x180022371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022376  mov     eax, 80004001h
0x18002237b  jmp     loc_180022533
0x180022380  mov     r15b, 23h ; '#'
0x180022383  jmp     short loc_180022388
0x180022385  mov     r15b, 21h ; '!'
0x180022388  mov     rax, [r14+48h]
0x18002238c  mov     edx, [rsp+138h+var_E4]
0x180022390  mov     [rax], edx
0x180022392  mov     [rax+4], edi
0x180022395  mov     edi, [rsp+138h+var_E8]
0x180022399  mov     r12, [r14+48h]
0x18002239d  jmp     short loc_18002241A
0x18002239f  lea     r12d, [rdi+4]
0x1800223a3  cmp     [r14+60h], r12d
0x1800223a7  jnb     short loc_1800223F9
0x1800223a9  mov     rcx, [r14+58h]; Block
  ... truncated ...
```
