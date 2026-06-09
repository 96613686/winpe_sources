# Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::GetFromAppUserModelIdForUser(Windows::Internal::StateRepository::IUser *,HSTRING__ *,__int64 *)

- ea: `0x180007bc0`
- end: `0x180007f20`
- name: `?GetFromAppUserModelIdForUser@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@UEAAJPEAUIUser@234@PEAUHSTRING__@@PEA_J@Z`
- size: `864`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::AppInfoFactoryBrokerServer *__hidden this, struct Windows::Internal::StateRepository::IUser *, HSTRING, __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001d60`
- `0x180006224`
- `0x1800071a4`
- `0x180007a84`
- `0x180007b74`
- `0x180007bc0`
- `0x180007f28`
- `0x1800080cc`
- `0x1800081c8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180007c6c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180007c6c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180007cfe`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180007e4f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180007cfe`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180007e4f`

## string_xrefs

- `0x180007c7a`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180007bff`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.appinfofactorybroker.cpp`
- `0x180007c9a`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.appinfofactorybroker.cpp`
- `0x180007d0e`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.appinfofactorybroker.cpp`
- `0x180007d6b`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.appinfofactorybroker.cpp`
- `0x180007e64`: `onecore\base\appmodel\staterepository\winrt\broker\lib\windows.internal.staterepository.appinfofactorybroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::GetFromAppUserModelIdForUser(
        Windows::Internal::StateRepository::AppInfoFactoryBrokerServer *this,
        struct Windows::Internal::StateRepository::IUser *a2,
        HSTRING a3,
        __int64 *a4)
{
  unsigned int v8; // ebx
  int ImpersonationTokenForClientOfObject_nothrow; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  char *v14; // r9
  __int64 v15; // rbx
  int ActivationFactory; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r9
  __int64 v22; // rbx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, struct Windows::Internal::StateRepository::IUser *, HSTRING, __int64 *); // rbx
  int ReturnLength; // [rsp+20h] [rbp-59h]
  __int64 TokenInformation; // [rsp+30h] [rbp-49h] BYREF
  DWORD v30[2]; // [rsp+38h] [rbp-41h] BYREF
  __int64 v31; // [rsp+40h] [rbp-39h] BYREF
  __int64 v32; // [rsp+48h] [rbp-31h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp-29h] BYREF
  __int64 v34; // [rsp+58h] [rbp-21h] BYREF
  __int64 v35; // [rsp+60h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-11h] BYREF
  __int64 v37; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( a4 )
  {
    TokenHandle = 0;
    ImpersonationTokenForClientOfObject_nothrow = wil::GetImpersonationTokenForClientOfObject_nothrow(
                                                    this,
                                                    983551,
                                                    &TokenHandle,
                                                    a4);
    v8 = ImpersonationTokenForClientOfObject_nothrow;
    if ( ImpersonationTokenForClientOfObject_nothrow < 0 )
    {
      v10 = 36;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.app"
                      "infofactorybroker.cpp",
        (const char *)(unsigned int)ImpersonationTokenForClientOfObject_nothrow,
        ReturnLength);
      goto LABEL_37;
    }
    LODWORD(TokenInformation) = 0;
    v30[0] = 0;
    v11 = -6;
    if ( TokenHandle )
      v11 = (__int64)TokenHandle;
    if ( GetTokenInformation((HANDLE)v11, TokenIsAppContainer, &TokenInformation, 4u, v30) )
    {
      if ( !(_DWORD)TokenInformation )
        goto LABEL_29;
    }
    else
    {
      ImpersonationTokenForClientOfObject_nothrow = wil::details::in1diag3::Return_GetLastError(
                                                      retaddr,
                                                      (void *)0x298,
                                                      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                                                      v14);
      v8 = ImpersonationTokenForClientOfObject_nothrow;
      if ( ImpersonationTokenForClientOfObject_nothrow < 0 )
      {
        v10 = 37;
        goto LABEL_10;
      }
    }
    if ( a2 )
    {
      *(_QWORD *)v30 = 0;
      v37 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.StateRepository.User",
        0x26u,
        0x25u);
      v15 = v37;
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(v30);
      ActivationFactory = RoGetActivationFactory(v15, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, v30);
      v8 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.a"
                        "ppinfofactorybroker.cpp",
          (const char *)(unsigned int)ActivationFactory,
          ReturnLength);
LABEL_15:
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(v30);
        goto LABEL_37;
      }
      v17 = *(_QWORD *)v30;
      TokenInformation = 0;
      v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v30 + 80LL);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&TokenInformation);
      v19 = v18(v17, 0, &TokenInformation);
      v8 = v19;
      if ( v19 < 0 )
      {
        v20 = 45;
LABEL_18:
        v21 = (unsigned int)v19;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.a"
                        "ppinfofactorybroker.cpp",
          (const char *)v21,
          ReturnLength);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&TokenInformation);
        goto LABEL_15;
      }
      v34 = 0;
      v35 = 0;
      v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)TokenInformation + 48LL))(TokenInformation, &v34);
      v8 = v19;
      if ( v19 < 0 )
      {
        v20 = 47;
        goto LABEL_18;
      }
      v19 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IUser *, __int64 *))(*(_QWORD *)a2 + 48LL))(
              a2,
              &v35);
      v8 = v19;
      if ( v19 < 0 )
      {
        v20 = 48;
        goto LABEL_18;
      }
      if ( v35 != v34 )
      {
        v8 = -2147024891;
        v20 = 50;
        v21 = 2147942405LL;
        goto LABEL_19;
      }
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&TokenInformation);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(v30);
    }
    ImpersonationTokenForClientOfObject_nothrow = Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::HasPackageQueryOrPackageManagmentCapability(
                                                    this,
                                                    v12,
                                                    v13,
                                                    (bool *)v14);
    v8 = ImpersonationTokenForClientOfObject_nothrow;
    if ( ImpersonationTokenForClientOfObject_nothrow < 0 )
    {
      v10 = 53;
      goto LABEL_10;
    }
LABEL_29:
    v32 = 0;
    v31 = 0;
    v37 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.Application",
      0x2Du,
      0x2Cu);
    v22 = v37;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v31);
    v23 = RoGetActivationFactory(v22, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v31);
    v8 = v23;
    if ( v23 >= 0 )
    {
      v25 = v31;
      v26 = *(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IUser *, HSTRING, __int64 *))(*(_QWORD *)v31 + 240LL);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v32);
      v23 = v26(v25, a2, a3, &v32);
      v8 = v23;
      if ( v23 >= 0 )
      {
        v23 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 48LL))(v32, a4);
        v8 = v23;
        if ( v23 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v31);
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v32);
          v8 = 0;
          goto LABEL_37;
        }
        v24 = 60;
      }
      else
      {
        v24 = 59;
      }
    }
    else
    {
      v24 = 58;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.appin"
                    "fofactorybroker.cpp",
      (const char *)(unsigned int)v23,
      ReturnLength);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v32);
LABEL_37:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v8;
  }
  v8 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x20,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\windows.internal.staterepository.appinfo"
                  "factorybroker.cpp",
    (const char *)0x80004003LL,
    ReturnLength);
  return v8;
}

```

## disassembly

```asm
0x180007bc0  push    rbp
0x180007bc2  push    rbx
0x180007bc3  push    rsi
0x180007bc4  push    rdi
0x180007bc5  push    r12
0x180007bc7  push    r13
0x180007bc9  push    r14
0x180007bcb  push    r15
0x180007bcd  lea     rbp, [rsp-1Fh]
0x180007bd2  sub     rsp, 98h
0x180007bd9  mov     rax, cs:__security_cookie
0x180007be0  xor     rax, rsp
0x180007be3  mov     [rbp+57h+var_48], rax
0x180007be7  xor     r13d, r13d
0x180007bea  mov     r15, r9
0x180007bed  mov     r12, r8
0x180007bf0  mov     rsi, rdx
0x180007bf3  mov     r14, rcx
0x180007bf6  test    r9, r9
0x180007bf9  jnz     short loc_180007C1C
0x180007bfb  mov     rcx, [rbp+5Fh]; this
0x180007bff  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x180007c06  mov     ebx, 80004003h
0x180007c0b  lea     edx, [r15+20h]; void *
0x180007c0f  mov     r9d, ebx; char *
0x180007c12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c17  jmp     loc_180007EFE
0x180007c1c  lea     r8, [rbp+57h+TokenHandle]
0x180007c20  mov     [rbp+57h+TokenHandle], r13
0x180007c24  mov     edx, 0F01FFh
0x180007c29  call    ?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z; wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x180007c2e  mov     ebx, eax
0x180007c30  test    eax, eax
0x180007c32  jns     short loc_180007C3B
0x180007c34  mov     edx, 24h ; '$'
0x180007c39  jmp     short loc_180007C96
0x180007c3b  mov     rax, [rbp+57h+TokenHandle]
0x180007c3f  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180007c43  test    rax, rax
0x180007c46  mov     dword ptr [rbp+57h+TokenInformation], r13d
0x180007c4a  mov     r9d, 4; TokenInformationLength
0x180007c50  mov     [rbp+57h+var_98], r13d
0x180007c54  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x180007c5b  cmovnz  rcx, rax; TokenHandle
0x180007c5f  lea     rax, [rbp+57h+var_98]
0x180007c63  mov     qword ptr [rsp+0D0h+ReturnLength], rax; int
0x180007c68  lea     edx, [r9+19h]; TokenInformationClass
0x180007c6c  call    cs:__imp_GetTokenInformation
0x180007c72  test    eax, eax
0x180007c74  jnz     short loc_180007CAE
0x180007c76  mov     rcx, [rbp+5Fh]; this
0x180007c7a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007c81  mov     edx, 298h; void *
0x180007c86  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007c8b  mov     ebx, eax
0x180007c8d  test    eax, eax
0x180007c8f  jns     short loc_180007CB8
0x180007c91  mov     edx, 25h ; '%'; void *
0x180007c96  mov     rcx, [rbp+5Fh]; this
0x180007c9a  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x180007ca1  mov     r9d, eax; char *
0x180007ca4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ca9  jmp     loc_180007EF5
0x180007cae  cmp     dword ptr [rbp+57h+TokenInformation], r13d
0x180007cb2  jz      loc_180007E0E
0x180007cb8  test    rsi, rsi
0x180007cbb  jz      loc_180007DF6
0x180007cc1  mov     r9d, 25h ; '%'; unsigned int
0x180007cc7  mov     qword ptr [rbp+57h+var_98], r13
0x180007ccb  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x180007cd2  mov     [rbp+57h+var_50], r13
0x180007cd6  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180007cda  lea     r8d, [r9+1]; unsigned int
0x180007cde  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180007ce3  mov     rbx, [rbp+57h+var_50]
0x180007ce7  lea     rcx, [rbp+57h+var_98]
0x180007ceb  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180007cf0  lea     r8, [rbp+57h+var_98]
0x180007cf4  mov     rcx, rbx
0x180007cf7  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x180007cfe  call    cs:__imp_RoGetActivationFactory
0x180007d04  mov     ebx, eax
0x180007d06  test    eax, eax
0x180007d08  jns     short loc_180007D30
0x180007d0a  mov     rcx, [rbp+5Fh]; this
0x180007d0e  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x180007d15  mov     r9d, eax; char *
0x180007d18  mov     edx, 2Bh ; '+'; void *
0x180007d1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d22  lea     rcx, [rbp+57h+var_98]
0x180007d26  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180007d2b  jmp     loc_180007EF5
0x180007d30  mov     rdi, qword ptr [rbp+57h+var_98]
0x180007d34  lea     rcx, [rbp+57h+TokenInformation]
0x180007d38  mov     [rbp+57h+TokenInformation], r13
0x180007d3c  mov     rax, [rdi]
0x180007d3f  mov     rbx, [rax+50h]
0x180007d43  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180007d48  lea     r8, [rbp+57h+TokenInformation]
0x180007d4c  xor     edx, edx
0x180007d4e  mov     rcx, rdi
0x180007d51  mov     rax, rbx
0x180007d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d59  mov     ebx, eax
0x180007d5b  test    eax, eax
0x180007d5d  jns     short loc_180007D82
0x180007d5f  mov     edx, 2Dh ; '-'; void *
0x180007d64  mov     r9d, eax; char *
0x180007d67  mov     rcx, [rbp+5Fh]; this
0x180007d6b  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x180007d72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d77  lea     rcx, [rbp+57h+TokenInformation]
0x180007d7b  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180007d80  jmp     short loc_180007D22
0x180007d82  mov     rcx, [rbp+57h+TokenInformation]
0x180007d86  lea     rdx, [rbp+57h+var_78]
0x180007d8a  mov     [rbp+57h+var_78], r13
0x180007d8e  mov     [rbp+57h+var_70], r13
0x180007d92  mov     rax, [rcx]
0x180007d95  mov     rax, [rax+30h]
0x180007d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d9e  mov     ebx, eax
0x180007da0  test    eax, eax
0x180007da2  jns     short loc_180007DAB
0x180007da4  mov     edx, 2Fh ; '/'
0x180007da9  jmp     short loc_180007D64
0x180007dab  mov     rax, [rsi]
0x180007dae  lea     rdx, [rbp+57h+var_70]
0x180007db2  mov     rcx, rsi
0x180007db5  mov     rax, [rax+30h]
0x180007db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dbe  mov     ebx, eax
0x180007dc0  test    eax, eax
0x180007dc2  jns     short loc_180007DCB
0x180007dc4  mov     edx, 30h ; '0'
0x180007dc9  jmp     short loc_180007D64
0x180007dcb  mov     rax, [rbp+57h+var_78]
0x180007dcf  cmp     [rbp+57h+var_70], rax
0x180007dd3  jz      short loc_180007DE4
0x180007dd5  mov     ebx, 80070005h
0x180007dda  mov     edx, 32h ; '2'
0x180007ddf  mov     r9d, ebx
0x180007de2  jmp     short loc_180007D67
0x180007de4  lea     rcx, [rbp+57h+TokenInformation]
0x180007de8  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180007ded  lea     rcx, [rbp+57h+var_98]
0x180007df1  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180007df6  mov     rcx, r14; this
0x180007df9  call    ?HasPackageQueryOrPackageManagmentCapability@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@AEAAJXZ; Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::HasPackageQueryOrPackageManagmentCapability(void)
0x180007dfe  mov     ebx, eax
0x180007e00  test    eax, eax
0x180007e02  jns     short loc_180007E0E
0x180007e04  mov     edx, 35h ; '5'
0x180007e09  jmp     loc_180007C96
0x180007e0e  mov     r9d, 2Ch ; ','; unsigned int
0x180007e14  mov     [rbp+57h+var_88], r13
0x180007e18  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180007e1f  mov     [rbp+57h+var_90], r13
0x180007e23  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180007e27  mov     [rbp+57h+var_50], r13
0x180007e2b  lea     r8d, [r9+1]; unsigned int
0x180007e2f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180007e34  mov     rbx, [rbp+57h+var_50]
0x180007e38  lea     rcx, [rbp+57h+var_90]
0x180007e3c  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180007e41  lea     r8, [rbp+57h+var_90]
0x180007e45  mov     rcx, rbx
0x180007e48  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x180007e4f  call    cs:__imp_RoGetActivationFactory
0x180007e55  mov     ebx, eax
0x180007e57  test    eax, eax
0x180007e59  jns     short loc_180007E87
0x180007e5b  mov     edx, 3Ah ; ':'; void *
0x180007e60  mov     rcx, [rbp+5Fh]; this
0x180007e64  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x180007e6b  mov     r9d, eax; char *
0x180007e6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e73  lea     rcx, [rbp+57h+var_90]
0x180007e77  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180007e7c  lea     rcx, [rbp+57h+var_88]
0x180007e80  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180007e85  jmp     short loc_180007EF5
0x180007e87  mov     rdi, [rbp+57h+var_90]
0x180007e8b  lea     rcx, [rbp+57h+var_88]
0x180007e8f  mov     rax, [rdi]
0x180007e92  mov     rbx, [rax+0F0h]
0x180007e99  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180007e9e  lea     r9, [rbp+57h+var_88]
0x180007ea2  mov     r8, r12
0x180007ea5  mov     rdx, rsi
0x180007ea8  mov     rcx, rdi
0x180007eab  mov     rax, rbx
0x180007eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eb3  mov     ebx, eax
0x180007eb5  test    eax, eax
0x180007eb7  jns     short loc_180007EC0
0x180007eb9  mov     edx, 3Bh ; ';'
0x180007ebe  jmp     short loc_180007E60
0x180007ec0  mov     rcx, [rbp+57h+var_88]
0x180007ec4  mov     rdx, r15
0x180007ec7  mov     rax, [rcx]
0x180007eca  mov     rax, [rax+30h]
0x180007ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ed3  mov     ebx, eax
0x180007ed5  test    eax, eax
0x180007ed7  jns     short loc_180007EE0
0x180007ed9  mov     edx, 3Ch ; '<'
0x180007ede  jmp     short loc_180007E60
0x180007ee0  lea     rcx, [rbp+57h+var_90]
0x180007ee4  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180007ee9  lea     rcx, [rbp+57h+var_88]
0x180007eed  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180007ef2  mov     ebx, r13d
0x180007ef5  lea     rcx, [rbp+57h+TokenHandle]
0x180007ef9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180007efe  mov     eax, ebx
0x180007f00  mov     rcx, [rbp+57h+var_48]
0x180007f04  xor     rcx, rsp; StackCookie
0x180007f07  call    __security_check_cookie
0x180007f0c  add     rsp, 98h
0x180007f13  pop     r15
0x180007f15  pop     r14
0x180007f17  pop     r13
0x180007f19  pop     r12
0x180007f1b  pop     rdi
0x180007f1c  pop     rsi
0x180007f1d  pop     rbx
0x180007f1e  pop     rbp
0x180007f1f  retn
```
