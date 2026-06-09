# Windows::Internal::Flighting::ClientAttributes::GetOrRefreshJsonFromOneSettings(bool,CtacJsonData *,Microsoft::WRL::Wrappers::HString &,Microsoft::WRL::ComPtr<CtacJsonData> &)

- ea: `0x180037e90`
- end: `0x18003835b`
- name: `?GetOrRefreshJsonFromOneSettings@ClientAttributes@Flighting@Internal@Windows@@CAJ_NPEAVCtacJsonData@@AEAVHString@Wrappers@WRL@Microsoft@@AEAV?$ComPtr@VCtacJsonData@@@89@@Z`
- size: `1227`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038acc`

## callees

- `0x180004b80`
- `0x180009758`
- `0x18000b19c`
- `0x18000cc8c`
- `0x18001146c`
- `0x1800198f0`
- `0x18003352c`
- `0x180033568`
- `0x180033c88`
- `0x180033e18`
- `0x180037e90`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180037ed8`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x180037ed8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180038138`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180038138`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800380b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038201`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003828d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003829d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800382ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800382e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038328`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800380b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038201`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003828d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003829d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800382ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800382e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038328`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038109`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003811d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003824f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038109`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003811d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003824f`

## string_xrefs

- `0x180037faa`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`
- `0x180038025`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`
- `0x1800380dd`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`
- `0x180038278`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`
- `0x1800382ff`: `onecore\base\flighting\flightsettings\broker\libs\ctac\clientattributes.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Internal::Flighting::ClientAttributes::GetOrRefreshJsonFromOneSettings(
        char a1,
        struct CtacJsonData *a2,
        HSTRING *a3,
        __int64 a4)
{
  int v6; // ebx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, __int64, __int64, __int64 *); // rdi
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rdx
  unsigned __int64 v14; // rdi
  __int64 (__fastcall *v15)(unsigned __int64, __int64, __int64 *); // rbx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v20; // rax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, __int64 *); // rbx
  int v23; // eax
  unsigned __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64, UINT32 *); // rbx
  int v28; // eax
  __int64 v29; // rdx
  HSTRING v30; // rbx
  CtacJsonData *v31; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-79h]
  HSTRING string; // [rsp+30h] [rbp-69h] BYREF
  UINT32 length[2]; // [rsp+38h] [rbp-61h] BYREF
  CtacJsonData *v36; // [rsp+40h] [rbp-59h] BYREF
  __int64 v37; // [rsp+48h] [rbp-51h] BYREF
  __int64 v38; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int64 v39; // [rsp+58h] [rbp-41h] BYREF
  __int64 v40; // [rsp+60h] [rbp-39h] BYREF
  UINT32 v41[2]; // [rsp+68h] [rbp-31h] BYREF
  struct CtacJsonData *v42; // [rsp+70h] [rbp-29h] BYREF
  HSTRING_HEADER v43; // [rsp+78h] [rbp-21h] BYREF
  __int64 v44; // [rsp+90h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-1h] BYREF
  __int64 v46; // [rsp+B0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v42 = a2;
  v37 = 0;
  if ( !a1 )
  {
    v39 = 0;
    v44 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &v43,
      L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
      0x3Au,
      0x39u);
    v12 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(
            v44,
            (__int64)&v39);
    v6 = v12;
    if ( v12 >= 0 )
    {
      v14 = v39;
      v15 = *(__int64 (__fastcall **)(unsigned __int64, __int64, __int64 *))(*(_QWORD *)v39 + 48LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
      v44 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v43, L"CTAC", 5u, 4u);
      v12 = v15(v14, v44, &v37);
      v6 = v12;
      if ( v12 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
        goto LABEL_17;
      }
      v13 = 752;
    }
    else
    {
      v13 = 749;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
      (const char *)(unsigned int)v12,
      bIgnoreCase);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
    goto LABEL_39;
  }
  v39 = (unsigned __int64)&Windows::Internal::Flighting::ClientAttributes::s_lockRefresh
      & -(__int64)TryEnterCriticalSection(&Windows::Internal::Flighting::ClientAttributes::s_lockRefresh);
  if ( v39 )
  {
    v40 = 0;
    v46 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.Flighting.OneSettings.OneSettingsManager",
      0x3Au,
      0x39u);
    v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsManager>>(
           v46,
           (__int64)&v40);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 740;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
        (const char *)(unsigned int)v7,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      goto LABEL_9;
    }
    v9 = v40;
    v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v40 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
    v46 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"10.0", 5u, 4u);
    v11 = v46;
    v44 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v43, L"CTAC", 5u, 4u);
    v7 = v10(v9, v44, v11, &v37);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 743;
      goto LABEL_8;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v39);
LABEL_17:
    string = 0;
    v16 = v37;
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 128LL);
    WindowsDeleteString(0);
    string = 0;
    v18 = v17(v16, &string);
    v6 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F5,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
        (const char *)(unsigned int)v18,
        bIgnoreCase);
LABEL_37:
      WindowsDeleteString(string);
      goto LABEL_38;
    }
    if ( string )
    {
      if ( *a3 )
      {
        length[0] = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(string, length);
        v41[0] = 0;
        v20 = WindowsGetStringRawBuffer(*a3, v41);
        if ( CompareStringOrdinal(StringRawBuffer, length[0], v20, v41[0], 1) == 2 )
        {
          WindowsDeleteString(string);
          v6 = 0;
LABEL_38:
          string = 0;
          goto LABEL_39;
        }
      }
    }
    v36 = 0;
    v38 = 0;
    v21 = v37;
    v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v37 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
    v44 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v43, L"CTACTARGETINGATTRIBUTES", 0x18u, 0x17u);
    v6 = v22(v21, v44, &v38);
    if ( v6 >= 0 )
    {
      *(_QWORD *)length = v38;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      v23 = Microsoft::WRL::Details::MakeAndInitialize<CtacJsonData,CtacJsonData,Windows::Data::Json::IJsonObject *,CtacJsonData * &>(
              &v36,
              (struct Windows::Data::Json::IJsonObject **)length,
              &v42);
      v6 = v23;
      if ( v23 < 0 )
      {
        v24 = (unsigned int)v23;
        v25 = 771;
LABEL_35:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
          (const char *)v24,
          bIgnoreCase);
        goto LABEL_36;
      }
LABEL_33:
      v30 = string;
      string = 0;
      WindowsDeleteString(*a3);
      *a3 = v30;
      v31 = v36;
      v36 = 0;
      Microsoft::WRL::ComPtr<CFlightStore>::Attach(a4, v31);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
      return 0;
    }
    if ( v6 != -2147483634 )
    {
      v24 = (unsigned int)v6;
      v25 = 787;
      goto LABEL_35;
    }
    *(_QWORD *)length = 0;
    v26 = v37;
    v27 = *(__int64 (__fastcall **)(__int64, __int64, UINT32 *))(*(_QWORD *)v37 + 72LL);
    WindowsDeleteString(0);
    *(_QWORD *)length = 0;
    v44 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v43, L"CTACTARGETINGATTRIBUTES", 0x18u, 0x17u);
    v28 = v27(v26, v44, length);
    v6 = v28;
    if ( v28 >= 0 )
    {
      *(_QWORD *)v41 = WindowsGetStringRawBuffer(*(HSTRING *)length, 0);
      v28 = Microsoft::WRL::Details::MakeAndInitialize<CtacJsonData,CtacJsonData,unsigned short const *,CtacJsonData * &>(
              &v36,
              (PCWSTR *)v41,
              &v42);
      v6 = v28;
      if ( v28 >= 0 )
      {
        WindowsDeleteString(*(HSTRING *)length);
        goto LABEL_33;
      }
      v29 = 783;
    }
    else
    {
      v29 = 780;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\clientattributes.cpp",
      (const char *)(unsigned int)v28,
      bIgnoreCase);
    WindowsDeleteString(*(HSTRING *)length);
    *(_QWORD *)length = 0;
LABEL_36:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
    goto LABEL_37;
  }
  v6 = 0;
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v39);
LABEL_39:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180037e90  push    rbp
0x180037e92  push    rbx
0x180037e93  push    rsi
0x180037e94  push    rdi
0x180037e95  push    r12
0x180037e97  push    r14
0x180037e99  push    r15
0x180037e9b  lea     rbp, [rsp-27h]
0x180037ea0  sub     rsp, 0C0h
0x180037ea7  mov     rax, cs:__security_cookie
0x180037eae  xor     rax, rsp
0x180037eb1  mov     [rbp+57h+var_38], rax
0x180037eb5  mov     r15, r9
0x180037eb8  mov     r14, r8
0x180037ebb  mov     [rbp+57h+var_80], rdx
0x180037ebf  xor     r12d, r12d
0x180037ec2  mov     [rbp+57h+var_A8], r12
0x180037ec6  test    cl, cl
0x180037ec8  jz      loc_180037FEB
0x180037ece  lea     rbx, ?s_lockRefresh@ClientAttributes@Flighting@Internal@Windows@@0Vcritical_section@wil@@A; wil::critical_section Windows::Internal::Flighting::ClientAttributes::s_lockRefresh
0x180037ed5  mov     rcx, rbx; lpCriticalSection
0x180037ed8  call    cs:__imp_TryEnterCriticalSection
0x180037ede  neg     eax
0x180037ee0  sbb     rcx, rcx
0x180037ee3  and     rcx, rbx
0x180037ee6  mov     [rbp+57h+var_98], rcx
0x180037eea  jnz     short loc_180037EF4
0x180037eec  mov     ebx, r12d
0x180037eef  jmp     loc_180037FC5
0x180037ef4  mov     [rbp+57h+var_90], r12
0x180037ef8  mov     [rbp+57h+var_40], r12
0x180037efc  mov     r9d, 39h ; '9'; unsigned int
0x180037f02  lea     r8d, [r9+1]; unsigned int
0x180037f06  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x180037f0d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180037f11  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180037f16  lea     rdx, [rbp+57h+var_90]
0x180037f1a  mov     rcx, [rbp+57h+var_40]
0x180037f1e  call    ??$GetActivationFactory@V?$ComPtr@UIOneSettingsManager@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIOneSettingsManager@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsManager>>)
0x180037f23  mov     ebx, eax
0x180037f25  test    eax, eax
0x180037f27  jns     short loc_180037F30
0x180037f29  mov     edx, 2E4h
0x180037f2e  jmp     short loc_180037FA7
0x180037f30  mov     rsi, [rbp+57h+var_90]
0x180037f34  mov     rax, [rsi]
0x180037f37  mov     rdi, [rax+38h]
0x180037f3b  lea     rcx, [rbp+57h+var_A8]
0x180037f3f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180037f44  mov     [rbp+57h+var_40], r12
0x180037f48  mov     r9d, 4; unsigned int
0x180037f4e  lea     r8d, [r9+1]; unsigned int
0x180037f52  lea     rdx, a100; "10.0"
0x180037f59  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180037f5d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180037f62  nop
0x180037f63  mov     rbx, [rbp+57h+var_40]
0x180037f67  mov     [rbp+57h+var_60], r12
0x180037f6b  mov     r9d, 4; unsigned int
0x180037f71  lea     r8d, [r9+1]; unsigned int
0x180037f75  lea     rdx, ?c_szCtacOneSettingsName@ClientAttributes@Flighting@Internal@Windows@@0QBGB; "CTAC"
0x180037f7c  lea     rcx, [rbp+57h+var_78]; hstringHeader
0x180037f80  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180037f85  nop
0x180037f86  lea     r9, [rbp+57h+var_A8]
0x180037f8a  mov     r8, rbx
0x180037f8d  mov     rdx, [rbp+57h+var_60]
0x180037f91  mov     rcx, rsi
0x180037f94  mov     rax, rdi
0x180037f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f9c  mov     ebx, eax
0x180037f9e  test    eax, eax
0x180037fa0  jns     short loc_180037FD3
0x180037fa2  mov     edx, 2E7h; void *
0x180037fa7  mov     r9d, eax; char *
0x180037faa  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x180037fb1  mov     rcx, [rbp+5Fh]; this
0x180037fb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037fba  nop
0x180037fbb  lea     rcx, [rbp+57h+var_90]
0x180037fbf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180037fc4  nop
0x180037fc5  lea     rcx, [rbp+57h+var_98]
0x180037fc9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180037fce  jmp     loc_180038332
0x180037fd3  lea     rcx, [rbp+57h+var_90]
0x180037fd7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180037fdc  nop
0x180037fdd  lea     rcx, [rbp+57h+var_98]
0x180037fe1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180037fe6  jmp     loc_1800380A3
0x180037feb  mov     [rbp+57h+var_98], r12
0x180037fef  mov     [rbp+57h+var_60], r12
0x180037ff3  mov     r9d, 39h ; '9'; unsigned int
0x180037ff9  lea     r8d, [r9+1]; unsigned int
0x180037ffd  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x180038004  lea     rcx, [rbp+57h+var_78]; hstringHeader
0x180038008  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003800d  lea     rdx, [rbp+57h+var_98]
0x180038011  mov     rcx, [rbp+57h+var_60]
0x180038015  call    ??$GetActivationFactory@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>)
0x18003801a  mov     ebx, eax
0x18003801c  test    eax, eax
0x18003801e  jns     short loc_180038047
0x180038020  mov     edx, 2EDh; void *
0x180038025  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x18003802c  mov     r9d, eax; char *
0x18003802f  mov     rcx, [rbp+5Fh]; this
0x180038033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038038  nop
0x180038039  lea     rcx, [rbp+57h+var_98]
0x18003803d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180038042  jmp     loc_180038332
0x180038047  mov     rdi, [rbp+57h+var_98]
0x18003804b  mov     rax, [rdi]
0x18003804e  mov     rbx, [rax+30h]
0x180038052  lea     rcx, [rbp+57h+var_A8]
0x180038056  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003805b  mov     [rbp+57h+var_60], r12
0x18003805f  mov     r9d, 4; unsigned int
0x180038065  lea     r8d, [r9+1]; unsigned int
0x180038069  lea     rdx, ?c_szCtacOneSettingsName@ClientAttributes@Flighting@Internal@Windows@@0QBGB; "CTAC"
0x180038070  lea     rcx, [rbp+57h+var_78]; hstringHeader
0x180038074  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180038079  nop
0x18003807a  lea     r8, [rbp+57h+var_A8]
0x18003807e  mov     rdx, [rbp+57h+var_60]
0x180038082  mov     rcx, rdi
0x180038085  mov     rax, rbx
0x180038088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003808d  mov     ebx, eax
0x18003808f  test    eax, eax
0x180038091  jns     short loc_18003809A
0x180038093  mov     edx, 2F0h
0x180038098  jmp     short loc_180038025
0x18003809a  lea     rcx, [rbp+57h+var_98]
0x18003809e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800380a3  mov     [rbp+57h+string], r12
0x1800380a7  mov     rdi, [rbp+57h+var_A8]
0x1800380ab  mov     rax, [rdi]
0x1800380ae  mov     rbx, [rax+80h]
0x1800380b5  xor     ecx, ecx; string
0x1800380b7  call    cs:__imp_WindowsDeleteString
0x1800380bd  mov     [rbp+57h+string], r12
0x1800380c1  lea     rdx, [rbp+57h+string]
0x1800380c5  mov     rcx, rdi
0x1800380c8  mov     rax, rbx
0x1800380cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380d0  mov     ebx, eax
0x1800380d2  test    eax, eax
0x1800380d4  jns     short loc_1800380F3
0x1800380d6  mov     rcx, [rbp+5Fh]; this
0x1800380da  mov     r9d, eax; char *
0x1800380dd  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x1800380e4  mov     edx, 2F5h; void *
0x1800380e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800380ee  jmp     loc_180038324
0x1800380f3  mov     rcx, [rbp+57h+string]; string
0x1800380f7  test    rcx, rcx
0x1800380fa  jz      short loc_180038155
0x1800380fc  cmp     [r14], r12
0x1800380ff  jz      short loc_180038155
0x180038101  mov     [rbp+57h+length], r12d
0x180038105  lea     rdx, [rbp+57h+length]; length
0x180038109  call    cs:__imp_WindowsGetStringRawBuffer
0x18003810f  mov     rbx, rax
0x180038112  mov     [rbp+57h+var_88], r12d
0x180038116  lea     rdx, [rbp+57h+var_88]; length
0x18003811a  mov     rcx, [r14]; string
0x18003811d  call    cs:__imp_WindowsGetStringRawBuffer
0x180038123  mov     [rsp+0F0h+bIgnoreCase], 1; bIgnoreCase
0x18003812b  mov     r9d, [rbp+57h+var_88]; cchCount2
0x18003812f  mov     r8, rax; lpString2
0x180038132  mov     edx, [rbp+57h+length]; cchCount1
0x180038135  mov     rcx, rbx; lpString1
0x180038138  call    cs:__imp_CompareStringOrdinal
0x18003813e  cmp     eax, 2
0x180038141  jnz     short loc_180038155
0x180038143  mov     rcx, [rbp+57h+string]; string
0x180038147  call    cs:__imp_WindowsDeleteString
0x18003814d  mov     ebx, r12d
0x180038150  jmp     loc_18003832E
0x180038155  mov     [rbp+57h+var_B0], r12
0x180038159  mov     [rbp+57h+var_A0], r12
0x18003815d  mov     rdi, [rbp+57h+var_A8]
0x180038161  mov     rax, [rdi]
0x180038164  mov     rbx, [rax+38h]
0x180038168  lea     rcx, [rbp+57h+var_A0]
0x18003816c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180038171  mov     [rbp+57h+var_60], r12
0x180038175  mov     esi, 17h
0x18003817a  mov     r9d, esi; unsigned int
0x18003817d  lea     r8d, [rsi+1]; unsigned int
0x180038181  lea     rdx, ?c_szCtacOneSettingsValue@ClientAttributes@Flighting@Internal@Windows@@0QBGB; "CTACTARGETINGATTRIBUTES"
0x180038188  lea     rcx, [rbp+57h+var_78]; hstringHeader
0x18003818c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180038191  nop
0x180038192  lea     r8, [rbp+57h+var_A0]
0x180038196  mov     rdx, [rbp+57h+var_60]
0x18003819a  mov     rcx, rdi
0x18003819d  mov     rax, rbx
0x1800381a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381a5  mov     ebx, eax
0x1800381a7  test    eax, eax
0x1800381a9  js      short loc_1800381E4
0x1800381ab  mov     rax, [rbp+57h+var_A0]
0x1800381af  mov     qword ptr [rbp+57h+length], rax
0x1800381b3  lea     rcx, [rbp+57h+var_B0]
0x1800381b7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800381bc  lea     r8, [rbp+57h+var_80]
0x1800381c0  lea     rdx, [rbp+57h+length]
0x1800381c4  lea     rcx, [rbp+57h+var_B0]
0x1800381c8  call    ??$MakeAndInitialize@VCtacJsonData@@V1@PEAUIJsonObject@Json@Data@Windows@@AEAPEAV1@@Details@WRL@Microsoft@@YAJPEAPEAVCtacJsonData@@$$QEAPEAUIJsonObject@Json@Data@Windows@@AEAPEAV3@@Z; Microsoft::WRL::Details::MakeAndInitialize<CtacJsonData,CtacJsonData,Windows::Data::Json::IJsonObject *,CtacJsonData * &>(CtacJsonData * *,Windows::Data::Json::IJsonObject * &&,CtacJsonData * &)
0x1800381cd  mov     ebx, eax
0x1800381cf  test    eax, eax
0x1800381d1  jns     loc_1800382A3
0x1800381d7  mov     r9d, eax
0x1800381da  mov     edx, 303h
0x1800381df  jmp     loc_1800382FF
0x1800381e4  cmp     ebx, 8000000Eh
0x1800381ea  jnz     loc_1800382F7
0x1800381f0  mov     qword ptr [rbp+57h+length], r12
0x1800381f4  mov     rdi, [rbp+57h+var_A8]
0x1800381f8  mov     rax, [rdi]
0x1800381fb  mov     rbx, [rax+48h]
0x1800381ff  xor     ecx, ecx; string
0x180038201  call    cs:__imp_WindowsDeleteString
0x180038207  mov     qword ptr [rbp+57h+length], r12
0x18003820b  mov     [rbp+57h+var_60], r12
0x18003820f  mov     r9d, esi; unsigned int
0x180038212  mov     r8d, 18h; unsigned int
0x180038218  lea     rdx, ?c_szCtacOneSettingsValue@ClientAttributes@Flighting@Internal@Windows@@0QBGB; "CTACTARGETINGATTRIBUTES"
0x18003821f  lea     rcx, [rbp+57h+var_78]; hstringHeader
0x180038223  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180038228  nop
0x180038229  lea     r8, [rbp+57h+length]
0x18003822d  mov     rdx, [rbp+57h+var_60]
0x180038231  mov     rcx, rdi
0x180038234  mov     rax, rbx
0x180038237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003823c  mov     ebx, eax
0x18003823e  test    eax, eax
0x180038240  jns     short loc_180038249
0x180038242  mov     edx, 30Ch
0x180038247  jmp     short loc_180038275
0x180038249  xor     edx, edx; length
0x18003824b  mov     rcx, qword ptr [rbp+57h+length]; string
0x18003824f  call    cs:__imp_WindowsGetStringRawBuffer
0x180038255  mov     qword ptr [rbp+57h+var_88], rax
0x180038259  lea     r8, [rbp+57h+var_80]
0x18003825d  lea     rdx, [rbp+57h+var_88]
0x180038261  lea     rcx, [rbp+57h+var_B0]
0x180038265  call    ??$MakeAndInitialize@VCtacJsonData@@V1@PEBGAEAPEAV1@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCtacJsonData@@@WRL@Microsoft@@@012@$$QEAPEBGAEAPEAVCtacJsonData@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CtacJsonData,CtacJsonData,ushort const *,CtacJsonData * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CtacJsonData>>,ushort const * &&,CtacJsonData * &)
0x18003826a  mov     ebx, eax
0x18003826c  test    eax, eax
0x18003826e  jns     short loc_180038299
0x180038270  mov     edx, 30Fh; void *
0x180038275  mov     r9d, eax; char *
0x180038278  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x18003827f  mov     rcx, [rbp+5Fh]; this
0x180038283  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038288  nop
0x180038289  mov     rcx, qword ptr [rbp+57h+length]; string
0x18003828d  call    cs:__imp_WindowsDeleteString
0x180038293  mov     qword ptr [rbp+57h+length], r12
0x180038297  jmp     short loc_180038310
0x180038299  mov     rcx, qword ptr [rbp+57h+length]; string
0x18003829d  call    cs:__imp_WindowsDeleteString
0x1800382a3  mov     rbx, [rbp+57h+string]
0x1800382a7  mov     [rbp+57h+string], r12
0x1800382ab  mov     rcx, [r14]; string
0x1800382ae  call    cs:__imp_WindowsDeleteString
0x1800382b4  mov     [r14], rbx
0x1800382b7  mov     rdx, [rbp+57h+var_B0]
0x1800382bb  mov     [rbp+57h+var_B0], r12
0x1800382bf  mov     rcx, r15
0x1800382c2  call    ?Attach@?$ComPtr@VCFlightStore@@@WRL@Microsoft@@QEAAXPEAVCFlightStore@@@Z; Microsoft::WRL::ComPtr<CFlightStore>::Attach(CFlightStore *)
0x1800382c7  nop
0x1800382c8  lea     rcx, [rbp+57h+var_A0]
0x1800382cc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800382d1  nop
0x1800382d2  lea     rcx, [rbp+57h+var_B0]
0x1800382d6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800382db  nop
0x1800382dc  mov     rcx, [rbp+57h+string]; string
0x1800382e0  call    cs:__imp_WindowsDeleteString
0x1800382e6  mov     [rbp+57h+string], r12
0x1800382ea  lea     rcx, [rbp+57h+var_A8]
0x1800382ee  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800382f3  xor     eax, eax
0x1800382f5  jmp     short loc_18003833D
0x1800382f7  mov     r9d, ebx; char *
0x1800382fa  mov     edx, 313h; void *
0x1800382ff  lea     r8, aOnecoreBaseFli_48; "onecore\\base\\flighting\\flightsetting"...
0x180038306  mov     rcx, [rbp+5Fh]; this
0x18003830a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003830f  nop
0x180038310  lea     rcx, [rbp+57h+var_A0]
0x180038314  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180038319  nop
  ... truncated ...
```
