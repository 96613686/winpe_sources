# AppInstallBroker::UninstallAppForUser(HSTRING__ *,Windows::System::IUser *)

- ea: `0x180218e60`
- end: `0x180219288`
- name: `?UninstallAppForUser@AppInstallBroker@@UEAAJPEAUHSTRING__@@PEAUIUser@System@Windows@@@Z`
- size: `1064`
- prototype: `__int64 __fastcall(AppInstallBroker *__hidden this, HSTRING, struct Windows::System::IUser *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18004f5d0`
- `0x18004ffc0`
- `0x180050934`
- `0x1800c06e8`
- `0x1800c402c`
- `0x1800d8e48`
- `0x18015ae78`
- `0x18019a0e8`
- `0x1801b9640`
- `0x180201e50`
- `0x1802027b0`
- `0x180204c10`
- `0x180218e60`
- `0x1802192e8`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802191e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180219239`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802191e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180219239`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180218edc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180218f59`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802190da`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180218edc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180218f59`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1802190da`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18021905a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18021905a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180218fcd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180218fcd`

## string_xrefs

- `0x180218eef`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180218f6a`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180218fe0`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x18021901a`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180219076`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x1802190eb`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x1802191c1`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`
- `0x180219225`: `shellcommon\shell\tiles\curatedtilecollections\brokers\appinstallbroker\lib\appinstallbroker.cpp`

## pseudocode

```c
__int64 __fastcall AppInstallBroker::UninstallAppForUser(
        AppInstallBroker *this,
        HSTRING a2,
        struct Windows::System::IUser *a3)
{
  __int64 result; // rax
  int ActivationFactory; // eax
  unsigned int LastError; // ebx
  int v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  int token_information; // eax
  void *v12; // rcx
  void *v13; // rsi
  bool v14; // bl
  const char *v15; // r9
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v20; // rax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, HSTRING, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  AppInstallBroker *v27; // rcx
  __int64 v28; // rdx
  int v29; // [rsp+20h] [rbp-59h]
  __int64 v30; // [rsp+30h] [rbp-49h] BYREF
  __int64 v31; // [rsp+38h] [rbp-41h] BYREF
  __int64 v32; // [rsp+40h] [rbp-39h] BYREF
  HSTRING string; // [rsp+48h] [rbp-31h] BYREF
  __int64 v34; // [rsp+50h] [rbp-29h] BYREF
  void *v35; // [rsp+58h] [rbp-21h] BYREF
  __int64 v36; // [rsp+60h] [rbp-19h] BYREF
  void *Block; // [rsp+68h] [rbp-11h] BYREF
  __int64 v38; // [rsp+70h] [rbp-9h] BYREF
  __int64 v39; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF
  __int64 v41; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  result = CallerIdentity::EnsureCallingProcessIsShellExperience(this);
  if ( (int)result >= 0 )
  {
    v38 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    v41 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.Package",
      0x29u,
      0x28u);
    ActivationFactory = RoGetActivationFactory(v41, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v38);
    LastError = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A5,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v29);
LABEL_40:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      return LastError;
    }
    v30 = 0;
    if ( a3 && (unsigned __int8)IsUMgrGetImpersonationTokenForContextPresent() )
    {
      v31 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      v41 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.System.Internal.UserManager",
        0x24u,
        0x23u);
      v8 = RoGetActivationFactory(v41, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v31);
      LastError = v8;
      if ( v8 < 0 )
      {
        v9 = 427;
LABEL_8:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
          (const char *)(unsigned int)v8,
          v29);
LABEL_9:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
LABEL_39:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
        goto LABEL_40;
      }
      v39 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, struct Windows::System::IUser *, __int64 *))(*(_QWORD *)v31 + 136LL))(
             v31,
             a3,
             &v39);
      LastError = v8;
      if ( v8 < 0 )
      {
        v9 = 431;
        goto LABEL_8;
      }
      v32 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v32,
        0);
      v10 = UMgrQueryUserToken(v39, &v32);
      LastError = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B2,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
          (const char *)(unsigned int)v10,
          v29);
LABEL_14:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v32);
        goto LABEL_9;
      }
      Block = 0;
      token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, v32);
      LastError = token_information;
      if ( token_information < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B5,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
          (const char *)(unsigned int)token_information,
          v29);
        v12 = Block;
        if ( !Block )
          goto LABEL_14;
LABEL_17:
        operator delete(v12);
        goto LABEL_14;
      }
      v35 = 0;
      hstringHeader.Reserved.Reserved1 = &v35;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
      hstringHeader.Reserved.Reserved2[16] = 1;
      v13 = Block;
      v14 = !ConvertSidToStringSidW(*(PSID *)Block, (LPWSTR *)&hstringHeader.Reserved.Reserved2[8]);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
      if ( v14 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1B8,
                      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\a"
                                    "ppinstallbroker.cpp",
                      v15);
LABEL_20:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
        if ( !v13 )
          goto LABEL_14;
        v12 = v13;
        goto LABEL_17;
      }
      v34 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      v41 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.StateRepository.User",
        0x26u,
        0x25u);
      v16 = RoGetActivationFactory(v41, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v34);
      LastError = v16;
      if ( v16 < 0 )
      {
        v17 = 443;
LABEL_24:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
          (const char *)(unsigned int)v16,
          v29);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        goto LABEL_20;
      }
      v18 = v34;
      v19 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v34 + 80LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      Block = v35;
      v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (const WCHAR **)&Block);
      v16 = v19(v18, v20[1].Reserved.Reserved1, &v30);
      LastError = v16;
      if ( v16 < 0 )
      {
        v17 = 445;
        goto LABEL_24;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
      if ( v13 )
        operator delete(v13);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    }
    v36 = 0;
    v21 = v38;
    v22 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64 *))(*(_QWORD *)v38 + 360LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    v23 = v22(v21, v30, a2, &v36);
    LastError = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
        (const char *)(unsigned int)v23,
        v29);
LABEL_38:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      goto LABEL_39;
    }
    string = 0;
    v24 = v36;
    v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 112LL);
    WindowsDeleteString(0);
    string = 0;
    v26 = v25(v24, &string);
    LastError = v26;
    if ( v26 >= 0 )
    {
      v26 = AppInstallBroker::UninstallPackageForUserImpl(v27, string, a3);
      LastError = v26;
      if ( v26 >= 0 )
      {
LABEL_37:
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_38;
      }
      v28 = 454;
    }
    else
    {
      v28 = 452;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\appinstallbroker\\lib\\appinstallbroker.cpp",
      (const char *)(unsigned int)v26,
      v29);
    goto LABEL_37;
  }
  return result;
}

```

## disassembly

```asm
0x180218e60  mov     [rsp-8+arg_0], rbx
0x180218e65  mov     [rsp-8+arg_18], rsi
0x180218e6a  push    rbp
0x180218e6b  push    rdi
0x180218e6c  push    r12
0x180218e6e  push    r14
0x180218e70  push    r15
0x180218e72  lea     rbp, [rsp-37h]
0x180218e77  sub     rsp, 0B0h
0x180218e7e  mov     rax, cs:__security_cookie
0x180218e85  xor     rax, rsp
0x180218e88  mov     [rbp+57h+var_30], rax
0x180218e8c  mov     r14, r8
0x180218e8f  mov     r15, rdx
0x180218e92  call    ?EnsureCallingProcessIsShellExperience@CallerIdentity@@YAJXZ; CallerIdentity::EnsureCallingProcessIsShellExperience(void)
0x180218e97  xor     r12d, r12d
0x180218e9a  test    eax, eax
0x180218e9c  js      loc_180219260
0x180218ea2  mov     [rbp+57h+var_60], r12
0x180218ea6  lea     rcx, [rbp+57h+var_60]
0x180218eaa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180218eaf  mov     [rbp+57h+var_38], r12
0x180218eb3  lea     r9d, [r12+28h]; unsigned int
0x180218eb8  lea     r8d, [r12+29h]; unsigned int
0x180218ebd  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180218ec4  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180218ec8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180218ecd  lea     r8, [rbp+57h+var_60]
0x180218ed1  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x180218ed8  mov     rcx, [rbp+57h+var_38]
0x180218edc  call    cs:__imp_RoGetActivationFactory
0x180218ee2  mov     ebx, eax
0x180218ee4  test    eax, eax
0x180218ee6  jns     short loc_180218F05
0x180218ee8  mov     rcx, [rbp+5Fh]; this
0x180218eec  mov     r9d, eax; char *
0x180218eef  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180218ef6  mov     edx, 1A5h; void *
0x180218efb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180218f00  jmp     loc_180219255
0x180218f05  mov     [rbp+57h+var_A0], r12
0x180218f09  test    r14, r14
0x180218f0c  jz      loc_180219183
0x180218f12  call    IsUMgrGetImpersonationTokenForContextPresent
0x180218f17  test    al, al
0x180218f19  jz      loc_180219183
0x180218f1f  mov     [rbp+57h+var_98], r12
0x180218f23  lea     rcx, [rbp+57h+var_98]
0x180218f27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180218f2c  mov     [rbp+57h+var_38], r12
0x180218f30  mov     r9d, 23h ; '#'; unsigned int
0x180218f36  lea     r8d, [r9+1]; unsigned int
0x180218f3a  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180218f41  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180218f45  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180218f4a  lea     r8, [rbp+57h+var_98]
0x180218f4e  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x180218f55  mov     rcx, [rbp+57h+var_38]
0x180218f59  call    cs:__imp_RoGetActivationFactory
0x180218f5f  mov     ebx, eax
0x180218f61  test    eax, eax
0x180218f63  jns     short loc_180218F8B
0x180218f65  mov     edx, 1ABh; void *
0x180218f6a  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180218f71  mov     r9d, eax; char *
0x180218f74  mov     rcx, [rbp+5Fh]; this
0x180218f78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180218f7d  lea     rcx, [rbp+57h+var_98]
0x180218f81  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180218f86  jmp     loc_18021924C
0x180218f8b  mov     [rbp+57h+var_58], r12
0x180218f8f  mov     rcx, [rbp+57h+var_98]
0x180218f93  mov     rax, [rcx]
0x180218f96  lea     r8, [rbp+57h+var_58]
0x180218f9a  mov     rdx, r14
0x180218f9d  mov     rax, [rax+88h]
0x180218fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180218fa9  mov     ebx, eax
0x180218fab  test    eax, eax
0x180218fad  jns     short loc_180218FB6
0x180218faf  mov     edx, 1AFh
0x180218fb4  jmp     short loc_180218F6A
0x180218fb6  mov     [rbp+57h+var_90], r12
0x180218fba  xor     edx, edx
0x180218fbc  lea     rcx, [rbp+57h+var_90]
0x180218fc0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180218fc5  lea     rdx, [rbp+57h+var_90]
0x180218fc9  mov     rcx, [rbp+57h+var_58]
0x180218fcd  call    cs:__imp_UMgrQueryUserToken
0x180218fd3  mov     ebx, eax
0x180218fd5  test    eax, eax
0x180218fd7  jns     short loc_180218FFC
0x180218fd9  mov     rcx, [rbp+5Fh]; this
0x180218fdd  mov     r9d, eax; char *
0x180218fe0  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180218fe7  mov     edx, 1B2h; void *
0x180218fec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180218ff1  lea     rcx, [rbp+57h+var_90]
0x180218ff5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180218ffa  jmp     short loc_180218F7D
0x180218ffc  mov     [rbp+57h+Block], r12
0x180219000  mov     rdx, [rbp+57h+var_90]
0x180219004  lea     rcx, [rbp+57h+Block]
0x180219008  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18021900d  mov     ebx, eax
0x18021900f  test    eax, eax
0x180219011  jns     short loc_18021903B
0x180219013  mov     rcx, [rbp+5Fh]; this
0x180219017  mov     r9d, eax; char *
0x18021901a  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180219021  mov     edx, 1B5h; void *
0x180219026  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021902b  mov     rcx, [rbp+57h+Block]; Block
0x18021902f  test    rcx, rcx
0x180219032  jz      short loc_180218FF1
0x180219034  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180219039  jmp     short loc_180218FF1
0x18021903b  mov     [rbp+57h+var_78], r12
0x18021903f  lea     rax, [rbp+57h+var_78]
0x180219043  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x180219047  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r12
0x18021904b  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
0x18021904f  lea     rdx, [rbp+57h+hstringHeader.Reserved+8]; StringSid
0x180219053  mov     rsi, [rbp+57h+Block]
0x180219057  mov     rcx, [rsi]; Sid
0x18021905a  call    cs:__imp_ConvertSidToStringSidW
0x180219060  test    eax, eax
0x180219062  setz    bl
0x180219065  lea     rcx, [rbp+57h+hstringHeader]
0x180219069  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18021906e  test    bl, bl
0x180219070  jz      short loc_1802190A0
0x180219072  mov     rcx, [rbp+5Fh]; this
0x180219076  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18021907d  mov     edx, 1B8h; void *
0x180219082  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180219087  mov     ebx, eax
0x180219089  lea     rcx, [rbp+57h+var_78]
0x18021908d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180219092  test    rsi, rsi
0x180219095  jz      loc_180218FF1
0x18021909b  mov     rcx, rsi
0x18021909e  jmp     short loc_180219034
0x1802190a0  mov     [rbp+57h+var_80], r12
0x1802190a4  lea     rcx, [rbp+57h+var_80]
0x1802190a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802190ad  mov     [rbp+57h+var_38], r12
0x1802190b1  mov     r9d, 25h ; '%'; unsigned int
0x1802190b7  lea     r8d, [r9+1]; unsigned int
0x1802190bb  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x1802190c2  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1802190c6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1802190cb  lea     r8, [rbp+57h+var_80]
0x1802190cf  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x1802190d6  mov     rcx, [rbp+57h+var_38]
0x1802190da  call    cs:__imp_RoGetActivationFactory
0x1802190e0  mov     ebx, eax
0x1802190e2  test    eax, eax
0x1802190e4  jns     short loc_180219109
0x1802190e6  mov     edx, 1BBh; void *
0x1802190eb  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1802190f2  mov     r9d, eax; char *
0x1802190f5  mov     rcx, [rbp+5Fh]; this
0x1802190f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802190fe  lea     rcx, [rbp+57h+var_80]
0x180219102  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180219107  jmp     short loc_180219089
0x180219109  mov     rdi, [rbp+57h+var_80]
0x18021910d  mov     rax, [rdi]
0x180219110  mov     rbx, [rax+50h]
0x180219114  lea     rcx, [rbp+57h+var_A0]
0x180219118  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021911d  mov     rdx, [rbp+57h+var_78]
0x180219121  mov     [rbp+57h+Block], rdx
0x180219125  lea     rdx, [rbp+57h+Block]
0x180219129  lea     rcx, [rbp+57h+hstringHeader]
0x18021912d  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180219132  lea     r8, [rbp+57h+var_A0]
0x180219136  mov     rdx, [rax+18h]
0x18021913a  mov     rcx, rdi
0x18021913d  mov     rax, rbx
0x180219140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180219145  mov     ebx, eax
0x180219147  test    eax, eax
0x180219149  jns     short loc_180219152
0x18021914b  mov     edx, 1BDh
0x180219150  jmp     short loc_1802190EB
0x180219152  lea     rcx, [rbp+57h+var_80]
0x180219156  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021915b  lea     rcx, [rbp+57h+var_78]
0x18021915f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180219164  test    rsi, rsi
0x180219167  jz      short loc_180219171
0x180219169  mov     rcx, rsi; Block
0x18021916c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180219171  lea     rcx, [rbp+57h+var_90]
0x180219175  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18021917a  lea     rcx, [rbp+57h+var_98]
0x18021917e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180219183  mov     [rbp+57h+var_70], r12
0x180219187  mov     rdi, [rbp+57h+var_60]
0x18021918b  mov     rax, [rdi]
0x18021918e  mov     rbx, [rax+168h]
0x180219195  lea     rcx, [rbp+57h+var_70]
0x180219199  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021919e  lea     r9, [rbp+57h+var_70]
0x1802191a2  mov     r8, r15
0x1802191a5  mov     rdx, [rbp+57h+var_A0]
0x1802191a9  mov     rcx, rdi
0x1802191ac  mov     rax, rbx
0x1802191af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802191b4  mov     ebx, eax
0x1802191b6  test    eax, eax
0x1802191b8  jns     short loc_1802191D4
0x1802191ba  mov     rcx, [rbp+5Fh]; this
0x1802191be  mov     r9d, eax; char *
0x1802191c1  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1802191c8  mov     edx, 1C1h; void *
0x1802191cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802191d2  jmp     short loc_180219243
0x1802191d4  mov     [rbp+57h+string], r12
0x1802191d8  mov     rdi, [rbp+57h+var_70]
0x1802191dc  mov     rax, [rdi]
0x1802191df  mov     rbx, [rax+70h]
0x1802191e3  xor     ecx, ecx; string
0x1802191e5  call    cs:__imp_WindowsDeleteString
0x1802191eb  mov     [rbp+57h+string], r12
0x1802191ef  lea     rdx, [rbp+57h+string]
0x1802191f3  mov     rcx, rdi
0x1802191f6  mov     rax, rbx
0x1802191f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802191fe  mov     ebx, eax
0x180219200  test    eax, eax
0x180219202  jns     short loc_18021920B
0x180219204  mov     edx, 1C4h
0x180219209  jmp     short loc_180219222
0x18021920b  mov     r8, r14; struct Windows::System::IUser *
0x18021920e  mov     rdx, [rbp+57h+string]; HSTRING
0x180219212  call    ?UninstallPackageForUserImpl@AppInstallBroker@@AEAAJPEAUHSTRING__@@PEAUIUser@System@Windows@@@Z; AppInstallBroker::UninstallPackageForUserImpl(HSTRING__ *,Windows::System::IUser *)
0x180219217  mov     ebx, eax
0x180219219  test    eax, eax
0x18021921b  jns     short loc_180219235
0x18021921d  mov     edx, 1C6h; void *
0x180219222  mov     r9d, eax; char *
0x180219225  lea     r8, aShellcommonShe_48; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18021922c  mov     rcx, [rbp+5Fh]; this
0x180219230  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180219235  mov     rcx, [rbp+57h+string]; string
0x180219239  call    cs:__imp_WindowsDeleteString
0x18021923f  mov     [rbp+57h+string], r12
0x180219243  lea     rcx, [rbp+57h+var_70]
0x180219247  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021924c  lea     rcx, [rbp+57h+var_A0]
0x180219250  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180219255  lea     rcx, [rbp+57h+var_60]
0x180219259  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021925e  mov     eax, ebx
0x180219260  mov     rcx, [rbp+57h+var_30]
0x180219264  xor     rcx, rsp; StackCookie
0x180219267  call    __security_check_cookie
0x18021926c  lea     r11, [rsp+0D0h+var_20]
0x180219274  mov     rbx, [r11+30h]
0x180219278  mov     rsi, [r11+48h]
0x18021927c  mov     rsp, r11
0x18021927f  pop     r15
0x180219281  pop     r14
0x180219283  pop     r12
0x180219285  pop     rdi
0x180219286  pop     rbp
0x180219287  retn
```
