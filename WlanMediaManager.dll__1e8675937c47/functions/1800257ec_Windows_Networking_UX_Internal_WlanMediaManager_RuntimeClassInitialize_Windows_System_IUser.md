# Windows::Networking::UX::Internal::WlanMediaManager::RuntimeClassInitialize(Windows::System::IUser *)

- ea: `0x1800257ec`
- end: `0x180025a08`
- name: `?RuntimeClassInitialize@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJPEAUIUser@System@5@@Z`
- size: `540`
- prototype: `__int64 __fastcall(void **this, struct Windows::System::IUser *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180029d24`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x180009794`
- `0x1800097b4`
- `0x18000bbf4`
- `0x1800236f0`
- `0x1800257ec`
- `0x180025a10`
- `0x180028984`
- `0x18008e010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002598c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002598c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002592d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002592d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002585d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002585d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Networking::UX::Internal::WlanMediaManager::RuntimeClassInitialize(
        void **this,
        struct Windows::System::IUser *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  int ActivationFactory; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int LastError; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  int v19; // eax
  __int64 v20; // rdx
  const char *v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-60h]
  __int64 v26; // [rsp+30h] [rbp-50h] BYREF
  HANDLE hExistingToken; // [rsp+38h] [rbp-48h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-40h] BYREF
  __int64 v29; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v31; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v28 = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Internal.UserManager",
    0x24u,
    0x23u);
  v4 = v31;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28, v5, v6);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, &v28);
  LastError = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v26 = 0;
    v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
    v14 = **v28;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26, v8, v9);
    v15 = v14(v13, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v26);
    LastError = v15;
    if ( v15 < 0 )
    {
      v16 = 75;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanmediamanager.cpp",
        (const char *)(unsigned int)v15,
        TokenType);
LABEL_6:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26, v17, v18);
      goto LABEL_18;
    }
    v29 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, struct Windows::System::IUser *, __int64 *))(*(_QWORD *)v26 + 136LL))(
            v26,
            a2,
            &v29);
    LastError = v15;
    if ( v15 < 0 )
    {
      v16 = 78;
      goto LABEL_5;
    }
    hExistingToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hExistingToken,
      0);
    v19 = UMgrQueryUserToken(v29, &hExistingToken);
    LastError = v19;
    if ( v19 >= 0 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        this + 120,
        0);
      if ( !DuplicateTokenEx(hExistingToken, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, this + 120) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x53,
                      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanmediamanager.cpp",
                      v21);
        goto LABEL_12;
      }
      v19 = Windows::Networking::UX::Internal::WlanMediaManager::RuntimeClassInitialize((Windows::Networking::UX::Internal::WlanMediaManager *)this);
      LastError = v19;
      if ( v19 >= 0 )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26, v22, v23);
        LastError = 0;
        goto LABEL_18;
      }
      v20 = 85;
    }
    else
    {
      v20 = 81;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanmediamanager.cpp",
      (const char *)(unsigned int)v19,
      TokenType);
LABEL_12:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x48,
    (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlanmediamanager.cpp",
    (const char *)(unsigned int)ActivationFactory,
    TokenType);
LABEL_18:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28, v11, v12);
  return LastError;
}

```

## disassembly

```asm
0x1800257ec  mov     [rsp-18h+arg_10], rbx
0x1800257f1  mov     [rsp-18h+arg_18], rsi
0x1800257f6  push    rbp
0x1800257f7  push    rdi
0x1800257f8  push    r14
0x1800257fa  mov     rbp, rsp
0x1800257fd  sub     rsp, 80h
0x180025804  mov     rax, cs:__security_cookie
0x18002580b  xor     rax, rsp
0x18002580e  mov     [rbp+var_10], rax
0x180025812  mov     r14, rdx
0x180025815  mov     rsi, rcx
0x180025818  mov     [rbp+var_40], 0
0x180025820  mov     [rbp+var_18], 0
0x180025828  mov     r9d, 23h ; '#'; unsigned int
0x18002582e  lea     r8d, [r9+1]; unsigned int
0x180025832  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180025839  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002583d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180025842  mov     rbx, [rbp+var_18]
0x180025846  lea     rcx, [rbp+var_40]
0x18002584a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002584f  lea     r8, [rbp+var_40]
0x180025853  lea     rdx, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x18002585a  mov     rcx, rbx
0x18002585d  call    cs:__imp_RoGetActivationFactory
0x180025863  mov     ebx, eax
0x180025865  test    eax, eax
0x180025867  jns     short loc_180025886
0x180025869  mov     rcx, [rbp+18h]; this
0x18002586d  mov     r9d, eax; char *
0x180025870  lea     r8, aOnecoreuapNetU_17; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180025877  mov     edx, 48h ; 'H'; void *
0x18002587c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025881  jmp     loc_1800259D9
0x180025886  mov     [rbp+var_50], 0
0x18002588e  mov     rbx, [rbp+var_40]
0x180025892  mov     rax, [rbx]
0x180025895  mov     rdi, [rax]
0x180025898  lea     rcx, [rbp+var_50]
0x18002589c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800258a1  lea     r8, [rbp+var_50]
0x1800258a5  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x1800258ac  mov     rcx, rbx
0x1800258af  mov     rax, rdi
0x1800258b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258b7  mov     ebx, eax
0x1800258b9  test    eax, eax
0x1800258bb  jns     short loc_1800258E3
0x1800258bd  mov     edx, 4Bh ; 'K'; void *
0x1800258c2  lea     r8, aOnecoreuapNetU_17; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800258c9  mov     r9d, eax; char *
0x1800258cc  mov     rcx, [rbp+18h]; this
0x1800258d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800258d5  lea     rcx, [rbp+var_50]
0x1800258d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800258de  jmp     loc_1800259D9
0x1800258e3  mov     [rbp+var_38], 0
0x1800258eb  mov     rcx, [rbp+var_50]
0x1800258ef  mov     rax, [rcx]
0x1800258f2  lea     r8, [rbp+var_38]
0x1800258f6  mov     rdx, r14
0x1800258f9  mov     rax, [rax+88h]
0x180025900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025905  mov     ebx, eax
0x180025907  test    eax, eax
0x180025909  jns     short loc_180025912
0x18002590b  mov     edx, 4Eh ; 'N'
0x180025910  jmp     short loc_1800258C2
0x180025912  mov     [rbp+hExistingToken], 0
0x18002591a  xor     edx, edx
0x18002591c  lea     rcx, [rbp+hExistingToken]
0x180025920  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180025925  lea     rdx, [rbp+hExistingToken]
0x180025929  mov     rcx, [rbp+var_38]
0x18002592d  call    cs:__imp_UMgrQueryUserToken
0x180025933  mov     ebx, eax
0x180025935  test    eax, eax
0x180025937  jns     short loc_18002595F
0x180025939  mov     edx, 51h ; 'Q'; void *
0x18002593e  lea     r8, aOnecoreuapNetU_17; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180025945  mov     r9d, eax; char *
0x180025948  mov     rcx, [rbp+18h]; this
0x18002594c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025951  lea     rcx, [rbp+hExistingToken]
0x180025955  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002595a  jmp     loc_1800258D5
0x18002595f  lea     rbx, [rsi+3C0h]
0x180025966  xor     edx, edx
0x180025968  mov     rcx, rbx
0x18002596b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180025970  mov     [rsp+80h+phNewToken], rbx; phNewToken
0x180025975  mov     r9d, 2; ImpersonationLevel
0x18002597b  mov     [rsp+80h+TokenType], r9d; TokenType
0x180025980  xor     r8d, r8d; lpTokenAttributes
0x180025983  mov     edx, 2000000h; dwDesiredAccess
0x180025988  mov     rcx, [rbp+hExistingToken]; hExistingToken
0x18002598c  call    cs:__imp_DuplicateTokenEx
0x180025992  test    eax, eax
0x180025994  jnz     short loc_1800259AD
0x180025996  mov     rcx, [rbp+18h]; this
0x18002599a  lea     r8, aOnecoreuapNetU_17; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800259a1  lea     edx, [rax+53h]; void *
0x1800259a4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800259a9  mov     ebx, eax
0x1800259ab  jmp     short loc_180025951
0x1800259ad  mov     rcx, rsi; this
0x1800259b0  call    ?RuntimeClassInitialize@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJXZ; Windows::Networking::UX::Internal::WlanMediaManager::RuntimeClassInitialize(void)
0x1800259b5  mov     ebx, eax
0x1800259b7  test    eax, eax
0x1800259b9  jns     short loc_1800259C5
0x1800259bb  mov     edx, 55h ; 'U'
0x1800259c0  jmp     loc_18002593E
0x1800259c5  lea     rcx, [rbp+hExistingToken]
0x1800259c9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800259ce  lea     rcx, [rbp+var_50]
0x1800259d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800259d7  xor     ebx, ebx
0x1800259d9  lea     rcx, [rbp+var_40]
0x1800259dd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800259e2  mov     eax, ebx
0x1800259e4  mov     rcx, [rbp+var_10]
0x1800259e8  xor     rcx, rsp; StackCookie
0x1800259eb  call    __security_check_cookie
0x1800259f0  lea     r11, [rsp+80h+var_s0]
0x1800259f8  mov     rbx, [r11+30h]
0x1800259fc  mov     rsi, [r11+38h]
0x180025a00  mov     rsp, r11
0x180025a03  pop     r14
0x180025a05  pop     rdi
0x180025a06  pop     rbp
0x180025a07  retn
```
