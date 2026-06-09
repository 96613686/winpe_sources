# LUASetUIAToken2

- ea: `0x18002d574`
- end: `0x18002d8c4`
- name: `LUASetUIAToken2`
- size: `848`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800163c0`

## callees

- `0x18001bbe0`
- `0x18002d574`
- `0x18002f3dc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002d6f6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002d6f6`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18002d6dd`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18002d6dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d5ed`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d62b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d659`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d724`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d7a2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d5ed`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d62b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d659`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d724`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d7a2`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d688`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d6c3`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d688`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002d6c3`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002d750`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002d7b2`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002d750`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18002d7b2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d7c3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18002d7c3`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002d784`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18002d784`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18002d801`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18002d82b`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18002d801`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18002d82b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d738`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d845`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d85b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d86e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d881`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d845`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d85b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d86e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d881`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d6a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d760`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d6a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d760`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d88e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d897`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d88e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d897`

## pseudocode

```c
__int64 __fastcall LUASetUIAToken2(HANDLE *a1)
{
  HANDLE v1; // rdi
  PSID *v3; // rsi
  void *v4; // r14
  DWORD LastError; // ebx
  HANDLE v6; // rbx
  HLOCAL v7; // rax
  PSID *v8; // rax
  PDWORD SidSubAuthority; // rcx
  int v10; // eax
  unsigned int v11; // eax
  DWORD cbSid; // [rsp+30h] [rbp-40h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-3Ch] BYREF
  WINBOOL IsMember; // [rsp+38h] [rbp-38h] BYREF
  int v16; // [rsp+3Ch] [rbp-34h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-30h] BYREF
  void *DuplicateTokenHandle; // [rsp+48h] [rbp-28h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+50h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+58h] [rbp-18h] BYREF

  v1 = *a1;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  ExistingTokenHandle = 0;
  v16 = 0;
  v3 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  DuplicateTokenHandle = 0;
  cbSid = 4;
  hObject = 0;
  IsMember = 0;
  v4 = 0;
  TokenInformation = 1;
  if ( !GetTokenInformation(v1, TokenUIAccess, &TokenInformation, 4u, &cbSid) )
    goto LABEL_2;
  LastError = 0;
  if ( TokenInformation != 1 )
  {
    if ( !GetTokenInformation(v1, TokenElevationType, &v16, 4u, &cbSid) )
      goto LABEL_2;
    if ( v16 == 3 )
    {
      if ( GetTokenInformation(v1, TokenLinkedToken, &ExistingTokenHandle, 8u, &cbSid) )
      {
        v6 = ExistingTokenHandle;
        if ( (unsigned int)LUAIsShadowAdminEnabled() )
        {
          cbSid = 0;
          if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, 0, &cbSid) )
          {
            LastError = 122;
            goto LABEL_32;
          }
          v7 = LocalAlloc(0, cbSid);
          v4 = v7;
          if ( !v7 )
          {
            LastError = 14;
            goto LABEL_32;
          }
          if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v7, &cbSid)
            || !DuplicateToken(v6, SecurityIdentification, &DuplicateTokenHandle)
            || !CheckTokenMembership(DuplicateTokenHandle, v4, &IsMember) )
          {
            goto LABEL_2;
          }
          if ( IsMember )
          {
            if ( !GetTokenInformation(v6, (TOKEN_INFORMATION_CLASS)-2, &hObject, 8u, &cbSid) )
              goto LABEL_2;
            v1 = hObject;
          }
        }
LABEL_20:
        cbSid = GetSidLengthRequired(1u) + 16;
        v8 = (PSID *)LocalAlloc(0, cbSid);
        v3 = v8;
        if ( !v8 )
        {
          LastError = 8;
          goto LABEL_32;
        }
        *v8 = v8 + 2;
        InitializeSid(v8 + 2, &pIdentifierAuthority, 1u);
        if ( !GetTokenInformation(v6, TokenIntegrityLevel, v3, cbSid, &cbSid) )
          goto LABEL_2;
        cbSid = GetSidLengthRequired(1u) + 16;
        SidSubAuthority = GetSidSubAuthority(*v3, 0);
        v10 = 0x2000;
        if ( *SidSubAuthority >= 0x2000 )
        {
          if ( *SidSubAuthority >= 0x3000 )
            goto LABEL_28;
          v10 = *SidSubAuthority;
        }
        v11 = v10 + 16;
        *SidSubAuthority = v11;
        if ( v11 > 0x3000 )
          *SidSubAuthority = 12288;
LABEL_28:
        *((_DWORD *)v3 + 2) = 96;
        if ( SetTokenInformation(v1, TokenIntegrityLevel, v3, cbSid) )
        {
          TokenInformation = 1;
          cbSid = 4;
          if ( SetTokenInformation(v1, TokenUIAccess, &TokenInformation, 4u) )
          {
            LastError = 0;
            if ( IsMember )
            {
              CloseHandle(*a1);
              *a1 = v1;
              hObject = 0;
            }
            goto LABEL_32;
          }
        }
LABEL_2:
        LastError = GetLastError();
        goto LABEL_32;
      }
      LastError = GetLastError();
      if ( LastError != 1312 )
        goto LABEL_32;
    }
    v6 = v1;
    goto LABEL_20;
  }
LABEL_32:
  if ( DuplicateTokenHandle )
  {
    CloseHandle(DuplicateTokenHandle);
    DuplicateTokenHandle = 0;
  }
  if ( ExistingTokenHandle )
  {
    CloseHandle(ExistingTokenHandle);
    ExistingTokenHandle = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  LocalFree(v4);
  LocalFree(v3);
  return LastError;
}

```

## disassembly

```asm
0x18002d574  mov     [rsp-28h+arg_8], rbx
0x18002d579  mov     [rsp-28h+arg_10], rsi
0x18002d57e  push    rbp
0x18002d57f  push    rdi
0x18002d580  push    r12
0x18002d582  push    r14
0x18002d584  push    r15
0x18002d586  mov     rbp, rsp
0x18002d589  sub     rsp, 70h
0x18002d58d  mov     rax, cs:__security_cookie
0x18002d594  xor     rax, rsp
0x18002d597  mov     [rbp+var_10], rax
0x18002d59b  mov     rdi, [rcx]
0x18002d59e  lea     rax, [rbp+cbSid]
0x18002d5a2  xor     r12d, r12d
0x18002d5a5  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 1000h
0x18002d5ab  mov     r15, rcx
0x18002d5ae  mov     [rbp+ExistingTokenHandle], r12
0x18002d5b2  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002d5b6  mov     [rbp+var_34], r12d
0x18002d5ba  mov     esi, r12d
0x18002d5bd  mov     dword ptr [rbp+pIdentifierAuthority.Value], r12d
0x18002d5c1  lea     ecx, [r12+4]
0x18002d5c6  mov     [rbp+DuplicateTokenHandle], r12
0x18002d5ca  mov     [rbp+cbSid], ecx
0x18002d5cd  lea     edx, [rcx+16h]; TokenInformationClass
0x18002d5d0  mov     r9d, ecx; TokenInformationLength
0x18002d5d3  mov     [rbp+hObject], r12
0x18002d5d7  mov     rcx, rdi; TokenHandle
0x18002d5da  mov     [rbp+IsMember], r12d
0x18002d5de  mov     r14d, r12d
0x18002d5e1  mov     [rbp+TokenInformation], 1
0x18002d5e8  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18002d5ed  call    cs:__imp_GetTokenInformation
0x18002d5f3  test    eax, eax
0x18002d5f5  jnz     short loc_18002D604
0x18002d5f7  call    cs:__imp_GetLastError
0x18002d5fd  mov     ebx, eax
0x18002d5ff  jmp     loc_18002D852
0x18002d604  cmp     [rbp+TokenInformation], 1
0x18002d608  mov     ebx, r12d
0x18002d60b  jz      loc_18002D852
0x18002d611  mov     r9d, 4; TokenInformationLength
0x18002d617  lea     rax, [rbp+cbSid]
0x18002d61b  lea     r8, [rbp+var_34]; TokenInformation
0x18002d61f  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18002d624  mov     rcx, rdi; TokenHandle
0x18002d627  lea     edx, [r9+0Eh]; TokenInformationClass
0x18002d62b  call    cs:__imp_GetTokenInformation
0x18002d631  test    eax, eax
0x18002d633  jz      short loc_18002D5F7
0x18002d635  cmp     [rbp+var_34], 3
0x18002d639  jnz     loc_18002D74B
0x18002d63f  mov     r9d, 8; TokenInformationLength
0x18002d645  lea     rax, [rbp+cbSid]
0x18002d649  lea     r8, [rbp+ExistingTokenHandle]; TokenInformation
0x18002d64d  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18002d652  mov     rcx, rdi; TokenHandle
0x18002d655  lea     edx, [r9+0Bh]; TokenInformationClass
0x18002d659  call    cs:__imp_GetTokenInformation
0x18002d65f  test    eax, eax
0x18002d661  jz      loc_18002D738
0x18002d667  mov     rbx, [rbp+ExistingTokenHandle]
0x18002d66b  call    LUAIsShadowAdminEnabled
0x18002d670  test    eax, eax
0x18002d672  jz      loc_18002D74E
0x18002d678  xor     edx, edx; DomainSid
0x18002d67a  mov     [rbp+cbSid], r12d
0x18002d67e  lea     r9, [rbp+cbSid]; cbSid
0x18002d682  xor     r8d, r8d; pSid
0x18002d685  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18002d688  call    cs:__imp_CreateWellKnownSid
0x18002d68e  test    eax, eax
0x18002d690  jz      short loc_18002D69C
0x18002d692  mov     ebx, 7Ah ; 'z'
0x18002d697  jmp     loc_18002D852
0x18002d69c  mov     edx, [rbp+cbSid]; uBytes
0x18002d69f  xor     ecx, ecx; uFlags
0x18002d6a1  call    cs:__imp_LocalAlloc
0x18002d6a7  mov     r14, rax
0x18002d6aa  test    rax, rax
0x18002d6ad  jnz     short loc_18002D6B7
0x18002d6af  lea     ebx, [rax+0Eh]
0x18002d6b2  jmp     loc_18002D852
0x18002d6b7  xor     edx, edx; DomainSid
0x18002d6b9  lea     r9, [rbp+cbSid]; cbSid
0x18002d6bd  mov     r8, r14; pSid
0x18002d6c0  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18002d6c3  call    cs:__imp_CreateWellKnownSid
0x18002d6c9  test    eax, eax
0x18002d6cb  jz      loc_18002D5F7
0x18002d6d1  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x18002d6d5  mov     edx, 1; ImpersonationLevel
0x18002d6da  mov     rcx, rbx; ExistingTokenHandle
0x18002d6dd  call    cs:__imp_DuplicateToken
0x18002d6e3  test    eax, eax
0x18002d6e5  jz      loc_18002D5F7
0x18002d6eb  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x18002d6ef  lea     r8, [rbp+IsMember]; IsMember
0x18002d6f3  mov     rdx, r14; SidToCheck
0x18002d6f6  call    cs:__imp_CheckTokenMembership
0x18002d6fc  test    eax, eax
0x18002d6fe  jz      loc_18002D5F7
0x18002d704  cmp     [rbp+IsMember], r12d
0x18002d708  jz      short loc_18002D74E
0x18002d70a  mov     r9d, 8; TokenInformationLength
0x18002d710  lea     rax, [rbp+cbSid]
0x18002d714  lea     r8, [rbp+hObject]; TokenInformation
0x18002d718  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18002d71d  mov     rcx, rbx; TokenHandle
0x18002d720  lea     edx, [r9-0Ah]; TokenInformationClass
0x18002d724  call    cs:__imp_GetTokenInformation
0x18002d72a  test    eax, eax
0x18002d72c  jz      loc_18002D5F7
0x18002d732  mov     rdi, [rbp+hObject]
0x18002d736  jmp     short loc_18002D74E
0x18002d738  call    cs:__imp_GetLastError
0x18002d73e  mov     ebx, eax
0x18002d740  cmp     eax, 520h
0x18002d745  jnz     loc_18002D852
0x18002d74b  mov     rbx, rdi
0x18002d74e  mov     cl, 1; nSubAuthorityCount
0x18002d750  call    cs:__imp_GetSidLengthRequired
0x18002d756  add     eax, 10h
0x18002d759  xor     ecx, ecx; uFlags
0x18002d75b  mov     edx, eax; uBytes
0x18002d75d  mov     [rbp+cbSid], eax
0x18002d760  call    cs:__imp_LocalAlloc
0x18002d766  mov     rsi, rax
0x18002d769  test    rax, rax
0x18002d76c  jnz     short loc_18002D776
0x18002d76e  lea     ebx, [rax+8]
0x18002d771  jmp     loc_18002D852
0x18002d776  lea     rcx, [rax+10h]; Sid
0x18002d77a  mov     r8b, 1; nSubAuthorityCount
0x18002d77d  lea     rdx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18002d781  mov     [rax], rcx
0x18002d784  call    cs:__imp_InitializeSid
0x18002d78a  mov     r9d, [rbp+cbSid]; TokenInformationLength
0x18002d78e  lea     rax, [rbp+cbSid]
0x18002d792  mov     r8, rsi; TokenInformation
0x18002d795  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18002d79a  mov     edx, 19h; TokenInformationClass
0x18002d79f  mov     rcx, rbx; TokenHandle
0x18002d7a2  call    cs:__imp_GetTokenInformation
0x18002d7a8  test    eax, eax
0x18002d7aa  jz      loc_18002D5F7
0x18002d7b0  mov     cl, 1; nSubAuthorityCount
0x18002d7b2  call    cs:__imp_GetSidLengthRequired
0x18002d7b8  add     eax, 10h
0x18002d7bb  xor     edx, edx; nSubAuthority
0x18002d7bd  mov     [rbp+cbSid], eax
0x18002d7c0  mov     rcx, [rsi]; pSid
0x18002d7c3  call    cs:__imp_GetSidSubAuthority
0x18002d7c9  mov     rcx, rax
0x18002d7cc  mov     edx, 3000h
0x18002d7d1  mov     eax, 2000h
0x18002d7d6  cmp     [rcx], eax
0x18002d7d8  jb      short loc_18002D7E0
0x18002d7da  cmp     [rcx], edx
0x18002d7dc  jnb     short loc_18002D7EB
0x18002d7de  mov     eax, [rcx]
0x18002d7e0  add     eax, 10h
0x18002d7e3  mov     [rcx], eax
0x18002d7e5  cmp     eax, edx
0x18002d7e7  jbe     short loc_18002D7EB
0x18002d7e9  mov     [rcx], edx
0x18002d7eb  mov     dword ptr [rsi+8], 60h ; '`'
0x18002d7f2  mov     r8, rsi; TokenInformation
0x18002d7f5  mov     r9d, [rbp+cbSid]; TokenInformationLength
0x18002d7f9  mov     edx, 19h; TokenInformationClass
0x18002d7fe  mov     rcx, rdi; TokenHandle
0x18002d801  call    cs:__imp_SetTokenInformation
0x18002d807  test    eax, eax
0x18002d809  jz      loc_18002D5F7
0x18002d80f  mov     eax, 4
0x18002d814  mov     [rbp+TokenInformation], 1
0x18002d81b  mov     r9d, eax; TokenInformationLength
0x18002d81e  mov     [rbp+cbSid], eax
0x18002d821  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002d825  mov     rcx, rdi; TokenHandle
0x18002d828  lea     edx, [rax+16h]; TokenInformationClass
0x18002d82b  call    cs:__imp_SetTokenInformation
0x18002d831  test    eax, eax
0x18002d833  jz      loc_18002D5F7
0x18002d839  mov     ebx, r12d
0x18002d83c  cmp     [rbp+IsMember], r12d
0x18002d840  jz      short loc_18002D852
0x18002d842  mov     rcx, [r15]; hObject
0x18002d845  call    cs:__imp_CloseHandle
0x18002d84b  mov     [r15], rdi
0x18002d84e  mov     [rbp+hObject], r12
0x18002d852  mov     rcx, [rbp+DuplicateTokenHandle]; hObject
0x18002d856  test    rcx, rcx
0x18002d859  jz      short loc_18002D865
0x18002d85b  call    cs:__imp_CloseHandle
0x18002d861  mov     [rbp+DuplicateTokenHandle], r12
0x18002d865  mov     rcx, [rbp+ExistingTokenHandle]; hObject
0x18002d869  test    rcx, rcx
0x18002d86c  jz      short loc_18002D878
0x18002d86e  call    cs:__imp_CloseHandle
0x18002d874  mov     [rbp+ExistingTokenHandle], r12
0x18002d878  mov     rcx, [rbp+hObject]; hObject
0x18002d87c  test    rcx, rcx
0x18002d87f  jz      short loc_18002D88B
0x18002d881  call    cs:__imp_CloseHandle
0x18002d887  mov     [rbp+hObject], r12
0x18002d88b  mov     rcx, r14; hMem
0x18002d88e  call    cs:__imp_LocalFree
0x18002d894  mov     rcx, rsi; hMem
0x18002d897  call    cs:__imp_LocalFree
0x18002d89d  mov     eax, ebx
0x18002d89f  mov     rcx, [rbp+var_10]
0x18002d8a3  xor     rcx, rsp; StackCookie
0x18002d8a6  call    __security_check_cookie
0x18002d8ab  lea     r11, [rsp+70h+var_s0]
0x18002d8b0  mov     rbx, [r11+38h]
0x18002d8b4  mov     rsi, [r11+40h]
0x18002d8b8  mov     rsp, r11
0x18002d8bb  pop     r15
0x18002d8bd  pop     r14
0x18002d8bf  pop     r12
0x18002d8c1  pop     rdi
0x18002d8c2  pop     rbp
0x18002d8c3  retn
```
