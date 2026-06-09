# Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::GetCallerUserSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180023e30`
- end: `0x180023f89`
- name: `?GetCallerUserSid@AssignedAccessControllerPrivileged@AssignedAccess@Internal@Windows@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `345`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180023300`

## callees

- `0x18000b694`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180022cdc`
- `0x180023e30`
- `0x1800506e0`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023eb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023eb7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023ecd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023ecd`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180023e5d`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180023e5d`

## string_xrefs

- `0x180023e8b`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivileged.cpp`
- `0x180023edb`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivileged.cpp`
- `0x180023f22`: `onecoreuap\base\embedded\sys\lockdown\runtime\libsrv\assignedaccesscontrollerprivileged.cpp`

## pseudocode

```c
// audit: GetCallerUserSid uses IServerSecurity impersonation + OpenThreadToken; real caller SID gate for low-user reachable ControllerPrivileged.
// Hidden C++ exception states: #wind=10
__int64 Windows::Internal::AssignedAccess::AssignedAccessControllerPrivileged::GetCallerUserSid()
{
  HRESULT v0; // eax
  unsigned int LastError; // ebx
  __int64 v2; // rdx
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  int UserSidFromToken; // eax
  int v7; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  void *ppInterface; // [rsp+40h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+20h] BYREF

  ppInterface = 0;
  v0 = CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface);
  LastError = v0;
  if ( v0 < 0 )
  {
    v2 = 118;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivileged.cpp",
      (const char *)(unsigned int)v0,
      v7);
    goto LABEL_11;
  }
  v0 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
  LastError = v0;
  if ( v0 < 0 )
  {
    v2 = 120;
    goto LABEL_5;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    UserSidFromToken = Windows::Internal::AssignedAccess::UserInfoHelper::GetUserSidFromToken(TokenHandle);
    LastError = UserSidFromToken;
    if ( UserSidFromToken >= 0 )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 40LL))(ppInterface);
      LastError = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivileged.cpp",
        (const char *)(unsigned int)UserSidFromToken,
        (int)&ppInterface);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 40LL))(ppInterface);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x7F,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\libsrv\\assignedaccesscontrollerprivileged.cpp",
                  v4);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 40LL))(ppInterface);
  }
LABEL_11:
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&ppInterface);
  return LastError;
}

```

## disassembly

```asm
0x180023e30  mov     [rsp-8+arg_8], rbx; audit: GetCallerUserSid uses IServerSecurity impersonation + OpenThreadToken; real caller SID gate for low-user reachable ControllerPrivileged.
0x180023e35  mov     [rsp-8+arg_18], rdi
0x180023e3a  mov     [rsp-8+ppInterface], rcx
0x180023e3f  push    rbp
0x180023e40  mov     rbp, rsp
0x180023e43  sub     rsp, 30h
0x180023e47  mov     rdi, rdx
0x180023e4a  mov     [rbp+ppInterface], 0
0x180023e52  lea     rdx, [rbp+ppInterface]; ppInterface
0x180023e56  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x180023e5d  call    cs:__imp_CoGetCallContext
0x180023e63  mov     ebx, eax
0x180023e65  test    eax, eax
0x180023e67  jns     short loc_180023E70
0x180023e69  mov     edx, 76h ; 'v'
0x180023e6e  jmp     short loc_180023E8B
0x180023e70  mov     rcx, [rbp+ppInterface]
0x180023e74  mov     rax, [rcx]
0x180023e77  mov     rax, [rax+20h]
0x180023e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e80  mov     ebx, eax
0x180023e82  test    eax, eax
0x180023e84  jns     short loc_180023EA3
0x180023e86  mov     edx, 78h ; 'x'; void *
0x180023e8b  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180023e92  mov     r9d, eax; char *
0x180023e95  mov     rcx, [rbp+8]; this
0x180023e99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023e9e  jmp     loc_180023F6E
0x180023ea3  lea     rax, [rbp+ppInterface]
0x180023ea7  mov     [rbp+var_10], rax
0x180023eab  mov     [rbp+var_8], 1
0x180023eaf  mov     [rbp+TokenHandle], 0
0x180023eb7  call    cs:__imp_GetCurrentThread
0x180023ebd  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180023ec1  mov     edx, 8; DesiredAccess
0x180023ec6  lea     r8d, [rdx-7]; OpenAsSelf
0x180023eca  mov     rcx, rax; ThreadHandle
0x180023ecd  call    cs:__imp_OpenThreadToken
0x180023ed3  test    eax, eax
0x180023ed5  jnz     short loc_180023F09
0x180023ed7  mov     rcx, [rbp+8]; this
0x180023edb  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180023ee2  lea     edx, [rax+7Fh]; void *
0x180023ee5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023eea  mov     ebx, eax
0x180023eec  lea     rcx, [rbp+TokenHandle]
0x180023ef0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180023ef5  nop
0x180023ef6  mov     rcx, [rbp+ppInterface]
0x180023efa  mov     rdx, [rcx]
0x180023efd  mov     rax, [rdx+28h]
0x180023f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f06  nop
0x180023f07  jmp     short loc_180023F6E
0x180023f09  mov     rdx, rdi
0x180023f0c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180023f10  call    ?GetUserSidFromToken@UserInfoHelper@AssignedAccess@Internal@Windows@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::AssignedAccess::UserInfoHelper::GetUserSidFromToken(void *,std::wstring &)
0x180023f15  mov     ebx, eax
0x180023f17  test    eax, eax
0x180023f19  jns     short loc_180023F51
0x180023f1b  mov     rcx, [rbp+8]; this
0x180023f1f  mov     r9d, eax; char *
0x180023f22  lea     r8, aOnecoreuapBase_75; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180023f29  mov     edx, 80h; void *
0x180023f2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f33  nop
0x180023f34  lea     rcx, [rbp+TokenHandle]
0x180023f38  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180023f3d  nop
0x180023f3e  mov     rcx, [rbp+ppInterface]
0x180023f42  mov     rax, [rcx]
0x180023f45  mov     rax, [rax+28h]
0x180023f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f4e  nop
0x180023f4f  jmp     short loc_180023F6E
0x180023f51  lea     rcx, [rbp+TokenHandle]
0x180023f55  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180023f5a  nop
0x180023f5b  mov     rcx, [rbp+ppInterface]
0x180023f5f  mov     rax, [rcx]
0x180023f62  mov     rax, [rax+28h]
0x180023f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f6b  nop
0x180023f6c  xor     ebx, ebx
0x180023f6e  lea     rcx, [rbp+ppInterface]
0x180023f72  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180023f77  mov     eax, ebx
0x180023f79  mov     rbx, [rsp+30h+arg_8]
0x180023f7e  mov     rdi, [rsp+30h+arg_18]
0x180023f83  add     rsp, 30h
0x180023f87  pop     rbp
0x180023f88  retn
```
