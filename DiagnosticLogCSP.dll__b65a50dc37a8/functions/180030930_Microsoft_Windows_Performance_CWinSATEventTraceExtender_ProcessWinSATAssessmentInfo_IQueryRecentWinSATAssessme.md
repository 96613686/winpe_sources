# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)

- ea: `0x180030930`
- end: `0x180030f5e`
- name: `?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z`
- size: `1582`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *__hidden this, struct IQueryRecentWinSATAssessment *, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002, unsigned __int8, OLECHAR *psz, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030f64`

## callees

- `0x180001b90`
- `0x18000265c`
- `0x180002d25`
- `0x180011648`
- `0x18001a030`
- `0x180030930`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030c9d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030d9a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030c9d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030d9a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180030cb3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180030db1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180030cb3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180030db1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800309bf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800309bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800309f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180030b9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180030c2e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800309f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180030b9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180030c2e`

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
0x180030930  push    rbx
0x180030932  push    rsi
0x180030933  push    rdi
0x180030934  push    r12
0x180030936  push    r13
0x180030938  push    r14
0x18003093a  push    r15
0x18003093c  sub     rsp, 100h
0x180030943  mov     rax, cs:__security_cookie
0x18003094a  xor     rax, rsp
0x18003094d  mov     [rsp+138h+var_48], rax
0x180030955  mov     r15b, r9b
0x180030958  mov     [rsp+138h+var_E4], r8d
0x18003095d  mov     r12, rdx
0x180030960  mov     r14, rcx
0x180030963  mov     rbx, [rsp+138h+psz]
0x18003096b  xor     esi, esi
0x18003096d  test    rdx, rdx
0x180030970  jnz     short loc_18003097C
0x180030972  mov     eax, 80004003h
0x180030977  jmp     loc_180030F2E
0x18003097c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180030983  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003098a  mov     rax, [rax+18h]
0x18003098e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030993  lea     rdi, [rax+18h]
0x180030997  mov     [rsp+138h+Src], rdi
0x18003099c  mov     [rsp+138h+var_E0], rsi
0x1800309a1  mov     [rsp+138h+var_D8], rsi
0x1800309a6  mov     r13, [r12]
0x1800309aa  test    rbx, rbx
0x1800309ad  jnz     short loc_1800309BC
0x1800309af  mov     rbx, rsi
0x1800309b2  mov     [rsp+138h+var_C0], rbx
0x1800309b7  mov     rdx, rsi
0x1800309ba  jmp     short loc_1800309DF
0x1800309bc  mov     rcx, rbx; psz
0x1800309bf  call    cs:__imp_SysAllocString
0x1800309c6  nop     dword ptr [rax+rax+00h]
0x1800309cb  mov     rbx, rax
0x1800309ce  mov     [rsp+138h+var_C0], rax
0x1800309d3  test    rax, rax
0x1800309d6  jz      loc_180030F52
0x1800309dc  mov     rdx, rax
0x1800309df  lea     r9, [rsp+138h+var_E0]
0x1800309e4  xor     r8d, r8d
0x1800309e7  mov     rcx, r12
0x1800309ea  mov     rax, [r13+38h]
0x1800309ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309f3  mov     r12d, eax
0x1800309f6  mov     rcx, rbx; bstrString
0x1800309f9  call    cs:__imp_SysFreeString
0x180030a00  nop     dword ptr [rax+rax+00h]
0x180030a05  test    r12d, r12d
0x180030a08  jns     short loc_180030A60
0x180030a0a  mov     rcx, [rsp+138h+var_D8]
0x180030a0f  test    rcx, rcx
0x180030a12  jz      short loc_180030A21
0x180030a14  mov     rax, [rcx]
0x180030a17  mov     rax, [rax+10h]
0x180030a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a20  nop
0x180030a21  mov     rcx, [rsp+138h+var_E0]
0x180030a26  test    rcx, rcx
0x180030a29  jz      short loc_180030A38
0x180030a2b  mov     rax, [rcx]
0x180030a2e  mov     rax, [rax+10h]
0x180030a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a37  nop
0x180030a38  lea     rdx, [rdi-18h]
0x180030a3c  or      eax, 0FFFFFFFFh
0x180030a3f  lock xadd [rdx+10h], eax
0x180030a44  sub     eax, 1
0x180030a47  jg      short loc_180030A58
0x180030a49  mov     rcx, [rdx]
0x180030a4c  mov     rax, [rcx]
0x180030a4f  mov     rax, [rax+8]
0x180030a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a58  mov     eax, r12d
0x180030a5b  jmp     loc_180030F2E
0x180030a60  mov     rcx, [rsp+138h+var_E0]
0x180030a65  test    rcx, rcx
0x180030a68  jnz     short loc_180030AC4
0x180030a6a  mov     rdx, [rsp+138h+var_D8]
0x180030a6f  test    rdx, rdx
0x180030a72  jz      short loc_180030A88
0x180030a74  mov     rax, [rdx]
0x180030a77  mov     rcx, rdx
0x180030a7a  mov     rax, [rax+10h]
0x180030a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a83  mov     rcx, [rsp+138h+var_E0]
0x180030a88  test    rcx, rcx
0x180030a8b  jz      short loc_180030A9A
0x180030a8d  mov     rax, [rcx]
0x180030a90  mov     rax, [rax+10h]
0x180030a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a99  nop
0x180030a9a  lea     rdx, [rdi-18h]
0x180030a9e  or      eax, 0FFFFFFFFh
0x180030aa1  lock xadd [rdx+10h], eax
0x180030aa6  sub     eax, 1
0x180030aa9  jg      short loc_180030ABA
0x180030aab  mov     rcx, [rdx]
0x180030aae  mov     rax, [rcx]
0x180030ab1  mov     rax, [rax+8]
0x180030ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030aba  mov     eax, 1
0x180030abf  jmp     loc_180030F2E
0x180030ac4  mov     rax, [rcx]
0x180030ac7  lea     rdx, [rsp+138h+var_D8]
0x180030acc  mov     rax, [rax+48h]
0x180030ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ad5  mov     ebx, eax
0x180030ad7  test    eax, eax
0x180030ad9  jns     short loc_180030B30
0x180030adb  mov     rcx, [rsp+138h+var_D8]
0x180030ae0  test    rcx, rcx
0x180030ae3  jz      short loc_180030AF2
0x180030ae5  mov     rdx, [rcx]
0x180030ae8  mov     rax, [rdx+10h]
0x180030aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030af1  nop
0x180030af2  mov     rcx, [rsp+138h+var_E0]
0x180030af7  test    rcx, rcx
0x180030afa  jz      short loc_180030B09
0x180030afc  mov     rax, [rcx]
0x180030aff  mov     rax, [rax+10h]
0x180030b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b08  nop
0x180030b09  lea     rdx, [rdi-18h]
0x180030b0d  or      eax, 0FFFFFFFFh
0x180030b10  lock xadd [rdx+10h], eax
0x180030b15  sub     eax, 1
0x180030b18  jg      short loc_180030B29
0x180030b1a  mov     rcx, [rdx]
0x180030b1d  mov     rax, [rcx]
0x180030b20  mov     rax, [rax+8]
0x180030b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b29  mov     eax, ebx
0x180030b2b  jmp     loc_180030F2E
0x180030b30  mov     rcx, [rsp+138h+var_D8]
0x180030b35  test    rcx, rcx
0x180030b38  jnz     short loc_180030B7B
0x180030b3a  mov     rcx, [rsp+138h+var_E0]
0x180030b3f  test    rcx, rcx
0x180030b42  jz      short loc_180030B51
0x180030b44  mov     rax, [rcx]
0x180030b47  mov     rax, [rax+10h]
0x180030b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b50  nop
0x180030b51  lea     rdx, [rdi-18h]
0x180030b55  or      eax, 0FFFFFFFFh
0x180030b58  lock xadd [rdx+10h], eax
0x180030b5d  sub     eax, 1
0x180030b60  jg      short loc_180030B71
0x180030b62  mov     rcx, [rdx]
0x180030b65  mov     rax, [rcx]
0x180030b68  mov     rax, [rax+8]
0x180030b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b71  mov     eax, 1
0x180030b76  jmp     loc_180030F2E
0x180030b7b  mov     [rsp+138h+bstrString], rsi
0x180030b80  mov     rax, [rcx]
0x180030b83  lea     rdx, [rsp+138h+bstrString]
0x180030b88  mov     rax, [rax+110h]
0x180030b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b94  mov     ebx, eax
0x180030b96  test    eax, eax
0x180030b98  jns     short loc_180030C01
0x180030b9a  mov     rcx, [rsp+138h+bstrString]; bstrString
0x180030b9f  call    cs:__imp_SysFreeString
0x180030ba6  nop     dword ptr [rax+rax+00h]
0x180030bab  nop
0x180030bac  mov     rcx, [rsp+138h+var_D8]
0x180030bb1  test    rcx, rcx
0x180030bb4  jz      short loc_180030BC3
0x180030bb6  mov     rax, [rcx]
0x180030bb9  mov     rax, [rax+10h]
0x180030bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bc2  nop
0x180030bc3  mov     rcx, [rsp+138h+var_E0]
0x180030bc8  test    rcx, rcx
0x180030bcb  jz      short loc_180030BDA
0x180030bcd  mov     rax, [rcx]
0x180030bd0  mov     rax, [rax+10h]
0x180030bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bd9  nop
0x180030bda  lea     rdx, [rdi-18h]
0x180030bde  or      eax, 0FFFFFFFFh
0x180030be1  lock xadd [rdx+10h], eax
0x180030be6  sub     eax, 1
0x180030be9  jg      short loc_180030BFA
0x180030beb  mov     rcx, [rdx]
0x180030bee  mov     rax, [rcx]
0x180030bf1  mov     rax, [rax+8]
0x180030bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bfa  mov     eax, ebx
0x180030bfc  jmp     loc_180030F2E
0x180030c01  mov     rdx, [rsp+138h+bstrString]
0x180030c06  test    rdx, rdx
0x180030c09  jnz     short loc_180030C10
0x180030c0b  mov     r8d, esi
0x180030c0e  jmp     short loc_180030C1E
0x180030c10  or      r8, 0FFFFFFFFFFFFFFFFh
0x180030c14  inc     r8
0x180030c17  cmp     [rdx+r8*2], si
0x180030c1c  jnz     short loc_180030C14
0x180030c1e  lea     rcx, [rsp+138h+Src]
0x180030c23  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180030c28  nop
0x180030c29  mov     rcx, [rsp+138h+bstrString]; bstrString
0x180030c2e  call    cs:__imp_SysFreeString
0x180030c35  nop     dword ptr [rax+rax+00h]
0x180030c3a  nop
0x180030c3b  mov     rcx, [rsp+138h+var_D8]
0x180030c40  test    rcx, rcx
0x180030c43  jz      short loc_180030C52
0x180030c45  mov     rax, [rcx]
0x180030c48  mov     rax, [rax+10h]
0x180030c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c51  nop
0x180030c52  mov     rcx, [rsp+138h+var_E0]
0x180030c57  test    rcx, rcx
0x180030c5a  jz      short loc_180030C69
0x180030c5c  mov     rax, [rcx]
0x180030c5f  mov     rax, [rax+10h]
0x180030c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c68  nop
0x180030c69  mov     rbx, [rsp+138h+Src]
0x180030c6e  mov     eax, [rbx-10h]
0x180030c71  lea     edi, ds:2[rax*2]
0x180030c78  mov     [rsp+138h+var_E8], esi
0x180030c7c  cmp     edi, 8
0x180030c7f  jb      loc_180030D8C
0x180030c85  cmp     [r14+21h], sil
0x180030c89  jnz     loc_180030D8C
0x180030c8f  lea     r12d, [rdi-8]
0x180030c93  cmp     [r14+50h], r12d
0x180030c97  jnb     short loc_180030CD0
0x180030c99  mov     rcx, [r14+48h]; Block
0x180030c9d  call    cs:__imp_free
0x180030ca4  nop     dword ptr [rax+rax+00h]
0x180030ca9  mov     [r14+48h], rsi
0x180030cad  mov     [r14+50h], esi
0x180030cb1  mov     ecx, edi; Size
0x180030cb3  call    cs:__imp_malloc
0x180030cba  nop     dword ptr [rax+rax+00h]
0x180030cbf  mov     [r14+48h], rax
0x180030cc3  test    rax, rax
0x180030cc6  jz      loc_180030DC6
0x180030ccc  mov     [r14+50h], edi
0x180030cd0  mov     rax, [r14+28h]
0x180030cd4  test    rax, rax
0x180030cd7  jz      loc_180030D8C
0x180030cdd  mov     r9, [r14+48h]
0x180030ce1  add     r9, 8
0x180030ce5  mov     ecx, 102h
0x180030cea  mov     rdx, [r14+38h]
0x180030cee  mov     [rsp+138h+var_100], rdx
0x180030cf3  lea     rdx, [rsp+138h+var_E8]
0x180030cf8  mov     [rsp+138h+var_108], rdx
0x180030cfd  mov     [rsp+138h+var_110], 1000h
0x180030d05  mov     [rsp+138h+var_118], r12d
0x180030d0a  mov     r8d, edi
0x180030d0d  mov     rdx, rbx
0x180030d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d15  test    eax, eax
0x180030d17  jnz     short loc_180030D8C
0x180030d19  mov     eax, [rsp+138h+var_E8]
0x180030d1d  cmp     eax, r12d
0x180030d20  ja      short loc_180030D8C
0x180030d22  add     eax, 8
0x180030d25  mov     [rsp+138h+var_E8], eax
0x180030d29  cmp     r15b, 20h ; ' '
0x180030d2d  jz      short loc_180030D6F
0x180030d2f  cmp     r15b, 22h ; '"'
0x180030d33  jz      short loc_180030D6A
0x180030d35  cmp     r15b, 24h ; '$'
0x180030d39  jnz     short loc_180030D40
0x180030d3b  mov     r15b, 25h ; '%'
0x180030d3e  jmp     short loc_180030D72
0x180030d40  lea     rdx, [rbx-18h]
0x180030d44  or      eax, 0FFFFFFFFh
0x180030d47  lock xadd [rdx+10h], eax
0x180030d4c  sub     eax, 1
0x180030d4f  jg      short loc_180030D60
0x180030d51  mov     rcx, [rdx]
0x180030d54  mov     rax, [rcx]
0x180030d57  mov     rax, [rax+8]
0x180030d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d60  mov     eax, 80004001h
0x180030d65  jmp     loc_180030F2E
0x180030d6a  mov     r15b, 23h ; '#'
0x180030d6d  jmp     short loc_180030D72
0x180030d6f  mov     r15b, 21h ; '!'
0x180030d72  mov     rax, [r14+48h]
0x180030d76  mov     edx, [rsp+138h+var_E4]
0x180030d7a  mov     [rax], edx
0x180030d7c  mov     [rax+4], edi
0x180030d7f  mov     edi, [rsp+138h+var_E8]
  ... truncated ...
```
