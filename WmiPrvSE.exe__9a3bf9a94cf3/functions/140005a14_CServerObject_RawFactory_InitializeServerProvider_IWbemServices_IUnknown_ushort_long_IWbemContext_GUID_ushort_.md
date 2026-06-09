# CServerObject_RawFactory::InitializeServerProvider(IWbemServices *,IUnknown *,ushort *,long,IWbemContext *,_GUID *,ushort const *,ushort const *,ushort const *,_GUID const &,void * *,CServerObject_ProviderRegistrationV1 &)

- ea: `0x140005a14`
- end: `0x140006c5d`
- name: `?InitializeServerProvider@CServerObject_RawFactory@@QEAAJPEAUIWbemServices@@PEAUIUnknown@@PEAGJPEAUIWbemContext@@PEAU_GUID@@PEBG55AEBU5@PEAPEAXAEAVCServerObject_ProviderRegistrationV1@@@Z`
- size: `4681`
- prototype: `__int64 __fastcall(CServerObject_RawFactory *this, struct IWbemServices *, struct IServerSecurity *, unsigned __int16 *, int, struct IWbemContext *, GUID *rguid, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **, struct CServerObject_ProviderRegistrationV1 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140007698`

## callees

- `0x1400053dc`
- `0x1400058dc`
- `0x140005984`
- `0x140005a14`
- `0x140006c64`
- `0x140006d34`
- `0x140006d5c`
- `0x140006e0c`
- `0x140006eec`
- `0x14000a530`
- `0x14001b698`
- `0x14001ca74`
- `0x14001e00c`
- `0x14001ebc4`
- `0x1400234b8`
- `0x1400297bc`
- `0x14004612c`
- `0x140046430`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005e8e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005e8e`
- `NCObjAPI!WmiSetAndCommitObject` at `0x140005f07`
- `NCObjAPI!WmiSetAndCommitObject` at `0x1400060eb`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14000689f`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14000690d`
- `NCObjAPI!WmiSetAndCommitObject` at `0x140005f07`
- `NCObjAPI!WmiSetAndCommitObject` at `0x1400060eb`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14000689f`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14000690d`
- `wbemcomn!GetMemLogObject` at `0x140006c47`
- `wbemcomn!GetMemLogObject` at `0x140006c47`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140006c52`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140006c52`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400062c9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400062c9`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140005d0c`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140005d88`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1400061e2`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140006541`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140005d0c`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140005d88`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1400061e2`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140006541`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140006005`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400061f9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000626f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000654e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140006005`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400061f9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000626f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000654e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140005e74`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140006017`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000620c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400063be`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140006562`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400066e5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140005e74`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140006017`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000620c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400063be`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140006562`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400066e5`

## pseudocode

```c
__int64 __fastcall CServerObject_RawFactory::InitializeServerProvider(
        CServerObject_RawFactory *this,
        struct IWbemServices *a2,
        struct IServerSecurity *a3,
        unsigned __int16 *a4,
        int a5,
        struct IWbemContext *a6,
        GUID *rguid,
        const unsigned __int16 *a8,
        const unsigned __int16 *a9,
        const unsigned __int16 *a10,
        const struct _GUID *a11,
        void **a12,
        struct CServerObject_ProviderRegistrationV1 *a13)
{
  struct IServerSecurity *v13; // r12
  struct CServerObject_ProviderRegistrationV1 *v14; // r14
  CInterceptor_IWbemProviderInitSink *v15; // r15
  unsigned int v16; // r13d
  unsigned int v17; // eax
  int v18; // edi
  _QWORD *v19; // rcx
  struct IServerSecurity *v20; // rax
  struct _SECURITY_DESCRIPTOR *v21; // rdx
  CServerObject_ProviderInitSink *inited; // rax
  CServerObject_ProviderInitSink *v23; // r12
  int Instance; // edi
  struct IServerSecurity *v25; // rax
  CInterceptor_IWbemProviderInitSink *v26; // rsi
  struct IServerSecurity *v27; // rax
  struct _SECURITY_DESCRIPTOR *v28; // rdx
  struct IUnknown *v29; // rax
  struct IUnknown *v30; // r12
  struct IServerSecurity *v31; // rsi
  struct IServerSecurityVtbl *lpVtbl; // rcx
  int v33; // r15d
  struct IUnknown *v34; // rdx
  int v35; // r15d
  CInterceptor_IWbemProviderInitSink *v36; // r15
  bool v37; // cf
  unsigned __int16 *v39; // rdx
  unsigned __int16 *v40; // r8
  unsigned __int16 *v41; // r9
  int v42; // edx
  int v43; // edi
  unsigned int CurrentImpersonationLevel; // esi
  HRESULT v45; // edi
  HRESULT v46; // eax
  unsigned __int16 *v47; // rdx
  unsigned __int16 *v48; // r8
  unsigned __int16 *v49; // r9
  struct IUnknown *v50; // rdi
  unsigned int v51; // eax
  unsigned int v52; // edx
  unsigned int v53; // r15d
  int v54; // eax
  struct IServerSecurity *v55; // r15
  struct IUnknown *v56; // r15
  unsigned int v57; // eax
  unsigned int v58; // edx
  struct IUnknown *v59; // r13
  unsigned int v60; // eax
  unsigned int v61; // edx
  CMemoryLog *MemLogObject; // rax
  unsigned int v63; // [rsp+20h] [rbp-1D8h]
  unsigned int v64; // [rsp+28h] [rbp-1D0h]
  unsigned int v65; // [rsp+30h] [rbp-1C8h]
  int v66; // [rsp+38h] [rbp-1C0h]
  struct IUnknown *v67; // [rsp+50h] [rbp-1A8h] BYREF
  int v68; // [rsp+58h] [rbp-1A0h] BYREF
  int v69; // [rsp+5Ch] [rbp-19Ch] BYREF
  const unsigned __int16 *v70; // [rsp+60h] [rbp-198h]
  unsigned __int16 *v71; // [rsp+68h] [rbp-190h]
  struct IServerSecurity *v72; // [rsp+70h] [rbp-188h] BYREF
  __int64 v73; // [rsp+78h] [rbp-180h]
  const unsigned __int16 *v74; // [rsp+80h] [rbp-178h]
  struct IUnknown *v75; // [rsp+88h] [rbp-170h] BYREF
  CInterceptor_IWbemProviderInitSink *v76; // [rsp+90h] [rbp-168h] BYREF
  struct IWbemServices *v77; // [rsp+98h] [rbp-160h] BYREF
  struct IServerSecurity *v78; // [rsp+A0h] [rbp-158h] BYREF
  void *ppInterface; // [rsp+A8h] [rbp-150h] BYREF
  struct IWbemContext *v80; // [rsp+B0h] [rbp-148h]
  struct IWbemServices *v81; // [rsp+B8h] [rbp-140h]
  struct IUnknown *v82; // [rsp+C0h] [rbp-138h] BYREF
  struct IUnknown *v83; // [rsp+C8h] [rbp-130h] BYREF
  struct IServerSecurity *v84; // [rsp+D0h] [rbp-128h] BYREF
  struct CServerObject_ProviderRegistrationV1 *v85; // [rsp+D8h] [rbp-120h]
  const unsigned __int16 *v86; // [rsp+E0h] [rbp-118h]
  const unsigned __int16 *v87; // [rsp+E8h] [rbp-110h]
  unsigned __int16 *v88; // [rsp+F0h] [rbp-108h]
  GUID *v89; // [rsp+F8h] [rbp-100h]
  struct CServerObject_ProviderRegistrationV1 *v90; // [rsp+100h] [rbp-F8h]
  struct IUnknown *v91; // [rsp+108h] [rbp-F0h] BYREF
  OLECHAR sz[80]; // [rsp+110h] [rbp-E8h] BYREF

  v71 = a4;
  v13 = a3;
  v81 = a2;
  v74 = a8;
  v87 = a8;
  v70 = a9;
  v86 = a9;
  v77 = a2;
  v78 = a3;
  v88 = a4;
  v80 = a6;
  v73 = (__int64)rguid;
  v89 = rguid;
  v14 = a13;
  v90 = a13;
  v85 = a13;
  if ( rguid )
    StringFromGUID2(rguid, sz, 78);
  v15 = (struct CServerObject_ProviderRegistrationV1 *)((char *)a13 + 2176);
  v76 = (struct CServerObject_ProviderRegistrationV1 *)((char *)a13 + 2176);
  if ( *((_DWORD *)a13 + 544) )
  {
    v75 = 0;
    v43 = ((__int64 (__fastcall *)(struct IServerSecurity *, GUID *, struct IUnknown **))v13->lpVtbl->QueryInterface)(
            v13,
            &IID_IWbemProviderIdentity,
            &v75);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
        (unsigned int)v43);
    }
    if ( v43 >= 0 )
    {
      v69 = 0;
      v83 = 0;
      v72 = 0;
      if ( (int)ProviderSubSystem_Common_Globals::BeginImpersonation(&v83, &v72, &v69, 0) < 0 )
      {
        v16 = 3;
LABEL_103:
        ((void (__fastcall *)(struct IUnknown *))v75->lpVtbl->Release)(v75);
        goto LABEL_5;
      }
      v68 = 0;
      v67 = 0;
      ppInterface = 0;
      v16 = 3;
      if ( CoGetCallContext(&IID_IUnknown, &ppInterface) < 0 )
        goto LABEL_93;
      CurrentImpersonationLevel = 3;
      v45 = CoImpersonateClient();
      if ( v45 >= 0 )
      {
        CurrentImpersonationLevel = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
        CoRevertToSelf();
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
      if ( v45 < 0 )
        goto LABEL_95;
      if ( CurrentImpersonationLevel == 2 )
        v46 = ProviderSubSystem_Common_Globals::SetProxyState_NoImpersonation(
                &IID_IWbemProviderIdentity,
                v75,
                &v67,
                &v68);
      else
LABEL_93:
        v46 = ProviderSubSystem_Common_Globals::SetProxyState(&IID_IWbemProviderIdentity, v75, &v67, &v68);
      v45 = v46;
LABEL_95:
      if ( v45 == -2147217406 )
      {
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          ((void (__fastcall *)(struct IUnknown *, _QWORD, _QWORD))v75->lpVtbl[1].QueryInterface)(
            v75,
            0,
            *((_QWORD *)v85 + 226));
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &Wmi_Heap_Exception `RTTI Type Descriptor', 0) )
          {
            v16 = 3;
            v13 = v78;
            v70 = v86;
            v74 = v87;
            v81 = v77;
            v71 = v88;
            v73 = (__int64)v89;
            v14 = v90;
            v15 = v76;
            __eh34_try_continuation(0, &Wmi_Heap_Exception `RTTI Type Descriptor', &loc_140006359);
          }
        }
        CoRevertToSelf();
      }
      else if ( v45 >= 0 )
      {
        v50 = v67;
        v51 = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
        if ( (int)ProviderSubSystem_Common_Globals::SetCloaking(v50, v52, v51) >= 0 )
        {
          if ( __eh34_try(-1, 2) )
          {
            __eh34_scope_strut(2);
            ((void (__fastcall *)(struct IUnknown *, _QWORD, _QWORD))v50->lpVtbl[1].QueryInterface)(
              v50,
              0,
              *((_QWORD *)v85 + 226));
          }
          if ( __eh34_catch(2) )
          {
            if ( __eh34_catch_type(2, &Wmi_Heap_Exception `RTTI Type Descriptor', 0) )
            {
              v16 = 3;
              v13 = v78;
              v70 = v86;
              v74 = v87;
              v81 = v77;
              v71 = v88;
              v73 = (__int64)v89;
              v14 = v90;
              v15 = v76;
              __eh34_try_continuation(2, &Wmi_Heap_Exception `RTTI Type Descriptor', &loc_140006411);
            }
          }
        }
        ProviderSubSystem_Common_Globals::RevertProxyState(v67, v68);
      }
      ProviderSubSystem_Common_Globals::EndImpersonation(v83, v72, v69);
      goto LABEL_103;
    }
  }
  v16 = 3;
LABEL_5:
  v82 = 0;
  v17 = ((__int64 (__fastcall *)(struct IServerSecurity *, GUID *, struct IUnknown **))v13->lpVtbl->QueryInterface)(
          v13,
          &IID_IWbemProviderInit,
          &v82);
  v18 = v17;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids, v17);
    v19 = WPP_GLOBAL_Control;
  }
  if ( v18 < 0 )
  {
    if ( (*((_DWORD *)v14 + 532) || *((_DWORD *)v14 + 554))
      && !*((_DWORD *)v14 + 464)
      && !*((_DWORD *)v14 + 504)
      && !*((_DWORD *)v14 + 522)
      && !*(_DWORD *)v15 )
    {
      Instance = 0;
      goto LABEL_47;
    }
    Instance = -2147217389;
    goto LABEL_157;
  }
  v75 = (struct IUnknown *)((char *)v14 + 1656);
  if ( !*((_DWORD *)v14 + 414) || !*((_DWORD *)v14 + 413) )
    goto LABEL_15;
  v20 = (struct IServerSecurity *)operator new(0x28u);
  v84 = v20;
  if ( !v20 )
    goto LABEL_52;
  inited = CServerObject_ProviderInitSink::CServerObject_ProviderInitSink((CServerObject_ProviderInitSink *)v20, v21);
  v23 = inited;
  ppInterface = inited;
  if ( !inited )
    goto LABEL_52;
  (*(void (__fastcall **)(CServerObject_ProviderInitSink *))(*(_QWORD *)inited + 8LL))(inited);
  Instance = CServerObject_ProviderInitSink::SinkInitialize(v23, *((struct _SECURITY_DESCRIPTOR **)v14 + 230));
  if ( Instance >= 0 )
  {
    v25 = (struct IServerSecurity *)operator new(0x20u);
    v84 = v25;
    if ( v25 )
      v26 = CInterceptor_IWbemProviderInitSink::CInterceptor_IWbemProviderInitSink(
              (CInterceptor_IWbemProviderInitSink *)v25,
              (struct IWbemProviderInitSink *)v23);
    else
      v26 = 0;
    v76 = v26;
    if ( v26 )
    {
      (*(void (__fastcall **)(CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)v26 + 8LL))(v26);
      v69 = 0;
      v91 = 0;
      v78 = 0;
      Instance = ProviderSubSystem_Common_Globals::BeginImpersonation(&v91, &v78, &v69, 0);
      if ( Instance < 0 )
      {
LABEL_135:
        (*(void (__fastcall **)(CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)v26 + 16LL))(v26);
        goto LABEL_14;
      }
      LODWORD(v72) = 0;
      v67 = 0;
      v83 = 0;
      if ( CoGetCallContext(&IID_IUnknown, (void **)&v83) < 0 )
        goto LABEL_113;
      v53 = 3;
      Instance = CoImpersonateClient();
      if ( Instance >= 0 )
      {
        v53 = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
        CoRevertToSelf();
      }
      ((void (__fastcall *)(struct IUnknown *))v83->lpVtbl->Release)(v83);
      if ( Instance < 0 )
      {
LABEL_115:
        if ( Instance == -2147217406 )
        {
          if ( __eh34_try(-1, 4) )
          {
            __eh34_scope_strut(4);
            v55 = (struct IServerSecurity *)((char *)v85 + 1660);
            v84 = (struct IServerSecurity *)((char *)v85 + 1660);
            v66 = (int)v26;
            Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, unsigned __int16 *, unsigned __int64, struct IWbemServices *, struct IWbemContext *))v82->lpVtbl[1].QueryInterface)(
                         v82,
                         0,
                         0,
                         v71,
                         (unsigned __int64)v70 & -(__int64)(*((_DWORD *)v85 + 415) != 0),
                         v81,
                         v80);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                23,
                WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
                (unsigned int)Instance);
            }
          }
          if ( __eh34_catch(4) )
          {
            if ( __eh34_catch_type(4, &Wmi_Heap_Exception `RTTI Type Descriptor', 0) )
            {
              v68 = -2147217404;
              v16 = 3;
              Instance = -2147217404;
              v23 = (CServerObject_ProviderInitSink *)ppInterface;
              v26 = v76;
              v55 = v84;
              v70 = v86;
              v74 = v87;
              v81 = v77;
              v71 = v88;
              v73 = (__int64)v89;
              v14 = v90;
              __eh34_try_continuation(4, &Wmi_Heap_Exception `RTTI Type Descriptor', &loc_140006674);
            }
          }
          CoRevertToSelf();
        }
        else
        {
          if ( Instance < 0 )
            goto LABEL_133;
          v56 = v67;
          v57 = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
          Instance = ProviderSubSystem_Common_Globals::SetCloaking(v56, v58, v57);
          if ( Instance >= 0 )
          {
            if ( __eh34_try(-1, 6) )
            {
              __eh34_scope_strut(6);
              v66 = (int)v26;
              Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, unsigned __int16 *, unsigned __int64, struct IWbemServices *, struct IWbemContext *))v56->lpVtbl[1].QueryInterface)(
                           v56,
                           0,
                           0,
                           v71,
                           (unsigned __int64)v70 & -(__int64)(*((_DWORD *)v85 + 415) != 0),
                           v81,
                           v80);
            }
            if ( __eh34_catch(6) )
            {
              if ( __eh34_catch_type(6, &Wmi_Heap_Exception `RTTI Type Descriptor', 0) )
              {
                v68 = -2147217404;
                v16 = 3;
                Instance = -2147217404;
                v23 = (CServerObject_ProviderInitSink *)ppInterface;
                v26 = v76;
                v70 = v86;
                v74 = v87;
                v81 = v77;
                v71 = v88;
                v73 = (__int64)v89;
                v14 = v90;
                __eh34_try_continuation(6, &Wmi_Heap_Exception `RTTI Type Descriptor', &loc_140006770);
              }
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
                (unsigned int)Instance);
            }
          }
          ProviderSubSystem_Common_Globals::RevertProxyState(v67, (int)v72);
          v55 = (struct IServerSecurity *)((char *)v14 + 1660);
        }
        if ( Instance >= 0 )
        {
          CServerObject_ProviderInitSink::Wait(v23, *((_DWORD *)v14 + 430));
          Instance = *((_DWORD *)v23 + 6);
          if ( Instance >= 0 )
          {
            WmiSetAndCommitObject(
              qword_140061388,
              1,
              v71,
              *((_QWORD *)v14 + 8),
              (unsigned __int64)v74 & -(__int64)(LODWORD(v75->lpVtbl) != 0),
              (unsigned __int64)v70 & -(__int64)(LODWORD(v55->lpVtbl) != 0),
              (unsigned __int64)sz & -(__int64)(v73 != 0),
              v66);
LABEL_134:
            ProviderSubSystem_Common_Globals::EndImpersonation(v91, v78, v69);
            goto LABEL_135;
          }
        }
LABEL_133:
        WmiSetAndCommitObject(
          qword_140061380,
          1,
          v71,
          *((_QWORD *)v14 + 8),
          (unsigned __int64)v74 & -(__int64)(LODWORD(v75->lpVtbl) != 0),
          (unsigned __int64)v70 & -(__int64)(*((_DWORD *)v14 + 415) != 0),
          (unsigned __int64)sz & -(__int64)(v73 != 0),
          Instance);
        Instance = -2147217389;
        goto LABEL_134;
      }
      if ( v53 == 2 )
        v54 = ProviderSubSystem_Common_Globals::SetProxyState_NoImpersonation(
                &IID_IWbemProviderInit,
                v82,
                &v67,
                (int *)&v72);
      else
LABEL_113:
        v54 = ProviderSubSystem_Common_Globals::SetProxyState(&IID_IWbemProviderInit, v82, &v67, (int *)&v72);
      Instance = v54;
      goto LABEL_115;
    }
    Instance = -2147217402;
  }
LABEL_14:
  (*(void (__fastcall **)(CServerObject_ProviderInitSink *))(*(_QWORD *)v23 + 16LL))(v23);
  if ( Instance < 0 )
    goto LABEL_45;
LABEL_15:
  v27 = (struct IServerSecurity *)operator new(0x28u);
  v84 = v27;
  if ( v27 )
  {
    v29 = (struct IUnknown *)CServerObject_ProviderInitSink::CServerObject_ProviderInitSink(
                               (CServerObject_ProviderInitSink *)v27,
                               v28);
    v30 = v29;
    v83 = v29;
    if ( v29 )
    {
      ((void (__fastcall *)(struct IUnknown *))v29->lpVtbl->AddRef)(v29);
      Instance = CServerObject_ProviderInitSink::SinkInitialize(
                   (CServerObject_ProviderInitSink *)v30,
                   *((struct _SECURITY_DESCRIPTOR **)v14 + 230));
      if ( Instance < 0 )
      {
LABEL_44:
        ((void (__fastcall *)(struct IUnknown *))v30->lpVtbl->Release)(v30);
        goto LABEL_45;
      }
      v31 = (struct IServerSecurity *)operator new(0x20u);
      v84 = v31;
      if ( v31 )
      {
        v31->lpVtbl = (struct IServerSecurityVtbl *)&CInterceptor_IWbemProviderInitSink::`vftable';
        v31[1].lpVtbl = 0;
        v31[2].lpVtbl = 0;
        v31[3].lpVtbl = (struct IServerSecurityVtbl *)v30;
        _InterlockedIncrement(&ProviderSubSystem_Globals::s_CInterceptor_IWbemProviderInitSink_ObjectsInProgress);
        _InterlockedIncrement(&ProviderSubSystem_Globals::s_ObjectsInProgress);
        lpVtbl = v31[3].lpVtbl;
        if ( lpVtbl )
          (*((void (__fastcall **)(struct IServerSecurityVtbl *))lpVtbl->QueryInterface + 1))(lpVtbl);
      }
      else
      {
        v31 = 0;
      }
      v78 = v31;
      if ( !v31 )
      {
        Instance = -2147217402;
        goto LABEL_44;
      }
      ((void (__fastcall *)(struct IServerSecurity *))v31->lpVtbl->AddRef)(v31);
      v33 = 0;
      v69 = 0;
      ppInterface = 0;
      v84 = 0;
      v77 = 0;
      if ( CoGetCallContext(&IID_IUnknown, &ppInterface) >= 0 )
      {
        if ( (**(int (__fastcall ***)(void *, GUID *, struct IWbemServices **))ppInterface)(
               ppInterface,
               &IID_IServerSecurity,
               &v77) < 0 )
        {
          v33 = 0;
          v69 = 0;
        }
        else
        {
          v33 = ((__int64 (__fastcall *)(struct IWbemServices *))v77->lpVtbl->GetObjectA)(v77);
          v69 = v33;
        }
      }
      v67 = 0;
      LODWORD(v72) = 5;
      Instance = ProviderSubSystem_Common_Globals::CreateInstance(
                   &CLSID__IWbemCallSec,
                   v34,
                   (DWORD *)&v72,
                   &IID__IWmiCallSec,
                   (void **)&v67);
      if ( Instance >= 0 )
      {
        v76 = 0;
        Instance = ((__int64 (__fastcall *)(struct IUnknown *, __int64, CInterceptor_IWbemProviderInitSink **))v67->lpVtbl[2].AddRef)(
                     v67,
                     7,
                     &v76);
        if ( Instance >= 0 )
        {
          Instance = ((__int64 (__fastcall *)(struct IUnknown *, CInterceptor_IWbemProviderInitSink *))v67->lpVtbl[2].Release)(
                       v67,
                       v76);
          if ( Instance >= 0 )
          {
            Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IServerSecurity **))v67->lpVtbl->QueryInterface)(
                         v67,
                         &IID_IServerSecurity,
                         &v84);
            if ( Instance >= 0 )
            {
              if ( v33 )
                ((void (__fastcall *)(struct IWbemServices *))v77->lpVtbl->QueryObjectSink)(v77);
            }
          }
          (*(void (__fastcall **)(CInterceptor_IWbemProviderInitSink *))(*(_QWORD *)v76 + 16LL))(v76);
        }
        ((void (__fastcall *)(struct IUnknown *))v67->lpVtbl->Release)(v67);
      }
      if ( v77 )
        ((void (__fastcall *)(struct IWbemServices *))v77->lpVtbl->Release)(v77);
      if ( Instance < 0 )
      {
LABEL_43:
        ((void (__fastcall *)(struct IServerSecurity *))v31->lpVtbl->Release)(v31);
        goto LABEL_44;
      }
      v67 = 0;
      v91 = 0;
      if ( CoGetCallContext(&IID_IUnknown, (void **)&v91) < 0 )
        goto LABEL_28;
      if ( CoImpersonateClient() >= 0 )
      {
        v16 = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
        CoRevertToSelf();
      }
      ((void (__fastcall *)(struct IUnknown *))v91->lpVtbl->Release)(v91);
      if ( v16 == 2 )
      {
        v35 = 0;
        LODWORD(v72) = 0;
        Instance = ProviderSubSystem_Common_Globals::GetProxy(&IID_IWbemProviderInit, v82, &v67);
        if ( Instance >= 0 )
        {
          Instance = SetInterfaceSecurity(v67, v39, v40, v41, v63, v64, v65);
          if ( Instance >= 0 )
            goto LABEL_31;
          v42 = 0;
          goto LABEL_89;
        }
      }
      else
      {
LABEL_28:
        v35 = 0;
        LODWORD(v72) = 0;
        Instance = ProviderSubSystem_Common_Globals::GetProxy(&IID_IWbemProviderInit, v82, &v67);
        if ( Instance >= 0 )
        {
          Instance = CoImpersonateClient();
          if ( Instance < 0 )
          {
            Instance = -2147217405;
          }
          else
          {
            if ( ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel() - 3 > 1 )
              Instance = SetInterfaceSecurity(v67, v47, v48, v49, v63, v64, v65);
            v35 = 1;
            LODWORD(v72) = 1;
            if ( Instance >= 0 )
            {
LABEL_31:
              if ( Instance == -2147217406 )
              {
                if ( __eh34_try(-1, 8) )
                {
                  __eh34_scope_strut(8);
                  v36 = (struct CServerObject_ProviderRegistrationV1 *)((char *)v85 + 1660);
                  v76 = (struct CServerObject_ProviderRegistrationV1 *)((char *)v85 + 1660);
                  v66 = (int)v31;
                  Instance = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int64, _QWORD, unsigned __int16 *, unsigned __int64, struct IWbemServices *, struct IWbemContext *))v82->lpVtbl[1].QueryInterface)(
                               v82,
                               (unsigned __int64)v74 & -(__int64)(LODWORD(v75->lpVtbl) != 0),
                               0,
                               v71,
                               (unsigned __int64)v70 & -(__int64)(*((_DWORD *)v85 + 415) != 0),
                               v81,
                               v80);
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      25,
                      WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
                      (unsigned int)Instance);
                  }
                }
                if ( __eh34_catch(8) )
                {
                  if ( __eh34_catch_type(8, &Wmi_Heap_Exception `RTTI Type Descriptor', 0) )
                  {
                    v68 = -2147217404;
                    Instance = -2147217404;
                    v30 = v83;
                    v31 = v78;
                    v36 = v76;
                    v70 = v86;
                    v74 = v87;
                    v71 = v88;
                    v73 = (__int64)v89;
                    v14 = v90;
                    __eh34_try_continuation(8, &Wmi_Heap_Exception `RTTI Type Descriptor', &loc_140006A9E);
                  }
                }
                CoRevertToSelf();
              }
              else
              {
                if ( Instance < 0 )
                  goto LABEL_63;
                v59 = v67;
                v60 = ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel();
                Instance = ProviderSubSystem_Common_Globals::SetCloaking(v59, v61, v60);
                if ( Instance >= 0 )
                {
                  if ( __eh34_try(-1, 10) )
                  {
                    __eh34_scope_strut(10);
                    v66 = (int)v31;
                    Instance = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int64, _QWORD, unsigned __int16 *, unsigned __int64, struct IWbemServices *, struct IWbemContext *))v59->lpVtbl[1].QueryInterface)(
                                 v59,
                                 (unsigned __int64)v74 & -(__int64)(LODWORD(v75->lpVtbl) != 0),
                                 0,
                                 v71,
                                 (unsigned __int64)v70 & -(__int64)(*((_DWORD *)v85 + 415) != 0),
                                 v81,
                                 v80);
                  }
                  if ( __eh34_catch(10) )
                  {
                    if ( __eh34_catch_type(10, &Wmi_Heap_Exception `RTTI Type Descriptor', 0) )
                    {
                      v68 = -2147217404;
                      Instance = -2147217404;
                      v30 = v83;
                      v31 = v78;
                      v35 = (int)v72;
                      v70 = v86;
                      v74 = v87;
                      v71 = v88;
                      v73 = (__int64)v89;
                      v14 = v90;
                      __eh34_try_continuation(10, &Wmi_Heap_Exception `RTTI Type Descriptor', &loc_140006B8C);
                    }
                  }
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      26,
                      WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids,
                      (unsigned int)Instance);
                  }
                }
                ProviderSubSystem_Common_Globals::RevertProxyState(v67, v35);
                v36 = (struct CServerObject_ProviderRegistrationV1 *)((char *)v14 + 1660);
              }
              if ( Instance >= 0 )
              {
                if ( WaitForSingleObject(v30[2].lpVtbl, *((_DWORD *)v14 + 430)) == 258 )
                  LODWORD(v30[3].lpVtbl) = -2147217389;
                Instance = (int)v30[3].lpVtbl;
                if ( Instance >= 0 )
                {
                  v37 = v73 != 0;
                  v73 = -v73;
                  WmiSetAndCommitObject(
                    qword_140061388,
                    1,
                    v71,
                    *((_QWORD *)v14 + 8),
                    (unsigned __int64)v74 & -(__int64)(LODWORD(v75->lpVtbl) != 0),
                    (unsigned __int64)v70 & -(__int64)(*(_DWORD *)v36 != 0),
                    (unsigned __int64)sz & -(__int64)v37,
                    v66);
LABEL_42:
                  ProviderSubSystem_Common_Globals::EndImpersonation((struct IUnknown *)ppInterface, v84, v69);
                  goto LABEL_43;
                }
              }
LABEL_63:
              v37 = v73 != 0;
              v73 = -v73;
              WmiSetAndCommitObject(
                qword_140061380,
                1,
                v71,
                *((_QWORD *)v14 + 8),
                (unsigned __int64)v74 & -(__int64)(LODWORD(v75->lpVtbl) != 0),
                (unsigned __int64)v70 & -(__int64)(*((_DWORD *)v14 + 415) != 0),
                (unsigned __int64)sz & -(__int64)v37,
                Instance);
              Instance = -2147217389;
              goto LABEL_42;
            }
          }
          v42 = v35;
LABEL_89:
          ProviderSubSystem_Common_Globals::RevertProxyState(v67, v42);
          goto LABEL_31;
        }
      }
      if ( Instance != -2147217406 )
        Instance = -2147217398;
      goto LABEL_31;
    }
  }
LABEL_52:
  Instance = -2147217402;
LABEL_45:
  ((void (__fastcall *)(struct IUnknown *))v82->lpVtbl->Release)(v82);
  if ( Instance < 0 )
  {
LABEL_157:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, Instance);
  }
  v19 = WPP_GLOBAL_Control;
LABEL_47:
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 && *((_BYTE *)v19 + 25) >= 2u )
    WPP_SF_d(v19[2], 27, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids, (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140005a14  push    rbx
0x140005a16  push    rsi
0x140005a17  push    rdi
0x140005a18  push    r12
0x140005a1a  push    r13
0x140005a1c  push    r14
0x140005a1e  push    r15
0x140005a20  sub     rsp, 1C0h
0x140005a27  mov     rax, cs:__security_cookie
0x140005a2e  xor     rax, rsp
0x140005a31  mov     [rsp+1F8h+var_48], rax
0x140005a39  mov     [rsp+1F8h+var_190], r9
0x140005a3e  mov     r12, r8
0x140005a41  mov     [rsp+1F8h+var_140], rdx
0x140005a49  mov     rax, [rsp+1F8h+arg_38]
0x140005a51  mov     [rsp+1F8h+var_178], rax
0x140005a59  mov     [rsp+1F8h+var_110], rax
0x140005a61  mov     rax, [rsp+1F8h+arg_40]
0x140005a69  mov     [rsp+1F8h+var_198], rax
0x140005a6e  mov     [rsp+1F8h+var_118], rax
0x140005a76  mov     [rsp+1F8h+var_160], rdx
0x140005a7e  mov     [rsp+1F8h+var_158], r8
0x140005a86  mov     [rsp+1F8h+var_108], r9
0x140005a8e  mov     rax, [rsp+1F8h+arg_28]
0x140005a96  mov     [rsp+1F8h+var_148], rax
0x140005a9e  mov     rax, [rsp+1F8h+rguid]
0x140005aa6  mov     [rsp+1F8h+var_180], rax
0x140005aab  mov     [rsp+1F8h+var_100], rax
0x140005ab3  mov     r14, [rsp+1F8h+arg_60]
0x140005abb  mov     [rsp+1F8h+var_F8], r14
0x140005ac3  mov     [rsp+1F8h+var_120], r14
0x140005acb  xor     ebx, ebx
0x140005acd  test    rax, rax
0x140005ad0  jnz     loc_1400062B8
0x140005ad6  lea     r15, [r14+880h]
0x140005add  mov     [rsp+1F8h+var_168], r15
0x140005ae5  cmp     [r15], ebx
0x140005ae8  jnz     loc_140006148
0x140005aee  lea     rsi, WPP_GLOBAL_Control
0x140005af5  mov     r13d, 3
0x140005afb  mov     [rsp+1F8h+var_138], rbx
0x140005b03  mov     rax, [r12]
0x140005b07  lea     r8, [rsp+1F8h+var_138]
0x140005b0f  lea     rdx, IID_IWbemProviderInit
0x140005b16  mov     rcx, r12
0x140005b19  mov     rax, [rax]
0x140005b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b21  mov     edi, eax
0x140005b23  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b2a  cmp     rcx, rsi
0x140005b2d  jnz     loc_140005F9A
0x140005b33  test    edi, edi
0x140005b35  js      loc_1400060FB
0x140005b3b  lea     rax, [r14+678h]
0x140005b42  mov     [rsp+1F8h+var_170], rax
0x140005b4a  cmp     [rax], ebx
0x140005b4c  jz      loc_140005C00
0x140005b52  cmp     [r14+674h], ebx
0x140005b59  jz      loc_140005C00
0x140005b5f  mov     ecx, 28h ; '('; dwBytes
0x140005b64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005b69  mov     [rsp+1F8h+var_128], rax
0x140005b71  test    rax, rax
0x140005b74  jz      loc_140005FD2
0x140005b7a  mov     rcx, rax; this
0x140005b7d  call    ??0CServerObject_ProviderInitSink@@QEAA@PEAU_SECURITY_DESCRIPTOR@@@Z; CServerObject_ProviderInitSink::CServerObject_ProviderInitSink(_SECURITY_DESCRIPTOR *)
0x140005b82  mov     r12, rax
0x140005b85  mov     [rsp+1F8h+ppInterface], rax
0x140005b8d  test    rax, rax
0x140005b90  jz      loc_140005FD2
0x140005b96  mov     rcx, [rax]
0x140005b99  mov     rax, [rcx+8]
0x140005b9d  mov     rcx, r12
0x140005ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ba5  mov     rdx, [r14+730h]; struct _SECURITY_DESCRIPTOR *
0x140005bac  mov     rcx, r12; this
0x140005baf  call    ?SinkInitialize@CServerObject_ProviderInitSink@@QEAAJPEAU_SECURITY_DESCRIPTOR@@@Z; CServerObject_ProviderInitSink::SinkInitialize(_SECURITY_DESCRIPTOR *)
0x140005bb4  mov     edi, eax
0x140005bb6  test    eax, eax
0x140005bb8  js      short loc_140005BE8
0x140005bba  mov     ecx, 20h ; ' '; dwBytes
0x140005bbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005bc4  mov     [rsp+1F8h+var_128], rax
0x140005bcc  test    rax, rax
0x140005bcf  jz      loc_1400064C3
0x140005bd5  mov     rdx, r12; struct IWbemProviderInitSink *
0x140005bd8  mov     rcx, rax; this
0x140005bdb  call    ??0CInterceptor_IWbemProviderInitSink@@QEAA@PEAUIWbemProviderInitSink@@@Z; CInterceptor_IWbemProviderInitSink::CInterceptor_IWbemProviderInitSink(IWbemProviderInitSink *)
0x140005be0  mov     rsi, rax
0x140005be3  jmp     loc_1400064C6
0x140005be8  mov     rax, [r12]
0x140005bec  mov     rcx, r12
0x140005bef  mov     rax, [rax+10h]
0x140005bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bf8  test    edi, edi
0x140005bfa  js      loc_140005F46
0x140005c00  mov     ecx, 28h ; '('; dwBytes
0x140005c05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005c0a  mov     [rsp+1F8h+var_128], rax
0x140005c12  test    rax, rax
0x140005c15  jz      loc_140005FD2
0x140005c1b  mov     rcx, rax; this
0x140005c1e  call    ??0CServerObject_ProviderInitSink@@QEAA@PEAU_SECURITY_DESCRIPTOR@@@Z; CServerObject_ProviderInitSink::CServerObject_ProviderInitSink(_SECURITY_DESCRIPTOR *)
0x140005c23  mov     r12, rax
0x140005c26  mov     [rsp+1F8h+var_130], rax
0x140005c2e  test    rax, rax
0x140005c31  jz      loc_140005FD2
0x140005c37  mov     rdx, [rax]
0x140005c3a  mov     rcx, rax
0x140005c3d  mov     rax, [rdx+8]
0x140005c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c46  mov     rdx, [r14+730h]; struct _SECURITY_DESCRIPTOR *
0x140005c4d  mov     rcx, r12; this
0x140005c50  call    ?SinkInitialize@CServerObject_ProviderInitSink@@QEAAJPEAU_SECURITY_DESCRIPTOR@@@Z; CServerObject_ProviderInitSink::SinkInitialize(_SECURITY_DESCRIPTOR *)
0x140005c55  mov     edi, eax
0x140005c57  test    eax, eax
0x140005c59  js      loc_140005F36
0x140005c5f  mov     ecx, 20h ; ' '; dwBytes
0x140005c64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005c69  mov     rsi, rax
0x140005c6c  mov     [rsp+1F8h+var_128], rax
0x140005c74  test    rax, rax
0x140005c77  jz      loc_14000625D
0x140005c7d  lea     rax, ??_7CInterceptor_IWbemProviderInitSink@@6B@; const CInterceptor_IWbemProviderInitSink::`vftable'
0x140005c84  mov     [rsi], rax
0x140005c87  mov     qword ptr [rsi+8], 0
0x140005c8f  mov     qword ptr [rsi+10h], 0
0x140005c97  mov     [rsi+18h], r12
0x140005c9b  lock inc cs:?s_CInterceptor_IWbemProviderInitSink_ObjectsInProgress@ProviderSubSystem_Globals@@2JA; long ProviderSubSystem_Globals::s_CInterceptor_IWbemProviderInitSink_ObjectsInProgress
0x140005ca2  lock inc cs:?s_ObjectsInProgress@ProviderSubSystem_Globals@@2JA; long ProviderSubSystem_Globals::s_ObjectsInProgress
0x140005ca9  mov     rcx, [rsi+18h]
0x140005cad  test    rcx, rcx
0x140005cb0  jz      short loc_140005CBE
0x140005cb2  mov     rax, [rcx]
0x140005cb5  mov     rax, [rax+8]
0x140005cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cbe  mov     [rsp+1F8h+var_158], rsi
0x140005cc6  test    rsi, rsi
0x140005cc9  jz      loc_140006265
0x140005ccf  mov     rax, [rsi]
0x140005cd2  mov     rcx, rsi
0x140005cd5  mov     rax, [rax+8]
0x140005cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cde  mov     r15d, ebx
0x140005ce1  mov     [rsp+1F8h+var_19C], ebx
0x140005ce5  mov     [rsp+1F8h+ppInterface], rbx
0x140005ced  mov     [rsp+1F8h+var_128], rbx
0x140005cf5  mov     [rsp+1F8h+var_160], rbx
0x140005cfd  lea     rdx, [rsp+1F8h+ppInterface]; ppInterface
0x140005d05  lea     rcx, IID_IUnknown; riid
0x140005d0c  call    cs:__imp_CoGetCallContext
0x140005d12  test    eax, eax
0x140005d14  jns     loc_140006950
0x140005d1a  mov     [rsp+1F8h+var_1A8], rbx
0x140005d1f  mov     dword ptr [rsp+1F8h+var_188], 5
0x140005d27  lea     rax, [rsp+1F8h+var_1A8]
0x140005d2c  mov     [rsp+1F8h+var_1D8], rax; unsigned int
0x140005d31  lea     r9, IID__IWmiCallSec; struct _GUID *
0x140005d38  lea     r8, [rsp+1F8h+var_188]; unsigned int *
0x140005d3d  lea     rcx, CLSID__IWbemCallSec; struct _GUID *
0x140005d44  call    ?CreateInstance@ProviderSubSystem_Common_Globals@@SAJAEBU_GUID@@PEAUIUnknown@@AEBK0PEAPEAX@Z; ProviderSubSystem_Common_Globals::CreateInstance(_GUID const &,IUnknown *,ulong const &,_GUID const &,void * *)
0x140005d49  mov     edi, eax
0x140005d4b  test    eax, eax
0x140005d4d  jns     loc_1400069A2
0x140005d53  mov     rcx, [rsp+1F8h+var_160]
0x140005d5b  test    rcx, rcx
0x140005d5e  jnz     loc_140006A55
0x140005d64  test    edi, edi
0x140005d66  js      loc_140005F27
0x140005d6c  mov     [rsp+1F8h+var_1A8], rbx
0x140005d71  mov     [rsp+1F8h+var_F0], rbx
0x140005d79  lea     rdx, [rsp+1F8h+var_F0]; ppInterface
0x140005d81  lea     rcx, IID_IUnknown; riid
0x140005d88  call    cs:__imp_CoGetCallContext
0x140005d8e  test    eax, eax
0x140005d90  jns     loc_140006005
0x140005d96  mov     r15d, ebx
0x140005d99  mov     dword ptr [rsp+1F8h+var_188], ebx
0x140005d9d  lea     r8, [rsp+1F8h+var_1A8]; struct IUnknown **
0x140005da2  mov     rdx, [rsp+1F8h+var_138]; struct IUnknown *
0x140005daa  lea     rcx, IID_IWbemProviderInit; struct _GUID *
0x140005db1  call    ?GetProxy@ProviderSubSystem_Common_Globals@@SAJAEBU_GUID@@PEAUIUnknown@@AEAPEAU3@@Z; ProviderSubSystem_Common_Globals::GetProxy(_GUID const &,IUnknown *,IUnknown * &)
0x140005db6  mov     edi, eax
0x140005db8  test    eax, eax
0x140005dba  jns     loc_14000626F
0x140005dc0  cmp     edi, 80041002h
0x140005dc6  mov     eax, 8004100Ah
0x140005dcb  cmovnz  edi, eax
0x140005dce  cmp     edi, 80041002h
0x140005dd4  jnz     loc_140006080
0x140005dda  mov     r15, [rsp+1F8h+var_120]
0x140005de2  add     r15, 67Ch
0x140005de9  mov     [rsp+1F8h+var_168], r15
0x140005df1  mov     rcx, [rsp+1F8h+var_138]
0x140005df9  mov     r8, [rcx]
0x140005dfc  mov     eax, [r15]
0x140005dff  neg     eax
0x140005e01  sbb     r9, r9
0x140005e04  and     r9, [rsp+1F8h+var_198]
0x140005e09  mov     rax, [rsp+1F8h+var_170]
0x140005e11  mov     eax, [rax]
0x140005e13  neg     eax
0x140005e15  sbb     rdx, rdx
0x140005e18  and     rdx, [rsp+1F8h+var_178]
0x140005e20  mov     rax, [r8+18h]
0x140005e24  mov     qword ptr [rsp+1F8h+var_1C0], rsi
0x140005e29  mov     r8, [rsp+1F8h+var_148]
0x140005e31  mov     [rsp+1F8h+var_1C8], r8
0x140005e36  mov     r8, [rsp+1F8h+var_140]
0x140005e3e  mov     [rsp+1F8h+var_1D0], r8
0x140005e43  mov     [rsp+1F8h+var_1D8], r9
0x140005e48  mov     r9, [rsp+1F8h+var_190]
0x140005e4d  xor     r8d, r8d
0x140005e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e55  mov     edi, eax
0x140005e57  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e5e  lea     rax, WPP_GLOBAL_Control
0x140005e65  cmp     rcx, rax
0x140005e68  jz      short loc_140005E74
0x140005e6a  test    byte ptr [rcx+1Ch], 4
0x140005e6e  jnz     loc_140006A77
0x140005e74  call    cs:__imp_CoRevertToSelf
0x140005e7a  test    edi, edi
0x140005e7c  js      loc_140006088
0x140005e82  mov     edx, [r14+6B8h]; dwMilliseconds
0x140005e89  mov     rcx, [r12+10h]; hHandle
0x140005e8e  call    cs:__imp_WaitForSingleObject
0x140005e94  cmp     eax, 102h
0x140005e99  jz      loc_140006C34
0x140005e9f  mov     edi, [r12+18h]
0x140005ea4  test    edi, edi
0x140005ea6  js      loc_140006088
0x140005eac  neg     [rsp+1F8h+var_180]
0x140005eb1  sbb     r11, r11
0x140005eb4  lea     rax, [rsp+1F8h+sz]
0x140005ebc  and     r11, rax
0x140005ebf  mov     eax, [r15]
0x140005ec2  neg     eax
0x140005ec4  sbb     r10, r10
0x140005ec7  and     r10, [rsp+1F8h+var_198]
0x140005ecc  mov     rax, [rsp+1F8h+var_170]
0x140005ed4  mov     eax, [rax]
0x140005ed6  neg     eax
0x140005ed8  sbb     rcx, rcx
0x140005edb  and     rcx, [rsp+1F8h+var_178]
0x140005ee3  mov     [rsp+1F8h+var_1C8], r11
0x140005ee8  mov     [rsp+1F8h+var_1D0], r10
0x140005eed  mov     [rsp+1F8h+var_1D8], rcx
0x140005ef2  mov     r9, [r14+40h]
0x140005ef6  mov     r8, [rsp+1F8h+var_190]
0x140005efb  mov     edx, 1
0x140005f00  mov     rcx, cs:qword_140061388
0x140005f07  call    cs:__imp_WmiSetAndCommitObject
0x140005f0d  mov     r8d, [rsp+1F8h+var_19C]; int
0x140005f12  mov     rdx, [rsp+1F8h+var_128]; struct IServerSecurity *
0x140005f1a  mov     rcx, [rsp+1F8h+ppInterface]; struct IUnknown *
0x140005f22  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x140005f27  mov     rax, [rsi]
0x140005f2a  mov     rcx, rsi
0x140005f2d  mov     rax, [rax+10h]
0x140005f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f36  mov     rax, [r12]
0x140005f3a  mov     rcx, r12
0x140005f3d  mov     rax, [rax+10h]
0x140005f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f46  mov     rcx, [rsp+1F8h+var_138]
0x140005f4e  mov     rax, [rcx]
0x140005f51  mov     rax, [rax+10h]
0x140005f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f5a  test    edi, edi
0x140005f5c  js      loc_140006C47
0x140005f62  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f69  lea     rax, WPP_GLOBAL_Control
0x140005f70  cmp     rcx, rax
0x140005f73  jnz     short loc_140005FDC
0x140005f75  mov     eax, edi
0x140005f77  mov     rcx, [rsp+1F8h+var_48]
0x140005f7f  xor     rcx, rsp; StackCookie
0x140005f82  call    __security_check_cookie
0x140005f87  add     rsp, 1C0h
0x140005f8e  pop     r15
0x140005f90  pop     r14
0x140005f92  pop     r13
0x140005f94  pop     r12
0x140005f96  pop     rdi
0x140005f97  pop     rsi
0x140005f98  pop     rbx
0x140005f99  retn
0x140005f9a  test    byte ptr [rcx+1Ch], 4
0x140005f9e  jz      loc_140005B33
0x140005fa4  cmp     byte ptr [rcx+19h], 5
0x140005fa8  jb      loc_140005B33
0x140005fae  mov     edx, 16h
0x140005fb3  mov     r9d, edi
0x140005fb6  lea     r8, WPP_193e19b36f463f6e7c2a56ec47a40428_Traceguids
0x140005fbd  mov     rcx, [rcx+10h]
0x140005fc1  call    WPP_SF_d
0x140005fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x140005fcd  jmp     loc_140005B33
0x140005fd2  mov     edi, 80041006h
  ... truncated ...
```
