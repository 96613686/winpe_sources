# WinStoreAuth::AuthenticationInternal::GetCurrentIUser(Windows::System::IUser * *)

- ea: `0x1800a60f4`
- end: `0x1800a62d6`
- name: `?GetCurrentIUser@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIUser@System@Windows@@@Z`
- size: `482`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, struct Windows::System::IUser **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a8170`

## callees

- `0x180004738`
- `0x18003dab0`
- `0x180061300`
- `0x180061c04`
- `0x180074ae0`
- `0x180074bc8`
- `0x180075e60`
- `0x180088cd0`
- `0x1800a60f4`
- `0x1800a82d8`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a616b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a616b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a612e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a612e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a6146`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a6146`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a617a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a617a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800a61a8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800a61a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetCurrentIUser(
        WinStoreAuth::AuthenticationInternal *this,
        struct Windows::System::IUser **a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  const char *v5; // r9
  unsigned int LastError; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v12; // [rsp+20h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-48h] BYREF
  __int64 v14; // [rsp+30h] [rbp-40h] BYREF
  __int64 v15; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v15 = 0;
  *(_QWORD *)this = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    goto LABEL_6;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(TokenHandle);
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
  {
LABEL_6:
    v7 = UMgrQueryUserContext(TokenHandle, &v15);
    LastError = v7;
    if ( v7 >= 0 )
    {
      v12 = 0;
      v17 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.System.Internal.UserManager",
        0x24u,
        0x23u);
      v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(
             v17,
             &v12);
      LastError = v8;
      if ( v8 >= 0 )
      {
        v14 = 0;
        v9 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(
               &v12,
               &v14);
        LastError = v9;
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, __int64, WinStoreAuth::AuthenticationInternal *))(*(_QWORD *)v14 + 160LL))(
                 v14,
                 v15,
                 this);
          LastError = v9;
          if ( v9 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12);
            LastError = 0;
            goto LABEL_17;
          }
          v10 = 1691;
        }
        else
        {
          v10 = 1689;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v9,
          v12);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v14);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x696,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v8,
          v12);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x693,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v7,
        v12);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x690,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                  v5);
  }
LABEL_17:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800a60f4  mov     [rsp-8+arg_8], rbx
0x1800a60f9  mov     [rsp-8+arg_10], rdi
0x1800a60fe  push    rbp
0x1800a60ff  mov     rbp, rsp
0x1800a6102  sub     rsp, 70h
0x1800a6106  mov     rax, cs:__security_cookie
0x1800a610d  xor     rax, rsp
0x1800a6110  mov     [rbp+var_10], rax
0x1800a6114  mov     rdi, rcx
0x1800a6117  mov     [rbp+var_38], 0
0x1800a611f  mov     qword ptr [rcx], 0
0x1800a6126  mov     [rbp+TokenHandle], 0
0x1800a612e  call    cs:__imp_GetCurrentThread
0x1800a6134  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800a6138  mov     ebx, 0Ch
0x1800a613d  lea     r8d, [rbx-0Bh]; OpenAsSelf
0x1800a6141  mov     edx, ebx; DesiredAccess
0x1800a6143  mov     rcx, rax; ThreadHandle
0x1800a6146  call    cs:__imp_OpenThreadToken
0x1800a614c  test    eax, eax
0x1800a614e  jnz     short loc_1800A61A0
0x1800a6150  mov     rcx, [rbp+TokenHandle]; hObject
0x1800a6154  lea     rax, [rcx-1]
0x1800a6158  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a615c  ja      short loc_1800A6163
0x1800a615e  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x1800a6163  mov     [rbp+TokenHandle], 0
0x1800a616b  call    cs:__imp_GetCurrentProcess
0x1800a6171  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800a6175  mov     edx, ebx; DesiredAccess
0x1800a6177  mov     rcx, rax; ProcessHandle
0x1800a617a  call    cs:__imp_OpenProcessToken
0x1800a6180  test    eax, eax
0x1800a6182  jnz     short loc_1800A61A0
0x1800a6184  mov     rcx, [rbp+8]; this
0x1800a6188  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a618f  mov     edx, 690h; void *
0x1800a6194  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a6199  mov     ebx, eax
0x1800a619b  jmp     loc_1800A62AD
0x1800a61a0  lea     rdx, [rbp+var_38]
0x1800a61a4  mov     rcx, [rbp+TokenHandle]
0x1800a61a8  call    cs:__imp_UMgrQueryUserContext
0x1800a61ae  mov     ebx, eax
0x1800a61b0  test    eax, eax
0x1800a61b2  jns     short loc_1800A61D1
0x1800a61b4  mov     rcx, [rbp+8]; this
0x1800a61b8  mov     r9d, eax; char *
0x1800a61bb  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a61c2  mov     edx, 693h; void *
0x1800a61c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a61cc  jmp     loc_1800A62AD
0x1800a61d1  mov     [rbp+var_50], 0
0x1800a61d9  mov     [rbp+var_18], 0
0x1800a61e1  mov     r9d, 23h ; '#'; unsigned int
0x1800a61e7  lea     r8d, [r9+1]; unsigned int
0x1800a61eb  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x1800a61f2  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800a61f6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a61fb  lea     rdx, [rbp+var_50]
0x1800a61ff  mov     rcx, [rbp+var_18]
0x1800a6203  call    ??$GetActivationFactory@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>>)
0x1800a6208  mov     ebx, eax
0x1800a620a  test    eax, eax
0x1800a620c  jns     short loc_1800A6232
0x1800a620e  mov     rcx, [rbp+8]; this
0x1800a6212  mov     r9d, eax; char *
0x1800a6215  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a621c  mov     edx, 696h; void *
0x1800a6221  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6226  nop
0x1800a6227  lea     rcx, [rbp+var_50]
0x1800a622b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a6230  jmp     short loc_1800A62AD
0x1800a6232  mov     [rbp+var_40], 0
0x1800a623a  lea     rdx, [rbp+var_40]
0x1800a623e  lea     rcx, [rbp+var_50]
0x1800a6242  call    ??$As@UISignInStateManager@Internal@System@Windows@@@?$ComPtr@UIUserManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics>::As<Windows::System::Internal::ISignInStateManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x1800a6247  mov     ebx, eax
0x1800a6249  test    eax, eax
0x1800a624b  jns     short loc_1800A6271
0x1800a624d  mov     edx, 699h; void *
0x1800a6252  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800a6259  mov     r9d, eax; char *
0x1800a625c  mov     rcx, [rbp+8]; this
0x1800a6260  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6265  nop
0x1800a6266  lea     rcx, [rbp+var_40]
0x1800a626a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a626f  jmp     short loc_1800A6227
0x1800a6271  mov     rcx, [rbp+var_40]
0x1800a6275  mov     rax, [rcx]
0x1800a6278  mov     r8, rdi
0x1800a627b  mov     rdx, [rbp+var_38]
0x1800a627f  mov     rax, [rax+0A0h]
0x1800a6286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a628b  mov     ebx, eax
0x1800a628d  test    eax, eax
0x1800a628f  jns     short loc_1800A6298
0x1800a6291  mov     edx, 69Bh
0x1800a6296  jmp     short loc_1800A6252
0x1800a6298  lea     rcx, [rbp+var_40]
0x1800a629c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a62a1  nop
0x1800a62a2  lea     rcx, [rbp+var_50]
0x1800a62a6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800a62ab  xor     ebx, ebx
0x1800a62ad  lea     rcx, [rbp+TokenHandle]
0x1800a62b1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a62b6  mov     eax, ebx
0x1800a62b8  mov     rcx, [rbp+var_10]
0x1800a62bc  xor     rcx, rsp; StackCookie
0x1800a62bf  call    __security_check_cookie
0x1800a62c4  lea     r11, [rsp+70h+var_s0]
0x1800a62c9  mov     rbx, [r11+18h]
0x1800a62cd  mov     rdi, [r11+20h]
0x1800a62d1  mov     rsp, r11
0x1800a62d4  pop     rbp
0x1800a62d5  retn
```
