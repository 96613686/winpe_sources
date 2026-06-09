# GetConcurrentInstallsFromOneSettings(void)

- ea: `0x1800247a0`
- end: `0x180024bad`
- name: `?GetConcurrentInstallsFromOneSettings@@YAJXZ`
- size: `1037`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b21c`

## callees

- `0x180003450`
- `0x18000760c`
- `0x18000912c`
- `0x18000e958`
- `0x180012f10`
- `0x18001f584`
- `0x1800247a0`
- `0x180046010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180024a9d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180024abe`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180024a9d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180024abe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002482d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002483d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800248de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800248ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024995`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800249a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800249dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024a4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024a5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024b18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024b28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024b51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024b63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002482d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002483d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800248de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800248ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024995`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800249a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800249dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024a4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024a5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024b18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024b28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024b51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024b63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024a8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024ab0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024a8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024ab0`

## string_xrefs

- `0x180024816`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x1800248c7`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18002497e`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180024a35`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x180024b03`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18002488c`: `SCCINSTALLSVC`
- `0x1800249fa`: `CONCURRENTMININSTALLS`
- `0x180024943`: `CONCURRENTDEFAULTINSTALLS`
- `0x180024af6`: `GetConcurrentInstallsFromOneSettings`
- `0x180024ae2`: `oneSettingsconcurrentDefaultInstalls = %d, oneSettingsconcurrentMinInstalls = %d`

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
         (__int64)&v25);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v3 = v25;
    v4 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v25 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
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
            dword_180069C00 = wcstoul(StringRawBuffer, 0, 10);
            v17 = WindowsGetStringRawBuffer(string, 0);
            dword_180069C04 = wcstoul(v17, 0, 10);
            v21 = dword_180069C04;
            v20 = dword_180069C00;
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
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
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
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
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
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
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
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
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
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
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
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x1800247a0  mov     r11, rsp
0x1800247a3  mov     [r11+8], rbx
0x1800247a7  mov     [r11+10h], rsi
0x1800247ab  push    rdi
0x1800247ac  sub     rsp, 0A0h
0x1800247b3  mov     rax, cs:__security_cookie
0x1800247ba  xor     rax, rsp
0x1800247bd  mov     [rsp+0A8h+var_18], rax
0x1800247c5  xor     esi, esi
0x1800247c7  mov     [r11-40h], rsi
0x1800247cb  mov     [r11-48h], rsi
0x1800247cf  mov     [r11-50h], rsi
0x1800247d3  mov     [r11-58h], rsi
0x1800247d7  mov     [r11-20h], rsi
0x1800247db  lea     r9d, [rsi+39h]; unsigned int
0x1800247df  lea     r8d, [rsi+3Ah]; unsigned int
0x1800247e3  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x1800247ea  lea     rcx, [r11-38h]; hstringHeader
0x1800247ee  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800247f3  lea     rdx, [rsp+0A8h+var_40]
0x1800247f8  mov     rcx, [rsp+0A8h+var_20]
0x180024800  call    ??$GetActivationFactory@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>)
0x180024805  mov     ebx, eax
0x180024807  test    eax, eax
0x180024809  jns     short loc_180024864
0x18002480b  mov     rcx, [rsp+0A8h]; this
0x180024813  mov     r9d, eax; char *
0x180024816  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002481d  mov     edx, 306h; void *
0x180024822  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024827  nop
0x180024828  mov     rcx, [rsp+0A8h+string]; string
0x18002482d  call    cs:__imp_WindowsDeleteString
0x180024833  mov     [rsp+0A8h+string], rsi
0x180024838  mov     rcx, [rsp+0A8h+var_50]; string
0x18002483d  call    cs:__imp_WindowsDeleteString
0x180024843  mov     [rsp+0A8h+var_50], rsi
0x180024848  lea     rcx, [rsp+0A8h+var_48]
0x18002484d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024852  nop
0x180024853  lea     rcx, [rsp+0A8h+var_40]
0x180024858  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002485d  mov     eax, ebx
0x18002485f  jmp     loc_180024B88
0x180024864  mov     rdi, [rsp+0A8h+var_40]
0x180024869  mov     rax, [rdi]
0x18002486c  mov     rbx, [rax+30h]
0x180024870  lea     rcx, [rsp+0A8h+var_48]
0x180024875  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002487a  mov     [rsp+0A8h+var_20], rsi
0x180024882  mov     r9d, 0Dh; unsigned int
0x180024888  lea     r8d, [r9+1]; unsigned int
0x18002488c  lea     rdx, aSccinstallsvc; "SCCINSTALLSVC"
0x180024893  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x180024898  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002489d  nop
0x18002489e  lea     r8, [rsp+0A8h+var_48]
0x1800248a3  mov     rdx, [rsp+0A8h+var_20]
0x1800248ab  mov     rcx, rdi
0x1800248ae  mov     rax, rbx
0x1800248b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248b6  mov     ebx, eax
0x1800248b8  test    eax, eax
0x1800248ba  jns     short loc_180024915
0x1800248bc  mov     rcx, [rsp+0A8h]; this
0x1800248c4  mov     r9d, eax; char *
0x1800248c7  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x1800248ce  mov     edx, 307h; void *
0x1800248d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800248d8  nop
0x1800248d9  mov     rcx, [rsp+0A8h+string]; string
0x1800248de  call    cs:__imp_WindowsDeleteString
0x1800248e4  mov     [rsp+0A8h+string], rsi
0x1800248e9  mov     rcx, [rsp+0A8h+var_50]; string
0x1800248ee  call    cs:__imp_WindowsDeleteString
0x1800248f4  mov     [rsp+0A8h+var_50], rsi
0x1800248f9  lea     rcx, [rsp+0A8h+var_48]
0x1800248fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024903  nop
0x180024904  lea     rcx, [rsp+0A8h+var_40]
0x180024909  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002490e  mov     eax, ebx
0x180024910  jmp     loc_180024B88
0x180024915  mov     rdi, [rsp+0A8h+var_48]
0x18002491a  mov     rax, [rdi]
0x18002491d  mov     rbx, [rax+48h]
0x180024921  mov     rcx, [rsp+0A8h+var_50]; string
0x180024926  call    cs:__imp_WindowsDeleteString
0x18002492c  mov     [rsp+0A8h+var_50], rsi
0x180024931  mov     [rsp+0A8h+var_20], rsi
0x180024939  mov     r9d, 19h; unsigned int
0x18002493f  lea     r8d, [r9+1]; unsigned int
0x180024943  lea     rdx, aConcurrentdefa; "CONCURRENTDEFAULTINSTALLS"
0x18002494a  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x18002494f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180024954  nop
0x180024955  lea     r8, [rsp+0A8h+var_50]
0x18002495a  mov     rdx, [rsp+0A8h+var_20]
0x180024962  mov     rcx, rdi
0x180024965  mov     rax, rbx
0x180024968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002496d  mov     ebx, eax
0x18002496f  test    eax, eax
0x180024971  jns     short loc_1800249CC
0x180024973  mov     rcx, [rsp+0A8h]; this
0x18002497b  mov     r9d, eax; char *
0x18002497e  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180024985  mov     edx, 309h; void *
0x18002498a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002498f  nop
0x180024990  mov     rcx, [rsp+0A8h+string]; string
0x180024995  call    cs:__imp_WindowsDeleteString
0x18002499b  mov     [rsp+0A8h+string], rsi
0x1800249a0  mov     rcx, [rsp+0A8h+var_50]; string
0x1800249a5  call    cs:__imp_WindowsDeleteString
0x1800249ab  mov     [rsp+0A8h+var_50], rsi
0x1800249b0  lea     rcx, [rsp+0A8h+var_48]
0x1800249b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800249ba  nop
0x1800249bb  lea     rcx, [rsp+0A8h+var_40]
0x1800249c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800249c5  mov     eax, ebx
0x1800249c7  jmp     loc_180024B88
0x1800249cc  mov     rdi, [rsp+0A8h+var_48]
0x1800249d1  mov     rax, [rdi]
0x1800249d4  mov     rbx, [rax+48h]
0x1800249d8  mov     rcx, [rsp+0A8h+string]; string
0x1800249dd  call    cs:__imp_WindowsDeleteString
0x1800249e3  mov     [rsp+0A8h+string], rsi
0x1800249e8  mov     [rsp+0A8h+var_20], rsi
0x1800249f0  mov     r9d, 15h; unsigned int
0x1800249f6  lea     r8d, [r9+1]; unsigned int
0x1800249fa  lea     rdx, aConcurrentmini; "CONCURRENTMININSTALLS"
0x180024a01  lea     rcx, [rsp+0A8h+hstringHeader]; hstringHeader
0x180024a06  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180024a0b  nop
0x180024a0c  lea     r8, [rsp+0A8h+string]
0x180024a11  mov     rdx, [rsp+0A8h+var_20]
0x180024a19  mov     rcx, rdi
0x180024a1c  mov     rax, rbx
0x180024a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a24  mov     ebx, eax
0x180024a26  test    eax, eax
0x180024a28  jns     short loc_180024A83
0x180024a2a  mov     rcx, [rsp+0A8h]; this
0x180024a32  mov     r9d, eax; char *
0x180024a35  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180024a3c  mov     edx, 30Ah; void *
0x180024a41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024a46  nop
0x180024a47  mov     rcx, [rsp+0A8h+string]; string
0x180024a4c  call    cs:__imp_WindowsDeleteString
0x180024a52  mov     [rsp+0A8h+string], rsi
0x180024a57  mov     rcx, [rsp+0A8h+var_50]; string
0x180024a5c  call    cs:__imp_WindowsDeleteString
0x180024a62  mov     [rsp+0A8h+var_50], rsi
0x180024a67  lea     rcx, [rsp+0A8h+var_48]
0x180024a6c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024a71  nop
0x180024a72  lea     rcx, [rsp+0A8h+var_40]
0x180024a77  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024a7c  mov     eax, ebx
0x180024a7e  jmp     loc_180024B88
0x180024a83  xor     edx, edx; length
0x180024a85  mov     rcx, [rsp+0A8h+var_50]; string
0x180024a8a  call    cs:__imp_WindowsGetStringRawBuffer
0x180024a90  mov     ebx, 0Ah
0x180024a95  mov     r8d, ebx; Radix
0x180024a98  xor     edx, edx; EndPtr
0x180024a9a  mov     rcx, rax; String
0x180024a9d  call    cs:__imp_wcstoul
0x180024aa3  mov     cs:dword_180069C00, eax
0x180024aa9  xor     edx, edx; length
0x180024aab  mov     rcx, [rsp+0A8h+string]; string
0x180024ab0  call    cs:__imp_WindowsGetStringRawBuffer
0x180024ab6  mov     r8d, ebx; Radix
0x180024ab9  xor     edx, edx; EndPtr
0x180024abb  mov     rcx, rax; String
0x180024abe  call    cs:__imp_wcstoul
0x180024ac4  mov     cs:dword_180069C04, eax
0x180024aca  mov     [rsp+0A8h+var_60], eax
0x180024ace  mov     eax, cs:dword_180069C00
0x180024ad4  mov     [rsp+0A8h+var_68], eax
0x180024ad8  mov     [rsp+0A8h+var_70], rsi; unsigned __int16 *
0x180024add  mov     [rsp+0A8h+var_78], rsi; char *
0x180024ae2  lea     rax, aOnesettingscon; "oneSettingsconcurrentDefaultInstalls = "...
0x180024ae9  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x180024aee  mov     [rsp+0A8h+var_88], 0FFFFFFFFh; int
0x180024af6  lea     r9, aGetconcurrenti; "GetConcurrentInstallsFromOneSettings"
0x180024afd  mov     r8d, 30Fh; unsigned int
0x180024b03  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180024b0a  lea     ecx, [rbx-6]; unsigned int
0x180024b0d  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180024b12  nop
0x180024b13  mov     rcx, [rsp+0A8h+string]; string
0x180024b18  call    cs:__imp_WindowsDeleteString
0x180024b1e  mov     [rsp+0A8h+string], rsi
0x180024b23  mov     rcx, [rsp+0A8h+var_50]; string
0x180024b28  call    cs:__imp_WindowsDeleteString
0x180024b2e  mov     [rsp+0A8h+var_50], rsi
0x180024b33  lea     rcx, [rsp+0A8h+var_48]
0x180024b38  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024b3d  nop
0x180024b3e  lea     rcx, [rsp+0A8h+var_40]
0x180024b43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024b48  xor     eax, eax
0x180024b4a  jmp     short loc_180024B88
0x180024b4c  mov     rcx, [rsp+0A8h+string]; string
0x180024b51  call    cs:__imp_WindowsDeleteString
0x180024b57  xor     esi, esi
0x180024b59  mov     [rsp+0A8h+string], rsi
0x180024b5e  mov     rcx, [rsp+0A8h+var_50]; string
0x180024b63  call    cs:__imp_WindowsDeleteString
0x180024b69  mov     [rsp+0A8h+var_50], rsi
0x180024b6e  lea     rcx, [rsp+0A8h+var_48]
0x180024b73  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024b78  nop
0x180024b79  lea     rcx, [rsp+0A8h+var_40]
0x180024b7e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024b83  mov     eax, 80004005h
0x180024b88  mov     rcx, [rsp+0A8h+var_18]
0x180024b90  xor     rcx, rsp; StackCookie
0x180024b93  call    __security_check_cookie
0x180024b98  lea     r11, [rsp+0A8h+var_8]
0x180024ba0  mov     rbx, [r11+10h]
0x180024ba4  mov     rsi, [r11+18h]
0x180024ba8  mov     rsp, r11
0x180024bab  pop     rdi
0x180024bac  retn
```
