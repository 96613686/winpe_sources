# CServicingWOSCSettings::Initialize(wchar_t const *)

- ea: `0x1800a8d50`
- end: `0x1800a900e`
- name: `?Initialize@CServicingWOSCSettings@@EEAAJPEB_W@Z`
- size: `702`
- prototype: `__int64 __fastcall(CServicingWOSCSettings *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800150c0`
- `0x180049f20`
- `0x18004b140`
- `0x18009cf78`
- `0x1800a8d50`
- `0x1800a9014`
- `0x1800a9034`
- `0x1800b9968`
- `0x1800eb920`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800a8dc6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800a8dfe`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800a8e36`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800a8ea2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800a8dc6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800a8dfe`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800a8e36`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800a8ea2`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800a8d92`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800a8e70`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800a8d92`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800a8e70`

## string_xrefs

- `0x1800a8e69`: `api-ms-win-core-winrt-l1-1-0.dll`
- `0x1800a8d8b`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x1800a8e2c`: `WindowsCreateStringReference`
- `0x1800a8df4`: `WindowsDeleteString`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CServicingWOSCSettings::Initialize(CServicingWOSCSettings *this, const wchar_t *a2)
{
  HMODULE Library; // rax
  HMODULE *v5; // rdi
  __int64 result; // rax
  const char *v7; // r9
  FARPROC ProcAddress; // rax
  const char *v9; // r9
  FARPROC v10; // rax
  const char *v11; // r9
  FARPROC v12; // rax
  const char *v13; // r9
  HMODULE v14; // rax
  HMODULE v15; // rcx
  FARPROC v16; // rdi
  const char *v17; // r9
  _QWORD *v18; // rax
  int v19; // eax
  unsigned int v20; // edi
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, char *); // r14
  _QWORD *v23; // rax
  int v24; // eax
  unsigned int v25; // ebx
  _BYTE v26[40]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v27; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    Library = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
    v5 = (HMODULE *)((char *)this + 24);
    Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership((char *)this + 24, Library);
    if ( !*((_QWORD *)this + 3) )
      return wil::details::GetLastErrorFailHr(0);
    ProcAddress = GetProcAddress(*((HMODULE *)this + 3), "WindowsGetStringRawBuffer");
    *((_QWORD *)this + 7) = ProcAddress;
    if ( ProcAddress )
    {
      v10 = GetProcAddress(*v5, "WindowsDeleteString");
      *((_QWORD *)this + 6) = v10;
      if ( v10 )
      {
        v12 = GetProcAddress(*v5, "WindowsCreateStringReference");
        *((_QWORD *)this + 8) = v12;
        if ( v12 )
        {
          v14 = LoadLibraryExW(L"api-ms-win-core-winrt-l1-1-0.dll", 0, 0x800u);
          Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership((char *)this + 32, v14);
          v15 = (HMODULE)*((_QWORD *)this + 4);
          if ( !v15 )
            return wil::details::GetLastErrorFailHr(0);
          v16 = GetProcAddress(v15, "RoGetActivationFactory");
          *((_QWORD *)this + 5) = v16;
          if ( v16 )
          {
            v27 = 0;
            Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(&v27);
            v18 = (_QWORD *)CServicingWOSCSettings::HStringRef::HStringRef(
                              (CServicingWOSCSettings::HStringRef *)v26,
                              L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
                              this);
            v19 = ((__int64 (__fastcall *)(_QWORD, GUID *, __int64 *))v16)(
                    *v18,
                    &GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0,
                    &v27);
            v20 = v19;
            if ( v19 >= 0 )
            {
              v21 = v27;
              v22 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v27 + 48LL);
              Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayload>::InternalRelease((char *)this + 16);
              v23 = (_QWORD *)CServicingWOSCSettings::HStringRef::HStringRef(
                                (CServicingWOSCSettings::HStringRef *)v26,
                                a2,
                                this);
              v24 = v22(v21, *v23, (char *)this + 16);
              v25 = v24;
              if ( v24 >= 0 )
              {
                Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(&v27);
                result = 0;
              }
              else if ( v24 == -2147024894 )
              {
                Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(&v27);
                result = 2147942402LL;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x32,
                  (unsigned int)"onecore\\base\\servicing\\onesettings\\onesettingshelper.cpp",
                  (const char *)(unsigned int)v24,
                  -2);
                Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(&v27);
                result = v25;
              }
            }
            else if ( v19 == -2147221164 )
            {
              Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(&v27);
              result = 2147746132LL;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2C,
                (unsigned int)"onecore\\base\\servicing\\onesettings\\onesettingshelper.cpp",
                (const char *)(unsigned int)v19,
                -2);
              Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(&v27);
              result = v20;
            }
          }
          else
          {
            result = wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       (void *)0x24,
                       (unsigned int)"onecore\\base\\servicing\\onesettings\\onesettingshelper.cpp",
                       v17);
          }
        }
        else
        {
          result = wil::details::in1diag3::Return_GetLastError(
                     retaddr,
                     (void *)0x1E,
                     (unsigned int)"onecore\\base\\servicing\\onesettings\\onesettingshelper.cpp",
                     v13);
        }
      }
      else
      {
        result = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x1B,
                   (unsigned int)"onecore\\base\\servicing\\onesettings\\onesettingshelper.cpp",
                   v11);
      }
    }
    else
    {
      result = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x18,
                 (unsigned int)"onecore\\base\\servicing\\onesettings\\onesettingshelper.cpp",
                 v9);
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x36,
                           (unsigned int)"onecore\\base\\servicing\\onesettings\\onesettingshelper.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800a8d50  mov     rax, rsp
0x1800a8d53  push    rdi
0x1800a8d54  push    r14
0x1800a8d56  push    r15
0x1800a8d58  sub     rsp, 60h
0x1800a8d5c  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x1800a8d64  mov     [rax+18h], rbx
0x1800a8d68  mov     [rax+20h], rsi
0x1800a8d6c  mov     rax, cs:__security_cookie
0x1800a8d73  xor     rax, rsp
0x1800a8d76  mov     [rsp+78h+var_20], rax
0x1800a8d7b  mov     r15, rdx
0x1800a8d7e  mov     rbx, rcx
0x1800a8d81  mov     esi, 800h
0x1800a8d86  mov     r8d, esi; dwFlags
0x1800a8d89  xor     edx, edx; hFile
0x1800a8d8b  lea     rcx, aApiMsWinCoreWi; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x1800a8d92  call    cs:__imp_LoadLibraryExW
0x1800a8d99  nop     dword ptr [rax+rax+00h]
0x1800a8d9e  lea     rdi, [rbx+18h]
0x1800a8da2  mov     rdx, rax
0x1800a8da5  mov     rcx, rdi
0x1800a8da8  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1800a8dad  mov     rcx, [rdi]; this
0x1800a8db0  test    rcx, rcx
0x1800a8db3  jnz     short loc_1800A8DBF
0x1800a8db5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800a8dba  jmp     loc_1800A8FEA
0x1800a8dbf  lea     rdx, aWindowsgetstri; "WindowsGetStringRawBuffer"
0x1800a8dc6  call    cs:__imp_GetProcAddress
0x1800a8dcd  nop     dword ptr [rax+rax+00h]
0x1800a8dd2  mov     [rbx+38h], rax
0x1800a8dd6  test    rax, rax
0x1800a8dd9  jnz     short loc_1800A8DF4
0x1800a8ddb  mov     rcx, [rsp+78h]; this
0x1800a8de0  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\onesettings\\"...
0x1800a8de7  lea     edx, [rax+18h]; void *
0x1800a8dea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a8def  jmp     loc_1800A8FEA
0x1800a8df4  lea     rdx, aWindowsdeletes; "WindowsDeleteString"
0x1800a8dfb  mov     rcx, [rdi]; hModule
0x1800a8dfe  call    cs:__imp_GetProcAddress
0x1800a8e05  nop     dword ptr [rax+rax+00h]
0x1800a8e0a  mov     [rbx+30h], rax
0x1800a8e0e  test    rax, rax
0x1800a8e11  jnz     short loc_1800A8E2C
0x1800a8e13  mov     rcx, [rsp+78h]; this
0x1800a8e18  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\onesettings\\"...
0x1800a8e1f  lea     edx, [rax+1Bh]; void *
0x1800a8e22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a8e27  jmp     loc_1800A8FEA
0x1800a8e2c  lea     rdx, aWindowscreates; "WindowsCreateStringReference"
0x1800a8e33  mov     rcx, [rdi]; hModule
0x1800a8e36  call    cs:__imp_GetProcAddress
0x1800a8e3d  nop     dword ptr [rax+rax+00h]
0x1800a8e42  mov     [rbx+40h], rax
0x1800a8e46  test    rax, rax
0x1800a8e49  jnz     short loc_1800A8E64
0x1800a8e4b  mov     rcx, [rsp+78h]; this
0x1800a8e50  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\onesettings\\"...
0x1800a8e57  lea     edx, [rax+1Eh]; void *
0x1800a8e5a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a8e5f  jmp     loc_1800A8FEA
0x1800a8e64  mov     r8d, esi; dwFlags
0x1800a8e67  xor     edx, edx; hFile
0x1800a8e69  lea     rcx, aApiMsWinCoreWi_0; "api-ms-win-core-winrt-l1-1-0.dll"
0x1800a8e70  call    cs:__imp_LoadLibraryExW
0x1800a8e77  nop     dword ptr [rax+rax+00h]
0x1800a8e7c  mov     rdx, rax
0x1800a8e7f  lea     rcx, [rbx+20h]
0x1800a8e83  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x1800a8e88  mov     rcx, [rbx+20h]; this
0x1800a8e8c  test    rcx, rcx
0x1800a8e8f  jnz     short loc_1800A8E9B
0x1800a8e91  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800a8e96  jmp     loc_1800A8FEA
0x1800a8e9b  lea     rdx, aRogetactivatio; "RoGetActivationFactory"
0x1800a8ea2  call    cs:__imp_GetProcAddress
0x1800a8ea9  nop     dword ptr [rax+rax+00h]
0x1800a8eae  mov     rdi, rax
0x1800a8eb1  mov     [rbx+28h], rax
0x1800a8eb5  test    rax, rax
0x1800a8eb8  jnz     short loc_1800A8ED3
0x1800a8eba  mov     rcx, [rsp+78h]; this
0x1800a8ebf  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\onesettings\\"...
0x1800a8ec6  lea     edx, [rax+24h]; void *
0x1800a8ec9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a8ece  jmp     loc_1800A8FEA
0x1800a8ed3  mov     [rsp+78h+var_28], 0
0x1800a8edc  lea     rcx, [rsp+78h+var_28]
0x1800a8ee1  call    ?InternalRelease@?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(void)
0x1800a8ee6  mov     r8, rbx; struct CServicingWOSCSettings *
0x1800a8ee9  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QB_WB; "Windows.Internal.Flighting.OneSettings."...
0x1800a8ef0  lea     rcx, [rsp+78h+var_50]; this
0x1800a8ef5  call    ??0HStringRef@CServicingWOSCSettings@@QEAA@PEB_WPEAV1@@Z; CServicingWOSCSettings::HStringRef::HStringRef(wchar_t const *,CServicingWOSCSettings *)
0x1800a8efa  lea     r8, [rsp+78h+var_28]
0x1800a8eff  lea     rdx, _GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0
0x1800a8f06  mov     rcx, [rax]
0x1800a8f09  mov     rax, rdi
0x1800a8f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8f11  mov     edi, eax
0x1800a8f13  test    eax, eax
0x1800a8f15  jns     short loc_1800A8F5C
0x1800a8f17  mov     ebx, 80040154h
0x1800a8f1c  cmp     eax, ebx
0x1800a8f1e  jnz     short loc_1800A8F31
0x1800a8f20  lea     rcx, [rsp+78h+var_28]
0x1800a8f25  call    ?InternalRelease@?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(void)
0x1800a8f2a  mov     eax, ebx
0x1800a8f2c  jmp     loc_1800A8FEA
0x1800a8f31  mov     rcx, [rsp+78h]; this
0x1800a8f36  mov     r9d, edi; char *
0x1800a8f39  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\onesettings\\"...
0x1800a8f40  mov     edx, 2Ch ; ','; void *
0x1800a8f45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8f4a  nop
0x1800a8f4b  lea     rcx, [rsp+78h+var_28]
0x1800a8f50  call    ?InternalRelease@?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(void)
0x1800a8f55  mov     eax, edi
0x1800a8f57  jmp     loc_1800A8FEA
0x1800a8f5c  mov     rdi, [rsp+78h+var_28]
0x1800a8f61  mov     rax, [rdi]
0x1800a8f64  mov     r14, [rax+30h]
0x1800a8f68  lea     rcx, [rbx+10h]
0x1800a8f6c  call    ?InternalRelease@?$ComPtr@UIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayload>::InternalRelease(void)
0x1800a8f71  mov     r8, rbx; struct CServicingWOSCSettings *
0x1800a8f74  mov     rdx, r15; wchar_t *
0x1800a8f77  lea     rcx, [rsp+78h+var_50]; this
0x1800a8f7c  call    ??0HStringRef@CServicingWOSCSettings@@QEAA@PEB_WPEAV1@@Z; CServicingWOSCSettings::HStringRef::HStringRef(wchar_t const *,CServicingWOSCSettings *)
0x1800a8f81  lea     r8, [rbx+10h]
0x1800a8f85  mov     rdx, [rax]
0x1800a8f88  mov     rcx, rdi
0x1800a8f8b  mov     rax, r14
0x1800a8f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8f93  mov     ebx, eax
0x1800a8f95  test    eax, eax
0x1800a8f97  jns     short loc_1800A8FD8
0x1800a8f99  mov     edi, 80070002h
0x1800a8f9e  cmp     eax, edi
0x1800a8fa0  jnz     short loc_1800A8FB0
0x1800a8fa2  lea     rcx, [rsp+78h+var_28]
0x1800a8fa7  call    ?InternalRelease@?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(void)
0x1800a8fac  mov     eax, edi
0x1800a8fae  jmp     short loc_1800A8FEA
0x1800a8fb0  mov     rcx, [rsp+78h]; this
0x1800a8fb5  mov     r9d, ebx; char *
0x1800a8fb8  lea     r8, aOnecoreBaseSer_1; "onecore\\base\\servicing\\onesettings\\"...
0x1800a8fbf  mov     edx, 32h ; '2'; void *
0x1800a8fc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8fc9  nop
0x1800a8fca  lea     rcx, [rsp+78h+var_28]
0x1800a8fcf  call    ?InternalRelease@?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(void)
0x1800a8fd4  mov     eax, ebx
0x1800a8fd6  jmp     short loc_1800A8FEA
0x1800a8fd8  lea     rcx, [rsp+78h+var_28]
0x1800a8fdd  call    ?InternalRelease@?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::InternalRelease(void)
0x1800a8fe2  xor     eax, eax
0x1800a8fe4  jmp     short loc_1800A8FEA
0x1800a8fe6  mov     eax, dword ptr [rsp+78h+var_28]
0x1800a8fea  mov     rcx, [rsp+78h+var_20]
0x1800a8fef  xor     rcx, rsp; StackCookie
0x1800a8ff2  call    __security_check_cookie
0x1800a8ff7  lea     r11, [rsp+78h+var_18]
0x1800a8ffc  mov     rbx, [r11+30h]
0x1800a9000  mov     rsi, [r11+38h]
0x1800a9004  mov     rsp, r11
0x1800a9007  pop     r15
0x1800a9009  pop     r14
0x1800a900b  pop     rdi
0x1800a900c  retn
```
