# WinStoreAuth::AuthenticationInternal::FetchStoreAccountIdFromRegistry(ushort const *,Windows::System::IUser *,HSTRING__ * *)

- ea: `0x18003aa0c`
- end: `0x18003ad94`
- name: `?FetchStoreAccountIdFromRegistry@AuthenticationInternal@WinStoreAuth@@YAJPEBGPEAUIUser@System@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `904`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, const unsigned __int16 *, struct Windows::System::IUser *, HSTRING *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006a520`

## callees

- `0x180004644`
- `0x180004738`
- `0x18003aa0c`
- `0x1800439fc`
- `0x180043d54`
- `0x180061224`
- `0x1800612b0`
- `0x180061300`
- `0x180061c04`
- `0x180061eec`
- `0x1800629dc`
- `0x180062a40`
- `0x180075e60`
- `0x18008a110`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003aad7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003aad7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ac43`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ac43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ab63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003abd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ac66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ab63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003abd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ac66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ab0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ab99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ab0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ab99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ad06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ad4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ad06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003ad4a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003aa8e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003abea`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003ac74`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003aa8e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003abea`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003ac74`

## string_xrefs

- `0x18003aaa3`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`
- `0x18003abff`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`
- `0x18003ac85`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinStoreAuth::AuthenticationInternal::FetchStoreAccountIdFromRegistry(
        WinStoreAuth::AuthenticationInternal *this,
        const unsigned __int16 *a2,
        struct Windows::System::IUser *a3,
        HSTRING *a4)
{
  int v5; // eax
  signed int v6; // ebx
  const char *v7; // r9
  unsigned __int64 v8; // rdi
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  const char *v11; // r9
  LSTATUS ValueW; // eax
  const char *v13; // r9
  HSTRING v14; // rax
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  int bIgnoreCasec; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v22; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v24[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h]
  unsigned __int16 pvData[512]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  *(_QWORD *)a3 = 0;
  v24[0] = 0;
  v25 = 0;
  v26 = 0;
  v5 = ConstrainedImpersonateLoggedOnUser::Impersonate((ConstrainedImpersonateLoggedOnUser *)v24);
  v6 = v5;
  if ( v5 >= 0 )
  {
    phkResult = 0;
    v8 = -1;
    if ( CompareStringOrdinal(L"PrimaryWebAccountId", -1, L"StoreAADAccountId", -1, 1) == 2 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      v9 = RegOpenKeyExW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Store",
             0,
             0x20019u,
             &phkResult);
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x570,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v6,
          bIgnoreCasea);
        goto LABEL_34;
      }
    }
    else
    {
      phkResult = 0;
      v10 = RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Store\\CurrentIdentity",
              0,
              0x20019u,
              &phkResult);
      v6 = v10;
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x574,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v6,
          bIgnoreCaseb);
        if ( phkResult )
          RegCloseKey(phkResult);
        if ( !v24[0] )
          goto LABEL_27;
        if ( !RevertToSelf() )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x49,
            (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
            v11);
        goto LABEL_26;
      }
    }
    pcbData = 1024;
    ValueW = RegGetValueW(phkResult, 0, L"StoreAADAccountId", 2u, 0, pvData, &pcbData);
    v6 = ValueW;
    if ( ValueW > 0 )
      v6 = (unsigned __int16)ValueW | 0x80070000;
    if ( v6 < 0 )
    {
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( !v24[0] )
        goto LABEL_27;
      if ( !RevertToSelf() )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x49,
          (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
          v13);
      goto LABEL_26;
    }
    string = 0;
    v22 = 0;
    do
      ++v8;
    while ( pvData[v8] );
    v6 = ULongLongToUInt(v8, &v22);
    if ( v6 >= 0 )
    {
      v6 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, pvData, v22);
      if ( v6 >= 0 )
      {
        v14 = string;
        string = 0;
        *(_QWORD *)a3 = v14;
        WindowsDeleteString(0);
        string = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser((ConstrainedImpersonateLoggedOnUser *)v24);
        return 0;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCasec);
    WindowsDeleteString(string);
    string = 0;
LABEL_34:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser((ConstrainedImpersonateLoggedOnUser *)v24);
    return (unsigned int)v6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56B,
    (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
    (const char *)(unsigned int)v5,
    bIgnoreCase);
  if ( v24[0] )
  {
    if ( !RevertToSelf() )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x49,
        (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
        v7);
LABEL_26:
    v24[0] = 0;
  }
LABEL_27:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)&v25 + 8);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003aa0c  mov     [rsp-8+arg_0], rbx
0x18003aa11  mov     [rsp-8+arg_8], rdi
0x18003aa16  push    rbp
0x18003aa17  push    r14
0x18003aa19  push    r15
0x18003aa1b  lea     rbp, [rsp-390h]
0x18003aa23  sub     rsp, 490h
0x18003aa2a  mov     rax, cs:__security_cookie
0x18003aa31  xor     rax, rsp
0x18003aa34  mov     [rbp+3A0h+var_20], rax
0x18003aa3b  mov     r14, r8
0x18003aa3e  xor     r15d, r15d
0x18003aa41  mov     [r8], r15
0x18003aa44  mov     [rsp+4A0h+var_440], r15b
0x18003aa49  xorps   xmm0, xmm0
0x18003aa4c  movdqu  [rsp+4A0h+var_438], xmm0
0x18003aa52  mov     [rsp+4A0h+var_428], r15
0x18003aa57  lea     rcx, [rsp+4A0h+var_440]; this
0x18003aa5c  call    ?Impersonate@ConstrainedImpersonateLoggedOnUser@@QEAAJXZ; ConstrainedImpersonateLoggedOnUser::Impersonate(void)
0x18003aa61  mov     ebx, eax
0x18003aa63  test    eax, eax
0x18003aa65  jns     short loc_18003AAB3
0x18003aa67  mov     rcx, [rbp+3A8h]; this
0x18003aa6e  mov     r9d, eax; char *
0x18003aa71  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003aa78  mov     edx, 56Bh; void *
0x18003aa7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aa82  nop
0x18003aa83  cmp     [rsp+4A0h+var_440], r15b
0x18003aa88  jz      loc_18003AC9A
0x18003aa8e  call    cs:__imp_RevertToSelf
0x18003aa94  test    eax, eax
0x18003aa96  jnz     loc_18003AC95
0x18003aa9c  mov     rcx, [rbp+3A8h]; this
0x18003aaa3  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18003aaaa  lea     edx, [rax+49h]; void *
0x18003aaad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003aab3  mov     [rsp+4A0h+phkResult], r15
0x18003aab8  mov     [rsp+4A0h+bIgnoreCase], 1; bIgnoreCase
0x18003aac0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003aac4  mov     r9d, edi; cchCount2
0x18003aac7  lea     r8, aStoreaadaccoun; "StoreAADAccountId"
0x18003aace  mov     edx, edi; cchCount1
0x18003aad0  lea     rcx, String1; "PrimaryWebAccountId"
0x18003aad7  call    cs:__imp_CompareStringOrdinal
0x18003aadd  cmp     eax, 2
0x18003aae0  jnz     short loc_18003AB4C
0x18003aae2  xor     edx, edx
0x18003aae4  lea     rcx, [rsp+4A0h+phkResult]
0x18003aae9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003aaee  lea     rax, [rsp+4A0h+phkResult]
0x18003aaf3  mov     qword ptr [rsp+4A0h+bIgnoreCase], rax; int
0x18003aaf8  mov     r9d, 20019h; samDesired
0x18003aafe  xor     r8d, r8d; ulOptions
0x18003ab01  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003ab08  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003ab0f  call    cs:__imp_RegOpenKeyExW
0x18003ab15  mov     ebx, eax
0x18003ab17  test    eax, eax
0x18003ab19  jle     short loc_18003AB24
0x18003ab1b  movzx   ebx, ax
0x18003ab1e  or      ebx, 80070000h
0x18003ab24  test    ebx, ebx
0x18003ab26  jns     loc_18003AC0F
0x18003ab2c  mov     rcx, [rbp+3A8h]; this
0x18003ab33  mov     r9d, ebx; char *
0x18003ab36  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003ab3d  mov     edx, 570h; void *
0x18003ab42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ab47  jmp     loc_18003AD55
0x18003ab4c  mov     rbx, [rsp+4A0h+phkResult]
0x18003ab51  test    rbx, rbx
0x18003ab54  jz      short loc_18003AB73
0x18003ab56  lea     rcx, [rsp+4A0h+var_450]; this
0x18003ab5b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003ab60  mov     rcx, rbx; hKey
0x18003ab63  call    cs:__imp_RegCloseKey
0x18003ab69  lea     rcx, [rsp+4A0h+var_450]; this
0x18003ab6e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003ab73  mov     [rsp+4A0h+phkResult], r15
0x18003ab78  lea     rax, [rsp+4A0h+phkResult]
0x18003ab7d  mov     qword ptr [rsp+4A0h+bIgnoreCase], rax; int
0x18003ab82  mov     r9d, 20019h; samDesired
0x18003ab88  xor     r8d, r8d; ulOptions
0x18003ab8b  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003ab92  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003ab99  call    cs:__imp_RegOpenKeyExW
0x18003ab9f  mov     ebx, eax
0x18003aba1  test    eax, eax
0x18003aba3  jle     short loc_18003ABAE
0x18003aba5  movzx   ebx, ax
0x18003aba8  or      ebx, 80070000h
0x18003abae  test    ebx, ebx
0x18003abb0  jns     short loc_18003AC0F
0x18003abb2  mov     rcx, [rbp+3A8h]; this
0x18003abb9  mov     r9d, ebx; char *
0x18003abbc  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003abc3  mov     edx, 574h; void *
0x18003abc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003abcd  nop
0x18003abce  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x18003abd3  test    rcx, rcx
0x18003abd6  jz      short loc_18003ABDF
0x18003abd8  call    cs:__imp_RegCloseKey
0x18003abde  nop
0x18003abdf  cmp     [rsp+4A0h+var_440], r15b
0x18003abe4  jz      loc_18003AC9A
0x18003abea  call    cs:__imp_RevertToSelf
0x18003abf0  test    eax, eax
0x18003abf2  jnz     loc_18003AC95
0x18003abf8  mov     rcx, [rbp+3A8h]; this
0x18003abff  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18003ac06  lea     edx, [rax+49h]; void *
0x18003ac09  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003ac0f  mov     [rsp+4A0h+var_448], 400h
0x18003ac17  lea     rax, [rsp+4A0h+var_448]
0x18003ac1c  mov     [rsp+4A0h+pcbData], rax; pcbData
0x18003ac21  lea     rax, [rbp+3A0h+var_420]
0x18003ac25  mov     [rsp+4A0h+pvData], rax; pvData
0x18003ac2a  mov     qword ptr [rsp+4A0h+bIgnoreCase], r15; int
0x18003ac2f  mov     r9d, 2; dwFlags
0x18003ac35  lea     r8, aStoreaadaccoun; "StoreAADAccountId"
0x18003ac3c  xor     edx, edx; lpSubKey
0x18003ac3e  mov     rcx, [rsp+4A0h+phkResult]; hkey
0x18003ac43  call    cs:__imp_RegGetValueW
0x18003ac49  mov     ebx, eax
0x18003ac4b  test    eax, eax
0x18003ac4d  jle     short loc_18003AC58
0x18003ac4f  movzx   ebx, ax
0x18003ac52  or      ebx, 80070000h
0x18003ac58  test    ebx, ebx
0x18003ac5a  jns     short loc_18003ACB3
0x18003ac5c  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x18003ac61  test    rcx, rcx
0x18003ac64  jz      short loc_18003AC6D
0x18003ac66  call    cs:__imp_RegCloseKey
0x18003ac6c  nop
0x18003ac6d  cmp     [rsp+4A0h+var_440], r15b
0x18003ac72  jz      short loc_18003AC9A
0x18003ac74  call    cs:__imp_RevertToSelf
0x18003ac7a  test    eax, eax
0x18003ac7c  jnz     short loc_18003AC95
0x18003ac7e  mov     rcx, [rbp+3A8h]; this
0x18003ac85  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18003ac8c  lea     edx, [rax+49h]; void *
0x18003ac8f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003ac95  mov     [rsp+4A0h+var_440], r15b
0x18003ac9a  lea     rcx, [rsp+4A0h+var_438+8]
0x18003ac9f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003aca4  lea     rcx, [rsp+4A0h+var_438]
0x18003aca9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003acae  jmp     loc_18003AD6A
0x18003acb3  mov     [rsp+4A0h+string], r15
0x18003acb8  mov     [rsp+4A0h+var_450], r15d
0x18003acbd  lea     rax, [rbp+3A0h+var_420]
0x18003acc1  inc     rdi
0x18003acc4  cmp     [rax+rdi*2], r15w
0x18003acc9  jnz     short loc_18003ACC1
0x18003accb  lea     rdx, [rsp+4A0h+var_450]; unsigned int *
0x18003acd0  mov     rcx, rdi; unsigned __int64
0x18003acd3  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18003acd8  mov     ebx, eax
0x18003acda  test    eax, eax
0x18003acdc  js      short loc_18003AD2A
0x18003acde  mov     r8d, [rsp+4A0h+var_450]; unsigned int
0x18003ace3  lea     rdx, [rbp+3A0h+var_420]; unsigned __int16 *
0x18003ace7  lea     rcx, [rsp+4A0h+string]; this
0x18003acec  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18003acf1  mov     ebx, eax
0x18003acf3  test    eax, eax
0x18003acf5  js      short loc_18003AD2A
0x18003acf7  mov     rax, [rsp+4A0h+string]
0x18003acfc  mov     [rsp+4A0h+string], r15
0x18003ad01  mov     [r14], rax
0x18003ad04  xor     ecx, ecx; string
0x18003ad06  call    cs:__imp_WindowsDeleteString
0x18003ad0c  mov     [rsp+4A0h+string], r15
0x18003ad11  lea     rcx, [rsp+4A0h+phkResult]
0x18003ad16  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003ad1b  nop
0x18003ad1c  lea     rcx, [rsp+4A0h+var_440]; this
0x18003ad21  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x18003ad26  xor     eax, eax
0x18003ad28  jmp     short loc_18003AD6C
0x18003ad2a  mov     rcx, [rbp+3A8h]; this
0x18003ad31  mov     r9d, ebx; char *
0x18003ad34  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003ad3b  mov     edx, 57Ch; void *
0x18003ad40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ad45  mov     rcx, [rsp+4A0h+string]; string
0x18003ad4a  call    cs:__imp_WindowsDeleteString
0x18003ad50  mov     [rsp+4A0h+string], r15
0x18003ad55  lea     rcx, [rsp+4A0h+phkResult]
0x18003ad5a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003ad5f  nop
0x18003ad60  lea     rcx, [rsp+4A0h+var_440]; this
0x18003ad65  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x18003ad6a  mov     eax, ebx
0x18003ad6c  mov     rcx, [rbp+3A0h+var_20]
0x18003ad73  xor     rcx, rsp; StackCookie
0x18003ad76  call    __security_check_cookie
0x18003ad7b  lea     r11, [rsp+4A0h+var_10]
0x18003ad83  mov     rbx, [r11+20h]
0x18003ad87  mov     rdi, [r11+28h]
0x18003ad8b  mov     rsp, r11
0x18003ad8e  pop     r15
0x18003ad90  pop     r14
0x18003ad92  pop     rbp
0x18003ad93  retn
```
