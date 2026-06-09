# LUASetUIAToken2

- ea: `0x18003a2fc`
- end: `0x18003a6e3`
- name: `LUASetUIAToken2`
- size: `999`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014da0`

## callees

- `0x18003a2fc`
- `0x180043f6c`
- `0x180044a20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003a428`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003a46f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003a428`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003a46f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a378`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a3bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a3f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a4e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a57e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a378`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a3bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a3f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a4e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a57e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003a4ae`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003a4ae`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a51a`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a594`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a51a`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a594`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a5ab`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a5ab`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18003a5ef`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18003a61f`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18003a5ef`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18003a61f`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18003a55a`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18003a55a`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003a48f`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003a48f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a4fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a4fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a63f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a65b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a674`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a68d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a63f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a65b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a674`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a68d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a447`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a530`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a447`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a530`

## pseudocode

```c
__int64 __fastcall LUASetUIAToken2(HANDLE *a1)
{
  HANDLE v1; // rdi
  DWORD LastError; // ebx
  PSID *v4; // rsi
  void *v5; // r14
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
  LastError = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  DuplicateTokenHandle = 0;
  cbSid = 4;
  hObject = 0;
  IsMember = 0;
  v4 = 0;
  TokenInformation = 1;
  v5 = 0;
  if ( !GetTokenInformation(v1, TokenUIAccess, &TokenInformation, 4u, &cbSid) )
    goto LABEL_2;
  if ( TokenInformation != 1 )
  {
    if ( !GetTokenInformation(v1, TokenElevationType, &v16, 4u, &cbSid) )
      goto LABEL_2;
    if ( v16 == 3 )
    {
      if ( GetTokenInformation(v1, TokenLinkedToken, &ExistingTokenHandle, 8u, &cbSid) )
      {
        v6 = ExistingTokenHandle;
        if ( !(unsigned int)LUAIsShadowAdminEnabled() )
          goto LABEL_20;
        cbSid = 0;
        if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, 0, &cbSid) )
        {
          LastError = 122;
          goto LABEL_31;
        }
        v7 = LocalAlloc(0, cbSid);
        v5 = v7;
        if ( !v7 )
        {
          LastError = 14;
          goto LABEL_31;
        }
        if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v7, &cbSid)
          && DuplicateToken(v6, SecurityIdentification, &DuplicateTokenHandle)
          && CheckTokenMembership(DuplicateTokenHandle, v5, &IsMember) )
        {
          if ( !IsMember )
            goto LABEL_20;
          if ( GetTokenInformation(v6, (TOKEN_INFORMATION_CLASS)-2, &hObject, 8u, &cbSid) )
          {
            v1 = hObject;
            goto LABEL_20;
          }
        }
LABEL_2:
        LastError = GetLastError();
        goto LABEL_31;
      }
      LastError = GetLastError();
      if ( LastError != 1312 )
        goto LABEL_31;
    }
    v6 = v1;
LABEL_20:
    cbSid = GetSidLengthRequired(1u) + 16;
    v8 = (PSID *)LocalAlloc(0, cbSid);
    v4 = v8;
    if ( v8 )
    {
      *v8 = v8 + 2;
      InitializeSid(v8 + 2, &pIdentifierAuthority, 1u);
      if ( !GetTokenInformation(v6, TokenIntegrityLevel, v4, cbSid, &cbSid) )
        goto LABEL_2;
      cbSid = GetSidLengthRequired(1u) + 16;
      SidSubAuthority = GetSidSubAuthority(*v4, 0);
      v10 = 0x2000;
      if ( *SidSubAuthority < 0x2000 || (v10 = *SidSubAuthority, *SidSubAuthority < 0x3000) )
      {
        v11 = v10 + 16;
        *SidSubAuthority = v11;
        if ( v11 > 0x3000 )
          *SidSubAuthority = 12288;
      }
      *((_DWORD *)v4 + 2) = 96;
      if ( !SetTokenInformation(v1, TokenIntegrityLevel, v4, cbSid) )
        goto LABEL_2;
      TokenInformation = 1;
      cbSid = 4;
      if ( !SetTokenInformation(v1, TokenUIAccess, &TokenInformation, 4u) )
        goto LABEL_2;
      LastError = 0;
      if ( IsMember )
      {
        CloseHandle(*a1);
        *a1 = v1;
        hObject = 0;
      }
    }
    else
    {
      LastError = 8;
    }
  }
LABEL_31:
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
  LocalFree(v5);
  LocalFree(v4);
  return LastError;
}

```

## disassembly

```asm
0x18003a2fc  mov     [rsp-28h+arg_8], rbx
0x18003a301  mov     [rsp-28h+arg_10], rsi
0x18003a306  push    rbp
0x18003a307  push    rdi
0x18003a308  push    r12
0x18003a30a  push    r14
0x18003a30c  push    r15
0x18003a30e  mov     rbp, rsp
0x18003a311  sub     rsp, 70h
0x18003a315  mov     rax, cs:__security_cookie
0x18003a31c  xor     rax, rsp
0x18003a31f  mov     [rbp+var_10], rax
0x18003a323  mov     rdi, [rcx]
0x18003a326  lea     rax, [rbp+cbSid]
0x18003a32a  xor     r12d, r12d
0x18003a32d  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 1000h
0x18003a333  mov     r15, rcx
0x18003a336  mov     [rbp+ExistingTokenHandle], r12
0x18003a33a  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18003a33e  mov     [rbp+var_34], r12d
0x18003a342  mov     ebx, r12d
0x18003a345  mov     dword ptr [rbp+pIdentifierAuthority.Value], r12d
0x18003a349  lea     ecx, [r12+4]
0x18003a34e  mov     [rbp+DuplicateTokenHandle], r12
0x18003a352  mov     [rbp+cbSid], ecx
0x18003a355  lea     edx, [rcx+16h]; TokenInformationClass
0x18003a358  mov     r9d, ecx; TokenInformationLength
0x18003a35b  mov     [rbp+hObject], r12
0x18003a35f  mov     rcx, rdi; TokenHandle
0x18003a362  mov     [rbp+IsMember], r12d
0x18003a366  mov     esi, r12d
0x18003a369  mov     [rbp+TokenInformation], 1
0x18003a370  mov     r14d, r12d
0x18003a373  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003a378  call    cs:__imp_GetTokenInformation
0x18003a37f  nop     dword ptr [rax+rax+00h]
0x18003a384  test    eax, eax
0x18003a386  jnz     short loc_18003A39B
0x18003a388  call    cs:__imp_GetLastError
0x18003a38f  nop     dword ptr [rax+rax+00h]
0x18003a394  mov     ebx, eax
0x18003a396  jmp     loc_18003A652
0x18003a39b  cmp     [rbp+TokenInformation], 1
0x18003a39f  jz      loc_18003A652
0x18003a3a5  mov     r9d, 4; TokenInformationLength
0x18003a3ab  lea     rax, [rbp+cbSid]
0x18003a3af  lea     r8, [rbp+var_34]; TokenInformation
0x18003a3b3  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003a3b8  mov     rcx, rdi; TokenHandle
0x18003a3bb  lea     edx, [r9+0Eh]; TokenInformationClass
0x18003a3bf  call    cs:__imp_GetTokenInformation
0x18003a3c6  nop     dword ptr [rax+rax+00h]
0x18003a3cb  test    eax, eax
0x18003a3cd  jz      short loc_18003A388
0x18003a3cf  cmp     [rbp+var_34], 3
0x18003a3d3  jnz     loc_18003A515
0x18003a3d9  mov     r9d, 8; TokenInformationLength
0x18003a3df  lea     rax, [rbp+cbSid]
0x18003a3e3  lea     r8, [rbp+ExistingTokenHandle]; TokenInformation
0x18003a3e7  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003a3ec  mov     rcx, rdi; TokenHandle
0x18003a3ef  lea     edx, [r9+0Bh]; TokenInformationClass
0x18003a3f3  call    cs:__imp_GetTokenInformation
0x18003a3fa  nop     dword ptr [rax+rax+00h]
0x18003a3ff  test    eax, eax
0x18003a401  jz      loc_18003A4FC
0x18003a407  mov     rbx, [rbp+ExistingTokenHandle]
0x18003a40b  call    LUAIsShadowAdminEnabled
0x18003a410  test    eax, eax
0x18003a412  jz      loc_18003A518
0x18003a418  xor     edx, edx; DomainSid
0x18003a41a  mov     [rbp+cbSid], r12d
0x18003a41e  lea     r9, [rbp+cbSid]; cbSid
0x18003a422  xor     r8d, r8d; pSid
0x18003a425  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18003a428  call    cs:__imp_CreateWellKnownSid
0x18003a42f  nop     dword ptr [rax+rax+00h]
0x18003a434  test    eax, eax
0x18003a436  jz      short loc_18003A442
0x18003a438  mov     ebx, 7Ah ; 'z'
0x18003a43d  jmp     loc_18003A652
0x18003a442  mov     edx, [rbp+cbSid]; uBytes
0x18003a445  xor     ecx, ecx; uFlags
0x18003a447  call    cs:__imp_LocalAlloc
0x18003a44e  nop     dword ptr [rax+rax+00h]
0x18003a453  mov     r14, rax
0x18003a456  test    rax, rax
0x18003a459  jnz     short loc_18003A463
0x18003a45b  lea     ebx, [rax+0Eh]
0x18003a45e  jmp     loc_18003A652
0x18003a463  xor     edx, edx; DomainSid
0x18003a465  lea     r9, [rbp+cbSid]; cbSid
0x18003a469  mov     r8, r14; pSid
0x18003a46c  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18003a46f  call    cs:__imp_CreateWellKnownSid
0x18003a476  nop     dword ptr [rax+rax+00h]
0x18003a47b  test    eax, eax
0x18003a47d  jz      loc_18003A388
0x18003a483  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x18003a487  mov     edx, 1; ImpersonationLevel
0x18003a48c  mov     rcx, rbx; ExistingTokenHandle
0x18003a48f  call    cs:__imp_DuplicateToken
0x18003a496  nop     dword ptr [rax+rax+00h]
0x18003a49b  test    eax, eax
0x18003a49d  jz      loc_18003A388
0x18003a4a3  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x18003a4a7  lea     r8, [rbp+IsMember]; IsMember
0x18003a4ab  mov     rdx, r14; SidToCheck
0x18003a4ae  call    cs:__imp_CheckTokenMembership
0x18003a4b5  nop     dword ptr [rax+rax+00h]
0x18003a4ba  test    eax, eax
0x18003a4bc  jz      loc_18003A388
0x18003a4c2  cmp     [rbp+IsMember], r12d
0x18003a4c6  jz      short loc_18003A518
0x18003a4c8  mov     r9d, 8; TokenInformationLength
0x18003a4ce  lea     rax, [rbp+cbSid]
0x18003a4d2  lea     r8, [rbp+hObject]; TokenInformation
0x18003a4d6  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003a4db  mov     rcx, rbx; TokenHandle
0x18003a4de  lea     edx, [r9-0Ah]; TokenInformationClass
0x18003a4e2  call    cs:__imp_GetTokenInformation
0x18003a4e9  nop     dword ptr [rax+rax+00h]
0x18003a4ee  test    eax, eax
0x18003a4f0  jz      loc_18003A388
0x18003a4f6  mov     rdi, [rbp+hObject]
0x18003a4fa  jmp     short loc_18003A518
0x18003a4fc  call    cs:__imp_GetLastError
0x18003a503  nop     dword ptr [rax+rax+00h]
0x18003a508  mov     ebx, eax
0x18003a50a  cmp     eax, 520h
0x18003a50f  jnz     loc_18003A652
0x18003a515  mov     rbx, rdi
0x18003a518  mov     cl, 1; nSubAuthorityCount
0x18003a51a  call    cs:__imp_GetSidLengthRequired
0x18003a521  nop     dword ptr [rax+rax+00h]
0x18003a526  add     eax, 10h
0x18003a529  xor     ecx, ecx; uFlags
0x18003a52b  mov     edx, eax; uBytes
0x18003a52d  mov     [rbp+cbSid], eax
0x18003a530  call    cs:__imp_LocalAlloc
0x18003a537  nop     dword ptr [rax+rax+00h]
0x18003a53c  mov     rsi, rax
0x18003a53f  test    rax, rax
0x18003a542  jnz     short loc_18003A54C
0x18003a544  lea     ebx, [rax+8]
0x18003a547  jmp     loc_18003A652
0x18003a54c  lea     rcx, [rax+10h]; Sid
0x18003a550  mov     r8b, 1; nSubAuthorityCount
0x18003a553  lea     rdx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18003a557  mov     [rax], rcx
0x18003a55a  call    cs:__imp_InitializeSid
0x18003a561  nop     dword ptr [rax+rax+00h]
0x18003a566  mov     r9d, [rbp+cbSid]; TokenInformationLength
0x18003a56a  lea     rax, [rbp+cbSid]
0x18003a56e  mov     r8, rsi; TokenInformation
0x18003a571  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003a576  mov     edx, 19h; TokenInformationClass
0x18003a57b  mov     rcx, rbx; TokenHandle
0x18003a57e  call    cs:__imp_GetTokenInformation
0x18003a585  nop     dword ptr [rax+rax+00h]
0x18003a58a  test    eax, eax
0x18003a58c  jz      loc_18003A388
0x18003a592  mov     cl, 1; nSubAuthorityCount
0x18003a594  call    cs:__imp_GetSidLengthRequired
0x18003a59b  nop     dword ptr [rax+rax+00h]
0x18003a5a0  add     eax, 10h
0x18003a5a3  xor     edx, edx; nSubAuthority
0x18003a5a5  mov     [rbp+cbSid], eax
0x18003a5a8  mov     rcx, [rsi]; pSid
0x18003a5ab  call    cs:__imp_GetSidSubAuthority
0x18003a5b2  nop     dword ptr [rax+rax+00h]
0x18003a5b7  mov     rcx, rax
0x18003a5ba  mov     edx, 3000h
0x18003a5bf  mov     eax, 2000h
0x18003a5c4  cmp     [rcx], eax
0x18003a5c6  jb      short loc_18003A5CE
0x18003a5c8  mov     eax, [rcx]
0x18003a5ca  cmp     eax, edx
0x18003a5cc  jnb     short loc_18003A5D9
0x18003a5ce  add     eax, 10h
0x18003a5d1  mov     [rcx], eax
0x18003a5d3  cmp     eax, edx
0x18003a5d5  jbe     short loc_18003A5D9
0x18003a5d7  mov     [rcx], edx
0x18003a5d9  mov     dword ptr [rsi+8], 60h ; '`'
0x18003a5e0  mov     r8, rsi; TokenInformation
0x18003a5e3  mov     r9d, [rbp+cbSid]; TokenInformationLength
0x18003a5e7  mov     edx, 19h; TokenInformationClass
0x18003a5ec  mov     rcx, rdi; TokenHandle
0x18003a5ef  call    cs:__imp_SetTokenInformation
0x18003a5f6  nop     dword ptr [rax+rax+00h]
0x18003a5fb  test    eax, eax
0x18003a5fd  jz      loc_18003A388
0x18003a603  mov     eax, 4
0x18003a608  mov     [rbp+TokenInformation], 1
0x18003a60f  mov     r9d, eax; TokenInformationLength
0x18003a612  mov     [rbp+cbSid], eax
0x18003a615  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18003a619  mov     rcx, rdi; TokenHandle
0x18003a61c  lea     edx, [rax+16h]; TokenInformationClass
0x18003a61f  call    cs:__imp_SetTokenInformation
0x18003a626  nop     dword ptr [rax+rax+00h]
0x18003a62b  test    eax, eax
0x18003a62d  jz      loc_18003A388
0x18003a633  mov     ebx, r12d
0x18003a636  cmp     [rbp+IsMember], r12d
0x18003a63a  jz      short loc_18003A652
0x18003a63c  mov     rcx, [r15]; hObject
0x18003a63f  call    cs:__imp_CloseHandle
0x18003a646  nop     dword ptr [rax+rax+00h]
0x18003a64b  mov     [r15], rdi
0x18003a64e  mov     [rbp+hObject], r12
0x18003a652  mov     rcx, [rbp+DuplicateTokenHandle]; hObject
0x18003a656  test    rcx, rcx
0x18003a659  jz      short loc_18003A66B
0x18003a65b  call    cs:__imp_CloseHandle
0x18003a662  nop     dword ptr [rax+rax+00h]
0x18003a667  mov     [rbp+DuplicateTokenHandle], r12
0x18003a66b  mov     rcx, [rbp+ExistingTokenHandle]; hObject
0x18003a66f  test    rcx, rcx
0x18003a672  jz      short loc_18003A684
0x18003a674  call    cs:__imp_CloseHandle
0x18003a67b  nop     dword ptr [rax+rax+00h]
0x18003a680  mov     [rbp+ExistingTokenHandle], r12
0x18003a684  mov     rcx, [rbp+hObject]; hObject
0x18003a688  test    rcx, rcx
0x18003a68b  jz      short loc_18003A69D
0x18003a68d  call    cs:__imp_CloseHandle
0x18003a694  nop     dword ptr [rax+rax+00h]
0x18003a699  mov     [rbp+hObject], r12
0x18003a69d  mov     rcx, r14; hMem
0x18003a6a0  call    cs:__imp_LocalFree
0x18003a6a7  nop     dword ptr [rax+rax+00h]
0x18003a6ac  mov     rcx, rsi; hMem
0x18003a6af  call    cs:__imp_LocalFree
0x18003a6b6  nop     dword ptr [rax+rax+00h]
0x18003a6bb  mov     eax, ebx
0x18003a6bd  mov     rcx, [rbp+var_10]
0x18003a6c1  xor     rcx, rsp; StackCookie
0x18003a6c4  call    __security_check_cookie
0x18003a6c9  lea     r11, [rsp+70h+var_s0]
0x18003a6ce  mov     rbx, [r11+38h]
0x18003a6d2  mov     rsi, [r11+40h]
0x18003a6d6  mov     rsp, r11
0x18003a6d9  pop     r15
0x18003a6db  pop     r14
0x18003a6dd  pop     r12
0x18003a6df  pop     rdi
0x18003a6e0  pop     rbp
0x18003a6e1  retn
```
