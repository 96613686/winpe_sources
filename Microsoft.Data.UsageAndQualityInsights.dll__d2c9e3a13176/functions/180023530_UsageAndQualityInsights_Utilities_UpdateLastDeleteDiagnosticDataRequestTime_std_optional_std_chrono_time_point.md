# UsageAndQualityInsights::Utilities::UpdateLastDeleteDiagnosticDataRequestTime(std::optional<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>)

- ea: `0x180023530`
- end: `0x180023695`
- name: `?UpdateLastDeleteDiagnosticDataRequestTime@Utilities@UsageAndQualityInsights@@YAXV?$optional@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@std@@@Z`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001573c`

## callees

- `0x1800033d0`
- `0x18000eee0`
- `0x180012940`
- `0x180016628`
- `0x180022de4`
- `0x1800233bc`
- `0x180023530`
- `0x1800238ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023622`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023635`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023635`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002362d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023662`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002362d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023662`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800235fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800235fb`

## string_xrefs

- `0x180023683`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180023649`: `LastDeleteDeviceRequestTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UsageAndQualityInsights::Utilities::UpdateLastDeleteDiagnosticDataRequestTime(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rcx
  int v3; // eax
  HKEY v4; // rbx
  HKEY v5; // rsi
  DWORD LastError; // edi
  DWORD dwOptions; // [rsp+20h] [rbp-49h]
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  int v9; // [rsp+58h] [rbp-11h]
  DWORD dwDisposition; // [rsp+5Ch] [rbp-Dh] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-9h] BYREF
  __int64 v12; // [rsp+68h] [rbp-1h] BYREF
  wchar_t v13[16]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v9 = 0;
  if ( *(_BYTE *)(a1 + 8) )
  {
    v1 = UsageAndQualityInsights::Utilities::TimePointToIso8601(v13);
    v12 = UsageAndQualityInsights::Utilities::PreciseUtc8601ToFileTime(v1);
    std::wstring::~wstring((char **)v13);
    hKey = 0;
    if ( (int)wil::reg::open_unique_key_nothrow(
                v2,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UsageAndQualityInsights",
                &hKey,
                1) >= 0 )
    {
      v4 = hKey;
    }
    else
    {
      v9 = 1;
      phkResult = 0;
      dwDisposition = 0;
      v3 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UsageAndQualityInsights",
             0,
             0,
             0,
             0xF003Fu,
             0,
             &phkResult,
             &dwDisposition);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      if ( v3 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v3,
          dwOptions);
      v4 = phkResult;
      v5 = hKey;
      if ( hKey )
      {
        LastError = GetLastError();
        RegCloseKey(v5);
        SetLastError(LastError);
      }
      hKey = v4;
    }
    wil::reg::set_value<unsigned __int64>(v4, L"LastDeleteDeviceRequestTime", &v12);
    if ( hKey )
      RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x180023530  push    rbp
0x180023532  push    rbx
0x180023533  push    rsi
0x180023534  push    rdi
0x180023535  lea     rbp, [rsp-3Fh]
0x18002353a  sub     rsp, 0A8h
0x180023541  mov     rax, cs:__security_cookie
0x180023548  xor     rax, rsp
0x18002354b  mov     [rbp+57h+var_30], rax
0x18002354f  mov     [rbp+57h+var_68], 0
0x180023556  cmp     byte ptr [rcx+8], 0
0x18002355a  jz      loc_180023668
0x180023560  mov     rdx, [rcx]
0x180023563  lea     rcx, [rbp+57h+var_50]; wchar_t *
0x180023567  call    ?TimePointToIso8601@Utilities@UsageAndQualityInsights@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@4@@Z; UsageAndQualityInsights::Utilities::TimePointToIso8601(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>)
0x18002356c  nop
0x18002356d  mov     rcx, rax
0x180023570  call    ?PreciseUtc8601ToFileTime@Utilities@UsageAndQualityInsights@@YA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UsageAndQualityInsights::Utilities::PreciseUtc8601ToFileTime(std::wstring const &)
0x180023575  mov     [rbp+57h+var_58], rax
0x180023579  lea     rcx, [rbp+57h+var_50]; void *
0x18002357d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023582  mov     [rbp+57h+hKey], 0
0x18002358a  mov     ebx, 1
0x18002358f  mov     r9d, ebx
0x180023592  lea     r8, [rbp+57h+hKey]
0x180023596  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002359d  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEB_WAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,wchar_t const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x1800235a2  test    eax, eax
0x1800235a4  jns     loc_180023641
0x1800235aa  mov     [rbp+57h+var_68], ebx
0x1800235ad  mov     [rbp+57h+var_60], 0
0x1800235b5  mov     [rbp+57h+dwDisposition], 0
0x1800235bc  lea     rax, [rbp+57h+dwDisposition]
0x1800235c0  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x1800235c5  lea     rax, [rbp+57h+var_60]
0x1800235c9  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800235ce  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800235d7  mov     [rsp+0C0h+samDesired], 0F003Fh; samDesired
0x1800235df  mov     [rsp+0C0h+dwOptions], 0; int
0x1800235e7  xor     r9d, r9d; lpClass
0x1800235ea  xor     r8d, r8d; Reserved
0x1800235ed  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800235f4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800235fb  call    cs:__imp_RegCreateKeyExW
0x180023601  test    eax, eax
0x180023603  jle     short loc_18002360D
0x180023605  movzx   eax, ax
0x180023608  or      eax, 80070000h
0x18002360d  mov     rcx, [rbp+5Fh]; this
0x180023611  test    eax, eax
0x180023613  js      short loc_180023680
0x180023615  mov     rbx, [rbp+57h+var_60]
0x180023619  mov     rsi, [rbp+57h+hKey]
0x18002361d  test    rsi, rsi
0x180023620  jz      short loc_18002363B
0x180023622  call    cs:__imp_GetLastError
0x180023628  mov     edi, eax
0x18002362a  mov     rcx, rsi; hKey
0x18002362d  call    cs:__imp_RegCloseKey
0x180023633  mov     ecx, edi; dwErrCode
0x180023635  call    cs:__imp_SetLastError
0x18002363b  mov     [rbp+57h+hKey], rbx
0x18002363f  jmp     short loc_180023645
0x180023641  mov     rbx, [rbp+57h+hKey]
0x180023645  lea     r8, [rbp+57h+var_58]
0x180023649  lea     rdx, aLastdeletedevi; "LastDeleteDeviceRequestTime"
0x180023650  mov     rcx, rbx
0x180023653  call    ??$set_value@_K@reg@wil@@YAXPEAUHKEY__@@PEB_WAEB_K@Z; wil::reg::set_value<unsigned __int64>(HKEY__ *,wchar_t const *,unsigned __int64 const &)
0x180023658  nop
0x180023659  mov     rcx, [rbp+57h+hKey]; hKey
0x18002365d  test    rcx, rcx
0x180023660  jz      short loc_180023668
0x180023662  call    cs:__imp_RegCloseKey
0x180023668  mov     rcx, [rbp+57h+var_30]
0x18002366c  xor     rcx, rsp; StackCookie
0x18002366f  call    __security_check_cookie
0x180023674  add     rsp, 0A8h
0x18002367b  pop     rdi
0x18002367c  pop     rsi
0x18002367d  pop     rbx
0x18002367e  pop     rbp
0x18002367f  retn
0x180023680  mov     r9d, eax; char *
0x180023683  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002368a  mov     edx, 1CBEh; void *
0x18002368f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
