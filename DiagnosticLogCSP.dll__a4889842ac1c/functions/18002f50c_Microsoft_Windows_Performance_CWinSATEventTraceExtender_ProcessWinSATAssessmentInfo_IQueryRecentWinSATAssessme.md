# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002f50c`
- end: `0x18002fb06`
- name: `?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z`
- size: `1530`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *__hidden this, struct IQueryRecentWinSATAssessment *, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002, unsigned __int8, OLECHAR *psz, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fb0c`

## callees

- `0x180001b60`
- `0x18000262c`
- `0x180002cf5`
- `0x180010db8`
- `0x180019260`
- `0x18002f50c`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002f861`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002f94f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002f861`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002f94f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002f871`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002f960`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002f871`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002f960`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f59b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002f59b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f5cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f76f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f7f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f5cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f76f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002f7f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
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
  unsigned int v24; // r12d
  void *v25; // rax
  unsigned int (__fastcall *v26)(__int64, volatile signed __int32 *, _QWORD, __int64, unsigned int, int, unsigned int *, _QWORD); // rax
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *v27; // rax
  unsigned int v28; // edi
  __int64 v29; // r12
  unsigned int v30; // r12d
  void *v31; // rax
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *v32; // rcx
  unsigned int v33; // [rsp+50h] [rbp-E8h] BYREF
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v34; // [rsp+54h] [rbp-E4h]
  __int64 v35; // [rsp+58h] [rbp-E0h] BYREF
  _QWORD *v36; // [rsp+60h] [rbp-D8h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-D0h] BYREF
  void *Src; // [rsp+70h] [rbp-C8h] BYREF
  BSTR v39; // [rsp+78h] [rbp-C0h]
  _WORD v40[2]; // [rsp+90h] [rbp-A8h] BYREF
  char v41; // [rsp+94h] [rbp-A4h]
  char v42; // [rsp+95h] [rbp-A3h]
  __int16 v43; // [rsp+96h] [rbp-A2h]
  union _LARGE_INTEGER v44; // [rsp+A0h] [rbp-98h]
  __int128 v45; // [rsp+A8h] [rbp-90h]
  __int64 v46; // [rsp+D8h] [rbp-60h]
  unsigned int v47; // [rsp+E0h] [rbp-58h]
  unsigned int v48; // [rsp+E4h] [rbp-54h]

  v34 = a3;
  if ( !a2 )
    return 2147500035LL;
  v12 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  Src = v12;
  v35 = 0;
  v36 = 0;
  lpVtbl = a2->lpVtbl;
  if ( psz )
  {
    v16 = SysAllocString(psz);
    v14 = v16;
    v39 = v16;
    if ( !v16 )
      ATL::AtlThrowImpl(-2147024882);
    v15 = v16;
  }
  else
  {
    v14 = 0;
    v39 = 0;
    v15 = 0;
  }
  v17 = ((__int64 (__fastcall *)(struct IQueryRecentWinSATAssessment *, BSTR, _QWORD, __int64 *))lpVtbl->get_XML)(
          a2,
          v15,
          0,
          &v35);
  SysFreeString(v14);
  if ( v17 < 0 )
  {
    if ( v36 )
      (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return (unsigned int)v17;
  }
  v18 = v35;
  if ( !v35 )
  {
    if ( v36 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
      v18 = v35;
    }
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return 1;
  }
  v19 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v35 + 72LL))(v35, &v36);
  if ( v19 < 0 )
  {
    if ( v36 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v36 + 16LL))(v36, *v36);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return (unsigned int)v19;
  }
  if ( !v36 )
  {
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
    return 1;
  }
  bstrString = 0;
  v20 = (*(__int64 (__fastcall **)(_QWORD *, BSTR *))(*v36 + 272LL))(v36, &bstrString);
  if ( v20 < 0 )
  {
    SysFreeString(bstrString);
    if ( v36 )
      (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
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
  if ( v36 )
    (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  v22 = (volatile signed __int32 *)Src;
  v23 = 2 * *((_DWORD *)Src - 4) + 2;
  v33 = 0;
  if ( v23 < 8 || *((_BYTE *)this + 33) )
    goto LABEL_71;
  v24 = v23 - 8;
  if ( *((_DWORD *)this + 20) < v23 - 8 )
  {
    free(*((void **)this + 9));
    *((_QWORD *)this + 9) = 0;
    *((_DWORD *)this + 20) = 0;
    v25 = malloc(v23);
    *((_QWORD *)this + 9) = v25;
    if ( !v25 )
    {
LABEL_73:
      if ( _InterlockedExchangeAdd(v22 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
      return 2147942414LL;
    }
    *((_DWORD *)this + 20) = v23;
  }
  v26 = (unsigned int (__fastcall *)(__int64, volatile signed __int32 *, _QWORD, __int64, unsigned int, int, unsigned int *, _QWORD))*((_QWORD *)this + 5);
  if ( !v26 || v26(258, v22, v23, *((_QWORD *)this + 9) + 8LL, v24, 4096, &v33, *((_QWORD *)this + 7)) || v33 > v24 )
  {
LABEL_71:
    v30 = v23 + 4;
    if ( *((_DWORD *)this + 24) < v23 + 4 )
    {
      free(*((void **)this + 11));
      *((_QWORD *)this + 11) = 0;
      *((_DWORD *)this + 24) = 0;
      v31 = malloc(v30);
      *((_QWORD *)this + 11) = v31;
      if ( !v31 )
        goto LABEL_73;
      *((_DWORD *)this + 24) = v30;
    }
    v32 = (enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *)*((_QWORD *)this + 11);
    *v32 = v34;
    memcpy_0(v32 + 1, (const void *)v22, v23);
    v29 = *((_QWORD *)this + 11);
    v28 = *((_DWORD *)this + 24);
LABEL_78:
    if ( v28 < 0xFFFF )
    {
      memset_0(v40, 0, 0x58u);
      v40[0] = a8;
      v44 = a6;
      v45 = *(_OWORD *)WinSATAssessmentGuid;
      v41 = a4;
      v43 = 0;
      v42 = 0;
      v46 = v29;
      v47 = v28;
      v48 = a7;
      (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
        *((_QWORD *)this + 2),
        v40,
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
  v33 += 8;
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
      v27 = (enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *)*((_QWORD *)this + 9);
      *v27 = v34;
      *((_DWORD *)v27 + 1) = v23;
      v28 = v33;
      v29 = *((_QWORD *)this + 9);
      goto LABEL_78;
  }
  if ( _InterlockedExchangeAdd(v22 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v22 - 3) + 8LL))(*((_QWORD *)v22 - 3));
  return 2147500033LL;
}

```

## disassembly

```asm
0x18002f50c  push    rbx
0x18002f50e  push    rsi
0x18002f50f  push    rdi
0x18002f510  push    r12
0x18002f512  push    r13
0x18002f514  push    r14
0x18002f516  push    r15
0x18002f518  sub     rsp, 100h
0x18002f51f  mov     rax, cs:__security_cookie
0x18002f526  xor     rax, rsp
0x18002f529  mov     [rsp+138h+var_48], rax
0x18002f531  mov     r15b, r9b
0x18002f534  mov     [rsp+138h+var_E4], r8d
0x18002f539  mov     r12, rdx
0x18002f53c  mov     r14, rcx
0x18002f53f  mov     rbx, [rsp+138h+psz]
0x18002f547  xor     esi, esi
0x18002f549  test    rdx, rdx
0x18002f54c  jnz     short loc_18002F558
0x18002f54e  mov     eax, 80004003h
0x18002f553  jmp     loc_18002FAD7
0x18002f558  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002f55f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002f566  mov     rax, [rax+18h]
0x18002f56a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f56f  lea     rdi, [rax+18h]
0x18002f573  mov     [rsp+138h+Src], rdi
0x18002f578  mov     [rsp+138h+var_E0], rsi
0x18002f57d  mov     [rsp+138h+var_D8], rsi
0x18002f582  mov     r13, [r12]
0x18002f586  test    rbx, rbx
0x18002f589  jnz     short loc_18002F598
0x18002f58b  mov     rbx, rsi
0x18002f58e  mov     [rsp+138h+var_C0], rbx
0x18002f593  mov     rdx, rsi
0x18002f596  jmp     short loc_18002F5B5
0x18002f598  mov     rcx, rbx; psz
0x18002f59b  call    cs:__imp_SysAllocString
0x18002f5a1  mov     rbx, rax
0x18002f5a4  mov     [rsp+138h+var_C0], rax
0x18002f5a9  test    rax, rax
0x18002f5ac  jz      loc_18002FAFA
0x18002f5b2  mov     rdx, rax
0x18002f5b5  lea     r9, [rsp+138h+var_E0]
0x18002f5ba  xor     r8d, r8d
0x18002f5bd  mov     rcx, r12
0x18002f5c0  mov     rax, [r13+38h]
0x18002f5c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5c9  mov     r12d, eax
0x18002f5cc  mov     rcx, rbx; bstrString
0x18002f5cf  call    cs:__imp_SysFreeString
0x18002f5d5  test    r12d, r12d
0x18002f5d8  jns     short loc_18002F630
0x18002f5da  mov     rcx, [rsp+138h+var_D8]
0x18002f5df  test    rcx, rcx
0x18002f5e2  jz      short loc_18002F5F1
0x18002f5e4  mov     rax, [rcx]
0x18002f5e7  mov     rax, [rax+10h]
0x18002f5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5f0  nop
0x18002f5f1  mov     rcx, [rsp+138h+var_E0]
0x18002f5f6  test    rcx, rcx
0x18002f5f9  jz      short loc_18002F608
0x18002f5fb  mov     rax, [rcx]
0x18002f5fe  mov     rax, [rax+10h]
0x18002f602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f607  nop
0x18002f608  lea     rdx, [rdi-18h]
0x18002f60c  or      eax, 0FFFFFFFFh
0x18002f60f  lock xadd [rdx+10h], eax
0x18002f614  sub     eax, 1
0x18002f617  jg      short loc_18002F628
0x18002f619  mov     rcx, [rdx]
0x18002f61c  mov     rax, [rcx]
0x18002f61f  mov     rax, [rax+8]
0x18002f623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f628  mov     eax, r12d
0x18002f62b  jmp     loc_18002FAD7
0x18002f630  mov     rcx, [rsp+138h+var_E0]
0x18002f635  test    rcx, rcx
0x18002f638  jnz     short loc_18002F694
0x18002f63a  mov     rdx, [rsp+138h+var_D8]
0x18002f63f  test    rdx, rdx
0x18002f642  jz      short loc_18002F658
0x18002f644  mov     rax, [rdx]
0x18002f647  mov     rcx, rdx
0x18002f64a  mov     rax, [rax+10h]
0x18002f64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f653  mov     rcx, [rsp+138h+var_E0]
0x18002f658  test    rcx, rcx
0x18002f65b  jz      short loc_18002F66A
0x18002f65d  mov     rax, [rcx]
0x18002f660  mov     rax, [rax+10h]
0x18002f664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f669  nop
0x18002f66a  lea     rdx, [rdi-18h]
0x18002f66e  or      eax, 0FFFFFFFFh
0x18002f671  lock xadd [rdx+10h], eax
0x18002f676  sub     eax, 1
0x18002f679  jg      short loc_18002F68A
0x18002f67b  mov     rcx, [rdx]
0x18002f67e  mov     rax, [rcx]
0x18002f681  mov     rax, [rax+8]
0x18002f685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f68a  mov     eax, 1
0x18002f68f  jmp     loc_18002FAD7
0x18002f694  mov     rax, [rcx]
0x18002f697  lea     rdx, [rsp+138h+var_D8]
0x18002f69c  mov     rax, [rax+48h]
0x18002f6a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6a5  mov     ebx, eax
0x18002f6a7  test    eax, eax
0x18002f6a9  jns     short loc_18002F700
0x18002f6ab  mov     rcx, [rsp+138h+var_D8]
0x18002f6b0  test    rcx, rcx
0x18002f6b3  jz      short loc_18002F6C2
0x18002f6b5  mov     rdx, [rcx]
0x18002f6b8  mov     rax, [rdx+10h]
0x18002f6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6c1  nop
0x18002f6c2  mov     rcx, [rsp+138h+var_E0]
0x18002f6c7  test    rcx, rcx
0x18002f6ca  jz      short loc_18002F6D9
0x18002f6cc  mov     rax, [rcx]
0x18002f6cf  mov     rax, [rax+10h]
0x18002f6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6d8  nop
0x18002f6d9  lea     rdx, [rdi-18h]
0x18002f6dd  or      eax, 0FFFFFFFFh
0x18002f6e0  lock xadd [rdx+10h], eax
0x18002f6e5  sub     eax, 1
0x18002f6e8  jg      short loc_18002F6F9
0x18002f6ea  mov     rcx, [rdx]
0x18002f6ed  mov     rax, [rcx]
0x18002f6f0  mov     rax, [rax+8]
0x18002f6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6f9  mov     eax, ebx
0x18002f6fb  jmp     loc_18002FAD7
0x18002f700  mov     rcx, [rsp+138h+var_D8]
0x18002f705  test    rcx, rcx
0x18002f708  jnz     short loc_18002F74B
0x18002f70a  mov     rcx, [rsp+138h+var_E0]
0x18002f70f  test    rcx, rcx
0x18002f712  jz      short loc_18002F721
0x18002f714  mov     rax, [rcx]
0x18002f717  mov     rax, [rax+10h]
0x18002f71b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f720  nop
0x18002f721  lea     rdx, [rdi-18h]
0x18002f725  or      eax, 0FFFFFFFFh
0x18002f728  lock xadd [rdx+10h], eax
0x18002f72d  sub     eax, 1
0x18002f730  jg      short loc_18002F741
0x18002f732  mov     rcx, [rdx]
0x18002f735  mov     rax, [rcx]
0x18002f738  mov     rax, [rax+8]
0x18002f73c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f741  mov     eax, 1
0x18002f746  jmp     loc_18002FAD7
0x18002f74b  mov     [rsp+138h+bstrString], rsi
0x18002f750  mov     rax, [rcx]
0x18002f753  lea     rdx, [rsp+138h+bstrString]
0x18002f758  mov     rax, [rax+110h]
0x18002f75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f764  mov     ebx, eax
0x18002f766  test    eax, eax
0x18002f768  jns     short loc_18002F7CB
0x18002f76a  mov     rcx, [rsp+138h+bstrString]; bstrString
0x18002f76f  call    cs:__imp_SysFreeString
0x18002f775  nop
0x18002f776  mov     rcx, [rsp+138h+var_D8]
0x18002f77b  test    rcx, rcx
0x18002f77e  jz      short loc_18002F78D
0x18002f780  mov     rax, [rcx]
0x18002f783  mov     rax, [rax+10h]
0x18002f787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f78c  nop
0x18002f78d  mov     rcx, [rsp+138h+var_E0]
0x18002f792  test    rcx, rcx
0x18002f795  jz      short loc_18002F7A4
0x18002f797  mov     rax, [rcx]
0x18002f79a  mov     rax, [rax+10h]
0x18002f79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7a3  nop
0x18002f7a4  lea     rdx, [rdi-18h]
0x18002f7a8  or      eax, 0FFFFFFFFh
0x18002f7ab  lock xadd [rdx+10h], eax
0x18002f7b0  sub     eax, 1
0x18002f7b3  jg      short loc_18002F7C4
0x18002f7b5  mov     rcx, [rdx]
0x18002f7b8  mov     rax, [rcx]
0x18002f7bb  mov     rax, [rax+8]
0x18002f7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7c4  mov     eax, ebx
0x18002f7c6  jmp     loc_18002FAD7
0x18002f7cb  mov     rdx, [rsp+138h+bstrString]
0x18002f7d0  test    rdx, rdx
0x18002f7d3  jnz     short loc_18002F7DA
0x18002f7d5  mov     r8d, esi
0x18002f7d8  jmp     short loc_18002F7E8
0x18002f7da  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002f7de  inc     r8
0x18002f7e1  cmp     [rdx+r8*2], si
0x18002f7e6  jnz     short loc_18002F7DE
0x18002f7e8  lea     rcx, [rsp+138h+Src]
0x18002f7ed  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002f7f2  nop
0x18002f7f3  mov     rcx, [rsp+138h+bstrString]; bstrString
0x18002f7f8  call    cs:__imp_SysFreeString
0x18002f7fe  nop
0x18002f7ff  mov     rcx, [rsp+138h+var_D8]
0x18002f804  test    rcx, rcx
0x18002f807  jz      short loc_18002F816
0x18002f809  mov     rax, [rcx]
0x18002f80c  mov     rax, [rax+10h]
0x18002f810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f815  nop
0x18002f816  mov     rcx, [rsp+138h+var_E0]
0x18002f81b  test    rcx, rcx
0x18002f81e  jz      short loc_18002F82D
0x18002f820  mov     rax, [rcx]
0x18002f823  mov     rax, [rax+10h]
0x18002f827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f82c  nop
0x18002f82d  mov     rbx, [rsp+138h+Src]
0x18002f832  mov     eax, [rbx-10h]
0x18002f835  lea     edi, ds:2[rax*2]
0x18002f83c  mov     [rsp+138h+var_E8], esi
0x18002f840  cmp     edi, 8
0x18002f843  jb      loc_18002F941
0x18002f849  cmp     [r14+21h], sil
0x18002f84d  jnz     loc_18002F941
0x18002f853  lea     r12d, [rdi-8]
0x18002f857  cmp     [r14+50h], r12d
0x18002f85b  jnb     short loc_18002F888
0x18002f85d  mov     rcx, [r14+48h]; Block
0x18002f861  call    cs:__imp_free
0x18002f867  mov     [r14+48h], rsi
0x18002f86b  mov     [r14+50h], esi
0x18002f86f  mov     ecx, edi; Size
0x18002f871  call    cs:__imp_malloc
0x18002f877  mov     [r14+48h], rax
0x18002f87b  test    rax, rax
0x18002f87e  jz      loc_18002F96F
0x18002f884  mov     [r14+50h], edi
0x18002f888  mov     rax, [r14+28h]
0x18002f88c  test    rax, rax
0x18002f88f  jz      loc_18002F941
0x18002f895  mov     r9, [r14+48h]
0x18002f899  add     r9, 8
0x18002f89d  mov     ecx, 102h
0x18002f8a2  mov     rdx, [r14+38h]
0x18002f8a6  mov     [rsp+138h+var_100], rdx
0x18002f8ab  lea     rdx, [rsp+138h+var_E8]
0x18002f8b0  mov     [rsp+138h+var_108], rdx
0x18002f8b5  mov     [rsp+138h+var_110], 1000h
0x18002f8bd  mov     [rsp+138h+var_118], r12d
0x18002f8c2  mov     r8d, edi
0x18002f8c5  mov     rdx, rbx
0x18002f8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8cd  test    eax, eax
0x18002f8cf  jnz     short loc_18002F941
0x18002f8d1  mov     eax, [rsp+138h+var_E8]
0x18002f8d5  cmp     eax, r12d
0x18002f8d8  ja      short loc_18002F941
0x18002f8da  add     eax, 8
0x18002f8dd  mov     [rsp+138h+var_E8], eax
0x18002f8e1  cmp     r15b, 20h ; ' '
0x18002f8e5  jz      short loc_18002F927
0x18002f8e7  cmp     r15b, 22h ; '"'
0x18002f8eb  jz      short loc_18002F922
0x18002f8ed  cmp     r15b, 24h ; '$'
0x18002f8f1  jnz     short loc_18002F8F8
0x18002f8f3  mov     r15b, 25h ; '%'
0x18002f8f6  jmp     short loc_18002F92A
0x18002f8f8  lea     rdx, [rbx-18h]
0x18002f8fc  or      eax, 0FFFFFFFFh
0x18002f8ff  lock xadd [rdx+10h], eax
0x18002f904  sub     eax, 1
0x18002f907  jg      short loc_18002F918
0x18002f909  mov     rcx, [rdx]
0x18002f90c  mov     rax, [rcx]
0x18002f90f  mov     rax, [rax+8]
0x18002f913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f918  mov     eax, 80004001h
0x18002f91d  jmp     loc_18002FAD7
0x18002f922  mov     r15b, 23h ; '#'
0x18002f925  jmp     short loc_18002F92A
0x18002f927  mov     r15b, 21h ; '!'
0x18002f92a  mov     rax, [r14+48h]
0x18002f92e  mov     edx, [rsp+138h+var_E4]
0x18002f932  mov     [rax], edx
0x18002f934  mov     [rax+4], edi
0x18002f937  mov     edi, [rsp+138h+var_E8]
0x18002f93b  mov     r12, [r14+48h]
0x18002f93f  jmp     short loc_18002F9BE
0x18002f941  lea     r12d, [rdi+4]
0x18002f945  cmp     [r14+60h], r12d
0x18002f949  jnb     short loc_18002F99D
0x18002f94b  mov     rcx, [r14+58h]; Block
  ... truncated ...
```
