# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::AddTargetProcessEx(ulong,TargetProcessFlags,CollectionStartReason,ushort const *)

- ea: `0x18001c978`
- end: `0x18001d17e`
- name: `?AddTargetProcessEx@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJKW4TargetProcessFlags@@W4CollectionStartReason@@PEBG@Z`
- size: `2054`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, unsigned int, OLECHAR *)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180013908`
- `0x18001dd80`

## callees

- `0x180008914`
- `0x180009fa4`
- `0x18000a078`
- `0x18000a17c`
- `0x18000f1b0`
- `0x180018004`
- `0x180019c10`
- `0x18001c7a0`
- `0x18001c978`
- `0x18002259c`
- `0x180022ae4`
- `0x18003d864`
- `0x180040d8c`
- `0x180041834`
- `0x180041938`
- `0x180041a18`
- `0x180049b04`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memset` at `0x18001d000`
- `VCRUNTIME140!memset` at `0x18001d000`
- `VCRUNTIME140!memcmp` at `0x18001ccc3`
- `VCRUNTIME140!memcmp` at `0x18001ccc3`
- `KERNEL32!WaitForSingleObject` at `0x18001cea0`
- `KERNEL32!WaitForSingleObject` at `0x18001cea0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cad2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cae9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cba8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cbc2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cdd5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001ce64`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cad2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cae9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cba8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cbc2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cdd5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001ce64`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001ca84`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001cb49`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001cc08`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001ca84`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001cb49`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001cc08`
- `KERNEL32!LeaveCriticalSection` at `0x18001cadc`
- `KERNEL32!LeaveCriticalSection` at `0x18001caf3`
- `KERNEL32!LeaveCriticalSection` at `0x18001cbb2`
- `KERNEL32!LeaveCriticalSection` at `0x18001cbcc`
- `KERNEL32!LeaveCriticalSection` at `0x18001cddf`
- `KERNEL32!LeaveCriticalSection` at `0x18001ce6e`
- `KERNEL32!LeaveCriticalSection` at `0x18001cadc`
- `KERNEL32!LeaveCriticalSection` at `0x18001caf3`
- `KERNEL32!LeaveCriticalSection` at `0x18001cbb2`
- `KERNEL32!LeaveCriticalSection` at `0x18001cbcc`
- `KERNEL32!LeaveCriticalSection` at `0x18001cddf`
- `KERNEL32!LeaveCriticalSection` at `0x18001ce6e`
- `KERNEL32!EnterCriticalSection` at `0x18001ca6c`
- `KERNEL32!EnterCriticalSection` at `0x18001cb2d`
- `KERNEL32!EnterCriticalSection` at `0x18001cbea`
- `KERNEL32!EnterCriticalSection` at `0x18001ca6c`
- `KERNEL32!EnterCriticalSection` at `0x18001cb2d`
- `KERNEL32!EnterCriticalSection` at `0x18001cbea`
- `ole32!CoTaskMemAlloc` at `0x18001cfc4`
- `ole32!CoTaskMemAlloc` at `0x18001cfc4`
- `OLEAUT32!__imp_SysAllocString` at `0x18001cfeb`
- `OLEAUT32!__imp_SysAllocString` at `0x18001cfeb`
- `OLEAUT32!__imp_VariantInit` at `0x18001d00b`
- `OLEAUT32!__imp_VariantInit` at `0x18001d00b`
- `OLEAUT32!__imp_VariantClear` at `0x18001d082`
- `OLEAUT32!__imp_VariantClear` at `0x18001d0ed`
- `OLEAUT32!__imp_VariantClear` at `0x18001d082`
- `OLEAUT32!__imp_VariantClear` at `0x18001d0ed`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18001cf5d`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18001cf5d`
- `OLEAUT32!__imp_GetRecordInfoFromTypeInfo` at `0x18001cfaf`
- `OLEAUT32!__imp_GetRecordInfoFromTypeInfo` at `0x18001cfaf`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18001cf1b`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18001cf1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::AddTargetProcessEx(
        __int64 a1,
        unsigned int a2,
        int a3,
        unsigned int a4,
        OLECHAR *a5)
{
  char v5; // di
  const unsigned __int16 *v9; // r8
  const struct _GUID *v10; // rdx
  HRESULT ModulePath; // ebx
  bool v12; // r12
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  int v14; // esi
  RTL_SRWLOCK *v15; // rcx
  bool v16; // r13
  const unsigned __int16 *v17; // r8
  const struct _GUID *v18; // rdx
  unsigned int v19; // edi
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  ITypeLib *v23; // r12
  struct ITypeLibVtbl *lpVtbl; // rbx
  HRESULT (__stdcall *GetTypeInfoType)(ITypeLib *, UINT, TYPEKIND *); // rax
  HRESULT (__stdcall *GetTypeInfo)(ITypeLib *, UINT, ITypeInfo **); // r13
  HRESULT (__stdcall *v27)(ITypeLib *, UINT, TYPEKIND *); // rsi
  __int64 v28; // rcx
  unsigned int v29; // eax
  const unsigned __int16 *v30; // r8
  const wchar_t *v31; // rdx
  int v32; // r12d
  size_t v33; // rax
  const OLECHAR *v34; // rcx
  _DWORD *v35; // rax
  LONGLONG v36; // rbx
  IRecordInfo *v37; // rax
  int v38; // [rsp+30h] [rbp-D0h]
  bool v39; // [rsp+40h] [rbp-C0h]
  OLECHAR *psz[2]; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-A8h] BYREF
  ITypeLib *pptlib; // [rsp+70h] [rbp-90h] BYREF
  ITypeInfo *pTypeInfo; // [rsp+78h] [rbp-88h] BYREF
  IRecordInfo *ppRecInfo; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID *v46[2]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *String[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-58h]
  LPCOLESTR szFile[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v50; // [rsp+C0h] [rbp-40h]
  __int128 v51; // [rsp+D0h] [rbp-30h]
  __int64 v52; // [rsp+E0h] [rbp-20h]
  __int128 Buf1; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v54; // [rsp+100h] [rbp+0h]
  __int128 v55; // [rsp+110h] [rbp+10h]
  __int64 v56; // [rsp+120h] [rbp+20h]

  v5 = a3;
  LODWORD(pTypeInfo) = a3;
  psz[0] = a5;
  if ( *(_BYTE *)(a1 + 3576) )
    return 3775987731LL;
  if ( a2 < 4 )
    return 2147942487LL;
  _mm_lfence();
  if ( (a2 & 1) != 0 )
    return 2147942487LL;
  if ( !*(_BYTE *)(a1 + 864) )
  {
    *(_OWORD *)v46 = 0;
    DiagHubCommon::HResultFormatter::HResultFormatter(
      (DiagHubCommon::HResultFormatter *)v46,
      -518979564,
      *(_WORD *)(a1 + 696));
    v10 = (const struct _GUID *)L"<unknown error>";
    if ( v46[0] )
      v10 = v46[0];
    DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v10, v9);
    ModulePath = (HRESULT)v46[1];
    DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)v46);
    return (unsigned int)ModulePath;
  }
  v12 = (a3 & 4) != 0;
  if ( (a3 & 4) != 0 )
  {
    v13 = (struct _RTL_CRITICAL_SECTION *)(a1 + 3496);
    pptlib = (ITypeLib *)(a1 + 3496);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 3496));
    String[0] = (wchar_t *)(a1 + 2848);
    LODWORD(String[1]) = 1;
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 2848));
    v51 = 0;
    v52 = 0;
    *(GUID *)szFile = SystemTraceControlGuid;
    *(_QWORD *)&v50 = 1;
    LOBYTE(v51) = 5;
    *((_QWORD *)&v50 + 1) = 1;
    v14 = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::AddProvidersWithFilters_Unsafe(
            (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)a1,
            1u,
            (struct EtwProviderConfigWithFilter *)szFile);
    _mm_lfence();
    v15 = (RTL_SRWLOCK *)(a1 + 2848);
    if ( v14 < 0 )
    {
      ReleaseSRWLockExclusive(v15);
      LeaveCriticalSection(v13);
      return (unsigned int)v14;
    }
    ReleaseSRWLockExclusive(v15);
    LeaveCriticalSection(v13);
    v5 = (char)pTypeInfo;
  }
  v16 = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::AddTargetProcessToFilter(
          (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter *)(a1 + 1048),
          a2,
          v12);
  v39 = v16;
  if ( v16 )
  {
    pptlib = (ITypeLib *)(a1 + 3496);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 3496));
    String[0] = (wchar_t *)(a1 + 2848);
    LODWORD(String[1]) = 1;
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 2848));
    if ( (unsigned int)Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::UpdateSessionsWithProcessFilter_Unsafe((Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)a1) )
    {
      *(_OWORD *)v46 = 0;
      DiagHubCommon::HResultFormatter::HResultFormatter(
        (DiagHubCommon::HResultFormatter *)v46,
        -518979500,
        *(_WORD *)(a1 + 696));
      v18 = (const struct _GUID *)L"<unknown error>";
      if ( v46[0] )
        v18 = v46[0];
      DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, v18, v17);
      v19 = (unsigned int)v46[1];
      DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)v46);
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 2848));
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 3496));
      return v19;
    }
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 2848));
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 3496));
  }
  if ( (v5 & 3) == 0 )
  {
LABEL_49:
    if ( v16 )
    {
      *(_OWORD *)String = 0;
      v48 = 0;
      ModulePath = DiagHubCommon::ModulePath::GetModulePath((HMODULE)0x180000000LL);
      if ( ModulePath < 0 )
      {
LABEL_68:
        std::vector<unsigned short>::~vector<unsigned short>(String);
        return (unsigned int)ModulePath;
      }
      *(_OWORD *)szFile = 0;
      v50 = 0;
      v33 = wcslen(String[0]);
      std::wstring::_Construct<1,unsigned short const *>(szFile, String[0], v33);
      std::wstring::append(szFile, L"\\1");
      pptlib = 0;
      v34 = (const OLECHAR *)szFile;
      if ( *((_QWORD *)&v50 + 1) > 7u )
        v34 = szFile[0];
      ModulePath = LoadTypeLib(v34, &pptlib);
      if ( ModulePath < 0 )
      {
LABEL_65:
        if ( pptlib )
          ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
        std::wstring::~wstring(szFile);
        goto LABEL_68;
      }
      pTypeInfo = 0;
      ModulePath = ((__int64 (__fastcall *)(ITypeLib *, GUID *, ITypeInfo **))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                     pptlib,
                     &GUID_b4936d6a_893b_4cdc_b4ff_5282c0eae45b,
                     &pTypeInfo);
      if ( ModulePath < 0 )
      {
LABEL_63:
        if ( pTypeInfo )
          ((void (__fastcall *)(ITypeInfo *))pTypeInfo->lpVtbl->Release)(pTypeInfo);
        goto LABEL_65;
      }
      ppRecInfo = 0;
      ModulePath = GetRecordInfoFromTypeInfo(pTypeInfo, &ppRecInfo);
      if ( ModulePath < 0 )
      {
LABEL_61:
        if ( ppRecInfo )
          ((void (__fastcall *)(IRecordInfo *))ppRecInfo->lpVtbl->Release)(ppRecInfo);
        goto LABEL_63;
      }
      v35 = CoTaskMemAlloc(0x10u);
      v36 = (LONGLONG)v35;
      if ( !v35 )
      {
        ModulePath = -2147024882;
        goto LABEL_61;
      }
      *v35 = a2;
      v35[1] = a4;
      *((_QWORD *)v35 + 1) = SysAllocString(psz[0]);
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      pvarg.vt = 36;
      pvarg.llVal = v36;
      v37 = ppRecInfo;
      ppRecInfo = 0;
      pvarg.pRecInfo = v37;
      ModulePath = Microsoft::DiagnosticsHub::StandardCollector::AgentController::CommunicateWithAgents(
                     a1 + 24,
                     5,
                     &pvarg);
      if ( ModulePath < 0
        || (_mm_lfence(),
            v46[0] = (struct _GUID *)&Microsoft::DiagnosticsHub::StandardCollector::TargetProfilingStartEvent::`vftable',
            v46[1] = (struct _GUID *)__PAIR64__(a4, a2),
            ModulePath = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::InjectArtificialEvent(
                           (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)a1,
                           (const struct Microsoft::DiagnosticsHub::StandardCollector::ArtificialEvent *)v46),
            ModulePath < 0) )
      {
        VariantClear(&pvarg);
        goto LABEL_61;
      }
      VariantClear(&pvarg);
      if ( ppRecInfo )
        ((void (__fastcall *)(IRecordInfo *))ppRecInfo->lpVtbl->Release)(ppRecInfo);
      if ( pTypeInfo )
        ((void (__fastcall *)(ITypeInfo *))pTypeInfo->lpVtbl->Release)(pTypeInfo);
      if ( pptlib )
        ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      std::wstring::~wstring(szFile);
      std::vector<unsigned short>::~vector<unsigned short>(String);
    }
    return 0;
  }
  v46[0] = (struct _GUID *)(a1 + 3496);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 3496));
  *(_QWORD *)&pvarg.vt = a1 + 2848;
  pvarg.lVal = 1;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 2848));
  v23 = *(ITypeLib **)(a1 + 2792);
  pptlib = v23;
  lpVtbl = v23->lpVtbl;
  if ( (ITypeLib *)v23->lpVtbl == v23 )
  {
LABEL_44:
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 2848));
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 3496));
    if ( ((unsigned __int8)pTypeInfo & 2) == 0 )
    {
      CodeMarker(25239);
      if ( *(int *)(a1 + 2776) < 0 || WaitForSingleObject(*(HANDLE *)(a1 + 2768), 0x7530u) )
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 56),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
          L"Rundown timeout exceeded");
      CodeMarker(25240);
    }
    goto LABEL_49;
  }
  while ( 1 )
  {
    *(_OWORD *)String = 0;
    GetTypeInfoType = lpVtbl->GetTypeInfoType;
    if ( GetTypeInfoType )
      _InterlockedIncrement((volatile signed __int32 *)GetTypeInfoType + 2);
    GetTypeInfo = lpVtbl->GetTypeInfo;
    String[0] = (wchar_t *)GetTypeInfo;
    v27 = lpVtbl->GetTypeInfoType;
    String[1] = (wchar_t *)v27;
    if ( !*((_QWORD *)GetTypeInfo + 3) )
      goto LABEL_38;
    Buf1 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    LOBYTE(v38) = *((_BYTE *)GetTypeInfo + 40);
    if ( !(unsigned __int8)Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController::RequiresRundown(
                             a1 + 2752,
                             a2,
                             GetTypeInfo,
                             *((_BYTE *)GetTypeInfo + 16) != 0 ? 3 : 0,
                             *((_DWORD *)GetTypeInfo + 5),
                             *((_QWORD *)GetTypeInfo + 3),
                             v38,
                             &Buf1) )
      goto LABEL_38;
    if ( !memcmp(&Buf1, &SystemTraceControlGuid, 0x10u) )
      break;
    v32 = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::AddProvidersWithFilters_Unsafe(
            (Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *)a1,
            1u,
            (struct EtwProviderConfigWithFilter *)&Buf1);
    if ( v32 < 0 )
      goto LABEL_31;
    v23 = pptlib;
LABEL_38:
    if ( v27 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(HRESULT (__stdcall *)(ITypeLib *, UINT, TYPEKIND *), __int64, __int64, __int64))v27)(
          v27,
          v20,
          v21,
          v22);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(HRESULT (__stdcall *)(ITypeLib *, UINT, TYPEKIND *)))(*(_QWORD *)v27 + 8LL))(v27);
      }
    }
    lpVtbl = (struct ITypeLibVtbl *)lpVtbl->QueryInterface;
    if ( lpVtbl == (struct ITypeLibVtbl *)v23 )
    {
      v16 = v39;
      goto LABEL_44;
    }
  }
  v28 = *(_QWORD *)(a1 + 2856);
  LODWORD(ppRecInfo) = *((_DWORD *)GetTypeInfo + 5);
  *((_DWORD *)GetTypeInfo + 5) = v54 | (unsigned int)ppRecInfo;
  *(_OWORD *)szFile = 0;
  LODWORD(szFile[0]) = DWORD2(v54);
  v50 = 0;
  v29 = (*(__int64 (__fastcall **)(__int64, LPCOLESTR *))(*(_QWORD *)v28 + 40LL))(v28, szFile);
  v22 = v29;
  if ( !v29 )
    goto LABEL_38;
  *((_DWORD *)GetTypeInfo + 5) = (_DWORD)ppRecInfo;
  DiagHubCommon::LogStream::Write(
    (DiagHubCommon::LogStream *)((char *)_logger + 112),
    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
    L"Failed to enable system trace rundown: %#08x",
    v29);
  *(_OWORD *)psz = 0;
  DiagHubCommon::HResultFormatter::HResultFormatter(
    (DiagHubCommon::HResultFormatter *)psz,
    -518979521,
    *(_WORD *)(a1 + 696));
  v31 = L"<unknown error>";
  if ( psz[0] )
    v31 = psz[0];
  DiagHubCommon::SetErrorInfo((DiagHubCommon *)&IID_ICollectionSession, (const struct _GUID *)v31, v30);
  v32 = (int)psz[1];
  DiagHubCommon::HResultFormatter::~HResultFormatter((DiagHubCommon::HResultFormatter *)psz);
LABEL_31:
  if ( v27 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(HRESULT (__stdcall *)(ITypeLib *, UINT, TYPEKIND *)))v27)(v27);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(HRESULT (__stdcall *)(ITypeLib *, UINT, TYPEKIND *)))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 2848));
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 3496));
  return (unsigned int)v32;
}

```

## disassembly

```asm
0x18001c978  mov     [rsp-8+arg_10], rbx
0x18001c97d  push    rbp
0x18001c97e  push    rsi
0x18001c97f  push    rdi
0x18001c980  push    r12
0x18001c982  push    r13
0x18001c984  push    r14
0x18001c986  push    r15
0x18001c988  lea     rbp, [rsp-40h]
0x18001c98d  sub     rsp, 140h
0x18001c994  mov     rax, cs:__security_cookie
0x18001c99b  xor     rax, rsp
0x18001c99e  mov     [rbp+70h+var_40], rax
0x18001c9a2  mov     [rsp+170h+var_12C], r9d
0x18001c9a7  mov     edi, r8d
0x18001c9aa  mov     dword ptr [rsp+170h+pTypeInfo], r8d
0x18001c9af  mov     r15d, edx
0x18001c9b2  mov     r14, rcx
0x18001c9b5  mov     rax, [rbp+70h+arg_20]
0x18001c9bc  mov     [rsp+170h+psz], rax
0x18001c9c1  mov     al, [rcx+0DF8h]
0x18001c9c7  test    al, al
0x18001c9c9  jz      short loc_18001C9D5
0x18001c9cb  mov     eax, 0E1110013h
0x18001c9d0  jmp     loc_18001D157
0x18001c9d5  cmp     r15d, 4
0x18001c9d9  jb      loc_18001D152
0x18001c9df  lfence
0x18001c9e2  mov     esi, 1
0x18001c9e7  test    sil, r15b
0x18001c9ea  jnz     loc_18001D152
0x18001c9f0  mov     al, [rcx+360h]
0x18001c9f6  test    al, al
0x18001c9f8  jnz     short loc_18001CA49
0x18001c9fa  xorps   xmm0, xmm0
0x18001c9fd  movups  xmmword ptr [rbp+70h+var_E8], xmm0
0x18001ca01  movzx   r8d, word ptr [rcx+2B8h]; unsigned __int16
0x18001ca09  mov     edx, 0E1110014h; int
0x18001ca0e  lea     rcx, [rbp+70h+var_E8]; this
0x18001ca12  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort)
0x18001ca17  nop
0x18001ca18  lea     rdx, aUnknownError; "<unknown error>"
0x18001ca1f  mov     rax, [rbp+70h+var_E8]
0x18001ca23  test    rax, rax
0x18001ca26  cmovnz  rdx, rax; struct _GUID *
0x18001ca2a  lea     rcx, IID_ICollectionSession; this
0x18001ca31  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x18001ca36  mov     ebx, dword ptr [rbp+70h+var_E8+8]
0x18001ca39  lea     rcx, [rbp+70h+var_E8]; this
0x18001ca3d  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x18001ca42  mov     eax, ebx
0x18001ca44  jmp     loc_18001D157
0x18001ca49  bt      r8d, 2
0x18001ca4e  setb    r12b
0x18001ca52  bt      r8d, 2
0x18001ca57  jnb     loc_18001CAFD
0x18001ca5d  lea     rbx, [rcx+0DA8h]
0x18001ca64  mov     [rsp+170h+pptlib], rbx
0x18001ca69  mov     rcx, rbx; lpCriticalSection
0x18001ca6c  call    cs:__imp_EnterCriticalSection
0x18001ca72  nop
0x18001ca73  lea     rdi, [r14+0B20h]
0x18001ca7a  mov     [rbp+70h+String], rdi
0x18001ca7e  mov     dword ptr [rbp+70h+String+8], esi
0x18001ca81  mov     rcx, rdi; SRWLock
0x18001ca84  call    cs:__imp_AcquireSRWLockExclusive
0x18001ca8a  nop
0x18001ca8b  xorps   xmm0, xmm0
0x18001ca8e  xor     eax, eax
0x18001ca90  movups  [rbp+70h+var_B0], xmm0
0x18001ca94  movups  [rbp+70h+var_A0], xmm0
0x18001ca98  mov     [rbp+70h+var_90], rax
0x18001ca9c  movups  xmm0, xmmword ptr cs:SystemTraceControlGuid.Data1
0x18001caa3  movdqu  xmmword ptr [rbp+70h+szFile], xmm0
0x18001caa8  mov     qword ptr [rbp+70h+var_B0], 1
0x18001cab0  mov     byte ptr [rbp+70h+var_A0], 5
0x18001cab4  mov     qword ptr [rbp+70h+var_B0+8], rsi
0x18001cab8  lea     r8, [rbp+70h+szFile]; struct EtwProviderConfigWithFilter *
0x18001cabc  mov     edx, esi; unsigned int
0x18001cabe  mov     rcx, r14; this
0x18001cac1  call    ?AddProvidersWithFilters_Unsafe@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJKPEAUEtwProviderConfigWithFilter@@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::AddProvidersWithFilters_Unsafe(ulong,EtwProviderConfigWithFilter *)
0x18001cac6  mov     esi, eax
0x18001cac8  lfence
0x18001cacb  mov     rcx, rdi; SRWLock
0x18001cace  test    eax, eax
0x18001cad0  jns     short loc_18001CAE9
0x18001cad2  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cad8  nop
0x18001cad9  mov     rcx, rbx; lpCriticalSection
0x18001cadc  call    cs:__imp_LeaveCriticalSection
0x18001cae2  mov     eax, esi
0x18001cae4  jmp     loc_18001D157
0x18001cae9  call    cs:__imp_ReleaseSRWLockExclusive
0x18001caef  nop
0x18001caf0  mov     rcx, rbx; lpCriticalSection
0x18001caf3  call    cs:__imp_LeaveCriticalSection
0x18001caf9  mov     edi, dword ptr [rsp+170h+pTypeInfo]
0x18001cafd  lea     rcx, [r14+418h]; this
0x18001cb04  mov     r8b, r12b; bool
0x18001cb07  mov     edx, r15d; unsigned int
0x18001cb0a  call    ?AddTargetProcessToFilter@EtwCollectionProcessFilter@StandardCollector@DiagnosticsHub@Microsoft@@IEAA_NI_N@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionProcessFilter::AddTargetProcessToFilter(uint,bool)
0x18001cb0f  mov     r13b, al
0x18001cb12  mov     [rsp+170h+var_130], al
0x18001cb16  test    al, al
0x18001cb18  jz      loc_18001CBD2
0x18001cb1e  lea     rbx, [r14+0DA8h]
0x18001cb25  mov     [rsp+170h+pptlib], rbx
0x18001cb2a  mov     rcx, rbx; lpCriticalSection
0x18001cb2d  call    cs:__imp_EnterCriticalSection
0x18001cb33  nop
0x18001cb34  lea     rsi, [r14+0B20h]
0x18001cb3b  mov     [rbp+70h+String], rsi
0x18001cb3f  mov     dword ptr [rbp+70h+String+8], 1
0x18001cb46  mov     rcx, rsi; SRWLock
0x18001cb49  call    cs:__imp_AcquireSRWLockExclusive
0x18001cb4f  nop
0x18001cb50  mov     rcx, r14; this
0x18001cb53  call    ?UpdateSessionsWithProcessFilter_Unsafe@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJXZ; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::UpdateSessionsWithProcessFilter_Unsafe(void)
0x18001cb58  test    eax, eax
0x18001cb5a  jz      short loc_18001CBBF
0x18001cb5c  xorps   xmm0, xmm0
0x18001cb5f  movups  xmmword ptr [rbp+70h+var_E8], xmm0
0x18001cb63  movzx   r8d, word ptr [r14+2B8h]; unsigned __int16
0x18001cb6b  mov     edx, 0E1110054h; int
0x18001cb70  lea     rcx, [rbp+70h+var_E8]; this
0x18001cb74  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort)
0x18001cb79  nop
0x18001cb7a  lea     rdx, aUnknownError; "<unknown error>"
0x18001cb81  mov     rax, [rbp+70h+var_E8]
0x18001cb85  test    rax, rax
0x18001cb88  cmovnz  rdx, rax; struct _GUID *
0x18001cb8c  lea     rcx, IID_ICollectionSession; this
0x18001cb93  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x18001cb98  mov     edi, dword ptr [rbp+70h+var_E8+8]
0x18001cb9b  lea     rcx, [rbp+70h+var_E8]; this
0x18001cb9f  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x18001cba4  nop
0x18001cba5  mov     rcx, rsi; SRWLock
0x18001cba8  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cbae  nop
0x18001cbaf  mov     rcx, rbx; lpCriticalSection
0x18001cbb2  call    cs:__imp_LeaveCriticalSection
0x18001cbb8  mov     eax, edi
0x18001cbba  jmp     loc_18001D157
0x18001cbbf  mov     rcx, rsi; SRWLock
0x18001cbc2  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cbc8  nop
0x18001cbc9  mov     rcx, rbx; lpCriticalSection
0x18001cbcc  call    cs:__imp_LeaveCriticalSection
0x18001cbd2  test    dil, 3
0x18001cbd6  jz      loc_18001CED4
0x18001cbdc  lea     rdi, [r14+0DA8h]
0x18001cbe3  mov     [rbp+70h+var_E8], rdi
0x18001cbe7  mov     rcx, rdi; lpCriticalSection
0x18001cbea  call    cs:__imp_EnterCriticalSection
0x18001cbf0  nop
0x18001cbf1  lea     rax, [r14+0B20h]
0x18001cbf8  mov     qword ptr [rsp+170h+pvarg], rax
0x18001cbfd  mov     dword ptr [rsp+170h+pvarg+8], 1
0x18001cc05  mov     rcx, rax; SRWLock
0x18001cc08  call    cs:__imp_AcquireSRWLockExclusive
0x18001cc0e  nop
0x18001cc0f  mov     r12, [r14+0AE8h]
0x18001cc16  mov     [rsp+170h+pptlib], r12
0x18001cc1b  mov     rbx, [r12]
0x18001cc1f  cmp     rbx, r12
0x18001cc22  jz      loc_18001CE5D
0x18001cc28  xorps   xmm0, xmm0
0x18001cc2b  movups  xmmword ptr [rbp+70h+String], xmm0
0x18001cc2f  mov     rax, [rbx+28h]
0x18001cc33  test    rax, rax
0x18001cc36  jz      short loc_18001CC3C
0x18001cc38  lock inc dword ptr [rax+8]
0x18001cc3c  mov     r13, [rbx+20h]
0x18001cc40  mov     [rbp+70h+String], r13
0x18001cc44  mov     rsi, [rbx+28h]
0x18001cc48  mov     [rbp+70h+String+8], rsi
0x18001cc4c  cmp     qword ptr [r13+18h], 0
0x18001cc51  jz      loc_18001CE0A
0x18001cc57  xor     eax, eax
0x18001cc59  movups  [rbp+70h+Buf1], xmm0
0x18001cc5d  movups  [rbp+70h+var_70], xmm0
0x18001cc61  movups  [rbp+70h+var_60], xmm0
0x18001cc65  mov     [rbp+70h+var_50], rax
0x18001cc69  mov     al, [r13+10h]
0x18001cc6d  neg     al
0x18001cc6f  sbb     r9d, r9d
0x18001cc72  and     r9d, 3
0x18001cc76  lea     rcx, [r14+0AC0h]
0x18001cc7d  lea     rax, [rbp+70h+Buf1]
0x18001cc81  mov     [rsp+170h+var_138], rax
0x18001cc86  mov     al, [r13+28h]
0x18001cc8a  mov     [rsp+170h+var_140], al
0x18001cc8e  mov     rax, [r13+18h]
0x18001cc92  mov     [rsp+170h+var_148], rax
0x18001cc97  mov     eax, [r13+14h]
0x18001cc9b  mov     dword ptr [rsp+170h+var_150], eax
0x18001cc9f  mov     r8, r13
0x18001cca2  mov     edx, r15d
0x18001cca5  call    ?RequiresRundown@EtwCollectionRundownController@StandardCollector@DiagnosticsHub@Microsoft@@IEAA_NIAEBU_GUID@@W4EtwConfigurationType@@W4EtwEventRoutingFlagsInternal@234@_KEAEAUEtwProviderConfig@@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController::RequiresRundown(uint,_GUID const &,EtwConfigurationType,Microsoft::DiagnosticsHub::StandardCollector::EtwEventRoutingFlagsInternal,unsigned __int64,uchar,EtwProviderConfig &)
0x18001ccaa  test    al, al
0x18001ccac  jz      loc_18001CE0A
0x18001ccb2  mov     r8d, 10h; Size
0x18001ccb8  lea     rdx, SystemTraceControlGuid; Buf2
0x18001ccbf  lea     rcx, [rbp+70h+Buf1]; Buf1
0x18001ccc3  call    cs:__imp_memcmp
0x18001ccc9  test    eax, eax
0x18001cccb  jnz     loc_18001CDED
0x18001ccd1  mov     rcx, [r14+0B28h]
0x18001ccd8  mov     eax, [r13+14h]
0x18001ccdc  mov     dword ptr [rbp+70h+ppRecInfo], eax
0x18001ccdf  or      eax, dword ptr [rbp+70h+var_70]
0x18001cce2  mov     [r13+14h], eax
0x18001cce6  xorps   xmm1, xmm1
0x18001cce9  movups  xmmword ptr [rbp+70h+szFile], xmm1
0x18001cced  mov     eax, dword ptr [rbp+70h+var_70+8]
0x18001ccf0  mov     dword ptr [rbp+70h+szFile], eax
0x18001ccf3  movups  xmm0, xmmword ptr [rbp+70h+szFile]
0x18001ccf7  movaps  xmmword ptr [rbp+70h+szFile], xmm0
0x18001ccfb  movaps  [rbp+70h+var_B0], xmm1
0x18001ccff  mov     rax, [rcx]
0x18001cd02  lea     rdx, [rbp+70h+szFile]
0x18001cd06  mov     rax, [rax+28h]
0x18001cd0a  call    cs:__guard_dispatch_icall_fptr
0x18001cd10  mov     r9d, eax
0x18001cd13  test    eax, eax
0x18001cd15  jz      loc_18001CE0A
0x18001cd1b  mov     eax, dword ptr [rbp+70h+ppRecInfo]
0x18001cd1e  mov     [r13+14h], eax
0x18001cd22  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001cd29  add     rcx, 70h ; 'p'; this
0x18001cd2d  lea     r8, aFailedToEnable_1; "Failed to enable system trace rundown: "...
0x18001cd34  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001cd3b  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001cd40  xorps   xmm0, xmm0
0x18001cd43  movups  xmmword ptr [rsp+170h+psz], xmm0
0x18001cd48  movzx   r8d, word ptr [r14+2B8h]; unsigned __int16
0x18001cd50  mov     edx, 0E111003Fh; int
0x18001cd55  lea     rcx, [rsp+170h+psz]; this
0x18001cd5a  call    ??0HResultFormatter@DiagHubCommon@@QEAA@JG@Z; DiagHubCommon::HResultFormatter::HResultFormatter(long,ushort)
0x18001cd5f  nop
0x18001cd60  lea     rdx, aUnknownError; "<unknown error>"
0x18001cd67  mov     rax, [rsp+170h+psz]
0x18001cd6c  test    rax, rax
0x18001cd6f  cmovnz  rdx, rax; struct _GUID *
0x18001cd73  lea     rcx, IID_ICollectionSession; this
0x18001cd7a  call    ?SetErrorInfo@DiagHubCommon@@YAXAEBU_GUID@@PEBG@Z; DiagHubCommon::SetErrorInfo(_GUID const &,ushort const *)
0x18001cd7f  mov     r12d, dword ptr [rsp+170h+psz+8]
0x18001cd84  lea     rcx, [rsp+170h+psz]; this
0x18001cd89  call    ??1HResultFormatter@DiagHubCommon@@QEAA@XZ; DiagHubCommon::HResultFormatter::~HResultFormatter(void)
0x18001cd8e  nop
0x18001cd8f  test    rsi, rsi
0x18001cd92  jz      short loc_18001CDCE
0x18001cd94  or      eax, 0FFFFFFFFh
0x18001cd97  lock xadd [rsi+8], eax
0x18001cd9c  cmp     eax, 1
0x18001cd9f  jnz     short loc_18001CDCE
0x18001cda1  mov     rax, [rsi]
0x18001cda4  mov     rcx, rsi
0x18001cda7  mov     rax, [rax]
0x18001cdaa  call    cs:__guard_dispatch_icall_fptr
0x18001cdb0  or      eax, 0FFFFFFFFh
0x18001cdb3  lock xadd [rsi+0Ch], eax
0x18001cdb8  cmp     eax, 1
0x18001cdbb  jnz     short loc_18001CDCE
0x18001cdbd  mov     rcx, [rsi]
0x18001cdc0  mov     rax, [rcx+8]
0x18001cdc4  mov     rcx, rsi
0x18001cdc7  call    cs:__guard_dispatch_icall_fptr
0x18001cdcd  nop
0x18001cdce  lea     rcx, [r14+0B20h]; SRWLock
0x18001cdd5  call    cs:__imp_ReleaseSRWLockExclusive
0x18001cddb  nop
0x18001cddc  mov     rcx, rdi; lpCriticalSection
0x18001cddf  call    cs:__imp_LeaveCriticalSection
0x18001cde5  mov     eax, r12d
0x18001cde8  jmp     loc_18001D157
0x18001cded  lea     r8, [rbp+70h+Buf1]; struct EtwProviderConfigWithFilter *
0x18001cdf1  mov     edx, 1; unsigned int
0x18001cdf6  mov     rcx, r14; this
0x18001cdf9  call    ?AddProvidersWithFilters_Unsafe@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJKPEAUEtwProviderConfigWithFilter@@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::AddProvidersWithFilters_Unsafe(ulong,EtwProviderConfigWithFilter *)
0x18001cdfe  mov     r12d, eax
0x18001ce01  test    eax, eax
0x18001ce03  js      short loc_18001CD8F
0x18001ce05  mov     r12, [rsp+170h+pptlib]
0x18001ce0a  test    rsi, rsi
0x18001ce0d  jz      short loc_18001CE4C
0x18001ce0f  or      r13d, 0FFFFFFFFh
0x18001ce13  mov     eax, r13d
0x18001ce16  lock xadd [rsi+8], eax
0x18001ce1b  add     eax, r13d
0x18001ce1e  jnz     short loc_18001CE4C
0x18001ce20  mov     rax, [rsi]
0x18001ce23  mov     rcx, rsi
0x18001ce26  mov     rax, [rax]
0x18001ce29  call    cs:__guard_dispatch_icall_fptr
0x18001ce2f  mov     eax, r13d
0x18001ce32  lock xadd [rsi+0Ch], eax
0x18001ce37  add     eax, r13d
0x18001ce3a  jnz     short loc_18001CE4C
  ... truncated ...
```
