# Execution::ActivationManagerShim::GetHostIdForSingleInstanceFgActivation(unsigned __int64 *,ushort const *,unsigned __int64 *)

- ea: `0x18006e4f8`
- end: `0x18006e734`
- name: `?GetHostIdForSingleInstanceFgActivation@ActivationManagerShim@Execution@@AEAAJPEA_KPEBG0@Z`
- size: `572`
- prototype: `__int64 __fastcall(Execution::ActivationManagerShim *__hidden this, unsigned __int64 *, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18006bcf8`
- `0x180071540`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180027ce8`
- `0x180044514`
- `0x18005ae90`
- `0x18005ba40`
- `0x18006e4f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006e66d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006e66d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18006e67a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18006e67a`
- `ntdll!NtOpenProcessTokenEx` at `0x18006e55f`
- `ntdll!NtOpenProcessTokenEx` at `0x18006e55f`
- `ntdll!NtQueryInformationToken` at `0x18006e63c`
- `ntdll!NtQueryInformationToken` at `0x18006e63c`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x18006e6ee`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x18006e6ee`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x18006e6bd`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x18006e6bd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006e5e8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006e5e8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006e592`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006e592`

## pseudocode

```c
__int64 __fastcall Execution::ActivationManagerShim::GetHostIdForSingleInstanceFgActivation(
        Execution::ActivationManagerShim *this,
        unsigned __int64 *a2,
        const unsigned __int16 *a3,
        unsigned __int64 *a4)
{
  NTSTATUS v7; // eax
  int v8; // ebx
  int v9; // eax
  int v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  NTSTATUS v13; // ebx
  __int64 v14; // rbx
  DWORD CurrentProcessId; // eax
  int v16; // eax
  __int64 v17; // rdx
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  DWORD pSessionId; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v22; // [rsp+40h] [rbp-C0h] BYREF
  ULONG v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[1056]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD TokenInformation[12]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  v24 = 0;
  v22 = 0;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  v7 = NtOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0, &TokenHandle);
  if ( v7 < 0 )
  {
    v8 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x724,
           (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
           (const char *)(unsigned int)v7,
           ReturnLength);
LABEL_5:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_18;
  }
  v9 = UMgrQueryUserContext(TokenHandle, &v24);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x725,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)(unsigned int)v9,
      ReturnLength);
    goto LABEL_5;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v22,
    0);
  v10 = UMgrQueryUserToken(v24, &v22);
  v8 = v10;
  if ( v10 < 0 )
  {
    v11 = (unsigned int)v10;
    v12 = 1832;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
      (const char *)v11,
      ReturnLength);
    goto LABEL_18;
  }
  v23 = 0;
  v13 = NtQueryInformationToken(v22, TokenUser, TokenInformation, 0x54u, &v23);
  if ( v13 < 0 )
  {
    v8 = v13 | 0x10000000;
    if ( v8 >= 0 )
      goto LABEL_18;
    v11 = (unsigned int)v8;
    v12 = 1837;
    goto LABEL_8;
  }
  v14 = TokenInformation[0];
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, &pSessionId);
  *((_DWORD *)this + 36) = 36;
  memset_0(v25, 0, 0x418u);
  v16 = HamHostIdInitializeKey(a3, v14, pSessionId, 0);
  if ( v16 >= 0 )
  {
    v16 = HamHostIdFindOrCreate(v25, a4);
    if ( v16 >= 0 )
    {
      *((_DWORD *)this + 36) = 0;
      v8 = 0;
      goto LABEL_18;
    }
    v17 = 1845;
  }
  else
  {
    v17 = 1844;
  }
  v8 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)v17,
         (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationmanagershim.cpp",
         (const char *)(unsigned int)v16,
         0);
LABEL_18:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006e4f8  push    rbp
0x18006e4fa  push    rbx
0x18006e4fb  push    rsi
0x18006e4fc  push    rdi
0x18006e4fd  push    r14
0x18006e4ff  lea     rbp, [rsp-3F0h]
0x18006e507  sub     rsp, 4F0h
0x18006e50e  mov     rax, cs:__security_cookie
0x18006e515  xor     rax, rsp
0x18006e518  mov     [rbp+410h+var_30], rax
0x18006e51f  mov     rdi, rcx
0x18006e522  mov     [rsp+510h+var_4C0], 0
0x18006e52b  lea     rcx, [rsp+510h+TokenHandle]
0x18006e530  mov     [rsp+510h+var_4D0], 0
0x18006e539  xor     edx, edx
0x18006e53b  mov     [rsp+510h+TokenHandle], 0
0x18006e544  mov     rsi, r9
0x18006e547  mov     r14, r8
0x18006e54a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006e54f  xor     r8d, r8d; HandleAttributes
0x18006e552  lea     r9, [rsp+510h+TokenHandle]; TokenHandle
0x18006e557  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18006e55b  lea     edx, [r8+8]; DesiredAccess
0x18006e55f  call    cs:__imp_NtOpenProcessTokenEx
0x18006e565  test    eax, eax
0x18006e567  jns     short loc_18006E588
0x18006e569  mov     rcx, [rbp+418h]; this
0x18006e570  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006e577  mov     r9d, eax; char *
0x18006e57a  mov     edx, 724h; void *
0x18006e57f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18006e584  mov     ebx, eax
0x18006e586  jmp     short loc_18006E5B9
0x18006e588  mov     rcx, [rsp+510h+TokenHandle]
0x18006e58d  lea     rdx, [rsp+510h+var_4C0]
0x18006e592  call    cs:__imp_UMgrQueryUserContext
0x18006e598  mov     ebx, eax
0x18006e59a  test    eax, eax
0x18006e59c  jns     short loc_18006E5C8
0x18006e59e  mov     rcx, [rbp+418h]; this
0x18006e5a5  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006e5ac  mov     r9d, eax; char *
0x18006e5af  mov     edx, 725h; void *
0x18006e5b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e5b9  lea     rcx, [rsp+510h+TokenHandle]
0x18006e5be  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006e5c3  jmp     loc_18006E70B
0x18006e5c8  lea     rcx, [rsp+510h+TokenHandle]
0x18006e5cd  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006e5d2  xor     edx, edx
0x18006e5d4  lea     rcx, [rsp+510h+var_4D0]
0x18006e5d9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006e5de  mov     rcx, [rsp+510h+var_4C0]
0x18006e5e3  lea     rdx, [rsp+510h+var_4D0]
0x18006e5e8  call    cs:__imp_UMgrQueryUserToken
0x18006e5ee  mov     ebx, eax
0x18006e5f0  test    eax, eax
0x18006e5f2  jns     short loc_18006E614
0x18006e5f4  mov     r9d, eax; char *
0x18006e5f7  mov     edx, 728h; void *
0x18006e5fc  mov     rcx, [rbp+418h]; this
0x18006e603  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006e60a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e60f  jmp     loc_18006E70B
0x18006e614  mov     rcx, [rsp+510h+var_4D0]; TokenHandle
0x18006e619  lea     rax, [rsp+510h+var_4C8]
0x18006e61e  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18006e624  mov     [rsp+510h+var_4C8], 0
0x18006e62c  lea     r8, [rbp+410h+TokenInformation]; TokenInformation
0x18006e633  mov     [rsp+510h+ReturnLength], rax; ReturnLength
0x18006e638  lea     edx, [r9-53h]; TokenInformationClass
0x18006e63c  call    cs:__imp_NtQueryInformationToken
0x18006e642  mov     ebx, eax
0x18006e644  test    eax, eax
0x18006e646  jns     short loc_18006E65E
0x18006e648  or      ebx, 10000000h
0x18006e64e  jge     loc_18006E70B
0x18006e654  mov     r9d, ebx
0x18006e657  mov     edx, 72Dh
0x18006e65c  jmp     short loc_18006E5FC
0x18006e65e  mov     rbx, [rbp+410h+TokenInformation]
0x18006e665  mov     [rsp+510h+pSessionId], 0
0x18006e66d  call    cs:__imp_GetCurrentProcessId
0x18006e673  mov     ecx, eax; dwProcessId
0x18006e675  lea     rdx, [rsp+510h+pSessionId]; pSessionId
0x18006e67a  call    cs:__imp_ProcessIdToSessionId
0x18006e680  xor     edx, edx; Val
0x18006e682  mov     dword ptr [rdi+90h], 24h ; '$'
0x18006e68c  mov     r8d, 418h; Size
0x18006e692  lea     rcx, [rsp+510h+var_4B0]; void *
0x18006e697  call    memset_0
0x18006e69c  mov     r8d, [rsp+510h+pSessionId]
0x18006e6a1  lea     rax, [rsp+510h+var_4B0]
0x18006e6a6  mov     [rsp+510h+var_4E8], rax
0x18006e6ab  xor     r9d, r9d
0x18006e6ae  mov     rdx, rbx
0x18006e6b1  mov     [rsp+510h+ReturnLength], 0; int
0x18006e6ba  mov     rcx, r14
0x18006e6bd  call    cs:__imp_HamHostIdInitializeKey
0x18006e6c3  test    eax, eax
0x18006e6c5  jns     short loc_18006E6E6
0x18006e6c7  mov     edx, 734h; void *
0x18006e6cc  mov     rcx, [rbp+418h]; this
0x18006e6d3  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18006e6da  mov     r9d, eax; char *
0x18006e6dd  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18006e6e2  mov     ebx, eax
0x18006e6e4  jmp     short loc_18006E70B
0x18006e6e6  mov     rdx, rsi
0x18006e6e9  lea     rcx, [rsp+510h+var_4B0]
0x18006e6ee  call    cs:__imp_HamHostIdFindOrCreate
0x18006e6f4  test    eax, eax
0x18006e6f6  jns     short loc_18006E6FF
0x18006e6f8  mov     edx, 735h
0x18006e6fd  jmp     short loc_18006E6CC
0x18006e6ff  mov     dword ptr [rdi+90h], 0
0x18006e709  xor     ebx, ebx
0x18006e70b  lea     rcx, [rsp+510h+var_4D0]
0x18006e710  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006e715  mov     eax, ebx
0x18006e717  mov     rcx, [rbp+410h+var_30]
0x18006e71e  xor     rcx, rsp; StackCookie
0x18006e721  call    __security_check_cookie
0x18006e726  add     rsp, 4F0h
0x18006e72d  pop     r14
0x18006e72f  pop     rdi
0x18006e730  pop     rsi
0x18006e731  pop     rbx
0x18006e732  pop     rbp
0x18006e733  retn
```
