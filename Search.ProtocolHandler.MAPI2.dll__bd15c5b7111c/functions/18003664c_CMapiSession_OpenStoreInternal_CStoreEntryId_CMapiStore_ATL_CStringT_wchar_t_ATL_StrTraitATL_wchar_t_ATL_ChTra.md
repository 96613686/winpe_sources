# CMapiSession::OpenStoreInternal(CStoreEntryId &,CMapiStore * *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)

- ea: `0x18003664c`
- end: `0x180036a9e`
- name: `?OpenStoreInternal@CMapiSession@@AEAAJAEAVCStoreEntryId@@PEAPEAVCMapiStore@@PEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z`
- size: `1106`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035e68`
- `0x1800361f4`

## callees

- `0x180002780`
- `0x180004c20`
- `0x18000ad14`
- `0x18000e684`
- `0x18000e6e0`
- `0x18000fd58`
- `0x1800113ac`
- `0x1800113ec`
- `0x180011884`
- `0x180030754`
- `0x180031ddc`
- `0x180032328`
- `0x180033a38`
- `0x18003583c`
- `0x18003664c`
- `0x180036d3c`
- `0x180037030`
- `0x180037850`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036a47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036a47`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x180036901`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x180036901`

## string_xrefs

- `0x180036789`: `failed OpenMsgStore() with UNKNOWN_FLAGS, trying again`
- `0x1800368ef`: `Error string: {%s}, Component: {%s}, Low level error: {0x%X}, Error context: {0x%X}`
- `0x1800369f6`: `CMapiSession::OpenStoreInternal: Do not index online classic OST {%s}`
- `0x1800367c6`: `OpenMsgStore()`
- `0x180036890`: `CMapiSession::OpenStoreInternal: Failed to open message store {%s}`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CMapiSession::OpenStoreInternal(__int64 a1, unsigned int *a2, _QWORD *a3, __int64 a4, int a5)
{
  unsigned int *v9; // rsi
  __int64 CachedStore; // rax
  void *v12; // rax
  CMapiStore *v13; // rax
  int v14; // edi
  int v15; // eax
  int v16; // esi
  CMapiStore *v17; // rax
  CMapiStore *v18; // rsi
  int *v19; // rsi
  int *v20; // r9
  void *v21; // rax
  char *v22; // rbx
  struct IUnknown *v23; // [rsp+20h] [rbp-50h]
  __int64 v24; // [rsp+28h] [rbp-48h]
  struct IMsgStore *v25; // [rsp+50h] [rbp-20h] BYREF
  CMapiStore *v26; // [rsp+58h] [rbp-18h] BYREF
  __int64 v27; // [rsp+60h] [rbp-10h] BYREF
  unsigned int *v28; // [rsp+68h] [rbp-8h]
  LPVOID pv; // [rsp+A8h] [rbp+38h] BYREF

  v9 = a2 + 20;
  v28 = a2 + 20;
  CachedStore = CMapiSession::FindCachedStore((struct _RTL_CRITICAL_SECTION *)a1, (_QWORD *)a2 + 10);
  if ( CachedStore )
  {
    *a3 = CachedStore;
    return 0;
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&v27);
  LODWORD(pv) = 0;
  if ( (unsigned int)CMapiSupport::GetTrustLevelPropVal(
                       *a2,
                       *((_QWORD *)a2 + 1),
                       (unsigned int)&v27,
                       (unsigned int)&pv,
                       (__int64)&v25) != 2 )
  {
    v15 = 0;
    if ( a2[4] )
      v15 = (unsigned int)CEntryId::operator==(a2) != 0 ? 16 : 48;
    v16 = v15 | 1;
    if ( *(_DWORD *)(a1 + 160) )
      v16 = v15;
    v25 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int, struct IMsgStore **))(**(_QWORD **)(a1 + 24) + 40LL))(
            *(_QWORD *)(a1 + 24),
            0,
            *a2,
            *((_QWORD *)a2 + 1),
            0,
            v16 | 0x2000000u,
            &v25);
    if ( v14 == -2147221242 )
    {
      CLogger::Info(L"failed OpenMsgStore() with UNKNOWN_FLAGS, trying again");
      v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int, struct IMsgStore **))(**(_QWORD **)(a1 + 24) + 40LL))(
              *(_QWORD *)(a1 + 24),
              0,
              *a2,
              *((_QWORD *)a2 + 1),
              0,
              v16,
              &v25);
    }
    CLogger::Info(v14, L"OpenMsgStore()");
    if ( v14 )
    {
      if ( v14 >= 0 )
      {
        v18 = 0;
      }
      else
      {
        if ( CLogger::m_fLoggingEnabled )
        {
          pv = 0;
          v19 = &dword_1800444C4;
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
            (__int64)&v26,
            (const wchar_t *)&dword_1800444C4);
          CLogger::Error((unsigned int)v14, L"CMapiSession::OpenStoreInternal: Failed to open message store {%s}", v26);
          if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64, LPVOID *))(**(_QWORD **)(a1 + 24) + 24LL))(
                 *(_QWORD *)(a1 + 24),
                 (unsigned int)v14,
                 0x80000000LL,
                 &pv) >= 0
            && pv )
          {
            v20 = &dword_1800444C4;
            if ( *((_QWORD *)pv + 2) )
              v20 = (int *)*((_QWORD *)pv + 2);
            if ( *((_QWORD *)pv + 1) )
              v19 = (int *)*((_QWORD *)pv + 1);
            LODWORD(v24) = *((_DWORD *)pv + 7);
            LODWORD(v23) = *((_DWORD *)pv + 6);
            CLogger::Error(
              (unsigned int)v14,
              L"Error string: {%s}, Component: {%s}, Low level error: {0x%X}, Error context: {0x%X}",
              v19,
              v20,
              v23,
              v24);
            MAPIFreeBuffer(pv);
          }
          ATL::CStringData::Release((CMapiStore *)((char *)v26 - 24));
        }
        if ( !a5 )
          goto LABEL_48;
        v21 = operator new(0x2A0u, (const struct std::nothrow_t *)&std::nothrow);
        pv = v21;
        if ( v21 )
          v18 = CMapiStore::CMapiStore(
                  (CMapiStore *)v21,
                  *(_QWORD *)(a1 + 16),
                  (__int64)a2,
                  (struct _SPropValue *)a1,
                  0,
                  1u,
                  0,
                  a4,
                  1);
        else
          v18 = 0;
        if ( !v18 )
          goto LABEL_21;
        v14 = 0;
      }
    }
    else
    {
      if ( a2[12] )
        CStoreEntryId::ReInitializeEID((CStoreEntryId *)a2, v25);
      v17 = (CMapiStore *)operator new(0x2A0u, (const struct std::nothrow_t *)&std::nothrow);
      v26 = v17;
      if ( v17 )
        v18 = CMapiStore::CMapiStore(
                v17,
                *(_QWORD *)(a1 + 16),
                (__int64)a2,
                (struct _SPropValue *)a1,
                (struct IUnknown *)v25,
                0,
                (_DWORD)pv == 0,
                a4,
                0);
      else
        v18 = 0;
      if ( !v18 )
      {
LABEL_21:
        v14 = -2147024882;
LABEL_48:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v25);
        v9 = v28;
        goto LABEL_49;
      }
    }
    if ( *((_DWORD *)v18 + 20) && a2[13] && !*((_DWORD *)v18 + 24) )
    {
      LODWORD(pv) = 0;
      v14 = CMapiSupport::CheckPolicyOnStore(v18, (int *)&pv, 0);
      if ( v14 < 0 )
      {
LABEL_46:
        if ( v18 )
          (*(void (__fastcall **)(CMapiStore *, __int64))(*(_QWORD *)v18 + 24LL))(v18, 1);
        goto LABEL_48;
      }
      if ( !(_DWORD)pv )
      {
        v14 = -2147216895;
        if ( CLogger::m_fLoggingEnabled )
        {
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)&pv);
          CMapiStore::GetDisplayName(v18, &pv);
          v22 = (char *)pv;
          CLogger::Info(-2147216895, L"CMapiSession::OpenStoreInternal: Do not index online classic OST {%s}", pv);
          ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
        }
        goto LABEL_46;
      }
    }
    *a3 = v18;
    goto LABEL_48;
  }
  v12 = operator new(0x2A0u, (const struct std::nothrow_t *)&std::nothrow);
  pv = v12;
  if ( v12 )
    v13 = CMapiStore::CMapiStore((CMapiStore *)v12, *(_QWORD *)(a1 + 16), (__int64)a2, 0, 0, 1u, 0, a4, 0);
  else
    v13 = 0;
  *a3 = v13;
  v14 = v13 == 0 ? 0x8007000E : 0;
LABEL_49:
  if ( v14 >= 0 )
  {
    if ( *a3 )
    {
      pv = (LPVOID)(a1 + 120);
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 120));
      ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiStore *>>::SetAt(
        a1 + 48,
        *(_QWORD *)v9,
        a3);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>((struct _RTL_CRITICAL_SECTION **)&pv);
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003664c  mov     [rsp-28h+arg_0], rbx
0x180036651  mov     [rsp-28h+arg_10], rsi
0x180036656  push    rbp
0x180036657  push    rdi
0x180036658  push    r13
0x18003665a  push    r14
0x18003665c  push    r15
0x18003665e  mov     rbp, rsp
0x180036661  sub     rsp, 70h
0x180036665  mov     r13, r9
0x180036668  mov     r15, r8
0x18003666b  mov     rbx, rdx
0x18003666e  mov     r14, rcx
0x180036671  lea     rsi, [rdx+50h]
0x180036675  mov     [rbp+var_8], rsi
0x180036679  mov     rdx, rsi
0x18003667c  call    ?FindCachedStore@CMapiSession@@AEAAPEAVCMapiStore@@AEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiSession::FindCachedStore(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180036681  xor     edi, edi
0x180036683  test    rax, rax
0x180036686  jz      short loc_180036692
0x180036688  mov     [r15], rax
0x18003668b  xor     eax, eax
0x18003668d  jmp     loc_180036A77
0x180036692  lea     rcx, [rbp+var_10]
0x180036696  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18003669b  nop
0x18003669c  mov     dword ptr [rbp+pv], edi
0x18003669f  lea     rax, [rbp+var_20]
0x1800366a3  mov     [rsp+70h+var_50], rax
0x1800366a8  lea     r9, [rbp+pv]
0x1800366ac  lea     r8, [rbp+var_10]
0x1800366b0  mov     rdx, [rbx+8]
0x1800366b4  mov     ecx, [rbx]
0x1800366b6  call    ?GetTrustLevelPropVal@CMapiSupport@@SAHKPEAEAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAK2@Z; CMapiSupport::GetTrustLevelPropVal(ulong,uchar *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ulong *,ulong *)
0x1800366bb  cmp     eax, 2
0x1800366be  jnz     short loc_180036720
0x1800366c0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800366c7  mov     ecx, 2A0h; unsigned __int64
0x1800366cc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800366d1  mov     [rbp+pv], rax
0x1800366d5  test    rax, rax
0x1800366d8  jz      short loc_180036708
0x1800366da  mov     [rsp+70h+var_30], edi; int
0x1800366de  mov     [rsp+70h+var_38], r13; __int64
0x1800366e3  mov     [rsp+70h+var_40], edi; int
0x1800366e7  mov     dword ptr [rsp+70h+var_48], 1; unsigned int
0x1800366ef  mov     [rsp+70h+var_50], rdi; struct IUnknown *
0x1800366f4  xor     r9d, r9d
0x1800366f7  mov     r8, rbx
0x1800366fa  mov     rdx, [r14+10h]
0x1800366fe  mov     rcx, rax; this
0x180036701  call    ??0CMapiStore@@QEAA@PEAVCMapiManager@@AEAVCStoreEntryId@@PEAVCMapiSession@@PEAUIMsgStore@@HHPEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z; CMapiStore::CMapiStore(CMapiManager *,CStoreEntryId &,CMapiSession *,IMsgStore *,int,int,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)
0x180036706  jmp     short loc_18003670B
0x180036708  mov     rax, rdi
0x18003670b  mov     [r15], rax
0x18003670e  neg     rax
0x180036711  sbb     edi, edi
0x180036713  not     edi
0x180036715  and     edi, 8007000Eh
0x18003671b  jmp     loc_180036A35
0x180036720  mov     eax, edi
0x180036722  lea     rdx, [rbx+10h]
0x180036726  cmp     [rdx], edi
0x180036728  jbe     short loc_18003673C
0x18003672a  mov     rcx, rbx
0x18003672d  call    ??8CEntryId@@QEAAHAEBV0@@Z; CEntryId::operator==(CEntryId const &)
0x180036732  neg     eax
0x180036734  sbb     eax, eax
0x180036736  and     eax, 0FFFFFFE0h
0x180036739  add     eax, 30h ; '0'
0x18003673c  mov     esi, eax
0x18003673e  or      esi, 1
0x180036741  cmp     [r14+0A0h], edi
0x180036748  cmovnz  esi, eax
0x18003674b  mov     [rbp+var_20], rdi
0x18003674f  mov     rcx, [r14+18h]
0x180036753  mov     rax, [rcx]
0x180036756  mov     edx, esi
0x180036758  bts     edx, 19h
0x18003675c  lea     r8, [rbp+var_20]
0x180036760  mov     qword ptr [rsp+70h+var_40], r8
0x180036765  mov     dword ptr [rsp+70h+var_48], edx
0x180036769  mov     [rsp+70h+var_50], rdi
0x18003676e  mov     r9, [rbx+8]
0x180036772  mov     r8d, [rbx]
0x180036775  xor     edx, edx
0x180036777  mov     rax, [rax+28h]
0x18003677b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036780  mov     edi, eax
0x180036782  cmp     eax, 80040106h
0x180036787  jnz     short loc_1800367C6
0x180036789  lea     rcx, aFailedOpenmsgs; "failed OpenMsgStore() with UNKNOWN_FLAG"...
0x180036790  call    ?Info@CLogger@@SAXPEB_WZZ; CLogger::Info(wchar_t const *,...)
0x180036795  mov     rcx, [r14+18h]
0x180036799  mov     rax, [rcx]
0x18003679c  lea     rdx, [rbp+var_20]
0x1800367a0  mov     qword ptr [rsp+70h+var_40], rdx
0x1800367a5  mov     dword ptr [rsp+70h+var_48], esi
0x1800367a9  mov     [rsp+70h+var_50], 0
0x1800367b2  mov     r9, [rbx+8]
0x1800367b6  mov     r8d, [rbx]
0x1800367b9  xor     edx, edx
0x1800367bb  mov     rax, [rax+28h]
0x1800367bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367c4  mov     edi, eax
0x1800367c6  lea     rdx, aOpenmsgstore; "OpenMsgStore()"
0x1800367cd  mov     ecx, edi; int
0x1800367cf  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x1800367d4  test    edi, edi
0x1800367d6  jnz     loc_18003685D
0x1800367dc  cmp     [rbx+30h], edi
0x1800367df  jz      short loc_1800367ED
0x1800367e1  mov     rdx, [rbp+var_20]; struct IMsgStore *
0x1800367e5  mov     rcx, rbx; this
0x1800367e8  call    ?ReInitializeEID@CStoreEntryId@@QEAAJPEAUIMsgStore@@@Z; CStoreEntryId::ReInitializeEID(IMsgStore *)
0x1800367ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800367f4  mov     ecx, 2A0h; unsigned __int64
0x1800367f9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800367fe  mov     [rbp+var_18], rax
0x180036802  test    rax, rax
0x180036805  jz      short loc_180036848
0x180036807  xor     edx, edx
0x180036809  cmp     dword ptr [rbp+pv], edx
0x18003680c  setz    dl
0x18003680f  mov     rcx, [rbp+var_20]
0x180036813  mov     [rsp+70h+var_30], 0; int
0x18003681b  mov     [rsp+70h+var_38], r13; __int64
0x180036820  mov     [rsp+70h+var_40], edx; int
0x180036824  mov     dword ptr [rsp+70h+var_48], 0; unsigned int
0x18003682c  mov     [rsp+70h+var_50], rcx; struct IUnknown *
0x180036831  mov     r9, r14
0x180036834  mov     r8, rbx
0x180036837  mov     rdx, [r14+10h]
0x18003683b  mov     rcx, rax; this
0x18003683e  call    ??0CMapiStore@@QEAA@PEAVCMapiManager@@AEAVCStoreEntryId@@PEAVCMapiSession@@PEAUIMsgStore@@HHPEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z; CMapiStore::CMapiStore(CMapiManager *,CStoreEntryId &,CMapiSession *,IMsgStore *,int,int,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)
0x180036843  mov     rsi, rax
0x180036846  jmp     short loc_18003684A
0x180036848  xor     esi, esi
0x18003684a  test    rsi, rsi
0x18003684d  jnz     loc_180036987
0x180036853  mov     edi, 8007000Eh
0x180036858  jmp     loc_180036A28
0x18003685d  jns     loc_180036985
0x180036863  cmp     cs:?m_fLoggingEnabled@CLogger@@0HA, 0; int CLogger::m_fLoggingEnabled
0x18003686a  jz      loc_180036915
0x180036870  mov     [rbp+pv], 0
0x180036878  lea     rsi, dword_1800444C4
0x18003687f  mov     rdx, rsi
0x180036882  lea     rcx, [rbp+var_18]
0x180036886  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18003688b  nop
0x18003688c  mov     r8, [rbp+var_18]
0x180036890  lea     rdx, aCmapisessionOp; "CMapiSession::OpenStoreInternal: Failed"...
0x180036897  mov     ecx, edi; int
0x180036899  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18003689e  mov     rcx, [r14+18h]
0x1800368a2  mov     rax, [rcx]
0x1800368a5  lea     r9, [rbp+pv]
0x1800368a9  mov     r8d, 80000000h
0x1800368af  mov     edx, edi
0x1800368b1  mov     rax, [rax+18h]
0x1800368b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368ba  test    eax, eax
0x1800368bc  js      short loc_180036908
0x1800368be  mov     rdx, [rbp+pv]
0x1800368c2  test    rdx, rdx
0x1800368c5  jz      short loc_180036908
0x1800368c7  mov     eax, [rdx+1Ch]
0x1800368ca  mov     ecx, [rdx+18h]
0x1800368cd  mov     r9, rsi
0x1800368d0  cmp     qword ptr [rdx+10h], 0
0x1800368d5  cmovnz  r9, [rdx+10h]
0x1800368da  cmp     qword ptr [rdx+8], 0
0x1800368df  cmovnz  rsi, [rdx+8]
0x1800368e4  mov     dword ptr [rsp+70h+var_48], eax
0x1800368e8  mov     dword ptr [rsp+70h+var_50], ecx
0x1800368ec  mov     r8, rsi
0x1800368ef  lea     rdx, aErrorStringSCo; "Error string: {%s}, Component: {%s}, Lo"...
0x1800368f6  mov     ecx, edi; int
0x1800368f8  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x1800368fd  mov     rcx, [rbp+pv]; pv
0x180036901  call    cs:__imp_MAPIFreeBuffer
0x180036907  nop
0x180036908  mov     rcx, [rbp+var_18]
0x18003690c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180036910  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180036915  cmp     [rbp+arg_20], 0
0x180036919  jz      loc_180036A28
0x18003691f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180036926  mov     ecx, 2A0h; unsigned __int64
0x18003692b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180036930  mov     [rbp+pv], rax
0x180036934  test    rax, rax
0x180036937  jz      short loc_180036976
0x180036939  mov     [rsp+70h+var_30], 1; int
0x180036941  mov     [rsp+70h+var_38], r13; __int64
0x180036946  mov     [rsp+70h+var_40], 0; int
0x18003694e  mov     dword ptr [rsp+70h+var_48], 1; unsigned int
0x180036956  mov     [rsp+70h+var_50], 0; struct IUnknown *
0x18003695f  mov     r9, r14
0x180036962  mov     r8, rbx
0x180036965  mov     rdx, [r14+10h]
0x180036969  mov     rcx, rax; this
0x18003696c  call    ??0CMapiStore@@QEAA@PEAVCMapiManager@@AEAVCStoreEntryId@@PEAVCMapiSession@@PEAUIMsgStore@@HHPEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@H@Z; CMapiStore::CMapiStore(CMapiManager *,CStoreEntryId &,CMapiSession *,IMsgStore *,int,int,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> *,int)
0x180036971  mov     rsi, rax
0x180036974  jmp     short loc_180036978
0x180036976  xor     esi, esi
0x180036978  test    rsi, rsi
0x18003697b  jz      loc_180036853
0x180036981  xor     edi, edi
0x180036983  jmp     short loc_180036987
0x180036985  xor     esi, esi
0x180036987  cmp     dword ptr [rsi+50h], 0
0x18003698b  jz      loc_180036A90
0x180036991  cmp     dword ptr [rbx+34h], 0
0x180036995  jz      loc_180036A90
0x18003699b  cmp     dword ptr [rsi+60h], 0
0x18003699f  jnz     loc_180036A90
0x1800369a5  mov     dword ptr [rbp+pv], 0
0x1800369ac  xor     r8d, r8d; enum POLICY_RESULT_ID *
0x1800369af  lea     rdx, [rbp+pv]; int *
0x1800369b3  mov     rcx, rsi; struct CMapiStore *
0x1800369b6  call    ?CheckPolicyOnStore@CMapiSupport@@SAJPEAVCMapiStore@@PEAHPEAW4POLICY_RESULT_ID@@@Z; CMapiSupport::CheckPolicyOnStore(CMapiStore *,int *,POLICY_RESULT_ID *)
0x1800369bb  mov     edi, eax
0x1800369bd  test    eax, eax
0x1800369bf  js      short loc_180036A0E
0x1800369c1  cmp     dword ptr [rbp+pv], 0
0x1800369c5  jnz     loc_180036A98
0x1800369cb  mov     edi, 80041201h
0x1800369d0  cmp     cs:?m_fLoggingEnabled@CLogger@@0HA, 0; int CLogger::m_fLoggingEnabled
0x1800369d7  jz      short loc_180036A0E
0x1800369d9  lea     rcx, [rbp+pv]
0x1800369dd  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800369e2  nop
0x1800369e3  lea     rdx, [rbp+pv]
0x1800369e7  mov     rcx, rsi
0x1800369ea  call    ?GetDisplayName@CMapiStore@@QEAAJAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiStore::GetDisplayName(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1800369ef  mov     rbx, [rbp+pv]
0x1800369f3  mov     r8, rbx
0x1800369f6  lea     rdx, aCmapisessionOp_3; "CMapiSession::OpenStoreInternal: Do not"...
0x1800369fd  mov     ecx, edi; int
0x1800369ff  call    ?Info@CLogger@@SAXJPEB_WZZ; CLogger::Info(long,wchar_t const *,...)
0x180036a04  nop
0x180036a05  lea     rcx, [rbx-18h]; this
0x180036a09  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180036a0e  test    rsi, rsi
0x180036a11  jz      short loc_180036A28
0x180036a13  mov     rax, [rsi]
0x180036a16  mov     edx, 1
0x180036a1b  mov     rcx, rsi
0x180036a1e  mov     rax, [rax+18h]
0x180036a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a27  nop
0x180036a28  lea     rcx, [rbp+var_20]
0x180036a2c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180036a31  mov     rsi, [rbp+var_8]
0x180036a35  test    edi, edi
0x180036a37  js      short loc_180036A68
0x180036a39  cmp     qword ptr [r15], 0
0x180036a3d  jz      short loc_180036A68
0x180036a3f  lea     rcx, [r14+78h]; lpCriticalSection
0x180036a43  mov     [rbp+pv], rcx
0x180036a47  call    cs:__imp_EnterCriticalSection
0x180036a4d  nop
0x180036a4e  lea     rcx, [r14+30h]
0x180036a52  mov     r8, r15
0x180036a55  mov     rdx, [rsi]
0x180036a58  call    ?SetAt@?$CAtlMap@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAVCMapiStore@@V?$CStringElementTraits@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAVCMapiStore@@@2@@ATL@@QEAAPEAU__POSITION@@PEB_WAEBQEAVCMapiStore@@@Z; ATL::CAtlMap<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,CMapiStore *,ATL::CStringElementTraits<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>,ATL::CElementTraits<CMapiStore *>>::SetAt(wchar_t const *,CMapiStore * const &)
0x180036a5d  nop
0x180036a5e  lea     rcx, [rbp+pv]
0x180036a62  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180036a67  nop
0x180036a68  mov     rcx, [rbp+var_10]
0x180036a6c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180036a70  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180036a75  mov     eax, edi
0x180036a77  lea     r11, [rsp+70h+var_s0]
0x180036a7c  mov     rbx, [r11+30h]
0x180036a80  mov     rsi, [r11+40h]
0x180036a84  mov     rsp, r11
0x180036a87  pop     r15
0x180036a89  pop     r14
0x180036a8b  pop     r13
0x180036a8d  pop     rdi
0x180036a8e  pop     rbp
0x180036a8f  retn
0x180036a90  test    edi, edi
0x180036a92  js      loc_180036A0E
0x180036a98  mov     [r15], rsi
0x180036a9b  jmp     short loc_180036A28
```
