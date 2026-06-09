# GetConcurrentInstallsFromOneSettings(void)

- ea: `0x18003b9a8`
- end: `0x18003bdb5`
- name: `?GetConcurrentInstallsFromOneSettings@@YAJXZ`
- size: `1037`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180048108`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001c414`
- `0x1800252e8`
- `0x180034328`
- `0x18003b9a8`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003bca5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003bcc6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003bca5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003bcc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bae6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003baf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bbad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bbe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bc54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bc64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bd20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bd30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bd59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bd6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ba45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bae6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003baf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bbad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bbe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bc54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bc64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bd20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bd30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bd59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bd6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bc92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bcb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bc92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bcb8`

## string_xrefs

- `0x18003ba1e`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003bacf`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003bb86`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003bc3d`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003bd0b`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003ba94`: `SCCINSTALLSVC`
- `0x18003bb4b`: `CONCURRENTDEFAULTINSTALLS`
- `0x18003bc02`: `CONCURRENTMININSTALLS`
- `0x18003bcea`: `oneSettingsconcurrentDefaultInstalls = %d, oneSettingsconcurrentMinInstalls = %d`
- `0x18003bcfe`: `GetConcurrentInstallsFromOneSettings`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 GetConcurrentInstallsFromOneSettings(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  __int64 result; // rax
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64, __int64 *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, HSTRING *); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64, HSTRING *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  const wchar_t *StringRawBuffer; // rax
  const wchar_t *v17; // rax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-88h]
  int v20; // [rsp+40h] [rbp-68h]
  int v21; // [rsp+48h] [rbp-60h]
  HSTRING string; // [rsp+50h] [rbp-58h] BYREF
  HSTRING v23; // [rsp+58h] [rbp-50h] BYREF
  __int64 v24; // [rsp+60h] [rbp-48h] BYREF
  __int64 v25; // [rsp+68h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-38h] BYREF
  __int64 v27; // [rsp+88h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v25 = 0;
  v24 = 0;
  v23 = 0;
  string = 0;
  v27 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
    0x3Au,
    0x39u);
  v0 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(
         v27,
         &v25);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v3 = v25;
    v4 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v25 + 48LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
    v27 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SCCINSTALLSVC", 0xEu, 0xDu);
    try
    {
      v5 = v4(v3, v27, &v24);
      v6 = v5;
      if ( v5 >= 0 )
      {
        v8 = v24;
        v9 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v24 + 72LL);
        WindowsDeleteString(v23);
        v23 = 0;
        v27 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"CONCURRENTDEFAULTINSTALLS",
          0x1Au,
          0x19u);
        v10 = v9(v8, v27, &v23);
        v11 = v10;
        if ( v10 >= 0 )
        {
          v12 = v24;
          v13 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v24 + 72LL);
          WindowsDeleteString(string);
          string = 0;
          v27 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"CONCURRENTMININSTALLS",
            0x16u,
            0x15u);
          v14 = v13(v12, v27, &string);
          v15 = v14;
          if ( v14 >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(v23, 0);
            dword_1802CA63C = wcstoul(StringRawBuffer, 0, 10);
            v17 = WindowsGetStringRawBuffer(string, 0);
            dword_1802CA638 = wcstoul(v17, 0, 10);
            v21 = dword_1802CA638;
            v20 = dword_1802CA63C;
            LogMessage(
              4u,
              "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              0x30Fu,
              "GetConcurrentInstallsFromOneSettings",
              -1,
              L"oneSettingsconcurrentDefaultInstalls = %d, oneSettingsconcurrentMinInstalls = %d",
              0,
              0,
              v20,
              v21);
            WindowsDeleteString(string);
            string = 0;
            WindowsDeleteString(v23);
            v23 = 0;
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x30A,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              (const char *)(unsigned int)v14,
              v19);
            WindowsDeleteString(string);
            string = 0;
            WindowsDeleteString(v23);
            v23 = 0;
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
            result = v15;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x309,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
            (const char *)(unsigned int)v10,
            v19);
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v23);
          v23 = 0;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
          result = v11;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x307,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          (const char *)(unsigned int)v5,
          v19);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v23);
        v23 = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
        result = v6;
      }
    }
    catch ( ... )
    {
      v18 = wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x313,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              v7);
      LogSimpleMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        0x313u,
        "GetConcurrentInstallsFromOneSettings",
        v18,
        L"Exception while fetching onesettings for concurrent installs",
        0,
        0);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v23);
      v23 = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
      return 2147500037LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x306,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      (const char *)(unsigned int)v0,
      v19);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v23);
    v23 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v24);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x18003b9a8  mov     r11, rsp
0x18003b9ab  mov     [r11+8], rbx
0x18003b9af  mov     [r11+10h], rsi
0x18003b9b3  push    rdi
0x18003b9b4  sub     rsp, 0A0h
0x18003b9bb  mov     rax, cs:__security_cookie
0x18003b9c2  xor     rax, rsp
0x18003b9c5  mov     [rsp+0A8h+var_18], rax
0x18003b9cd  xor     esi, esi
0x18003b9cf  mov     [r11-40h], rsi
0x18003b9d3  mov     [r11-48h], rsi
0x18003b9d7  mov     [r11-50h], rsi
0x18003b9db  mov     [r11-58h], rsi
0x18003b9df  mov     [r11-20h], rsi
0x18003b9e3  lea     r9d, [rsi+39h]; unsigned int
0x18003b9e7  lea     r8d, [rsi+3Ah]; unsigned int
0x18003b9eb  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18003b9f2  lea     rcx, [r11-38h]; hstringHeader
0x18003b9f6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003b9fb  lea     rdx, [rsp+0A8h+var_40]
0x18003ba00  mov     rcx, [rsp+0A8h+var_20]
0x18003ba08  call    ??$GetActivationFactory@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>)
0x18003ba0d  mov     ebx, eax
0x18003ba0f  test    eax, eax
0x18003ba11  jns     short loc_18003BA6C
0x18003ba13  mov     rcx, [rsp+0A8h]; this
0x18003ba1b  mov     r9d, eax; char *
0x18003ba1e  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003ba25  mov     edx, 306h; void *
0x18003ba2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ba2f  nop
0x18003ba30  mov     rcx, [rsp+0A8h+string]; string
0x18003ba35  call    cs:__imp_WindowsDeleteString
0x18003ba3b  mov     [rsp+0A8h+string], rsi
0x18003ba40  mov     rcx, [rsp+0A8h+var_50]; string
0x18003ba45  call    cs:__imp_WindowsDeleteString
0x18003ba4b  mov     [rsp+0A8h+var_50], rsi
0x18003ba50  lea     rcx, [rsp+0A8h+var_48]
0x18003ba55  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003ba5a  nop
0x18003ba5b  lea     rcx, [rsp+0A8h+var_40]
0x18003ba60  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003ba65  mov     eax, ebx
0x18003ba67  jmp     loc_18003BD90
0x18003ba6c  mov     rdi, [rsp+0A8h+var_40]
0x18003ba71  mov     rax, [rdi]
0x18003ba74  mov     rbx, [rax+30h]
0x18003ba78  lea     rcx, [rsp+0A8h+var_48]
0x18003ba7d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003ba82  mov     [rsp+0A8h+var_20], rsi
0x18003ba8a  mov     r9d, 0Dh; unsigned int
0x18003ba90  lea     r8d, [r9+1]; unsigned int
0x18003ba94  lea     rdx, aSccinstallsvc; "SCCINSTALLSVC"
0x18003ba9b  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x18003baa0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003baa5  nop
0x18003baa6  lea     r8, [rsp+0A8h+var_48]
0x18003baab  mov     rdx, [rsp+0A8h+var_20]
0x18003bab3  mov     rcx, rdi
0x18003bab6  mov     rax, rbx
0x18003bab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003babe  mov     ebx, eax
0x18003bac0  test    eax, eax
0x18003bac2  jns     short loc_18003BB1D
0x18003bac4  mov     rcx, [rsp+0A8h]; this
0x18003bacc  mov     r9d, eax; char *
0x18003bacf  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003bad6  mov     edx, 307h; void *
0x18003badb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bae0  nop
0x18003bae1  mov     rcx, [rsp+0A8h+string]; string
0x18003bae6  call    cs:__imp_WindowsDeleteString
0x18003baec  mov     [rsp+0A8h+string], rsi
0x18003baf1  mov     rcx, [rsp+0A8h+var_50]; string
0x18003baf6  call    cs:__imp_WindowsDeleteString
0x18003bafc  mov     [rsp+0A8h+var_50], rsi
0x18003bb01  lea     rcx, [rsp+0A8h+var_48]
0x18003bb06  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003bb0b  nop
0x18003bb0c  lea     rcx, [rsp+0A8h+var_40]
0x18003bb11  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003bb16  mov     eax, ebx
0x18003bb18  jmp     loc_18003BD90
0x18003bb1d  mov     rdi, [rsp+0A8h+var_48]
0x18003bb22  mov     rax, [rdi]
0x18003bb25  mov     rbx, [rax+48h]
0x18003bb29  mov     rcx, [rsp+0A8h+var_50]; string
0x18003bb2e  call    cs:__imp_WindowsDeleteString
0x18003bb34  mov     [rsp+0A8h+var_50], rsi
0x18003bb39  mov     [rsp+0A8h+var_20], rsi
0x18003bb41  mov     r9d, 19h; unsigned int
0x18003bb47  lea     r8d, [r9+1]; unsigned int
0x18003bb4b  lea     rdx, aConcurrentdefa; "CONCURRENTDEFAULTINSTALLS"
0x18003bb52  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x18003bb57  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003bb5c  nop
0x18003bb5d  lea     r8, [rsp+0A8h+var_50]
0x18003bb62  mov     rdx, [rsp+0A8h+var_20]
0x18003bb6a  mov     rcx, rdi
0x18003bb6d  mov     rax, rbx
0x18003bb70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb75  mov     ebx, eax
0x18003bb77  test    eax, eax
0x18003bb79  jns     short loc_18003BBD4
0x18003bb7b  mov     rcx, [rsp+0A8h]; this
0x18003bb83  mov     r9d, eax; char *
0x18003bb86  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003bb8d  mov     edx, 309h; void *
0x18003bb92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bb97  nop
0x18003bb98  mov     rcx, [rsp+0A8h+string]; string
0x18003bb9d  call    cs:__imp_WindowsDeleteString
0x18003bba3  mov     [rsp+0A8h+string], rsi
0x18003bba8  mov     rcx, [rsp+0A8h+var_50]; string
0x18003bbad  call    cs:__imp_WindowsDeleteString
0x18003bbb3  mov     [rsp+0A8h+var_50], rsi
0x18003bbb8  lea     rcx, [rsp+0A8h+var_48]
0x18003bbbd  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003bbc2  nop
0x18003bbc3  lea     rcx, [rsp+0A8h+var_40]
0x18003bbc8  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003bbcd  mov     eax, ebx
0x18003bbcf  jmp     loc_18003BD90
0x18003bbd4  mov     rdi, [rsp+0A8h+var_48]
0x18003bbd9  mov     rax, [rdi]
0x18003bbdc  mov     rbx, [rax+48h]
0x18003bbe0  mov     rcx, [rsp+0A8h+string]; string
0x18003bbe5  call    cs:__imp_WindowsDeleteString
0x18003bbeb  mov     [rsp+0A8h+string], rsi
0x18003bbf0  mov     [rsp+0A8h+var_20], rsi
0x18003bbf8  mov     r9d, 15h; unsigned int
0x18003bbfe  lea     r8d, [r9+1]; unsigned int
0x18003bc02  lea     rdx, aConcurrentmini; "CONCURRENTMININSTALLS"
0x18003bc09  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x18003bc0e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003bc13  nop
0x18003bc14  lea     r8, [rsp+0A8h+string]
0x18003bc19  mov     rdx, [rsp+0A8h+var_20]
0x18003bc21  mov     rcx, rdi
0x18003bc24  mov     rax, rbx
0x18003bc27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc2c  mov     ebx, eax
0x18003bc2e  test    eax, eax
0x18003bc30  jns     short loc_18003BC8B
0x18003bc32  mov     rcx, [rsp+0A8h]; this
0x18003bc3a  mov     r9d, eax; char *
0x18003bc3d  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003bc44  mov     edx, 30Ah; void *
0x18003bc49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bc4e  nop
0x18003bc4f  mov     rcx, [rsp+0A8h+string]; string
0x18003bc54  call    cs:__imp_WindowsDeleteString
0x18003bc5a  mov     [rsp+0A8h+string], rsi
0x18003bc5f  mov     rcx, [rsp+0A8h+var_50]; string
0x18003bc64  call    cs:__imp_WindowsDeleteString
0x18003bc6a  mov     [rsp+0A8h+var_50], rsi
0x18003bc6f  lea     rcx, [rsp+0A8h+var_48]
0x18003bc74  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003bc79  nop
0x18003bc7a  lea     rcx, [rsp+0A8h+var_40]
0x18003bc7f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003bc84  mov     eax, ebx
0x18003bc86  jmp     loc_18003BD90
0x18003bc8b  xor     edx, edx; length
0x18003bc8d  mov     rcx, [rsp+0A8h+var_50]; string
0x18003bc92  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bc98  mov     ebx, 0Ah
0x18003bc9d  mov     r8d, ebx; Radix
0x18003bca0  xor     edx, edx; EndPtr
0x18003bca2  mov     rcx, rax; String
0x18003bca5  call    cs:__imp_wcstoul
0x18003bcab  mov     cs:dword_1802CA63C, eax
0x18003bcb1  xor     edx, edx; length
0x18003bcb3  mov     rcx, [rsp+0A8h+string]; string
0x18003bcb8  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bcbe  mov     r8d, ebx; Radix
0x18003bcc1  xor     edx, edx; EndPtr
0x18003bcc3  mov     rcx, rax; String
0x18003bcc6  call    cs:__imp_wcstoul
0x18003bccc  mov     cs:dword_1802CA638, eax
0x18003bcd2  mov     [rsp+0A8h+var_60], eax
0x18003bcd6  mov     eax, cs:dword_1802CA63C
0x18003bcdc  mov     [rsp+0A8h+var_68], eax
0x18003bce0  mov     [rsp+0A8h+var_70], rsi; unsigned __int16 *
0x18003bce5  mov     [rsp+0A8h+var_78], rsi; char *
0x18003bcea  lea     rax, aOnesettingscon; "oneSettingsconcurrentDefaultInstalls = "...
0x18003bcf1  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x18003bcf6  mov     [rsp+0A8h+var_88], 0FFFFFFFFh; int
0x18003bcfe  lea     r9, aGetconcurrenti; "GetConcurrentInstallsFromOneSettings"
0x18003bd05  mov     r8d, 30Fh; unsigned int
0x18003bd0b  lea     rdx, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003bd12  lea     ecx, [rbx-6]; unsigned int
0x18003bd15  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18003bd1a  nop
0x18003bd1b  mov     rcx, [rsp+0A8h+string]; string
0x18003bd20  call    cs:__imp_WindowsDeleteString
0x18003bd26  mov     [rsp+0A8h+string], rsi
0x18003bd2b  mov     rcx, [rsp+0A8h+var_50]; string
0x18003bd30  call    cs:__imp_WindowsDeleteString
0x18003bd36  mov     [rsp+0A8h+var_50], rsi
0x18003bd3b  lea     rcx, [rsp+0A8h+var_48]
0x18003bd40  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003bd45  nop
0x18003bd46  lea     rcx, [rsp+0A8h+var_40]
0x18003bd4b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003bd50  xor     eax, eax
0x18003bd52  jmp     short loc_18003BD90
0x18003bd54  mov     rcx, [rsp+0A8h+string]; string
0x18003bd59  call    cs:__imp_WindowsDeleteString
0x18003bd5f  xor     esi, esi
0x18003bd61  mov     [rsp+0A8h+string], rsi
0x18003bd66  mov     rcx, [rsp+0A8h+var_50]; string
0x18003bd6b  call    cs:__imp_WindowsDeleteString
0x18003bd71  mov     [rsp+0A8h+var_50], rsi
0x18003bd76  lea     rcx, [rsp+0A8h+var_48]
0x18003bd7b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003bd80  nop
0x18003bd81  lea     rcx, [rsp+0A8h+var_40]
0x18003bd86  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003bd8b  mov     eax, 80004005h
0x18003bd90  mov     rcx, [rsp+0A8h+var_18]
0x18003bd98  xor     rcx, rsp; StackCookie
0x18003bd9b  call    __security_check_cookie
0x18003bda0  lea     r11, [rsp+0A8h+var_8]
0x18003bda8  mov     rbx, [r11+10h]
0x18003bdac  mov     rsi, [r11+18h]
0x18003bdb0  mov     rsp, r11
0x18003bdb3  pop     rdi
0x18003bdb4  retn
```
