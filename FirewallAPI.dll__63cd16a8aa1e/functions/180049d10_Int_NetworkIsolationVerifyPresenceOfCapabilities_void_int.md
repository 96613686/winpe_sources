# Int_NetworkIsolationVerifyPresenceOfCapabilities(void *,int *)

- ea: `0x180049d10`
- end: `0x180049f01`
- name: `?Int_NetworkIsolationVerifyPresenceOfCapabilities@@YAKPEAXPEAH@Z`
- size: `497`
- prototype: `unsigned int __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180053e20`
- `0x180053fa0`

## callees

- `0x180005954`
- `0x1800277b0`
- `0x180049d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049da5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049da5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e9f`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180049e95`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180049e95`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180049e0e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180049e0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180049d63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180049d63`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180049d9b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180049d9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180049d89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180049d89`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180049d7b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180049d7b`
- `fwbase!FwCloseHandle` at `0x180049e4c`
- `fwbase!FwCloseHandle` at `0x180049eda`
- `fwbase!FwCloseHandle` at `0x180049e4c`
- `fwbase!FwCloseHandle` at `0x180049eda`

## pseudocode

```c
__int64 __fastcall Int_NetworkIsolationVerifyPresenceOfCapabilities(PSECURITY_DESCRIPTOR pSecurityDescriptor, int *a2)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  FwPolicy2 *v7; // rcx
  __int64 v8; // rdx
  void *v9; // rdx
  void *TokenHandle; // [rsp+40h] [rbp-9h] BYREF
  void *phNewToken; // [rsp+48h] [rbp-1h] BYREF
  WINBOOL AccessStatus; // [rsp+50h] [rbp+7h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp+Bh] BYREF
  DWORD PrivilegeSetLength; // [rsp+58h] [rbp+Fh] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+17h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp+27h] BYREF

  PrivilegeSetLength = 20;
  TokenHandle = 0;
  phNewToken = 0;
  *(_QWORD *)&GenericMapping.GenericRead = 0;
  *(_QWORD *)&GenericMapping.GenericExecute = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GrantedAccess = 0;
  AccessStatus = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    v9 = TokenHandle;
LABEL_13:
    if ( AccessCheck(
           pSecurityDescriptor,
           v9,
           0x20000u,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      LastError = 0;
      *a2 = AccessStatus;
    }
    else
    {
      LastError = GetLastError();
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 523;
        goto LABEL_6;
      }
    }
    goto LABEL_18;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xEu, &TokenHandle) )
  {
    LastError = GetLastError();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 520;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, LastError);
      goto LABEL_18;
    }
    goto LABEL_18;
  }
  if ( DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
  {
    FwCloseHandle(TokenHandle);
    v9 = phNewToken;
    TokenHandle = phNewToken;
    phNewToken = 0;
    goto LABEL_13;
  }
  LastError = GetLastError();
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v8 = 521;
    goto LABEL_6;
  }
LABEL_18:
  if ( TokenHandle )
    FwCloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180049d10  mov     [rsp-8+arg_10], rbx
0x180049d15  push    rbp
0x180049d16  push    rsi
0x180049d17  push    rdi
0x180049d18  lea     rbp, [rsp-47h]
0x180049d1d  sub     rsp, 90h
0x180049d24  mov     rax, cs:__security_cookie
0x180049d2b  xor     rax, rsp
0x180049d2e  mov     [rbp+57h+var_18], rax
0x180049d32  xor     esi, esi
0x180049d34  mov     [rbp+57h+PrivilegeSetLength], 14h
0x180049d3b  xorps   xmm0, xmm0
0x180049d3e  mov     [rbp+57h+TokenHandle], rsi
0x180049d42  xor     eax, eax
0x180049d44  mov     [rbp+57h+var_58], rsi
0x180049d48  mov     qword ptr [rbp+57h+GenericMapping.GenericRead], rsi
0x180049d4c  mov     rdi, rdx
0x180049d4f  mov     qword ptr [rbp+57h+GenericMapping.GenericExecute], rsi
0x180049d53  mov     rbx, rcx
0x180049d56  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x180049d5a  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x180049d5d  mov     [rbp+57h+var_4C], esi
0x180049d60  mov     [rbp+57h+var_50], esi
0x180049d63  call    cs:__imp_GetCurrentThread
0x180049d69  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180049d6d  mov     edx, 0Ch; DesiredAccess
0x180049d72  mov     rcx, rax; ThreadHandle
0x180049d75  mov     r8d, 1; OpenAsSelf
0x180049d7b  call    cs:__imp_OpenThreadToken
0x180049d81  test    eax, eax
0x180049d83  jnz     loc_180049E60
0x180049d89  call    cs:__imp_GetCurrentProcess
0x180049d8f  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180049d93  mov     edx, 0Eh; DesiredAccess
0x180049d98  mov     rcx, rax; ProcessHandle
0x180049d9b  call    cs:__imp_OpenProcessToken
0x180049da1  test    eax, eax
0x180049da3  jnz     short loc_180049DEB
0x180049da5  call    cs:__imp_GetLastError
0x180049dab  mov     ebx, eax
0x180049dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180049db4  lea     rax, WPP_GLOBAL_Control
0x180049dbb  cmp     rcx, rax
0x180049dbe  jz      loc_180049ED1
0x180049dc4  test    byte ptr [rcx+1Ch], 1
0x180049dc8  jz      loc_180049ED1
0x180049dce  mov     edx, 208h
0x180049dd3  mov     rcx, [rcx+10h]
0x180049dd7  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180049dde  mov     r9d, ebx
0x180049de1  call    WPP_SF_d
0x180049de6  jmp     loc_180049ED1
0x180049deb  mov     rcx, [rbp+57h+TokenHandle]; hExistingToken
0x180049def  lea     rax, [rbp+57h+var_58]
0x180049df3  mov     [rsp+0A0h+phNewToken], rax; phNewToken
0x180049df8  mov     r9d, 2; ImpersonationLevel
0x180049dfe  xor     r8d, r8d; lpTokenAttributes
0x180049e01  mov     [rsp+0A0h+TokenType], 2; TokenType
0x180049e09  mov     edx, 0Ch; dwDesiredAccess
0x180049e0e  call    cs:__imp_DuplicateTokenEx
0x180049e14  test    eax, eax
0x180049e16  jnz     short loc_180049E48
0x180049e18  call    cs:__imp_GetLastError
0x180049e1e  mov     ebx, eax
0x180049e20  mov     rcx, cs:WPP_GLOBAL_Control
0x180049e27  lea     rax, WPP_GLOBAL_Control
0x180049e2e  cmp     rcx, rax
0x180049e31  jz      loc_180049ED1
0x180049e37  test    byte ptr [rcx+1Ch], 1
0x180049e3b  jz      loc_180049ED1
0x180049e41  mov     edx, 209h
0x180049e46  jmp     short loc_180049DD3
0x180049e48  mov     rcx, [rbp+57h+TokenHandle]
0x180049e4c  call    cs:__imp_FwCloseHandle
0x180049e52  mov     rdx, [rbp+57h+var_58]
0x180049e56  mov     [rbp+57h+TokenHandle], rdx
0x180049e5a  mov     [rbp+57h+var_58], rsi
0x180049e5e  jmp     short loc_180049E64
0x180049e60  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x180049e64  lea     rax, [rbp+57h+var_50]
0x180049e68  mov     r8d, 20000h; DesiredAccess
0x180049e6e  mov     [rsp+0A0h+AccessStatus], rax; AccessStatus
0x180049e73  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180049e77  lea     rax, [rbp+57h+var_4C]
0x180049e7b  mov     rcx, rbx; pSecurityDescriptor
0x180049e7e  mov     [rsp+0A0h+GrantedAccess], rax; GrantedAccess
0x180049e83  lea     rax, [rbp+57h+PrivilegeSetLength]
0x180049e87  mov     [rsp+0A0h+phNewToken], rax; PrivilegeSetLength
0x180049e8c  lea     rax, [rbp+57h+PrivilegeSet]
0x180049e90  mov     qword ptr [rsp+0A0h+TokenType], rax; PrivilegeSet
0x180049e95  call    cs:__imp_AccessCheck
0x180049e9b  test    eax, eax
0x180049e9d  jnz     short loc_180049ECA
0x180049e9f  call    cs:__imp_GetLastError
0x180049ea5  mov     ebx, eax
0x180049ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x180049eae  lea     rax, WPP_GLOBAL_Control
0x180049eb5  cmp     rcx, rax
0x180049eb8  jz      short loc_180049ED1
0x180049eba  test    byte ptr [rcx+1Ch], 1
0x180049ebe  jz      short loc_180049ED1
0x180049ec0  mov     edx, 20Bh
0x180049ec5  jmp     loc_180049DD3
0x180049eca  mov     eax, [rbp+57h+var_50]
0x180049ecd  mov     ebx, esi
0x180049ecf  mov     [rdi], eax
0x180049ed1  mov     rcx, [rbp+57h+TokenHandle]
0x180049ed5  test    rcx, rcx
0x180049ed8  jz      short loc_180049EE0
0x180049eda  call    cs:__imp_FwCloseHandle
0x180049ee0  mov     eax, ebx
0x180049ee2  mov     rcx, [rbp+57h+var_18]
0x180049ee6  xor     rcx, rsp; StackCookie
0x180049ee9  call    __security_check_cookie
0x180049eee  mov     rbx, [rsp+0A0h+arg_10]
0x180049ef6  add     rsp, 90h
0x180049efd  pop     rdi
0x180049efe  pop     rsi
0x180049eff  pop     rbp
0x180049f00  retn
```
