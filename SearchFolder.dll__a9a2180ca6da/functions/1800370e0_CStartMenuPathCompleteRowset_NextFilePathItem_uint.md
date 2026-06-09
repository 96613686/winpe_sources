# CStartMenuPathCompleteRowset::_NextFilePathItem(uint *)

- ea: `0x1800370e0`
- end: `0x18003748c`
- name: `?_NextFilePathItem@CStartMenuPathCompleteRowset@@AEAAJPEAI@Z`
- size: `940`
- prototype: `__int64 __fastcall(CStartMenuPathCompleteRowset *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002ca90`

## callees

- `0x180003790`
- `0x180005460`
- `0x1800054b0`
- `0x180005c88`
- `0x1800076dc`
- `0x180028ddc`
- `0x18002d230`
- `0x18002eff0`
- `0x18002f7b0`
- `0x180030cdc`
- `0x1800370e0`
- `0x180037750`
- `0x180051010`

## import_xrefs

- `SHELL32!SHBindToObject` at `0x180037268`
- `SHELL32!SHBindToObject` at `0x180037268`
- `SHELL32!__imp_SHCoCreateInstance` at `0x1800371d2`
- `SHELL32!__imp_SHCoCreateInstance` at `0x1800371d2`
- `SHLWAPI!StrCmpIW` at `0x180037183`
- `SHLWAPI!StrCmpIW` at `0x180037183`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037171`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037171`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180037194`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180037466`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180037194`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180037466`

## pseudocode

```c
__int64 __fastcall CStartMenuPathCompleteRowset::_NextFilePathItem(
        CStartMenuPathCompleteRowset *this,
        unsigned int *a2)
{
  HRESULT ContinueOnSite; // edi
  __int64 v5; // rcx
  __int64 v6; // rdi
  const WCHAR *v7; // r14
  signed int v8; // ebx
  const WCHAR *v9; // rcx
  int v10; // eax
  int v11; // r15d
  unsigned int *v12; // rcx
  unsigned int v13; // r14d
  __int64 v14; // rcx
  INT_PTR v15; // rdx
  __int64 (__fastcall ***Ptr)(PVOID, GUID *, struct IShellFolder **); // rax
  __int64 (__fastcall ***v17)(PVOID, GUID *, struct IShellFolder **); // r9
  struct IEnumIDList *v18; // rbx
  struct CONDITIONEVALPROPS *v19; // r8
  _QWORD v21[2]; // [rsp+30h] [rbp-50h] BYREF
  int v22; // [rsp+40h] [rbp-40h]
  int v23; // [rsp+68h] [rbp-18h]
  void *ppv; // [rsp+C0h] [rbp+40h] BYREF
  struct IShellFolder *v25; // [rsp+C8h] [rbp+48h] BYREF
  struct IEnumIDList *v26; // [rsp+D0h] [rbp+50h] BYREF
  LPCITEMIDLIST pidl; // [rsp+D8h] [rbp+58h] BYREF

  *a2 = 0;
  ContinueOnSite = -2147467259;
  _InterlockedExchange64((volatile __int64 *)this + 21, (__int64)g_pStartMenuPathCompleteQueryCache);
  v5 = *((_QWORD *)this + 21);
  if ( v5 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
    ContinueOnSite = CStartMenuPathCompleteQueryCache::WaitForLock(
                       *((CStartMenuPathCompleteQueryCache **)this + 21),
                       *((struct IUnknown **)this + 3));
    if ( ContinueOnSite < 0 )
    {
LABEL_38:
      CStartMenuPathCompleteQueryCache::Release(*((CStartMenuPathCompleteQueryCache **)this + 21));
      return (unsigned int)ContinueOnSite;
    }
    ContinueOnSite = QueryContinueOnSite(*((struct IUnknown **)this + 3));
    if ( ContinueOnSite < 0 )
      goto LABEL_37;
    v6 = *((_QWORD *)this + 21);
    v7 = (const WCHAR *)*((_QWORD *)this + 17);
    v8 = -2147467259;
    WaitForSingleObject(*(HANDLE *)(v6 + 16), 0xFFFFFFFF);
    v9 = *(const WCHAR **)(v6 + 32);
    if ( v9 )
      v8 = StrCmpIW(v9, v7) != 0 ? 0x80004005 : 0;
    ReleaseMutex(*(HANDLE *)(v6 + 16));
    if ( v8 < 0 )
    {
      *((_DWORD *)this + 44) = 0;
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&ppv);
      ContinueOnSite = SHCoCreateInstance(0, &CLSID_ShellUrl, 0, &GUID_4f33718d_bae1_4f9b_96f2_d2a16e683346, &ppv);
      if ( ContinueOnSite >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppv + 184LL))(ppv, 0);
        ContinueOnSite = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
                           ppv,
                           *((_QWORD *)this + 17),
                           v10 | 1u);
        if ( ContinueOnSite >= 0 )
        {
          pidl = 0;
          ContinueOnSite = (*(__int64 (__fastcall **)(void *, LPCITEMIDLIST *))(*(_QWORD *)ppv + 56LL))(ppv, &pidl);
          if ( ContinueOnSite >= 0 )
          {
            ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v25);
            ContinueOnSite = SHBindToObject(0, pidl, 0, &GUID_000214e6_0000_0000_c000_000000000046, (void **)&v25);
            if ( ContinueOnSite >= 0 )
            {
              ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v26);
              ContinueOnSite = ((__int64 (__fastcall *)(struct IShellFolder *, _QWORD, __int64, struct IEnumIDList **))v25->lpVtbl->EnumObjects)(
                                 v25,
                                 0,
                                 96,
                                 &v26);
              if ( !ContinueOnSite )
              {
                ContinueOnSite = CStartMenuPathCompleteRowset::_PopulateCache(
                                   this,
                                   *((const unsigned __int16 **)this + 17),
                                   v25,
                                   v26);
                if ( ContinueOnSite >= 0 )
                  ContinueOnSite = QueryContinueOnSite(*((struct IUnknown **)this + 3));
              }
              ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v26);
            }
            ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v25);
          }
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&pidl);
        }
      }
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&ppv);
      if ( ContinueOnSite < 0 )
      {
LABEL_37:
        ReleaseMutex(*(HANDLE *)(*((_QWORD *)this + 21) + 16LL));
        goto LABEL_38;
      }
    }
    v11 = 0;
    v12 = *(unsigned int **)(*((_QWORD *)this + 21) + 24LL);
    if ( v12 )
      v13 = *v12;
    else
      v13 = 0;
    ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v26);
    v14 = *((_QWORD *)this + 16);
    if ( v14 )
    {
      ContinueOnSite = (*(__int64 (__fastcall **)(__int64, struct IEnumIDList **))(*(_QWORD *)v14 + 112LL))(v14, &v26);
      if ( ContinueOnSite < 0 )
      {
LABEL_35:
        ContinueOnSite = -2147467259;
LABEL_36:
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v26);
        goto LABEL_37;
      }
    }
    else
    {
      ContinueOnSite = 0;
    }
    do
    {
      if ( *((_DWORD *)this + 44) >= v13 )
        break;
      ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v25);
      v25 = 0;
      ContinueOnSite = -2147467259;
      Ptr = (__int64 (__fastcall ***)(PVOID, GUID *, struct IShellFolder **))g_pfn_DPA_GetPtr(
                                                                               *(HDPA *)(*((_QWORD *)this + 21) + 24LL),
                                                                               v15);
      v17 = Ptr;
      if ( Ptr )
        ContinueOnSite = (**Ptr)(Ptr, &GUID_3017056d_9a91_4e90_937d_746c72abbf4f, &v25);
      if ( ContinueOnSite >= 0 )
      {
        ++*((_DWORD *)this + 44);
        v18 = v26;
        LODWORD(ppv) = v26 == 0;
        if ( !v26
          || (memset_0(v21, 0, (unsigned int)(v26 == 0) + 72),
              v22 = 1,
              v21[0] = v25,
              v21[1] = v18,
              v23 = 1,
              GrepDoesItemMatchCondition((const struct CONDITIONEVALINFO *)v21, (int *)&ppv, v19),
              (_DWORD)ppv) )
        {
          LODWORD(ppv) = 0;
          ContinueOnSite = CDPA_Base<IPropertyStoreCache,CTContainer_PolicyUnOwned<IPropertyStoreCache>>::AppendPtr(
                             (char *)this + 144,
                             v25,
                             &ppv,
                             v17);
          if ( ContinueOnSite >= 0 )
          {
            ((void (__fastcall *)(struct IShellFolder *))v25->lpVtbl->AddRef)(v25);
            *a2 = (unsigned int)ppv;
            v11 = 1;
          }
        }
      }
      ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>((__int64)&v25);
    }
    while ( ContinueOnSite >= 0 );
    if ( v11 )
      goto LABEL_36;
    goto LABEL_35;
  }
  return (unsigned int)ContinueOnSite;
}

```

## disassembly

```asm
0x1800370e0  push    rbp
0x1800370e2  push    rbx
0x1800370e3  push    rsi
0x1800370e4  push    rdi
0x1800370e5  push    r12
0x1800370e7  push    r14
0x1800370e9  push    r15
0x1800370eb  mov     rbp, rsp
0x1800370ee  sub     rsp, 80h
0x1800370f5  mov     r12, rdx
0x1800370f8  mov     rsi, rcx
0x1800370fb  mov     dword ptr [rdx], 0
0x180037101  mov     r15d, 80004005h
0x180037107  mov     edi, r15d
0x18003710a  mov     rax, cs:?g_pStartMenuPathCompleteQueryCache@@3PEAVCStartMenuPathCompleteQueryCache@@EA; CStartMenuPathCompleteQueryCache * g_pStartMenuPathCompleteQueryCache
0x180037111  xchg    rax, [rcx+0A8h]
0x180037118  mov     rcx, [rcx+0A8h]
0x18003711f  test    rcx, rcx
0x180037122  jz      loc_180037478
0x180037128  lock inc dword ptr [rcx+8]
0x18003712c  mov     rdx, [rsi+18h]; struct IUnknown *
0x180037130  mov     rcx, [rsi+0A8h]; this
0x180037137  call    ?WaitForLock@CStartMenuPathCompleteQueryCache@@QEAAJPEAUIUnknown@@@Z; CStartMenuPathCompleteQueryCache::WaitForLock(IUnknown *)
0x18003713c  mov     edi, eax
0x18003713e  test    eax, eax
0x180037140  js      loc_18003746C
0x180037146  mov     rcx, [rsi+18h]; struct IUnknown *
0x18003714a  call    ?QueryContinueOnSite@@YAJPEAUIUnknown@@@Z; QueryContinueOnSite(IUnknown *)
0x18003714f  mov     edi, eax
0x180037151  test    eax, eax
0x180037153  js      loc_18003745B
0x180037159  mov     rdi, [rsi+0A8h]
0x180037160  mov     r14, [rsi+88h]
0x180037167  mov     ebx, r15d
0x18003716a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003716d  mov     rcx, [rdi+10h]; hHandle
0x180037171  call    cs:__imp_WaitForSingleObject
0x180037177  mov     rcx, [rdi+20h]; psz1
0x18003717b  test    rcx, rcx
0x18003717e  jz      short loc_180037190
0x180037180  mov     rdx, r14; psz2
0x180037183  call    cs:__imp_StrCmpIW
0x180037189  neg     eax
0x18003718b  sbb     ebx, ebx
0x18003718d  and     ebx, r15d
0x180037190  mov     rcx, [rdi+10h]; hMutex
0x180037194  call    cs:__imp_ReleaseMutex
0x18003719a  test    ebx, ebx
0x18003719c  jns     loc_1800372F5
0x1800371a2  mov     dword ptr [rsi+0B0h], 0
0x1800371ac  lea     rcx, [rbp+arg_0]; void *
0x1800371b0  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800371b5  nop
0x1800371b6  lea     rax, [rbp+arg_0]
0x1800371ba  mov     [rsp+80h+ppv], rax; ppv
0x1800371bf  lea     r9, _GUID_4f33718d_bae1_4f9b_96f2_d2a16e683346; riid
0x1800371c6  xor     r8d, r8d; pUnkOuter
0x1800371c9  lea     rdx, CLSID_ShellUrl; pclsid
0x1800371d0  xor     ecx, ecx; pszCLSID
0x1800371d2  call    cs:__imp_SHCoCreateInstance
0x1800371d8  mov     edi, eax
0x1800371da  test    eax, eax
0x1800371dc  js      loc_1800372E4
0x1800371e2  mov     rcx, [rbp+arg_0]
0x1800371e6  mov     rax, [rcx]
0x1800371e9  xor     edx, edx
0x1800371eb  mov     rax, [rax+0B8h]
0x1800371f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371f7  mov     r8d, eax
0x1800371fa  or      r8d, 1
0x1800371fe  mov     rcx, [rbp+arg_0]
0x180037202  mov     rax, [rcx]
0x180037205  mov     rdx, [rsi+88h]
0x18003720c  mov     rax, [rax+18h]
0x180037210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037215  mov     edi, eax
0x180037217  test    eax, eax
0x180037219  js      loc_1800372E4
0x18003721f  mov     [rbp+pidl], 0
0x180037227  mov     rcx, [rbp+arg_0]
0x18003722b  mov     rax, [rcx]
0x18003722e  lea     rdx, [rbp+pidl]
0x180037232  mov     rax, [rax+38h]
0x180037236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003723b  mov     edi, eax
0x18003723d  test    eax, eax
0x18003723f  js      loc_1800372DA
0x180037245  lea     rcx, [rbp+arg_8]; void *
0x180037249  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003724e  nop
0x18003724f  lea     rax, [rbp+arg_8]
0x180037253  mov     [rsp+80h+ppv], rax; ppv
0x180037258  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18003725f  xor     r8d, r8d; pbc
0x180037262  mov     rdx, [rbp+pidl]; pidl
0x180037266  xor     ecx, ecx; psf
0x180037268  call    cs:__imp_SHBindToObject
0x18003726e  mov     edi, eax
0x180037270  test    eax, eax
0x180037272  js      short loc_1800372D0
0x180037274  lea     rcx, [rbp+arg_10]; void *
0x180037278  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003727d  nop
0x18003727e  mov     rcx, [rbp+arg_8]
0x180037282  mov     rax, [rcx]
0x180037285  lea     r9, [rbp+arg_10]
0x180037289  xor     edx, edx
0x18003728b  lea     r8d, [rdx+60h]
0x18003728f  mov     rax, [rax+20h]
0x180037293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037298  mov     edi, eax
0x18003729a  test    eax, eax
0x18003729c  jnz     short loc_1800372C6
0x18003729e  mov     r9, [rbp+arg_10]; struct IEnumIDList *
0x1800372a2  mov     r8, [rbp+arg_8]; struct IShellFolder *
0x1800372a6  mov     rdx, [rsi+88h]; unsigned __int16 *
0x1800372ad  mov     rcx, rsi; this
0x1800372b0  call    ?_PopulateCache@CStartMenuPathCompleteRowset@@AEAAJPEBGPEAUIShellFolder@@PEAUIEnumIDList@@@Z; CStartMenuPathCompleteRowset::_PopulateCache(ushort const *,IShellFolder *,IEnumIDList *)
0x1800372b5  mov     edi, eax
0x1800372b7  test    eax, eax
0x1800372b9  js      short loc_1800372C6
0x1800372bb  mov     rcx, [rsi+18h]; struct IUnknown *
0x1800372bf  call    ?QueryContinueOnSite@@YAJPEAUIUnknown@@@Z; QueryContinueOnSite(IUnknown *)
0x1800372c4  mov     edi, eax
0x1800372c6  lea     rcx, [rbp+arg_10]
0x1800372ca  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800372cf  nop
0x1800372d0  lea     rcx, [rbp+arg_8]
0x1800372d4  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800372d9  nop
0x1800372da  lea     rcx, [rbp+pidl]; void *
0x1800372de  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800372e3  nop
0x1800372e4  lea     rcx, [rbp+arg_0]
0x1800372e8  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800372ed  test    edi, edi
0x1800372ef  js      loc_18003745B
0x1800372f5  xor     r15d, r15d
0x1800372f8  mov     rax, [rsi+0A8h]
0x1800372ff  mov     rcx, [rax+18h]
0x180037303  test    rcx, rcx
0x180037306  jz      short loc_18003730D
0x180037308  mov     r14d, [rcx]
0x18003730b  jmp     short loc_180037310
0x18003730d  xor     r14d, r14d
0x180037310  lea     rcx, [rbp+arg_10]; void *
0x180037314  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x180037319  nop
0x18003731a  mov     rcx, [rsi+80h]
0x180037321  test    rcx, rcx
0x180037324  jz      short loc_180037342
0x180037326  mov     rax, [rcx]
0x180037329  lea     rdx, [rbp+arg_10]
0x18003732d  mov     rax, [rax+70h]
0x180037331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037336  mov     edi, eax
0x180037338  test    eax, eax
0x18003733a  js      loc_18003744D
0x180037340  jmp     short loc_180037344
0x180037342  xor     edi, edi
0x180037344  movsxd  rdx, dword ptr [rsi+0B0h]
0x18003734b  cmp     edx, r14d
0x18003734e  jnb     loc_180037448
0x180037354  lea     rcx, [rbp+arg_8]; void *
0x180037358  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x18003735d  nop
0x18003735e  mov     [rbp+arg_8], 0
0x180037366  mov     edi, 80004005h
0x18003736b  mov     rcx, [rsi+0A8h]
0x180037372  mov     rcx, [rcx+18h]; hdpa
0x180037376  call    cs:g_pfn_DPA_GetPtr
0x18003737c  mov     r9, rax
0x18003737f  test    rax, rax
0x180037382  jz      short loc_18003739F
0x180037384  mov     rcx, [rax]
0x180037387  mov     rax, [rcx]
0x18003738a  lea     r8, [rbp+arg_8]
0x18003738e  lea     rdx, _GUID_3017056d_9a91_4e90_937d_746c72abbf4f
0x180037395  mov     rcx, r9
0x180037398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003739d  mov     edi, eax
0x18003739f  test    edi, edi
0x1800373a1  js      loc_180037437
0x1800373a7  inc     dword ptr [rsi+0B0h]
0x1800373ad  xor     eax, eax
0x1800373af  mov     rbx, [rbp+arg_10]
0x1800373b3  test    rbx, rbx
0x1800373b6  setz    al
0x1800373b9  mov     dword ptr [rbp+arg_0], eax
0x1800373bc  test    eax, eax
0x1800373be  jnz     short loc_1800373F9
0x1800373c0  xor     edx, edx; Val
0x1800373c2  lea     r8d, [rax+48h]; Size
0x1800373c6  lea     rcx, [rbp+var_50]; void *
0x1800373ca  call    memset_0
0x1800373cf  mov     ecx, 1
0x1800373d4  mov     [rbp+var_40], ecx
0x1800373d7  mov     rax, [rbp+arg_8]
0x1800373db  mov     [rbp+var_50], rax
0x1800373df  mov     [rbp+var_48], rbx
0x1800373e3  mov     [rbp+var_18], ecx
0x1800373e6  lea     rdx, [rbp+arg_0]; int *
0x1800373ea  lea     rcx, [rbp+var_50]; struct CONDITIONEVALINFO *
0x1800373ee  call    ?GrepDoesItemMatchCondition@@YAJPEBUCONDITIONEVALINFO@@PEAHPEAUCONDITIONEVALPROPS@@@Z; GrepDoesItemMatchCondition(CONDITIONEVALINFO const *,int *,CONDITIONEVALPROPS *)
0x1800373f3  cmp     dword ptr [rbp+arg_0], 0
0x1800373f7  jz      short loc_180037437
0x1800373f9  mov     dword ptr [rbp+arg_0], 0
0x180037400  lea     rcx, [rsi+90h]
0x180037407  lea     r8, [rbp+arg_0]
0x18003740b  mov     rdx, [rbp+arg_8]
0x18003740f  call    ?AppendPtr@?$CDPA_Base@UIPropertyStoreCache@@V?$CTContainer_PolicyUnOwned@UIPropertyStoreCache@@@@@@QEAAJPEAUIPropertyStoreCache@@PEAH@Z; CDPA_Base<IPropertyStoreCache,CTContainer_PolicyUnOwned<IPropertyStoreCache>>::AppendPtr(IPropertyStoreCache *,int *)
0x180037414  mov     edi, eax
0x180037416  test    eax, eax
0x180037418  js      short loc_180037437
0x18003741a  mov     rcx, [rbp+arg_8]
0x18003741e  mov     rax, [rcx]
0x180037421  mov     rax, [rax+8]
0x180037425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003742a  mov     eax, dword ptr [rbp+arg_0]
0x18003742d  mov     [r12], eax
0x180037431  mov     r15d, 1
0x180037437  lea     rcx, [rbp+arg_8]
0x18003743b  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x180037440  test    edi, edi
0x180037442  jns     loc_180037344
0x180037448  test    r15d, r15d
0x18003744b  jnz     short loc_180037452
0x18003744d  mov     edi, 80004005h
0x180037452  lea     rcx, [rbp+arg_10]
0x180037456  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18003745b  mov     rcx, [rsi+0A8h]
0x180037462  mov     rcx, [rcx+10h]; hMutex
0x180037466  call    cs:__imp_ReleaseMutex
0x18003746c  mov     rcx, [rsi+0A8h]; this
0x180037473  call    ?Release@CStartMenuPathCompleteQueryCache@@UEAAKXZ; CStartMenuPathCompleteQueryCache::Release(void)
0x180037478  mov     eax, edi
0x18003747a  add     rsp, 80h
0x180037481  pop     r15
0x180037483  pop     r14
0x180037485  pop     r12
0x180037487  pop     rdi
0x180037488  pop     rsi
0x180037489  pop     rbx
0x18003748a  pop     rbp
0x18003748b  retn
```
