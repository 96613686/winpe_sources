# Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::HeadlessGraphUpdateMain(DiagHubCommon::AutoEvent const &)

- ea: `0x1800070d8`
- end: `0x180007c04`
- name: `?HeadlessGraphUpdateMain@CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEBVAutoEvent@DiagHubCommon@@@Z`
- size: `2860`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *__hidden this, const struct DiagHubCommon::AutoEvent *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180009270`

## callees

- `0x180002604`
- `0x180007050`
- `0x1800070d8`
- `0x180007f94`
- `0x18000856c`
- `0x1800086a4`
- `0x180008898`
- `0x18000b2fc`
- `0x1800257bc`
- `0x18002a794`
- `0x18003d864`
- `0x18004428c`
- `0x1800442d0`
- `0x180044310`
- `0x180044350`
- `0x180044454`
- `0x180044828`
- `0x18004489c`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memset` at `0x18000717b`
- `VCRUNTIME140!memset` at `0x18000717b`
- `KERNEL32!WaitForSingleObject` at `0x18000748d`
- `KERNEL32!WaitForSingleObject` at `0x18000748d`
- `KERNEL32!CreateFileW` at `0x180007150`
- `KERNEL32!CreateFileW` at `0x180007150`
- `KERNEL32!LeaveCriticalSection` at `0x180007609`
- `KERNEL32!LeaveCriticalSection` at `0x180007883`
- `KERNEL32!LeaveCriticalSection` at `0x180007b28`
- `KERNEL32!LeaveCriticalSection` at `0x180007b88`
- `KERNEL32!LeaveCriticalSection` at `0x180007609`
- `KERNEL32!LeaveCriticalSection` at `0x180007883`
- `KERNEL32!LeaveCriticalSection` at `0x180007b28`
- `KERNEL32!LeaveCriticalSection` at `0x180007b88`
- `KERNEL32!EnterCriticalSection` at `0x1800074c7`
- `KERNEL32!EnterCriticalSection` at `0x180007587`
- `KERNEL32!EnterCriticalSection` at `0x1800074c7`
- `KERNEL32!EnterCriticalSection` at `0x180007587`
- `KERNEL32!CloseHandle` at `0x180007b97`
- `KERNEL32!CloseHandle` at `0x180007b97`
- `KERNEL32!GetLastError` at `0x180007455`
- `KERNEL32!GetLastError` at `0x180007b34`
- `KERNEL32!GetLastError` at `0x180007455`
- `KERNEL32!GetLastError` at `0x180007b34`
- `KERNEL32!WriteFile` at `0x180007664`
- `KERNEL32!WriteFile` at `0x180007664`
- `ole32!CoTaskMemFree` at `0x180007847`
- `ole32!CoTaskMemFree` at `0x180007866`
- `ole32!CoTaskMemFree` at `0x180007847`
- `ole32!CoTaskMemFree` at `0x180007866`
- `OLEAUT32!__imp_SysAllocString` at `0x1800079ce`
- `OLEAUT32!__imp_SysAllocString` at `0x1800079ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800077fb`
- `OLEAUT32!__imp_SysFreeString` at `0x180007824`
- `OLEAUT32!__imp_SysFreeString` at `0x18000782f`
- `OLEAUT32!__imp_SysFreeString` at `0x180007a22`
- `OLEAUT32!__imp_SysFreeString` at `0x180007aa4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800077fb`
- `OLEAUT32!__imp_SysFreeString` at `0x180007824`
- `OLEAUT32!__imp_SysFreeString` at `0x18000782f`
- `OLEAUT32!__imp_SysFreeString` at `0x180007a22`
- `OLEAUT32!__imp_SysFreeString` at `0x180007aa4`
- `OLEAUT32!__imp_VariantInit` at `0x180007185`
- `OLEAUT32!__imp_VariantInit` at `0x180007185`
- `OLEAUT32!__imp_VariantClear` at `0x1800073ea`
- `OLEAUT32!__imp_VariantClear` at `0x180007443`
- `OLEAUT32!__imp_VariantClear` at `0x1800073ea`
- `OLEAUT32!__imp_VariantClear` at `0x180007443`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000754f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000754f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007438`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007521`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007a3e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007ac0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007bb3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007438`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007521`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007a3e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007ac0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007bb3`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180007200`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180007568`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180007200`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180007568`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180007249`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000742b`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000750d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180007a31`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180007ab3`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180007ba6`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180007249`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000742b`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000750d`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180007a31`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180007ab3`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180007ba6`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800071bf`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800071bf`

## string_xrefs

- `0x18000745e`: `Failed to create counters file for headless collection. Error code: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::HeadlessGraphUpdateMain(
        LPCWSTR *this,
        SAFEARRAY *a2)
{
  SAFEARRAY *v2; // r12
  Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *v3; // rsi
  SAFEARRAY *v4; // rbx
  HANDLE FileW; // rax
  void *v6; // r14
  void *v7; // r15
  int StartInfo; // r13d
  SAFEARRAY *parray; // rdi
  HRESULT Vartype; // eax
  VARTYPE v11; // cx
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // r12
  _QWORD *v14; // rdx
  _QWORD *v15; // rdx
  DiagHubCommon::LogStream *v16; // rdi
  DWORD LastError; // eax
  int v18; // edi
  struct _RTL_CRITICAL_SECTION *v19; // r12
  __int64 *v20; // r14
  __int64 v21; // rdi
  SAFEARRAY *v22; // rax
  struct _RTL_CRITICAL_SECTION *v23; // rsi
  __int64 *v24; // rdi
  __int64 **v25; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v28; // rax
  unsigned int v29; // ecx
  __int64 v30; // rsi
  LONGLONG llVal; // rdi
  unsigned int v32; // edi
  unsigned __int64 v33; // rcx
  __int64 v34; // rax
  _QWORD *v35; // rdx
  BSTR *pbstrVal; // r13
  __int64 v37; // rdi
  __int64 v38; // r12
  unsigned int v39; // r15d
  __int64 v40; // rsi
  BSTR v41; // rdi
  void *v42; // rcx
  __int64 v43; // rax
  BSTR v44; // rax
  OLECHAR *v45; // rdi
  SAFEARRAY *v46; // rbx
  _QWORD *v47; // rdx
  _QWORD *v48; // rdx
  signed int v49; // eax
  _QWORD *v50; // rdx
  char v52; // [rsp+40h] [rbp-79h]
  SAFEARRAY *v53; // [rsp+48h] [rbp-71h] BYREF
  unsigned __int64 ullVal; // [rsp+50h] [rbp-69h]
  SAFEARRAY *v55; // [rsp+58h] [rbp-61h] BYREF
  Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *v56; // [rsp+60h] [rbp-59h]
  HANDLE v57; // [rsp+68h] [rbp-51h]
  struct _RTL_CRITICAL_SECTION *v58; // [rsp+70h] [rbp-49h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-41h] BYREF
  VARTYPE pvt[4]; // [rsp+90h] [rbp-29h] BYREF
  SAFEARRAY *psa; // [rsp+98h] [rbp-21h] BYREF
  __int128 v62; // [rsp+A0h] [rbp-19h] BYREF
  void *v63; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v64; // [rsp+B8h] [rbp-1h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+C8h] [rbp+Fh] BYREF

  v2 = a2;
  v55 = a2;
  v3 = (Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *)this;
  v56 = (Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *)this;
  v4 = 0;
  v53 = 0;
  LODWORD(v63) = *((_DWORD *)this[31] + 240);
  v52 = 0;
  FileW = CreateFileW(this[49], 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v6 = FileW;
  v7 = 0;
  v57 = 0;
  if ( FileW != (HANDLE)-1LL )
  {
    v7 = FileW;
    v57 = FileW;
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    StartInfo = Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::GetStartInfo(
                  *((Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController **)v3 + 31),
                  &pvarg);
    if ( StartInfo >= 0 )
    {
      psa = 0;
      parray = pvarg.parray;
      if ( !pvarg.llVal )
        goto LABEL_139;
      Vartype = SafeArrayGetVartype(pvarg.parray, pvt);
      if ( Vartype < 0 )
      {
        _mm_lfence();
        ATL::AtlThrowImpl(Vartype);
      }
      v11 = pvt[0];
      if ( pvt[0] == 13 && (parray->fFeatures & 0x440) == 0x440 )
      {
        v11 = 9;
        pvt[0] = 9;
      }
      if ( v11 != 21 )
LABEL_139:
        ATL::AtlThrowImpl(-2147024809);
      psa = parray;
      StartInfo = SafeArrayLock(parray);
      if ( StartInfo >= 0 )
      {
        v12 = *(_QWORD *)ATL::CComSafeArray<unsigned __int64,21>::operator[](&psa, 0);
        v13 = *(_QWORD *)ATL::CComSafeArray<unsigned __int64,21>::operator[](&psa, 1);
        ullVal = *(_QWORD *)ATL::CComSafeArray<unsigned __int64,21>::operator[](&psa, 2);
        SafeArrayUnlock(psa);
        parray = 0;
        psa = 0;
        v62 = 0;
        Microsoft::Json::StringBuilder::StringBuilder((Microsoft::Json::StringBuilder *)&v62);
        StartInfo = Microsoft::Json::StringBuilder::StartObject((Microsoft::Json::StringBuilder *)&v62);
        if ( StartInfo >= 0 )
        {
          StartInfo = Microsoft::Json::StringBuilder::AddPropertyName(
                        (Microsoft::Json::StringBuilder *)&v62,
                        L"beginTime");
          if ( StartInfo >= 0 )
          {
            StartInfo = Microsoft::Json::Services::SerializeTimestamp(
                          v12,
                          (struct Microsoft::Json::StringBuilder *)&v62);
            if ( StartInfo >= 0 )
            {
              StartInfo = Microsoft::Json::StringBuilder::AddPropertyName(
                            (Microsoft::Json::StringBuilder *)&v62,
                            L"beginTimeQpc");
              if ( StartInfo >= 0 )
              {
                StartInfo = Microsoft::Json::Services::SerializeTimestamp(
                              v13,
                              (struct Microsoft::Json::StringBuilder *)&v62);
                if ( StartInfo >= 0 )
                {
                  StartInfo = Microsoft::Json::StringBuilder::AddPropertyName(
                                (Microsoft::Json::StringBuilder *)&v62,
                                L"qpcFrequency");
                  if ( StartInfo >= 0 )
                  {
                    StartInfo = Microsoft::Json::Services::SerializeTimestamp(
                                  ullVal,
                                  (struct Microsoft::Json::StringBuilder *)&v62);
                    if ( StartInfo >= 0 )
                    {
                      StartInfo = Microsoft::Json::StringBuilder::AddPropertyName(
                                    (Microsoft::Json::StringBuilder *)&v62,
                                    L"duration");
                      if ( StartInfo >= 0 )
                      {
                        StartInfo = Microsoft::Json::Services::SerializeTimestamp(
                                      0,
                                      (struct Microsoft::Json::StringBuilder *)&v62);
                        if ( StartInfo >= 0 )
                        {
                          StartInfo = Microsoft::Json::StringBuilder::AddPropertyName(
                                        (Microsoft::Json::StringBuilder *)&v62,
                                        L"isProcessed");
                          if ( StartInfo >= 0 )
                          {
                            if ( (_BYTE)v62 )
                              ATL::CSimpleStringT<unsigned short,0>::AppendChar((char *)&v62 + 8, 44);
                            ATL::CSimpleStringT<unsigned short,0>::Append((char *)&v62 + 8, L"false");
                            LOBYTE(v62) = 1;
                            StartInfo = Microsoft::Json::StringBuilder::AddPropertyName(
                                          (Microsoft::Json::StringBuilder *)&v62,
                                          L"counters");
                            if ( StartInfo >= 0 )
                            {
                              StartInfo = Microsoft::Json::StringBuilder::StartArray((Microsoft::Json::StringBuilder *)&v62);
                              if ( StartInfo >= 0 )
                              {
                                StartInfo = anonymous_namespace_::WriteJsonToFile(v6);
                                if ( StartInfo >= 0 )
                                {
                                  v14 = (_QWORD *)(*((_QWORD *)&v62 + 1) - 24LL);
                                  if ( _InterlockedExchangeAdd(
                                         (volatile signed __int32 *)(*((_QWORD *)&v62 + 1) - 24LL + 16),
                                         0xFFFFFFFF) <= 1 )
                                  {
                                    _mm_lfence();
                                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
                                  }
                                  VariantClear(&pvarg);
                                  v3 = v56;
                                  v2 = v55;
                                  goto LABEL_35;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        v15 = (_QWORD *)(*((_QWORD *)&v62 + 1) - 24LL);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v62 + 1) - 24LL + 16), 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
        }
      }
      if ( parray && SafeArrayUnlock(parray) >= 0 )
        SafeArrayDestroy(parray);
    }
    VariantClear(&pvarg);
    goto LABEL_131;
  }
  v16 = _logger;
  LastError = GetLastError();
  DiagHubCommon::LogStream::Write(
    (DiagHubCommon::LogStream *)((char *)v16 + 112),
    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
    L"Failed to create counters file for headless collection. Error code: %d",
    LastError);
LABEL_35:
  v18 = (int)v63;
  while ( 1 )
  {
    while ( 1 )
    {
      do
      {
        if ( (v2->cLocks & 0x80000000) == 0 && !WaitForSingleObject(*(HANDLE *)&v2->cDims, 0x64u) )
        {
          if ( (unsigned int)ATL::CComSafeArray<unsigned short *,8>::GetCount(&v53) )
          {
            if ( v7 )
            {
              *(_OWORD *)&pvarg.vt = 0;
              Microsoft::Json::StringBuilder::StringBuilder((Microsoft::Json::StringBuilder *)&pvarg);
              ATL::CSimpleStringT<unsigned short,0>::AppendChar(&pvarg.decVal.Lo32, 93);
              LOBYTE(pvarg.vt) = 1;
              ATL::CSimpleStringT<unsigned short,0>::AppendChar(&pvarg.decVal.Lo32, 125);
              LOBYTE(pvarg.vt) = 1;
              StartInfo = anonymous_namespace_::WriteJsonToFile(v7);
              if ( StartInfo >= 0 )
              {
                v42 = 0;
                v63 = 0;
                v43 = *((_QWORD *)v3 + 31);
                if ( (*(_BYTE *)(v43 + 856) & 4) != 0 )
                {
                  StartInfo = -2147019873;
                }
                else
                {
                  StartInfo = Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager::GetPackageResult(
                                (Microsoft::DiagnosticsHub::StandardCollector::PackagingResultManager *)(v43 + 880),
                                &GUID_00000000_0000_0000_c000_000000000046,
                                &v63);
                  if ( StartInfo >= 0 )
                  {
                    psa = 0;
                    StartInfo = (**(__int64 (__fastcall ***)(void *, GUID *, SAFEARRAY **))v63)(
                                  v63,
                                  &GUID_03779dc9_70da_4063_808f_43ee228b18c4,
                                  &psa);
                    if ( StartInfo >= 0 )
                    {
                      StartInfo = (*(__int64 (__fastcall **)(SAFEARRAY *, const wchar_t *, _QWORD, _QWORD, int, __int128 *))(*(_QWORD *)&psa->cDims + 64LL))(
                                    psa,
                                    L"DiagnosticsHub.Resource.CountersFile",
                                    *((_QWORD *)v3 + 49),
                                    0,
                                    1,
                                    &v64);
                      if ( StartInfo >= 0 )
                      {
                        v55 = 0;
                        v44 = SysAllocString(L"DiagnosticsHub.Tag.Internal.FirstDataSourceToImport");
                        v45 = v44;
                        v58 = (struct _RTL_CRITICAL_SECTION *)v44;
                        if ( !v44 )
                          ATL::AtlThrowImpl(-2147024882);
                        *(_QWORD *)&v62 = v44;
                        ATL::CComSafeArray<unsigned short *,8>::Add(&v55, &v62, 1);
                        v46 = v55;
                        StartInfo = (*(__int64 (__fastcall **)(SAFEARRAY *, __int128 *, SAFEARRAY *))(*(_QWORD *)&psa->cDims + 56LL))(
                                      psa,
                                      &v64,
                                      v55);
                        if ( StartInfo >= 0 )
                        {
                          SysFreeString(v45);
                          if ( v46 && SafeArrayUnlock(v46) >= 0 )
                            SafeArrayDestroy(v46);
                          if ( psa )
                            (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&psa->cDims + 16LL))(psa);
                          if ( v63 )
                            (*(void (__fastcall **)(void *))(*(_QWORD *)v63 + 16LL))(v63);
                          v48 = (_QWORD *)(pvarg.llVal - 24);
                          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(pvarg.llVal - 24 + 16), 0xFFFFFFFF) <= 1 )
                          {
                            _mm_lfence();
                            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v48 + 8LL))(*v48);
                          }
                          goto LABEL_122;
                        }
                        SysFreeString(v45);
                        if ( v46 && SafeArrayUnlock(v46) >= 0 )
                          SafeArrayDestroy(v46);
                      }
                    }
                    if ( psa )
                      (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&psa->cDims + 16LL))(psa);
                  }
                  v42 = v63;
                }
                if ( v42 )
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v42 + 16LL))(v42);
              }
              v47 = (_QWORD *)(pvarg.llVal - 24);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(pvarg.llVal - 24 + 16), 0xFFFFFFFF) <= 1 )
              {
                _mm_lfence();
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v47 + 8LL))(*v47);
              }
              goto LABEL_112;
            }
          }
          else
          {
            DiagHubCommon::LogStream::Write(
              _logger,
              L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
              L"No counters requested for headless collection");
          }
LABEL_122:
          StartInfo = 0;
LABEL_112:
          v4 = v53;
          goto LABEL_131;
        }
        v18 -= 100;
      }
      while ( v18 > 0 );
      if ( *((_DWORD *)v3 + 101) == 2 )
        break;
      v18 = 100;
    }
    v19 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)v3 + 31) + 200LL);
    v58 = v19;
    EnterCriticalSection(v19);
    *(_QWORD *)&v62 = *(_QWORD *)(*((_QWORD *)v3 + 31) + 248LL);
    v20 = *(__int64 **)v62;
    if ( *(_QWORD *)v62 != (_QWORD)v62 )
      break;
LABEL_90:
    v18 = (int)v63;
    LeaveCriticalSection(v19);
    v2 = v55;
  }
  while ( *((_BYTE *)v20 + 40) )
  {
LABEL_89:
    v20 = (__int64 *)*v20;
    if ( v20 == (__int64 *)v62 )
      goto LABEL_90;
  }
  *(_OWORD *)&pvarg.vt = 0;
  v21 = *((_QWORD *)v3 + 31);
  if ( v4 )
  {
    StartInfo = SafeArrayUnlock(v4);
    if ( StartInfo < 0 )
      goto LABEL_130;
    StartInfo = SafeArrayDestroy(v4);
    if ( StartInfo < 0 )
      goto LABEL_130;
  }
  rgsabound = 0;
  v22 = SafeArrayCreate(8u, 1u, &rgsabound);
  v4 = v22;
  v53 = v22;
  if ( !v22 )
  {
    StartInfo = -2147024882;
    goto LABEL_130;
  }
  StartInfo = SafeArrayLock(v22);
  if ( StartInfo < 0 )
    goto LABEL_130;
  v23 = (struct _RTL_CRITICAL_SECTION *)(v21 + 984);
  ullVal = v21 + 984;
  EnterCriticalSection((LPCRITICAL_SECTION)(v21 + 984));
  v24 = **(__int64 ***)(v21 + 968);
  if ( !*((_BYTE *)v24 + 25) )
  {
    do
    {
      StartInfo = ATL::CComSafeArray<unsigned short *,8>::Add(&v53, v24 + 4, 1);
      if ( StartInfo < 0 )
      {
        LeaveCriticalSection(v23);
        v4 = v53;
        goto LABEL_130;
      }
      v25 = (__int64 **)v24[2];
      if ( *((_BYTE *)v25 + 25) )
      {
        for ( i = (__int64 *)v24[1]; !*((_BYTE *)i + 25) && v24 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v24 = i;
        v24 = i;
      }
      else
      {
        v24 = (__int64 *)v24[2];
        for ( j = *v25; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v24 = j;
      }
    }
    while ( !*((_BYTE *)v24 + 25) );
    v4 = v53;
  }
  LeaveCriticalSection(v23);
  v3 = v56;
  (*(void (__fastcall **)(Microsoft::DiagnosticsHub::StandardCollector::CollectionSession *, __int64 *, SAFEARRAY *, VARIANTARG *))(*(_QWORD *)v56 + 96LL))(
    v56,
    v20 + 2,
    v4,
    &pvarg);
  if ( !v7 || !*(_DWORD *)&pvarg.vt )
  {
LABEL_79:
    pbstrVal = pvarg.pbstrVal;
    if ( pvarg.llVal )
    {
      v37 = 0;
      *(_DWORD *)pvt = 0;
      if ( *(_DWORD *)&pvarg.vt )
      {
        do
        {
          v38 = 5 * v37;
          SysFreeString(pbstrVal[5 * v37 + 2]);
          if ( pbstrVal[5 * v37 + 4] )
          {
            v39 = 0;
            if ( LODWORD(pbstrVal[5 * v37 + 3]) )
            {
              do
              {
                v40 = 16LL * v39;
                v41 = pbstrVal[v38 + 4];
                SysFreeString(*(BSTR *)&v41[v40 + 8]);
                SysFreeString(*(BSTR *)&v41[v40 + 12]);
                ++v39;
              }
              while ( v39 < LODWORD(pbstrVal[v38 + 3]) );
              LODWORD(v37) = *(_DWORD *)pvt;
            }
            CoTaskMemFree(pbstrVal[v38 + 4]);
          }
          v37 = (unsigned int)(v37 + 1);
          *(_DWORD *)pvt = v37;
          pbstrVal = pvarg.pbstrVal;
        }
        while ( (unsigned int)v37 < *(_DWORD *)&pvarg.vt );
        v7 = v57;
        v19 = v58;
      }
      CoTaskMemFree(pbstrVal);
      v3 = v56;
    }
    goto LABEL_89;
  }
  if ( v52 && !WriteFile(v7, L",", 2u, (LPDWORD)&psa, 0) )
  {
    v49 = GetLastError();
    StartInfo = (unsigned __int16)v49 | 0x80070000;
    if ( v49 <= 0 )
      StartInfo = v49;
    goto LABEL_130;
  }
  v64 = 0;
  Microsoft::Json::StringBuilder::StringBuilder((Microsoft::Json::StringBuilder *)&v64);
  v28 = 0;
  *(_DWORD *)pvt = 0;
  v29 = *(_DWORD *)&pvarg.vt;
  if ( !*(_DWORD *)&pvarg.vt )
  {
LABEL_76:
    StartInfo = anonymous_namespace_::WriteJsonToFile(v7);
    if ( StartInfo < 0 )
      goto LABEL_127;
    v52 = 1;
    v35 = (_QWORD *)(*((_QWORD *)&v64 + 1) - 24LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v64 + 1) - 24LL + 16), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v35 + 8LL))(*v35);
    }
    goto LABEL_79;
  }
  while ( 1 )
  {
    v30 = 5 * v28;
    llVal = pvarg.llVal;
    ullVal = pvarg.ullVal;
    if ( !*(_DWORD *)(pvarg.llVal + 40 * v28 + 24) )
      goto LABEL_74;
    StartInfo = Microsoft::Json::StringBuilder::StartObject((Microsoft::Json::StringBuilder *)&v64);
    if ( StartInfo < 0 )
      goto LABEL_127;
    StartInfo = Microsoft::Json::StringBuilder::AddStringProperty(
                  (Microsoft::Json::StringBuilder *)&v64,
                  L"id",
                  *(const unsigned __int16 **)(llVal + 8 * v30 + 16));
    if ( StartInfo < 0 )
      goto LABEL_127;
    StartInfo = Microsoft::Json::StringBuilder::AddPropertyName((Microsoft::Json::StringBuilder *)&v64, L"p");
    if ( StartInfo < 0 )
      goto LABEL_127;
    StartInfo = Microsoft::Json::StringBuilder::StartArray((Microsoft::Json::StringBuilder *)&v64);
    if ( StartInfo < 0 )
      goto LABEL_127;
    v32 = 0;
    v33 = ullVal;
    if ( *(_DWORD *)(ullVal + 8 * v30 + 24) )
      break;
LABEL_73:
    ATL::CSimpleStringT<unsigned short,0>::AppendChar((char *)&v64 + 8, 93);
    LOBYTE(v64) = 1;
    ATL::CSimpleStringT<unsigned short,0>::AppendChar((char *)&v64 + 8, 125);
    LOBYTE(v64) = 1;
    v29 = *(_DWORD *)&pvarg.vt;
LABEL_74:
    v28 = (unsigned int)(*(_DWORD *)pvt + 1);
    *(_DWORD *)pvt = v28;
    if ( (unsigned int)v28 >= v29 )
    {
      v3 = v56;
      goto LABEL_76;
    }
  }
  while ( 1 )
  {
    v34 = 32LL * v32;
    StartInfo = Microsoft::Json::Services::SerializeDataPoint(
                  *(_QWORD *)(v34 + *(_QWORD *)(v33 + 8 * v30 + 32)),
                  *(double *)(v34 + *(_QWORD *)(v33 + 8 * v30 + 32) + 8),
                  *(const unsigned __int16 **)(v34 + *(_QWORD *)(v33 + 8 * v30 + 32) + 16),
                  *(const unsigned __int16 **)(v34 + *(_QWORD *)(v33 + 8 * v30 + 32) + 24),
                  (struct Microsoft::Json::StringBuilder *)&v64);
    if ( StartInfo < 0 )
      break;
    ++v32;
    v33 = ullVal;
    if ( v32 >= *(_DWORD *)(ullVal + 8 * v30 + 24) )
      goto LABEL_73;
  }
LABEL_127:
  v50 = (_QWORD *)(*((_QWORD *)&v64 + 1) - 24LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v64 + 1) - 24LL + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v50 + 8LL))(*v50);
  }
LABEL_130:
  LeaveCriticalSection(v19);
LABEL_131:
  if ( v7 )
    CloseHandle(v7);
  if ( v4 && SafeArrayUnlock(v4) >= 0 )
    SafeArrayDestroy(v4);
  return (unsigned int)StartInfo;
}

```

## disassembly

```asm
0x1800070d8  mov     [rsp-8+arg_10], rbx
0x1800070dd  push    rbp
0x1800070de  push    rsi
0x1800070df  push    rdi
0x1800070e0  push    r12
0x1800070e2  push    r13
0x1800070e4  push    r14
0x1800070e6  push    r15
0x1800070e8  lea     rbp, [rsp-27h]
0x1800070ed  sub     rsp, 0E0h
0x1800070f4  mov     rax, cs:__security_cookie
0x1800070fb  xor     rax, rsp
0x1800070fe  mov     [rbp+57h+var_40], rax
0x180007102  mov     r12, rdx
0x180007105  mov     [rbp+57h+var_B8], rdx
0x180007109  mov     rsi, rcx
0x18000710c  mov     [rbp+57h+var_B0], rcx
0x180007110  xor     ebx, ebx
0x180007112  mov     [rbp+57h+var_C8], rbx
0x180007116  mov     rax, [rcx+0F8h]
0x18000711d  mov     eax, [rax+3C0h]
0x180007123  mov     dword ptr [rbp+57h+var_60], eax
0x180007126  mov     [rbp+57h+var_D0], bl
0x180007129  mov     [rsp+110h+hTemplateFile], rbx; hTemplateFile
0x18000712e  mov     [rsp+110h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180007136  mov     [rsp+110h+dwCreationDisposition], 2; dwCreationDisposition
0x18000713e  xor     r9d, r9d; lpSecurityAttributes
0x180007141  xor     r8d, r8d; dwShareMode
0x180007144  mov     edx, 40000000h; dwDesiredAccess
0x180007149  mov     rcx, [rcx+188h]; lpFileName
0x180007150  call    cs:__imp_CreateFileW
0x180007156  mov     r14, rax
0x180007159  xor     r15d, r15d
0x18000715c  mov     [rbp+57h+var_A8], r15
0x180007160  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007164  jz      loc_18000744E
0x18000716a  mov     r15, rax
0x18000716d  mov     [rbp+57h+var_A8], rax
0x180007171  xor     edx, edx; Val
0x180007173  lea     r8d, [rbx+18h]; Size
0x180007177  lea     rcx, [rbp+57h+pvarg]; void *
0x18000717b  call    cs:__imp_memset
0x180007181  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180007185  call    cs:__imp_VariantInit
0x18000718b  nop
0x18000718c  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x180007190  mov     rcx, [rsi+0F8h]; this
0x180007197  call    ?GetStartInfo@CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJPEAUtagVARIANT@@@Z; Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::GetStartInfo(tagVARIANT *)
0x18000719c  mov     r13d, eax
0x18000719f  test    eax, eax
0x1800071a1  js      loc_18000743F
0x1800071a7  mov     [rbp+57h+psa], rbx
0x1800071ab  mov     rdi, qword ptr [rbp+57h+pvarg+8]
0x1800071af  test    rdi, rdi
0x1800071b2  jz      loc_180007BF9
0x1800071b8  lea     rdx, [rbp+57h+pvt]; pvt
0x1800071bc  mov     rcx, rdi; psa
0x1800071bf  call    cs:__imp_SafeArrayGetVartype
0x1800071c5  test    eax, eax
0x1800071c7  js      loc_180007BEE
0x1800071cd  movzx   ecx, [rbp+57h+pvt]
0x1800071d1  cmp     cx, 0Dh
0x1800071d5  jnz     short loc_1800071EF
0x1800071d7  movzx   eax, word ptr [rdi+2]
0x1800071db  mov     edx, 440h
0x1800071e0  and     ax, dx
0x1800071e3  cmp     ax, dx
0x1800071e6  jnz     short loc_1800071EF
0x1800071e8  lea     ecx, [rbx+9]
0x1800071eb  mov     [rbp+57h+pvt], cx
0x1800071ef  cmp     cx, 15h
0x1800071f3  jnz     loc_180007BF9
0x1800071f9  mov     [rbp+57h+psa], rdi
0x1800071fd  mov     rcx, rdi; psa
0x180007200  call    cs:__imp_SafeArrayLock
0x180007206  mov     r13d, eax
0x180007209  test    eax, eax
0x18000720b  js      loc_180007423
0x180007211  xor     edx, edx
0x180007213  lea     rcx, [rbp+57h+psa]
0x180007217  call    ??A?$CComSafeArray@_K$0BF@@ATL@@QEAAAEA_KH@Z; ATL::CComSafeArray<unsigned __int64,21>::operator[](int)
0x18000721c  mov     rsi, [rax]
0x18000721f  mov     edx, 1
0x180007224  lea     rcx, [rbp+57h+psa]
0x180007228  call    ??A?$CComSafeArray@_K$0BF@@ATL@@QEAAAEA_KH@Z; ATL::CComSafeArray<unsigned __int64,21>::operator[](int)
0x18000722d  mov     r12, [rax]
0x180007230  mov     edx, 2
0x180007235  lea     rcx, [rbp+57h+psa]
0x180007239  call    ??A?$CComSafeArray@_K$0BF@@ATL@@QEAAAEA_KH@Z; ATL::CComSafeArray<unsigned __int64,21>::operator[](int)
0x18000723e  mov     rax, [rax]
0x180007241  mov     [rbp+57h+var_C0], rax
0x180007245  mov     rcx, [rbp+57h+psa]; psa
0x180007249  call    cs:__imp_SafeArrayUnlock
0x18000724f  xor     edi, edi
0x180007251  mov     [rbp+57h+psa], rdi
0x180007255  xorps   xmm0, xmm0
0x180007258  movups  [rbp+57h+var_70], xmm0
0x18000725c  lea     rcx, [rbp+57h+var_70]; this
0x180007260  call    ??0StringBuilder@Json@Microsoft@@QEAA@XZ; Microsoft::Json::StringBuilder::StringBuilder(void)
0x180007265  nop
0x180007266  lea     rcx, [rbp+57h+var_70]; this
0x18000726a  call    ?StartObject@StringBuilder@Json@Microsoft@@QEAAJXZ; Microsoft::Json::StringBuilder::StartObject(void)
0x18000726f  mov     r13d, eax
0x180007272  test    eax, eax
0x180007274  js      loc_1800073FA
0x18000727a  lea     rdx, aBegintime; "beginTime"
0x180007281  lea     rcx, [rbp+57h+var_70]; this
0x180007285  call    ?AddPropertyName@StringBuilder@Json@Microsoft@@QEAAJPEBG@Z; Microsoft::Json::StringBuilder::AddPropertyName(ushort const *)
0x18000728a  mov     r13d, eax
0x18000728d  test    eax, eax
0x18000728f  js      loc_1800073FA
0x180007295  lea     rdx, [rbp+57h+var_70]; this
0x180007299  mov     rcx, rsi; unsigned __int64
0x18000729c  call    ?SerializeTimestamp@Services@Json@Microsoft@@SAJ_KAEAVStringBuilder@23@@Z; Microsoft::Json::Services::SerializeTimestamp(unsigned __int64,Microsoft::Json::StringBuilder &)
0x1800072a1  mov     r13d, eax
0x1800072a4  test    eax, eax
0x1800072a6  js      loc_1800073FA
0x1800072ac  lea     rdx, aBegintimeqpc; "beginTimeQpc"
0x1800072b3  lea     rcx, [rbp+57h+var_70]; this
0x1800072b7  call    ?AddPropertyName@StringBuilder@Json@Microsoft@@QEAAJPEBG@Z; Microsoft::Json::StringBuilder::AddPropertyName(ushort const *)
0x1800072bc  mov     r13d, eax
0x1800072bf  test    eax, eax
0x1800072c1  js      loc_1800073FA
0x1800072c7  lea     rdx, [rbp+57h+var_70]; this
0x1800072cb  mov     rcx, r12; unsigned __int64
0x1800072ce  call    ?SerializeTimestamp@Services@Json@Microsoft@@SAJ_KAEAVStringBuilder@23@@Z; Microsoft::Json::Services::SerializeTimestamp(unsigned __int64,Microsoft::Json::StringBuilder &)
0x1800072d3  mov     r13d, eax
0x1800072d6  test    eax, eax
0x1800072d8  js      loc_1800073FA
0x1800072de  lea     rdx, aQpcfrequency; "qpcFrequency"
0x1800072e5  lea     rcx, [rbp+57h+var_70]; this
0x1800072e9  call    ?AddPropertyName@StringBuilder@Json@Microsoft@@QEAAJPEBG@Z; Microsoft::Json::StringBuilder::AddPropertyName(ushort const *)
0x1800072ee  mov     r13d, eax
0x1800072f1  test    eax, eax
0x1800072f3  js      loc_1800073FA
0x1800072f9  lea     rdx, [rbp+57h+var_70]; this
0x1800072fd  mov     rcx, [rbp+57h+var_C0]; unsigned __int64
0x180007301  call    ?SerializeTimestamp@Services@Json@Microsoft@@SAJ_KAEAVStringBuilder@23@@Z; Microsoft::Json::Services::SerializeTimestamp(unsigned __int64,Microsoft::Json::StringBuilder &)
0x180007306  mov     r13d, eax
0x180007309  test    eax, eax
0x18000730b  js      loc_1800073FA
0x180007311  lea     rdx, aDuration; "duration"
0x180007318  lea     rcx, [rbp+57h+var_70]; this
0x18000731c  call    ?AddPropertyName@StringBuilder@Json@Microsoft@@QEAAJPEBG@Z; Microsoft::Json::StringBuilder::AddPropertyName(ushort const *)
0x180007321  mov     r13d, eax
0x180007324  test    eax, eax
0x180007326  js      loc_1800073FA
0x18000732c  lea     rdx, [rbp+57h+var_70]; this
0x180007330  xor     ecx, ecx; unsigned __int64
0x180007332  call    ?SerializeTimestamp@Services@Json@Microsoft@@SAJ_KAEAVStringBuilder@23@@Z; Microsoft::Json::Services::SerializeTimestamp(unsigned __int64,Microsoft::Json::StringBuilder &)
0x180007337  mov     r13d, eax
0x18000733a  test    eax, eax
0x18000733c  js      loc_1800073FA
0x180007342  lea     rdx, aIsprocessed; "isProcessed"
0x180007349  lea     rcx, [rbp+57h+var_70]; this
0x18000734d  call    ?AddPropertyName@StringBuilder@Json@Microsoft@@QEAAJPEBG@Z; Microsoft::Json::StringBuilder::AddPropertyName(ushort const *)
0x180007352  mov     r13d, eax
0x180007355  test    eax, eax
0x180007357  js      loc_1800073FA
0x18000735d  cmp     byte ptr [rbp+57h+var_70], dil
0x180007361  jz      short loc_18000736F
0x180007363  lea     edx, [rdi+2Ch]
0x180007366  lea     rcx, [rbp+57h+var_70+8]
0x18000736a  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18000736f  lea     rdx, aFalse; "false"
0x180007376  lea     rcx, [rbp+57h+var_70+8]
0x18000737a  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18000737f  mov     byte ptr [rbp+57h+var_70], 1
0x180007383  lea     rdx, aCounters; "counters"
0x18000738a  lea     rcx, [rbp+57h+var_70]; this
0x18000738e  call    ?AddPropertyName@StringBuilder@Json@Microsoft@@QEAAJPEBG@Z; Microsoft::Json::StringBuilder::AddPropertyName(ushort const *)
0x180007393  mov     r13d, eax
0x180007396  test    eax, eax
0x180007398  js      short loc_1800073FA
0x18000739a  lea     rcx, [rbp+57h+var_70]; this
0x18000739e  call    ?StartArray@StringBuilder@Json@Microsoft@@QEAAJXZ; Microsoft::Json::StringBuilder::StartArray(void)
0x1800073a3  mov     r13d, eax
0x1800073a6  test    eax, eax
0x1800073a8  js      short loc_1800073FA
0x1800073aa  lea     rdx, [rbp+57h+var_70]
0x1800073ae  mov     rcx, r14; hFile
0x1800073b1  call    _anonymous_namespace___WriteJsonToFile
0x1800073b6  mov     r13d, eax
0x1800073b9  test    eax, eax
0x1800073bb  js      short loc_1800073FA
0x1800073bd  mov     rdx, qword ptr [rbp+57h+var_70+8]
0x1800073c1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800073c5  or      eax, 0FFFFFFFFh
0x1800073c8  lock xadd [rdx+10h], eax
0x1800073cd  sub     eax, 1
0x1800073d0  jg      short loc_1800073E6
0x1800073d2  lfence
0x1800073d5  mov     rcx, [rdx]
0x1800073d8  mov     rax, [rcx]
0x1800073db  mov     rax, [rax+8]
0x1800073df  call    cs:__guard_dispatch_icall_fptr
0x1800073e5  nop
0x1800073e6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800073ea  call    cs:__imp_VariantClear
0x1800073f0  mov     rsi, [rbp+57h+var_B0]
0x1800073f4  mov     r12, [rbp+57h+var_B8]
0x1800073f8  jmp     short loc_180007475
0x1800073fa  mov     rdx, qword ptr [rbp+57h+var_70+8]
0x1800073fe  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180007402  or      eax, 0FFFFFFFFh
0x180007405  lock xadd [rdx+10h], eax
0x18000740a  sub     eax, 1
0x18000740d  jg      short loc_180007423
0x18000740f  lfence
0x180007412  mov     rcx, [rdx]
0x180007415  mov     rax, [rcx]
0x180007418  mov     rax, [rax+8]
0x18000741c  call    cs:__guard_dispatch_icall_fptr
0x180007422  nop
0x180007423  test    rdi, rdi
0x180007426  jz      short loc_18000743F
0x180007428  mov     rcx, rdi; psa
0x18000742b  call    cs:__imp_SafeArrayUnlock
0x180007431  test    eax, eax
0x180007433  js      short loc_18000743F
0x180007435  mov     rcx, rdi; psa
0x180007438  call    cs:__imp_SafeArrayDestroy
0x18000743e  nop
0x18000743f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180007443  call    cs:__imp_VariantClear
0x180007449  jmp     loc_180007B8F
0x18000744e  mov     rdi, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180007455  call    cs:__imp_GetLastError
0x18000745b  mov     r9d, eax
0x18000745e  lea     r8, aFailedToCreate_1; "Failed to create counters file for head"...
0x180007465  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000746c  lea     rcx, [rdi+70h]; this
0x180007470  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180007475  mov     edi, dword ptr [rbp+57h+var_60]
0x180007478  mov     eax, [r12+8]
0x18000747d  shr     eax, 1Fh
0x180007480  test    al, al
0x180007482  jnz     short loc_18000749B
0x180007484  mov     edx, 64h ; 'd'; dwMilliseconds
0x180007489  mov     rcx, [r12]; hHandle
0x18000748d  call    cs:__imp_WaitForSingleObject
0x180007493  test    eax, eax
0x180007495  jz      loc_180007892
0x18000749b  sub     edi, 64h ; 'd'
0x18000749e  test    edi, edi
0x1800074a0  jg      short loc_180007478
0x1800074a2  cmp     dword ptr [rsi+194h], 2
0x1800074a9  jz      short loc_1800074B2
0x1800074ab  mov     edi, 64h ; 'd'
0x1800074b0  jmp     short loc_180007478
0x1800074b2  mov     r12, [rsi+0F8h]
0x1800074b9  add     r12, 0C8h
0x1800074c0  mov     [rbp+57h+var_A0], r12
0x1800074c4  mov     rcx, r12; lpCriticalSection
0x1800074c7  call    cs:__imp_EnterCriticalSection
0x1800074cd  nop
0x1800074ce  mov     rax, [rsi+0F8h]
0x1800074d5  mov     rax, [rax+0F8h]
0x1800074dc  mov     qword ptr [rbp+57h+var_70], rax
0x1800074e0  mov     r14, [rax]
0x1800074e3  cmp     r14, rax
0x1800074e6  jz      loc_18000787D
0x1800074ec  cmp     byte ptr [r14+28h], 0
0x1800074f1  jnz     loc_180007870
0x1800074f7  xorps   xmm0, xmm0
0x1800074fa  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800074fe  mov     rdi, [rsi+0F8h]
0x180007505  test    rbx, rbx
0x180007508  jz      short loc_180007534
0x18000750a  mov     rcx, rbx; psa
0x18000750d  call    cs:__imp_SafeArrayUnlock
0x180007513  mov     r13d, eax
0x180007516  test    eax, eax
0x180007518  js      loc_180007B85
0x18000751e  mov     rcx, rbx; psa
0x180007521  call    cs:__imp_SafeArrayDestroy
0x180007527  mov     r13d, eax
0x18000752a  test    eax, eax
0x18000752c  js      loc_180007B85
0x180007532  xor     ebx, ebx
0x180007534  mov     qword ptr [rbp+57h+rgsabound.cElements], 0
0x18000753c  test    rbx, rbx
0x18000753f  jnz     loc_180007B7F
0x180007545  lea     ecx, [rbx+8]; vt
0x180007548  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x18000754c  lea     edx, [rbx+1]; cDims
0x18000754f  call    cs:__imp_SafeArrayCreate
0x180007555  mov     rbx, rax
0x180007558  mov     [rbp+57h+var_C8], rax
0x18000755c  test    rax, rax
0x18000755f  jz      loc_180007B77
0x180007565  mov     rcx, rax; psa
0x180007568  call    cs:__imp_SafeArrayLock
0x18000756e  mov     r13d, eax
0x180007571  test    eax, eax
0x180007573  js      loc_180007B85
0x180007579  lea     rsi, [rdi+3D8h]
0x180007580  mov     [rbp+57h+var_C0], rsi
0x180007584  mov     rcx, rsi; lpCriticalSection
0x180007587  call    cs:__imp_EnterCriticalSection
  ... truncated ...
```
