# Windows::Internal::AssignedAccess::UserInfoHelper::CheckGroupMembershipForCurrentProcess(void *,bool &)

- ea: `0x18004ff34`
- end: `0x180050083`
- name: `?CheckGroupMembershipForCurrentProcess@UserInfoHelper@AssignedAccess@Internal@Windows@@CAJPEAXAEA_N@Z`
- size: `335`
- prototype: `__int64 __fastcall(PSID SidToCheck, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180050980`

## callees

- `0x18000b694`
- `0x180022cdc`
- `0x180025de8`
- `0x18004ff34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005006c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005006c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004ff6a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004ff6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ff58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ff58`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18004ffa3`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18004ffa3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004ffdb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180050031`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004ffdb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180050031`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005001c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005001c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::UserInfoHelper::CheckGroupMembershipForCurrentProcess(
        PSID SidToCheck,
        bool *a2)
{
  HANDLE CurrentProcess; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int LastError; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  HANDLE TokenInformation; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  WINBOOL IsMember; // [rsp+68h] [rbp+28h] BYREF
  DWORD ReturnLength; // [rsp+70h] [rbp+30h] BYREF
  void *DuplicateTokenHandle; // [rsp+78h] [rbp+38h] BYREF

  *a2 = 0;
  DuplicateTokenHandle = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle) )
  {
    if ( (char *)DuplicateTokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(DuplicateTokenHandle);
    DuplicateTokenHandle = 0;
    if ( !DuplicateToken(TokenHandle, SecurityIdentification, &DuplicateTokenHandle) )
    {
      v6 = 212;
      goto LABEL_7;
    }
    IsMember = 0;
    if ( !CheckTokenMembership(DuplicateTokenHandle, SidToCheck, &IsMember) )
    {
      v6 = 215;
      goto LABEL_7;
    }
    if ( IsMember )
      goto LABEL_15;
    TokenInformation = 0;
    ReturnLength = 0;
    if ( GetTokenInformation(DuplicateTokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength) )
    {
      if ( !CheckTokenMembership(TokenInformation, SidToCheck, &IsMember) )
      {
        v6 = 227;
        goto LABEL_7;
      }
      if ( IsMember )
LABEL_15:
        *a2 = 1;
    }
    else if ( GetLastError() != 1312 )
    {
      v6 = 239;
      goto LABEL_7;
    }
    LastError = 0;
    goto LABEL_17;
  }
  v6 = 211;
LABEL_7:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v6,
                (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
                v5);
LABEL_17:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&DuplicateTokenHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18004ff34  push    rbp
0x18004ff36  push    rbx
0x18004ff37  push    rdi
0x18004ff38  mov     rbp, rsp
0x18004ff3b  sub     rsp, 40h
0x18004ff3f  mov     rdi, rdx
0x18004ff42  mov     byte ptr [rdx], 0
0x18004ff45  mov     rbx, rcx
0x18004ff48  mov     [rbp+DuplicateTokenHandle], 0
0x18004ff50  mov     [rbp+TokenHandle], 0
0x18004ff58  call    cs:__imp_GetCurrentProcess
0x18004ff5e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18004ff62  mov     edx, 0Eh; DesiredAccess
0x18004ff67  mov     rcx, rax; ProcessHandle
0x18004ff6a  call    cs:__imp_OpenProcessToken
0x18004ff70  test    eax, eax
0x18004ff72  jnz     short loc_18004FF7B
0x18004ff74  mov     edx, 0D3h
0x18004ff79  jmp     short loc_18004FFB2
0x18004ff7b  mov     rcx, [rbp+DuplicateTokenHandle]; hObject
0x18004ff7f  lea     rax, [rcx-1]
0x18004ff83  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004ff87  ja      short loc_18004FF8E
0x18004ff89  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18004ff8e  mov     rcx, [rbp+TokenHandle]; ExistingTokenHandle
0x18004ff92  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x18004ff96  mov     edx, 1; ImpersonationLevel
0x18004ff9b  mov     [rbp+DuplicateTokenHandle], 0
0x18004ffa3  call    cs:__imp_DuplicateToken
0x18004ffa9  test    eax, eax
0x18004ffab  jnz     short loc_18004FFC9
0x18004ffad  mov     edx, 0D4h; void *
0x18004ffb2  mov     rcx, [rbp+18h]; this
0x18004ffb6  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004ffbd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004ffc2  mov     ebx, eax
0x18004ffc4  jmp     loc_180050050
0x18004ffc9  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x18004ffcd  lea     r8, [rbp+IsMember]; IsMember
0x18004ffd1  mov     rdx, rbx; SidToCheck
0x18004ffd4  mov     [rbp+IsMember], 0
0x18004ffdb  call    cs:__imp_CheckTokenMembership
0x18004ffe1  test    eax, eax
0x18004ffe3  jnz     short loc_18004FFEC
0x18004ffe5  mov     edx, 0D7h
0x18004ffea  jmp     short loc_18004FFB2
0x18004ffec  cmp     [rbp+IsMember], 0
0x18004fff0  jnz     short loc_18005004B
0x18004fff2  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x18004fff6  lea     rax, [rbp+arg_10]
0x18004fffa  mov     r9d, 8; TokenInformationLength
0x180050000  mov     [rbp+TokenInformation], 0
0x180050008  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18005000c  mov     [rbp+arg_10], 0
0x180050013  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180050018  lea     edx, [r9+0Bh]; TokenInformationClass
0x18005001c  call    cs:__imp_GetTokenInformation
0x180050022  test    eax, eax
0x180050024  jz      short loc_18005006C
0x180050026  mov     rcx, [rbp+TokenInformation]; TokenHandle
0x18005002a  lea     r8, [rbp+IsMember]; IsMember
0x18005002e  mov     rdx, rbx; SidToCheck
0x180050031  call    cs:__imp_CheckTokenMembership
0x180050037  test    eax, eax
0x180050039  jnz     short loc_180050045
0x18005003b  mov     edx, 0E3h
0x180050040  jmp     loc_18004FFB2
0x180050045  cmp     [rbp+IsMember], 0
0x180050049  jz      short loc_18005004E
0x18005004b  mov     byte ptr [rdi], 1
0x18005004e  xor     ebx, ebx
0x180050050  lea     rcx, [rbp+DuplicateTokenHandle]
0x180050054  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180050059  lea     rcx, [rbp+TokenHandle]
0x18005005d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180050062  mov     eax, ebx
0x180050064  add     rsp, 40h
0x180050068  pop     rdi
0x180050069  pop     rbx
0x18005006a  pop     rbp
0x18005006b  retn
0x18005006c  call    cs:__imp_GetLastError
0x180050072  cmp     eax, 520h
0x180050077  jz      short loc_18005004E
0x180050079  mov     edx, 0EFh
0x18005007e  jmp     loc_18004FFB2
```
