# CLockScreen::GetImageStream(Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x180009320`
- end: `0x1800099e0`
- name: `?GetImageStream@CLockScreen@@UEAAJPEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z`
- size: `1728`
- prototype: `__int64 __fastcall(CLockScreen *__hidden this, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `0`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180009320`
- `0x180009f0c`
- `0x18000a910`
- `0x18000ada8`
- `0x18000b0d4`
- `0x18000bb20`
- `0x18000d340`
- `0x180023fb0`
- `0x18003217c`
- `0x180032a8c`
- `0x18003395c`
- `0x180034db4`
- `0x180039c30`
- `0x18003a5bc`
- `0x18003d6a4`
- `0x18003d768`
- `0x18003d858`
- `0x1800405f4`
- `0x1800406ec`
- `0x1800436a8`
- `0x180044054`
- `0x180045dc4`
- `0x180049de8`
- `0x180050ba0`
- `0x1800ab378`
- `0x1800af2e8`
- `0x1800b23a4`
- `0x1800b9970`
- `0x1800d4f30`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000987a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000987a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000939d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000939d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800093b6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800093b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009883`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009883`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x18000948e`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x180009593`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x1800096e5`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x18000948e`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x180009593`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x1800096e5`
- `SHELL32!__imp_ILFree` at `0x18000982c`
- `SHELL32!__imp_ILFree` at `0x18000982c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000976e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009839`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000976e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009839`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009866`

## string_xrefs

- `0x180009688`: `LandscapeAssetPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CLockScreen::GetImageStream(void **this, struct Windows::Storage::Streams::IRandomAccessStream **a2)
{
  struct Windows::Storage::Streams::IRandomAccessStream **v2; // r15
  int updated; // ebx
  bool v5; // r12
  HANDLE MutexW; // rax
  void *v7; // rsi
  int v8; // eax
  char v9; // r14
  unsigned __int16 *v10; // rbx
  __int64 v11; // r9
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  int Stream; // eax
  __int64 v16; // rdx
  PCWSTR v17; // rbx
  int v18; // eax
  int v19; // r9d
  int v20; // eax
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // rdx
  unsigned __int16 v24; // r15
  const struct _GUID *v25; // rdx
  int v26; // eax
  struct Windows::Storage::Streams::IRandomAccessStream *v27; // rax
  int v28; // eax
  struct Windows::Storage::Streams::IRandomAccessStream *v29; // rax
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  bool *v33; // [rsp+28h] [rbp-D8h]
  struct Windows::Storage::Streams::IRandomAccessStream *v34; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v35; // [rsp+38h] [rbp-C8h] BYREF
  PCWSTR pszPath; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h]
  __int64 v38; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  void *v40; // [rsp+60h] [rbp-A0h] BYREF
  struct Windows::Storage::Streams::IRandomAccessStream **v41; // [rsp+68h] [rbp-98h] BYREF
  HANDLE v42; // [rsp+70h] [rbp-90h] BYREF
  bool v43; // [rsp+78h] [rbp-88h]
  _BYTE v44[1624]; // [rsp+80h] [rbp-80h] BYREF
  LPITEMIDLIST pidl; // [rsp+6D8h] [rbp+5D8h]
  LPVOID v46; // [rsp+6E0h] [rbp+5E0h]
  _BYTE v47[1664]; // [rsp+700h] [rbp+600h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+DC8h] [rbp+CC8h]

  v2 = a2;
  v41 = a2;
  if ( CLockScreen::s_IsSystemProcess() )
  {
    updated = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1419,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)0x8000FFFFLL,
      v31);
    return (unsigned int)updated;
  }
  v5 = 0;
  v43 = 0;
  MutexW = CreateMutexW(0, 0, L"Local\\Microsoft-Windows-LockScreenHistory");
  v7 = MutexW;
  v42 = MutexW;
  if ( MutexW )
  {
    v5 = (WaitForSingleObject(MutexW, 0xFFFFFFFF) & 0xFFFFFF7F) == 0;
    v43 = v5;
  }
  *v2 = 0;
  if ( CLockScreen::_s_IsAppContainerProcess() )
  {
    v8 = CheckCallerCapabilityAndReportError(WinCapabilityPicturesLibrarySid, 0x9805u);
    updated = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x141F,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v8,
        v31);
LABEL_72:
      CLockScreenHistory::CSynchronizedOperation::~CSynchronizedOperation((CLockScreenHistory::CSynchronizedOperation *)&v42);
      return (unsigned int)updated;
    }
  }
  v35 = 0;
  v9 = 0;
  v34 = 0;
  if ( CLockScreen::_s_IsSpecificLockScreenLogonImageForced(&v35) )
  {
    v10 = v35;
    if ( !v35 )
    {
      updated = -2147467261;
      v11 = 2147500035LL;
      v12 = 5161;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)v11,
        v31);
LABEL_12:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v35);
      goto LABEL_72;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    v13 = CreateRandomAccessStreamOnFile(v10, 0, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v34);
    updated = v13;
    if ( v13 < 0 )
    {
      v11 = (unsigned int)v13;
      v12 = 5162;
      goto LABEL_11;
    }
LABEL_63:
    v40 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    v26 = CloneToInMemoryStream(v34, v25, &v40);
    updated = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1453,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v26,
        v31);
LABEL_65:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      goto LABEL_12;
    }
    v27 = (struct Windows::Storage::Streams::IRandomAccessStream *)v40;
    if ( v9 )
    {
      pv = 0;
      v41 = (struct Windows::Storage::Streams::IRandomAccessStream **)v40;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
      v28 = Microsoft::WRL::Details::MakeAndInitialize<CCreativeInMemoryStream,Windows::Storage::Streams::IRandomAccessStream,Windows::Storage::Streams::IRandomAccessStream *>(
              &pv,
              (__int64 *)&v41);
      updated = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x145C,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v28,
          v31);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
        goto LABEL_65;
      }
      v29 = (struct Windows::Storage::Streams::IRandomAccessStream *)pv;
      pv = 0;
      *v2 = v29;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pv);
    }
    else
    {
      v40 = 0;
      *v2 = v27;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v35);
    updated = 0;
    goto LABEL_72;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
  if ( CLockScreen::_s_IsSpotlightEnabled(0) )
  {
    pszPath = 0;
    v37 = 0;
    v38 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    v37 = -1;
    v38 = -1;
    v14 = CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(
            0,
            0,
            (unsigned __int16 **)&pszPath,
            0,
            0,
            v33);
    if ( v14 >= 0 )
    {
      v17 = pszPath;
      if ( pszPath && *pszPath )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        v18 = CreateRandomAccessStreamOnFile(v17, 0, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v34);
        updated = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1432,
            (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
            (const char *)(unsigned int)v18,
            v31);
          goto LABEL_25;
        }
        v9 = 1;
        goto LABEL_32;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x142F,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v14,
        v31);
    }
    CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v47);
    Stream = CLockScreenHistory::_EnsureCurrentUserSid((CLockScreenHistory *)(this + 15));
    updated = Stream;
    if ( Stream < 0 )
    {
      v16 = 5176;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)Stream,
        v31);
      CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v47);
      goto LABEL_25;
    }
    Stream = CLockScreenHistory::_InitAndEnsureGPEntry(
               (CLockScreenHistory *)(this + 15),
               (struct CLockScreenHistory::CLockScreenHistoryEntry *)v47,
               0x5Au);
    updated = Stream;
    if ( Stream < 0 )
    {
      v16 = 5177;
      goto LABEL_20;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    Stream = CLockScreenHistory::CLockScreenHistoryEntry::GetStream(
               (CLockScreenHistory::CLockScreenHistoryEntry *)v47,
               &v34);
    updated = Stream;
    if ( Stream < 0 )
    {
      v16 = 5178;
      goto LABEL_20;
    }
    v9 = 1;
    CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v47);
LABEL_32:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    goto LABEL_63;
  }
  if ( CLockScreen::_s_IsSpotlight() && !CLockScreen::_s_IsSpotlightExpired() )
  {
    pszPath = 0;
    v37 = 0;
    v38 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    v37 = -1;
    v38 = -1;
    v20 = SHRegAllocData(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen\\Creative",
            L"LandscapeAssetPath",
            v19,
            (void **)&pszPath,
            (unsigned int *)v33);
    updated = v20;
    if ( v20 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      v20 = CreateRandomAccessStreamOnFile(pszPath, 0, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &v34);
      updated = v20;
      if ( v20 >= 0 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
        v9 = 1;
        goto LABEL_63;
      }
      v21 = 5187;
    }
    else
    {
      v21 = 5186;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)(unsigned int)v20,
      v31);
LABEL_25:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    goto LABEL_12;
  }
  CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v44);
  v22 = CLockScreenHistory::_EnsureCurrentUserSid((CLockScreenHistory *)(this + 15));
  updated = v22;
  if ( v22 < 0 )
  {
    v23 = 5193;
    goto LABEL_43;
  }
  pv = 0;
  if ( (int)CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(this[15], 1, (unsigned __int16 **)&pv) < 0 )
  {
    v24 = String2[0];
  }
  else
  {
    v24 = *(_WORD *)pv;
    CoTaskMemFree(pv);
  }
  updated = CLockScreenHistory::CLockScreenHistoryEntry::Init((CLockScreenHistory::CLockScreenHistoryEntry *)v44, v24);
  if ( updated >= 0 && v24 == 80 )
  {
    pszPath = 0;
    v37 = 0;
    v38 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
    v37 = -1;
    v38 = -1;
    updated = LockScreenPathFromPolicy((unsigned __int16 **)&pszPath);
    if ( updated >= 0 )
      updated = CLockScreenHistory::_InitOrUpdateGPImages((CLockScreenHistory *)(this + 15), pszPath);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
  }
  if ( updated >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    v22 = CLockScreenHistory::CLockScreenHistoryEntry::GetStream(
            (CLockScreenHistory::CLockScreenHistoryEntry *)v44,
            &v34);
    updated = v22;
    if ( v22 >= 0 )
    {
      CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v44);
      v2 = v41;
      goto LABEL_63;
    }
    v23 = 5197;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)(unsigned int)v22,
      v31);
    CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v44);
    goto LABEL_12;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x685,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
    (const char *)(unsigned int)updated,
    v31);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x144C,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
    (const char *)(unsigned int)updated,
    v32);
  ILFree(pidl);
  CoTaskMemFree(v46);
  if ( v35 )
    CoTaskMemFree(v35);
  if ( v7 )
  {
    if ( v5 )
      ReleaseMutex(v7);
    CloseHandle(v7);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180009320  mov     [rsp-8+arg_10], rbx
0x180009325  push    rbp
0x180009326  push    rsi
0x180009327  push    rdi
0x180009328  push    r12
0x18000932a  push    r13
0x18000932c  push    r14
0x18000932e  push    r15
0x180009330  lea     rbp, [rsp-0C90h]
0x180009338  sub     rsp, 0D90h
0x18000933f  mov     rax, cs:__security_cookie
0x180009346  xor     rax, rsp
0x180009349  mov     [rbp+0CC0h+var_40], rax
0x180009350  mov     r15, rdx
0x180009353  mov     [rsp+0DC0h+var_D58], rdx
0x180009358  mov     r13, rcx
0x18000935b  call    ?s_IsSystemProcess@CLockScreen@@SA_NXZ; CLockScreen::s_IsSystemProcess(void)
0x180009360  xor     ebx, ebx
0x180009362  test    al, al
0x180009364  jz      short loc_18000938B
0x180009366  mov     rcx, [rbp+0CC8h]; this
0x18000936d  mov     ebx, 8000FFFFh
0x180009372  mov     r9d, ebx; char *
0x180009375  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000937c  mov     edx, 1419h; void *
0x180009381  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009386  jmp     loc_1800099B4
0x18000938b  mov     r12b, bl
0x18000938e  mov     [rsp+0DC0h+var_D48], bl
0x180009392  lea     r8, Name; "Local\\Microsoft-Windows-LockScreenHist"...
0x180009399  xor     edx, edx; bInitialOwner
0x18000939b  xor     ecx, ecx; lpMutexAttributes
0x18000939d  call    cs:__imp_CreateMutexW
0x1800093a3  mov     rsi, rax
0x1800093a6  mov     [rsp+0DC0h+var_D50], rax
0x1800093ab  test    rax, rax
0x1800093ae  jz      short loc_1800093CA
0x1800093b0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800093b3  mov     rcx, rax; hHandle
0x1800093b6  call    cs:__imp_WaitForSingleObject
0x1800093bc  test    eax, 0FFFFFF7Fh
0x1800093c1  setz    r12b
0x1800093c5  mov     [rsp+0DC0h+var_D48], r12b
0x1800093ca  mov     [r15], rbx
0x1800093cd  call    ?_s_IsAppContainerProcess@CLockScreen@@KA_NXZ; CLockScreen::_s_IsAppContainerProcess(void)
0x1800093d2  test    al, al
0x1800093d4  jz      short loc_18000940D
0x1800093d6  mov     edx, 9805h; unsigned int
0x1800093db  mov     ecx, 58h ; 'X'; enum WELL_KNOWN_SID_TYPE
0x1800093e0  call    ?CheckCallerCapabilityAndReportError@@YAJW4WELL_KNOWN_SID_TYPE@@IZZ; CheckCallerCapabilityAndReportError(WELL_KNOWN_SID_TYPE,uint,...)
0x1800093e5  mov     ebx, eax
0x1800093e7  test    eax, eax
0x1800093e9  jns     short loc_18000940B
0x1800093eb  mov     rcx, [rbp+0CC8h]; this
0x1800093f2  mov     r9d, eax; char *
0x1800093f5  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x1800093fc  mov     edx, 141Fh; void *
0x180009401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009406  jmp     loc_1800099AA
0x18000940b  xor     ebx, ebx
0x18000940d  mov     [rsp+0DC0h+var_D88], rbx
0x180009412  lea     rcx, [rsp+0DC0h+var_D88]; unsigned __int16 **
0x180009417  call    ?_s_IsSpecificLockScreenLogonImageForced@CLockScreen@@KA_NPEAPEAG@Z; CLockScreen::_s_IsSpecificLockScreenLogonImageForced(ushort * *)
0x18000941c  mov     r14b, bl
0x18000941f  mov     [rsp+0DC0h+var_D90], rbx
0x180009424  lea     rdi, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000942b  test    al, al
0x18000942d  jz      short loc_1800094A8
0x18000942f  mov     rbx, [rsp+0DC0h+var_D88]
0x180009434  xor     r13d, r13d
0x180009437  test    rbx, rbx
0x18000943a  jnz     short loc_180009473
0x18000943c  mov     ebx, 80004003h
0x180009441  mov     r9d, ebx; char *
0x180009444  mov     edx, 1429h; void *
0x180009449  mov     r8, rdi; unsigned int
0x18000944c  mov     rcx, [rbp+0CC8h]; this
0x180009453  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009458  nop
0x180009459  lea     rcx, [rsp+0DC0h+var_D90]
0x18000945e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180009463  nop
0x180009464  lea     rcx, [rsp+0DC0h+var_D88]
0x180009469  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000946e  jmp     loc_1800099AA
0x180009473  lea     rcx, [rsp+0DC0h+var_D90]
0x180009478  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000947d  lea     r9, [rsp+0DC0h+var_D90]
0x180009482  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180009489  xor     edx, edx
0x18000948b  mov     rcx, rbx
0x18000948e  call    cs:__imp_CreateRandomAccessStreamOnFile
0x180009494  mov     ebx, eax
0x180009496  test    eax, eax
0x180009498  jns     loc_1800098C5
0x18000949e  mov     r9d, eax
0x1800094a1  mov     edx, 142Ah
0x1800094a6  jmp     short loc_180009449
0x1800094a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x1800094af  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x1800094b4  xor     ecx, ecx; this
0x1800094b6  call    ?_s_IsSpotlightEnabled@CLockScreen@@KA_NPEBG@Z; CLockScreen::_s_IsSpotlightEnabled(ushort const *)
0x1800094bb  test    al, al
0x1800094bd  jz      loc_18000963D
0x1800094c3  mov     [rsp+0DC0h+pszPath], rbx
0x1800094c8  mov     [rsp+0DC0h+var_D78], rbx
0x1800094cd  mov     [rsp+0DC0h+var_D70], rbx
0x1800094d2  lea     rcx, [rsp+0DC0h+pszPath]
0x1800094d7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800094dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800094e0  mov     [rsp+0DC0h+var_D78], rax
0x1800094e5  mov     [rsp+0DC0h+var_D70], rax
0x1800094ea  mov     [rsp+0DC0h+var_DA0], rbx; int
0x1800094ef  xor     r9d, r9d; unsigned __int16 **
0x1800094f2  lea     r8, [rsp+0DC0h+pszPath]; unsigned __int16 **
0x1800094f7  xor     edx, edx; unsigned __int16 *
0x1800094f9  xor     ecx, ecx; this
0x1800094fb  call    ?PeekLockScreenRegistryKeys@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBGPEAPEAG11PEA_N@Z; CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(ushort const *,ushort * *,ushort * *,ushort * *,bool *)
0x180009500  mov     rcx, [rbp+0CC8h]; this
0x180009507  test    eax, eax
0x180009509  jns     short loc_180009567
0x18000950b  mov     r9d, eax; char *
0x18000950e  mov     r8, rdi; unsigned int
0x180009511  mov     edx, 142Fh; void *
0x180009516  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000951b  lea     rcx, [rbp+0CC0h+var_6C0]; this
0x180009522  call    ??0CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry(void)
0x180009527  nop
0x180009528  lea     rsi, [r13+78h]
0x18000952c  mov     rcx, rsi; this
0x18000952f  call    ?_EnsureCurrentUserSid@CLockScreenHistory@@IEAAJXZ; CLockScreenHistory::_EnsureCurrentUserSid(void)
0x180009534  mov     ebx, eax
0x180009536  xor     r13d, r13d
0x180009539  test    eax, eax
0x18000953b  jns     loc_1800095CE
0x180009541  mov     edx, 1438h; void *
0x180009546  mov     rcx, [rbp+0CC8h]; this
0x18000954d  mov     r9d, eax; char *
0x180009550  mov     r8, rdi; unsigned int
0x180009553  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009558  nop
0x180009559  lea     rcx, [rbp+0CC0h+var_6C0]; this
0x180009560  call    ??1CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry(void)
0x180009565  jmp     short loc_1800095BA
0x180009567  mov     rbx, [rsp+0DC0h+pszPath]
0x18000956c  xor     eax, eax
0x18000956e  test    rbx, rbx
0x180009571  jz      short loc_18000951B
0x180009573  cmp     [rbx], ax
0x180009576  jz      short loc_18000951B
0x180009578  lea     rcx, [rsp+0DC0h+var_D90]
0x18000957d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180009582  lea     r9, [rsp+0DC0h+var_D90]
0x180009587  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x18000958e  xor     edx, edx
0x180009590  mov     rcx, rbx
0x180009593  call    cs:__imp_CreateRandomAccessStreamOnFile
0x180009599  mov     ebx, eax
0x18000959b  xor     r13d, r13d
0x18000959e  test    eax, eax
0x1800095a0  jns     short loc_1800095C9
0x1800095a2  mov     rcx, [rbp+0CC8h]; this
0x1800095a9  mov     r9d, eax; char *
0x1800095ac  mov     r8, rdi; unsigned int
0x1800095af  mov     edx, 1432h; void *
0x1800095b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800095b9  nop
0x1800095ba  lea     rcx, [rsp+0DC0h+pszPath]
0x1800095bf  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800095c4  jmp     loc_180009459
0x1800095c9  mov     r14b, 1
0x1800095cc  jmp     short loc_18000962E
0x1800095ce  mov     r8d, 5Ah ; 'Z'; unsigned __int16
0x1800095d4  lea     rdx, [rbp+0CC0h+var_6C0]; struct CLockScreenHistory::CLockScreenHistoryEntry *
0x1800095db  mov     rcx, rsi; this
0x1800095de  call    ?_InitAndEnsureGPEntry@CLockScreenHistory@@IEAAJPEAVCLockScreenHistoryEntry@1@G@Z; CLockScreenHistory::_InitAndEnsureGPEntry(CLockScreenHistory::CLockScreenHistoryEntry *,ushort)
0x1800095e3  mov     ebx, eax
0x1800095e5  test    eax, eax
0x1800095e7  jns     short loc_1800095F3
0x1800095e9  mov     edx, 1439h
0x1800095ee  jmp     loc_180009546
0x1800095f3  lea     rcx, [rsp+0DC0h+var_D90]
0x1800095f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800095fd  lea     rdx, [rsp+0DC0h+var_D90]; struct Windows::Storage::Streams::IRandomAccessStream **
0x180009602  lea     rcx, [rbp+0CC0h+var_6C0]; this
0x180009609  call    ?GetStream@CLockScreenHistoryEntry@CLockScreenHistory@@QEAAJPEAPEAUIRandomAccessStream@Streams@Storage@Windows@@@Z; CLockScreenHistory::CLockScreenHistoryEntry::GetStream(Windows::Storage::Streams::IRandomAccessStream * *)
0x18000960e  mov     ebx, eax
0x180009610  test    eax, eax
0x180009612  jns     short loc_18000961E
0x180009614  mov     edx, 143Ah
0x180009619  jmp     loc_180009546
0x18000961e  mov     r14b, 1
0x180009621  lea     rcx, [rbp+0CC0h+var_6C0]; this
0x180009628  call    ??1CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry(void)
0x18000962d  nop
0x18000962e  lea     rcx, [rsp+0DC0h+pszPath]
0x180009633  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009638  jmp     loc_1800098C5
0x18000963d  call    ?_s_IsSpotlight@CLockScreen@@KA_NXZ; CLockScreen::_s_IsSpotlight(void)
0x180009642  test    al, al
0x180009644  jz      loc_18000970A
0x18000964a  call    ?_s_IsSpotlightExpired@CLockScreen@@KA_NXZ; CLockScreen::_s_IsSpotlightExpired(void)
0x18000964f  test    al, al
0x180009651  jnz     loc_18000970A
0x180009657  mov     [rsp+0DC0h+pszPath], rbx
0x18000965c  mov     [rsp+0DC0h+var_D78], rbx
0x180009661  mov     [rsp+0DC0h+var_D70], rbx
0x180009666  lea     rcx, [rsp+0DC0h+pszPath]
0x18000966b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009670  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009674  mov     [rsp+0DC0h+var_D78], rax
0x180009679  mov     [rsp+0DC0h+var_D70], rax
0x18000967e  lea     rax, [rsp+0DC0h+pszPath]
0x180009683  mov     [rsp+0DC0h+var_DA0], rax; int
0x180009688  lea     r8, ?c_landscapeAssetPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "LandscapeAssetPath"
0x18000968f  lea     rdx, ?c_lockScreenCreativeKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180009696  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18000969d  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1800096a2  mov     ebx, eax
0x1800096a4  xor     r13d, r13d
0x1800096a7  test    eax, eax
0x1800096a9  jns     short loc_1800096C8
0x1800096ab  mov     edx, 1442h; void *
0x1800096b0  mov     r8, rdi; unsigned int
0x1800096b3  mov     r9d, eax; char *
0x1800096b6  mov     rcx, [rbp+0CC8h]; this
0x1800096bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096c2  nop
0x1800096c3  jmp     loc_1800095BA
0x1800096c8  lea     rcx, [rsp+0DC0h+var_D90]
0x1800096cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800096d2  lea     r9, [rsp+0DC0h+var_D90]
0x1800096d7  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x1800096de  xor     edx, edx
0x1800096e0  mov     rcx, [rsp+0DC0h+pszPath]
0x1800096e5  call    cs:__imp_CreateRandomAccessStreamOnFile
0x1800096eb  mov     ebx, eax
0x1800096ed  test    eax, eax
0x1800096ef  jns     short loc_1800096F8
0x1800096f1  mov     edx, 1443h
0x1800096f6  jmp     short loc_1800096B0
0x1800096f8  lea     rcx, [rsp+0DC0h+pszPath]
0x1800096fd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180009702  mov     r14b, 1
0x180009705  jmp     loc_1800098C5
0x18000970a  lea     rcx, [rbp+0CC0h+var_D40]; this
0x18000970e  call    ??0CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry(void)
0x180009713  nop
0x180009714  lea     rcx, [r13+78h]; this
0x180009718  call    ?_EnsureCurrentUserSid@CLockScreenHistory@@IEAAJXZ; CLockScreenHistory::_EnsureCurrentUserSid(void)
0x18000971d  mov     ebx, eax
0x18000971f  xor     r15d, r15d
0x180009722  test    eax, eax
0x180009724  jns     short loc_18000974C
0x180009726  mov     edx, 1449h; void *
0x18000972b  mov     r8, rdi; unsigned int
0x18000972e  mov     r9d, eax; char *
0x180009731  mov     rcx, [rbp+0CC8h]; this
0x180009738  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000973d  nop
0x18000973e  lea     rcx, [rbp+0CC0h+var_D40]; this
0x180009742  call    ??1CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry(void)
0x180009747  jmp     loc_180009459
0x18000974c  mov     [rsp+0DC0h+pv], r15
0x180009751  lea     r8, [rsp+0DC0h+pv]; unsigned __int16 **
0x180009756  mov     dl, 1; bool
0x180009758  mov     rcx, [r13+78h]; void *
0x18000975c  call    ?_s_GetLockScreenHistoryOrderInternal@CLockScreenHistory@@KAJPEAX_NPEAPEAG@Z; CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(void *,bool,ushort * *)
0x180009761  test    eax, eax
0x180009763  js      short loc_180009776
0x180009765  mov     rcx, [rsp+0DC0h+pv]; pv
0x18000976a  movzx   r15d, word ptr [rcx]
0x18000976e  call    cs:__imp_CoTaskMemFree
0x180009774  jmp     short loc_18000977E
0x180009776  movzx   r15d, word ptr cs:String2; "ZYXWVU"
0x18000977e  movzx   edx, r15w; unsigned __int16
0x180009782  lea     rcx, [rbp+0CC0h+var_D40]; this
0x180009786  call    ?Init@CLockScreenHistoryEntry@CLockScreenHistory@@QEAAJG@Z; CLockScreenHistory::CLockScreenHistoryEntry::Init(ushort)
0x18000978b  mov     ebx, eax
0x18000978d  xor     eax, eax
0x18000978f  test    ebx, ebx
0x180009791  js      short loc_1800097EB
0x180009793  cmp     r15w, 50h ; 'P'
0x180009798  jnz     short loc_1800097EB
0x18000979a  mov     [rsp+0DC0h+pszPath], rax
0x18000979f  mov     [rsp+0DC0h+var_D78], rax
0x1800097a4  mov     [rsp+0DC0h+var_D70], rax
0x1800097a9  lea     rcx, [rsp+0DC0h+pszPath]
0x1800097ae  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800097b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800097b7  mov     [rsp+0DC0h+var_D78], rax
0x1800097bc  mov     [rsp+0DC0h+var_D70], rax
0x1800097c1  lea     rcx, [rsp+0DC0h+pszPath]; unsigned __int16 **
0x1800097c6  call    ?LockScreenPathFromPolicy@@YAJPEAPEAG@Z; LockScreenPathFromPolicy(ushort * *)
0x1800097cb  mov     ebx, eax
0x1800097cd  test    eax, eax
0x1800097cf  js      short loc_1800097E1
0x1800097d1  mov     rdx, [rsp+0DC0h+pszPath]; pszPath
0x1800097d6  lea     rcx, [r13+78h]; this
0x1800097da  call    ?_InitOrUpdateGPImages@CLockScreenHistory@@IEAAJPEBG@Z; CLockScreenHistory::_InitOrUpdateGPImages(ushort const *)
  ... truncated ...
```
