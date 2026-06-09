# CFeatureOnDemandPackageContentProcessor::Process(uint,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ICbsUIHandler *,_CbsRequiredAction *,wchar_t * *)

- ea: `0x1800ab3c8`
- end: `0x1800ac98e`
- name: `?Process@CFeatureOnDemandPackageContentProcessor@@UEAAJIPEB_W000PEAUICbsUIHandler@@PEAW4_CbsRequiredAction@@PEAPEA_W@Z`
- size: `5574`
- prototype: `__int64 __fastcall(CFeatureOnDemandPackageContentProcessor *__hidden this, unsigned int, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, struct ICbsUIHandler *, enum _CbsRequiredAction *, wchar_t **)`
- caller_count: `1`
- callee_count: `36`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18019a4f0`

## callees

- `0x18000d910`
- `0x180010cc0`
- `0x180013250`
- `0x1800138b8`
- `0x180015420`
- `0x1800194bc`
- `0x180019bdc`
- `0x180019c10`
- `0x18001ef60`
- `0x1800261e0`
- `0x18002a448`
- `0x18002fa74`
- `0x180033f80`
- `0x18004a6d8`
- `0x18004b52c`
- `0x1800532d4`
- `0x180056e00`
- `0x180059a00`
- `0x18005aa38`
- `0x180093c4c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ab3c8`
- `0x1800ac994`
- `0x1800ad1f0`
- `0x1800bd218`
- `0x1800c2180`
- `0x1800c246c`
- `0x1800eb920`
- `0x18015ac3c`
- `0x180162674`
- `0x1801c0448`
- `0x1801c9e70`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800abc65`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800abc65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac0ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac157`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac194`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac1b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac66d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac6fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac0ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac157`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac194`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac1b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac66d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac6fc`

## string_xrefs

- `0x1800ab967`: `update.mum`
- `0x1800abb33`: `Failed adding payload path source`
- `0x1800ac379`: `Failed adding payload path source`
- `0x1800ab6f4`: `Failed setting reservicing sandbox path`
- `0x1800ac482`: `Failed adding package path source: {}`
- `0x1800ac93e`: `Failed to create sandbox`
- `0x1800ab7af`: `No install package found in ActionList: {}`
- `0x1800ac2e1`: `Failed to add lcu express path`
- `0x1800ac5bb`: `Failed to create package.`
- `0x1800ac8d5`: `Failed to create package.`
- `0x1800abcc1`: `Adding sandbox metadata source: {}{} for FOD install`

## pseudocode

```c
__int64 __fastcall CFeatureOnDemandPackageContentProcessor::Process(
        CFeatureOnDemandPackageContentProcessor *this,
        __int64 a2,
        wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        struct ICbsUIHandler *a7,
        enum _CbsRequiredAction *a8,
        wchar_t **a9)
{
  int v10; // r12d
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  unsigned __int64 v14; // r9
  int v15; // eax
  int v16; // eax
  __int64 v17; // r14
  int v18; // eax
  __int64 i; // rax
  __int64 j; // rcx
  __int64 v21; // rbx
  __int64 k; // rbx
  wchar_t *v23; // rsi
  bool v24; // zf
  int Package; // edi
  const struct _LUTF8_STRING *v26; // rdx
  int v27; // ecx
  wchar_t *v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  wchar_t *v34; // rdi
  int v35; // esi
  char IsEnabled; // al
  int v37; // esi
  __int64 m; // rdi
  int v39; // eax
  __int64 v40; // r8
  wchar_t *v41; // r12
  wchar_t *v42; // rdi
  __int64 v43; // rdi
  __int64 v44; // rax
  _BYTE *v45; // rsi
  wchar_t *v46; // rdi
  wchar_t *v47; // rax
  _BYTE *v48; // r12
  __int64 v49; // rdi
  __int64 v50; // rax
  _QWORD *v51; // r12
  _QWORD *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rcx
  wchar_t *v55; // rdi
  char v56; // al
  void *v57; // rcx
  char v58; // al
  void *v59; // rcx
  int v60; // eax
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // rdx
  wchar_t **v65; // rcx
  __int64 v66; // rdx
  __int64 v68; // rdx
  const wchar_t *v69; // rdx
  const wchar_t *v70; // rdx
  const wchar_t *v71; // rdx
  int InitPointer; // [rsp+20h] [rbp-E0h]
  wchar_t *v73; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v74; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v75; // [rsp+70h] [rbp-90h] BYREF
  int v76[2]; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v78; // [rsp+88h] [rbp-78h] BYREF
  __int64 v79; // [rsp+90h] [rbp-70h] BYREF
  char v80[8]; // [rsp+98h] [rbp-68h] BYREF
  char *v81; // [rsp+A0h] [rbp-60h]
  __int128 v82; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v83; // [rsp+B8h] [rbp-48h]
  wchar_t *v84; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v85; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t *v86; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v87; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t *v88; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *v89; // [rsp+E8h] [rbp-18h] BYREF
  const wchar_t *v90; // [rsp+F0h] [rbp-10h] BYREF
  CCbsPackage *v91; // [rsp+F8h] [rbp-8h] BYREF
  int v92[2]; // [rsp+100h] [rbp+0h] BYREF
  int v93[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v94; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v95[3]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v10 = 0;
  v86 = a3;
  v90 = a4;
  if ( a8 )
    *(_DWORD *)a8 = 0;
  if ( a9 )
    *a9 = 0;
  if ( LogAdapter::g_Logger )
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (__int64)LogAdapter::g_Logger,
      1,
      1,
      (__int64)"FOD: Process actionList: {}, sandbox: {}",
      (__int64)&v86,
      (__int64)&v90);
  v87 = 0;
  v83 = 0;
  v95[0] = &Windows::Rtl::PrivateHeapPool::`vftable';
  v82 = 0;
  v95[1] = 0;
  v95[2] = 0;
  v79 = 0;
  if ( *((_BYTE *)this - 40) )
    RevertImpersonate();
  v80[0] = 1;
  v81 = (char *)this - 80;
  v11 = ActionListParser::ReadActionList(v86, v95, &v87, &v82);
  v12 = v11;
  if ( v11 < 0 )
  {
    v93[0] = v11;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to load actions from {}",
        (__int64)&v86);
      v84 = (wchar_t *)v93;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v84);
    }
    v13 = 4010;
LABEL_17:
    v14 = v12;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
      (const char *)v14,
      InitPointer);
    goto LABEL_191;
  }
  if ( !*(_QWORD *)(*(_QWORD *)(v87 + 112) + 8LL) )
  {
    v12 = -2146498222;
    v92[0] = -2146498222;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"No download package found in ActionList: {}",
        (__int64)&v86);
      v84 = (wchar_t *)v92;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v84);
    }
    v13 = 4013;
    goto LABEL_17;
  }
  if ( *((_QWORD *)this - 4) && *(_BYTE *)(v87 + 161) )
  {
    v89 = 0;
    v15 = DuplicateParserString(
            (struct Windows::Rtl::IPoolAllocator *)v95,
            (const struct _LUTF8_STRING *)(v87 + 56),
            &v89);
    v12 = v15;
    if ( v15 < 0 )
    {
      v92[0] = v15;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to duplicate string");
        v84 = (wchar_t *)v92;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v84);
      }
      v13 = 4020;
      goto LABEL_17;
    }
    if ( !(unsigned __int8)StringsAreEqual(*((_QWORD *)this - 4), v89, 1) )
    {
      v12 = -2146498536;
      v92[0] = -2146498536;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"FOD: Mismatch between repository and OS, OS build: {}, Repository build: {}",
          (__int64)this - 32,
          (__int64)&v89);
        v84 = (wchar_t *)v92;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v84);
      }
      v13 = 4023;
      goto LABEL_17;
    }
  }
  v16 = DirectoryFromPath(v86);
  v12 = v16;
  if ( v16 < 0 )
  {
    v14 = (unsigned int)v16;
    v13 = 4026;
    goto LABEL_18;
  }
  v17 = v79;
  v18 = SczAllocFromSz(*((_QWORD *)this - 7) + 2352LL, v79);
  v12 = v18;
  if ( v18 < 0 )
  {
    v92[0] = v18;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed setting reservicing sandbox path");
      v84 = (wchar_t *)v92;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v84);
    }
    v13 = 4029;
    goto LABEL_17;
  }
  for ( i = **(_QWORD **)(v87 + 112); i; i = *(_QWORD *)(i + 256) )
  {
    for ( j = *(_QWORD *)(i + 240); j; j = *(_QWORD *)(j + 416) )
      *(_QWORD *)(*((_QWORD *)this - 7) + 1600LL) += *(_QWORD *)(j + 144);
  }
  v21 = *(_QWORD *)(v87 + 152);
  if ( !*(_QWORD *)(v21 + 64) )
  {
    v12 = -2146498222;
    v93[0] = -2146498222;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"No install package found in ActionList: {}",
        (__int64)&v86);
      v84 = (wchar_t *)v93;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v84);
    }
    v13 = 4043;
    goto LABEL_17;
  }
  for ( k = *(_QWORD *)(v21 + 56); ; k = *(_QWORD *)(k + 296) )
  {
    if ( !k )
      goto LABEL_190;
    v91 = 0;
    v23 = 0;
    v84 = 0;
    v85 = 0;
    v24 = *(_DWORD *)(k + 144) == 2;
    v75 = 0;
    v74 = 0;
    v73 = 0;
    if ( !v24 )
      goto LABEL_53;
    if ( *(_BYTE *)(k + 307) && *(_BYTE *)(k + 305) )
    {
      Package = DuplicateParserString(
                  (struct Windows::Rtl::IPoolAllocator *)v95,
                  (const struct _LUTF8_STRING *)(k + 88),
                  &v85);
      if ( Package < 0 )
      {
        v63 = 4064;
        goto LABEL_173;
      }
      Package = DuplicateParserString(
                  (struct Windows::Rtl::IPoolAllocator *)v95,
                  (const struct _LUTF8_STRING *)(k + 40),
                  &v73);
      if ( Package < 0 )
      {
        v63 = 4069;
        goto LABEL_173;
      }
      v23 = v73;
      v93[0] = 1;
    }
    else
    {
LABEL_53:
      v26 = (const struct _LUTF8_STRING *)(*(_QWORD *)(k + 256) + 56LL);
      v93[0] = 0;
      Package = DuplicateParserString((struct Windows::Rtl::IPoolAllocator *)v95, v26, &v85);
      if ( Package < 0 )
      {
        v63 = 4075;
        goto LABEL_173;
      }
    }
    Package = CCbsSession::CreateSessionSandbox(
                *((CCbsSession **)this - 7),
                *(void **)(*((_QWORD *)this - 7) + 1128LL),
                v85,
                &v75);
    if ( Package < 0 )
    {
      v92[0] = Package;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create sandbox");
        *(_QWORD *)v76 = v92;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v76);
      }
      v63 = 4083;
      goto LABEL_173;
    }
    Package = SczAllocFormatted(&v74, L"%ws%ws", *((_QWORD *)this - 6), v85);
    if ( Package < 0 )
    {
      v63 = 4085;
      goto LABEL_173;
    }
    if ( v93[0] == 1 )
    {
      if ( (unsigned __int8)DoesDirectoryExist(v74, 0)
        || (Package = SczAllocCombinePath2Sz(&v74, v17, v85), Package >= 0) )
      {
        Package = SczEnsureBackslashTerminated(&v74);
        if ( Package < 0 )
        {
          v63 = 4095;
        }
        else
        {
          if ( *(_DWORD *)(k + 140) == 6 && *(_DWORD *)(k + 136) != 4 )
          {
            Package = SczAllocFromSz(*((_QWORD *)this - 7) + 2344LL, v74);
            if ( Package < 0 )
            {
              v92[0] = Package;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to add lcu express path");
                v73 = (wchar_t *)v92;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v73);
              }
              v63 = 4104;
              goto LABEL_173;
            }
          }
          Package = SczAllocConcatSz(&v74, L"update.mum");
          if ( Package >= 0 )
            goto LABEL_64;
          v63 = 4107;
        }
      }
      else
      {
        v63 = 4092;
      }
LABEL_173:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v63,
        (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
        (const char *)(unsigned int)Package,
        InitPointer);
      goto LABEL_174;
    }
LABEL_64:
    v27 = *(_DWORD *)(k + 140);
    if ( (unsigned int)(v27 - 2) > 1 )
    {
      if ( v27 != 5 )
      {
        if ( v27 == 6 )
        {
          v30 = *((_QWORD *)this - 3);
          v31 = *(_QWORD *)(v30 + 40);
          v32 = v31 + 8LL * *(_QWORD *)(v30 + 24);
          while ( v31 != v32 )
          {
            if ( (**(_BYTE **)v31 & 4) != 0 )
              *(_BYTE *)(*(_QWORD *)v31 + 168LL) = 0;
            v31 += 8;
          }
        }
        else if ( v27 != 13 )
        {
          v12 = -2146498221;
          v92[0] = -2146498221;
          if ( LogAdapter::g_Logger )
          {
            v28 = (wchar_t *)&qword_1802EB518;
            if ( *((_QWORD *)v91 + 15) )
              v28 = (wchar_t *)*((_QWORD *)v91 + 15);
            v73 = v28;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"FOD: Invalid FOD package reason type. cab: {}, package: {}",
              (__int64)&v85,
              (__int64)&v73);
            *(_QWORD *)v93 = v92;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v93);
          }
          v29 = 4415;
LABEL_222:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v29,
            (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
            (const char *)v12,
            InitPointer);
LABEL_223:
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v75);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v91);
          goto LABEL_191;
        }
      }
      if ( v23 )
      {
        v33 = *((_QWORD *)this - 6);
        v73 = 0;
        Package = SczAllocFormatted(&v73, L"%ws%ws", v33, v23);
        if ( Package < 0 )
        {
          v64 = 4257;
          goto LABEL_183;
        }
        v34 = v73;
        v35 = CCbsSession::AddSource(*((CCbsSession **)this - 7), 1, 2u, v73, 0);
        if ( (unsigned int)(v35 + 2147024894) <= 1 )
        {
          Package = SczAllocCombinePath2Sz(&v73, v17, v85);
          if ( Package < 0 )
          {
            v64 = 4268;
            goto LABEL_183;
          }
          v34 = v73;
          v35 = CCbsSession::AddSource(*((CCbsSession **)this - 7), 1, 2u, v73, 0);
          if ( v35 == -2147024894 )
            goto LABEL_88;
        }
        if ( v35 == -2147024893 )
        {
LABEL_88:
          *(_QWORD *)v92 = v34;
          if ( LogAdapter::g_Logger )
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              1,
              1,
              (__int64)"Express payload folder '{}' doesn't exist, this could happen if LCU doesn't contain binary change"
                       " for the FOD, continue",
              (__int64)v92);
        }
        else if ( v35 < 0 )
        {
          v92[0] = v35;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding payload path source");
            *(_QWORD *)v93 = v92;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v93);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x10B9,
            (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
            (const char *)(unsigned int)v35,
            InitPointer);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v73);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v75);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v91);
          v12 = v35;
          goto LABEL_191;
        }
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v73);
      }
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MultihopWithMultipleBaselineAlternateSource>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MultihopWithMultipleBaselineAlternateSource>::GetImpl'::`2'::impl);
      v37 = (int)v74;
      if ( IsEnabled )
      {
        if ( *(_BYTE *)(k + 307) && *(_DWORD *)(k + 140) == 6 && *(_DWORD *)(k + 136) != 4 )
        {
          for ( m = *(_QWORD *)(k + 256); m; m = *(_QWORD *)(m + 128) )
          {
            v88 = 0;
            v39 = DuplicateParserString(
                    (struct Windows::Rtl::IPoolAllocator *)v95,
                    (const struct _LUTF8_STRING *)(m + 80),
                    &v88);
            v10 = v39;
            if ( v39 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x10CC,
                (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
                (const char *)(unsigned int)v39,
                InitPointer);
              goto LABEL_189;
            }
            if ( (unsigned int)_o__wcsicmp(v88, v85) )
            {
              v40 = *((_QWORD *)this - 6);
              v73 = 0;
              v10 = SczAllocFormatted(&v73, L"%ws%ws", v40, v88);
              if ( v10 < 0 )
              {
                v66 = 4316;
                goto LABEL_188;
              }
              if ( LogAdapter::g_Logger )
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  1,
                  (__int64)"Adding sandbox metadata source: {}{} for FOD install",
                  (__int64)this - 48,
                  (__int64)&v88);
              v10 = CCbsSession::AddSource(*((CCbsSession **)this - 7), 1, 2u, v73, 0);
              if ( v10 < 0 )
              {
                v92[0] = v10;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed adding payload path source");
                  *(_QWORD *)v93 = v92;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)v93);
                }
                v66 = 4327;
                goto LABEL_188;
              }
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v73);
            }
          }
        }
        v41 = (wchar_t *)(k + 136);
        goto LABEL_110;
      }
      v41 = (wchar_t *)(k + 136);
      v24 = *(_DWORD *)(k + 136) == 4;
      *(_QWORD *)v92 = k + 136;
      if ( !v24 )
      {
LABEL_110:
        v94 = 0;
        if ( *(_BYTE *)(k + 308) )
        {
          v73 = 0;
          Package = DuplicateParserString(
                      (struct Windows::Rtl::IPoolAllocator *)v95,
                      (const struct _LUTF8_STRING *)(k + 112),
                      &v73);
          if ( Package < 0 )
          {
            v68 = 4357;
            goto LABEL_200;
          }
          Package = SczAllocCombinePath2Sz(&v94, *((_QWORD *)this - 6), v73);
          if ( Package < 0 )
          {
            v68 = 4358;
            goto LABEL_200;
          }
          if ( LogAdapter::g_Logger )
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              1,
              1,
              (__int64)"ActionList: Using TurboContainer: {}",
              (__int64)&v94);
        }
        v43 = *((_QWORD *)this - 7);
        Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v91);
        InitPointer = v37;
        Package = CCbsSession::InternalCreatePackage(
                    v43,
                    *(_QWORD *)(*((_QWORD *)this - 7) + 1128LL),
                    8,
                    (unsigned int)v93[0]);
        if ( Package < 0 )
        {
          v93[0] = Package;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create package.");
            v73 = (wchar_t *)v93;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v73);
          }
          v68 = 4375;
LABEL_200:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v68,
            (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
            (const char *)(unsigned int)Package,
            InitPointer);
          v65 = (wchar_t **)&v94;
LABEL_184:
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v65);
          goto LABEL_174;
        }
        if ( *(_DWORD *)v41 )
        {
          if ( *(_DWORD *)v41 == 5 )
          {
            *((_BYTE *)v91 + 1062) = 1;
          }
          else
          {
            if ( *(_DWORD *)v41 != 4 )
            {
              v12 = -2146498218;
              v92[0] = -2146498218;
              if ( LogAdapter::g_Logger )
              {
                v69 = &qword_1802EB518;
                if ( *((_QWORD *)v91 + 15) )
                  v69 = (const wchar_t *)*((_QWORD *)v91 + 15);
                *(_QWORD *)v76 = v69;
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (__int64)"FOD: Invalid FOD package action type. cab: {}, package: {}",
                  (__int64)&v85,
                  (__int64)v76);
                v73 = (wchar_t *)v92;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)&v73);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1139,
                (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
                (const char *)0x800F0956LL,
                InitPointer);
              Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v94);
              goto LABEL_223;
            }
            *(_WORD *)((char *)v91 + 1061) = 257;
          }
        }
        if ( *(_DWORD *)(k + 140) == 6 )
        {
          v10 = 0;
          if ( !CCbsPackage::IsPartialBaselinePackage(v91) && *(_QWORD *)(k + 264) > 1u )
            *(_BYTE *)(*((_QWORD *)this - 7) + 2255LL) = 1;
        }
        else
        {
          v10 = 0;
        }
        Package = CCbsSession::AddLCUOrGDRToInstall(*((CCbsSession **)this - 7), v91);
        if ( Package < 0 )
        {
          v68 = 4404;
          goto LABEL_200;
        }
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v94);
        goto LABEL_170;
      }
      v73 = 0;
      Package = DirectoryFromPath(v74);
      if ( Package >= 0 )
      {
        v42 = v73;
        v10 = CCbsSession::AddSource(*((CCbsSession **)this - 7), 1, 2u, v73, 0);
        if ( v10 < 0 )
        {
          v92[0] = v10;
          if ( LogAdapter::g_Logger )
          {
            *(_QWORD *)v93 = v42;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed adding package path source: {}",
              (__int64)v93);
            *(_QWORD *)v76 = v92;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v76);
          }
          v66 = 4349;
LABEL_188:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v66,
            (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
            (const char *)(unsigned int)v10,
            InitPointer);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v73);
LABEL_189:
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v75);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v91);
LABEL_190:
          v12 = v10;
          goto LABEL_191;
        }
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v73);
        v41 = *(wchar_t **)v92;
        goto LABEL_110;
      }
      v64 = 4341;
LABEL_183:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v64,
        (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
        (const char *)(unsigned int)Package,
        InitPointer);
      v65 = &v73;
      goto LABEL_184;
    }
    Package = DuplicateParserString(
                (struct Windows::Rtl::IPoolAllocator *)v95,
                (const struct _LUTF8_STRING *)(k + 176),
                &v84);
    if ( Package < 0 )
    {
      v63 = 4115;
      goto LABEL_173;
    }
    v44 = *((_QWORD *)this - 3);
    v45 = 0;
    v46 = *(wchar_t **)(v44 + 40);
    v47 = &v46[4 * *(_QWORD *)(v44 + 24)];
    v73 = v47;
    while ( v46 != v47 )
    {
      v48 = *(_BYTE **)v46;
      if ( (**(_BYTE **)v46 & 2) != 0 )
      {
        if ( (unsigned __int8)StringsAreEqual(v84, *(_QWORD *)(*((_QWORD *)v48 + 1) + 48LL), 1) )
        {
          v45 = v48;
          v48[170] = *((_BYTE *)this - 16);
          break;
        }
        v47 = v73;
      }
      v46 += 4;
    }
    v49 = *((_QWORD *)this - 7);
    v10 = 0;
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v91);
    InitPointer = (int)v74;
    Package = CCbsSession::InternalCreatePackage(
                v49,
                *(_QWORD *)(*((_QWORD *)this - 7) + 1128LL),
                8,
                (unsigned int)v93[0]);
    if ( Package < 0 )
    {
      v93[0] = Package;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create package.");
        *(_QWORD *)v76 = v93;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v76);
      }
      v63 = 4150;
      goto LABEL_173;
    }
    if ( !v45 )
      break;
LABEL_163:
    v60 = *(_DWORD *)(k + 140);
    if ( v60 == 2 )
    {
      if ( CCbsPackage::IsSatellitePackage(v91) )
      {
        v12 = -2147418113;
        v92[0] = -2147418113;
        if ( LogAdapter::g_Logger )
        {
          v70 = &qword_1802EB518;
          if ( *(_QWORD *)(v61 + 120) )
            v70 = *(const wchar_t **)(v61 + 120);
          *(_QWORD *)v76 = v70;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"FOD: Package is a satellite package but reported by actionList as standalone. Cab: {}, package: {}",
            (__int64)&v85,
            (__int64)v76);
          v73 = (wchar_t *)v92;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v73);
        }
        v29 = 4213;
        goto LABEL_222;
      }
      v73 = (wchar_t *)v61;
      Package = CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::Add(v45 + 40, &v73);
      if ( Package < 0 )
      {
        v63 = 4215;
        goto LABEL_173;
      }
      v45[168] = 0;
      *(_DWORD *)(*((_QWORD *)this - 7) + 1160LL) |= *((_BYTE *)this - 16) != 0 ? 2 : 16;
    }
    else if ( v60 == 3 )
    {
      if ( !CCbsPackage::IsSatellitePackage(v91) )
      {
        v12 = -2147418113;
        v92[0] = -2147418113;
        if ( LogAdapter::g_Logger )
        {
          v71 = &qword_1802EB518;
          if ( *(_QWORD *)(v62 + 120) )
            v71 = *(const wchar_t **)(v62 + 120);
          *(_QWORD *)v76 = v71;
          LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"FOD: Package is a not satellite package but reported by actionList as one. Cab: {}, package: {}",
            (__int64)&v85,
            (__int64)v76);
          v73 = (wchar_t *)v92;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v73);
        }
        v29 = 4225;
        goto LABEL_222;
      }
      v73 = (wchar_t *)v62;
      Package = CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::Add(v45 + 104, &v73);
      if ( Package < 0 )
      {
        v63 = 4227;
        goto LABEL_173;
      }
    }
LABEL_170:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v75);
    Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v91);
  }
  if ( !CCbsPackage::IsSatellitePackage(v91) )
  {
LABEL_219:
    v12 = -2146498221;
    v92[0] = -2146498221;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"FOD: Package downloaded does not match any of the requested feature: {}",
        (__int64)&v84);
      *(_QWORD *)v76 = v92;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v76);
    }
    v29 = 4207;
    goto LABEL_222;
  }
  v50 = *((_QWORD *)this - 3);
  v51 = *(_QWORD **)(v50 + 40);
  v52 = &v51[*(_QWORD *)(v50 + 24)];
  *(_QWORD *)v93 = v52;
  while ( 2 )
  {
    if ( v51 == v52 )
      goto LABEL_219;
    v45 = (_BYTE *)*v51;
    if ( (*(_BYTE *)*v51 & 2) == 0 )
      goto LABEL_157;
    v53 = *((_QWORD *)v45 + 1);
    if ( v53 )
    {
      v54 = v53 + 8 + *(int *)(*(_QWORD *)(v53 + 8) + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 8LL))(v54);
      v55 = (wchar_t *)*((_QWORD *)v45 + 1);
    }
    else
    {
      v55 = 0;
    }
    *(_QWORD *)v92 = v55;
    v73 = v55;
    if ( !CCbsPackage::IsArchSatellitePackage(v91) )
      goto LABEL_151;
    pv = 0;
    InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&pv);
    Package = CCbsCapability::GetProperty(v55, *((_QWORD *)this - 7), *(_QWORD *)(*((_QWORD *)this - 7) + 1128LL), 46);
    if ( Package >= 0 )
    {
      v56 = StringsAreEqual(*((_QWORD *)v91 + 14) + 648LL, pv, 1);
      v57 = pv;
      if ( v56 )
      {
        v10 = 0;
        v45[170] = *((_BYTE *)this - 16);
        if ( v57 )
        {
          CoTaskMemFree(v57);
          pv = 0;
        }
        goto LABEL_162;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v55 = *(wchar_t **)v92;
LABEL_151:
      if ( CCbsPackage::IsLanguageSatellitePackage(v91) )
      {
        v78 = 0;
        InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v78);
        Package = CCbsCapability::GetProperty(
                    v55,
                    *((_QWORD *)this - 7),
                    *(_QWORD *)(*((_QWORD *)this - 7) + 1128LL),
                    45);
        if ( Package < 0 )
        {
          v92[0] = Package;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get declareArchitecture");
            *(_QWORD *)v76 = v92;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v76);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1062,
            (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
            (const char *)(unsigned int)Package,
            InitPointer);
          if ( v78 )
          {
            CoTaskMemFree(v78);
            v78 = 0;
          }
          goto LABEL_214;
        }
        v58 = StringsAreEqual(*((_QWORD *)v91 + 14) + 584LL, v78, 1);
        v59 = v78;
        if ( v58 )
        {
          v10 = 0;
          v45[170] = *((_BYTE *)this - 16);
          if ( v59 )
          {
            CoTaskMemFree(v59);
            v78 = 0;
          }
LABEL_162:
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v73);
          goto LABEL_163;
        }
        if ( v78 )
        {
          CoTaskMemFree(v78);
          v78 = 0;
        }
      }
      Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v73);
      v52 = *(_QWORD **)v93;
LABEL_157:
      ++v51;
      continue;
    }
    break;
  }
  v92[0] = Package;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get declareLanguage");
    *(_QWORD *)v76 = v92;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)v76);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x104E,
    (unsigned int)"onecore\\base\\cbs\\core\\capabilitymanager.cpp",
    (const char *)(unsigned int)Package,
    InitPointer);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
LABEL_214:
  Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v73);
LABEL_174:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v74);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v75);
  Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v91);
  v12 = Package;
LABEL_191:
  Windows::Detail::OnBlockExitImpl__CFeatureOnDemandPackageContentProcessor::Process_::_2_::_lambda_1___::_OnBlockExitImpl__CFeatureOnDemandPackageContentProcessor::Process_::_2_::_lambda_1___(v80);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v79);
  Windows::Rtl::PrivateHeapPool::~PrivateHeapPool((Windows::Rtl::PrivateHeapPool *)v95);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v82);
  return v12;
}

```

## disassembly

```asm
0x1800ab3c8  mov     [rsp-8+arg_8], rbx
0x1800ab3cd  push    rbp
0x1800ab3ce  push    rsi
0x1800ab3cf  push    rdi
0x1800ab3d0  push    r12
0x1800ab3d2  push    r13
0x1800ab3d4  push    r14
0x1800ab3d6  push    r15
0x1800ab3d8  lea     rbp, [rsp-40h]
0x1800ab3dd  sub     rsp, 140h
0x1800ab3e4  mov     rax, cs:__security_cookie
0x1800ab3eb  xor     rax, rsp
0x1800ab3ee  mov     [rbp+70h+var_40], rax
0x1800ab3f2  mov     rax, [rbp+70h+arg_40]
0x1800ab3f9  mov     r13, rcx
0x1800ab3fc  mov     rcx, [rbp+70h+arg_38]
0x1800ab403  xor     r12d, r12d
0x1800ab406  mov     [rbp+70h+var_A0], r8
0x1800ab40a  mov     [rbp+70h+var_80], r9
0x1800ab40e  test    rcx, rcx
0x1800ab411  jz      short loc_1800AB416
0x1800ab413  mov     [rcx], r12d
0x1800ab416  test    rax, rax
0x1800ab419  jz      short loc_1800AB41E
0x1800ab41b  mov     [rax], r12
0x1800ab41e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ab425  test    rcx, rcx
0x1800ab428  jz      short loc_1800AB451
0x1800ab42a  lea     rax, [rbp+70h+var_80]
0x1800ab42e  mov     r8d, 1
0x1800ab434  mov     [rsp+170h+var_148], rax
0x1800ab439  lea     r9, aFodProcessActi; "FOD: Process actionList: {}, sandbox: {"...
0x1800ab440  lea     rax, [rbp+70h+var_A0]
0x1800ab444  mov     dl, r8b
0x1800ab447  mov     [rsp+170h+var_150], rax; int
0x1800ab44c  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800ab451  xor     eax, eax
0x1800ab453  mov     [rbp+70h+var_98], r12
0x1800ab457  mov     [rbp+70h+var_B8], rax
0x1800ab45b  lea     rbx, [r13-50h]
0x1800ab45f  lea     rax, ??_7PrivateHeapPool@Rtl@Windows@@6B@; const Windows::Rtl::PrivateHeapPool::`vftable'
0x1800ab466  xorps   xmm0, xmm0
0x1800ab469  mov     [rbp+70h+var_58], rax
0x1800ab46d  movups  [rbp+70h+var_C8], xmm0
0x1800ab471  mov     [rbp+70h+var_50], r12
0x1800ab475  mov     [rbp+70h+var_48], r12
0x1800ab479  mov     [rbp+70h+var_E0], r12
0x1800ab47d  cmp     [rbx+28h], r12b
0x1800ab481  jz      short loc_1800AB488
0x1800ab483  call    RevertImpersonate
0x1800ab488  mov     rcx, [rbp+70h+var_A0]
0x1800ab48c  lea     r9, [rbp+70h+var_C8]
0x1800ab490  lea     r8, [rbp+70h+var_98]
0x1800ab494  mov     [rbp+70h+var_D8], 1
0x1800ab498  lea     rdx, [rbp+70h+var_58]
0x1800ab49c  mov     [rbp+70h+var_D0], rbx
0x1800ab4a0  call    ?ReadActionList@ActionListParser@@YAJQEB_WAEAVIPoolAllocator@Rtl@Windows@@PEAPEAUActionListDocument@1@PEAV?$Auto@U_LBLOB@@@4@@Z; ActionListParser::ReadActionList(wchar_t const * const,Windows::Rtl::IPoolAllocator &,ActionListParser::ActionListDocument * *,Windows::Auto<_LBLOB> *)
0x1800ab4a5  mov     ebx, eax
0x1800ab4a7  test    eax, eax
0x1800ab4a9  jns     short loc_1800AB50A
0x1800ab4ab  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ab4b2  mov     [rbp+70h+var_68], eax
0x1800ab4b5  test    rcx, rcx
0x1800ab4b8  jz      short loc_1800AB503
0x1800ab4ba  lea     rax, [rbp+70h+var_A0]
0x1800ab4be  mov     r15d, 3
0x1800ab4c4  mov     r8d, r15d
0x1800ab4c7  mov     [rsp+170h+var_150], rax
0x1800ab4cc  lea     r9, aFailedToLoadAc_2; "Failed to load actions from {}"
0x1800ab4d3  xor     edx, edx
0x1800ab4d5  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800ab4da  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ab4e1  lea     rax, [rbp+70h+var_68]
0x1800ab4e5  mov     [rbp+70h+var_B0], rax
0x1800ab4e9  lea     r9, asc_1802EE7AC; ": {}"
0x1800ab4f0  lea     rax, [rbp+70h+var_B0]
0x1800ab4f4  mov     r8d, r15d
0x1800ab4f7  mov     dl, 1
0x1800ab4f9  mov     [rsp+170h+var_150], rax
0x1800ab4fe  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ab503  mov     edx, 0FAAh
0x1800ab508  jmp     short loc_1800AB57A
0x1800ab50a  mov     rdx, [rbp+70h+var_98]
0x1800ab50e  mov     rax, [rdx+70h]
0x1800ab512  cmp     [rax+8], r12
0x1800ab516  jnz     short loc_1800AB592
0x1800ab518  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ab51f  mov     ebx, 800F0952h
0x1800ab524  mov     [rbp+70h+var_70], ebx
0x1800ab527  test    rcx, rcx
0x1800ab52a  jz      short loc_1800AB575
0x1800ab52c  lea     rax, [rbp+70h+var_A0]
0x1800ab530  mov     r15d, 3
0x1800ab536  mov     r8d, r15d
0x1800ab539  mov     [rsp+170h+var_150], rax
0x1800ab53e  lea     r9, aNoDownloadPack; "No download package found in ActionList"...
0x1800ab545  xor     edx, edx
0x1800ab547  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800ab54c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ab553  lea     rax, [rbp+70h+var_70]
0x1800ab557  mov     [rbp+70h+var_B0], rax
0x1800ab55b  lea     r9, asc_1802EE7AC; ": {}"
0x1800ab562  lea     rax, [rbp+70h+var_B0]
0x1800ab566  mov     r8d, r15d
0x1800ab569  mov     dl, 1
0x1800ab56b  mov     [rsp+170h+var_150], rax; int
0x1800ab570  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ab575  mov     edx, 0FADh; void *
0x1800ab57a  mov     r9d, ebx; char *
0x1800ab57d  mov     rcx, [rbp+78h]; this
0x1800ab581  lea     r8, aOnecoreBaseCbs_141; "onecore\\base\\cbs\\core\\capabilityman"...
0x1800ab588  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab58d  jmp     loc_1800AC3F5
0x1800ab592  lea     rdi, [r13-20h]
0x1800ab596  cmp     [rdi], r12
0x1800ab599  jz      loc_1800AB6A2
0x1800ab59f  cmp     [rdx+0A1h], r12b
0x1800ab5a6  jz      loc_1800AB6A2
0x1800ab5ac  add     rdx, 38h ; '8'; struct _LUTF8_STRING *
0x1800ab5b0  mov     [rbp+70h+var_88], r12
0x1800ab5b4  lea     r8, [rbp+70h+var_88]; wchar_t **
0x1800ab5b8  lea     rcx, [rbp+70h+var_58]; struct Windows::Rtl::IPoolAllocator *
0x1800ab5bc  call    ?DuplicateParserString@@YAJAEAVIPoolAllocator@Rtl@Windows@@AEBU_LUTF8_STRING@@PEAPEA_W@Z; DuplicateParserString(Windows::Rtl::IPoolAllocator &,_LUTF8_STRING const &,wchar_t * *)
0x1800ab5c1  mov     ebx, eax
0x1800ab5c3  test    eax, eax
0x1800ab5c5  jns     short loc_1800AB620
0x1800ab5c7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ab5ce  mov     [rbp+70h+var_70], eax
0x1800ab5d1  test    rcx, rcx
0x1800ab5d4  jz      short loc_1800AB616
0x1800ab5d6  mov     r15d, 3
0x1800ab5dc  lea     r9, aFailedToDuplic; "Failed to duplicate string"
0x1800ab5e3  mov     r8d, r15d
0x1800ab5e6  xor     edx, edx
0x1800ab5e8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800ab5ed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ab5f4  lea     rax, [rbp+70h+var_70]
0x1800ab5f8  mov     [rbp+70h+var_B0], rax
0x1800ab5fc  lea     r9, asc_1802EE7AC; ": {}"
0x1800ab603  lea     rax, [rbp+70h+var_B0]
0x1800ab607  mov     r8d, r15d
0x1800ab60a  mov     dl, 1
0x1800ab60c  mov     [rsp+170h+var_150], rax
0x1800ab611  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ab616  mov     edx, 0FB4h
0x1800ab61b  jmp     loc_1800AB57A
0x1800ab620  mov     rdx, [rbp+70h+var_88]
0x1800ab624  mov     r8d, 1
0x1800ab62a  mov     rcx, [rdi]
0x1800ab62d  call    StringsAreEqual
0x1800ab632  test    al, al
0x1800ab634  jnz     short loc_1800AB6A2
0x1800ab636  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ab63d  mov     ebx, 800F0818h
0x1800ab642  mov     [rbp+70h+var_70], ebx
0x1800ab645  test    rcx, rcx
0x1800ab648  jz      short loc_1800AB698
0x1800ab64a  lea     rax, [rbp+70h+var_88]
0x1800ab64e  mov     r15d, 3
0x1800ab654  mov     [rsp+170h+var_148], rax
0x1800ab659  lea     r9, aFodMismatchBet; "FOD: Mismatch between repository and OS"...
0x1800ab660  mov     r8d, r15d
0x1800ab663  mov     [rsp+170h+var_150], rdi
0x1800ab668  xor     edx, edx
0x1800ab66a  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800ab66f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ab676  lea     rax, [rbp+70h+var_70]
0x1800ab67a  mov     [rbp+70h+var_B0], rax
0x1800ab67e  lea     r9, asc_1802EE7AC; ": {}"
0x1800ab685  lea     rax, [rbp+70h+var_B0]
0x1800ab689  mov     r8d, r15d
0x1800ab68c  mov     dl, 1
0x1800ab68e  mov     [rsp+170h+var_150], rax
0x1800ab693  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ab698  mov     edx, 0FB7h
0x1800ab69d  jmp     loc_1800AB57A
0x1800ab6a2  mov     rcx, [rbp+70h+var_A0]; wchar_t *
0x1800ab6a6  lea     rdx, [rbp+70h+var_E0]
0x1800ab6aa  call    DirectoryFromPath
0x1800ab6af  mov     ebx, eax
0x1800ab6b1  test    eax, eax
0x1800ab6b3  jns     short loc_1800AB6C2
0x1800ab6b5  mov     r9d, eax
0x1800ab6b8  mov     edx, 0FBAh
0x1800ab6bd  jmp     loc_1800AB57D
0x1800ab6c2  mov     rcx, [r13-38h]
0x1800ab6c6  mov     r14, [rbp+70h+var_E0]
0x1800ab6ca  add     rcx, 930h
0x1800ab6d1  mov     rdx, r14
0x1800ab6d4  call    SczAllocFromSz
0x1800ab6d9  mov     ebx, eax
0x1800ab6db  test    eax, eax
0x1800ab6dd  jns     short loc_1800AB738
0x1800ab6df  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ab6e6  mov     [rbp+70h+var_70], eax
0x1800ab6e9  test    rcx, rcx
0x1800ab6ec  jz      short loc_1800AB72E
0x1800ab6ee  mov     r15d, 3
0x1800ab6f4  lea     r9, aFailedSettingR_6; "Failed setting reservicing sandbox path"
0x1800ab6fb  mov     r8d, r15d
0x1800ab6fe  xor     edx, edx
0x1800ab700  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800ab705  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ab70c  lea     rax, [rbp+70h+var_70]
0x1800ab710  mov     [rbp+70h+var_B0], rax
0x1800ab714  lea     r9, asc_1802EE7AC; ": {}"
0x1800ab71b  lea     rax, [rbp+70h+var_B0]
0x1800ab71f  mov     r8d, r15d
0x1800ab722  mov     dl, 1
0x1800ab724  mov     [rsp+170h+var_150], rax
0x1800ab729  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ab72e  mov     edx, 0FBDh
0x1800ab733  jmp     loc_1800AB57A
0x1800ab738  mov     rax, [rbp+70h+var_98]
0x1800ab73c  mov     rax, [rax+70h]
0x1800ab740  mov     rax, [rax]
0x1800ab743  test    rax, rax
0x1800ab746  jz      short loc_1800AB778
0x1800ab748  mov     rcx, [rax+0F0h]
0x1800ab74f  test    rcx, rcx
0x1800ab752  jz      short loc_1800AB76F
0x1800ab754  mov     rdx, [rcx+90h]
0x1800ab75b  mov     r8, [r13-38h]
0x1800ab75f  add     [r8+640h], rdx
0x1800ab766  mov     rcx, [rcx+1A0h]
0x1800ab76d  jmp     short loc_1800AB74F
0x1800ab76f  mov     rax, [rax+100h]
0x1800ab776  jmp     short loc_1800AB743
0x1800ab778  mov     rax, [rbp+70h+var_98]
0x1800ab77c  mov     rbx, [rax+98h]
0x1800ab783  cmp     [rbx+40h], r12
0x1800ab787  jnz     short loc_1800AB7F0
0x1800ab789  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ab790  mov     ebx, 800F0952h
0x1800ab795  mov     [rbp+70h+var_68], ebx
0x1800ab798  test    rcx, rcx
0x1800ab79b  jz      short loc_1800AB7E6
0x1800ab79d  lea     rax, [rbp+70h+var_A0]
0x1800ab7a1  mov     r15d, 3
0x1800ab7a7  mov     r8d, r15d
0x1800ab7aa  mov     [rsp+170h+var_150], rax
0x1800ab7af  lea     r9, aNoInstallPacka_0; "No install package found in ActionList:"...
0x1800ab7b6  xor     edx, edx
0x1800ab7b8  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800ab7bd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ab7c4  lea     rax, [rbp+70h+var_68]
0x1800ab7c8  mov     [rbp+70h+var_B0], rax
0x1800ab7cc  lea     r9, asc_1802EE7AC; ": {}"
0x1800ab7d3  lea     rax, [rbp+70h+var_B0]
0x1800ab7d7  mov     r8d, r15d
0x1800ab7da  mov     dl, 1
0x1800ab7dc  mov     [rsp+170h+var_150], rax
0x1800ab7e1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ab7e6  mov     edx, 0FCBh
0x1800ab7eb  jmp     loc_1800AB57A
0x1800ab7f0  mov     rbx, [rbx+38h]
0x1800ab7f4  mov     r15d, 3
0x1800ab7fa  test    rbx, rbx
0x1800ab7fd  jz      loc_1800AC3F2
0x1800ab803  mov     [rbp+70h+var_78], r12
0x1800ab807  mov     rsi, r12
0x1800ab80a  mov     [rbp+70h+var_B0], r12
0x1800ab80e  mov     [rbp+70h+var_A8], r12
0x1800ab812  cmp     dword ptr [rbx+90h], 2
0x1800ab819  mov     [rsp+170h+var_100], r12
0x1800ab81e  mov     [rsp+170h+var_108], r12
0x1800ab823  mov     [rsp+170h+var_110], r12
0x1800ab828  jnz     short loc_1800AB881
0x1800ab82a  cmp     [rbx+133h], r12b
0x1800ab831  jz      short loc_1800AB881
0x1800ab833  cmp     [rbx+131h], r12b
0x1800ab83a  jz      short loc_1800AB881
0x1800ab83c  lea     rdx, [rbx+58h]; struct _LUTF8_STRING *
0x1800ab840  lea     r8, [rbp+70h+var_A8]; wchar_t **
0x1800ab844  lea     rcx, [rbp+70h+var_58]; struct Windows::Rtl::IPoolAllocator *
0x1800ab848  call    ?DuplicateParserString@@YAJAEAVIPoolAllocator@Rtl@Windows@@AEBU_LUTF8_STRING@@PEAPEA_W@Z; DuplicateParserString(Windows::Rtl::IPoolAllocator &,_LUTF8_STRING const &,wchar_t * *)
0x1800ab84d  mov     edi, eax
0x1800ab84f  test    eax, eax
0x1800ab851  js      loc_1800AC28F
0x1800ab857  lea     rdx, [rbx+28h]; struct _LUTF8_STRING *
0x1800ab85b  lea     r8, [rsp+170h+var_110]; wchar_t **
0x1800ab860  lea     rcx, [rbp+70h+var_58]; struct Windows::Rtl::IPoolAllocator *
0x1800ab864  call    ?DuplicateParserString@@YAJAEAVIPoolAllocator@Rtl@Windows@@AEBU_LUTF8_STRING@@PEAPEA_W@Z; DuplicateParserString(Windows::Rtl::IPoolAllocator &,_LUTF8_STRING const &,wchar_t * *)
0x1800ab869  mov     edi, eax
0x1800ab86b  test    eax, eax
0x1800ab86d  js      loc_1800AC288
0x1800ab873  mov     rsi, [rsp+170h+var_110]
0x1800ab878  mov     [rbp+70h+var_68], 1
0x1800ab87f  jmp     short loc_1800AB8A7
0x1800ab881  mov     rdx, [rbx+100h]
0x1800ab888  lea     r8, [rbp+70h+var_A8]; wchar_t **
0x1800ab88c  add     rdx, 38h ; '8'; struct _LUTF8_STRING *
0x1800ab890  mov     [rbp+70h+var_68], r12d
0x1800ab894  lea     rcx, [rbp+70h+var_58]; struct Windows::Rtl::IPoolAllocator *
0x1800ab898  call    ?DuplicateParserString@@YAJAEAVIPoolAllocator@Rtl@Windows@@AEBU_LUTF8_STRING@@PEAPEA_W@Z; DuplicateParserString(Windows::Rtl::IPoolAllocator &,_LUTF8_STRING const &,wchar_t * *)
0x1800ab89d  mov     edi, eax
0x1800ab89f  test    eax, eax
0x1800ab8a1  js      loc_1800AC984
0x1800ab8a7  mov     rcx, [r13-38h]; this
0x1800ab8ab  lea     r9, [rsp+170h+var_100]; wchar_t **
  ... truncated ...
```
