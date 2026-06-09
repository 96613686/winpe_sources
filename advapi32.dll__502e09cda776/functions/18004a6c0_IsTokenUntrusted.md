# IsTokenUntrusted

- ea: `0x18004a6c0`
- end: `0x18004a996`
- name: `IsTokenUntrusted`
- size: `726`
- prototype: `BOOL __stdcall(HANDLE TokenHandle)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18004a6c0`
- `0x1800720b0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18004a755`
- `KERNELBASE!LocalAlloc` at `0x18004a79c`
- `KERNELBASE!LocalAlloc` at `0x18004a7e6`
- `KERNELBASE!LocalAlloc` at `0x18004a755`
- `KERNELBASE!LocalAlloc` at `0x18004a79c`
- `KERNELBASE!LocalAlloc` at `0x18004a7e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004a8c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004a8c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004a8ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004a8ad`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004a89d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004a89d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18004a7ba`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18004a7ba`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004a808`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004a808`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004a7d1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004a7d1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004a82d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004a82d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18004a86a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18004a86a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004a739`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004a783`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004a739`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004a783`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18004a909`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18004a909`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18004a87f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18004a87f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004a959`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004a959`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18004a84d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18004a84d`
- `KERNEL32!LocalFree` at `0x18004a92f`
- `KERNEL32!LocalFree` at `0x18004a93e`
- `KERNEL32!LocalFree` at `0x18004a94d`
- `KERNEL32!LocalFree` at `0x18004a92f`
- `KERNEL32!LocalFree` at `0x18004a93e`
- `KERNEL32!LocalFree` at `0x18004a94d`
- `KERNEL32!CloseHandle` at `0x18004a920`
- `KERNEL32!CloseHandle` at `0x18004a920`

## pseudocode

```c
BOOL __stdcall IsTokenUntrusted(HANDLE TokenHandle)
{
  PSID *v2; // rdi
  HLOCAL v3; // rax
  void *v4; // rbx
  DWORD v5; // r14d
  ACL *v6; // rax
  ACL *v7; // rsi
  HANDLE CurrentThread; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp-19h] BYREF
  BOOL AccessStatus; // [rsp+44h] [rbp-15h] BYREF
  DWORD GrantedAccess; // [rsp+48h] [rbp-11h] BYREF
  DWORD PrivilegeSetLength; // [rsp+4Ch] [rbp-Dh] BYREF
  HANDLE TokenHandlea; // [rsp+50h] [rbp-9h] BYREF
  GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp-1h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+68h] [rbp+Fh] BYREF

  AccessStatus = 0;
  GrantedAccess = 0;
  PrivilegeSetLength = 20;
  TokenInformationLength = 0;
  TokenHandlea = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GenericMapping = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v2 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( v2 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
      {
        v3 = LocalAlloc(0x40u, 0x28u);
        v4 = v3;
        if ( v3 )
        {
          if ( InitializeSecurityDescriptor(v3, 1u) )
          {
            v5 = GetLengthSid(*v2) + 16;
            v6 = (ACL *)LocalAlloc(0x40u, v5);
            v7 = v6;
            if ( v6 )
            {
              if ( InitializeAcl(v6, v5, 2u) )
              {
                if ( AddAccessAllowedAce(v7, 2u, 3u, *v2) )
                {
                  if ( SetSecurityDescriptorDacl(v4, 1, v7, 0) )
                  {
                    SetSecurityDescriptorGroup(v4, *v2, 0);
                    SetSecurityDescriptorOwner(v4, *v2, 0);
                    GenericMapping.GenericRead = 1;
                    *(_QWORD *)&GenericMapping.GenericWrite = 2;
                    GenericMapping.GenericAll = 3;
                    if ( ImpersonateLoggedOnUser(TokenHandle) )
                    {
                      CurrentThread = GetCurrentThread();
                      if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandlea) )
                      {
                        if ( !AccessCheck(
                                v4,
                                TokenHandlea,
                                1u,
                                &GenericMapping,
                                &PrivilegeSet,
                                &PrivilegeSetLength,
                                &GrantedAccess,
                                &AccessStatus) )
                          AccessStatus = 0;
                        CloseHandle(TokenHandlea);
                      }
                    }
                  }
                }
              }
              LocalFree(v7);
            }
          }
          LocalFree(v4);
        }
      }
      LocalFree(v2);
    }
  }
  RevertToSelf();
  return !AccessStatus;
}

```

## disassembly

```asm
0x18004a6c0  mov     [rsp-8+arg_8], rbx
0x18004a6c5  mov     [rsp-8+arg_10], rsi
0x18004a6ca  push    rbp
0x18004a6cb  push    rdi
0x18004a6cc  push    r13
0x18004a6ce  push    r14
0x18004a6d0  push    r15
0x18004a6d2  lea     rbp, [rsp-37h]
0x18004a6d7  sub     rsp, 90h
0x18004a6de  mov     rax, cs:__security_cookie
0x18004a6e5  xor     rax, rsp
0x18004a6e8  mov     [rbp+57h+var_30], rax
0x18004a6ec  xor     eax, eax
0x18004a6ee  mov     [rbp+57h+var_6C], 0
0x18004a6f5  xorps   xmm0, xmm0
0x18004a6f8  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x18004a6fb  xor     r9d, r9d; TokenInformationLength
0x18004a6fe  mov     [rbp+57h+var_68], 0
0x18004a705  lea     rax, [rbp+57h+TokenInformationLength]
0x18004a709  mov     [rbp+57h+var_64], 14h
0x18004a710  xor     r8d, r8d; TokenInformation
0x18004a713  mov     [rbp+57h+TokenInformationLength], 0
0x18004a71a  mov     r15, rcx
0x18004a71d  mov     [rbp+57h+TokenHandle], 0
0x18004a725  lea     r13d, [r9+1]
0x18004a729  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18004a72e  mov     edx, r13d; TokenInformationClass
0x18004a731  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x18004a735  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x18004a739  call    cs:__imp_GetTokenInformation
0x18004a740  nop     dword ptr [rax+rax+00h]
0x18004a745  test    eax, eax
0x18004a747  jnz     loc_18004A959
0x18004a74d  mov     edx, [rbp+57h+TokenInformationLength]; uBytes
0x18004a750  lea     esi, [rax+40h]
0x18004a753  mov     ecx, esi; uFlags
0x18004a755  call    cs:__imp_LocalAlloc
0x18004a75c  nop     dword ptr [rax+rax+00h]
0x18004a761  mov     rdi, rax
0x18004a764  test    rax, rax
0x18004a767  jz      loc_18004A959
0x18004a76d  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18004a771  lea     rax, [rbp+57h+TokenInformationLength]
0x18004a775  mov     r8, rdi; TokenInformation
0x18004a778  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18004a77d  mov     edx, r13d; TokenInformationClass
0x18004a780  mov     rcx, r15; TokenHandle
0x18004a783  call    cs:__imp_GetTokenInformation
0x18004a78a  nop     dword ptr [rax+rax+00h]
0x18004a78f  test    eax, eax
0x18004a791  jz      loc_18004A94A
0x18004a797  lea     edx, [rsi-18h]; uBytes
0x18004a79a  mov     ecx, esi; uFlags
0x18004a79c  call    cs:__imp_LocalAlloc
0x18004a7a3  nop     dword ptr [rax+rax+00h]
0x18004a7a8  mov     rbx, rax
0x18004a7ab  test    rax, rax
0x18004a7ae  jz      loc_18004A94A
0x18004a7b4  mov     edx, r13d; dwRevision
0x18004a7b7  mov     rcx, rax; pSecurityDescriptor
0x18004a7ba  call    cs:__imp_InitializeSecurityDescriptor
0x18004a7c1  nop     dword ptr [rax+rax+00h]
0x18004a7c6  test    eax, eax
0x18004a7c8  jz      loc_18004A93B
0x18004a7ce  mov     rcx, [rdi]; pSid
0x18004a7d1  call    cs:__imp_GetLengthSid
0x18004a7d8  nop     dword ptr [rax+rax+00h]
0x18004a7dd  mov     ecx, esi; uFlags
0x18004a7df  lea     r14d, [rax+10h]
0x18004a7e3  mov     edx, r14d; uBytes
0x18004a7e6  call    cs:__imp_LocalAlloc
0x18004a7ed  nop     dword ptr [rax+rax+00h]
0x18004a7f2  mov     rsi, rax
0x18004a7f5  test    rax, rax
0x18004a7f8  jz      loc_18004A93B
0x18004a7fe  lea     r8d, [r13+1]; dwAclRevision
0x18004a802  mov     edx, r14d; nAclLength
0x18004a805  mov     rcx, rax; pAcl
0x18004a808  call    cs:__imp_InitializeAcl
0x18004a80f  nop     dword ptr [rax+rax+00h]
0x18004a814  test    eax, eax
0x18004a816  jz      loc_18004A92C
0x18004a81c  mov     r9, [rdi]; pSid
0x18004a81f  lea     r14d, [r13+1]
0x18004a823  mov     edx, r14d; dwAceRevision
0x18004a826  lea     r8d, [r13+2]; AccessMask
0x18004a82a  mov     rcx, rsi; pAcl
0x18004a82d  call    cs:__imp_AddAccessAllowedAce
0x18004a834  nop     dword ptr [rax+rax+00h]
0x18004a839  test    eax, eax
0x18004a83b  jz      loc_18004A92C
0x18004a841  xor     r9d, r9d; bDaclDefaulted
0x18004a844  mov     r8, rsi; pDacl
0x18004a847  mov     edx, r13d; bDaclPresent
0x18004a84a  mov     rcx, rbx; pSecurityDescriptor
0x18004a84d  call    cs:__imp_SetSecurityDescriptorDacl
0x18004a854  nop     dword ptr [rax+rax+00h]
0x18004a859  test    eax, eax
0x18004a85b  jz      loc_18004A92C
0x18004a861  mov     rdx, [rdi]; pGroup
0x18004a864  xor     r8d, r8d; bGroupDefaulted
0x18004a867  mov     rcx, rbx; pSecurityDescriptor
0x18004a86a  call    cs:__imp_SetSecurityDescriptorGroup
0x18004a871  nop     dword ptr [rax+rax+00h]
0x18004a876  mov     rdx, [rdi]; pOwner
0x18004a879  xor     r8d, r8d; bOwnerDefaulted
0x18004a87c  mov     rcx, rbx; pSecurityDescriptor
0x18004a87f  call    cs:__imp_SetSecurityDescriptorOwner
0x18004a886  nop     dword ptr [rax+rax+00h]
0x18004a88b  mov     rcx, r15; hToken
0x18004a88e  mov     [rbp+57h+GenericMapping.GenericRead], r13d
0x18004a892  mov     qword ptr [rbp+57h+GenericMapping.GenericWrite], r14
0x18004a896  mov     [rbp+57h+GenericMapping.GenericAll], 3
0x18004a89d  call    cs:__imp_ImpersonateLoggedOnUser
0x18004a8a4  nop     dword ptr [rax+rax+00h]
0x18004a8a9  test    eax, eax
0x18004a8ab  jz      short loc_18004A92C
0x18004a8ad  call    cs:__imp_GetCurrentThread
0x18004a8b4  nop     dword ptr [rax+rax+00h]
0x18004a8b9  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18004a8bd  xor     r8d, r8d; OpenAsSelf
0x18004a8c0  mov     rcx, rax; ThreadHandle
0x18004a8c3  lea     edx, [r13+7]; DesiredAccess
0x18004a8c7  call    cs:__imp_OpenThreadToken
0x18004a8ce  nop     dword ptr [rax+rax+00h]
0x18004a8d3  test    eax, eax
0x18004a8d5  jz      short loc_18004A92C
0x18004a8d7  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x18004a8db  lea     rax, [rbp+57h+var_6C]
0x18004a8df  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x18004a8e4  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18004a8e8  lea     rax, [rbp+57h+var_68]
0x18004a8ec  mov     r8d, r13d; DesiredAccess
0x18004a8ef  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x18004a8f4  mov     rcx, rbx; pSecurityDescriptor
0x18004a8f7  lea     rax, [rbp+57h+var_64]
0x18004a8fb  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18004a900  lea     rax, [rbp+57h+PrivilegeSet]
0x18004a904  mov     [rsp+0B0h+ReturnLength], rax; PrivilegeSet
0x18004a909  call    cs:__imp_AccessCheck
0x18004a910  nop     dword ptr [rax+rax+00h]
0x18004a915  test    eax, eax
0x18004a917  jnz     short loc_18004A91C
0x18004a919  mov     [rbp+57h+var_6C], eax
0x18004a91c  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18004a920  call    cs:__imp_CloseHandle
0x18004a927  nop     dword ptr [rax+rax+00h]
0x18004a92c  mov     rcx, rsi; hMem
0x18004a92f  call    cs:__imp_LocalFree
0x18004a936  nop     dword ptr [rax+rax+00h]
0x18004a93b  mov     rcx, rbx; hMem
0x18004a93e  call    cs:__imp_LocalFree
0x18004a945  nop     dword ptr [rax+rax+00h]
0x18004a94a  mov     rcx, rdi; hMem
0x18004a94d  call    cs:__imp_LocalFree
0x18004a954  nop     dword ptr [rax+rax+00h]
0x18004a959  call    cs:__imp_RevertToSelf
0x18004a960  nop     dword ptr [rax+rax+00h]
0x18004a965  xor     eax, eax
0x18004a967  cmp     [rbp+57h+var_6C], eax
0x18004a96a  setz    al
0x18004a96d  mov     rcx, [rbp+57h+var_30]
0x18004a971  xor     rcx, rsp; StackCookie
0x18004a974  call    __security_check_cookie
0x18004a979  lea     r11, [rsp+0B0h+var_20]
0x18004a981  mov     rbx, [r11+38h]
0x18004a985  mov     rsi, [r11+40h]
0x18004a989  mov     rsp, r11
0x18004a98c  pop     r15
0x18004a98e  pop     r14
0x18004a990  pop     r13
0x18004a992  pop     rdi
0x18004a993  pop     rbp
0x18004a994  retn
```
