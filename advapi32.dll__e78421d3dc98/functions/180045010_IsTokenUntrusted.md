# IsTokenUntrusted

- ea: `0x180045010`
- end: `0x180045267`
- name: `IsTokenUntrusted`
- size: `599`
- prototype: `BOOL __stdcall(HANDLE TokenHandle)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180045010`
- `0x180065090`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18004509f`
- `KERNELBASE!LocalAlloc` at `0x1800450da`
- `KERNELBASE!LocalAlloc` at `0x180045112`
- `KERNELBASE!LocalAlloc` at `0x18004509f`
- `KERNELBASE!LocalAlloc` at `0x1800450da`
- `KERNELBASE!LocalAlloc` at `0x180045112`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800451c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800451c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800451af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800451af`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800451a5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800451a5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800450f2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800450f2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004512e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004512e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180045103`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180045103`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004514d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004514d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18004517e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18004517e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045089`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800450c7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045089`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800450c7`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800451ff`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800451ff`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18004518d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18004518d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180045231`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180045231`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180045167`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180045167`
- `KERNEL32!LocalFree` at `0x180045219`
- `KERNEL32!LocalFree` at `0x180045222`
- `KERNEL32!LocalFree` at `0x18004522b`
- `KERNEL32!LocalFree` at `0x180045219`
- `KERNEL32!LocalFree` at `0x180045222`
- `KERNEL32!LocalFree` at `0x18004522b`
- `KERNEL32!CloseHandle` at `0x180045210`
- `KERNEL32!CloseHandle` at `0x180045210`

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
0x180045010  mov     [rsp-8+arg_8], rbx
0x180045015  mov     [rsp-8+arg_10], rsi
0x18004501a  push    rbp
0x18004501b  push    rdi
0x18004501c  push    r13
0x18004501e  push    r14
0x180045020  push    r15
0x180045022  lea     rbp, [rsp-37h]
0x180045027  sub     rsp, 90h
0x18004502e  mov     rax, cs:__security_cookie
0x180045035  xor     rax, rsp
0x180045038  mov     [rbp+57h+var_30], rax
0x18004503c  xor     eax, eax
0x18004503e  mov     [rbp+57h+var_6C], 0
0x180045045  xorps   xmm0, xmm0
0x180045048  mov     [rbp+57h+PrivilegeSet.Privilege.Attributes], eax
0x18004504b  xor     r9d, r9d; TokenInformationLength
0x18004504e  mov     [rbp+57h+var_68], 0
0x180045055  lea     rax, [rbp+57h+TokenInformationLength]
0x180045059  mov     [rbp+57h+var_64], 14h
0x180045060  xor     r8d, r8d; TokenInformation
0x180045063  mov     [rbp+57h+TokenInformationLength], 0
0x18004506a  mov     r15, rcx
0x18004506d  mov     [rbp+57h+TokenHandle], 0
0x180045075  lea     r13d, [r9+1]
0x180045079  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18004507e  mov     edx, r13d; TokenInformationClass
0x180045081  movups  xmmword ptr [rbp+57h+PrivilegeSet.PrivilegeCount], xmm0
0x180045085  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x180045089  call    cs:__imp_GetTokenInformation
0x18004508f  test    eax, eax
0x180045091  jnz     loc_180045231
0x180045097  mov     edx, [rbp+57h+TokenInformationLength]; uBytes
0x18004509a  lea     esi, [rax+40h]
0x18004509d  mov     ecx, esi; uFlags
0x18004509f  call    cs:__imp_LocalAlloc
0x1800450a5  mov     rdi, rax
0x1800450a8  test    rax, rax
0x1800450ab  jz      loc_180045231
0x1800450b1  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1800450b5  lea     rax, [rbp+57h+TokenInformationLength]
0x1800450b9  mov     r8, rdi; TokenInformation
0x1800450bc  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800450c1  mov     edx, r13d; TokenInformationClass
0x1800450c4  mov     rcx, r15; TokenHandle
0x1800450c7  call    cs:__imp_GetTokenInformation
0x1800450cd  test    eax, eax
0x1800450cf  jz      loc_180045228
0x1800450d5  lea     edx, [rsi-18h]; uBytes
0x1800450d8  mov     ecx, esi; uFlags
0x1800450da  call    cs:__imp_LocalAlloc
0x1800450e0  mov     rbx, rax
0x1800450e3  test    rax, rax
0x1800450e6  jz      loc_180045228
0x1800450ec  mov     edx, r13d; dwRevision
0x1800450ef  mov     rcx, rax; pSecurityDescriptor
0x1800450f2  call    cs:__imp_InitializeSecurityDescriptor
0x1800450f8  test    eax, eax
0x1800450fa  jz      loc_18004521F
0x180045100  mov     rcx, [rdi]; pSid
0x180045103  call    cs:__imp_GetLengthSid
0x180045109  mov     ecx, esi; uFlags
0x18004510b  lea     r14d, [rax+10h]
0x18004510f  mov     edx, r14d; uBytes
0x180045112  call    cs:__imp_LocalAlloc
0x180045118  mov     rsi, rax
0x18004511b  test    rax, rax
0x18004511e  jz      loc_18004521F
0x180045124  lea     r8d, [r13+1]; dwAclRevision
0x180045128  mov     edx, r14d; nAclLength
0x18004512b  mov     rcx, rax; pAcl
0x18004512e  call    cs:__imp_InitializeAcl
0x180045134  test    eax, eax
0x180045136  jz      loc_180045216
0x18004513c  mov     r9, [rdi]; pSid
0x18004513f  lea     r14d, [r13+1]
0x180045143  mov     edx, r14d; dwAceRevision
0x180045146  lea     r8d, [r13+2]; AccessMask
0x18004514a  mov     rcx, rsi; pAcl
0x18004514d  call    cs:__imp_AddAccessAllowedAce
0x180045153  test    eax, eax
0x180045155  jz      loc_180045216
0x18004515b  xor     r9d, r9d; bDaclDefaulted
0x18004515e  mov     r8, rsi; pDacl
0x180045161  mov     edx, r13d; bDaclPresent
0x180045164  mov     rcx, rbx; pSecurityDescriptor
0x180045167  call    cs:__imp_SetSecurityDescriptorDacl
0x18004516d  test    eax, eax
0x18004516f  jz      loc_180045216
0x180045175  mov     rdx, [rdi]; pGroup
0x180045178  xor     r8d, r8d; bGroupDefaulted
0x18004517b  mov     rcx, rbx; pSecurityDescriptor
0x18004517e  call    cs:__imp_SetSecurityDescriptorGroup
0x180045184  mov     rdx, [rdi]; pOwner
0x180045187  xor     r8d, r8d; bOwnerDefaulted
0x18004518a  mov     rcx, rbx; pSecurityDescriptor
0x18004518d  call    cs:__imp_SetSecurityDescriptorOwner
0x180045193  mov     rcx, r15; hToken
0x180045196  mov     [rbp+57h+GenericMapping.GenericRead], r13d
0x18004519a  mov     qword ptr [rbp+57h+GenericMapping.GenericWrite], r14
0x18004519e  mov     [rbp+57h+GenericMapping.GenericAll], 3
0x1800451a5  call    cs:__imp_ImpersonateLoggedOnUser
0x1800451ab  test    eax, eax
0x1800451ad  jz      short loc_180045216
0x1800451af  call    cs:__imp_GetCurrentThread
0x1800451b5  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800451b9  xor     r8d, r8d; OpenAsSelf
0x1800451bc  mov     rcx, rax; ThreadHandle
0x1800451bf  lea     edx, [r13+7]; DesiredAccess
0x1800451c3  call    cs:__imp_OpenThreadToken
0x1800451c9  test    eax, eax
0x1800451cb  jz      short loc_180045216
0x1800451cd  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x1800451d1  lea     rax, [rbp+57h+var_6C]
0x1800451d5  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x1800451da  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1800451de  lea     rax, [rbp+57h+var_68]
0x1800451e2  mov     r8d, r13d; DesiredAccess
0x1800451e5  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x1800451ea  mov     rcx, rbx; pSecurityDescriptor
0x1800451ed  lea     rax, [rbp+57h+var_64]
0x1800451f1  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800451f6  lea     rax, [rbp+57h+PrivilegeSet]
0x1800451fa  mov     [rsp+0B0h+ReturnLength], rax; PrivilegeSet
0x1800451ff  call    cs:__imp_AccessCheck
0x180045205  test    eax, eax
0x180045207  jnz     short loc_18004520C
0x180045209  mov     [rbp+57h+var_6C], eax
0x18004520c  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180045210  call    cs:__imp_CloseHandle
0x180045216  mov     rcx, rsi; hMem
0x180045219  call    cs:__imp_LocalFree
0x18004521f  mov     rcx, rbx; hMem
0x180045222  call    cs:__imp_LocalFree
0x180045228  mov     rcx, rdi; hMem
0x18004522b  call    cs:__imp_LocalFree
0x180045231  call    cs:__imp_RevertToSelf
0x180045237  xor     eax, eax
0x180045239  cmp     [rbp+57h+var_6C], eax
0x18004523c  setz    al
0x18004523f  mov     rcx, [rbp+57h+var_30]
0x180045243  xor     rcx, rsp; StackCookie
0x180045246  call    __security_check_cookie
0x18004524b  lea     r11, [rsp+0B0h+var_20]
0x180045253  mov     rbx, [r11+38h]
0x180045257  mov     rsi, [r11+40h]
0x18004525b  mov     rsp, r11
0x18004525e  pop     r15
0x180045260  pop     r14
0x180045262  pop     r13
0x180045264  pop     rdi
0x180045265  pop     rbp
0x180045266  retn
```
