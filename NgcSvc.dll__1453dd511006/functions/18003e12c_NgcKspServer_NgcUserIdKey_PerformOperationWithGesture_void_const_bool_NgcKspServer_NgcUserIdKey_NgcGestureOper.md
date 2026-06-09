# NgcKspServer::NgcUserIdKey::PerformOperationWithGesture(void * const,bool,NgcKspServer::NgcUserIdKey::NgcGestureOperationType,NgcKspServer::NgcUserIdKey::NgcGestureOperationInParameter const &,NgcKspServer::NgcUserIdKey::NgcGestureOperationOutParameter &)

- ea: `0x18003e12c`
- end: `0x18003f22a`
- name: `?PerformOperationWithGesture@NgcUserIdKey@NgcKspServer@@AEAAJQEAX_NW4NgcGestureOperationType@12@AEBTNgcGestureOperationInParameter@12@AEATNgcGestureOperationOutParameter@12@@Z`
- size: `4350`
- prototype: `int __high(void *const, bool, enum NgcKspServer::NgcUserIdKey::NgcGestureOperationType, const union NgcKspServer::NgcUserIdKey::NgcGestureOperationInParameter *, union NgcKspServer::NgcUserIdKey::NgcGestureOperationOutParameter *)`
- caller_count: `7`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180076c30`
- `0x180077780`
- `0x180077ee0`
- `0x180079850`
- `0x18007a8d0`
- `0x18007db80`
- `0x18007e170`

## callees

- `0x18000782c`
- `0x180010990`
- `0x180010a94`
- `0x180011c04`
- `0x1800137c0`
- `0x180022510`
- `0x180022c50`
- `0x180028d18`
- `0x180029f0c`
- `0x18002ae64`
- `0x18002d740`
- `0x18002dc0c`
- `0x18002eee8`
- `0x18002fb30`
- `0x180031b54`
- `0x180031c3c`
- `0x1800323d0`
- `0x180032dec`
- `0x180035c40`
- `0x180035ee8`
- `0x180035fb4`
- `0x180038764`
- `0x18003e12c`
- `0x180041394`
- `0x180046d90`
- `0x180048394`
- `0x180057e74`
- `0x180059df4`
- `0x18005cee0`
- `0x18005dd20`
- `0x18006c8d0`
- `0x18006caa4`
- `0x180076664`
- `0x180078510`
- `0x1800818c8`
- `0x1800a962c`
- `0x1800cd010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18003ef47`
- `ntdll!RtlPublishWnfStateData` at `0x18003ef47`

## string_xrefs

- `0x18003e464`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18003e823`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18003eb6a`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18003ec56`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18003ed8d`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18003ee87`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18003ef71`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18003f0a6`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18003f10c`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18003f193`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall NgcKspServer::NgcUserIdKey::PerformOperationWithGesture(
        __int64 a1,
        void *a2,
        char a3,
        unsigned int a4,
        char **a5,
        __int64 a6)
{
  void *v6; // r15
  int v8; // r12d
  unsigned __int64 v9; // rsi
  __int64 *v10; // r10
  __int64 v11; // rax
  char v12; // al
  bool IsZero; // al
  struct _GUID *v14; // r9
  int v15; // r8d
  RPC_STATUS v16; // eax
  unsigned int v17; // ebx
  int v18; // r8d
  int v19; // r14d
  char v20; // bl
  __int64 v21; // r9
  __int64 v22; // rdx
  unsigned __int8 *v23; // rdx
  NgcKspServer::PinCacheManager *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  unsigned __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rdx
  char *v31; // rdx
  int v32; // r12d
  char v33; // r13
  int v34; // r14d
  const unsigned __int16 *v35; // rdx
  _QWORD *v36; // rdx
  char v37; // r8
  char v38; // r10
  int v39; // eax
  unsigned __int64 *v40; // r15
  int v41; // eax
  __int64 v42; // rdx
  int *v43; // rdx
  int v44; // ecx
  int v45; // eax
  int v46; // eax
  int v47; // eax
  unsigned __int8 *v48; // rdx
  char IsEnabled; // al
  __int64 (__fastcall *v50)(__int64, __int64, __int64, unsigned __int64 *); // r11
  __int64 v51; // rdx
  __int64 v52; // rcx
  int v53; // eax
  int v54; // eax
  int v55; // eax
  unsigned int v56; // ebx
  unsigned __int64 v57; // r9
  NgcKspServer::PinCacheManager *v58; // rax
  int v60; // [rsp+20h] [rbp-100h]
  int v61; // [rsp+20h] [rbp-100h]
  int v62; // [rsp+20h] [rbp-100h]
  int v63; // [rsp+40h] [rbp-E0h]
  char *v64; // [rsp+A0h] [rbp-80h] BYREF
  unsigned __int64 v65; // [rsp+A8h] [rbp-78h] BYREF
  char v66; // [rsp+B0h] [rbp-70h] BYREF
  char v67; // [rsp+B1h] [rbp-6Fh] BYREF
  char v68; // [rsp+B2h] [rbp-6Eh] BYREF
  char v69; // [rsp+B3h] [rbp-6Dh] BYREF
  int v70; // [rsp+B4h] [rbp-6Ch] BYREF
  __int64 v71; // [rsp+B8h] [rbp-68h] BYREF
  int *v72; // [rsp+C0h] [rbp-60h]
  char v73; // [rsp+C8h] [rbp-58h] BYREF
  char v74; // [rsp+C9h] [rbp-57h] BYREF
  char v75; // [rsp+CAh] [rbp-56h] BYREF
  char v76; // [rsp+CBh] [rbp-55h] BYREF
  char v77[4]; // [rsp+CCh] [rbp-54h] BYREF
  unsigned __int64 v78; // [rsp+D0h] [rbp-50h] BYREF
  unsigned int v79; // [rsp+D8h] [rbp-48h] BYREF
  __int128 Buf2; // [rsp+E0h] [rbp-40h] BYREF
  __int128 v81; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v82; // [rsp+100h] [rbp-20h]
  __int64 v83; // [rsp+108h] [rbp-18h] BYREF
  __int64 v84; // [rsp+110h] [rbp-10h]
  int v85; // [rsp+118h] [rbp-8h] BYREF
  int v86; // [rsp+11Ch] [rbp-4h] BYREF
  unsigned __int64 v87; // [rsp+120h] [rbp+0h] BYREF
  int v88; // [rsp+128h] [rbp+8h] BYREF
  char **v89; // [rsp+130h] [rbp+10h]
  __int128 v90; // [rsp+138h] [rbp+18h] BYREF
  __int64 v91; // [rsp+148h] [rbp+28h]
  void *v92; // [rsp+150h] [rbp+30h]
  _BYTE v93[24]; // [rsp+158h] [rbp+38h] BYREF
  _BYTE v94[4]; // [rsp+170h] [rbp+50h] BYREF
  int v95; // [rsp+174h] [rbp+54h]
  __int64 v96; // [rsp+178h] [rbp+58h]
  char v97; // [rsp+180h] [rbp+60h]
  int v98; // [rsp+184h] [rbp+64h]
  int v99; // [rsp+188h] [rbp+68h]
  __int128 v100; // [rsp+18Ch] [rbp+6Ch]
  int v101; // [rsp+19Ch] [rbp+7Ch]
  __int64 v102; // [rsp+1A0h] [rbp+80h]
  int v103; // [rsp+1A8h] [rbp+88h]
  __int64 v104; // [rsp+1B0h] [rbp+90h]
  __int64 v105[10]; // [rsp+1C0h] [rbp+A0h] BYREF
  char v106; // [rsp+210h] [rbp+F0h]
  int v107; // [rsp+214h] [rbp+F4h]
  int v108; // [rsp+218h] [rbp+F8h]
  _QWORD v109[10]; // [rsp+220h] [rbp+100h] BYREF
  __int16 v110; // [rsp+270h] [rbp+150h]
  __int128 v111; // [rsp+280h] [rbp+160h] BYREF
  __int64 v112; // [rsp+290h] [rbp+170h]
  int v113[24]; // [rsp+2A0h] [rbp+180h] BYREF
  int v114; // [rsp+300h] [rbp+1E0h] BYREF
  char v115; // [rsp+304h] [rbp+1E4h]
  GUID v116; // [rsp+308h] [rbp+1E8h] BYREF
  struct _GUID v117; // [rsp+318h] [rbp+1F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+258h]
  char v119; // [rsp+390h] [rbp+270h] BYREF

  v119 = a3;
  v6 = a2;
  v92 = a2;
  v8 = (int)a5;
  v89 = a5;
  v79 = a4;
  v104 = a6;
  v9 = 0;
  LODWORD(v64) = 0;
  v85 = 0;
  if ( a4 != 8 )
  {
    v90 = 0;
    v91 = 0;
    v10 = *(__int64 **)(a1 + 352);
    v11 = *v10;
    v70 = 3;
    v60 = a1 + 104;
    LODWORD(v64) = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64))(v11 + 216))(
                     v10,
                     a1 + 56,
                     a1 + 136,
                     a1 + 72);
    if ( (int)v64 >= 0 )
    {
      v85 = *(_DWORD *)v90;
    }
    else
    {
      if ( (unsigned int)dword_180122070 > 3 )
      {
        v70 = (int)v64;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)&word_180101AAE,
          0,
          0,
          (__int64)&v70);
      }
      LODWORD(v64) = 0;
    }
    std::vector<unsigned char>::_Tidy(&v90);
  }
  *((_DWORD *)NgcKspServer::PinCacheManager::Instance() + 21) = v85;
  v69 = 0;
  v88 = 0;
  v67 = 0;
  v66 = 0;
  v114 = 0;
  v115 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v114);
  if ( (unsigned int)dword_180122070 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180122070, 0x400000000000LL) )
  {
    LODWORD(v83) = v85;
    LODWORD(v87) = *(_DWORD *)(a1 + 516);
    v73 = v67;
    LODWORD(v78) = v88;
    v74 = *(_BYTE *)(a1 + 370);
    v75 = v69;
    v76 = v66;
    LOWORD(v86) = v79;
    LOWORD(v70) = 0;
    v77[0] = *(_BYTE *)(a1 + 512);
    if ( v119 || (v12 = 0, *(_BYTE *)(a1 + 264)) )
      v12 = 1;
    v68 = v12;
    LODWORD(v65) = (_DWORD)v64;
    if ( !v115 || (IsZero = _tlgGuidIsZero(&v117), v14 = &v117, IsZero) )
      v14 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)byte_1801019C1,
      &v116,
      v14,
      (__int64)&v65,
      (__int64)&v68,
      (__int64)v77,
      (__int64)&v70,
      (__int64)&v86,
      (__int64)&v76,
      (__int64)&v75,
      (__int64)&v74,
      (__int64)&v78,
      (__int64)&v73,
      (__int64)&v87,
      (__int64)&v83);
  }
  v109[0] = &v114;
  v109[1] = &v64;
  v109[2] = &v119;
  v109[3] = a1;
  v109[4] = &v79;
  v109[5] = &v66;
  v109[6] = &v69;
  v109[7] = &v88;
  v109[8] = &v67;
  v109[9] = &v85;
  v110 = 256;
  v78 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v78,
      0);
    LODWORD(v64) = DoKeyAccessCheckWorkRequiringImpersonation(v6, 1, v18, &v78);
    if ( (int)v64 < 0 )
    {
      if ( (unsigned int)dword_180122070 > 2 )
      {
        LODWORD(v65) = (_DWORD)v64;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_180101981,
          0,
          0,
          (__int64)&v65);
      }
      v17 = (unsigned int)v64;
      goto LABEL_24;
    }
LABEL_25:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v78);
    v111 = 0;
    v112 = 0;
    v19 = *(_DWORD *)(a1 + 516);
    v70 = v19;
    Buf2 = 0;
    v83 = (a1 + 568) & -(__int64)(memcmp_0((const void *)(a1 + 568), &Buf2, 0x10u) != 0);
    *(_QWORD *)&Buf2 = a1;
    v20 = 0;
    WORD4(Buf2) = 256;
    if ( *(_BYTE *)(a1 + 512) )
    {
      LODWORD(v64) = -2146893778;
    }
    else
    {
      v21 = *(_QWORD *)(a1 + 328);
      if ( v21 == -1 )
      {
        LODWORD(v64) = -2146893773;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          v22 = 6827;
LABEL_181:
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
            (const char *)(unsigned int)v64,
            v60);
          goto LABEL_185;
        }
        if ( (unsigned int)dword_180122070 > 2 )
        {
          v23 = (unsigned __int8 *)&dword_180101934;
          goto LABEL_184;
        }
LABEL_185:
        v17 = (unsigned int)v64;
LABEL_186:
        wil::details::ScopeExitFnGuard__lambda_fdbfd235a139f1df5b3d69004c204dbb___::operator()(&Buf2);
        goto LABEL_187;
      }
      if ( v21 )
      {
        if ( v79 != 8 || v19 == 1 )
        {
          if ( (unsigned int)dword_180122070 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180122070, 0x400000000000LL) )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              (__int64)&dword_180122070,
              (unsigned __int8 *)&dword_1801018AC,
              0);
          v9 = *(_QWORD *)(a1 + 328);
          v66 = 1;
          *((_BYTE *)NgcKspServer::PinCacheManager::Instance() + 88) = 1;
        }
        else
        {
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 352) + 16LL))(
            *(_QWORD *)(a1 + 352),
            a1 + 56,
            0);
        }
      }
      else if ( v19 == 1 )
      {
        LODWORD(v64) = -2146893778;
        if ( (unsigned int)dword_180122070 > 3 )
        {
          LODWORD(v65) = (_DWORD)v64;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)byte_1801018E5,
            0,
            0,
            (__int64)&v65);
        }
      }
    }
    if ( (_DWORD)v64 != -2146893778 )
    {
      LODWORD(v64) = 0;
      if ( v9 )
        goto LABEL_49;
      NgcUtils::RpcCallerInfo::RpcCallerInfo((NgcUtils::RpcCallerInfo *)v94, v6);
      v65 = 0;
      v24 = NgcKspServer::PinCacheManager::Instance();
      LODWORD(v64) = NgcKspServer::PinCacheManager::GetAuthTicket(
                       v24,
                       (const struct NgcUtils::RpcCallerInfo *)v94,
                       (const struct NgcUtils::NgcKeyName *)(a1 + 32),
                       &v65);
      if ( (int)v64 >= 0 && v19 != 1 )
      {
        v9 = v65;
        v20 = 1;
        *((_BYTE *)NgcKspServer::PinCacheManager::Instance() + 89) = 1;
      }
      NgcUtils::RpcCallerInfo::~RpcCallerInfo((NgcUtils::RpcCallerInfo *)v94);
      if ( (int)v64 >= 0 )
      {
LABEL_49:
        v60 = v8;
        LODWORD(v64) = NgcKspServer::NgcUserIdKey::DispatchGestureOperation(a1, v79, &v111, v9);
        if ( (unsigned int)dword_180122070 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180122070, 0x400000000000LL) )
        {
          v68 = v20;
          LODWORD(v65) = (_DWORD)v64;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
            v25,
            (unsigned __int8 *)byte_180101861,
            v26,
            v27,
            (__int64)&v65,
            (__int64)&v68);
        }
        v20 = 0;
        if ( (int)v64 >= 0 )
          goto LABEL_185;
        v28 = (unsigned int)((_DWORD)v64 + 2146893808);
        if ( (unsigned int)v28 > 0x23 || (v29 = 0x840000001LL, !_bittest64(&v29, v28)) )
        {
          if ( (unsigned int)dword_180122070 > 2 )
          {
            v23 = (unsigned __int8 *)&unk_180101818;
            goto LABEL_184;
          }
          goto LABEL_185;
        }
      }
      else
      {
        v20 = 0;
      }
    }
    if ( v119 || *(_BYTE *)(a1 + 264) )
    {
      LODWORD(v64) = -2146893790;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        v22 = 6956;
        goto LABEL_181;
      }
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_185;
      v23 = (unsigned __int8 *)&byte_1801017CF;
LABEL_184:
      LODWORD(v65) = (_DWORD)v64;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        v23,
        0,
        0,
        (__int64)&v65);
      goto LABEL_185;
    }
    *((_BYTE *)NgcKspServer::PinCacheManager::Instance() + 91) = 1;
    v81 = 0;
    v82 = 0;
    if ( !*(_QWORD *)(a1 + 304) && (unsigned int)dword_180122070 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)&word_180101796,
        0);
    if ( (*(_BYTE *)(a1 + 24) & 1) != 0 )
    {
      if ( (_QWORD)v81 != *((_QWORD *)&v81 + 1) )
        *((_QWORD *)&v81 + 1) = v81;
      LODWORD(v64) = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int128 *))(**(_QWORD **)(a1 + 352) + 248LL))(
                       *(_QWORD *)(a1 + 352),
                       a1 + 56,
                       3,
                       &v81);
      if ( (int)v64 < 0 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          v30 = 6996;
LABEL_70:
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)v30,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
            (const char *)(unsigned int)v64,
            v60);
          goto LABEL_74;
        }
        if ( (unsigned int)dword_180122070 > 2 )
        {
          v31 = byte_180101733;
LABEL_73:
          LODWORD(v65) = (_DWORD)v64;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)v31,
            0,
            0,
            (__int64)&v65);
          goto LABEL_74;
        }
        goto LABEL_74;
      }
      if ( *((_QWORD *)&v81 + 1) - (_QWORD)v81 != 4 )
      {
        LODWORD(v64) = -2146893792;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          v30 = 7014;
          goto LABEL_70;
        }
        if ( (unsigned int)dword_180122070 > 2 )
        {
          v31 = &byte_1801016DF;
          goto LABEL_73;
        }
LABEL_74:
        v17 = (unsigned int)v64;
LABEL_178:
        std::vector<unsigned char>::_Tidy(&v81);
        goto LABEL_186;
      }
      v32 = HIWORD(*(_DWORD *)v81);
      v33 = *(_DWORD *)v81 & 1;
      v20 = (*(_DWORD *)v81 & 2) != 0;
    }
    else
    {
      v33 = 0;
      v32 = 0;
    }
    v34 = 0;
    if ( *(_QWORD *)(a1 + 392) )
    {
      v35 = (const unsigned __int16 *)(a1 + 376);
      if ( *(_QWORD *)(a1 + 400) > 7u )
        v35 = *(const unsigned __int16 **)v35;
    }
    else
    {
      v35 = 0;
    }
    NgcKspServer::CredUIStringsContext::CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v105, v35, 1);
    v36 = (_QWORD *)(a1 + 672);
    if ( *(_QWORD *)(a1 + 696) > 7u )
      v36 = (_QWORD *)*v36;
    std::wstring::assign(v105[0], v36);
    v106 = 0;
    while ( 1 )
    {
      if ( (_QWORD)v81 != *((_QWORD *)&v81 + 1) )
        *((_QWORD *)&v81 + 1) = v81;
      LODWORD(v64) = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int128 *))(**(_QWORD **)(a1 + 352) + 248LL))(
                       *(_QWORD *)(a1 + 352),
                       a1 + 56,
                       8,
                       &v81);
      if ( (int)v64 < 0 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x1B8A,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
            (const char *)(unsigned int)v64,
            v60);
        }
        else if ( (unsigned int)dword_180122070 > 2 )
        {
          LODWORD(v65) = (_DWORD)v64;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)&dword_180101684,
            0,
            0,
            (__int64)&v65);
        }
        v17 = HResultToSecurityStatus((int)v64);
        LODWORD(v64) = v17;
        goto LABEL_177;
      }
      if ( *((_QWORD *)&v81 + 1) - (_QWORD)v81 != 20 )
      {
        LODWORD(v64) = -2146893792;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x1B9D,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
            (const char *)(unsigned int)v64,
            v60);
        }
        else if ( (unsigned int)dword_180122070 > 2 )
        {
          LODWORD(v65) = (_DWORD)v64;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)byte_180101637,
            0,
            0,
            (__int64)&v65);
        }
        v17 = (unsigned int)v64;
        goto LABEL_177;
      }
      if ( *(_DWORD *)v81 || !*(_DWORD *)(v81 + 12) )
      {
        v34 = -2146893775;
        v107 = -2146893775;
      }
      if ( (v79 & 0xFFFFFFF7) == 0 || v79 == 3 || v79 == 9 )
      {
        v38 = (*v89)[1];
        v37 = **v89;
      }
      else
      {
        v37 = 0;
        v38 = 0;
      }
      v71 = (__int64)&Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
      v72 = 0;
      v39 = NgcKspServer::PromptForGesture(
              (int)v6,
              *(_QWORD *)(a1 + 304),
              v34,
              *(_DWORD *)(a1 + 24),
              *(_BYTE *)(a1 + 369),
              v33,
              v32,
              v20,
              v63,
              *(PSID *)(a1 + 32),
              v37,
              v38,
              a1 + 624,
              a1 + 648,
              *(_BYTE *)(a1 + 457),
              (v81 + 8) & -(__int64)(*(_DWORD *)v81 != 0),
              v83,
              (__int64)v105,
              (__int64)&v71);
      LODWORD(v64) = v39;
      if ( v39 < 0 )
      {
        v44 = v39;
        goto LABEL_118;
      }
      v78 = 0;
      v87 = 0;
      v40 = &v87;
      if ( v70 != 1 )
        v40 = 0;
      v60 = (int)v40;
      v41 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, unsigned __int64 *))(**(_QWORD **)(a1 + 352) + 8LL))(
              *(_QWORD *)(a1 + 352),
              a1 + 56,
              v72,
              &v78);
      v34 = v41;
      LODWORD(v64) = v41;
      if ( v41 >= 0 )
        goto LABEL_152;
      if ( ((v41 + 2146893775) & 0xFFFFFFFD) != 0 )
        break;
      v107 = v41;
      v108 = *v72;
      v71 = (__int64)&Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v71);
      LODWORD(v6) = (_DWORD)v92;
    }
    if ( v41 == -2146893769 )
    {
      if ( (_QWORD)v81 != *((_QWORD *)&v81 + 1) )
        *((_QWORD *)&v81 + 1) = v81;
      LODWORD(v64) = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int128 *))(**(_QWORD **)(a1 + 352) + 248LL))(
                       *(_QWORD *)(a1 + 352),
                       a1 + 56,
                       2,
                       &v81);
      if ( (int)v64 < 0 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          v42 = 7168;
          goto LABEL_113;
        }
        if ( (unsigned int)dword_180122070 > 2 )
        {
          v43 = &dword_1801015E4;
          goto LABEL_116;
        }
LABEL_117:
        v44 = (int)v64;
LABEL_118:
        v17 = HResultToSecurityStatus(v44);
        LODWORD(v64) = v17;
LABEL_119:
        v71 = (__int64)&Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
LABEL_120:
        Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v71);
LABEL_177:
        NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v105);
        goto LABEL_178;
      }
      v94[0] = 0;
      v95 = 1;
      v96 = 1;
      v97 = 0;
      v98 = 8;
      v99 = 127;
      v100 = 0;
      v101 = 2;
      v102 = 1;
      v103 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        v45 = NgcPolicy::NgcPolicy::Initialize(v94, &v81);
        v46 = HResultToSecurityStatus(v45);
        v17 = v46;
        if ( v46 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1C10,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
            (const char *)(unsigned int)v46,
            (int)v40);
          goto LABEL_119;
        }
LABEL_127:
        NgcKspServer::CredUIStringsContext::CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v113, 0, 1);
        v83 = (__int64)&Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
        v84 = 0;
        v47 = NgcKspServer::PromptForNewPin(
                (_DWORD)v92,
                *(_QWORD *)(a1 + 304),
                0,
                (unsigned int)v94,
                (__int64)v113,
                (__int64)&v83);
        LODWORD(v64) = v47;
        if ( v47 < 0 )
        {
          v17 = HResultToSecurityStatus(v47);
          LODWORD(v64) = v17;
LABEL_129:
          v83 = (__int64)&Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
          Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v83);
          NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v113);
          goto LABEL_130;
        }
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
          &v90,
          *((_QWORD *)v72 + 1),
          *((_QWORD *)v72 + 1) + (unsigned int)v72[4]);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
          v93,
          *(_QWORD *)(v84 + 8),
          *(_QWORD *)(v84 + 8) + *(unsigned int *)(v84 + 16));
        LODWORD(v64) = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, _BYTE *))(**(_QWORD **)(a1 + 352) + 24LL))(
                         *(_QWORD *)(a1 + 352),
                         a1 + 56,
                         &v90,
                         v93);
        if ( (int)v64 < 0 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x1C40,
              (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
              (const char *)(unsigned int)v64,
              v61);
LABEL_134:
            v17 = HResultToSecurityStatus((int)v64);
            LODWORD(v64) = v17;
LABEL_135:
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v93);
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v90);
            goto LABEL_129;
          }
          if ( (unsigned int)dword_180122070 <= 2 )
            goto LABEL_134;
          v48 = (unsigned __int8 *)word_18010156A;
LABEL_138:
          LODWORD(v65) = (_DWORD)v64;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            v48,
            0,
            0,
            (__int64)&v65);
          goto LABEL_134;
        }
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, unsigned __int64))(**(_QWORD **)(a1 + 352) + 16LL))(
          *(_QWORD *)(a1 + 352),
          a1 + 56,
          0,
          v78);
        if ( v87 )
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 352) + 16LL))(
            *(_QWORD *)(a1 + 352),
            a1 + 56,
            0);
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
        v50 = *(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned __int64 *))(**(_QWORD **)(a1 + 352) + 8LL);
        v51 = a1 + 56;
        v52 = *(_QWORD *)(a1 + 352);
        if ( IsEnabled )
        {
          v53 = v50(v52, v51, v84, &v78);
          v54 = HResultToSecurityStatus(v53);
          v17 = v54;
          if ( v54 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1C64,
              (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
              (const char *)(unsigned int)v54,
              (int)v40);
            goto LABEL_135;
          }
        }
        else
        {
          LODWORD(v64) = ((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned __int64 *, unsigned __int64 *))v50)(
                           v52,
                           v51,
                           v84,
                           &v78,
                           v40);
          if ( (int)v64 < 0 )
          {
            if ( (unsigned int)dword_180122070 <= 2 )
              goto LABEL_134;
            v48 = (unsigned __int8 *)&unk_180101510;
            goto LABEL_138;
          }
        }
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v93);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v90);
        v83 = (__int64)&Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v83);
        NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v113);
LABEL_152:
        v55 = RtlPublishWnfStateData(WNF_NGC_GESTURE_SUCCEEDED, 0, 0, 0, 0);
        v56 = v55 | 0x10000000;
        if ( v55 < 0 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x1C91,
              (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
              (const char *)v56,
              v62);
          }
          else if ( (unsigned int)dword_180122070 > 2 )
          {
            LODWORD(v65) = v56;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (__int64)&dword_180122070,
              (unsigned __int8 *)word_18010147A,
              0,
              0,
              (__int64)&v65);
          }
        }
        v57 = v78;
        if ( v70 == 1 )
          v57 = v87;
        LODWORD(v64) = NgcKspServer::NgcUserIdKey::DispatchGestureOperation(a1, v79, v72, v57);
        if ( (int)v64 >= 0 )
        {
          v58 = NgcKspServer::PinCacheManager::Instance();
          LODWORD(v64) = NgcKspServer::PinCacheManager::AddAuthTicket(
                           v58,
                           (const struct NgcUtils::NgcKeyName *)(a1 + 32),
                           v78);
          if ( (int)v64 >= 0 )
          {
            v67 = 1;
            *((_BYTE *)NgcKspServer::PinCacheManager::Instance() + 90) = 1;
          }
          LODWORD(v64) = 0;
          v71 = (__int64)&Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
          Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v71);
          NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v105);
          std::vector<unsigned char>::_Tidy(&v81);
          goto LABEL_185;
        }
        if ( (unsigned int)dword_180122070 > 2 )
        {
          LODWORD(v65) = (_DWORD)v64;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)byte_180101431,
            0,
            0,
            (__int64)&v65);
        }
        v17 = (unsigned int)v64;
LABEL_130:
        v71 = (__int64)&Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
        goto LABEL_120;
      }
      LODWORD(v64) = NgcPolicy::NgcPolicy::Initialize(v94, &v81);
      if ( (int)v64 >= 0 )
        goto LABEL_127;
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_117;
      v43 = &dword_1801015B4;
    }
    else
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        v42 = 7292;
LABEL_113:
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)v42,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
          (const char *)(unsigned int)v64,
          (int)v40);
        goto LABEL_117;
      }
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_117;
      v43 = &dword_1801014BC;
    }
LABEL_116:
    LODWORD(v65) = (_DWORD)v64;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)v43,
      0,
      0,
      (__int64)&v65);
    goto LABEL_117;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v78,
    0);
  v16 = DoKeyAccessCheckWorkRequiringImpersonation(v6, 1, v15, &v78);
  v17 = v16;
  if ( v16 >= 0 )
    goto LABEL_25;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A7D,
    (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
    (const char *)(unsigned int)v16,
    v60);
LABEL_24:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v78);
LABEL_187:
  wil::details::ScopeExitFnGuard__lambda_42a3dea12be678c5357e1f360428c223___::operator()(v109);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v114);
  return v17;
}

```

## disassembly

```asm
0x18003e12c  mov     [rsp-8+arg_10], r8b
0x18003e131  push    rbp
0x18003e132  push    rbx
0x18003e133  push    rsi
0x18003e134  push    rdi
0x18003e135  push    r12
0x18003e137  push    r13
0x18003e139  push    r14
0x18003e13b  push    r15
0x18003e13d  lea     rbp, [rsp-218h]
0x18003e145  sub     rsp, 338h
0x18003e14c  mov     rax, cs:__security_cookie
0x18003e153  xor     rax, rsp
0x18003e156  mov     [rbp+250h+var_48], rax
0x18003e15d  mov     r15, rdx
0x18003e160  mov     [rbp+250h+var_220], rdx
0x18003e164  mov     rdi, rcx
0x18003e167  mov     r12, [rbp+250h+arg_20]
0x18003e16e  mov     [rbp+250h+var_240], r12
0x18003e172  mov     [rbp+250h+var_298], r9d
0x18003e176  mov     r13, [rbp+250h+arg_28]
0x18003e17d  mov     [rbp+250h+var_1C0], r13
0x18003e184  xor     esi, esi
0x18003e186  mov     dword ptr [rbp+250h+var_2D0], esi
0x18003e189  mov     [rbp+250h+var_258], esi
0x18003e18c  lea     rbx, dword_180122070
0x18003e193  cmp     r9d, 8
0x18003e197  jz      loc_18003E240
0x18003e19d  xorps   xmm0, xmm0
0x18003e1a0  movdqu  [rbp+250h+var_238], xmm0
0x18003e1a5  mov     [rbp+250h+var_228], rsi
0x18003e1a9  mov     r10, [rcx+160h]
0x18003e1b0  mov     rax, [r10]
0x18003e1b3  mov     [rbp+250h+var_2BC], 3
0x18003e1ba  add     rcx, 68h ; 'h'
0x18003e1be  lea     r9, [rdi+48h]
0x18003e1c2  lea     r8, [rdi+88h]
0x18003e1c9  lea     rdx, [rdi+38h]
0x18003e1cd  lea     r11, [rbp+250h+var_238]
0x18003e1d1  mov     qword ptr [rsp+370h+var_340], r11
0x18003e1d6  lea     r11, [rbp+250h+var_2BC]
0x18003e1da  mov     qword ptr [rsp+370h+var_348], r11
0x18003e1df  mov     qword ptr [rsp+370h+var_350], rcx
0x18003e1e4  mov     rcx, r10
0x18003e1e7  mov     rax, [rax+0D8h]
0x18003e1ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1f3  mov     dword ptr [rbp+250h+var_2D0], eax
0x18003e1f6  test    eax, eax
0x18003e1f8  jns     short loc_18003E22E
0x18003e1fa  mov     eax, cs:dword_180122070
0x18003e200  cmp     eax, 3
0x18003e203  jbe     short loc_18003E229
0x18003e205  mov     eax, dword ptr [rbp+250h+var_2D0]
0x18003e208  mov     [rbp+250h+var_2BC], eax
0x18003e20b  lea     rax, [rbp+250h+var_2BC]
0x18003e20f  mov     qword ptr [rsp+370h+var_350], rax
0x18003e214  xor     r9d, r9d
0x18003e217  xor     r8d, r8d
0x18003e21a  lea     rdx, word_180101AAE
0x18003e221  mov     rcx, rbx
0x18003e224  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003e229  mov     dword ptr [rbp+250h+var_2D0], esi
0x18003e22c  jmp     short loc_18003E237
0x18003e22e  mov     rax, qword ptr [rbp+250h+var_238]
0x18003e232  mov     ecx, [rax]
0x18003e234  mov     [rbp+250h+var_258], ecx
0x18003e237  lea     rcx, [rbp+250h+var_238]
0x18003e23b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003e240  call    ?Instance@PinCacheManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::PinCacheManager::Instance(void)
0x18003e245  mov     ecx, [rbp+250h+var_258]
0x18003e248  mov     [rax+54h], ecx
0x18003e24b  mov     [rbp+250h+var_2BD], sil
0x18003e24f  mov     [rbp+250h+var_248], esi
0x18003e252  mov     [rbp+250h+var_2BF], sil
0x18003e256  mov     [rbp+250h+var_2C0], sil
0x18003e25a  mov     [rbp+250h+var_70], esi
0x18003e260  mov     [rbp+250h+var_6C], sil
0x18003e267  lea     rcx, [rbp+250h+var_70]
0x18003e26e  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18003e273  mov     eax, cs:dword_180122070
0x18003e279  mov     r14d, 1
0x18003e27f  cmp     eax, 5
0x18003e282  jbe     loc_18003E3AD
0x18003e288  mov     rdx, 400000000000h
0x18003e292  mov     rcx, rbx
0x18003e295  call    _tlgKeywordOn
0x18003e29a  test    al, al
0x18003e29c  jz      loc_18003E3AD
0x18003e2a2  mov     eax, [rbp+250h+var_258]
0x18003e2a5  mov     dword ptr [rbp+250h+var_268], eax
0x18003e2a8  mov     eax, [rdi+204h]
0x18003e2ae  mov     dword ptr [rbp+250h+var_250], eax
0x18003e2b1  mov     al, [rbp+250h+var_2BF]
0x18003e2b4  mov     [rbp+250h+var_2A8], al
0x18003e2b7  mov     eax, [rbp+250h+var_248]
0x18003e2ba  mov     dword ptr [rbp+250h+var_2A0], eax
0x18003e2bd  mov     al, [rdi+172h]
0x18003e2c3  mov     [rbp+250h+var_2A7], al
0x18003e2c6  mov     al, [rbp+250h+var_2BD]
0x18003e2c9  mov     [rbp+250h+var_2A6], al
0x18003e2cc  mov     al, [rbp+250h+var_2C0]
0x18003e2cf  mov     [rbp+250h+var_2A5], al
0x18003e2d2  movzx   eax, word ptr [rbp+250h+var_298]
0x18003e2d6  mov     word ptr [rbp+250h+var_254], ax
0x18003e2da  mov     word ptr [rbp+250h+var_2BC], si
0x18003e2de  mov     al, [rdi+200h]
0x18003e2e4  mov     [rbp+250h+var_2A4], al
0x18003e2e7  cmp     [rbp+250h+arg_10], sil
0x18003e2ee  jnz     short loc_18003E2FC
0x18003e2f0  cmp     [rdi+108h], sil
0x18003e2f7  mov     al, sil
0x18003e2fa  jz      short loc_18003E2FF
0x18003e2fc  mov     al, r14b
0x18003e2ff  mov     [rbp+250h+var_2BE], al
0x18003e302  mov     eax, dword ptr [rbp+250h+var_2D0]
0x18003e305  mov     dword ptr [rbp+250h+var_2C8], eax
0x18003e308  cmp     [rbp+250h+var_6C], sil
0x18003e30f  jz      short loc_18003E328
0x18003e311  lea     rcx, [rbp+250h+var_58]; struct _GUID *
0x18003e318  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18003e31d  test    al, al
0x18003e31f  lea     r9, [rbp+250h+var_58]
0x18003e326  jz      short loc_18003E32B
0x18003e328  mov     r9, rsi
0x18003e32b  lea     rax, [rbp+250h+var_268]
0x18003e32f  mov     [rsp+370h+var_2F8], rax
0x18003e334  lea     rax, [rbp+250h+var_250]
0x18003e338  mov     qword ptr [rsp+370h+var_300], rax
0x18003e33d  lea     rax, [rbp+250h+var_2A8]
0x18003e341  mov     [rsp+370h+var_308], rax
0x18003e346  lea     rax, [rbp+250h+var_2A0]
0x18003e34a  mov     [rsp+370h+var_310], rax
0x18003e34f  lea     rax, [rbp+250h+var_2A7]
0x18003e353  mov     qword ptr [rsp+370h+var_318], rax
0x18003e358  lea     rax, [rbp+250h+var_2A6]
0x18003e35c  mov     qword ptr [rsp+370h+var_320], rax
0x18003e361  lea     rax, [rbp+250h+var_2A5]
0x18003e365  mov     [rsp+370h+pSid], rax
0x18003e36a  lea     rax, [rbp+250h+var_254]
0x18003e36e  mov     qword ptr [rsp+370h+var_330], rax; int
0x18003e373  lea     rax, [rbp+250h+var_2BC]
0x18003e377  mov     qword ptr [rsp+370h+var_338], rax
0x18003e37c  lea     rax, [rbp+250h+var_2A4]
0x18003e380  mov     qword ptr [rsp+370h+var_340], rax
0x18003e385  lea     rax, [rbp+250h+var_2BE]
0x18003e389  mov     qword ptr [rsp+370h+var_348], rax
0x18003e38e  lea     rax, [rbp+250h+var_2C8]
0x18003e392  mov     qword ptr [rsp+370h+var_350], rax; int
0x18003e397  lea     r8, [rbp+250h+var_68]
0x18003e39e  lea     rdx, byte_1801019C1
0x18003e3a5  mov     rcx, rbx
0x18003e3a8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U2@U?$_tlgWrapperByVal@$01@@U3@U2@U2@U2@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@4AEBU?$_tlgWrapperByVal@$01@@54443433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003e3ad  lea     rax, [rbp+250h+var_70]
0x18003e3b4  mov     [rbp+250h+var_150], rax
0x18003e3bb  lea     rax, [rbp+250h+var_2D0]
0x18003e3bf  mov     [rbp+250h+var_148], rax
0x18003e3c6  lea     rax, [rbp+250h+arg_10]
0x18003e3cd  mov     [rbp+250h+var_140], rax
0x18003e3d4  mov     [rbp+250h+var_138], rdi
0x18003e3db  lea     rax, [rbp+250h+var_298]
0x18003e3df  mov     [rbp+250h+var_130], rax
0x18003e3e6  lea     rax, [rbp+250h+var_2C0]
0x18003e3ea  mov     [rbp+250h+var_128], rax
0x18003e3f1  lea     rax, [rbp+250h+var_2BD]
0x18003e3f5  mov     [rbp+250h+var_120], rax
0x18003e3fc  lea     rax, [rbp+250h+var_248]
0x18003e400  mov     [rbp+250h+var_118], rax
0x18003e407  lea     rax, [rbp+250h+var_2BF]
0x18003e40b  mov     [rbp+250h+var_110], rax
0x18003e412  lea     rax, [rbp+250h+var_258]
0x18003e416  mov     [rbp+250h+var_108], rax
0x18003e41d  mov     [rbp+250h+var_100], 100h
0x18003e426  mov     [rbp+250h+var_2A0], rsi
0x18003e42a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18003e431  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18003e436  xor     edx, edx
0x18003e438  lea     rcx, [rbp+250h+var_2A0]
0x18003e43c  test    al, al
0x18003e43e  jz      short loc_18003E477
0x18003e440  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003e445  lea     r9, [rbp+250h+var_2A0]
0x18003e449  mov     edx, r14d
0x18003e44c  mov     rcx, r15
0x18003e44f  call    DoKeyAccessCheckWorkRequiringImpersonation
0x18003e454  mov     ebx, eax
0x18003e456  test    eax, eax
0x18003e458  jns     short loc_18003E4D2
0x18003e45a  mov     rcx, [rbp+258h]; this
0x18003e461  mov     r9d, eax; char *
0x18003e464  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18003e46b  mov     edx, 1A7Dh; void *
0x18003e470  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e475  jmp     short loc_18003E4C4
0x18003e477  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003e47c  lea     r9, [rbp+250h+var_2A0]
0x18003e480  mov     edx, r14d
0x18003e483  mov     rcx, r15
0x18003e486  call    DoKeyAccessCheckWorkRequiringImpersonation
0x18003e48b  mov     dword ptr [rbp+250h+var_2D0], eax
0x18003e48e  test    eax, eax
0x18003e490  jns     short loc_18003E4D2
0x18003e492  mov     eax, cs:dword_180122070
0x18003e498  cmp     eax, 2
0x18003e49b  jbe     short loc_18003E4C1
0x18003e49d  mov     eax, dword ptr [rbp+250h+var_2D0]
0x18003e4a0  mov     dword ptr [rbp+250h+var_2C8], eax
0x18003e4a3  lea     rax, [rbp+250h+var_2C8]
0x18003e4a7  mov     qword ptr [rsp+370h+var_350], rax
0x18003e4ac  xor     r9d, r9d
0x18003e4af  xor     r8d, r8d
0x18003e4b2  lea     rdx, byte_180101981
0x18003e4b9  mov     rcx, rbx
0x18003e4bc  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003e4c1  mov     ebx, dword ptr [rbp+250h+var_2D0]
0x18003e4c4  lea     rcx, [rbp+250h+var_2A0]
0x18003e4c8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003e4cd  jmp     loc_18003F1EC
0x18003e4d2  lea     rcx, [rbp+250h+var_2A0]
0x18003e4d6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003e4db  xorps   xmm0, xmm0
0x18003e4de  xor     eax, eax
0x18003e4e0  movups  [rbp+250h+var_F0], xmm0
0x18003e4e7  mov     [rbp+250h+var_E0], rax
0x18003e4ee  mov     r14d, [rdi+204h]
0x18003e4f5  mov     [rbp+250h+var_2BC], r14d
0x18003e4f9  movups  [rbp+250h+Buf2], xmm0
0x18003e4fd  lea     rbx, [rdi+238h]
0x18003e504  lea     r8d, [rax+10h]; Size
0x18003e508  lea     rdx, [rbp+250h+Buf2]; Buf2
0x18003e50c  mov     rcx, rbx; Buf1
0x18003e50f  call    memcmp_0
0x18003e514  neg     eax
0x18003e516  sbb     rax, rax
0x18003e519  and     rax, rbx
0x18003e51c  mov     [rbp+250h+var_268], rax
0x18003e520  mov     qword ptr [rbp+250h+Buf2], rdi
0x18003e524  xor     ebx, ebx
0x18003e526  mov     word ptr [rbp+250h+Buf2+8], 100h
0x18003e52c  mov     eax, 8009002Eh
0x18003e531  cmp     [rdi+200h], bl
0x18003e537  jnz     loc_18003E647
0x18003e53d  mov     r9, [rdi+148h]
0x18003e544  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18003e548  jnz     short loc_18003E586
0x18003e54a  mov     dword ptr [rbp+250h+var_2D0], 80090033h
0x18003e551  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18003e558  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18003e55d  test    al, al
0x18003e55f  jz      short loc_18003E56B
0x18003e561  mov     edx, 1AABh
0x18003e566  jmp     loc_18003F193
0x18003e56b  mov     eax, cs:dword_180122070
0x18003e571  cmp     eax, 2
0x18003e574  jbe     loc_18003F1DF
0x18003e57a  lea     rdx, dword_180101934
0x18003e581  jmp     loc_18003F1BE
0x18003e586  test    r9, r9
0x18003e589  jnz     short loc_18003E5CE
0x18003e58b  cmp     r14d, 1
0x18003e58f  jnz     loc_18003E64A
0x18003e595  mov     dword ptr [rbp+250h+var_2D0], eax
0x18003e598  mov     eax, cs:dword_180122070
0x18003e59e  cmp     eax, 3
0x18003e5a1  jbe     loc_18003E64A
0x18003e5a7  mov     eax, dword ptr [rbp+250h+var_2D0]
0x18003e5aa  mov     dword ptr [rbp+250h+var_2C8], eax
0x18003e5ad  lea     rax, [rbp+250h+var_2C8]
0x18003e5b1  mov     qword ptr [rsp+370h+var_350], rax
0x18003e5b6  xor     r8d, r8d
0x18003e5b9  lea     rdx, byte_1801018E5
0x18003e5c0  lea     rcx, dword_180122070
0x18003e5c7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003e5cc  jmp     short loc_18003E64A
0x18003e5ce  cmp     [rbp+250h+var_298], 8
0x18003e5d2  jnz     short loc_18003E5F6
0x18003e5d4  cmp     r14d, 1
0x18003e5d8  jz      short loc_18003E5F6
0x18003e5da  mov     rcx, [rdi+160h]
0x18003e5e1  mov     rax, [rcx]
0x18003e5e4  lea     rdx, [rdi+38h]
0x18003e5e8  xor     r8d, r8d
0x18003e5eb  mov     rax, [rax+10h]
0x18003e5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e5f4  jmp     short loc_18003E64A
0x18003e5f6  mov     eax, cs:dword_180122070
0x18003e5fc  cmp     eax, 5
0x18003e5ff  jbe     short loc_18003E631
0x18003e601  mov     rdx, 400000000000h
0x18003e60b  lea     rcx, dword_180122070
0x18003e612  call    _tlgKeywordOn
0x18003e617  test    al, al
0x18003e619  jz      short loc_18003E631
0x18003e61b  xor     r8d, r8d
0x18003e61e  lea     rdx, dword_1801018AC
0x18003e625  lea     rcx, dword_180122070
0x18003e62c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003e631  mov     rsi, [rdi+148h]
0x18003e638  mov     [rbp+250h+var_2C0], 1
0x18003e63c  call    ?Instance@PinCacheManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::PinCacheManager::Instance(void)
0x18003e641  mov     byte ptr [rax+58h], 1
  ... truncated ...
```
