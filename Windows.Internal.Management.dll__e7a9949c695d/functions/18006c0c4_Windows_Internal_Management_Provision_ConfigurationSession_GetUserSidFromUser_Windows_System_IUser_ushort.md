# Windows::Internal::Management::Provision::ConfigurationSession::GetUserSidFromUser(Windows::System::IUser *,ushort * *)

- ea: `0x18006c0c4`
- end: `0x18006c282`
- name: `?GetUserSidFromUser@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEAUIUser@System@5@PEAPEAG@Z`
- size: `446`
- prototype: `__int64 __fastcall(struct Windows::System::IUser *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006c9d0`

## callees

- `0x180004d50`
- `0x18000992c`
- `0x18000a2a4`
- `0x180014af0`
- `0x1800176c4`
- `0x18003b6f8`
- `0x18003b88c`
- `0x18006c0c4`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmGetUserSidFromToken` at `0x18006c233`
- `DMCmnUtils!DmGetUserSidFromToken` at `0x18006c233`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006c1fc`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006c1fc`

## string_xrefs

- `0x18006c0f6`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006c165`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006c19b`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006c20d`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`

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
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-40h] BYREF
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
           (__int64)&v14);
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
           (__int64)&v12);
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
0x18006c0c4  mov     [rsp-18h+arg_10], rbx
0x18006c0c9  push    rbp
0x18006c0ca  push    rsi
0x18006c0cb  push    rdi
0x18006c0cc  mov     rbp, rsp
0x18006c0cf  sub     rsp, 70h
0x18006c0d3  mov     rax, cs:__security_cookie
0x18006c0da  xor     rax, rsp
0x18006c0dd  mov     [rbp+var_10], rax
0x18006c0e1  mov     rdi, rdx
0x18006c0e4  mov     rsi, rcx
0x18006c0e7  test    rcx, rcx
0x18006c0ea  jnz     short loc_18006C10E
0x18006c0ec  mov     edx, 11Eh; void *
0x18006c0f1  mov     ebx, 80070057h
0x18006c0f6  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006c0fd  mov     r9d, ebx; char *
0x18006c100  mov     rcx, [rbp+18h]; this
0x18006c104  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c109  jmp     loc_18006C264
0x18006c10e  test    rdi, rdi
0x18006c111  jnz     short loc_18006C11A
0x18006c113  mov     edx, 11Fh
0x18006c118  jmp     short loc_18006C0F1
0x18006c11a  mov     qword ptr [rdx], 0
0x18006c121  mov     [rbp+var_40], 0
0x18006c129  mov     [rbp+var_18], 0
0x18006c131  mov     r9d, 23h ; '#'; unsigned int
0x18006c137  lea     r8d, [r9+1]; unsigned int
0x18006c13b  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18006c142  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18006c146  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006c14b  lea     rdx, [rbp+var_40]
0x18006c14f  mov     rcx, [rbp+var_18]
0x18006c153  call    ??$GetActivationFactory@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>)
0x18006c158  mov     ebx, eax
0x18006c15a  test    eax, eax
0x18006c15c  jns     short loc_18006C17B
0x18006c15e  mov     rcx, [rbp+18h]; this
0x18006c162  mov     r9d, eax; char *
0x18006c165  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006c16c  mov     edx, 125h; void *
0x18006c171  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c176  jmp     loc_18006C25B
0x18006c17b  mov     [rbp+var_50], 0
0x18006c183  lea     rdx, [rbp+var_50]
0x18006c187  lea     rcx, [rbp+var_40]
0x18006c18b  call    ??$As@UISignInStateManager@Internal@System@Windows@@@?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x18006c190  mov     ebx, eax
0x18006c192  test    eax, eax
0x18006c194  jns     short loc_18006C1BD
0x18006c196  mov     edx, 128h; void *
0x18006c19b  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006c1a2  mov     r9d, eax; char *
0x18006c1a5  mov     rcx, [rbp+18h]; this
0x18006c1a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c1ae  nop
0x18006c1af  lea     rcx, [rbp+var_50]
0x18006c1b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006c1b8  jmp     loc_18006C25B
0x18006c1bd  mov     [rbp+var_38], 0
0x18006c1c5  mov     rcx, [rbp+var_50]
0x18006c1c9  mov     rax, [rcx]
0x18006c1cc  lea     r8, [rbp+var_38]
0x18006c1d0  mov     rdx, rsi
0x18006c1d3  mov     rax, [rax+88h]
0x18006c1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c1df  mov     ebx, eax
0x18006c1e1  test    eax, eax
0x18006c1e3  jns     short loc_18006C1EC
0x18006c1e5  mov     edx, 12Bh
0x18006c1ea  jmp     short loc_18006C19B
0x18006c1ec  mov     [rbp+var_48], 0
0x18006c1f4  lea     rdx, [rbp+var_48]
0x18006c1f8  mov     rcx, [rbp+var_38]
0x18006c1fc  call    cs:__imp_UMgrQueryUserToken
0x18006c202  mov     ebx, eax
0x18006c204  test    eax, eax
0x18006c206  jns     short loc_18006C22C
0x18006c208  mov     edx, 12Eh; void *
0x18006c20d  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006c214  mov     r9d, eax; char *
0x18006c217  mov     rcx, [rbp+18h]; this
0x18006c21b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c220  nop
0x18006c221  lea     rcx, [rbp+var_48]
0x18006c225  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006c22a  jmp     short loc_18006C1AF
0x18006c22c  mov     rdx, rdi
0x18006c22f  mov     rcx, [rbp+var_48]
0x18006c233  call    cs:__imp_?DmGetUserSidFromToken@@YAJPEAXPEAPEAG@Z; DmGetUserSidFromToken(void *,ushort * *)
0x18006c239  mov     ebx, eax
0x18006c23b  test    eax, eax
0x18006c23d  jns     short loc_18006C246
0x18006c23f  mov     edx, 130h
0x18006c244  jmp     short loc_18006C20D
0x18006c246  lea     rcx, [rbp+var_48]
0x18006c24a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006c24f  nop
0x18006c250  lea     rcx, [rbp+var_50]
0x18006c254  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006c259  xor     ebx, ebx
0x18006c25b  lea     rcx, [rbp+var_40]
0x18006c25f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006c264  mov     eax, ebx
0x18006c266  mov     rcx, [rbp+var_10]
0x18006c26a  xor     rcx, rsp; StackCookie
0x18006c26d  call    __security_check_cookie
0x18006c272  mov     rbx, [rsp+70h+arg_10]
0x18006c27a  add     rsp, 70h
0x18006c27e  pop     rdi
0x18006c27f  pop     rsi
0x18006c280  pop     rbp
0x18006c281  retn
```
