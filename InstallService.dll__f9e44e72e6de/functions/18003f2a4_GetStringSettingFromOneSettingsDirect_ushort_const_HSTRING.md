# GetStringSettingFromOneSettingsDirect(ushort const *,HSTRING__ * *)

- ea: `0x18003f2a4`
- end: `0x18003f557`
- name: `?GetStringSettingFromOneSettingsDirect@@YAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `691`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HSTRING *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180037cdc`
- `0x18003ef58`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001cce0`
- `0x1800252e8`
- `0x1800341b0`
- `0x18003e698`
- `0x18003f2a4`
- `0x1800d5db4`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f2d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f312`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f371`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f3f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f48d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f503`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f2d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f312`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f371`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f3f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f48d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f503`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f528`

## string_xrefs

- `0x18003f39a`: `Windows.Data.Json.JsonObject`
- `0x18003f2fb`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003f34f`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003f3c8`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003f460`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003f4d6`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall GetStringSettingFromOneSettingsDirect(const unsigned __int16 *a1, HSTRING *a2)
{
  int InstallServiceSettingsFromOneSettingsDirect; // eax
  unsigned int v4; // ebx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  struct Windows::Data::Json::IJsonObject *v10; // rdi
  __int64 (__fastcall *v11)(struct Windows::Data::Json::IJsonObject *, __int64, __int64 *); // rbx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v16; // rax
  int v17; // eax
  unsigned int v18; // ebx
  HSTRING string; // [rsp+20h] [rbp-58h] BYREF
  __int64 v20; // [rsp+28h] [rbp-50h] BYREF
  struct Windows::Data::Json::IJsonObject *v21; // [rsp+30h] [rbp-48h] BYREF
  const unsigned __int16 *v22; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  __int64 v24; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v22 = a1;
  WindowsDeleteString(0);
  string = 0;
  InstallServiceSettingsFromOneSettingsDirect = GetInstallServiceSettingsFromOneSettingsDirect(&string);
  v4 = InstallServiceSettingsFromOneSettingsDirect;
  if ( InstallServiceSettingsFromOneSettingsDirect >= 0 )
  {
    v21 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v21);
    v6 = Json_Parse(string, &v21);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v20 = 0;
      v24 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonObject",
        0x1Du,
        0x1Cu);
      v8 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(v24, &v20);
      v9 = v8;
      if ( v8 >= 0 )
      {
        v10 = v21;
        v11 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, __int64 *))(*(_QWORD *)v21 + 64LL);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v20);
        v24 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"settings", 9u, 8u);
        v12 = v11(v10, v24, &v20);
        v13 = v12;
        if ( v12 >= 0 )
        {
          v14 = v20;
          v15 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v20 + 80LL);
          v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v22);
          v17 = v15(v14, *(_QWORD *)(v16 + 24), a2);
          v18 = v17;
          if ( v17 >= 0 )
          {
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v20);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v21);
            WindowsDeleteString(string);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x245,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
              (const char *)(unsigned int)v17,
              (int)string);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v20);
            Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v21);
            WindowsDeleteString(string);
            return v18;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x244,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
            (const char *)(unsigned int)v12,
            (int)string);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v20);
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v21);
          WindowsDeleteString(string);
          return v13;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x243,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          (const char *)(unsigned int)v8,
          (int)string);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v20);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v21);
        WindowsDeleteString(string);
        return v9;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23F,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        (const char *)(unsigned int)v6,
        (int)string);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v21);
      WindowsDeleteString(string);
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      (const char *)(unsigned int)InstallServiceSettingsFromOneSettingsDirect,
      (int)string);
    WindowsDeleteString(string);
    return v4;
  }
}

```

## disassembly

```asm
0x18003f2a4  mov     r11, rsp
0x18003f2a7  mov     [r11+18h], rbx
0x18003f2ab  mov     [r11+20h], rsi
0x18003f2af  push    rdi
0x18003f2b0  sub     rsp, 70h
0x18003f2b4  mov     rax, cs:__security_cookie
0x18003f2bb  xor     rax, rsp
0x18003f2be  mov     [rsp+78h+var_18], rax
0x18003f2c3  mov     rsi, rdx
0x18003f2c6  mov     [r11-40h], rcx
0x18003f2ca  mov     qword ptr [r11-58h], 0
0x18003f2d2  xor     ecx, ecx; string
0x18003f2d4  call    cs:__imp_WindowsDeleteString
0x18003f2da  mov     [rsp+78h+string], 0; int
0x18003f2e3  lea     rcx, [rsp+78h+string]; HSTRING *
0x18003f2e8  call    ?GetInstallServiceSettingsFromOneSettingsDirect@@YAJPEAPEAUHSTRING__@@@Z; GetInstallServiceSettingsFromOneSettingsDirect(HSTRING__ * *)
0x18003f2ed  mov     ebx, eax
0x18003f2ef  test    eax, eax
0x18003f2f1  jns     short loc_18003F31F
0x18003f2f3  mov     rcx, [rsp+78h]; this
0x18003f2f8  mov     r9d, eax; char *
0x18003f2fb  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003f302  mov     edx, 23Ch; void *
0x18003f307  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f30c  nop
0x18003f30d  mov     rcx, [rsp+78h+string]; string
0x18003f312  call    cs:__imp_WindowsDeleteString
0x18003f318  mov     eax, ebx
0x18003f31a  jmp     loc_18003F537
0x18003f31f  mov     [rsp+78h+var_48], 0
0x18003f328  lea     rcx, [rsp+78h+var_48]
0x18003f32d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003f332  lea     rdx, [rsp+78h+var_48]; struct Windows::Data::Json::IJsonObject **
0x18003f337  mov     rcx, [rsp+78h+string]; HSTRING
0x18003f33c  call    ?Json_Parse@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@Windows@@@Z; Json_Parse(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18003f341  mov     ebx, eax
0x18003f343  test    eax, eax
0x18003f345  jns     short loc_18003F37E
0x18003f347  mov     rcx, [rsp+78h]; this
0x18003f34c  mov     r9d, eax; char *
0x18003f34f  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003f356  mov     edx, 23Fh; void *
0x18003f35b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f360  nop
0x18003f361  lea     rcx, [rsp+78h+var_48]
0x18003f366  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003f36b  nop
0x18003f36c  mov     rcx, [rsp+78h+string]; string
0x18003f371  call    cs:__imp_WindowsDeleteString
0x18003f377  mov     eax, ebx
0x18003f379  jmp     loc_18003F537
0x18003f37e  mov     [rsp+78h+var_50], 0
0x18003f387  mov     [rsp+78h+var_20], 0
0x18003f390  mov     r9d, 1Ch; unsigned int
0x18003f396  lea     r8d, [r9+1]; unsigned int
0x18003f39a  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18003f3a1  lea     rcx, [rsp+78h+hstringHeader]; hstringHeader
0x18003f3a6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003f3ab  lea     rdx, [rsp+78h+var_50]
0x18003f3b0  mov     rcx, [rsp+78h+var_20]
0x18003f3b5  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x18003f3ba  mov     ebx, eax
0x18003f3bc  test    eax, eax
0x18003f3be  jns     short loc_18003F402
0x18003f3c0  mov     rcx, [rsp+78h]; this
0x18003f3c5  mov     r9d, eax; char *
0x18003f3c8  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003f3cf  mov     edx, 243h; void *
0x18003f3d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f3d9  nop
0x18003f3da  lea     rcx, [rsp+78h+var_50]
0x18003f3df  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003f3e4  nop
0x18003f3e5  lea     rcx, [rsp+78h+var_48]
0x18003f3ea  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003f3ef  nop
0x18003f3f0  mov     rcx, [rsp+78h+string]; string
0x18003f3f5  call    cs:__imp_WindowsDeleteString
0x18003f3fb  mov     eax, ebx
0x18003f3fd  jmp     loc_18003F537
0x18003f402  mov     rdi, [rsp+78h+var_48]
0x18003f407  mov     rax, [rdi]
0x18003f40a  mov     rbx, [rax+40h]
0x18003f40e  lea     rcx, [rsp+78h+var_50]
0x18003f413  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003f418  mov     [rsp+78h+var_20], 0
0x18003f421  mov     r9d, 8; unsigned int
0x18003f427  lea     r8d, [r9+1]; unsigned int
0x18003f42b  lea     rdx, aSettings; "settings"
0x18003f432  lea     rcx, [rsp+78h+hstringHeader]; hstringHeader
0x18003f437  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003f43c  nop
0x18003f43d  lea     r8, [rsp+78h+var_50]
0x18003f442  mov     rdx, [rsp+78h+var_20]
0x18003f447  mov     rcx, rdi
0x18003f44a  mov     rax, rbx
0x18003f44d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f452  mov     ebx, eax
0x18003f454  test    eax, eax
0x18003f456  jns     short loc_18003F49A
0x18003f458  mov     rcx, [rsp+78h]; this
0x18003f45d  mov     r9d, eax; char *
0x18003f460  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003f467  mov     edx, 244h; void *
0x18003f46c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f471  nop
0x18003f472  lea     rcx, [rsp+78h+var_50]
0x18003f477  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003f47c  nop
0x18003f47d  lea     rcx, [rsp+78h+var_48]
0x18003f482  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003f487  nop
0x18003f488  mov     rcx, [rsp+78h+string]; string
0x18003f48d  call    cs:__imp_WindowsDeleteString
0x18003f493  mov     eax, ebx
0x18003f495  jmp     loc_18003F537
0x18003f49a  mov     rdi, [rsp+78h+var_50]
0x18003f49f  mov     rax, [rdi]
0x18003f4a2  mov     rbx, [rax+50h]
0x18003f4a6  lea     rdx, [rsp+78h+var_40]
0x18003f4ab  lea     rcx, [rsp+78h+hstringHeader]
0x18003f4b0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003f4b5  nop
0x18003f4b6  mov     r8, rsi
0x18003f4b9  mov     rdx, [rax+18h]
0x18003f4bd  mov     rcx, rdi
0x18003f4c0  mov     rax, rbx
0x18003f4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f4c8  mov     ebx, eax
0x18003f4ca  test    eax, eax
0x18003f4cc  jns     short loc_18003F50D
0x18003f4ce  mov     rcx, [rsp+78h]; this
0x18003f4d3  mov     r9d, eax; char *
0x18003f4d6  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003f4dd  mov     edx, 245h; void *
0x18003f4e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f4e7  nop
0x18003f4e8  lea     rcx, [rsp+78h+var_50]
0x18003f4ed  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003f4f2  nop
0x18003f4f3  lea     rcx, [rsp+78h+var_48]
0x18003f4f8  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003f4fd  nop
0x18003f4fe  mov     rcx, [rsp+78h+string]; string
0x18003f503  call    cs:__imp_WindowsDeleteString
0x18003f509  mov     eax, ebx
0x18003f50b  jmp     short loc_18003F537
0x18003f50d  lea     rcx, [rsp+78h+var_50]
0x18003f512  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003f517  nop
0x18003f518  lea     rcx, [rsp+78h+var_48]
0x18003f51d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003f522  nop
0x18003f523  mov     rcx, [rsp+78h+string]; string
0x18003f528  call    cs:__imp_WindowsDeleteString
0x18003f52e  nop
0x18003f52f  xor     eax, eax
0x18003f531  jmp     short loc_18003F537
0x18003f533  mov     eax, dword ptr [rsp+78h+string]
0x18003f537  mov     rcx, [rsp+78h+var_18]
0x18003f53c  xor     rcx, rsp; StackCookie
0x18003f53f  call    __security_check_cookie
0x18003f544  lea     r11, [rsp+78h+var_8]
0x18003f549  mov     rbx, [r11+20h]
0x18003f54d  mov     rsi, [r11+28h]
0x18003f551  mov     rsp, r11
0x18003f554  pop     rdi
0x18003f555  retn
```
