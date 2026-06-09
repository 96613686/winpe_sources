# Windows::Internal::Management::Provision::ConfigurationSession::GetUserSidFromUser(Windows::System::IUser *,ushort * *)

- ea: `0x18006d3e8`
- end: `0x18006d5b6`
- name: `?GetUserSidFromUser@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEAUIUser@System@5@PEAPEAG@Z`
- size: `462`
- prototype: `__int64 __fastcall(struct Windows::System::IUser *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006dd20`

## callees

- `0x180004eb0`
- `0x180009be4`
- `0x18000a5c4`
- `0x1800151e0`
- `0x180017ed0`
- `0x18003ae88`
- `0x18003b01c`
- `0x18006d3e8`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetUserSidFromToken` at `0x18006d560`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18006d560`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006d520`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006d520`

## string_xrefs

- `0x18006d41a`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006d489`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006d4bf`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006d537`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Management::Provision::ConfigurationSession::GetUserSidFromUser(
        struct Windows::System::IUser *a1,
        unsigned __int16 **a2)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdx
  int UserSidFromToken; // eax
  __int64 v10; // rdx
  __int64 v12; // [rsp+20h] [rbp-50h] BYREF
  void *v13; // [rsp+28h] [rbp-48h] BYREF
  __int64 v14; // [rsp+30h] [rbp-40h] BYREF
  __int64 v15; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  if ( a1 )
  {
    if ( !a2 )
    {
      v4 = 287;
      goto LABEL_3;
    }
    *a2 = 0;
    v14 = 0;
    v17 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Internal.UserManager",
      0x24u,
      0x23u);
    v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(
           v17,
           &v14);
    v5 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x125,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
        (const char *)(unsigned int)v6,
        v12);
LABEL_20:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      return v5;
    }
    v12 = 0;
    v7 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(
           &v14,
           &v12);
    v5 = v7;
    if ( v7 >= 0 )
    {
      v15 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, struct Windows::System::IUser *, __int64 *))(*(_QWORD *)v12 + 136LL))(
             v12,
             a1,
             &v15);
      v5 = v7;
      if ( v7 >= 0 )
      {
        v13 = 0;
        UserSidFromToken = UMgrQueryUserToken(v15, &v13);
        v5 = UserSidFromToken;
        if ( UserSidFromToken >= 0 )
        {
          UserSidFromToken = DmGetUserSidFromToken(v13, a2);
          v5 = UserSidFromToken;
          if ( UserSidFromToken >= 0 )
          {
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
            v5 = 0;
            goto LABEL_20;
          }
          v10 = 304;
        }
        else
        {
          v10 = 302;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
          (const char *)(unsigned int)UserSidFromToken,
          v12);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
        goto LABEL_11;
      }
      v8 = 299;
    }
    else
    {
      v8 = 296;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
      (const char *)(unsigned int)v7,
      v12);
LABEL_11:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
    goto LABEL_20;
  }
  v4 = 286;
LABEL_3:
  v5 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
    (const char *)0x80070057LL,
    v12);
  return v5;
}

```

## disassembly

```asm
0x18006d3e8  mov     [rsp-18h+arg_10], rbx
0x18006d3ed  push    rbp
0x18006d3ee  push    rsi
0x18006d3ef  push    rdi
0x18006d3f0  mov     rbp, rsp
0x18006d3f3  sub     rsp, 70h
0x18006d3f7  mov     rax, cs:__security_cookie
0x18006d3fe  xor     rax, rsp
0x18006d401  mov     [rbp+var_10], rax
0x18006d405  mov     rdi, rdx
0x18006d408  mov     rsi, rcx
0x18006d40b  test    rcx, rcx
0x18006d40e  jnz     short loc_18006D432
0x18006d410  mov     edx, 11Eh; void *
0x18006d415  mov     ebx, 80070057h
0x18006d41a  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006d421  mov     r9d, ebx; char *
0x18006d424  mov     rcx, [rbp+18h]; this
0x18006d428  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d42d  jmp     loc_18006D597
0x18006d432  test    rdi, rdi
0x18006d435  jnz     short loc_18006D43E
0x18006d437  mov     edx, 11Fh
0x18006d43c  jmp     short loc_18006D415
0x18006d43e  mov     qword ptr [rdx], 0
0x18006d445  mov     [rbp+var_40], 0
0x18006d44d  mov     [rbp+var_18], 0
0x18006d455  mov     r9d, 23h ; '#'; unsigned int
0x18006d45b  lea     r8d, [r9+1]; unsigned int
0x18006d45f  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18006d466  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18006d46a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006d46f  lea     rdx, [rbp+var_40]
0x18006d473  mov     rcx, [rbp+var_18]
0x18006d477  call    ??$GetActivationFactory@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>)
0x18006d47c  mov     ebx, eax
0x18006d47e  test    eax, eax
0x18006d480  jns     short loc_18006D49F
0x18006d482  mov     rcx, [rbp+18h]; this
0x18006d486  mov     r9d, eax; char *
0x18006d489  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006d490  mov     edx, 125h; void *
0x18006d495  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d49a  jmp     loc_18006D58E
0x18006d49f  mov     [rbp+var_50], 0
0x18006d4a7  lea     rdx, [rbp+var_50]
0x18006d4ab  lea     rcx, [rbp+var_40]
0x18006d4af  call    ??$As@UISignInStateManager@Internal@System@Windows@@@?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x18006d4b4  mov     ebx, eax
0x18006d4b6  test    eax, eax
0x18006d4b8  jns     short loc_18006D4E1
0x18006d4ba  mov     edx, 128h; void *
0x18006d4bf  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006d4c6  mov     r9d, eax; char *
0x18006d4c9  mov     rcx, [rbp+18h]; this
0x18006d4cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d4d2  nop
0x18006d4d3  lea     rcx, [rbp+var_50]
0x18006d4d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006d4dc  jmp     loc_18006D58E
0x18006d4e1  mov     [rbp+var_38], 0
0x18006d4e9  mov     rcx, [rbp+var_50]
0x18006d4ed  mov     rax, [rcx]
0x18006d4f0  lea     r8, [rbp+var_38]
0x18006d4f4  mov     rdx, rsi
0x18006d4f7  mov     rax, [rax+88h]
0x18006d4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d503  mov     ebx, eax
0x18006d505  test    eax, eax
0x18006d507  jns     short loc_18006D510
0x18006d509  mov     edx, 12Bh
0x18006d50e  jmp     short loc_18006D4BF
0x18006d510  mov     [rbp+var_48], 0
0x18006d518  lea     rdx, [rbp+var_48]
0x18006d51c  mov     rcx, [rbp+var_38]
0x18006d520  call    cs:__imp_UMgrQueryUserToken
0x18006d527  nop     dword ptr [rax+rax+00h]
0x18006d52c  mov     ebx, eax
0x18006d52e  test    eax, eax
0x18006d530  jns     short loc_18006D559
0x18006d532  mov     edx, 12Eh; void *
0x18006d537  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006d53e  mov     r9d, eax; char *
0x18006d541  mov     rcx, [rbp+18h]; this
0x18006d545  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d54a  nop
0x18006d54b  lea     rcx, [rbp+var_48]
0x18006d54f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006d554  jmp     loc_18006D4D3
0x18006d559  mov     rdx, rdi
0x18006d55c  mov     rcx, [rbp+var_48]
0x18006d560  call    cs:__imp_?DmGetUserSidFromToken@@YAJPEAXPEAPEAG@Z; DmGetUserSidFromToken(void *,ushort * *)
0x18006d567  nop     dword ptr [rax+rax+00h]
0x18006d56c  mov     ebx, eax
0x18006d56e  test    eax, eax
0x18006d570  jns     short loc_18006D579
0x18006d572  mov     edx, 130h
0x18006d577  jmp     short loc_18006D537
0x18006d579  lea     rcx, [rbp+var_48]
0x18006d57d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006d582  nop
0x18006d583  lea     rcx, [rbp+var_50]
0x18006d587  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006d58c  xor     ebx, ebx
0x18006d58e  lea     rcx, [rbp+var_40]
0x18006d592  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006d597  mov     eax, ebx
0x18006d599  mov     rcx, [rbp+var_10]
0x18006d59d  xor     rcx, rsp; StackCookie
0x18006d5a0  call    __security_check_cookie
0x18006d5a5  mov     rbx, [rsp+70h+arg_10]
0x18006d5ad  add     rsp, 70h
0x18006d5b1  pop     rdi
0x18006d5b2  pop     rsi
0x18006d5b3  pop     rbp
0x18006d5b4  retn
```
