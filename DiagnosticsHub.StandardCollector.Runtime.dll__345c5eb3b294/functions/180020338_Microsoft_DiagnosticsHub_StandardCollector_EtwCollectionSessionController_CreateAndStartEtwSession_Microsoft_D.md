# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::CreateAndStartEtwSession(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionType,Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation &)

- ea: `0x180020338`
- end: `0x180020c71`
- name: `?CreateAndStartEtwSession@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJW4EtwSessionType@1234@AEAUEtwSessionInformation@1234@@Z`
- size: `2361`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `6`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x18001c7a0`
- `0x18001eaf0`
- `0x18001f72c`
- `0x180022ae4`
- `0x180024c30`
- `0x180024d00`

## callees

- `0x1800020bc`
- `0x1800023c4`
- `0x180002604`
- `0x18000288c`
- `0x18000856c`
- `0x180010120`
- `0x180020338`
- `0x180027d7c`
- `0x180027e64`
- `0x18002824c`
- `0x18002eaac`
- `0x18003d864`
- `0x180041834`
- `0x180041a48`
- `0x1800481e4`
- `0x180048e20`
- `0x180048f78`
- `0x1800494f4`
- `0x180049924`
- `0x180049b50`
- `0x18004a03c`
- `0x18004ad26`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x1800207fd`
- `VCRUNTIME140!memcmp` at `0x1800207fd`
- `KERNEL32!LocalFree` at `0x1800209db`
- `KERNEL32!LocalFree` at `0x1800209db`
- `ole32!StringFromGUID2` at `0x180020398`
- `ole32!StringFromGUID2` at `0x180020398`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800207c6`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800207c6`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::CreateAndStartEtwSession(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  unsigned int v4; // r12d
  unsigned int v6; // edi
  __int64 v7; // rbx
  struct ATL::IAtlStringMgr *Instance; // rax
  _WORD *v9; // rcx
  __int16 v10; // ax
  int DirectoryPath; // ebx
  unsigned __int16 *v12; // rdx
  struct ATL::IAtlStringMgr *v14; // rax
  unsigned __int16 *v15; // rbx
  __int64 *v16; // rax
  __int64 v17; // rdx
  void (__fastcall ***v18)(_QWORD, __int64); // rcx
  __int64 *v19; // rax
  __int64 v20; // rdx
  void (__fastcall ***v21)(_QWORD, __int64); // rcx
  __int64 *v22; // rax
  __int64 v23; // rdx
  void (__fastcall ***v24)(_QWORD, __int64); // rcx
  __int64 *v25; // rax
  __int64 v26; // rdx
  void (__fastcall ***v27)(_QWORD, __int64); // rcx
  __int64 v28; // rcx
  const wchar_t *v29; // rbx
  unsigned int v30; // eax
  unsigned __int16 v31; // r8
  __int64 v32; // rcx
  void *v33; // r12
  unsigned __int16 *v34; // rdi
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r9
  int v39; // eax
  unsigned int v40; // r8d
  const unsigned __int16 *v41; // r8
  const struct _GUID *v42; // rdx
  unsigned int v43; // r14d
  __int64 v44; // rdx
  __int64 v45; // r9
  int v46; // eax
  unsigned int v47; // r8d
  unsigned __int16 *v48; // rdx
  unsigned __int16 *v49; // rdx
  unsigned __int16 *v50; // rdx
  unsigned __int16 *v51; // rdx
  _BYTE *v52; // rbx
  void (__fastcall ***v53)(_QWORD, __int64); // rcx
  __int64 v54; // rax
  const void *v55; // rbx
  const unsigned __int16 *v56; // r8
  const struct _GUID *v57; // rdx
  unsigned __int16 *v58; // [rsp+30h] [rbp-168h] BYREF
  unsigned int v59; // [rsp+38h] [rbp-160h]
  unsigned __int16 *v60; // [rsp+40h] [rbp-158h] BYREF
  HLOCAL hMem[2]; // [rsp+48h] [rbp-150h] BYREF
  int pExceptionObject; // [rsp+58h] [rbp-140h] BYREF
  int v63; // [rsp+5Ch] [rbp-13Ch] BYREF
  struct ITraceEventCallback *v64; // [rsp+60h] [rbp-138h]
  unsigned int v65; // [rsp+68h] [rbp-130h] BYREF
  OLECHAR sz[39]; // [rsp+70h] [rbp-128h] BYREF
  _WORD v67[73]; // [rsp+BEh] [rbp-DAh] BYREF
  __int128 v68; // [rsp+150h] [rbp-48h] BYREF
  _BYTE *v69; // [rsp+160h] [rbp-38h] BYREF

  v4 = a2;
  v59 = a2;
  hMem[0] = (HLOCAL)a1;
  v69 = (_BYTE *)a3;
  v6 = *(_DWORD *)(a1 + 860);
  v7 = 39;
  if ( !StringFromGUID2((const GUID *const)(a1 + 840), sz, 39) )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  v67[0] = 0;
  v67[39] = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v58 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                           + 24);
  if ( !v67[0] )
  {
    v9 = v67;
    while ( v7 != 3 )
    {
      v10 = *(v9 - 38);
      if ( v10 )
      {
        *v9++ = v10;
        if ( --v7 )
          continue;
      }
      if ( !v7 )
      {
        *(v9 - 1) = 0;
        v67[0] = 0;
        goto LABEL_11;
      }
      break;
    }
    *v9 = 0;
  }
LABEL_11:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v58,
    L"%s.%s.%d.",
    L"DiagHubEtwSession.17",
    v67,
    v6);
  if ( a1 )
  {
    v64 = (struct ITraceEventCallback *)(a1 + 1040);
    v4 = v59;
  }
  else
  {
    v64 = 0;
  }
  *(_BYTE *)(a3 + 104) = 1;
  DirectoryPath = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(
                    *(Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory **)(a1 + 3928),
                    (const unsigned __int16 **)&v68);
  if ( DirectoryPath < 0 )
  {
    _mm_lfence();
    v12 = v58 - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
    }
    return (unsigned int)DirectoryPath;
  }
  v14 = ATL::CAtlStringMgr::GetInstance();
  if ( !v14 )
    ATL::AtlThrowImpl(-2147467259);
  v60 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v14 + 24LL))(v14) + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v60,
    (const wchar_t *)v68);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( v4 )
    {
      switch ( v4 )
      {
        case 1u:
          ATL::CSimpleStringT<unsigned short,0>::Append(&v58, L"user_heap");
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            &v60,
            L"sc.%s.%d.etl",
            L"user_heap",
            v6);
          v15 = v58;
          v22 = (__int64 *)Microsoft::EventTrace::HeapTraceSession::Create((__int64)&v68, v58);
          break;
        case 2u:
          ATL::CSimpleStringT<unsigned short,0>::Append(&v58, L"user_npaged");
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            &v60,
            L"sc.%s.%d.etl",
            L"user_npaged",
            v6);
          v15 = v58;
          v22 = (__int64 *)Microsoft::EventTrace::UserSession::Create(&v68, v58);
          break;
        case 3u:
          ATL::CSimpleStringT<unsigned short,0>::Append(&v58, L"user_paged");
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            &v60,
            L"sc.%s.%d.etl",
            L"user_paged",
            v6);
          v15 = v58;
          v19 = (__int64 *)Microsoft::EventTrace::UserSession::Create(&v68, v58);
          v20 = *v19;
          *v19 = 0;
          v21 = *(void (__fastcall ****)(_QWORD, __int64))a3;
          *(_QWORD *)a3 = v20;
          if ( v21 )
            (**v21)(v21, 1);
          if ( (_QWORD)v68 )
            (**(void (__fastcall ***)(_QWORD, __int64))v68)(v68, 1);
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 8LL) + 64LL) |= 0x1000000u;
          goto LABEL_56;
        case 4u:
          ATL::CSimpleStringT<unsigned short,0>::Append(&v58, L"user_injected");
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            &v60,
            L"sc.%s.%d.etl",
            L"user_injected",
            v6);
          v15 = v58;
          v16 = (__int64 *)Microsoft::EventTrace::UserSession::Create(&v68, v58);
          v17 = *v16;
          *v16 = 0;
          v18 = *(void (__fastcall ****)(_QWORD, __int64))a3;
          *(_QWORD *)a3 = v17;
          if ( v18 )
            (**v18)(v18, 1);
          if ( (_QWORD)v68 )
            (**(void (__fastcall ***)(_QWORD, __int64))v68)(v68, 1);
          v64 = 0;
LABEL_55:
          *(_BYTE *)(a3 + 104) = 0;
          goto LABEL_56;
        default:
          v15 = v58;
LABEL_56:
          if ( memcmp((const void *)(a3 + 108), &GUID_NULL, 0x10u) )
            *(_OWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 8LL) + 24LL) = *(_OWORD *)(a3 + 108);
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 8LL) + 48LL) = *(_DWORD *)(a1 + 2680);
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 8LL) + 56LL) = *(_DWORD *)(a1 + 2688);
          v32 = *(_QWORD *)(*(_QWORD *)a3 + 8LL);
          *(_DWORD *)(v32 + 52) = *(_DWORD *)(a1 + 2684);
          if ( IsWindowsVersionOrGreater(v32, 3u, v31) )
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 8LL) + 64LL) |= 0x8000000u;
          if ( __eh34_try(0, 1) )
          {
            __eh34_scope_strut(1);
            if ( *(_BYTE *)(a1 + 2692) )
              *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 8LL) + 64LL) |= 0x10000000u;
            if ( *(_BYTE *)(a3 + 104) )
              std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,std::equal_to<_GUID>>,std::allocator<_GUID>,0>>::emplace<_GUID const &>(
                a3 + 16,
                &v68,
                a1 + 2648);
            v33 = operator new(0x120u);
            *(_QWORD *)&v68 = v33;
            memset_0(v33, 0, 0x120u);
            v34 = v60;
            v35 = ((_QWORD (__stdcall *)(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger *, unsigned int, const unsigned __int16 *, const unsigned __int16 *))Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::EtwCollectionSessionRelogger)(
                    (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger *)v33,
                    v59,
                    v15,
                    v60);
            v36 = *(_QWORD *)(a3 + 8);
            *(_QWORD *)(a3 + 8) = v35;
            if ( v36 )
              (**(void (__fastcall ***)(__int64, __int64))(v36 + 8))(v36 + 8, 1);
          }
          if ( __eh34_catch(1) )
          {
            if ( __eh34_catch_type(1, &std::bad_alloc `RTTI Type Descriptor', 0) )
            {
              v63 = -2147024882;
              throw (long *)&v63;
            }
          }
          goto LABEL_134;
      }
LABEL_40:
      v23 = *v22;
      *v22 = 0;
      v24 = *(void (__fastcall ****)(_QWORD, __int64))a3;
      *(_QWORD *)a3 = v23;
      if ( v24 )
        (**v24)(v24, 1);
      if ( (_QWORD)v68 )
        (**(void (__fastcall ***)(_QWORD, __int64))v68)(v68, 1);
      goto LABEL_56;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      &v60,
      L"sc.%s.%d.etl",
      L"kernel",
      v6);
    if ( !*(_BYTE *)(a1 + 3578) )
    {
      ATL::CSimpleStringT<unsigned short,0>::Append(&v58, L"kernel");
      v15 = v58;
      v22 = (__int64 *)Microsoft::EventTrace::SystemTraceSession::Create(&v68, v58);
      goto LABEL_40;
    }
    v25 = (__int64 *)Microsoft::EventTrace::NTKernelSession::Create(&v68);
    v26 = *v25;
    *v25 = 0;
    v27 = *(void (__fastcall ****)(_QWORD, __int64))a3;
    *(_QWORD *)a3 = v26;
    if ( v27 )
      (**v27)(v27, 1);
    if ( (_QWORD)v68 )
      (**(void (__fastcall ***)(_QWORD, __int64))v68)(v68, 1);
    v28 = *(_QWORD *)(*(_QWORD *)a3 + 8LL);
    if ( v28 && *(_DWORD *)(v28 + 116) )
    {
      v29 = (const wchar_t *)(v28 + *(unsigned int *)(v28 + 116));
      if ( v29 )
      {
        v30 = wcslen(v29);
LABEL_54:
        ATL::CSimpleStringT<unsigned short,0>::SetString((__int64 *)&v58, v29, v30);
        v15 = v58;
        goto LABEL_55;
      }
    }
    else
    {
      v29 = 0;
    }
    v30 = 0;
    goto LABEL_54;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v65) )
    {
      v52 = v69;
      v69[104] = 0;
      v53 = *(void (__fastcall ****)(_QWORD, __int64))v52;
      *(_QWORD *)v52 = 0;
      if ( v53 )
        (**v53)(v53, 1);
      v54 = *((_QWORD *)v52 + 1);
      *((_QWORD *)v52 + 1) = 0;
      if ( v54 )
        (**(void (__fastcall ***)(__int64, __int64))(v54 + 8))(v54 + 8, 1);
      std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,std::equal_to<_GUID>>,std::allocator<_GUID>,0>>::clear(v52 + 16);
      if ( *((_QWORD *)v52 + 10) != *((_QWORD *)v52 + 11) )
        *((_QWORD *)v52 + 11) = *((_QWORD *)v52 + 10);
      *(GUID *)(v52 + 108) = GUID_NULL;
      v55 = (const void *)(int)v65;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
        L"HRESULT during session construction: %#08x",
        v65);
      if ( (_DWORD)v55 == -2147024882 )
      {
        __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_180020B5D);
        v48 = v60 - 12;
        if ( _InterlockedDecrement((volatile signed __int32 *)v60 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v48 + 8LL))(*(_QWORD *)v48);
        }
        v49 = v58 - 12;
        if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v49 + 8LL))(*(_QWORD *)v49);
        }
        return 2147942414LL;
      }
      else
      {
        v69 = v55;
        v68 = 0;
        *(_QWORD *)&v68 = 0;
        DWORD2(v68) = -518979510;
        DiagHubCommon::HResultFormatter::Init(
          (DiagHubCommon::HResultFormatter *)&v68,
          *((_WORD *)hMem[0] + 348),
          -518979510,
          (const void **const)&v69);
        v57 = (const struct _GUID *)L"<unknown error>";
        if ( (_QWORD)v68 )
          v57 = (const struct _GUID *)v68;
        DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, (const OLECHAR *)v57, v56);
        v59 = DWORD2(v68);
        if ( (_QWORD)v68 && (const OLECHAR *)v68 != &word_180055D48 && (wchar_t *)v68 != L"Out of memory" )
          LocalFree((HLOCAL)v68);
        __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_180020BBA);
        v50 = v60 - 12;
        if ( _InterlockedDecrement((volatile signed __int32 *)v60 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v50 + 8LL))(*(_QWORD *)v50);
        }
        v51 = v58 - 12;
        if ( _InterlockedDecrement((volatile signed __int32 *)v58 - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v51 + 8LL))(*(_QWORD *)v51);
        }
        return v59;
      }
    }
  }
LABEL_134:
  if ( *(_QWORD *)_logger != *((_QWORD *)_logger + 1) )
  {
    v37 = *(_QWORD *)(*(_QWORD *)a3 + 8LL);
    if ( v37 && *(_DWORD *)(v37 + 116) )
      v38 = v37 + *(unsigned int *)(v37 + 116);
    else
      v38 = 0;
    DiagHubCommon::LogStream::Write(
      _logger,
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
      L"Starting ETW session: %s",
      v38);
  }
  v39 = Microsoft::EventTrace::Session::Start(*(Microsoft::EventTrace::Session **)a3);
  if ( v39 )
  {
    v40 = -518979560;
    if ( v39 == -2147024713 || v39 == -2147023446 )
      v40 = -518979557;
    *(_QWORD *)&v68 = v39;
    hMem[0] = 0;
    hMem[1] = (HLOCAL)v40;
    DiagHubCommon::HResultFormatter::Init(
      (DiagHubCommon::HResultFormatter *)hMem,
      *(_WORD *)(a1 + 696),
      v40,
      (const void **const)&v68);
    v42 = (const struct _GUID *)L"<unknown error>";
    if ( hMem[0] )
      v42 = (const struct _GUID *)hMem[0];
LABEL_78:
    DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, (const OLECHAR *)v42, v41);
    v43 = (unsigned int)hMem[1];
    if ( hMem[0] && hMem[0] != &word_180055D48 && hMem[0] != L"Out of memory" )
      LocalFree(hMem[0]);
    if ( _InterlockedDecrement((volatile signed __int32 *)v34 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v34 - 3) + 8LL))(*((_QWORD *)v34 - 3));
    }
    if ( _InterlockedDecrement((volatile signed __int32 *)v15 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
    }
    return v43;
  }
  if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
  {
    v44 = *(_QWORD *)(*(_QWORD *)a3 + 8LL);
    if ( v44 && *(_DWORD *)(v44 + 116) )
      v45 = v44 + *(unsigned int *)(v44 + 116);
    else
      v45 = 0;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
      L"Starting ETW session relogger for %s into file: '%s'",
      v45,
      *(_QWORD *)(*(_QWORD *)(a3 + 8) + 272LL));
  }
  v46 = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger::Start(
          *(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionRelogger **)(a3 + 8),
          v64);
  if ( v46 )
  {
    v47 = -518979509;
    if ( v46 == -518979527 )
      v47 = -518979527;
    *(_QWORD *)&v68 = v46;
    hMem[0] = 0;
    hMem[1] = (HLOCAL)v47;
    DiagHubCommon::HResultFormatter::Init(
      (DiagHubCommon::HResultFormatter *)hMem,
      *(_WORD *)(a1 + 696),
      v47,
      (const void **const)&v68);
    v42 = (const struct _GUID *)L"<unknown error>";
    if ( hMem[0] )
      v42 = (const struct _GUID *)hMem[0];
    goto LABEL_78;
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)v34 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v34 - 3) + 8LL))(*((_QWORD *)v34 - 3));
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)v15 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
  }
  return 0;
}

```

## disassembly

```asm
0x180020338  mov     [rsp+arg_8], rbx
0x18002033d  mov     [rsp+arg_18], rsi
0x180020342  push    rdi
0x180020343  push    r12
0x180020345  push    r13
0x180020347  push    r14
0x180020349  push    r15
0x18002034b  sub     rsp, 170h
0x180020352  mov     rax, cs:__security_cookie
0x180020359  xor     rax, rsp
0x18002035c  mov     [rsp+198h+var_30], rax
0x180020364  mov     r14, r8
0x180020367  mov     r12d, edx
0x18002036a  mov     [rsp+198h+var_160], edx
0x18002036e  mov     r13, rcx
0x180020371  mov     [rsp+198h+hMem], rcx
0x180020376  mov     [rsp+198h+var_38], r8
0x18002037e  mov     edi, [rcx+35Ch]
0x180020384  add     rcx, 348h; rguid
0x18002038b  mov     ebx, 27h ; '''
0x180020390  mov     r8d, ebx; cchMax
0x180020393  lea     rdx, [rsp+198h+sz]; lpsz
0x180020398  call    cs:__imp_StringFromGUID2
0x18002039e  xor     esi, esi
0x1800203a0  test    eax, eax
0x1800203a2  jz      loc_180020C41
0x1800203a8  mov     [rsp+198h+var_DA], si
0x1800203b0  mov     [rsp+198h+var_8C], si
0x1800203b8  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1800203bd  mov     rcx, rax
0x1800203c0  test    rax, rax
0x1800203c3  jz      loc_180020C5B
0x1800203c9  mov     rax, [rax]
0x1800203cc  mov     rax, [rax+18h]
0x1800203d0  call    cs:__guard_dispatch_icall_fptr
0x1800203d6  add     rax, 18h
0x1800203da  mov     [rsp+198h+var_168], rax
0x1800203df  mov     r15d, 1
0x1800203e5  cmp     [rsp+198h+var_DA], si
0x1800203ed  jnz     short loc_18002042B
0x1800203ef  lea     rcx, [rsp+198h+var_DA]
0x1800203f7  lea     rax, [rbx-3]
0x1800203fb  test    rax, rax
0x1800203fe  jz      short loc_180020428
0x180020400  movzx   eax, word ptr [rcx-4Ch]
0x180020404  test    ax, ax
0x180020407  jz      short loc_180020415
0x180020409  mov     [rcx], ax
0x18002040c  add     rcx, 2
0x180020410  sub     rbx, r15
0x180020413  jnz     short loc_1800203F7
0x180020415  test    rbx, rbx
0x180020418  jnz     short loc_180020428
0x18002041a  mov     [rcx-2], si
0x18002041e  mov     [rsp+198h+var_DA], si
0x180020426  jmp     short loc_18002042B
0x180020428  mov     [rcx], si
0x18002042b  mov     dword ptr [rsp+198h+var_178], edi
0x18002042f  lea     r9, [rsp+198h+var_DA]
0x180020437  lea     r8, aDiaghubetwsess; "DiagHubEtwSession.17"
0x18002043e  lea     rdx, aSSD; "%s.%s.%d."
0x180020445  lea     rcx, [rsp+198h+var_168]
0x18002044a  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18002044f  test    r13, r13
0x180020452  jz      short loc_180020467
0x180020454  lea     r12, [r13+410h]
0x18002045b  mov     [rsp+198h+var_138], r12
0x180020460  mov     r12d, [rsp+198h+var_160]
0x180020465  jmp     short loc_18002046C
0x180020467  mov     [rsp+198h+var_138], rsi
0x18002046c  mov     [r14+68h], r15b
0x180020470  lea     rdx, [rsp+198h+var_48]; unsigned __int16 **
0x180020478  mov     rcx, [r13+0F58h]; this
0x18002047f  call    ?GetDirectoryPath@SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJPEAPEBG@Z; Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(ushort const * *)
0x180020484  mov     ebx, eax
0x180020486  test    eax, eax
0x180020488  jns     short loc_1800204C0
0x18002048a  lfence
0x18002048d  mov     rdx, [rsp+198h+var_168]
0x180020492  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180020496  or      edi, 0FFFFFFFFh
0x180020499  mov     ecx, edi
0x18002049b  lock xadd [rdx+10h], ecx
0x1800204a0  add     ecx, edi
0x1800204a2  test    ecx, ecx
0x1800204a4  jg      short loc_1800204B9
0x1800204a6  lfence
0x1800204a9  mov     rcx, [rdx]
0x1800204ac  mov     rax, [rcx]
0x1800204af  mov     rax, [rax+8]
0x1800204b3  call    cs:__guard_dispatch_icall_fptr
0x1800204b9  mov     eax, ebx
0x1800204bb  jmp     loc_180020C14
0x1800204c0  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1800204c5  mov     rcx, rax
0x1800204c8  test    rax, rax
0x1800204cb  jz      loc_180020C66
0x1800204d1  mov     rax, [rax]
0x1800204d4  mov     rax, [rax+18h]
0x1800204d8  call    cs:__guard_dispatch_icall_fptr
0x1800204de  add     rax, 18h
0x1800204e2  mov     [rsp+198h+var_158], rax
0x1800204e7  mov     rdx, qword ptr [rsp+198h+var_48]
0x1800204ef  lea     rcx, [rsp+198h+var_158]
0x1800204f4  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800204f9  nop
0x1800204fa  mov     ecx, r12d
0x1800204fd  test    r12d, r12d
0x180020500  jz      loc_1800206D2
0x180020506  sub     ecx, 1
0x180020509  jz      loc_18002068F
0x18002050f  sub     ecx, 1
0x180020512  jz      loc_180020649
0x180020518  sub     ecx, 1
0x18002051b  jz      loc_1800205BB
0x180020521  cmp     ecx, 1
0x180020524  jnz     loc_1800205B1
0x18002052a  lea     rdx, aUserInjected; "user_injected"
0x180020531  lea     rcx, [rsp+198h+var_168]
0x180020536  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18002053b  mov     r9d, edi
0x18002053e  lea     r8, aUserInjected; "user_injected"
0x180020545  lea     rdx, aScSDEtl; "sc.%s.%d.etl"
0x18002054c  lea     rcx, [rsp+198h+var_158]
0x180020551  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180020556  mov     rbx, [rsp+198h+var_168]
0x18002055b  mov     rdx, rbx
0x18002055e  lea     rcx, [rsp+198h+var_48]
0x180020566  call    ?Create@UserSession@EventTrace@Microsoft@@SA?AV?$unique_ptr@VUserSession@EventTrace@Microsoft@@U?$default_delete@VUserSession@EventTrace@Microsoft@@@std@@@std@@PEBG0@Z; Microsoft::EventTrace::UserSession::Create(ushort const *,ushort const *)
0x18002056b  mov     rdx, [rax]
0x18002056e  mov     [rax], rsi
0x180020571  mov     rcx, [r14]
0x180020574  mov     [r14], rdx
0x180020577  test    rcx, rcx
0x18002057a  jz      short loc_18002058B
0x18002057c  mov     rax, [rcx]
0x18002057f  mov     edx, r15d
0x180020582  mov     rax, [rax]
0x180020585  call    cs:__guard_dispatch_icall_fptr
0x18002058b  mov     rcx, qword ptr [rsp+198h+var_48]
0x180020593  test    rcx, rcx
0x180020596  jz      short loc_1800205A7
0x180020598  mov     rax, [rcx]
0x18002059b  mov     edx, r15d
0x18002059e  mov     rax, [rax]
0x1800205a1  call    cs:__guard_dispatch_icall_fptr
0x1800205a7  mov     [rsp+198h+var_138], rsi
0x1800205ac  jmp     loc_1800207E8
0x1800205b1  mov     rbx, [rsp+198h+var_168]
0x1800205b6  jmp     loc_1800207EC
0x1800205bb  lea     rdx, aUserPaged; "user_paged"
0x1800205c2  lea     rcx, [rsp+198h+var_168]
0x1800205c7  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800205cc  mov     r9d, edi
0x1800205cf  lea     r8, aUserPaged; "user_paged"
0x1800205d6  lea     rdx, aScSDEtl; "sc.%s.%d.etl"
0x1800205dd  lea     rcx, [rsp+198h+var_158]
0x1800205e2  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800205e7  mov     rbx, [rsp+198h+var_168]
0x1800205ec  mov     rdx, rbx
0x1800205ef  lea     rcx, [rsp+198h+var_48]
0x1800205f7  call    ?Create@UserSession@EventTrace@Microsoft@@SA?AV?$unique_ptr@VUserSession@EventTrace@Microsoft@@U?$default_delete@VUserSession@EventTrace@Microsoft@@@std@@@std@@PEBG0@Z; Microsoft::EventTrace::UserSession::Create(ushort const *,ushort const *)
0x1800205fc  mov     rdx, [rax]
0x1800205ff  mov     [rax], rsi
0x180020602  mov     rcx, [r14]
0x180020605  mov     [r14], rdx
0x180020608  test    rcx, rcx
0x18002060b  jz      short loc_18002061C
0x18002060d  mov     rax, [rcx]
0x180020610  mov     edx, r15d
0x180020613  mov     rax, [rax]
0x180020616  call    cs:__guard_dispatch_icall_fptr
0x18002061c  mov     rcx, qword ptr [rsp+198h+var_48]
0x180020624  test    rcx, rcx
0x180020627  jz      short loc_180020638
0x180020629  mov     rax, [rcx]
0x18002062c  mov     edx, r15d
0x18002062f  mov     rax, [rax]
0x180020632  call    cs:__guard_dispatch_icall_fptr
0x180020638  mov     rax, [r14]
0x18002063b  mov     rcx, [rax+8]
0x18002063f  bts     dword ptr [rcx+40h], 18h
0x180020644  jmp     loc_1800207EC
0x180020649  lea     rdx, aUserNpaged; "user_npaged"
0x180020650  lea     rcx, [rsp+198h+var_168]
0x180020655  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18002065a  mov     r9d, edi
0x18002065d  lea     r8, aUserNpaged; "user_npaged"
0x180020664  lea     rdx, aScSDEtl; "sc.%s.%d.etl"
0x18002066b  lea     rcx, [rsp+198h+var_158]
0x180020670  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180020675  mov     rbx, [rsp+198h+var_168]
0x18002067a  mov     rdx, rbx
0x18002067d  lea     rcx, [rsp+198h+var_48]
0x180020685  call    ?Create@UserSession@EventTrace@Microsoft@@SA?AV?$unique_ptr@VUserSession@EventTrace@Microsoft@@U?$default_delete@VUserSession@EventTrace@Microsoft@@@std@@@std@@PEBG0@Z; Microsoft::EventTrace::UserSession::Create(ushort const *,ushort const *)
0x18002068a  jmp     loc_18002071C
0x18002068f  lea     rdx, aUserHeap; "user_heap"
0x180020696  lea     rcx, [rsp+198h+var_168]
0x18002069b  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800206a0  mov     r9d, edi
0x1800206a3  lea     r8, aUserHeap; "user_heap"
0x1800206aa  lea     rdx, aScSDEtl; "sc.%s.%d.etl"
0x1800206b1  lea     rcx, [rsp+198h+var_158]
0x1800206b6  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800206bb  mov     rbx, [rsp+198h+var_168]
0x1800206c0  mov     rdx, rbx
0x1800206c3  lea     rcx, [rsp+198h+var_48]
0x1800206cb  call    ?Create@HeapTraceSession@EventTrace@Microsoft@@SA?AV?$unique_ptr@VHeapTraceSession@EventTrace@Microsoft@@U?$default_delete@VHeapTraceSession@EventTrace@Microsoft@@@std@@@std@@PEBG0@Z; Microsoft::EventTrace::HeapTraceSession::Create(ushort const *,ushort const *)
0x1800206d0  jmp     short loc_18002068A
0x1800206d2  mov     r9d, edi
0x1800206d5  lea     r8, aKernel; "kernel"
0x1800206dc  lea     rdx, aScSDEtl; "sc.%s.%d.etl"
0x1800206e3  lea     rcx, [rsp+198h+var_158]
0x1800206e8  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800206ed  cmp     [r13+0DFAh], sil
0x1800206f4  jnz     short loc_180020761
0x1800206f6  lea     rdx, aKernel; "kernel"
0x1800206fd  lea     rcx, [rsp+198h+var_168]
0x180020702  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180020707  mov     rbx, [rsp+198h+var_168]
0x18002070c  mov     rdx, rbx
0x18002070f  lea     rcx, [rsp+198h+var_48]
0x180020717  call    ?Create@SystemTraceSession@EventTrace@Microsoft@@SA?AV?$unique_ptr@VSystemTraceSession@EventTrace@Microsoft@@U?$default_delete@VSystemTraceSession@EventTrace@Microsoft@@@std@@@std@@PEBG0@Z; Microsoft::EventTrace::SystemTraceSession::Create(ushort const *,ushort const *)
0x18002071c  mov     rdx, [rax]
0x18002071f  mov     [rax], rsi
0x180020722  mov     rcx, [r14]
0x180020725  mov     [r14], rdx
0x180020728  test    rcx, rcx
0x18002072b  jz      short loc_18002073C
0x18002072d  mov     rax, [rcx]
0x180020730  mov     edx, r15d
0x180020733  mov     rax, [rax]
0x180020736  call    cs:__guard_dispatch_icall_fptr
0x18002073c  mov     rcx, qword ptr [rsp+198h+var_48]
0x180020744  test    rcx, rcx
0x180020747  jz      loc_1800207EC
0x18002074d  mov     rax, [rcx]
0x180020750  mov     edx, r15d
0x180020753  mov     rax, [rax]
0x180020756  call    cs:__guard_dispatch_icall_fptr
0x18002075c  jmp     loc_1800207EC
0x180020761  lea     rcx, [rsp+198h+var_48]
0x180020769  call    ?Create@NTKernelSession@EventTrace@Microsoft@@SA?AV?$unique_ptr@VNTKernelSession@EventTrace@Microsoft@@U?$default_delete@VNTKernelSession@EventTrace@Microsoft@@@std@@@std@@IPEBG@Z; Microsoft::EventTrace::NTKernelSession::Create(uint,ushort const *)
0x18002076e  mov     rdx, [rax]
0x180020771  mov     [rax], rsi
0x180020774  mov     rcx, [r14]
0x180020777  mov     [r14], rdx
0x18002077a  test    rcx, rcx
0x18002077d  jz      short loc_18002078E
0x18002077f  mov     rax, [rcx]
0x180020782  mov     edx, r15d
0x180020785  mov     rax, [rax]
0x180020788  call    cs:__guard_dispatch_icall_fptr
0x18002078e  mov     rcx, qword ptr [rsp+198h+var_48]
0x180020796  test    rcx, rcx
0x180020799  jz      short loc_1800207AA
0x18002079b  mov     rax, [rcx]
0x18002079e  mov     edx, r15d
0x1800207a1  mov     rax, [rax]
0x1800207a4  call    cs:__guard_dispatch_icall_fptr
0x1800207aa  mov     rax, [r14]
0x1800207ad  mov     rcx, [rax+8]
0x1800207b1  test    rcx, rcx
0x1800207b4  jz      short loc_1800207CE
0x1800207b6  cmp     [rcx+74h], esi
0x1800207b9  jz      short loc_1800207CE
0x1800207bb  mov     ebx, [rcx+74h]
0x1800207be  add     rbx, rcx
0x1800207c1  jz      short loc_1800207D1
0x1800207c3  mov     rcx, rbx; String
0x1800207c6  call    cs:__imp_wcslen
0x1800207cc  jmp     short loc_1800207D3
0x1800207ce  mov     rbx, rsi
0x1800207d1  mov     eax, esi
0x1800207d3  mov     r8d, eax
0x1800207d6  mov     rdx, rbx
0x1800207d9  lea     rcx, [rsp+198h+var_168]
0x1800207de  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800207e3  mov     rbx, [rsp+198h+var_168]
0x1800207e8  mov     [r14+68h], sil
0x1800207ec  mov     r8d, 10h; Size
0x1800207f2  lea     rdx, GUID_NULL; Buf2
0x1800207f9  lea     rcx, [r14+6Ch]; Buf1
0x1800207fd  call    cs:__imp_memcmp
0x180020803  test    eax, eax
0x180020805  jz      short loc_180020818
0x180020807  movups  xmm0, xmmword ptr [r14+6Ch]
0x18002080c  mov     rax, [r14]
0x18002080f  mov     rcx, [rax+8]
0x180020813  movdqu  xmmword ptr [rcx+18h], xmm0
0x180020818  mov     rax, [r14]
0x18002081b  mov     rcx, [rax+8]
0x18002081f  mov     eax, [r13+0A78h]
0x180020826  mov     [rcx+30h], eax
0x180020829  mov     rax, [r14]
0x18002082c  mov     rcx, [rax+8]
0x180020830  mov     eax, [r13+0A80h]
0x180020837  mov     [rcx+38h], eax
0x18002083a  mov     rax, [r14]
0x18002083d  mov     rcx, [rax+8]; unsigned __int16
  ... truncated ...
```
