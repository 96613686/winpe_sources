# CloudPrint::CloudPrintHelper::GetMpsCachedState(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool *)

- ea: `0x180014de4`
- end: `0x1800154f6`
- name: `?GetMpsCachedState@CloudPrintHelper@CloudPrint@@IEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEA_N@Z`
- size: `1810`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001963c`

## callees

- `0x180003a60`
- `0x180007468`
- `0x180009264`
- `0x18000e208`
- `0x18000f87c`
- `0x18000f8b4`
- `0x180012700`
- `0x180012bc0`
- `0x180012bfc`
- `0x180014de4`
- `0x1800169f4`
- `0x18001a404`
- `0x18001bfe4`
- `0x18001c0a8`
- `0x18001c298`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014ef4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180014ef4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015018`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015018`

## string_xrefs

- `0x180015083`: `https://graph.microsoft.com/v1.0`
- `0x180014e2e`: `GetMpsCachedState`
- `0x180014e95`: `No MPS Cached state.`
- `0x18001549e`: `No MPS Cached state.`
- `0x180014e9c`: `CloudPrint::CloudPrintHelper::GetMpsCachedState`
- `0x180014ecb`: `CloudPrint::CloudPrintHelper::GetMpsCachedState`
- `0x1800154a5`: `CloudPrint::CloudPrintHelper::GetMpsCachedState`
- `0x180014f7f`: `We have cached state but not timestamp low.`
- `0x180014fd2`: `We have cached state but not timestamp high.`
- `0x1800150c5`: `We have cached state but not OAuthAuthority.`
- `0x18001511d`: `MPS Cached state for different MPS config. Returning no Cache.`
- `0x1800151f0`: `MPS Cached state for different MPS config. Returning no Cache.`
- `0x1800152df`: `MPS Cached state for different MPS config. Returning no Cache.`
- `0x18001518a`: `We have cached state but not MSGraphResourceId.`
- `0x18001526b`: `We have cached state but not MSGraphBaseUrl.`
- `0x180015389`: `We have cached state but not discovery endpoint.`
- `0x180015472`: `MPS cache expired.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CloudPrint::CloudPrintHelper::GetMpsCachedState(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5)
{
  HKEY v8; // rax
  HKEY v9; // rbx
  unsigned int DwordValue; // esi
  unsigned int v12; // r14d
  unsigned int v13; // r14d
  unsigned int v14; // eax
  unsigned __int64 v15; // rdx
  char v16; // r14
  char v17; // r13
  char v18; // r12
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 StringValue; // rax
  bool v24; // [rsp+30h] [rbp-158h] BYREF
  HKEY v25; // [rsp+38h] [rbp-150h] BYREF
  HKEY v26; // [rsp+40h] [rbp-148h] BYREF
  __int64 v27; // [rsp+48h] [rbp-140h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-138h] BYREF
  __int64 v29; // [rsp+58h] [rbp-130h]
  __int64 v30; // [rsp+60h] [rbp-128h]
  _BYTE *v31; // [rsp+68h] [rbp-120h]
  _BYTE v32[80]; // [rsp+70h] [rbp-118h] BYREF
  _BYTE v33[32]; // [rsp+C0h] [rbp-C8h] BYREF
  _BYTE v34[32]; // [rsp+E0h] [rbp-A8h] BYREF
  _BYTE v35[32]; // [rsp+100h] [rbp-88h] BYREF
  _BYTE v36[32]; // [rsp+120h] [rbp-68h] BYREF

  v30 = a4;
  v27 = a3;
  v29 = a2;
  v31 = a5;
  CloudPrintHelperTelemetry::WatchCurrentThread(v32, "GetMpsCachedState");
  *a5 = 0;
  v24 = 0;
  v8 = (HKEY)CloudPrint::CloudPrintHelper::OpenCurrentUserMpsRegKey(a1, 1, 0, 0x20019u);
  v9 = v8;
  v26 = v8;
  if ( v8 )
  {
    v25 = v8;
    DwordValue = PrintCore::RegHelpers::GetDwordValue(&v25, 0, L"State", &v24);
    if ( !v24 )
    {
      CloudPrintHelperTelemetry::WriteDbgTraceInfo(
        "CloudPrint::CloudPrintHelper::GetMpsCachedState",
        L"No MPS Cached state.");
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
      return 2147745798LL;
    }
    v12 = 0;
    while ( DwordValue == 1 )
    {
      if ( v12 >= *(_DWORD *)(a1 + 320) )
        goto LABEL_9;
      CloudPrintHelperTelemetry::WriteDbgTraceInfo(
        "CloudPrint::CloudPrintHelper::GetMpsCachedState",
        L"MPS state is InProgress, waiting...");
      Sleep(0x3E8u);
      ++v12;
      v25 = v9;
      DwordValue = PrintCore::RegHelpers::GetDwordValue(&v25, 0, L"State", &v24);
    }
    if ( DwordValue - 3 > 1 )
    {
LABEL_9:
      CloudPrintHelperTelemetry::WriteDbgTraceInfo(
        "CloudPrint::CloudPrintHelper::GetMpsCachedState",
        L"MPS state is not determined. State: %u",
        DwordValue);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
      return 2147745798LL;
    }
    v25 = v9;
    v13 = PrintCore::RegHelpers::GetDwordValue(&v25, 0, L"TimestampLow", &v24);
    if ( !v24 )
    {
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::GetMpsCachedState",
        L"We have cached state but not timestamp low.");
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
      return 2147745798LL;
    }
    v25 = v9;
    v14 = PrintCore::RegHelpers::GetDwordValue(&v25, 0, L"TimestampHigh", &v24);
    if ( !v24 )
    {
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::GetMpsCachedState",
        L"We have cached state but not timestamp high.");
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
      return 2147745798LL;
    }
    v25 = (HKEY)__PAIR64__(v14, v13);
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v15 = (*(_QWORD *)&SystemTimeAsFileTime - (_QWORD)v25) / 0x989680uLL;
    if ( DwordValue == 3 && v15 < *(_QWORD *)(a1 + 304) || DwordValue == 4 && v15 < *(_QWORD *)(a1 + 312) )
    {
      v16 = std::operator!=<unsigned short>(a2, L"organizations");
      v17 = std::operator!=<unsigned short>(v27, L"00000003-0000-0000-c000-000000000000");
      v18 = std::operator!=<unsigned short>(a4, L"https://graph.microsoft.com/v1.0");
      v25 = v9;
      PrintCore::RegHelpers::GetStringValue(v33, &v25, v19, L"OAuthAuthority");
      if ( !v24 )
      {
        CloudPrintHelperTelemetry::WriteDbgTraceWarning(
          "CloudPrint::CloudPrintHelper::GetMpsCachedState",
          L"We have cached state but not OAuthAuthority.");
        std::wstring::_Tidy_deallocate(v33);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
        wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
        return 2147745798LL;
      }
      if ( v16 && (unsigned __int8)std::operator!=<unsigned short>(v29, v33) )
      {
        CloudPrintHelperTelemetry::WriteDbgTraceInfo(
          "CloudPrint::CloudPrintHelper::GetMpsCachedState",
          L"MPS Cached state for different MPS config. Returning no Cache.");
        std::wstring::_Tidy_deallocate(v33);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
        wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
        return 2147745798LL;
      }
      v25 = v9;
      PrintCore::RegHelpers::GetStringValue(v34, &v25, v20, L"MSGraphResourceId");
      if ( !v24 )
      {
        CloudPrintHelperTelemetry::WriteDbgTraceWarning(
          "CloudPrint::CloudPrintHelper::GetMpsCachedState",
          L"We have cached state but not MSGraphResourceId.");
        std::wstring::_Tidy_deallocate(v34);
        std::wstring::_Tidy_deallocate(v33);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
        wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
        return 2147745798LL;
      }
      if ( v17 && (unsigned __int8)std::operator!=<unsigned short>(v27, v34) )
      {
        CloudPrintHelperTelemetry::WriteDbgTraceInfo(
          "CloudPrint::CloudPrintHelper::GetMpsCachedState",
          L"MPS Cached state for different MPS config. Returning no Cache.");
        std::wstring::_Tidy_deallocate(v34);
        std::wstring::_Tidy_deallocate(v33);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
        wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
        return 2147745798LL;
      }
      v25 = v9;
      PrintCore::RegHelpers::GetStringValue(v35, &v25, v21, L"MSGraphBaseUrl");
      if ( !v24 )
      {
        CloudPrintHelperTelemetry::WriteDbgTraceWarning(
          "CloudPrint::CloudPrintHelper::GetMpsCachedState",
          L"We have cached state but not MSGraphBaseUrl.");
        std::wstring::_Tidy_deallocate(v35);
        std::wstring::_Tidy_deallocate(v34);
        std::wstring::_Tidy_deallocate(v33);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
        wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
        return 2147745798LL;
      }
      if ( v18 && (unsigned __int8)std::operator!=<unsigned short>(v30, v35) )
      {
        CloudPrintHelperTelemetry::WriteDbgTraceInfo(
          "CloudPrint::CloudPrintHelper::GetMpsCachedState",
          L"MPS Cached state for different MPS config. Returning no Cache.");
        std::wstring::_Tidy_deallocate(v35);
        std::wstring::_Tidy_deallocate(v34);
        std::wstring::_Tidy_deallocate(v33);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
        wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
        return 2147745798LL;
      }
      if ( DwordValue == 4 )
      {
        v25 = v9;
        StringValue = PrintCore::RegHelpers::GetStringValue(v36, &v25, v22, L"DiscoveryEndpoint");
        std::wstring::operator=(a1 + 40, StringValue);
        std::wstring::_Tidy_deallocate(v36);
        if ( !v24 )
        {
          CloudPrintHelperTelemetry::WriteDbgTraceWarning(
            "CloudPrint::CloudPrintHelper::GetMpsCachedState",
            L"We have cached state but not discovery endpoint.");
          std::wstring::_Tidy_deallocate(v35);
          std::wstring::_Tidy_deallocate(v34);
          std::wstring::_Tidy_deallocate(v33);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
          wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
          return 2147745798LL;
        }
        if ( !v16 )
          std::wstring::operator=(v29, v33);
        if ( !v17 )
          std::wstring::operator=(v27, v34);
        if ( !v18 )
          std::wstring::operator=(v30, v35);
        *v31 = 1;
      }
      std::wstring::_Tidy_deallocate(v35);
      std::wstring::_Tidy_deallocate(v34);
      std::wstring::_Tidy_deallocate(v33);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
      return 0;
    }
    else
    {
      CloudPrintHelperTelemetry::WriteDbgTraceInfo(
        "CloudPrint::CloudPrintHelper::GetMpsCachedState",
        L"MPS cache expired.");
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
      return 2147745798LL;
    }
  }
  else
  {
    CloudPrintHelperTelemetry::WriteDbgTraceInfo(
      "CloudPrint::CloudPrintHelper::GetMpsCachedState",
      L"No MPS Cached state.");
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v32);
    return 2147745798LL;
  }
}

```

## disassembly

```asm
0x180014de4  push    rbx
0x180014de6  push    rsi
0x180014de7  push    rdi
0x180014de8  push    r12
0x180014dea  push    r13
0x180014dec  push    r14
0x180014dee  push    r15
0x180014df0  sub     rsp, 150h
0x180014df7  mov     rax, cs:__security_cookie
0x180014dfe  xor     rax, rsp
0x180014e01  mov     [rsp+188h+var_48], rax
0x180014e09  mov     r12, r9
0x180014e0c  mov     [rsp+188h+var_128], r9
0x180014e11  mov     [rsp+188h+var_140], r8
0x180014e16  mov     r13, rdx
0x180014e19  mov     [rsp+188h+var_130], rdx
0x180014e1e  mov     r15, rcx
0x180014e21  mov     rbx, [rsp+188h+arg_20]
0x180014e29  mov     [rsp+188h+var_120], rbx
0x180014e2e  lea     rdx, aGetmpscachedst; "GetMpsCachedState"
0x180014e35  lea     rcx, [rsp+188h+var_118]
0x180014e3a  call    ?WatchCurrentThread@CloudPrintHelperTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CloudPrintHelperTelemetry::WatchCurrentThread(char const *)
0x180014e3f  nop
0x180014e40  xor     edi, edi
0x180014e42  mov     [rbx], dil
0x180014e45  mov     [rsp+188h+var_158], dil
0x180014e4a  mov     r9d, 20019h
0x180014e50  xor     r8d, r8d
0x180014e53  lea     edx, [rdi+1]
0x180014e56  mov     rcx, r15
0x180014e59  call    ?OpenCurrentUserMpsRegKey@CloudPrintHelper@CloudPrint@@IEAAPEAUHKEY__@@W4MpsRegKey@2@_NK@Z; CloudPrint::CloudPrintHelper::OpenCurrentUserMpsRegKey(CloudPrint::MpsRegKey,bool,ulong)
0x180014e5e  mov     rbx, rax
0x180014e61  mov     [rsp+188h+var_148], rax
0x180014e66  test    rax, rax
0x180014e69  jz      loc_18001549E
0x180014e6f  mov     [rsp+188h+var_150], rax
0x180014e74  lea     r9, [rsp+188h+var_158]; bool *
0x180014e79  lea     r8, ValueName; "State"
0x180014e80  xor     edx, edx; unsigned __int16 *
0x180014e82  lea     rcx, [rsp+188h+var_150]; HKEY *
0x180014e87  call    ?GetDwordValue@RegHelpers@PrintCore@@SAKAEBQEAUHKEY__@@PEBG1PEA_N@Z; PrintCore::RegHelpers::GetDwordValue(HKEY__ * const &,ushort const *,ushort const *,bool *)
0x180014e8c  mov     esi, eax
0x180014e8e  cmp     [rsp+188h+var_158], dil
0x180014e93  jnz     short loc_180014EC8
0x180014e95  lea     rdx, aNoMpsCachedSta; "No MPS Cached state."
0x180014e9c  lea     rcx, aCloudprintClou_7; "CloudPrint::CloudPrintHelper::GetMpsCac"...
0x180014ea3  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014ea8  nop
0x180014ea9  lea     rcx, [rsp+188h+var_148]
0x180014eae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180014eb3  nop
0x180014eb4  lea     rcx, [rsp+188h+var_118]; this
0x180014eb9  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180014ebe  mov     eax, 80040006h
0x180014ec3  jmp     loc_1800154D2
0x180014ec8  mov     r14d, edi
0x180014ecb  lea     rdi, aCloudprintClou_7; "CloudPrint::CloudPrintHelper::GetMpsCac"...
0x180014ed2  cmp     esi, 1
0x180014ed5  jnz     short loc_180014F1E
0x180014ed7  cmp     r14d, [r15+140h]
0x180014ede  jnb     short loc_180014F26
0x180014ee0  lea     rdx, aMpsStateIsInpr; "MPS state is InProgress, waiting..."
0x180014ee7  mov     rcx, rdi; char *
0x180014eea  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014eef  mov     ecx, 3E8h; dwMilliseconds
0x180014ef4  call    cs:__imp_Sleep
0x180014efa  inc     r14d
0x180014efd  mov     [rsp+188h+var_150], rbx
0x180014f02  lea     r9, [rsp+188h+var_158]; bool *
0x180014f07  lea     r8, ValueName; "State"
0x180014f0e  xor     edx, edx; unsigned __int16 *
0x180014f10  lea     rcx, [rsp+188h+var_150]; HKEY *
0x180014f15  call    ?GetDwordValue@RegHelpers@PrintCore@@SAKAEBQEAUHKEY__@@PEBG1PEA_N@Z; PrintCore::RegHelpers::GetDwordValue(HKEY__ * const &,ushort const *,ushort const *,bool *)
0x180014f1a  mov     esi, eax
0x180014f1c  jmp     short loc_180014ED2
0x180014f1e  lea     eax, [rsi-3]
0x180014f21  cmp     eax, 1
0x180014f24  jbe     short loc_180014F58
0x180014f26  mov     r8d, esi
0x180014f29  lea     rdx, aMpsStateIsNotD; "MPS state is not determined. State: %u"
0x180014f30  mov     rcx, rdi; char *
0x180014f33  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014f38  nop
0x180014f39  lea     rcx, [rsp+188h+var_148]
0x180014f3e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180014f43  nop
0x180014f44  lea     rcx, [rsp+188h+var_118]; this
0x180014f49  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180014f4e  mov     eax, 80040006h
0x180014f53  jmp     loc_1800154D2
0x180014f58  mov     [rsp+188h+var_150], rbx
0x180014f5d  lea     r9, [rsp+188h+var_158]; bool *
0x180014f62  lea     r8, aTimestamplow; "TimestampLow"
0x180014f69  xor     edx, edx; unsigned __int16 *
0x180014f6b  lea     rcx, [rsp+188h+var_150]; HKEY *
0x180014f70  call    ?GetDwordValue@RegHelpers@PrintCore@@SAKAEBQEAUHKEY__@@PEBG1PEA_N@Z; PrintCore::RegHelpers::GetDwordValue(HKEY__ * const &,ushort const *,ushort const *,bool *)
0x180014f75  mov     r14d, eax
0x180014f78  cmp     [rsp+188h+var_158], 0
0x180014f7d  jnz     short loc_180014FAE
0x180014f7f  lea     rdx, aWeHaveCachedSt_4; "We have cached state but not timestamp "...
0x180014f86  mov     rcx, rdi; char *
0x180014f89  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180014f8e  nop
0x180014f8f  lea     rcx, [rsp+188h+var_148]
0x180014f94  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180014f99  nop
0x180014f9a  lea     rcx, [rsp+188h+var_118]; this
0x180014f9f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180014fa4  mov     eax, 80040006h
0x180014fa9  jmp     loc_1800154D2
0x180014fae  mov     [rsp+188h+var_150], rbx
0x180014fb3  lea     r9, [rsp+188h+var_158]; bool *
0x180014fb8  lea     r8, aTimestamphigh; "TimestampHigh"
0x180014fbf  xor     edx, edx; unsigned __int16 *
0x180014fc1  lea     rcx, [rsp+188h+var_150]; HKEY *
0x180014fc6  call    ?GetDwordValue@RegHelpers@PrintCore@@SAKAEBQEAUHKEY__@@PEBG1PEA_N@Z; PrintCore::RegHelpers::GetDwordValue(HKEY__ * const &,ushort const *,ushort const *,bool *)
0x180014fcb  cmp     [rsp+188h+var_158], 0
0x180014fd0  jnz     short loc_180015001
0x180014fd2  lea     rdx, aWeHaveCachedSt_2; "We have cached state but not timestamp "...
0x180014fd9  mov     rcx, rdi; char *
0x180014fdc  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180014fe1  nop
0x180014fe2  lea     rcx, [rsp+188h+var_148]
0x180014fe7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180014fec  nop
0x180014fed  lea     rcx, [rsp+188h+var_118]; this
0x180014ff2  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180014ff7  mov     eax, 80040006h
0x180014ffc  jmp     loc_1800154D2
0x180015001  mov     dword ptr [rsp+188h+var_150], r14d
0x180015006  mov     dword ptr [rsp+188h+var_150+4], eax
0x18001500a  mov     qword ptr [rsp+188h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180015013  lea     rcx, [rsp+188h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180015018  call    cs:__imp_GetSystemTimeAsFileTime
0x18001501e  mov     rcx, qword ptr [rsp+188h+SystemTimeAsFileTime.dwLowDateTime]
0x180015023  sub     rcx, [rsp+188h+var_150]
0x180015028  mov     rax, 0D6BF94D5E57A42BDh
0x180015032  mul     rcx
0x180015035  shr     rdx, 17h
0x180015039  cmp     esi, 3
0x18001503c  jnz     short loc_180015047
0x18001503e  cmp     rdx, [r15+130h]
0x180015045  jb      short loc_18001505D
0x180015047  cmp     esi, 4
0x18001504a  jnz     loc_180015472
0x180015050  cmp     rdx, [r15+138h]
0x180015057  jnb     loc_180015472
0x18001505d  lea     rdx, aOrganizations; "organizations"
0x180015064  mov     rcx, r13
0x180015067  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x18001506c  mov     r14b, al
0x18001506f  lea     rdx, a00000003000000; "00000003-0000-0000-c000-000000000000"
0x180015076  mov     rcx, [rsp+188h+var_140]
0x18001507b  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x180015080  mov     r13b, al
0x180015083  lea     rdx, aHttpsGraphMicr_0; "https://graph.microsoft.com/v1.0"
0x18001508a  mov     rcx, r12
0x18001508d  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x180015092  mov     r12b, al
0x180015095  mov     [rsp+188h+var_150], rbx
0x18001509a  lea     rax, [rsp+188h+var_158]
0x18001509f  mov     [rsp+188h+var_160], rax
0x1800150a4  lea     r9, aOauthauthority; "OAuthAuthority"
0x1800150ab  lea     rdx, [rsp+188h+var_150]
0x1800150b0  lea     rcx, [rsp+188h+var_C8]
0x1800150b8  call    ?GetStringValue@RegHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAUHKEY__@@PEBG1KPEA_N@Z; PrintCore::RegHelpers::GetStringValue(HKEY__ * const &,ushort const *,ushort const *,ulong,bool *)
0x1800150bd  nop
0x1800150be  cmp     [rsp+188h+var_158], 0
0x1800150c3  jnz     short loc_180015102
0x1800150c5  lea     rdx, aWeHaveCachedSt; "We have cached state but not OAuthAutho"...
0x1800150cc  mov     rcx, rdi; char *
0x1800150cf  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800150d4  nop
0x1800150d5  lea     rcx, [rsp+188h+var_C8]
0x1800150dd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800150e2  nop
0x1800150e3  lea     rcx, [rsp+188h+var_148]
0x1800150e8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800150ed  nop
0x1800150ee  lea     rcx, [rsp+188h+var_118]; this
0x1800150f3  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800150f8  mov     eax, 80040006h
0x1800150fd  jmp     loc_1800154D2
0x180015102  test    r14b, r14b
0x180015105  jz      short loc_18001515A
0x180015107  lea     rdx, [rsp+188h+var_C8]
0x18001510f  mov     rcx, [rsp+188h+var_130]
0x180015114  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator!=<ushort>(std::wstring const &,std::wstring const &)
0x180015119  test    al, al
0x18001511b  jz      short loc_18001515A
0x18001511d  lea     rdx, aMpsCachedState; "MPS Cached state for different MPS conf"...
0x180015124  mov     rcx, rdi; char *
0x180015127  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001512c  nop
0x18001512d  lea     rcx, [rsp+188h+var_C8]
0x180015135  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001513a  nop
0x18001513b  lea     rcx, [rsp+188h+var_148]
0x180015140  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180015145  nop
0x180015146  lea     rcx, [rsp+188h+var_118]; this
0x18001514b  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180015150  mov     eax, 80040006h
0x180015155  jmp     loc_1800154D2
0x18001515a  mov     [rsp+188h+var_150], rbx
0x18001515f  lea     rax, [rsp+188h+var_158]
0x180015164  mov     [rsp+188h+var_160], rax
0x180015169  lea     r9, aMsgraphresourc; "MSGraphResourceId"
0x180015170  lea     rdx, [rsp+188h+var_150]
0x180015175  lea     rcx, [rsp+188h+var_A8]
0x18001517d  call    ?GetStringValue@RegHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAUHKEY__@@PEBG1KPEA_N@Z; PrintCore::RegHelpers::GetStringValue(HKEY__ * const &,ushort const *,ushort const *,ulong,bool *)
0x180015182  nop
0x180015183  cmp     [rsp+188h+var_158], 0
0x180015188  jnz     short loc_1800151D5
0x18001518a  lea     rdx, aWeHaveCachedSt_3; "We have cached state but not MSGraphRes"...
0x180015191  mov     rcx, rdi; char *
0x180015194  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180015199  nop
0x18001519a  lea     rcx, [rsp+188h+var_A8]
0x1800151a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800151a7  nop
0x1800151a8  lea     rcx, [rsp+188h+var_C8]
0x1800151b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800151b5  nop
0x1800151b6  lea     rcx, [rsp+188h+var_148]
0x1800151bb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800151c0  nop
0x1800151c1  lea     rcx, [rsp+188h+var_118]; this
0x1800151c6  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800151cb  mov     eax, 80040006h
0x1800151d0  jmp     loc_1800154D2
0x1800151d5  test    r13b, r13b
0x1800151d8  jz      short loc_18001523B
0x1800151da  lea     rdx, [rsp+188h+var_A8]
0x1800151e2  mov     rcx, [rsp+188h+var_140]
0x1800151e7  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator!=<ushort>(std::wstring const &,std::wstring const &)
0x1800151ec  test    al, al
0x1800151ee  jz      short loc_18001523B
0x1800151f0  lea     rdx, aMpsCachedState; "MPS Cached state for different MPS conf"...
0x1800151f7  mov     rcx, rdi; char *
0x1800151fa  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800151ff  nop
0x180015200  lea     rcx, [rsp+188h+var_A8]
0x180015208  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001520d  nop
0x18001520e  lea     rcx, [rsp+188h+var_C8]
0x180015216  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001521b  nop
0x18001521c  lea     rcx, [rsp+188h+var_148]
0x180015221  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180015226  nop
0x180015227  lea     rcx, [rsp+188h+var_118]; this
0x18001522c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180015231  mov     eax, 80040006h
0x180015236  jmp     loc_1800154D2
0x18001523b  mov     [rsp+188h+var_150], rbx
0x180015240  lea     rax, [rsp+188h+var_158]
0x180015245  mov     [rsp+188h+var_160], rax
0x18001524a  lea     r9, aMsgraphbaseurl; "MSGraphBaseUrl"
0x180015251  lea     rdx, [rsp+188h+var_150]
0x180015256  lea     rcx, [rsp+188h+var_88]
0x18001525e  call    ?GetStringValue@RegHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAUHKEY__@@PEBG1KPEA_N@Z; PrintCore::RegHelpers::GetStringValue(HKEY__ * const &,ushort const *,ushort const *,ulong,bool *)
0x180015263  nop
0x180015264  cmp     [rsp+188h+var_158], 0
0x180015269  jnz     short loc_1800152C4
0x18001526b  lea     rdx, aWeHaveCachedSt_0; "We have cached state but not MSGraphBas"...
0x180015272  mov     rcx, rdi; char *
0x180015275  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001527a  nop
0x18001527b  lea     rcx, [rsp+188h+var_88]
0x180015283  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015288  nop
0x180015289  lea     rcx, [rsp+188h+var_A8]
0x180015291  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015296  nop
0x180015297  lea     rcx, [rsp+188h+var_C8]
0x18001529f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800152a4  nop
0x1800152a5  lea     rcx, [rsp+188h+var_148]
0x1800152aa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800152af  nop
0x1800152b0  lea     rcx, [rsp+188h+var_118]; this
0x1800152b5  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800152ba  mov     eax, 80040006h
0x1800152bf  jmp     loc_1800154D2
0x1800152c4  test    r12b, r12b
0x1800152c7  jz      short loc_180015338
0x1800152c9  lea     rdx, [rsp+188h+var_88]
0x1800152d1  mov     rcx, [rsp+188h+var_128]
0x1800152d6  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator!=<ushort>(std::wstring const &,std::wstring const &)
0x1800152db  test    al, al
0x1800152dd  jz      short loc_180015338
0x1800152df  lea     rdx, aMpsCachedState; "MPS Cached state for different MPS conf"...
0x1800152e6  mov     rcx, rdi; char *
0x1800152e9  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800152ee  nop
0x1800152ef  lea     rcx, [rsp+188h+var_88]
0x1800152f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800152fc  nop
0x1800152fd  lea     rcx, [rsp+188h+var_A8]
  ... truncated ...
```
