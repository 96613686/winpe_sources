# NotifyUser::IncrementNotificationCount(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180070a20`
- end: `0x180070bbe`
- name: `?IncrementNotificationCount@NotifyUser@@QEAAEAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006fd7c`

## callees

- `0x18000d030`
- `0x180014a00`
- `0x180017500`
- `0x180019d4c`
- `0x18001c5ec`
- `0x18001dcf4`
- `0x180057218`
- `0x1800702f4`
- `0x180070414`
- `0x180070a20`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070b5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070b5b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070b1b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070b1b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180070b0b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180070b0b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180070b33`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180070b33`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180070ad7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180070ad7`

## string_xrefs

- `0x180070b63`: `UserImpersonationFailed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall NotifyUser::IncrementNotificationCount(_QWORD *a1, __int64 a2)
{
  char v4; // bl
  DWORD LastError; // ebx
  __int64 v7; // rax
  HANDLE Token; // [rsp+30h] [rbp-9h] BYREF
  HANDLE hExistingToken; // [rsp+38h] [rbp-1h] BYREF
  __int64 v10; // [rsp+40h] [rbp+7h] BYREF
  char v11; // [rsp+49h] [rbp+10h]
  __int64 v12; // [rsp+50h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+27h] BYREF
  __int64 v14; // [rsp+78h] [rbp+3Fh]

  v12 = 0;
  hExistingToken = 0;
  Token = 0;
  v10 = 0;
  v14 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Internal.UserManager",
    0x24u,
    0x23u);
  if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(
              v14,
              (__int64)&v10) >= 0
    && (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v10 + 136LL))(v10, *a1, &v12) >= 0
    && (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &hExistingToken,
          0),
        (int)UMgrQueryUserToken(v12, &hExistingToken) >= 0)
    && (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &Token,
          0),
        DuplicateTokenEx(hExistingToken, 4u, 0, SecurityImpersonation, TokenImpersonation, &Token))
    && SetThreadToken(0, Token) )
  {
    v11 = 1;
    v4 = RegistryHelpers::IncrementNotificationCount(a2);
    RevertToSelf();
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
    return v4;
  }
  else
  {
    LastError = GetLastError();
    v7 = std::string::string(&hstringHeader, "UserImpersonationFailed");
    StorageHealthMonitorTelemetry::TraceLoggingWriteStatusErrorCode(v7, LastError);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
    return 0;
  }
}

```

## disassembly

```asm
0x180070a20  mov     [rsp-8+arg_10], rbx
0x180070a25  mov     [rsp-8+arg_18], rdi
0x180070a2a  push    rbp
0x180070a2b  lea     rbp, [rsp-57h]
0x180070a30  sub     rsp, 90h
0x180070a37  mov     rax, cs:__security_cookie
0x180070a3e  xor     rax, rsp
0x180070a41  mov     [rbp+57h+var_10], rax
0x180070a45  mov     rbx, rdx
0x180070a48  mov     rdi, rcx
0x180070a4b  mov     [rbp+57h+var_40], 0
0x180070a53  mov     [rbp+57h+hExistingToken], 0
0x180070a5b  mov     [rbp+57h+Token], 0
0x180070a63  mov     [rbp+57h+var_50], 0
0x180070a6b  mov     [rbp+57h+var_18], 0
0x180070a73  mov     r9d, 23h ; '#'; unsigned int
0x180070a79  lea     r8d, [r9+1]; unsigned int
0x180070a7d  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180070a84  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180070a88  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180070a8d  lea     rdx, [rbp+57h+var_50]
0x180070a91  mov     rcx, [rbp+57h+var_18]
0x180070a95  call    ??$GetActivationFactory@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x180070a9a  test    eax, eax
0x180070a9c  js      loc_180070B5B
0x180070aa2  mov     rcx, [rbp+57h+var_50]
0x180070aa6  mov     rax, [rcx]
0x180070aa9  lea     r8, [rbp+57h+var_40]
0x180070aad  mov     rdx, [rdi]
0x180070ab0  mov     rax, [rax+88h]
0x180070ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070abc  test    eax, eax
0x180070abe  js      loc_180070B5B
0x180070ac4  xor     edx, edx
0x180070ac6  lea     rcx, [rbp+57h+hExistingToken]
0x180070aca  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180070acf  lea     rdx, [rbp+57h+hExistingToken]
0x180070ad3  mov     rcx, [rbp+57h+var_40]
0x180070ad7  call    cs:__imp_UMgrQueryUserToken
0x180070add  test    eax, eax
0x180070adf  js      short loc_180070B5B
0x180070ae1  xor     edx, edx
0x180070ae3  lea     rcx, [rbp+57h+Token]
0x180070ae7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180070aec  lea     rax, [rbp+57h+Token]
0x180070af0  mov     [rsp+90h+phNewToken], rax; phNewToken
0x180070af5  mov     r9d, 2; ImpersonationLevel
0x180070afb  mov     [rsp+90h+TokenType], r9d; TokenType
0x180070b00  xor     r8d, r8d; lpTokenAttributes
0x180070b03  lea     edx, [r9+2]; dwDesiredAccess
0x180070b07  mov     rcx, [rbp+57h+hExistingToken]; hExistingToken
0x180070b0b  call    cs:__imp_DuplicateTokenEx
0x180070b11  test    eax, eax
0x180070b13  jz      short loc_180070B5B
0x180070b15  mov     rdx, [rbp+57h+Token]; Token
0x180070b19  xor     ecx, ecx; Thread
0x180070b1b  call    cs:__imp_SetThreadToken
0x180070b21  test    eax, eax
0x180070b23  jz      short loc_180070B5B
0x180070b25  mov     [rbp+57h+var_47], 1
0x180070b29  mov     rcx, rbx
0x180070b2c  call    ?IncrementNotificationCount@RegistryHelpers@@SAEAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegistryHelpers::IncrementNotificationCount(std::wstring const &)
0x180070b31  mov     bl, al
0x180070b33  call    cs:__imp_RevertToSelf
0x180070b39  nop
0x180070b3a  lea     rcx, [rbp+57h+var_50]
0x180070b3e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180070b43  nop
0x180070b44  lea     rcx, [rbp+57h+Token]
0x180070b48  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180070b4d  nop
0x180070b4e  lea     rcx, [rbp+57h+hExistingToken]
0x180070b52  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180070b57  mov     al, bl
0x180070b59  jmp     short loc_180070B9D
0x180070b5b  call    cs:__imp_GetLastError
0x180070b61  mov     ebx, eax
0x180070b63  lea     rdx, aUserimpersonat; "UserImpersonationFailed"
0x180070b6a  lea     rcx, [rbp+57h+hstringHeader]
0x180070b6e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180070b73  mov     edx, ebx
0x180070b75  mov     rcx, rax
0x180070b78  call    ?TraceLoggingWriteStatusErrorCode@StorageHealthMonitorTelemetry@@SAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@Z; StorageHealthMonitorTelemetry::TraceLoggingWriteStatusErrorCode(std::string,ulong)
0x180070b7d  nop
0x180070b7e  lea     rcx, [rbp+57h+var_50]
0x180070b82  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180070b87  nop
0x180070b88  lea     rcx, [rbp+57h+Token]
0x180070b8c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180070b91  nop
0x180070b92  lea     rcx, [rbp+57h+hExistingToken]
0x180070b96  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180070b9b  xor     al, al
0x180070b9d  mov     rcx, [rbp+57h+var_10]
0x180070ba1  xor     rcx, rsp; StackCookie
0x180070ba4  call    __security_check_cookie
0x180070ba9  lea     r11, [rsp+90h+var_s0]
0x180070bb1  mov     rbx, [r11+20h]
0x180070bb5  mov     rdi, [r11+28h]
0x180070bb9  mov     rsp, r11
0x180070bbc  pop     rbp
0x180070bbd  retn
```
