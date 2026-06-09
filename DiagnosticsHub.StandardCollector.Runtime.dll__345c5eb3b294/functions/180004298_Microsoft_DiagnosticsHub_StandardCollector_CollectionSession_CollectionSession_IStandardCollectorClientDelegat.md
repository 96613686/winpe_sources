# Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::CollectionSession(IStandardCollectorClientDelegate *,SessionConfiguration const &,std::shared_ptr<Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory>,void *,std::function<Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController * (void *)>)

- ea: `0x180004298`
- end: `0x18000491a`
- name: `??0CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@PEAUIStandardCollectorClientDelegate@@AEBUSessionConfiguration@@V?$shared_ptr@VSecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@@std@@PEAXV?$function@$$A6APEAVCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@PEAX@Z@7@@Z`
- size: `1666`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007c38`
- `0x180007d7c`

## callees

- `0x1800023c4`
- `0x180002604`
- `0x18000288c`
- `0x180004298`
- `0x1800084d0`
- `0x18000a224`
- `0x18000a2d0`
- `0x18002eaac`
- `0x18003d864`
- `0x180049b50`
- `0x18004a03c`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memset` at `0x180004467`
- `VCRUNTIME140!memset` at `0x180004467`
- `KERNEL32!GetCurrentProcess` at `0x180004555`
- `KERNEL32!GetCurrentProcess` at `0x18000455e`
- `KERNEL32!GetCurrentProcess` at `0x180004555`
- `KERNEL32!GetCurrentProcess` at `0x18000455e`
- `KERNEL32!DuplicateHandle` at `0x18000458e`
- `KERNEL32!DuplicateHandle` at `0x18000458e`
- `KERNEL32!InitializeSRWLock` at `0x18000442c`
- `KERNEL32!InitializeSRWLock` at `0x18000442c`
- `KERNEL32!CreateEventW` at `0x1800045e1`
- `KERNEL32!CreateEventW` at `0x1800045e1`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800047c9`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800047c9`
- `KERNEL32!AcquireSRWLockShared` at `0x18000479e`
- `KERNEL32!AcquireSRWLockShared` at `0x18000479e`
- `KERNEL32!InitializeCriticalSection` at `0x1800043ba`
- `KERNEL32!InitializeCriticalSection` at `0x1800043ed`
- `KERNEL32!InitializeCriticalSection` at `0x1800043ba`
- `KERNEL32!InitializeCriticalSection` at `0x1800043ed`
- `KERNEL32!GetLastError` at `0x1800045f6`
- `KERNEL32!GetLastError` at `0x18000460f`
- `KERNEL32!GetLastError` at `0x1800048c0`
- `KERNEL32!GetLastError` at `0x1800045f6`
- `KERNEL32!GetLastError` at `0x18000460f`
- `KERNEL32!GetLastError` at `0x1800048c0`
- `ole32!StringFromGUID2` at `0x1800044ce`
- `ole32!StringFromGUID2` at `0x1800046f1`
- `ole32!StringFromGUID2` at `0x1800044ce`
- `ole32!StringFromGUID2` at `0x1800046f1`
- `OLEAUT32!__imp_SysAllocString` at `0x180004410`
- `OLEAUT32!__imp_SysAllocString` at `0x180004410`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047f5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047f5`
- `OLEAUT32!__imp_VariantInit` at `0x180004470`
- `OLEAUT32!__imp_VariantInit` at `0x180004470`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x18000468e`
- `MSVCP140!?_Xbad_function_call@std@@YAXXZ` at `0x18000468e`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18000453c`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18000453c`

## string_xrefs

- `0x180004779`: `Session created.`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::CollectionSession(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        __int64 a6)
{
  BSTR v9; // rax
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v11; // rsi
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  wchar_t v14; // ax
  int v15; // eax
  HANDLE CurrentProcess; // rbx
  HANDLE v17; // rax
  char *v18; // r14
  _QWORD *v19; // rbx
  const WCHAR *v20; // r9
  HANDLE EventW; // rax
  signed int v22; // eax
  unsigned int v23; // ecx
  volatile signed __int32 *v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rcx
  int DirectoryPath; // eax
  wchar_t *v29; // rcx
  wchar_t v30; // ax
  __int64 v31; // rdx
  volatile signed __int32 *v32; // rbx
  __int64 v33; // rcx
  signed int LastError; // eax
  unsigned int v36; // ecx
  BSTR bstrString; // [rsp+40h] [rbp-158h] BYREF
  int pExceptionObject; // [rsp+48h] [rbp-150h] BYREF
  unsigned int v39; // [rsp+4Ch] [rbp-14Ch] BYREF
  int v40; // [rsp+50h] [rbp-148h] BYREF
  int v41; // [rsp+54h] [rbp-144h] BYREF
  int v42; // [rsp+58h] [rbp-140h] BYREF
  __int64 v43; // [rsp+60h] [rbp-138h]
  __int64 v44; // [rsp+68h] [rbp-130h]
  OLECHAR sz[39]; // [rsp+70h] [rbp-128h] BYREF
  wchar_t String[39]; // [rsp+BEh] [rbp-DAh] BYREF
  __int16 v47; // [rsp+10Ch] [rbp-8Ch]
  HANDLE hSourceHandle; // [rsp+150h] [rbp-48h] BYREF
  int v49; // [rsp+158h] [rbp-40h]
  __int64 v50; // [rsp+160h] [rbp-38h]

  v43 = a1;
  v44 = a4;
  hSourceHandle = a5;
  v50 = a6;
  *(_DWORD *)(a1 + 56) = 1;
  *(_QWORD *)(a1 + 48) = &CModuleRefCount::`vftable';
  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&CModuleRefCount::s_ulcModuleRef) >= 0x7FFFFFFF )
    __fastfail(0xEu);
  *(_QWORD *)a1 = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `ICollectionSession'};
  *(_QWORD *)(a1 + 8) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `ICollectionSessionPausable'};
  *(_QWORD *)(a1 + 16) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::ICollectionSessionEx'};
  *(_QWORD *)(a1 + 24) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `IDebuggerCollectionSession'};
  *(_QWORD *)(a1 + 32) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `IStandardCollectorVersion'};
  *(_QWORD *)(a1 + 40) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `ISupportErrorInfo'};
  *(_QWORD *)(a1 + 48) = &Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `CModuleRefCount'};
  *(_OWORD *)(a1 + 64) = *(_OWORD *)(a3 + 16);
  *(_DWORD *)(a1 + 80) = *(_DWORD *)(a3 + 4);
  *(_WORD *)(a1 + 84) = *(_WORD *)(a3 + 40);
  *(_BYTE *)(a1 + 86) = (*(_DWORD *)(a3 + 8) & 2) != 0;
  *(_BYTE *)(a1 + 87) = (*(_DWORD *)(a3 + 8) & 0x20) != 0;
  *(_WORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_OWORD *)(a1 + 104) = 0;
  *(_OWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_OWORD *)(a1 + 168) = 0;
  *(_OWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 168));
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  v9 = SysAllocString(L"Notify.");
  *(_QWORD *)(a1 + 224) = v9;
  if ( !v9 )
    ATL::AtlThrowImpl(-2147024882);
  InitializeSRWLock((PSRWLOCK)(a1 + 232));
  *(_QWORD *)(a1 + 240) = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  *(_QWORD *)(a1 + 248) = 0;
  memset((void *)(a1 + 256), 0, 0x18u);
  VariantInit((VARIANTARG *)(a1 + 256));
  DiagHubCommon::HubTask<long,0>::HubTask<long,0>(a1 + 280);
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  *(_QWORD *)(a1 + 392) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                        + 24;
  *(_DWORD *)(a1 + 400) = 0;
  *(_DWORD *)(a1 + 404) = 1;
  v11 = 39;
  if ( !StringFromGUID2((const GUID *const)(a1 + 64), sz, 39) )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  String[0] = 0;
  v47 = 0;
  v12 = 39;
  v13 = String;
  while ( v12 != 3 )
  {
    v14 = *(v13 - 38);
    if ( v14 )
    {
      *v13++ = v14;
      if ( --v12 )
        continue;
    }
    if ( !v12 )
    {
      *(v13 - 1) = 0;
      String[0] = 0;
      goto LABEL_15;
    }
    break;
  }
  *v13 = 0;
LABEL_15:
  v15 = wcslen(String);
  ATL::CComBSTR::Append((ATL::CComBSTR *)(a1 + 224), String, v15);
  CurrentProcess = GetCurrentProcess();
  v17 = GetCurrentProcess();
  if ( !DuplicateHandle(v17, hSourceHandle, CurrentProcess, (LPHANDLE)(a1 + 96), 0, 0, 2u) )
  {
    LastError = GetLastError();
    v36 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v36 = LastError;
    v39 = v36;
    throw (long *)&v39;
  }
  try
  {
    v18 = (char *)operator new(0x20u);
    *((_DWORD *)v18 + 2) = 1;
    *((_DWORD *)v18 + 3) = 1;
    *(_QWORD *)v18 = &std::_Ref_count_obj2<DiagHubCommon::AutoEvent>::`vftable';
    v19 = v18 + 16;
    v20 = *(const WCHAR **)(a1 + 224);
    *((_QWORD *)v18 + 2) = -1;
    *((_DWORD *)v18 + 6) = 0;
    EventW = CreateEventW(0, 0, 0, v20);
    *((_QWORD *)v18 + 2) = EventW;
    if ( EventW )
    {
      if ( GetLastError() == 183 )
        *((_DWORD *)v18 + 6) = 1;
    }
    else
    {
      *v19 = -1;
      v22 = GetLastError();
      v23 = (unsigned __int16)v22 | 0x80070000;
      if ( v22 <= 0 )
        v23 = v22;
      *((_DWORD *)v18 + 6) = v23;
    }
    *(_QWORD *)(a1 + 208) = v19;
    v24 = *(volatile signed __int32 **)(a1 + 216);
    *(_QWORD *)(a1 + 216) = v18;
    if ( v24 )
    {
      if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    hSourceHandle = *(HANDLE *)(a1 + 96);
    v25 = *(_QWORD *)(a6 + 56);
    if ( !v25 )
      std::_Xbad_function_call();
    v26 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v25 + 16LL))(v25, &hSourceHandle);
    v27 = *(_QWORD *)(a1 + 248);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    *(_QWORD *)(a1 + 248) = v26;
  }
  catch ( std::bad_alloc )
  {
    v42 = -2147024882;
    throw (long *)&v42;
  }
  DirectoryPath = Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(
                    *(Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory **)a4,
                    (const unsigned __int16 **)&hSourceHandle);
  if ( DirectoryPath < 0 )
  {
    v40 = DirectoryPath;
    throw (long *)&v40;
  }
  if ( !StringFromGUID2((const GUID *const)(a1 + 64), sz, 39) )
  {
    v41 = -2147024882;
    throw (long *)&v41;
  }
  String[0] = 0;
  v47 = 0;
  v29 = String;
  while ( v11 != 3 )
  {
    v30 = *(v29 - 38);
    if ( v30 )
    {
      *v29++ = v30;
      if ( --v11 )
        continue;
    }
    if ( !v11 )
    {
      *(v29 - 1) = 0;
      String[0] = 0;
      goto LABEL_41;
    }
    break;
  }
  *v29 = 0;
LABEL_41:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    (_QWORD *)(a1 + 392),
    L"%s%s.counters",
    hSourceHandle,
    String);
  bstrString = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, "Session created.");
  hSourceHandle = (HANDLE)(a1 + 232);
  v49 = 0;
  AcquireSRWLockShared((PSRWLOCK)(a1 + 232));
  (*(void (__fastcall **)(_QWORD, __int128 *, BSTR))(**(_QWORD **)(a1 + 240) + 24LL))(
    *(_QWORD *)(a1 + 240),
    &xmmword_180076FE0,
    bstrString);
  ReleaseSRWLockShared((PSRWLOCK)(a1 + 232));
  if ( *(_BYTE *)(a1 + 86) )
    DiagHubCommon::LogStream::Write(
      _logger,
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
      L"Collection with debugger enabled");
  SysFreeString(bstrString);
  v32 = *(volatile signed __int32 **)(a4 + 8);
  if ( v32 )
  {
    if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
      if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
    }
  }
  v33 = *(_QWORD *)(a6 + 56);
  if ( v33 )
  {
    LOBYTE(v31) = v33 != a6;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 32LL))(v33, v31);
    *(_QWORD *)(a6 + 56) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180004298  mov     r11, rsp
0x18000429b  mov     [r11+10h], rbx
0x18000429f  mov     [r11+18h], rsi
0x1800042a3  push    rdi
0x1800042a4  push    r12
0x1800042a6  push    r13
0x1800042a8  push    r14
0x1800042aa  push    r15
0x1800042ac  sub     rsp, 170h
0x1800042b3  mov     rax, cs:__security_cookie
0x1800042ba  xor     rax, rsp
0x1800042bd  mov     [rsp+198h+var_30], rax
0x1800042c5  mov     r12, r9
0x1800042c8  mov     rbx, rdx
0x1800042cb  mov     rdi, rcx
0x1800042ce  mov     [rsp+198h+var_138], rcx
0x1800042d3  mov     [rsp+198h+var_130], r9
0x1800042d8  mov     rax, [rsp+198h+arg_20]
0x1800042e0  mov     [rsp+198h+hSourceHandle], rax
0x1800042e8  mov     r15, [rsp+198h+arg_28]
0x1800042f0  mov     [r11-38h], r15
0x1800042f4  xor     esi, esi
0x1800042f6  mov     dword ptr [rcx+38h], 1
0x1800042fd  lea     rax, ??_7CModuleRefCount@@6B@; const CModuleRefCount::`vftable'
0x180004304  mov     [rcx+30h], rax
0x180004308  lea     eax, [rsi+1]
0x18000430b  lock xadd cs:?s_ulcModuleRef@CModuleRefCount@@0KA, eax; ulong CModuleRefCount::s_ulcModuleRef
0x180004313  inc     eax
0x180004315  cmp     eax, 7FFFFFFFh
0x18000431a  jb      short loc_180004321
0x18000431c  lea     ecx, [rsi+0Eh]
0x18000431f  int     29h; Win8: RtlFailFast(ecx)
0x180004321  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BICollectionSession@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `ICollectionSession'}
0x180004328  mov     [rdi], rax
0x18000432b  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BICollectionSessionPausable@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `ICollectionSessionPausable'}
0x180004332  mov     [rdi+8], rax
0x180004336  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BICollectionSessionEx@123@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `Microsoft::DiagnosticsHub::StandardCollector::ICollectionSessionEx'}
0x18000433d  mov     [rdi+10h], rax
0x180004341  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BIDebuggerCollectionSession@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `IDebuggerCollectionSession'}
0x180004348  mov     [rdi+18h], rax
0x18000434c  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BIStandardCollectorVersion@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `IStandardCollectorVersion'}
0x180004353  mov     [rdi+20h], rax
0x180004357  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BISupportErrorInfo@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `ISupportErrorInfo'}
0x18000435e  mov     [rdi+28h], rax
0x180004362  lea     rax, ??_7CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@6BCModuleRefCount@@@; const Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::`vftable'{for `CModuleRefCount'}
0x180004369  mov     [rdi+30h], rax
0x18000436d  movups  xmm0, xmmword ptr [r8+10h]
0x180004372  movdqu  xmmword ptr [rdi+40h], xmm0
0x180004377  mov     eax, [r8+4]
0x18000437b  mov     [rdi+50h], eax
0x18000437e  movzx   eax, word ptr [r8+28h]
0x180004383  mov     [rdi+54h], ax
0x180004387  mov     eax, [r8+8]
0x18000438b  shr     eax, 1
0x18000438d  and     al, 1
0x18000438f  mov     [rdi+56h], al
0x180004392  mov     eax, [r8+8]
0x180004396  shr     eax, 5
0x180004399  and     al, 1
0x18000439b  mov     [rdi+57h], al
0x18000439e  mov     [rdi+58h], si
0x1800043a2  mov     [rdi+60h], rsi
0x1800043a6  lea     rcx, [rdi+68h]; lpCriticalSection
0x1800043aa  xorps   xmm0, xmm0
0x1800043ad  xor     eax, eax
0x1800043af  movups  xmmword ptr [rcx], xmm0
0x1800043b2  movups  xmmword ptr [rcx+10h], xmm0
0x1800043b6  mov     [rcx+20h], rax
0x1800043ba  call    cs:__imp_InitializeCriticalSection
0x1800043c0  nop
0x1800043c1  mov     [rdi+90h], rsi
0x1800043c8  mov     [rdi+98h], rsi
0x1800043cf  mov     [rdi+0A0h], rsi
0x1800043d6  lea     rcx, [rdi+0A8h]; lpCriticalSection
0x1800043dd  xorps   xmm0, xmm0
0x1800043e0  xor     eax, eax
0x1800043e2  movups  xmmword ptr [rcx], xmm0
0x1800043e5  movups  xmmword ptr [rcx+10h], xmm0
0x1800043e9  mov     [rcx+20h], rax
0x1800043ed  call    cs:__imp_InitializeCriticalSection
0x1800043f3  nop
0x1800043f4  mov     [rdi+0D0h], rsi
0x1800043fb  mov     [rdi+0D8h], rsi
0x180004402  lea     r14, [rdi+0E0h]
0x180004409  lea     rcx, psz; "Notify."
0x180004410  call    cs:__imp_SysAllocString
0x180004416  mov     [r14], rax
0x180004419  test    rax, rax
0x18000441c  jz      loc_180004890
0x180004422  lea     r13, [rdi+0E8h]
0x180004429  mov     rcx, r13; SRWLock
0x18000442c  call    cs:__imp_InitializeSRWLock
0x180004432  nop
0x180004433  mov     [rdi+0F0h], rbx
0x18000443a  test    rbx, rbx
0x18000443d  jz      short loc_180004450
0x18000443f  mov     rax, [rbx]
0x180004442  mov     rcx, rbx
0x180004445  mov     rax, [rax+8]
0x180004449  call    cs:__guard_dispatch_icall_fptr
0x18000444f  nop
0x180004450  mov     [rdi+0F8h], rsi
0x180004457  lea     rbx, [rdi+100h]
0x18000445e  xor     edx, edx; Val
0x180004460  lea     r8d, [rdx+18h]; Size
0x180004464  mov     rcx, rbx; void *
0x180004467  call    cs:__imp_memset
0x18000446d  mov     rcx, rbx; pvarg
0x180004470  call    cs:__imp_VariantInit
0x180004476  nop
0x180004477  lea     rcx, [rdi+118h]
0x18000447e  call    ??0?$HubTask@J$0A@@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HubTask<long,0>::HubTask<long,0>(void)
0x180004483  nop
0x180004484  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x180004489  mov     rcx, rax
0x18000448c  test    rax, rax
0x18000448f  jz      loc_18000489B
0x180004495  mov     rax, [rax]
0x180004498  mov     rax, [rax+18h]
0x18000449c  call    cs:__guard_dispatch_icall_fptr
0x1800044a2  add     rax, 18h
0x1800044a6  mov     [rdi+188h], rax
0x1800044ad  mov     [rdi+190h], esi
0x1800044b3  mov     dword ptr [rdi+194h], 1
0x1800044bd  mov     esi, 27h ; '''
0x1800044c2  mov     r8d, esi; cchMax
0x1800044c5  lea     rdx, [rsp+198h+sz]; lpsz
0x1800044ca  lea     rcx, [rdi+40h]; rguid
0x1800044ce  call    cs:__imp_StringFromGUID2
0x1800044d4  xor     r8d, r8d
0x1800044d7  test    eax, eax
0x1800044d9  jz      loc_1800048A6
0x1800044df  mov     [rsp+198h+String], r8w
0x1800044e8  mov     [rsp+198h+var_8C], r8w
0x1800044f1  mov     rdx, rsi
0x1800044f4  lea     rcx, [rsp+198h+String]
0x1800044fc  lea     rax, [rdx-3]
0x180004500  test    rax, rax
0x180004503  jz      short loc_180004530
0x180004505  movzx   eax, word ptr [rcx-4Ch]
0x180004509  test    ax, ax
0x18000450c  jz      short loc_18000451B
0x18000450e  mov     [rcx], ax
0x180004511  add     rcx, 2
0x180004515  sub     rdx, 1
0x180004519  jnz     short loc_1800044FC
0x18000451b  test    rdx, rdx
0x18000451e  jnz     short loc_180004530
0x180004520  mov     [rcx-2], r8w
0x180004525  mov     [rsp+198h+String], r8w
0x18000452e  jmp     short loc_180004534
0x180004530  mov     [rcx], r8w
0x180004534  lea     rcx, [rsp+198h+String]; String
0x18000453c  call    cs:__imp_wcslen
0x180004542  mov     r8d, eax; int
0x180004545  lea     rdx, [rsp+198h+String]; unsigned __int16 *
0x18000454d  mov     rcx, r14; this
0x180004550  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180004555  call    cs:__imp_GetCurrentProcess
0x18000455b  mov     rbx, rax
0x18000455e  call    cs:__imp_GetCurrentProcess
0x180004564  mov     [rsp+198h+dwOptions], 2; dwOptions
0x18000456c  mov     [rsp+198h+bInheritHandle], 0; bInheritHandle
0x180004574  mov     [rsp+198h+dwDesiredAccess], 0; dwDesiredAccess
0x18000457c  lea     r9, [rdi+60h]; lpTargetHandle
0x180004580  mov     r8, rbx; hTargetProcessHandle
0x180004583  mov     rdx, [rsp+198h+hSourceHandle]; hSourceHandle
0x18000458b  mov     rcx, rax; hSourceProcessHandle
0x18000458e  call    cs:__imp_DuplicateHandle
0x180004594  test    eax, eax
0x180004596  jz      loc_1800048C0
0x18000459c  mov     ecx, 20h ; ' '; Size
0x1800045a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045a6  mov     r14, rax
0x1800045a9  mov     dword ptr [rax+8], 1
0x1800045b0  mov     dword ptr [rax+0Ch], 1
0x1800045b7  lea     rax, ??_7?$_Ref_count_obj2@VAutoEvent@DiagHubCommon@@@std@@6B@; const std::_Ref_count_obj2<DiagHubCommon::AutoEvent>::`vftable'
0x1800045be  mov     [r14], rax
0x1800045c1  lea     rbx, [r14+10h]
0x1800045c5  mov     r9, [rdi+0E0h]; lpName
0x1800045cc  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800045d3  mov     dword ptr [rbx+8], 0
0x1800045da  xor     r8d, r8d; bInitialState
0x1800045dd  xor     edx, edx; bManualReset
0x1800045df  xor     ecx, ecx; lpEventAttributes
0x1800045e1  call    cs:__imp_CreateEventW
0x1800045e7  mov     [rbx], rax
0x1800045ea  test    rax, rax
0x1800045ed  jnz     short loc_18000460F
0x1800045ef  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800045f6  call    cs:__imp_GetLastError
0x1800045fc  movzx   ecx, ax
0x1800045ff  or      ecx, 80070000h
0x180004605  test    eax, eax
0x180004607  cmovle  ecx, eax
0x18000460a  mov     [rbx+8], ecx
0x18000460d  jmp     short loc_180004623
0x18000460f  call    cs:__imp_GetLastError
0x180004615  cmp     eax, 0B7h
0x18000461a  jnz     short loc_180004623
0x18000461c  mov     dword ptr [rbx+8], 1
0x180004623  mov     [rdi+0D0h], rbx
0x18000462a  mov     rbx, [rdi+0D8h]
0x180004631  mov     [rdi+0D8h], r14
0x180004638  xor     r14d, r14d
0x18000463b  test    rbx, rbx
0x18000463e  jz      short loc_180004679
0x180004640  or      eax, 0FFFFFFFFh
0x180004643  lock xadd [rbx+8], eax
0x180004648  cmp     eax, 1
0x18000464b  jnz     short loc_180004679
0x18000464d  mov     rax, [rbx]
0x180004650  mov     rcx, rbx
0x180004653  mov     rax, [rax]
0x180004656  call    cs:__guard_dispatch_icall_fptr
0x18000465c  or      eax, 0FFFFFFFFh
0x18000465f  lock xadd [rbx+0Ch], eax
0x180004664  cmp     eax, 1
0x180004667  jnz     short loc_180004679
0x180004669  mov     rax, [rbx]
0x18000466c  mov     rcx, rbx
0x18000466f  mov     rax, [rax+8]
0x180004673  call    cs:__guard_dispatch_icall_fptr
0x180004679  mov     rax, [rdi+60h]
0x18000467d  mov     [rsp+198h+hSourceHandle], rax
0x180004685  mov     rcx, [r15+38h]
0x180004689  test    rcx, rcx
0x18000468c  jnz     short loc_180004694
0x18000468e  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180004694  mov     rax, [rcx]
0x180004697  lea     rdx, [rsp+198h+hSourceHandle]
0x18000469f  mov     rax, [rax+10h]
0x1800046a3  call    cs:__guard_dispatch_icall_fptr
0x1800046a9  mov     rbx, rax
0x1800046ac  mov     rcx, [rdi+0F8h]
0x1800046b3  test    rcx, rcx
0x1800046b6  jz      short loc_1800046C5
0x1800046b8  mov     rax, [rcx]
0x1800046bb  mov     rax, [rax+10h]
0x1800046bf  call    cs:__guard_dispatch_icall_fptr
0x1800046c5  mov     [rdi+0F8h], rbx
0x1800046cc  lea     rdx, [rsp+198h+hSourceHandle]; unsigned __int16 **
0x1800046d4  mov     rcx, [r12]; this
0x1800046d8  call    ?GetDirectoryPath@SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJPEAPEBG@Z; Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::GetDirectoryPath(ushort const * *)
0x1800046dd  test    eax, eax
0x1800046df  js      loc_1800048EA
0x1800046e5  mov     r8d, esi; cchMax
0x1800046e8  lea     rdx, [rsp+198h+sz]; lpsz
0x1800046ed  lea     rcx, [rdi+40h]; rguid
0x1800046f1  call    cs:__imp_StringFromGUID2
0x1800046f7  test    eax, eax
0x1800046f9  jz      loc_180004900
0x1800046ff  mov     [rsp+198h+String], r14w
0x180004708  mov     [rsp+198h+var_8C], r14w
0x180004711  lea     rcx, [rsp+198h+String]
0x180004719  lea     rax, [rsi-3]
0x18000471d  test    rax, rax
0x180004720  jz      short loc_18000474D
0x180004722  movzx   eax, word ptr [rcx-4Ch]
0x180004726  test    ax, ax
0x180004729  jz      short loc_180004738
0x18000472b  mov     [rcx], ax
0x18000472e  add     rcx, 2
0x180004732  sub     rsi, 1
0x180004736  jnz     short loc_180004719
0x180004738  test    rsi, rsi
0x18000473b  jnz     short loc_18000474D
0x18000473d  mov     [rcx-2], r14w
0x180004742  mov     [rsp+198h+String], r14w
0x18000474b  jmp     short loc_180004751
0x18000474d  mov     [rcx], r14w
0x180004751  lea     r9, [rsp+198h+String]
0x180004759  mov     r8, [rsp+198h+hSourceHandle]
0x180004761  lea     rdx, aSSCounters; "%s%s.counters"
0x180004768  lea     rcx, [rdi+188h]
0x18000476f  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180004774  mov     [rsp+198h+bstrString], r14
0x180004779  lea     rdx, aSessionCreated; "Session created."
0x180004780  lea     rcx, [rsp+198h+bstrString]; this
0x180004785  call    ??0CComBSTR@ATL@@QEAA@PEBD@Z; ATL::CComBSTR::CComBSTR(char const *)
0x18000478a  nop
0x18000478b  mov     [rsp+198h+hSourceHandle], r13
0x180004793  mov     [rsp+198h+var_40], r14d
0x18000479b  mov     rcx, r13; SRWLock
0x18000479e  call    cs:__imp_AcquireSRWLockShared
0x1800047a4  nop
0x1800047a5  mov     rcx, [rdi+0F0h]
0x1800047ac  mov     rax, [rcx]
0x1800047af  mov     r8, [rsp+198h+bstrString]
0x1800047b4  lea     rdx, xmmword_180076FE0
0x1800047bb  mov     rax, [rax+18h]
0x1800047bf  call    cs:__guard_dispatch_icall_fptr
0x1800047c5  nop
0x1800047c6  mov     rcx, r13; SRWLock
0x1800047c9  call    cs:__imp_ReleaseSRWLockShared
0x1800047cf  cmp     [rdi+56h], r14b
0x1800047d3  jz      short loc_1800047F0
0x1800047d5  lea     r8, aCollectionWith; "Collection with debugger enabled"
0x1800047dc  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800047e3  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
  ... truncated ...
```
