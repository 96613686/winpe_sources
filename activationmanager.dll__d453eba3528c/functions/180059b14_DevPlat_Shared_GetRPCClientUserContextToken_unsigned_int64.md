# DevPlat::Shared::GetRPCClientUserContextToken(unsigned __int64 *)

- ea: `0x180059b14`
- end: `0x180059cd1`
- name: `?GetRPCClientUserContextToken@Shared@DevPlat@@YAJPEA_K@Z`
- size: `445`
- prototype: `int(DevPlat::Shared *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180059920`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180027ce8`
- `0x180044408`
- `0x180044514`
- `0x1800445ac`
- `0x180059b14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180059b8e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180059b8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180059b78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180059b78`
- `ntdll!NtOpenProcessTokenEx` at `0x180059c3d`
- `ntdll!NtOpenProcessTokenEx` at `0x180059c3d`
- `RPCRT4!RpcImpersonateClient` at `0x180059b5f`
- `RPCRT4!RpcImpersonateClient` at `0x180059b5f`
- `RPCRT4!RpcRevertToSelf` at `0x180059bad`
- `RPCRT4!RpcRevertToSelf` at `0x180059bc3`
- `RPCRT4!RpcRevertToSelf` at `0x180059bad`
- `RPCRT4!RpcRevertToSelf` at `0x180059bc3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180059bd9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180059bd9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DevPlat::Shared::GetRPCClientUserContextToken(DevPlat::Shared *this, unsigned __int64 *a2)
{
  unsigned int LastError; // ebx
  unsigned int v4; // eax
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  int v7; // eax
  NTSTATUS v8; // eax
  unsigned int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  void *TokenHandle; // [rsp+30h] [rbp+10h] BYREF
  __int64 v13; // [rsp+38h] [rbp+18h] BYREF

  if ( this )
  {
    *(_QWORD *)this = 0;
    TokenHandle = 0;
    v4 = RpcImpersonateClient(0);
    if ( v4 )
    {
      if ( v4 != 1725 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x2C,
                      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\rpcutilsuser.cpp",
                      (const char *)v4,
                      savedregs);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return LastError;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      v8 = NtOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0, &TokenHandle);
      if ( v8 < 0 )
      {
        LastError = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x28,
                      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\rpcutilsuser.cpp",
                      (const char *)(unsigned int)v8,
                      savedregs);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return LastError;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x24,
                      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\rpcutilsuser.cpp",
                      v6);
        RpcRevertToSelf();
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        return LastError;
      }
      RpcRevertToSelf();
    }
    v13 = 0;
    v7 = UMgrQueryUserContext(TokenHandle, &v13);
    LastError = v7;
    if ( v7 >= 0 )
    {
      *(_QWORD *)this = v13;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return 0;
    }
    if ( v7 == -2147023584 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      return 1;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\rpcutilsuser.cpp",
      (const char *)(unsigned int)v7,
      savedregs);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  else
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\rpcutilsuser.cpp",
      (const char *)0x80070057LL,
      savedregs);
  }
  return LastError;
}

```

## disassembly

```asm
0x180059b14  mov     [rsp-8+arg_10], rbx
0x180059b19  mov     [rsp-8+arg_18], rdi
0x180059b1e  push    rbp; unsigned int
0x180059b1f  mov     rbp, rsp
0x180059b22  sub     rsp, 20h
0x180059b26  mov     rdi, rcx
0x180059b29  test    rcx, rcx
0x180059b2c  jnz     short loc_180059B4E
0x180059b2e  mov     rcx, [rbp+8]; this
0x180059b32  mov     ebx, 80070057h
0x180059b37  mov     r9d, ebx; char *
0x180059b3a  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180059b41  lea     edx, [rdi+18h]; void *
0x180059b44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059b49  jmp     loc_180059CBF
0x180059b4e  mov     qword ptr [rcx], 0
0x180059b55  mov     [rbp+TokenHandle], 0
0x180059b5d  xor     ecx, ecx; BindingHandle
0x180059b5f  call    cs:__imp_RpcImpersonateClient
0x180059b65  test    eax, eax
0x180059b67  jnz     loc_180059C1C
0x180059b6d  xor     edx, edx
0x180059b6f  lea     rcx, [rbp+TokenHandle]
0x180059b73  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180059b78  call    cs:__imp_GetCurrentThread
0x180059b7e  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180059b82  mov     edx, 8; DesiredAccess
0x180059b87  lea     r8d, [rdx-7]; OpenAsSelf
0x180059b8b  mov     rcx, rax; ThreadHandle
0x180059b8e  call    cs:__imp_OpenThreadToken
0x180059b94  test    eax, eax
0x180059b96  jnz     short loc_180059BC3
0x180059b98  mov     rcx, [rbp+8]; this
0x180059b9c  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180059ba3  lea     edx, [rax+24h]; void *
0x180059ba6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180059bab  mov     ebx, eax
0x180059bad  call    cs:__imp_RpcRevertToSelf
0x180059bb3  nop
0x180059bb4  lea     rcx, [rbp+TokenHandle]
0x180059bb8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180059bbd  nop
0x180059bbe  jmp     loc_180059CBF
0x180059bc3  call    cs:__imp_RpcRevertToSelf
0x180059bc9  mov     [rbp+arg_8], 0
0x180059bd1  lea     rdx, [rbp+arg_8]
0x180059bd5  mov     rcx, [rbp+TokenHandle]
0x180059bd9  call    cs:__imp_UMgrQueryUserContext
0x180059bdf  mov     ebx, eax
0x180059be1  test    eax, eax
0x180059be3  jns     loc_180059C6D
0x180059be9  cmp     eax, 80070520h
0x180059bee  jz      loc_180059C75
0x180059bf4  mov     rcx, [rbp+8]; this
0x180059bf8  mov     r9d, eax; char *
0x180059bfb  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180059c02  mov     edx, 31h ; '1'; void *
0x180059c07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059c0c  nop
0x180059c0d  lea     rcx, [rbp+TokenHandle]
0x180059c11  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180059c16  nop
0x180059c17  jmp     loc_180059CBF
0x180059c1c  cmp     eax, 6BDh
0x180059c21  jnz     short loc_180059C9B
0x180059c23  xor     edx, edx
0x180059c25  lea     rcx, [rbp+TokenHandle]
0x180059c29  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180059c2e  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180059c32  xor     r8d, r8d; HandleAttributes
0x180059c35  lea     edx, [r8+8]; DesiredAccess
0x180059c39  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180059c3d  call    cs:__imp_NtOpenProcessTokenEx
0x180059c43  test    eax, eax
0x180059c45  jns     short loc_180059BC9
0x180059c47  mov     rcx, [rbp+8]; this
0x180059c4b  mov     r9d, eax; char *
0x180059c4e  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180059c55  mov     edx, 28h ; '('; void *
0x180059c5a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180059c5f  mov     ebx, eax
0x180059c61  lea     rcx, [rbp+TokenHandle]
0x180059c65  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180059c6a  nop
0x180059c6b  jmp     short loc_180059CBF
0x180059c6d  cmp     ebx, 80070520h
0x180059c73  jnz     short loc_180059C86
0x180059c75  lea     rcx, [rbp+TokenHandle]
0x180059c79  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180059c7e  nop
0x180059c7f  mov     eax, 1
0x180059c84  jmp     short loc_180059CC1
0x180059c86  mov     rax, [rbp+arg_8]
0x180059c8a  mov     [rdi], rax
0x180059c8d  lea     rcx, [rbp+TokenHandle]
0x180059c91  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180059c96  nop
0x180059c97  xor     eax, eax
0x180059c99  jmp     short loc_180059CC1
0x180059c9b  mov     rcx, [rbp+8]; this
0x180059c9f  mov     r9d, eax; char *
0x180059ca2  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180059ca9  mov     edx, 2Ch ; ','; void *
0x180059cae  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180059cb3  mov     ebx, eax
0x180059cb5  lea     rcx, [rbp+TokenHandle]
0x180059cb9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180059cbe  nop
0x180059cbf  mov     eax, ebx
0x180059cc1  mov     rbx, [rsp+20h+arg_10]
0x180059cc6  mov     rdi, [rsp+20h+arg_18]
0x180059ccb  add     rsp, 20h
0x180059ccf  pop     rbp
0x180059cd0  retn
```
