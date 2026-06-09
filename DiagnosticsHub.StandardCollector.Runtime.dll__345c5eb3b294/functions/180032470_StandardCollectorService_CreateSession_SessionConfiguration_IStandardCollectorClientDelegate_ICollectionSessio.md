# StandardCollectorService::CreateSession(SessionConfiguration *,IStandardCollectorClientDelegate *,ICollectionSession * *)

- ea: `0x180032470`
- end: `0x180033d7b`
- name: `?CreateSession@StandardCollectorService@@UEAAJPEAUSessionConfiguration@@PEAUIStandardCollectorClientDelegate@@PEAPEAUICollectionSession@@@Z`
- size: `6411`
- prototype: `__int64 __fastcall(StandardCollectorService *__hidden this, struct SessionConfiguration *, struct IStandardCollectorClientDelegate *, struct ICollectionSession **)`
- caller_count: `0`
- callee_count: `33`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800023c4`
- `0x180002604`
- `0x18000288c`
- `0x180003d54`
- `0x180007c38`
- `0x180007d7c`
- `0x18000a17c`
- `0x18002d9a4`
- `0x18002e994`
- `0x1800317d8`
- `0x180031db0`
- `0x180031fe4`
- `0x1800323b4`
- `0x180032470`
- `0x1800352ec`
- `0x180035c60`
- `0x180035f18`
- `0x1800360bc`
- `0x18003d864`
- `0x180040d8c`
- `0x180041834`
- `0x180041968`
- `0x180041a18`
- `0x180041e6c`
- `0x1800420ec`
- `0x180042334`
- `0x180042880`
- `0x180049b50`
- `0x18004a03c`
- `0x18004a078`
- `0x18004ad26`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!wcsrchr` at `0x180032829`
- `VCRUNTIME140!wcsrchr` at `0x180032829`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180032961`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1800329fc`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180032961`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x1800329fc`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180032aa2`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180032adb`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180032aa2`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180032adb`
- `KERNEL32!GetFileAttributesW` at `0x180032bfa`
- `KERNEL32!GetFileAttributesW` at `0x180032bfa`
- `KERNEL32!CreateFileW` at `0x1800328dc`
- `KERNEL32!CreateFileW` at `0x1800328dc`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800325a5`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800325cb`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800325a5`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800325cb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180033676`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180033873`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180033676`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180033873`
- `KERNEL32!AcquireSRWLockShared` at `0x180032590`
- `KERNEL32!AcquireSRWLockShared` at `0x180032590`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180033641`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180033641`
- `KERNEL32!CloseHandle` at `0x18003298a`
- `KERNEL32!CloseHandle` at `0x180032a22`
- `KERNEL32!CloseHandle` at `0x180032a80`
- `KERNEL32!CloseHandle` at `0x180032c50`
- `KERNEL32!CloseHandle` at `0x180032f07`
- `KERNEL32!CloseHandle` at `0x1800331ed`
- `KERNEL32!CloseHandle` at `0x180033347`
- `KERNEL32!CloseHandle` at `0x1800334c5`
- `KERNEL32!CloseHandle` at `0x1800335b0`
- `KERNEL32!CloseHandle` at `0x180033745`
- `KERNEL32!CloseHandle` at `0x180033824`
- `KERNEL32!CloseHandle` at `0x1800338fc`
- `KERNEL32!CloseHandle` at `0x1800339c2`
- `KERNEL32!CloseHandle` at `0x180033a8e`
- `KERNEL32!CloseHandle` at `0x180033b7a`
- `KERNEL32!CloseHandle` at `0x18003298a`
- `KERNEL32!CloseHandle` at `0x180032a22`
- `KERNEL32!CloseHandle` at `0x180032a80`
- `KERNEL32!CloseHandle` at `0x180032c50`
- `KERNEL32!CloseHandle` at `0x180032f07`
- `KERNEL32!CloseHandle` at `0x1800331ed`
- `KERNEL32!CloseHandle` at `0x180033347`
- `KERNEL32!CloseHandle` at `0x1800334c5`
- `KERNEL32!CloseHandle` at `0x1800335b0`
- `KERNEL32!CloseHandle` at `0x180033745`
- `KERNEL32!CloseHandle` at `0x180033824`
- `KERNEL32!CloseHandle` at `0x1800338fc`
- `KERNEL32!CloseHandle` at `0x1800339c2`
- `KERNEL32!CloseHandle` at `0x180033a8e`
- `KERNEL32!CloseHandle` at `0x180033b7a`
- `KERNEL32!GetLastError` at `0x1800328ee`
- `KERNEL32!GetLastError` at `0x18003296e`
- `KERNEL32!GetLastError` at `0x180032a06`
- `KERNEL32!GetLastError` at `0x180033c7f`
- `KERNEL32!GetLastError` at `0x1800328ee`
- `KERNEL32!GetLastError` at `0x18003296e`
- `KERNEL32!GetLastError` at `0x180032a06`
- `KERNEL32!GetLastError` at `0x180033c7f`
- `ole32!StringFromGUID2` at `0x180032da7`
- `ole32!StringFromGUID2` at `0x1800333ce`
- `ole32!StringFromGUID2` at `0x180032da7`
- `ole32!StringFromGUID2` at `0x1800333ce`
- `OLEAUT32!__imp_SysAllocString` at `0x180032cb1`
- `OLEAUT32!__imp_SysAllocString` at `0x180032cb1`
- `OLEAUT32!__imp_SysFreeString` at `0x180032c69`
- `OLEAUT32!__imp_SysFreeString` at `0x180032f2e`
- `OLEAUT32!__imp_SysFreeString` at `0x180033200`
- `OLEAUT32!__imp_SysFreeString` at `0x18003335a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800334d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800335c3`
- `OLEAUT32!__imp_SysFreeString` at `0x180033758`
- `OLEAUT32!__imp_SysFreeString` at `0x18003383c`
- `OLEAUT32!__imp_SysFreeString` at `0x180033914`
- `OLEAUT32!__imp_SysFreeString` at `0x1800339e0`
- `OLEAUT32!__imp_SysFreeString` at `0x180033aac`
- `OLEAUT32!__imp_SysFreeString` at `0x180033b98`
- `OLEAUT32!__imp_SysFreeString` at `0x180033bec`
- `OLEAUT32!__imp_SysFreeString` at `0x180032c69`
- `OLEAUT32!__imp_SysFreeString` at `0x180032f2e`
- `OLEAUT32!__imp_SysFreeString` at `0x180033200`
- `OLEAUT32!__imp_SysFreeString` at `0x18003335a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800334d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800335c3`
- `OLEAUT32!__imp_SysFreeString` at `0x180033758`
- `OLEAUT32!__imp_SysFreeString` at `0x18003383c`
- `OLEAUT32!__imp_SysFreeString` at `0x180033914`
- `OLEAUT32!__imp_SysFreeString` at `0x1800339e0`
- `OLEAUT32!__imp_SysFreeString` at `0x180033aac`
- `OLEAUT32!__imp_SysFreeString` at `0x180033b98`
- `OLEAUT32!__imp_SysFreeString` at `0x180033bec`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x1800327d9`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x1800327d9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180032c5f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180032ef1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180032f1d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003315b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800331de`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800331f6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033338`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033350`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800334b6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800334ce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800335a1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800335b9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033736`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003374e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033810`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003382d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800338e8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033905`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800339ae`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800339d1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033a7a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033a9d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033b66`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033b89`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180032c5f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180032ef1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180032f1d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003315b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800331de`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800331f6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033338`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033350`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800334b6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800334ce`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800335a1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800335b9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033736`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003374e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033810`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18003382d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800338e8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033905`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800339ae`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800339d1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033a7a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033a9d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033b66`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180033b89`

## string_xrefs

- `0x18003273f`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`
- `0x1800333fd`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`
- `0x180033612`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`
- `0x180033c8f`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`
- `0x180032738`: `Failed to create new session. Maximum number of sessions have already been reached: %s`
- `0x180033c88`: `Failed to resolve scratch path. Error code %#08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall StandardCollectorService::CreateSession(
        StandardCollectorService *this,
        struct SessionConfiguration *a2,
        struct IStandardCollectorClientDelegate *a3,
        struct ICollectionSession **a4)
{
  struct IStandardCollectorClientDelegate *v4; // rdi
  unsigned __int16 *v7; // r13
  void *v8; // rbx
  GUID *v9; // rbx
  unsigned __int16 v10; // r14
  signed int MessageResourceRootDirectory; // ebx
  int (__fastcall ***v13)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v14; // rax
  unsigned int MaxNumberOfSessions; // ebx
  unsigned int v16; // r14d
  struct ATL::IAtlStringMgr *Instance; // rax
  GUID *v18; // rbx
  const unsigned __int16 *v19; // r8
  const struct _GUID *v20; // rdx
  unsigned int v21; // esi
  wchar_t *v22; // rax
  const WCHAR *v23; // rcx
  GUID *FileW; // rax
  GUID *v25; // rbx
  signed int v26; // eax
  DWORD FinalPathNameByHandleW; // eax
  DWORD v28; // r14d
  signed int v29; // eax
  signed int v30; // eax
  unsigned __int64 v31; // r8
  DWORD v32; // eax
  DWORD v33; // ebx
  const unsigned __int16 *v34; // r8
  const struct _GUID *v35; // rdx
  OLECHAR *v36; // r14
  DWORD FileAttributesW; // eax
  volatile signed __int32 *v38; // r13
  struct ATL::IAtlStringMgr *v39; // rax
  __int64 v40; // rdx
  _WORD *v41; // rcx
  __int16 v42; // ax
  HANDLE v43; // rbx
  unsigned __int16 *v44; // rsi
  Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *v45; // rsi
  Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *v46; // rsi
  _DWORD *v47; // rax
  _DWORD *v48; // rax
  wchar_t *v49; // rsi
  int IsAdministrator; // eax
  Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *v51; // rcx
  __int64 v52; // rsi
  unsigned int Ptr_high; // edx
  StandardCollectorService *v54; // r13
  RTL_SRWLOCK *v55; // rsi
  _QWORD *v56; // rax
  volatile signed __int32 *v57; // rsi
  volatile signed __int32 *v58; // rbx
  volatile signed __int32 *v59; // rbx
  const unsigned __int16 *v60; // r8
  const struct _GUID *v61; // rdx
  DiagHubCommon::LogStream *v62; // rbx
  DWORD LastError; // eax
  int v64; // [rsp+40h] [rbp-268h]
  int v65; // [rsp+40h] [rbp-268h]
  DiagHubCommon::LogStream *v66; // [rsp+40h] [rbp-268h]
  PSRWLOCK SRWLock[2]; // [rsp+48h] [rbp-260h] BYREF
  GUID *rguid; // [rsp+58h] [rbp-250h] BYREF
  unsigned __int16 *v69; // [rsp+60h] [rbp-248h] BYREF
  __int128 v70; // [rsp+68h] [rbp-240h] BYREF
  LPWSTR lpszFilePath[2]; // [rsp+78h] [rbp-230h] BYREF
  __int64 v72; // [rsp+88h] [rbp-220h]
  HANDLE hObject; // [rsp+90h] [rbp-218h] BYREF
  void *Block; // [rsp+98h] [rbp-210h] BYREF
  struct IStandardCollectorClientDelegate *v75; // [rsp+A0h] [rbp-208h]
  BSTR bstrString; // [rsp+A8h] [rbp-200h]
  int pExceptionObject; // [rsp+B0h] [rbp-1F8h] BYREF
  int v78; // [rsp+B4h] [rbp-1F4h] BYREF
  StandardCollectorService *v79; // [rsp+B8h] [rbp-1F0h]
  struct ICollectionSession **v80; // [rsp+C8h] [rbp-1E0h] BYREF
  _QWORD v81[8]; // [rsp+D8h] [rbp-1D0h] BYREF
  _OWORD v82[2]; // [rsp+118h] [rbp-190h] BYREF
  unsigned __int16 *v83[2]; // [rsp+138h] [rbp-170h]
  _QWORD *v84; // [rsp+148h] [rbp-160h] BYREF
  Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *v85; // [rsp+150h] [rbp-158h] BYREF
  wchar_t *Str[2]; // [rsp+158h] [rbp-150h] BYREF
  __int128 v87; // [rsp+168h] [rbp-140h]
  wchar_t *v88; // [rsp+178h] [rbp-130h]
  OLECHAR sz[39]; // [rsp+180h] [rbp-128h] BYREF
  _WORD v90[39]; // [rsp+1CEh] [rbp-DAh] BYREF
  __int16 v91; // [rsp+21Ch] [rbp-8Ch]

  v80 = a4;
  v4 = a3;
  SRWLock[0] = (PSRWLOCK)a2;
  v79 = this;
  if ( !a2 || !a4 )
    return 2147500035LL;
  *a4 = 0;
  v75 = a3;
  if ( a3 )
    (*(void (__fastcall **)(struct IStandardCollectorClientDelegate *))(*(_QWORD *)a3 + 8LL))(a3);
  if ( !v4 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v4 = (struct IStandardCollectorClientDelegate *)operator new(0x18u);
      rguid = (GUID *)v4;
      *(_QWORD *)v4 = 0;
      *((_QWORD *)v4 + 2) = 1;
      *((_QWORD *)v4 + 1) = &CModuleRefCount::`vftable';
      if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&CModuleRefCount::s_ulcModuleRef) >= 0x7FFFFFFF )
        __fastfail(0xEu);
      *(_QWORD *)v4 = &Microsoft::DiagnosticsHub::StandardCollector::DefaultClientDelegate::`vftable'{for `IStandardCollectorClientDelegate'};
      *((_QWORD *)v4 + 1) = &Microsoft::DiagnosticsHub::StandardCollector::DefaultClientDelegate::`vftable'{for `CModuleRefCount'};
      v75 = v4;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180032553);
        goto LABEL_239;
      }
    }
  }
  v64 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 != 1 && *(_DWORD *)a2 != 2 || !*((_QWORD *)a2 + 4) )
    goto LABEL_245;
  v7 = (unsigned __int16 *)((char *)a2 + 40);
  LOWORD(v70) = *((_WORD *)a2 + 20);
  AcquireSRWLockShared(&::SRWLock);
  v8 = qword_180077138;
  if ( qword_180077138 )
  {
    rguid = 0;
    std::_Hash<std::_Umap_traits<unsigned short,HINSTANCE__ *,std::_Uhash_compare<unsigned short,std::hash<unsigned short>,std::equal_to<unsigned short>>,std::allocator<std::pair<unsigned short const,HINSTANCE__ *>>,0>>::find(
      qword_180077138,
      &rguid,
      &v70);
    v9 = (GUID *)*((_QWORD *)v8 + 1);
    ReleaseSRWLockShared(&::SRWLock);
    if ( rguid != v9 )
      goto LABEL_21;
  }
  else
  {
    ReleaseSRWLockShared(&::SRWLock);
  }
  v10 = *v7;
  MessageResourceRootDirectory = anonymous_namespace_::GetMessageResourceRootDirectory(&rguid);
  if ( MessageResourceRootDirectory < 0
    || (MessageResourceRootDirectory = DiagHubCommon::ResourceDll::EnsureInitialized(
                                         (const unsigned __int16 *)rguid,
                                         v10),
        MessageResourceRootDirectory < 0) )
  {
    _mm_lfence();
    if ( !v4 )
      return (unsigned int)MessageResourceRootDirectory;
LABEL_19:
    (*(void (__fastcall **)(struct IStandardCollectorClientDelegate *))(*(_QWORD *)v4 + 16LL))(v4);
    return (unsigned int)MessageResourceRootDirectory;
  }
LABEL_21:
  v13 = (int (__fastcall ***)(_QWORD, GUID *, _QWORD **))*((_QWORD *)this + 22);
  v14 = 0;
  v84 = 0;
  if ( v13 )
  {
    if ( (**v13)(v13, &GUID_f008dad5_0306_4b76_b24a_aea5779974d5, &v84) >= 0 )
    {
      v14 = v84;
    }
    else
    {
      v14 = 0;
      v84 = 0;
    }
  }
  if ( v14 )
  {
    MaxNumberOfSessions = anonymous_namespace_::GetMaxNumberOfSessions();
    if ( MaxNumberOfSessions != -1 )
    {
      v16 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v84 + 48LL))(v84, *v84);
      if ( v16 >= MaxNumberOfSessions )
      {
        Instance = ATL::CAtlStringMgr::GetInstance();
        if ( !Instance )
          ATL::AtlThrowImpl(-2147467259);
        _mm_lfence();
        rguid = (GUID *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                       + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          &rguid,
          L"%u",
          v16);
        *(_OWORD *)SRWLock = 0;
        v18 = rguid;
        DiagHubCommon::HResultFormatter::HResultFormatter(
          (DiagHubCommon::HResultFormatter *)SRWLock,
          -518979490,
          (const unsigned __int16 *)rguid,
          *v7);
        v20 = (const struct _GUID *)L"<unknown error>";
        if ( SRWLock[0] )
          v20 = (const struct _GUID *)SRWLock[0];
        DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v20, v19);
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 168),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
          L"Failed to create new session. Maximum number of sessions have already been reached: %s",
          v18);
        v21 = (unsigned int)SRWLock[1];
        DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)SRWLock);
        if ( _InterlockedDecrement((volatile signed __int32 *)v18[-1].Data4) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18[-2].Data4 + 8LL))(*(_QWORD *)v18[-2].Data4);
        }
        if ( v84 )
          (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
        if ( v4 )
          (*(void (__fastcall **)(struct IStandardCollectorClientDelegate *))(*(_QWORD *)v4 + 16LL))(v4);
        return v21;
      }
    }
  }
  *(_OWORD *)lpszFilePath = 0;
  v72 = 0;
  if ( wcscmp(*((const wchar_t **)a2 + 4), L"#") )
  {
    v32 = ExpandEnvironmentStringsW(*((LPCWSTR *)a2 + 4), 0, 0);
    v33 = v32;
    if ( v32 < 2 )
    {
      *(_OWORD *)SRWLock = 0;
      DiagHubCommon::HResultFormatter::HResultFormatter(
        (DiagHubCommon::HResultFormatter *)SRWLock,
        -518979522,
        *((const unsigned __int16 **)a2 + 4),
        *v7);
      v61 = (const struct _GUID *)L"<unknown error>";
      if ( SRWLock[0] )
        v61 = (const struct _GUID *)SRWLock[0];
      DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v61, v60);
      v62 = _logger;
      LastError = GetLastError();
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)v62 + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
        L"Failed to resolve scratch path. Error code %#08x",
        LastError);
      MessageResourceRootDirectory = (signed int)SRWLock[1];
      DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)SRWLock);
      std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
      if ( v84 )
        (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
      if ( !v4 )
        return (unsigned int)MessageResourceRootDirectory;
    }
    else
    {
      _mm_lfence();
      std::vector<unsigned short>::resize(lpszFilePath, v32 + 1LL);
      if ( ExpandEnvironmentStringsW(*((LPCWSTR *)a2 + 4), lpszFilePath[0], lpszFilePath[1] - lpszFilePath[0]) == v33 )
        goto LABEL_84;
      *(_OWORD *)SRWLock = 0;
      DiagHubCommon::HResultFormatter::HResultFormatter(
        (DiagHubCommon::HResultFormatter *)SRWLock,
        -518979522,
        *((const unsigned __int16 **)a2 + 4),
        *v7);
      v35 = (const struct _GUID *)L"<unknown error>";
      if ( SRWLock[0] )
        v35 = (const struct _GUID *)SRWLock[0];
      DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v35, v34);
      MessageResourceRootDirectory = (signed int)SRWLock[1];
      DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)SRWLock);
      std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
      if ( v84 )
        (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
      if ( !v4 )
        return (unsigned int)MessageResourceRootDirectory;
    }
    (*(void (__fastcall **)(struct IStandardCollectorClientDelegate *))(*(_QWORD *)v4 + 16LL))(v4);
    return (unsigned int)MessageResourceRootDirectory;
  }
  *(_OWORD *)Str = 0;
  v87 = 0;
  v88 = 0;
  MessageResourceRootDirectory = DiagHubCommon::ModulePath::GetModulePath(0);
  if ( MessageResourceRootDirectory < 0
    || ((v22 = wcsrchr(Str[0], 0x5Cu)) != 0
      ? (const WCHAR *)(*v22 = 0,
                        v23 = Str[0],
                        *((wchar_t **)&v87 + 1) = Str[0],
                        v88 = v22 + 1,
                        MessageResourceRootDirectory = 0)
      : (MessageResourceRootDirectory = -2147024735, v23 = (const WCHAR *)*((_QWORD *)&v87 + 1)),
        MessageResourceRootDirectory < 0) )
  {
    _mm_lfence();
    std::vector<unsigned short>::~vector<unsigned short>(Str);
    std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
    if ( v84 )
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
    if ( !v4 )
      return (unsigned int)MessageResourceRootDirectory;
    goto LABEL_19;
  }
  FileW = (GUID *)CreateFileW(v23, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
  v25 = FileW;
  if ( FileW == (GUID *)-1LL )
  {
    v26 = GetLastError();
    MessageResourceRootDirectory = (unsigned __int16)v26 | 0x80070000;
    if ( v26 <= 0 )
      MessageResourceRootDirectory = v26;
    std::vector<unsigned short>::~vector<unsigned short>(Str);
    std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
    if ( v84 )
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
    if ( !v4 )
      return (unsigned int)MessageResourceRootDirectory;
    goto LABEL_19;
  }
  rguid = FileW;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 0);
  v28 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
  {
    v29 = GetLastError();
    v21 = (unsigned __int16)v29 | 0x80070000;
    if ( v29 <= 0 )
      v21 = v29;
    if ( v25 )
      CloseHandle(v25);
    std::vector<unsigned short>::~vector<unsigned short>(Str);
    std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
    if ( v84 )
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
    if ( !v4 )
      return v21;
    goto LABEL_63;
  }
  std::vector<unsigned short>::resize(lpszFilePath, FinalPathNameByHandleW + 1LL);
  if ( !GetFinalPathNameByHandleW(v25, lpszFilePath[0], v28, 0) )
  {
    v30 = GetLastError();
    v21 = (unsigned __int16)v30 | 0x80070000;
    if ( v30 <= 0 )
      v21 = v30;
    if ( v25 )
      CloseHandle(v25);
    std::vector<unsigned short>::~vector<unsigned short>(Str);
    std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
    if ( v84 )
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
    if ( !v4 )
      return v21;
LABEL_63:
    (*(void (__fastcall **)(struct IStandardCollectorClientDelegate *))(*(_QWORD *)v4 + 16LL))(v4);
    return v21;
  }
  if ( v25 )
    CloseHandle(v25);
  std::vector<unsigned short>::~vector<unsigned short>(Str);
LABEL_84:
  MessageResourceRootDirectory = Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchAddBackslash(
                                   (Microsoft::DiagnosticsHub::UnifiedPlatform *)lpszFilePath[0],
                                   (unsigned __int16 *)(lpszFilePath[1] - lpszFilePath[0]),
                                   v31);
  if ( MessageResourceRootDirectory < 0 )
  {
    _mm_lfence();
    std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
    if ( v84 )
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
    if ( !v4 )
      return (unsigned int)MessageResourceRootDirectory;
    goto LABEL_19;
  }
  if ( lpszFilePath[0] )
  {
    v36 = SysAllocString(lpszFilePath[0]);
    bstrString = v36;
    if ( !v36 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    v36 = 0;
    bstrString = 0;
  }
  FileAttributesW = GetFileAttributesW(v36);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    SysFreeString(v36);
    std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
    if ( v84 )
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
LABEL_245:
    if ( v4 )
      (*(void (__fastcall **)(struct IStandardCollectorClientDelegate *))(*(_QWORD *)v4 + 16LL))(v4);
    return 2147942487LL;
  }
  Block = 0;
  hObject = 0;
  MessageResourceRootDirectory = anonymous_namespace_::GetUserTokenOfCaller(&Block, &hObject);
  if ( MessageResourceRootDirectory < 0 )
  {
    _mm_lfence();
    if ( hObject )
      CloseHandle(hObject);
    free(Block);
    SysFreeString(v36);
    std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
    if ( v84 )
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
    if ( !v4 )
      return (unsigned int)MessageResourceRootDirectory;
    goto LABEL_19;
  }
  v82[0] = *(_OWORD *)a2;
  v82[1] = *((_OWORD *)a2 + 1);
  v83[1] = *((unsigned __int16 **)a2 + 5);
  v83[0] = v36;
  *(_OWORD *)Str = 0;
  v87 = 0;
  v69 = (unsigned __int16 *)v79;
  v85 = (Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *)operator new(0xB0u);
  rguid = (GUID *)((char *)a2 + 16);
  v38 = (volatile signed __int32 *)std::_Ref_count_obj2<StandardCollectorService::SessionLifetimeMonitor>::_Ref_count_obj2<StandardCollectorService::SessionLifetimeMonitor>(
                                     v85,
                                     &v69,
                                     (char *)a2 + 16,
                                     (char *)a2 + 40);
  *(_QWORD *)&v87 = v38 + 4;
  *((_QWORD *)&v87 + 1) = v38;
  v85 = 0;
  v39 = ATL::CAtlStringMgr::GetInstance();
  if ( !v39 )
    ATL::AtlThrowImpl(-2147467259);
  v69 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v39 + 24LL))(v39) + 24);
  if ( !StringFromGUID2((const GUID *const)a2 + 1, sz, 39) )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  v90[0] = 0;
  v91 = 0;
  v40 = 39;
  v41 = v90;
  while ( v40 != 3 )
  {
    v42 = *(v41 - 38);
    if ( v42 )
    {
      *v41++ = v42;
      if ( --v40 )
        continue;
    }
    if ( !v40 )
    {
      *(v41 - 1) = 0;
      v90[0] = 0;
      goto LABEL_111;
    }
    break;
  }
  *v41 = 0;
LABEL_111:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v69,
    L"%s.scratch",
    v90);
  v43 = hObject;
  v44 = v69;
  LODWORD(v70) = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::Create(v83[0], v69, hObject, 1, &v85);
  if ( (int)v70 < 0 )
  {
    _mm_lfence();
    if ( _InterlockedDecrement((volatile signed __int32 *)v44 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v44 - 3) + 8LL))(*((_QWORD *)v44 - 3));
    }
    v45 = v85;
    if ( v85 )
    {
      Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::~SecuredDirectory(v85);
      operator delete(v45);
    }
    if ( v38 )
    {
      if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
        if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
      }
    }
    free(0);
    Str[0] = 0;
    if ( v43 )
    {
      CloseHandle(v43);
      hObject = 0;
    }
    free(Block);
    Block = 0;
    SysFreeString(v36);
    std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
    if ( v84 )
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
    if ( v4 )
      (*(void (__fastcall **)(struct IStandardCollectorClientDelegate *))(*(_QWORD *)v4 + 16LL))(v4);
    return (unsigned int)v70;
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)v44 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v44 - 3) + 8LL))(*((_QWORD *)v44 - 3));
  }
  if ( v64 == 1 )
  {
    v69 = (unsigned __int16 *)operator new(0x1A0u);
    memset_0(v69, 0, 0x1A0u);
    v70 = 0;
    v46 = v85;
    if ( v85 )
    {
      v48 = operator new(0x18u);
      v48[2] = 1;
      v48[3] = 1;
      *(_QWORD *)v48 = &std::_Ref_count_resource<Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *,std::default_delete<Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory>>::`vftable';
      *((_QWORD *)v48 + 2) = v46;
      *(_QWORD *)&v70 = v46;
      *((_QWORD *)&v70 + 1) = v48;
      v46 = 0;
      v85 = 0;
    }
    *(_QWORD *)&v70 = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSession::EtwCollectionSession(
                        (int)v69,
                        (int)v4,
                        (int)v82,
                        *((_QWORD *)v79 + 21),
                        (__int64)&v70,
                        (__int64)v43);
    Str[1] = (wchar_t *)v70;
  }
  else if ( v64 == 2 )
  {
    v69 = (unsigned __int16 *)operator new(0x198u);
    memset_0(v69, 0, 0x198u);
    v70 = 0;
    v46 = v85;
    if ( v85 )
    {
      v47 = operator new(0x18u);
      v47[2] = 1;
      v47[3] = 1;
      *(_QWORD *)v47 = &std::_Ref_count_resource<Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *,std::default_delete<Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory>>::`vftable';
      *((_QWORD *)v47 + 2) = v46;
      *(_QWORD *)&v70 = v46;
      *((_QWORD *)&v70 + 1) = v47;
      v46 = 0;
      v85 = 0;
    }
    *(_QWORD *)&v70 = Microsoft::DiagnosticsHub::StandardCollector::AgentHostCollectionSession::AgentHostCollectionSession(
                        (int)v69,
                        (int)v4,
                        (int)v82,
                        (int)&v70,
                        (__int64)v43);
    Str[1] = (wchar_t *)v70;
  }
  else
  {
    *(wchar_t **)&v70 = Str[1];
    v46 = v85;
  }
  if ( v46 )
  {
    Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::~SecuredDirectory(v46);
    operator delete(v46);
  }
  v49 = (wchar_t *)Block;
  v69 = (unsigned __int16 *)Block;
  Block = 0;
  free(0);
  Str[0] = v49;
  IsAdministrator = anonymous_namespace_::QueryIsAdministrator(v43);
  v65 = IsAdministrator;
  if ( IsAdministrator < 0 )
  {
    _mm_lfence();
    if ( v38 )
    {
      if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
        if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
      }
    }
    if ( (_QWORD)v70 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v70 + 16LL))(v70);
    free(v49);
    if ( v43 )
      CloseHandle(v43);
    free(0);
    SysFreeString(v36);
    std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
    if ( v84 )
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
    if ( !v4 )
      return (unsigned int)v65;
    goto LABEL_203;
  }
  if ( IsAdministrator )
  {
    v52 = v70;
  }
  else
  {
    v51 = 0;
    v85 = 0;
    v52 = v70;
    if ( (_QWORD)v70 )
    {
      if ( (**(int (__fastcall ***)(_QWORD, GUID *, Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory **))v70)(
             v70,
             &GUID_136ebf68_b310_41fd_a41f_853cee6cc0da,
             &v85) >= 0 )
      {
        v51 = v85;
      }
      else
      {
        v51 = 0;
        v85 = 0;
      }
    }
    if ( v51 )
    {
      v65 = (*(__int64 (__fastcall **)(Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *))(*(_QWORD *)v51 + 32LL))(v51);
      if ( v65 < 0 )
      {
        _mm_lfence();
        if ( v85 )
          (*(void (__fastcall **)(Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *, _QWORD))(*(_QWORD *)v85 + 16LL))(
            v85,
            *(_QWORD *)v85);
        if ( v38 )
        {
          if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
            if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
          }
        }
        if ( v52 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
        free(v69);
        if ( v43 )
          CloseHandle(v43);
        free(0);
        SysFreeString(v36);
        std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
        if ( v84 )
          (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
        if ( !v4 )
          return (unsigned int)v65;
        goto LABEL_203;
      }
      v66 = (DiagHubCommon::LogStream *)((char *)_logger + 56);
      if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
      {
        if ( !StringFromGUID2(rguid, sz, 39) )
        {
          v78 = -2147024882;
          throw (long *)&v78;
        }
        v90[0] = 0;
        v91 = 0;
        DiagHubCommon::LogStream::Write(
          v66,
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
          L"Starting session %s authorized",
          sz);
      }
      v51 = v85;
    }
    if ( v51 )
      (*(void (__fastcall **)(Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *))(*(_QWORD *)v51 + 16LL))(v51);
  }
  v65 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ICollectionSession **))v52)(
          v52,
          &GUID_92ea564a_3d21_47d2_a5b2_516a0dc5deb7,
          v80);
  if ( v65 < 0 )
  {
    _mm_lfence();
    if ( v38 )
    {
      if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
        if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    free(v69);
    if ( v43 )
      CloseHandle(v43);
    free(0);
    SysFreeString(v36);
    std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
    if ( v84 )
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
    if ( !v4 )
      return (unsigned int)v65;
    goto LABEL_203;
  }
  Ptr_high = HIDWORD(SRWLock[0][1].Ptr);
  if ( Ptr_high )
  {
    v65 = StandardCollectorService::SessionLifetimeMonitor::AddProcessToMonitor(
            (StandardCollectorService::SessionLifetimeMonitor *)(v38 + 4),
            Ptr_high);
    if ( v65 < 0 )
    {
      _mm_lfence();
      if ( v38 )
      {
        if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
          if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      free(v69);
      if ( v43 )
        CloseHandle(v43);
      free(0);
      SysFreeString(v36);
      std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
      if ( v84 )
        (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
      if ( !v4 )
        return (unsigned int)v65;
LABEL_203:
      (*(void (__fastcall **)(struct IStandardCollectorClientDelegate *))(*(_QWORD *)v4 + 16LL))(v4);
      return (unsigned int)v65;
    }
  }
  else
  {
    DiagHubCommon::LogStream::Write(
      _logger,
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
      L"No session lifetime monitor process ID supplied. Session lifetime must be explicitly handled.");
  }
  v54 = v79;
  v55 = (RTL_SRWLOCK *)((char *)v79 + 96);
  SRWLock[0] = (PSRWLOCK)((char *)v79 + 96);
  LODWORD(SRWLock[1]) = 1;
  AcquireSRWLockExclusive((PSRWLOCK)v79 + 12);
  if ( __eh34_try(-1, 4) )
  {
    __eh34_scope_strut(4);
    v56 = (_QWORD *)std::_Hash<std::_Umap_traits<_GUID,StandardCollectorService::SessionContainer,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<std::pair<_GUID const,StandardCollectorService::SessionContainer>>,0>>::_Try_emplace<_GUID const &,>(
                      (char *)v54 + 104,
                      &v80,
                      rguid);
    StandardCollectorService::SessionContainer::operator=(*v56 + 32LL, Str);
    ReleaseSRWLockExclusive(v55);
  }
  if ( __eh34_catch(4) )
  {
    if ( __eh34_catch_type(4, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      __eh34_try_continuation(4, &std::bad_alloc `RTTI Type Descriptor', &loc_18003386E);
      ReleaseSRWLockExclusive(SRWLock[0]);
      v59 = (volatile signed __int32 *)*((_QWORD *)&v87 + 1);
      if ( *((_QWORD *)&v87 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v87 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
          if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
        }
      }
      if ( Str[1] )
        (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)Str[1] + 16LL))(Str[1]);
      free(Str[0]);
      if ( hObject )
        CloseHandle(hObject);
      free(0);
      SysFreeString(bstrString);
      std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
      if ( !v84 )
        goto LABEL_239;
      goto LABEL_238;
    }
  }
  if ( __eh34_try(-1, 6) )
  {
    __eh34_scope_strut(6);
    v81[0] = &std::_Func_impl_no_alloc<_lambda_f6b43b3007c996eb32448fa6f735711a_,bool,_GUID const &>::`vftable';
    v81[1] = v54;
    v81[7] = v81;
    Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSession::CleanUpAbandonedSessions((__int64)v81);
  }
  if ( __eh34_catch(6) )
  {
    if ( __eh34_catch_type(6, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      __eh34_try_continuation(6, &std::bad_alloc `RTTI Type Descriptor', &loc_1800337A2);
      v58 = (volatile signed __int32 *)*((_QWORD *)&v87 + 1);
      if ( *((_QWORD *)&v87 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v87 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
          if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
        }
      }
      if ( Str[1] )
        (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)Str[1] + 16LL))(Str[1]);
      free(Str[0]);
      if ( hObject )
        CloseHandle(hObject);
      free(0);
      SysFreeString(bstrString);
      std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
      if ( !v84 )
        goto LABEL_239;
LABEL_238:
      (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
LABEL_239:
      if ( v75 )
        (*(void (__fastcall **)(struct IStandardCollectorClientDelegate *))(*(_QWORD *)v75 + 16LL))(v75);
      return 2147942414LL;
    }
  }
  (*(void (__fastcall **)(_QWORD, GUID *))(**((_QWORD **)v54 + 22) + 24LL))(*((_QWORD *)v54 + 22), rguid);
  v57 = (volatile signed __int32 *)*((_QWORD *)&v87 + 1);
  if ( *((_QWORD *)&v87 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v87 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
      if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
    }
  }
  if ( Str[1] )
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)Str[1] + 16LL))(Str[1]);
  free(Str[0]);
  if ( v43 )
    CloseHandle(v43);
  free(0);
  SysFreeString(v36);
  std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
  if ( v84 )
    (*(void (__fastcall **)(_QWORD *))(*v84 + 16LL))(v84);
  if ( v4 )
    (*(void (__fastcall **)(struct IStandardCollectorClientDelegate *))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x180032470  push    rbx
0x180032472  push    rsi
0x180032473  push    rdi
0x180032474  push    r12
0x180032476  push    r13
0x180032478  push    r14
0x18003247a  push    r15
0x18003247c  sub     rsp, 270h
0x180032483  mov     rax, cs:__security_cookie
0x18003248a  xor     rax, rsp
0x18003248d  mov     [rsp+2A8h+var_48], rax
0x180032495  mov     rax, r9
0x180032498  mov     [rsp+2A8h+var_1E0], rax
0x1800324a0  mov     rdi, r8
0x1800324a3  mov     rsi, rdx
0x1800324a6  mov     [rsp+2A8h+SRWLock], rdx
0x1800324ab  mov     r12, rcx
0x1800324ae  mov     [rsp+2A8h+var_1F0], rcx
0x1800324b6  xor     r15d, r15d
0x1800324b9  test    rdx, rdx
0x1800324bc  jz      loc_180033CF2
0x1800324c2  test    rax, rax
0x1800324c5  jz      loc_180033CF2
0x1800324cb  mov     [r9], r15
0x1800324ce  mov     [rsp+2A8h+var_208], r8
0x1800324d6  test    r8, r8
0x1800324d9  jz      short loc_1800324EC
0x1800324db  mov     rax, [r8]
0x1800324de  mov     rcx, r8
0x1800324e1  mov     rax, [rax+8]
0x1800324e5  call    cs:__guard_dispatch_icall_fptr
0x1800324eb  nop
0x1800324ec  test    rdi, rdi
0x1800324ef  jnz     short loc_180032558
0x1800324f1  lea     ecx, [rdi+18h]; Size
0x1800324f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800324f9  mov     rdi, rax
0x1800324fc  mov     [rsp+2A8h+rguid], rax
0x180032501  mov     [rax], r15
0x180032504  mov     qword ptr [rax+10h], 1
0x18003250c  lea     rax, ??_7CModuleRefCount@@6B@; const CModuleRefCount::`vftable'
0x180032513  mov     [rdi+8], rax
0x180032517  mov     eax, 1
0x18003251c  lock xadd cs:?s_ulcModuleRef@CModuleRefCount@@0KA, eax; ulong CModuleRefCount::s_ulcModuleRef
0x180032524  inc     eax
0x180032526  cmp     eax, 7FFFFFFFh
0x18003252b  jb      short loc_180032534
0x18003252d  mov     ecx, 0Eh
0x180032532  int     29h; Win8: RtlFailFast(ecx)
0x180032534  lea     rax, ??_7DefaultClientDelegate@StandardCollector@DiagnosticsHub@Microsoft@@6BIStandardCollectorClientDelegate@@@; const Microsoft::DiagnosticsHub::StandardCollector::DefaultClientDelegate::`vftable'{for `IStandardCollectorClientDelegate'}
0x18003253b  mov     [rdi], rax
0x18003253e  lea     rax, ??_7DefaultClientDelegate@StandardCollector@DiagnosticsHub@Microsoft@@6BCModuleRefCount@@@; const Microsoft::DiagnosticsHub::StandardCollector::DefaultClientDelegate::`vftable'{for `CModuleRefCount'}
0x180032545  mov     [rdi+8], rax
0x180032549  mov     [rsp+2A8h+var_208], rdi
0x180032551  jmp     short loc_180032558
0x180032553  jmp     loc_180033AD9
0x180032558  mov     eax, [rsi]
0x18003255a  mov     dword ptr [rsp+2A8h+var_268], eax
0x18003255e  cmp     eax, 1
0x180032561  jz      short loc_18003256D
0x180032563  cmp     eax, 2
0x180032566  jz      short loc_18003256D
0x180032568  jmp     loc_180033C19
0x18003256d  cmp     [rsi+20h], r15
0x180032571  jnz     short loc_180032578
0x180032573  jmp     loc_180033C19
0x180032578  lea     r13, [rsi+28h]
0x18003257c  movzx   eax, word ptr [r13+0]
0x180032581  mov     word ptr [rsp+2A8h+var_240], ax
0x180032586  lea     r14, SRWLock
0x18003258d  mov     rcx, r14; SRWLock
0x180032590  call    cs:__imp_AcquireSRWLockShared
0x180032596  mov     rbx, cs:qword_180077138
0x18003259d  test    rbx, rbx
0x1800325a0  jnz     short loc_1800325AD
0x1800325a2  mov     rcx, r14; SRWLock
0x1800325a5  call    cs:__imp_ReleaseSRWLockShared
0x1800325ab  jmp     short loc_1800325D8
0x1800325ad  mov     [rsp+2A8h+rguid], r15
0x1800325b2  lea     r8, [rsp+2A8h+var_240]
0x1800325b7  lea     rdx, [rsp+2A8h+rguid]
0x1800325bc  mov     rcx, rbx
0x1800325bf  call    ?find@?$_Hash@V?$_Umap_traits@GPEAUHINSTANCE__@@V?$_Uhash_compare@GU?$hash@G@std@@U?$equal_to@G@2@@std@@V?$allocator@U?$pair@$$CBGPEAUHINSTANCE__@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBGPEAUHINSTANCE__@@@std@@@std@@@std@@@2@AEBG@Z; std::_Hash<std::_Umap_traits<ushort,HINSTANCE__ *,std::_Uhash_compare<ushort,std::hash<ushort>,std::equal_to<ushort>>,std::allocator<std::pair<ushort const,HINSTANCE__ *>>,0>>::find(ushort const &)
0x1800325c4  mov     rbx, [rbx+8]
0x1800325c8  mov     rcx, r14; SRWLock
0x1800325cb  call    cs:__imp_ReleaseSRWLockShared
0x1800325d1  cmp     [rsp+2A8h+rguid], rbx
0x1800325d6  jnz     short loc_180032621
0x1800325d8  movzx   r14d, word ptr [r13+0]
0x1800325dd  lea     rcx, [rsp+2A8h+rguid]
0x1800325e2  call    _anonymous_namespace___GetMessageResourceRootDirectory
0x1800325e7  mov     ebx, eax
0x1800325e9  test    eax, eax
0x1800325eb  js      short loc_180032601
0x1800325ed  movzx   edx, r14w; unsigned __int16
0x1800325f1  mov     rcx, [rsp+2A8h+rguid]; unsigned __int16 *
0x1800325f6  call    ?EnsureInitialized@ResourceDll@DiagHubCommon@@CAJPEBGG@Z; DiagHubCommon::ResourceDll::EnsureInitialized(ushort const *,ushort)
0x1800325fb  mov     ebx, eax
0x1800325fd  test    eax, eax
0x1800325ff  jns     short loc_180032621
0x180032601  lfence
0x180032604  test    rdi, rdi
0x180032607  jz      short loc_18003261A
0x180032609  mov     rcx, [rdi]
0x18003260c  mov     rax, [rcx+10h]
0x180032610  mov     rcx, rdi
0x180032613  call    cs:__guard_dispatch_icall_fptr
0x180032619  nop
0x18003261a  mov     eax, ebx
0x18003261c  jmp     loc_180033CF7
0x180032621  mov     rcx, [r12+0B0h]
0x180032629  mov     rax, r15
0x18003262c  mov     [rsp+2A8h+var_160], rax
0x180032634  test    rcx, rcx
0x180032637  jz      short loc_18003266D
0x180032639  mov     rax, [rcx]
0x18003263c  lea     r8, [rsp+2A8h+var_160]
0x180032644  lea     rdx, _GUID_f008dad5_0306_4b76_b24a_aea5779974d5
0x18003264b  mov     rax, [rax]
0x18003264e  call    cs:__guard_dispatch_icall_fptr
0x180032654  test    eax, eax
0x180032656  jns     short loc_180032665
0x180032658  mov     rax, r15
0x18003265b  mov     [rsp+2A8h+var_160], rax
0x180032663  jmp     short loc_18003266D
0x180032665  mov     rax, [rsp+2A8h+var_160]
0x18003266d  test    rax, rax
0x180032670  jz      loc_1800327BD
0x180032676  call    _anonymous_namespace___GetMaxNumberOfSessions
0x18003267b  mov     ebx, eax
0x18003267d  cmp     eax, 0FFFFFFFFh
0x180032680  jz      loc_1800327BD
0x180032686  mov     rcx, [rsp+2A8h+var_160]
0x18003268e  mov     rdx, [rcx]
0x180032691  mov     rax, [rdx+30h]
0x180032695  call    cs:__guard_dispatch_icall_fptr
0x18003269b  mov     r14d, eax
0x18003269e  cmp     eax, ebx
0x1800326a0  jb      loc_1800327BD
0x1800326a6  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1800326ab  mov     rcx, rax
0x1800326ae  test    rax, rax
0x1800326b1  jz      loc_180033D1A
0x1800326b7  lfence
0x1800326ba  mov     rax, [rax]
0x1800326bd  mov     rax, [rax+18h]
0x1800326c1  call    cs:__guard_dispatch_icall_fptr
0x1800326c7  add     rax, 18h
0x1800326cb  mov     [rsp+2A8h+rguid], rax
0x1800326d0  mov     r8d, r14d
0x1800326d3  lea     rdx, aU; "%u"
0x1800326da  lea     rcx, [rsp+2A8h+rguid]
0x1800326df  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800326e4  xorps   xmm0, xmm0
0x1800326e7  movups  xmmword ptr [rsp+2A8h+SRWLock], xmm0
0x1800326ec  movzx   r9d, word ptr [r13+0]; unsigned __int16
0x1800326f1  mov     rbx, [rsp+2A8h+rguid]
0x1800326f6  mov     r8, rbx; unsigned __int16 *
0x1800326f9  mov     edx, 0E111005Eh; int
0x1800326fe  lea     rcx, [rsp+2A8h+SRWLock]; this
0x180032703  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JPEBGG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort const *,ushort)
0x180032708  nop
0x180032709  lea     rdx, aUnknownError; "<unknown error>"
0x180032710  cmp     [rsp+2A8h+SRWLock], r15
0x180032715  cmovnz  rdx, [rsp+2A8h+SRWLock]; struct _GUID *
0x18003271b  lea     rcx, IID_ICollectionSession; this
0x180032722  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x180032727  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003272e  add     rcx, 0A8h; this
0x180032735  mov     r9, rbx
0x180032738  lea     r8, aFailedToCreate_2; "Failed to create new session. Maximum n"...
0x18003273f  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180032746  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003274b  mov     esi, dword ptr [rsp+2A8h+SRWLock+8]
0x18003274f  lea     rcx, [rsp+2A8h+SRWLock]; this
0x180032754  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x180032759  nop
0x18003275a  lea     rdx, [rbx-18h]
0x18003275e  or      r12, 0FFFFFFFFFFFFFFFFh
0x180032762  mov     eax, r12d
0x180032765  lock xadd [rdx+10h], eax
0x18003276a  add     eax, r12d
0x18003276d  test    eax, eax
0x18003276f  jg      short loc_180032785
0x180032771  lfence
0x180032774  mov     rcx, [rdx]
0x180032777  mov     rax, [rcx]
0x18003277a  mov     rax, [rax+8]
0x18003277e  call    cs:__guard_dispatch_icall_fptr
0x180032784  nop
0x180032785  mov     rcx, [rsp+2A8h+var_160]
0x18003278d  test    rcx, rcx
0x180032790  jz      short loc_1800327A0
0x180032792  mov     rax, [rcx]
0x180032795  mov     rax, [rax+10h]
0x180032799  call    cs:__guard_dispatch_icall_fptr
0x18003279f  nop
0x1800327a0  test    rdi, rdi
0x1800327a3  jz      short loc_1800327B6
0x1800327a5  mov     rcx, [rdi]
0x1800327a8  mov     rax, [rcx+10h]
0x1800327ac  mov     rcx, rdi
0x1800327af  call    cs:__guard_dispatch_icall_fptr
0x1800327b5  nop
0x1800327b6  mov     eax, esi
0x1800327b8  jmp     loc_180033CF7
0x1800327bd  xorps   xmm1, xmm1
0x1800327c0  movdqu  xmmword ptr [rsp+2A8h+lpszFilePath], xmm1
0x1800327c6  mov     [rsp+2A8h+var_220], r15
0x1800327ce  lea     rdx, asc_18005D1F0; "#"
0x1800327d5  mov     rcx, [rsi+20h]; String1
0x1800327d9  call    cs:__imp_wcscmp
0x1800327df  test    eax, eax
0x1800327e1  jnz     loc_180032A99
0x1800327e7  xorps   xmm0, xmm0
0x1800327ea  movdqu  xmmword ptr [rsp+2A8h+Str], xmm0
0x1800327f3  xorps   xmm1, xmm1
0x1800327f6  movdqu  [rsp+2A8h+var_140], xmm1
0x1800327ff  mov     [rsp+2A8h+var_130], r15
0x180032807  lea     rdx, [rsp+2A8h+Str]
0x18003280f  xor     ecx, ecx; hModule
0x180032811  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x180032816  mov     ebx, eax
0x180032818  test    eax, eax
0x18003281a  js      short loc_18003286A
0x18003281c  mov     edx, 5Ch ; '\'; Ch
0x180032821  mov     rcx, [rsp+2A8h+Str]; Str
0x180032829  call    cs:__imp_wcsrchr
0x18003282f  test    rax, rax
0x180032832  jnz     short loc_180032843
0x180032834  mov     ebx, 800700A1h
0x180032839  mov     rcx, qword ptr [rsp+2A8h+var_140+8]
0x180032841  jmp     short loc_180032866
0x180032843  mov     [rax], r15w
0x180032847  mov     rcx, [rsp+2A8h+Str]; lpFileName
0x18003284f  mov     qword ptr [rsp+2A8h+var_140+8], rcx
0x180032857  add     rax, 2
0x18003285b  mov     [rsp+2A8h+var_130], rax
0x180032863  mov     ebx, r15d
0x180032866  test    ebx, ebx
0x180032868  jns     short loc_1800328BC
0x18003286a  lfence
0x18003286d  lea     rcx, [rsp+2A8h+Str]
0x180032875  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003287a  nop
0x18003287b  lea     rcx, [rsp+2A8h+lpszFilePath]
0x180032880  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180032885  nop
0x180032886  mov     rcx, [rsp+2A8h+var_160]
0x18003288e  test    rcx, rcx
0x180032891  jz      short loc_1800328A1
0x180032893  mov     rax, [rcx]
0x180032896  mov     rax, [rax+10h]
0x18003289a  call    cs:__guard_dispatch_icall_fptr
0x1800328a0  nop
0x1800328a1  test    rdi, rdi
0x1800328a4  jz      short loc_1800328B7
0x1800328a6  mov     rcx, [rdi]
0x1800328a9  mov     rax, [rcx+10h]
0x1800328ad  mov     rcx, rdi
0x1800328b0  call    cs:__guard_dispatch_icall_fptr
0x1800328b6  nop
0x1800328b7  jmp     loc_18003261A
0x1800328bc  mov     [rsp+2A8h+hTemplateFile], r15; hTemplateFile
0x1800328c1  mov     [rsp+2A8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800328c9  mov     r8d, 3; dwShareMode
0x1800328cf  mov     [rsp+2A8h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800328d4  xor     r9d, r9d; lpSecurityAttributes
0x1800328d7  mov     edx, 80000000h; dwDesiredAccess
0x1800328dc  call    cs:__imp_CreateFileW
0x1800328e2  mov     rbx, rax
0x1800328e5  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800328e9  cmp     rax, r12
0x1800328ec  jnz     short loc_180032951
0x1800328ee  call    cs:__imp_GetLastError
0x1800328f4  movzx   ebx, ax
0x1800328f7  or      ebx, 80070000h
0x1800328fd  test    eax, eax
0x1800328ff  cmovle  ebx, eax
0x180032902  lea     rcx, [rsp+2A8h+Str]
0x18003290a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003290f  nop
0x180032910  lea     rcx, [rsp+2A8h+lpszFilePath]
0x180032915  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003291a  nop
0x18003291b  mov     rcx, [rsp+2A8h+var_160]
0x180032923  test    rcx, rcx
0x180032926  jz      short loc_180032936
0x180032928  mov     rax, [rcx]
0x18003292b  mov     rax, [rax+10h]
0x18003292f  call    cs:__guard_dispatch_icall_fptr
0x180032935  nop
0x180032936  test    rdi, rdi
0x180032939  jz      short loc_18003294C
0x18003293b  mov     rcx, [rdi]
0x18003293e  mov     rax, [rcx+10h]
0x180032942  mov     rcx, rdi
0x180032945  call    cs:__guard_dispatch_icall_fptr
0x18003294b  nop
0x18003294c  jmp     loc_18003261A
  ... truncated ...
```
