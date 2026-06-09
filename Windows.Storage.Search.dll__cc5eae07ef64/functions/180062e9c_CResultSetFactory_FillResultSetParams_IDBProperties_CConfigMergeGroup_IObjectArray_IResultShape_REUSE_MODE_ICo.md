# CResultSetFactory::_FillResultSetParams(IDBProperties *,CConfigMergeGroup *,IObjectArray *,IResultShape *,REUSE_MODE,ICondition2 *,IRowset *,QUERY_RESULT_TYPE,IServiceProvider *,CResultSetParams *,FORCE_RESULT_TYPE,IIndexerExternalDataSource *)

- ea: `0x180062e9c`
- end: `0x180063815`
- name: `?_FillResultSetParams@CResultSetFactory@@AEAAJPEAUIDBProperties@@PEAVCConfigMergeGroup@@PEAUIObjectArray@@PEAUIResultShape@@W4REUSE_MODE@@PEAUICondition2@@PEAUIRowset@@W4QUERY_RESULT_TYPE@@PEAUIServiceProvider@@PEAVCResultSetParams@@W4FORCE_RESULT_TYPE@@PEAUIIndexerExternalDataSource@@@Z`
- size: `2425`
- prototype: `__int64 __fastcall(__int64, struct IDBProperties *, __int64, void *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), unsigned int, struct ICondition *, struct IRowset *, int, IUnknown *punkSite, struct CResultSetParams *, __int64, struct IIndexerExternalDataSource *)`
- caller_count: `2`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180062d00`
- `0x1800a6440`

## callees

- `0x180006ca8`
- `0x18001d7f8`
- `0x18001db40`
- `0x18003986c`
- `0x18004d56c`
- `0x18004dc68`
- `0x18004f710`
- `0x180051a5c`
- `0x18005493c`
- `0x18005525c`
- `0x180057b18`
- `0x180059c1c`
- `0x180062160`
- `0x180062e9c`
- `0x180063a68`
- `0x180063f24`
- `0x1800647ec`
- `0x180070088`
- `0x180070f08`
- `0x180071dc0`
- `0x1800a0e94`
- `0x1800a28b8`
- `0x1800a32e0`
- `0x1800a3770`
- `0x1800a4f40`
- `0x1800aa890`
- `0x1800ad134`
- `0x1800ad9e4`
- `0x1800adc4c`
- `0x1800b0fa4`
- `0x1800b57f0`
- `0x1800b5924`
- `0x1800b599c`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x180062f65`
- `SHCORE!IUnknown_SetSite` at `0x180063274`
- `SHCORE!IUnknown_SetSite` at `0x1800635bd`
- `SHCORE!IUnknown_SetSite` at `0x1800637bb`
- `SHCORE!IUnknown_SetSite` at `0x180062f65`
- `SHCORE!IUnknown_SetSite` at `0x180063274`
- `SHCORE!IUnknown_SetSite` at `0x1800635bd`
- `SHCORE!IUnknown_SetSite` at `0x1800637bb`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800630f3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800630f3`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x18006310c`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHStringFromGUIDW` at `0x18006310c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CResultSetFactory::_FillResultSetParams(
        __int64 a1,
        struct IDBProperties *a2,
        __int64 a3,
        void *a4,
        __int64 (__fastcall ***a5)(_QWORD, GUID *, __int64 *),
        unsigned int a6,
        struct ICondition *a7,
        struct IRowset *a8,
        int a9,
        IUnknown *punkSite,
        struct CResultSetParams *a11,
        __int64 a12,
        struct IIndexerExternalDataSource *a13)
{
  int v15; // eax
  int v16; // esi
  int v17; // ebx
  int v18; // edi
  int v19; // eax
  const unsigned __int16 *v20; // rbx
  struct IUnknown *v21; // rdi
  int v22; // eax
  int ContinueOnSite; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  struct IUnknownVtbl *lpVtbl; // rax
  struct IUnknownVtbl *v27; // rax
  int v28; // eax
  struct CResultSetParams *v29; // rbx
  int v30; // eax
  int v31; // eax
  wil::details::in1diag3 *v32; // rcx
  __int64 v33; // rdx
  int v34; // eax
  wil::details::in1diag3 *v35; // rcx
  __int64 v36; // rdx
  CResultSetFactory *v37; // rcx
  int SortType; // eax
  __int64 v39; // rdx
  __int64 v40; // rdi
  int (__fastcall *v41)(__int64, GUID *, struct IRowset **); // rbx
  int v42; // eax
  int v44; // [rsp+20h] [rbp-E0h]
  GUID *p_pguid; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  struct IRowset *v47; // [rsp+28h] [rbp-D8h]
  const struct _GUID *v48; // [rsp+60h] [rbp-A0h]
  IUnknown *v49; // [rsp+70h] [rbp-90h] BYREF
  struct IRowset *v50; // [rsp+78h] [rbp-88h] BYREF
  int v51; // [rsp+80h] [rbp-80h] BYREF
  int v52[2]; // [rsp+88h] [rbp-78h] BYREF
  struct IRowset *v53; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v54; // [rsp+98h] [rbp-68h]
  unsigned int v55; // [rsp+9Ch] [rbp-64h]
  struct IResultShape *v56; // [rsp+A0h] [rbp-60h]
  __int64 v57; // [rsp+A8h] [rbp-58h] BYREF
  IUnknown *punk; // [rsp+B0h] [rbp-50h] BYREF
  int v59; // [rsp+B8h] [rbp-48h]
  struct CResultSetParams *v60; // [rsp+C0h] [rbp-40h]
  struct ICondition *v61; // [rsp+C8h] [rbp-38h] BYREF
  struct ICondition *v62; // [rsp+D0h] [rbp-30h] BYREF
  struct ICondition *v63; // [rsp+D8h] [rbp-28h]
  __int64 v64; // [rsp+E0h] [rbp-20h]
  IUnknown *v65; // [rsp+E8h] [rbp-18h]
  void *TokenHandle[2]; // [rsp+F0h] [rbp-10h] BYREF
  GUID pguid; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v68[42]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v69[42]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v70[80]; // [rsp+3B0h] [rbp+2B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+458h] [rbp+358h]

  TokenHandle[0] = a4;
  v53 = a8;
  v65 = punkSite;
  v60 = a11;
  v51 = 0;
  punk = 0;
  v15 = CResultSetFactory::_CreateSession(
          (CResultSetFactory *)a1,
          (const struct _GUID *)a3,
          a2,
          (struct IServiceProvider *)punkSite,
          (enum PROVIDER_CAPABILITIES *)&v51,
          (const struct _GUID *)v47,
          &punk);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x28FD,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v15,
      v44);
LABEL_82:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29C6,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v16,
      (int)p_pguid);
    return (unsigned int)v16;
  }
  IUnknown_SetSite(punk, punkSite);
  v54 = 0;
  v52[0] = 0;
  v17 = 0;
  LODWORD(v50) = 0;
  v57 = 0;
  v63 = a7;
  v64 = 0;
  if ( *(_QWORD *)(a3 + 48) )
  {
    v16 = (**a5)(a5, &GUID_6bc63938_8254_4965_9680_565933185060, &v57);
  }
  else
  {
    v44 = v51 & 0x80;
    v16 = CResultSetFactory::_AdjustShapeForStack(a1, a5, a6, v52);
    v54 = v52[0];
    v17 = (int)v50;
  }
  if ( v16 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2907,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v16,
      v44);
    goto LABEL_81;
  }
  v18 = CResultSetFactory::_AdjustCapabilites(a1, v57, (unsigned int)v51);
  v59 = v18;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54259651>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54259651>::GetImpl'::`2'::impl)
    && a13
    && (*(_QWORD *)a3 != *(_QWORD *)&GUID_b4fb0684_6315_4210_97de_a4ec1ccffcf6.Data1
     || *(_QWORD *)(a3 + 8) != *(_QWORD *)GUID_b4fb0684_6315_4210_97de_a4ec1ccffcf6.Data4) )
  {
    LODWORD(v50) = v17 | 0x10;
  }
  v55 = 0;
  v56 = 0;
  v63 = 0;
  v19 = CResultSetFactory::_AdjustShape(a1, v57, *(_QWORD *)(a3 + 48) != 0, &PKEY_Null);
  v16 = v19;
  if ( v19 >= 0 )
  {
    v20 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57984070>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57984070>::GetImpl'::`2'::impl) )
    {
      pguid = 0;
      if ( CoCreateGuid(&pguid) >= 0 )
      {
        SHStringFromGUIDW(&pguid, v70, 39);
        v20 = (const unsigned __int16 *)v70;
      }
    }
    v49 = 0;
    v62 = 0;
    v61 = 0;
    v51 = 0;
    v21 = v65;
    v22 = CResultSetFactory::_CreateCommand(
            (CResultSetFactory *)a1,
            (struct IDBCreateCommand *)punk,
            (struct CConfigMergeGroup *)a3,
            v56,
            a7,
            v53,
            (struct IServiceProvider *)v65,
            (enum QUERY_RESULT_SET_FLAGS *)&v50,
            v20,
            (enum QUERY_RESULT_SET_FLAGS *)&v51,
            &v62,
            &v61,
            v48,
            (void **)&v49);
    v16 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x292A,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
        (const char *)(unsigned int)v22,
        (int)p_pguid);
LABEL_79:
      (*(void (__fastcall **)(struct IResultShape *))(*(_QWORD *)v56 + 16LL))(v56);
      ((void (__fastcall *)(struct ICondition *))v63->lpVtbl->Release)(v63);
      goto LABEL_80;
    }
    ContinueOnSite = QueryContinueOnSite(v21);
    v16 = ContinueOnSite;
    if ( ContinueOnSite < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x292D,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
        (const char *)(unsigned int)ContinueOnSite,
        (int)p_pguid);
LABEL_76:
      SafeRelease<IShellItemArray>(&v61);
      SafeRelease<IShellItemArray>(&v62);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58637795>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58637795>::GetImpl'::`2'::impl) )
        CResultSetFactory::ClearCurrentCommand((CResultSetFactory *)(a1 + 8), v49);
      ((void (__fastcall *)(IUnknown *))v49->lpVtbl->Release)(v49);
      goto LABEL_79;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl)
      && a13 )
    {
      *(_QWORD *)v52 = 0;
      lpVtbl = v49->lpVtbl;
      *(_QWORD *)v52 = 0;
      if ( ((int (__fastcall *)(IUnknown *, GUID *, int *))lpVtbl->QueryInterface)(
             v49,
             &GUID_d6b569b3_a806_48fb_bffd_97972516917c,
             v52) >= 0 )
        (*(void (__fastcall **)(_QWORD, struct IIndexerExternalDataSource *))(**(_QWORD **)v52 + 24LL))(
          *(_QWORD *)v52,
          a13);
      wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(v52);
    }
    *(_QWORD *)&pguid.Data1 = 0;
    v50 = 0;
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
      McTemplateU0jq_EtwEventWriteTransfer(v25, v24, a3, v53 != 0);
    IUnknown_SetSite(v49, v21);
    wil::ActivityBase<FileExplorerLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v69);
    v69[0] = &ResultSetFactoryTelemetry::RSF_CommandExecute::`vftable';
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57984070>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57984070>::GetImpl'::`2'::impl) )
    {
      wil::ActivityBase<FileExplorerLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v68);
      v68[0] = &ResultSetFactoryTelemetry::RSF_CommandExecute::`vftable';
      ResultSetFactoryTelemetry::RSF_CommandExecute::StartActivity(
        (ResultSetFactoryTelemetry::RSF_CommandExecute *)v68,
        v20,
        (const char *)(a1 + 88));
      ResultSetFactoryTelemetry::RSF_CommandExecute::operator=(v69, v68);
      ResultSetFactoryTelemetry::RSF_CommandExecute::~RSF_CommandExecute((ResultSetFactoryTelemetry::RSF_CommandExecute *)v68);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
    {
      FileExplorerTelemetry::QueryCommandExecute<_GUID const &>(a3);
      v53 = 0;
      v27 = v49->lpVtbl;
      v53 = 0;
      v16 = ((__int64 (__fastcall *)(IUnknown *, GUID *, struct IRowset **))v27->QueryInterface)(
              v49,
              &GUID_0d96fc4e_2ee9_47a4_9459_67771ad57ba3,
              &v53);
      if ( v16 >= 0 )
      {
        v52[0] = 0;
        v28 = ((__int64 (__fastcall *)(struct IRowset *, int *))v53->lpVtbl->AddRefRows)(v53, v52);
        v16 = v28;
        if ( v28 >= 0 )
        {
          if ( (v52[0] & 4) != 0 )
          {
            v29 = v60;
            v30 = CResultSetFactory::ExecuteOrReuseCloudCommand(
                    (CResultSetFactory *)a1,
                    (struct IObjectArray *)TokenHandle[0],
                    (struct IServiceProvider *)v21,
                    a13,
                    (struct ICommand *)v49,
                    v60);
            v16 = v30;
            if ( v30 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x2958,
                (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
                (const char *)(unsigned int)v30,
                (int)p_pguid);
            goto LABEL_48;
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2955,
            (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
            (const char *)(unsigned int)v28,
            (int)p_pguid);
        }
      }
      CImpersonateToken::CImpersonateToken(TokenHandle, *(HANDLE *)(a1 + 320));
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58637795>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58637795>::GetImpl'::`2'::impl) )
      {
        if ( CResultSetFactory::IsCancellationRequested((CResultSetFactory *)a1) )
        {
          v16 = -2147023673;
LABEL_47:
          CImpersonateToken::~CImpersonateToken((CImpersonateToken *)TokenHandle);
          v29 = v60;
LABEL_48:
          wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(&v53);
LABEL_58:
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57984070>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57984070>::GetImpl'::`2'::impl) )
            ResultSetFactoryTelemetry::RSF_CommandExecute::Stop(
              (ResultSetFactoryTelemetry::RSF_CommandExecute *)v69,
              (const char *)(a1 + 88));
          IUnknown_SetSite(v49, 0);
          if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
            McTemplateU0j_EtwEventWriteTransfer(v37, DataLayer_CommandExecute_Stop, a3);
          if ( v16 < 0 )
          {
            v53 = 0;
            v40 = *(_QWORD *)(a1 + 416);
            v41 = *(int (__fastcall **)(__int64, GUID *, struct IRowset **))(*(_QWORD *)v40 + 32LL);
            Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v53);
            if ( v41(v40, &GUID_180086f7_d0dc_44db_85bc_1b8146f75963, &v53) >= 0 )
            {
              v42 = ((__int64 (__fastcall *)(struct IRowset *, IUnknown *, _QWORD))v53->lpVtbl->AddRefRows)(
                      v53,
                      v65,
                      (unsigned int)v16);
              if ( v42 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x29B2,
                  (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
                  (const char *)(unsigned int)v42,
                  (int)p_pguid);
            }
            Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v53);
          }
          else
          {
            v52[0] = 0;
            SortType = CResultSetFactory::_GetSortType(
                         v37,
                         v56,
                         v50,
                         (struct IServiceProvider *)v21,
                         (enum PROVIDER_SORT_TYPE *)v52);
            v16 = SortType;
            if ( SortType >= 0 )
            {
              v39 = v54;
              if ( a9 == 2 )
                v39 = 1;
              LODWORD(p_pguid) = v59;
              v16 = CResultSetParams::InitializeSetParams(v29, v39, v55, (unsigned int)v51);
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x299D,
                (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
                (const char *)(unsigned int)SortType,
                v46);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl'::`2'::impl) )
              SafeRelease<IShellItemArray>(&v50);
            else
              ((void (__fastcall *)(struct IRowset *))v50->lpVtbl->Release)(v50);
          }
          ResultSetFactoryTelemetry::RSF_CommandExecute::~RSF_CommandExecute((ResultSetFactoryTelemetry::RSF_CommandExecute *)v69);
          goto LABEL_76;
        }
        CResultSetFactory::SetCurrentCommand((CResultSetFactory *)a1, (struct ICommand *)v49);
        if ( v16 < 0 )
          goto LABEL_47;
        p_pguid = &pguid;
        v31 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, GUID *, _QWORD))v49->lpVtbl[1].AddRef)(
                v49,
                0,
                &IID_IRowset,
                0);
        v16 = v31;
        v32 = retaddr;
        if ( v31 >= 0 )
          goto LABEL_47;
        v33 = 10605;
      }
      else
      {
        p_pguid = &pguid;
        v31 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, GUID *, _QWORD))v49->lpVtbl[1].AddRef)(
                v49,
                0,
                &IID_IRowset,
                0);
        v16 = v31;
        v32 = retaddr;
        if ( v31 >= 0 )
          goto LABEL_47;
        v33 = 10610;
      }
      wil::details::in1diag3::_Log_Hr(
        v32,
        (void *)v33,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
        (const char *)(unsigned int)v31,
        (int)&pguid);
      goto LABEL_47;
    }
    CImpersonateToken::CImpersonateToken(TokenHandle, *(HANDLE *)(a1 + 320));
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58637795>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58637795>::GetImpl'::`2'::impl) )
    {
      if ( CResultSetFactory::IsCancellationRequested((CResultSetFactory *)a1) )
      {
        v16 = -2147023673;
LABEL_57:
        CImpersonateToken::~CImpersonateToken((CImpersonateToken *)TokenHandle);
        v29 = v60;
        goto LABEL_58;
      }
      CResultSetFactory::SetCurrentCommand((CResultSetFactory *)a1, (struct ICommand *)v49);
      p_pguid = &pguid;
      v34 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, GUID *, _QWORD))v49->lpVtbl[1].AddRef)(v49, 0, &IID_IRowset, 0);
      v16 = v34;
      v35 = retaddr;
      if ( v34 >= 0 )
        goto LABEL_57;
      v36 = 10631;
    }
    else
    {
      p_pguid = &pguid;
      v34 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, GUID *, _QWORD))v49->lpVtbl[1].AddRef)(v49, 0, &IID_IRowset, 0);
      v16 = v34;
      v35 = retaddr;
      if ( v34 >= 0 )
        goto LABEL_57;
      v36 = 10636;
    }
    wil::details::in1diag3::_Log_Hr(
      v35,
      (void *)v36,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v34,
      (int)&pguid);
    goto LABEL_57;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x2918,
    (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
    (const char *)(unsigned int)v19,
    v18);
LABEL_80:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
LABEL_81:
  IUnknown_SetSite(punk, 0);
  ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
  if ( v16 < 0 )
    goto LABEL_82;
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180062e9c  push    rbp
0x180062e9e  push    rbx
0x180062e9f  push    rsi
0x180062ea0  push    rdi
0x180062ea1  push    r12
0x180062ea3  push    r13
0x180062ea5  push    r14
0x180062ea7  push    r15
0x180062ea9  lea     rbp, [rsp-318h]
0x180062eb1  sub     rsp, 418h
0x180062eb8  mov     rax, cs:__security_cookie
0x180062ebf  xor     rax, rsp
0x180062ec2  mov     [rbp+350h+var_50], rax
0x180062ec9  mov     [rbp+350h+TokenHandle], r9
0x180062ecd  mov     r13, r8
0x180062ed0  mov     r14, rcx
0x180062ed3  mov     rdi, [rbp+350h+arg_20]
0x180062eda  mov     r15, [rbp+350h+arg_30]
0x180062ee1  mov     rax, [rbp+350h+arg_38]
0x180062ee8  mov     [rbp+350h+var_3C0], rax
0x180062eec  mov     rbx, [rbp+350h+punkSite]
0x180062ef3  mov     [rbp+350h+var_368], rbx
0x180062ef7  mov     rax, [rbp+350h+arg_50]
0x180062efe  mov     [rbp+350h+var_390], rax
0x180062f02  mov     r12, [rbp+350h+arg_60]
0x180062f09  mov     [rbp+350h+var_3D0], 0
0x180062f10  mov     [rbp+350h+punk], 0
0x180062f18  lea     rax, [rbp+350h+punk]
0x180062f1c  mov     [rsp+450h+var_420], rax; struct IUnknown **
0x180062f21  lea     rax, [rbp+350h+var_3D0]
0x180062f25  mov     [rsp+450h+var_430], rax; int
0x180062f2a  mov     r9, rbx; struct IServiceProvider *
0x180062f2d  mov     r8, rdx; struct IDBProperties *
0x180062f30  mov     rdx, r13; struct _GUID *
0x180062f33  call    ?_CreateSession@CResultSetFactory@@AEAAJAEBU_GUID@@PEAUIDBProperties@@PEAUIServiceProvider@@PEAW4PROVIDER_CAPABILITIES@@0PEAPEAUIUnknown@@@Z; CResultSetFactory::_CreateSession(_GUID const &,IDBProperties *,IServiceProvider *,PROVIDER_CAPABILITIES *,_GUID const &,IUnknown * *)
0x180062f38  mov     esi, eax
0x180062f3a  mov     rcx, [rbp+358h]; this
0x180062f41  test    eax, eax
0x180062f43  jns     short loc_180062F5E
0x180062f45  mov     r9d, eax; char *
0x180062f48  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x180062f4f  mov     edx, 28FDh; void *
0x180062f54  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180062f59  jmp     loc_1800637D5
0x180062f5e  mov     rdx, rbx; punkSite
0x180062f61  mov     rcx, [rbp+350h+punk]; punk
0x180062f65  call    cs:__imp_IUnknown_SetSite
0x180062f6b  xor     ecx, ecx
0x180062f6d  mov     [rbp+350h+var_3B8], ecx
0x180062f70  mov     [rbp+350h+var_3C8], ecx
0x180062f73  mov     ebx, ecx
0x180062f75  mov     dword ptr [rsp+450h+var_3D8], ecx
0x180062f79  mov     [rbp+350h+var_3A8], rcx
0x180062f7d  mov     [rbp+350h+var_378], r15
0x180062f81  mov     [rbp+350h+var_370], rcx
0x180062f85  cmp     [r13+30h], rcx
0x180062f89  jz      short loc_180062FA8
0x180062f8b  mov     rax, [rdi]
0x180062f8e  lea     r8, [rbp+350h+var_3A8]
0x180062f92  lea     rdx, _GUID_6bc63938_8254_4965_9680_565933185060
0x180062f99  mov     rcx, rdi
0x180062f9c  mov     rax, [rax]
0x180062f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062fa4  mov     esi, eax
0x180062fa6  jmp     short loc_180062FF2
0x180062fa8  mov     eax, [rbp+350h+var_3D0]
0x180062fab  and     eax, 80h
0x180062fb0  lea     rcx, [rbp+350h+var_3A8]
0x180062fb4  mov     [rsp+450h+var_410], rcx
0x180062fb9  lea     rcx, [rsp+450h+var_3D8]
0x180062fbe  mov     [rsp+450h+var_420], rcx
0x180062fc3  lea     rcx, [rbp+350h+var_378]
0x180062fc7  mov     [rsp+450h+var_428], rcx
0x180062fcc  mov     dword ptr [rsp+450h+var_430], eax; int
0x180062fd0  lea     r9, [rbp+350h+var_3C8]
0x180062fd4  mov     r8d, [rbp+350h+arg_28]
0x180062fdb  mov     rdx, rdi
0x180062fde  mov     rcx, r14
0x180062fe1  call    ?_AdjustShapeForStack@CResultSetFactory@@AEAAJPEAUIResultShape@@W4REUSE_MODE@@PEAHHPEBUCONDITIONDATA@1@PEAW4QUERY_RESULT_SET_FLAGS@@AEBU_GUID@@PEAPEAX@Z; CResultSetFactory::_AdjustShapeForStack(IResultShape *,REUSE_MODE,int *,int,CResultSetFactory::CONDITIONDATA const *,QUERY_RESULT_SET_FLAGS *,_GUID const &,void * *)
0x180062fe6  mov     esi, eax
0x180062fe8  mov     eax, [rbp+350h+var_3C8]
0x180062feb  mov     [rbp+350h+var_3B8], eax
0x180062fee  mov     ebx, dword ptr [rsp+450h+var_3D8]
0x180062ff2  mov     rcx, [rbp+358h]; this
0x180062ff9  test    esi, esi
0x180062ffb  jns     short loc_180063016
0x180062ffd  mov     r9d, esi; char *
0x180063000  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x180063007  mov     edx, 2907h; void *
0x18006300c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180063011  jmp     loc_1800637B5
0x180063016  mov     r8d, [rbp+350h+var_3D0]
0x18006301a  mov     rdx, [rbp+350h+var_3A8]
0x18006301e  mov     rcx, r14
0x180063021  call    ?_AdjustCapabilites@CResultSetFactory@@AEAA?AW4PROVIDER_CAPABILITIES@@PEAUIResultShape@@W42@@Z; CResultSetFactory::_AdjustCapabilites(IResultShape *,PROVIDER_CAPABILITIES)
0x180063026  mov     edi, eax
0x180063028  mov     [rbp+350h+var_398], eax
0x18006302b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54259651@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54259651@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54259651> `wil::Feature<__WilFeatureTraits_Feature_54259651>::GetImpl(void)'::`2'::impl
0x180063032  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54259651@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54259651>::__private_IsEnabled(void)
0x180063037  xor     edx, edx
0x180063039  test    al, al
0x18006303b  jz      short loc_180063063
0x18006303d  test    r12, r12
0x180063040  jz      short loc_180063063
0x180063042  mov     rcx, [r13+0]
0x180063046  cmp     rcx, qword ptr cs:_GUID_b4fb0684_6315_4210_97de_a4ec1ccffcf6.Data1
0x18006304d  jnz     short loc_18006305C
0x18006304f  mov     rax, [r13+8]
0x180063053  cmp     rax, qword ptr cs:_GUID_b4fb0684_6315_4210_97de_a4ec1ccffcf6.Data4
0x18006305a  jz      short loc_180063063
0x18006305c  or      ebx, 10h
0x18006305f  mov     dword ptr [rsp+450h+var_3D8], ebx
0x180063063  mov     [rbp+350h+var_3B4], edx
0x180063066  mov     [rbp+350h+var_3B0], rdx
0x18006306a  mov     [rbp+350h+var_378], rdx
0x18006306e  mov     r8d, edx
0x180063071  cmp     [r13+30h], rdx
0x180063075  setnz   r8b
0x180063079  lea     rax, [rbp+350h+var_378]
0x18006307d  mov     [rsp+450h+var_410], rax
0x180063082  lea     rax, [rbp+350h+var_3B0]
0x180063086  mov     [rsp+450h+var_418], rax
0x18006308b  lea     rax, [rbp+350h+var_3B4]
0x18006308f  mov     [rsp+450h+var_420], rax
0x180063094  mov     [rsp+450h+var_428], r15
0x180063099  mov     dword ptr [rsp+450h+var_430], edi; int
0x18006309d  lea     r9, PKEY_Null
0x1800630a4  mov     rdx, [rbp+350h+var_3A8]
0x1800630a8  mov     rcx, r14
0x1800630ab  call    ?_AdjustShape@CResultSetFactory@@AEAAJPEAUIResultShape@@HAEBU_tagpropertykey@@W4PROVIDER_CAPABILITIES@@PEAUICondition@@PEAHPEAPEAU2@5@Z; CResultSetFactory::_AdjustShape(IResultShape *,int,_tagpropertykey const &,PROVIDER_CAPABILITIES,ICondition *,int *,IResultShape * *,IResultShape * *)
0x1800630b0  mov     esi, eax
0x1800630b2  mov     rcx, [rbp+358h]; this
0x1800630b9  test    eax, eax
0x1800630bb  jns     short loc_1800630D6
0x1800630bd  mov     r9d, eax; char *
0x1800630c0  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x1800630c7  mov     edx, 2918h; void *
0x1800630cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800630d1  jmp     loc_1800637A5
0x1800630d6  xor     ebx, ebx
0x1800630d8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57984070@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57984070@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57984070> `wil::Feature<__WilFeatureTraits_Feature_57984070>::GetImpl(void)'::`2'::impl
0x1800630df  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57984070@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57984070>::__private_IsEnabled(void)
0x1800630e4  test    al, al
0x1800630e6  jz      short loc_180063119
0x1800630e8  xorps   xmm0, xmm0
0x1800630eb  movups  xmmword ptr [rbp+350h+pguid.Data1], xmm0
0x1800630ef  lea     rcx, [rbp+350h+pguid]; pguid
0x1800630f3  call    cs:__imp_CoCreateGuid
0x1800630f9  test    eax, eax
0x1800630fb  js      short loc_180063119
0x1800630fd  lea     r8d, [rbx+27h]
0x180063101  lea     rdx, [rbp+350h+var_A0]
0x180063108  lea     rcx, [rbp+350h+pguid]
0x18006310c  call    cs:__imp_SHStringFromGUIDW
0x180063112  lea     rbx, [rbp+350h+var_A0]
0x180063119  mov     [rsp+450h+var_3E0], 0
0x180063122  mov     [rbp+350h+var_380], 0
0x18006312a  mov     [rbp+350h+var_388], 0
0x180063132  mov     [rbp+350h+var_3D0], 0
0x180063139  lea     rax, [rsp+450h+var_3E0]
0x18006313e  mov     [rsp+450h+var_3E8], rax; void **
0x180063143  lea     rax, [rbp+350h+var_388]
0x180063147  mov     [rsp+450h+var_3F8], rax; struct ICondition **
0x18006314c  lea     rax, [rbp+350h+var_380]
0x180063150  mov     [rsp+450h+var_400], rax; struct ICondition **
0x180063155  lea     rax, [rbp+350h+var_3D0]
0x180063159  mov     [rsp+450h+var_408], rax; enum QUERY_RESULT_SET_FLAGS *
0x18006315e  mov     [rsp+450h+var_410], rbx; unsigned __int16 *
0x180063163  lea     rax, [rsp+450h+var_3D8]
0x180063168  mov     [rsp+450h+var_418], rax; enum QUERY_RESULT_SET_FLAGS *
0x18006316d  mov     rdi, [rbp+350h+var_368]
0x180063171  mov     [rsp+450h+var_420], rdi; struct IServiceProvider *
0x180063176  mov     rax, [rbp+350h+var_3C0]
0x18006317a  mov     [rsp+450h+var_428], rax; struct IRowset *
0x18006317f  mov     [rsp+450h+var_430], r15; int
0x180063184  mov     r9, [rbp+350h+var_3B0]; struct IResultShape *
0x180063188  mov     r8, r13; struct CConfigMergeGroup *
0x18006318b  mov     rdx, [rbp+350h+punk]; struct IDBCreateCommand *
0x18006318f  mov     rcx, r14; this
0x180063192  call    ?_CreateCommand@CResultSetFactory@@AEAAJPEAUIDBCreateCommand@@PEAVCConfigMergeGroup@@PEAUIResultShape@@PEAUICondition@@PEAUIRowset@@PEAUIServiceProvider@@PEAW4QUERY_RESULT_SET_FLAGS@@PEBG6PEAPEAU5@8AEBU_GUID@@PEAPEAX@Z; CResultSetFactory::_CreateCommand(IDBCreateCommand *,CConfigMergeGroup *,IResultShape *,ICondition *,IRowset *,IServiceProvider *,QUERY_RESULT_SET_FLAGS *,ushort const *,QUERY_RESULT_SET_FLAGS *,ICondition * *,ICondition * *,_GUID const &,void * *)
0x180063197  mov     esi, eax
0x180063199  mov     rcx, [rbp+358h]; this
0x1800631a0  xor     r15d, r15d
0x1800631a3  test    eax, eax
0x1800631a5  jns     short loc_1800631C0
0x1800631a7  mov     r9d, eax; char *
0x1800631aa  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x1800631b1  mov     edx, 292Ah; void *
0x1800631b6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800631bb  jmp     loc_180063785
0x1800631c0  mov     rcx, rdi; struct IUnknown *
0x1800631c3  call    ?QueryContinueOnSite@@YAJPEAUIUnknown@@@Z; QueryContinueOnSite(IUnknown *)
0x1800631c8  mov     esi, eax
0x1800631ca  mov     rcx, [rbp+358h]; this
0x1800631d1  test    eax, eax
0x1800631d3  jns     short loc_1800631EE
0x1800631d5  mov     r9d, eax; char *
0x1800631d8  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x1800631df  mov     edx, 292Dh; void *
0x1800631e4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800631e9  jmp     loc_180063744
0x1800631ee  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45690266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266> `wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl(void)'::`2'::impl
0x1800631f5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(void)
0x1800631fa  test    al, al
0x1800631fc  jz      short loc_180063247
0x1800631fe  test    r12, r12
0x180063201  jz      short loc_180063247
0x180063203  mov     qword ptr [rbp+350h+var_3C8], r15
0x180063207  mov     rcx, [rsp+450h+var_3E0]
0x18006320c  mov     rax, [rcx]
0x18006320f  mov     qword ptr [rbp+350h+var_3C8], r15
0x180063213  lea     r8, [rbp+350h+var_3C8]
0x180063217  lea     rdx, _GUID_d6b569b3_a806_48fb_bffd_97972516917c
0x18006321e  mov     rax, [rax]
0x180063221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063226  test    eax, eax
0x180063228  js      short loc_18006323E
0x18006322a  mov     rcx, qword ptr [rbp+350h+var_3C8]
0x18006322e  mov     rax, [rcx]
0x180063231  mov     rdx, r12
0x180063234  mov     rax, [rax+18h]
0x180063238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006323d  nop
0x18006323e  lea     rcx, [rbp+350h+var_3C8]
0x180063242  call    ??1?$com_ptr_t@UIInitializeSortColumnArray@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>::~com_ptr_t<IInitializeSortColumnArray,wil::err_exception_policy>(void)
0x180063247  mov     qword ptr [rbp+350h+pguid.Data1], r15
0x18006324b  mov     [rsp+450h+var_3D8], r15
0x180063250  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180063257  jz      short loc_18006326C
0x180063259  mov     r9d, r15d
0x18006325c  cmp     [rbp+350h+var_3C0], r15
0x180063260  setnz   r9b
0x180063264  mov     r8, r13
0x180063267  call    McTemplateU0jq_EtwEventWriteTransfer
0x18006326c  mov     rdx, rdi; punkSite
0x18006326f  mov     rcx, [rsp+450h+var_3E0]; punk
0x180063274  call    cs:__imp_IUnknown_SetSite
0x18006327a  lea     rcx, [rbp+350h+var_1F0]; struct wil::details::IFailureCallback *
0x180063281  call    ??0?$ActivityBase@VFileExplorerLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FileExplorerLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180063286  lea     rsi, ??_7RSF_CommandExecute@ResultSetFactoryTelemetry@@6B@; const ResultSetFactoryTelemetry::RSF_CommandExecute::`vftable'
0x18006328d  mov     [rbp+350h+var_1F0], rsi
0x180063294  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57984070@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57984070@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57984070> `wil::Feature<__WilFeatureTraits_Feature_57984070>::GetImpl(void)'::`2'::impl
0x18006329b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57984070@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57984070>::__private_IsEnabled(void)
0x1800632a0  test    al, al
0x1800632a2  jz      short loc_1800632DB
0x1800632a4  lea     rcx, [rbp+350h+var_340]; struct wil::details::IFailureCallback *
0x1800632a8  call    ??0?$ActivityBase@VFileExplorerLogging@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<FileExplorerLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800632ad  mov     [rbp+350h+var_340], rsi
0x1800632b1  lea     r8, [r14+58h]; char *
0x1800632b5  mov     rdx, rbx; unsigned __int16 *
0x1800632b8  lea     rcx, [rbp+350h+var_340]; this
0x1800632bc  call    ?StartActivity@RSF_CommandExecute@ResultSetFactoryTelemetry@@QEAAXPEBGPEBD@Z; ResultSetFactoryTelemetry::RSF_CommandExecute::StartActivity(ushort const *,char const *)
0x1800632c1  nop
0x1800632c2  lea     rdx, [rbp+350h+var_340]
0x1800632c6  lea     rcx, [rbp+350h+var_1F0]
0x1800632cd  call    ??4RSF_CommandExecute@ResultSetFactoryTelemetry@@QEAAAEAV01@$$QEAV01@@Z; ResultSetFactoryTelemetry::RSF_CommandExecute::operator=(ResultSetFactoryTelemetry::RSF_CommandExecute &&)
0x1800632d2  lea     rcx, [rbp+350h+var_340]; this
0x1800632d6  call    ??1RSF_CommandExecute@ResultSetFactoryTelemetry@@QEAA@XZ; ResultSetFactoryTelemetry::RSF_CommandExecute::~RSF_CommandExecute(void)
0x1800632db  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI45690266@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266> `wil::Feature<__WilFeatureTraits_Feature_FI45690266>::GetImpl(void)'::`2'::impl
0x1800632e2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FI45690266@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI45690266>::__private_IsEnabled(void)
0x1800632e7  test    al, al
0x1800632e9  jz      loc_1800634AF
0x1800632ef  mov     rcx, r13
0x1800632f2  call    ??$QueryCommandExecute@AEBU_GUID@@@FileExplorerTelemetry@@SAXAEBU_GUID@@@Z; FileExplorerTelemetry::QueryCommandExecute<_GUID const &>(_GUID const &)
0x1800632f7  mov     [rbp+350h+var_3C0], r15
0x1800632fb  mov     rcx, [rsp+450h+var_3E0]
0x180063300  mov     rax, [rcx]
0x180063303  mov     [rbp+350h+var_3C0], r15
0x180063307  lea     r8, [rbp+350h+var_3C0]
0x18006330b  lea     rdx, _GUID_0d96fc4e_2ee9_47a4_9459_67771ad57ba3
0x180063312  mov     rax, [rax]
0x180063315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006331a  mov     esi, eax
0x18006331c  test    eax, eax
0x18006331e  js      short loc_180063359
0x180063320  mov     [rbp+350h+var_3C8], r15d
0x180063324  mov     rcx, [rbp+350h+var_3C0]
0x180063328  mov     rax, [rcx]
0x18006332b  lea     rdx, [rbp+350h+var_3C8]
0x18006332f  mov     rax, [rax+18h]
0x180063333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063338  mov     esi, eax
0x18006333a  mov     rcx, [rbp+358h]; this
0x180063341  test    eax, eax
0x180063343  jns     short loc_180063394
0x180063345  mov     r9d, eax; char *
0x180063348  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x18006334f  mov     edx, 2955h; void *
0x180063354  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180063359  mov     rdx, [r14+140h]; Token
0x180063360  lea     rcx, [rbp+350h+TokenHandle]; TokenHandle
0x180063364  call    ??0CImpersonateToken@@QEAA@PEAX@Z; CImpersonateToken::CImpersonateToken(void *)
0x180063369  nop
0x18006336a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58637795@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58637795@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58637795> `wil::Feature<__WilFeatureTraits_Feature_58637795>::GetImpl(void)'::`2'::impl
0x180063371  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58637795@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58637795>::__private_IsEnabled(void)
0x180063376  test    al, al
0x180063378  jz      loc_180063442
0x18006337e  mov     rcx, r14; this
0x180063381  call    ?IsCancellationRequested@CResultSetFactory@@AEAA_NXZ; CResultSetFactory::IsCancellationRequested(void)
0x180063386  test    al, al
  ... truncated ...
```
