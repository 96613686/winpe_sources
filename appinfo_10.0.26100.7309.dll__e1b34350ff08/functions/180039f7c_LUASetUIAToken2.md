# LUASetUIAToken2

- ea: `0x180039f7c`
- end: `0x18003a363`
- name: `LUASetUIAToken2`
- size: `999`
- prototype: `__int64 __fastcall(HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014da0`

## callees

- `0x180039f7c`
- `0x180043a2c`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003a0a8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003a0ef`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003a0a8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003a0ef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039ff8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a03f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a073`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a162`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a1fe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039ff8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a03f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a073`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a162`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003a1fe`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003a12e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003a12e`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a19a`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a214`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a19a`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003a214`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a22b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003a22b`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18003a26f`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18003a29f`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18003a26f`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18003a29f`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18003a1da`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18003a1da`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003a10f`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003a10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a17c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a2bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a2db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a2f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a30d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a2bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a2db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a2f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a30d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a320`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a32f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a320`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a32f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a0c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a1b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a0c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a1b0`

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
0x180039f7c  mov     [rsp-28h+arg_8], rbx
0x180039f81  mov     [rsp-28h+arg_10], rsi
0x180039f86  push    rbp
0x180039f87  push    rdi
0x180039f88  push    r12
0x180039f8a  push    r14
0x180039f8c  push    r15
0x180039f8e  mov     rbp, rsp
0x180039f91  sub     rsp, 70h
0x180039f95  mov     rax, cs:__security_cookie
0x180039f9c  xor     rax, rsp
0x180039f9f  mov     [rbp+var_10], rax
0x180039fa3  mov     rdi, [rcx]
0x180039fa6  lea     rax, [rbp+cbSid]
0x180039faa  xor     r12d, r12d
0x180039fad  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 1000h
0x180039fb3  mov     r15, rcx
0x180039fb6  mov     [rbp+ExistingTokenHandle], r12
0x180039fba  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180039fbe  mov     [rbp+var_34], r12d
0x180039fc2  mov     ebx, r12d
0x180039fc5  mov     dword ptr [rbp+pIdentifierAuthority.Value], r12d
0x180039fc9  lea     ecx, [r12+4]
0x180039fce  mov     [rbp+DuplicateTokenHandle], r12
0x180039fd2  mov     [rbp+cbSid], ecx
0x180039fd5  lea     edx, [rcx+16h]; TokenInformationClass
0x180039fd8  mov     r9d, ecx; TokenInformationLength
0x180039fdb  mov     [rbp+hObject], r12
0x180039fdf  mov     rcx, rdi; TokenHandle
0x180039fe2  mov     [rbp+IsMember], r12d
0x180039fe6  mov     esi, r12d
0x180039fe9  mov     [rbp+TokenInformation], 1
0x180039ff0  mov     r14d, r12d
0x180039ff3  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180039ff8  call    cs:__imp_GetTokenInformation
0x180039fff  nop     dword ptr [rax+rax+00h]
0x18003a004  test    eax, eax
0x18003a006  jnz     short loc_18003A01B
0x18003a008  call    cs:__imp_GetLastError
0x18003a00f  nop     dword ptr [rax+rax+00h]
0x18003a014  mov     ebx, eax
0x18003a016  jmp     loc_18003A2D2
0x18003a01b  cmp     [rbp+TokenInformation], 1
0x18003a01f  jz      loc_18003A2D2
0x18003a025  mov     r9d, 4; TokenInformationLength
0x18003a02b  lea     rax, [rbp+cbSid]
0x18003a02f  lea     r8, [rbp+var_34]; TokenInformation
0x18003a033  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003a038  mov     rcx, rdi; TokenHandle
0x18003a03b  lea     edx, [r9+0Eh]; TokenInformationClass
0x18003a03f  call    cs:__imp_GetTokenInformation
0x18003a046  nop     dword ptr [rax+rax+00h]
0x18003a04b  test    eax, eax
0x18003a04d  jz      short loc_18003A008
0x18003a04f  cmp     [rbp+var_34], 3
0x18003a053  jnz     loc_18003A195
0x18003a059  mov     r9d, 8; TokenInformationLength
0x18003a05f  lea     rax, [rbp+cbSid]
0x18003a063  lea     r8, [rbp+ExistingTokenHandle]; TokenInformation
0x18003a067  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003a06c  mov     rcx, rdi; TokenHandle
0x18003a06f  lea     edx, [r9+0Bh]; TokenInformationClass
0x18003a073  call    cs:__imp_GetTokenInformation
0x18003a07a  nop     dword ptr [rax+rax+00h]
0x18003a07f  test    eax, eax
0x18003a081  jz      loc_18003A17C
0x18003a087  mov     rbx, [rbp+ExistingTokenHandle]
0x18003a08b  call    LUAIsShadowAdminEnabled
0x18003a090  test    eax, eax
0x18003a092  jz      loc_18003A198
0x18003a098  xor     edx, edx; DomainSid
0x18003a09a  mov     [rbp+cbSid], r12d
0x18003a09e  lea     r9, [rbp+cbSid]; cbSid
0x18003a0a2  xor     r8d, r8d; pSid
0x18003a0a5  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18003a0a8  call    cs:__imp_CreateWellKnownSid
0x18003a0af  nop     dword ptr [rax+rax+00h]
0x18003a0b4  test    eax, eax
0x18003a0b6  jz      short loc_18003A0C2
0x18003a0b8  mov     ebx, 7Ah ; 'z'
0x18003a0bd  jmp     loc_18003A2D2
0x18003a0c2  mov     edx, [rbp+cbSid]; uBytes
0x18003a0c5  xor     ecx, ecx; uFlags
0x18003a0c7  call    cs:__imp_LocalAlloc
0x18003a0ce  nop     dword ptr [rax+rax+00h]
0x18003a0d3  mov     r14, rax
0x18003a0d6  test    rax, rax
0x18003a0d9  jnz     short loc_18003A0E3
0x18003a0db  lea     ebx, [rax+0Eh]
0x18003a0de  jmp     loc_18003A2D2
0x18003a0e3  xor     edx, edx; DomainSid
0x18003a0e5  lea     r9, [rbp+cbSid]; cbSid
0x18003a0e9  mov     r8, r14; pSid
0x18003a0ec  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18003a0ef  call    cs:__imp_CreateWellKnownSid
0x18003a0f6  nop     dword ptr [rax+rax+00h]
0x18003a0fb  test    eax, eax
0x18003a0fd  jz      loc_18003A008
0x18003a103  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x18003a107  mov     edx, 1; ImpersonationLevel
0x18003a10c  mov     rcx, rbx; ExistingTokenHandle
0x18003a10f  call    cs:__imp_DuplicateToken
0x18003a116  nop     dword ptr [rax+rax+00h]
0x18003a11b  test    eax, eax
0x18003a11d  jz      loc_18003A008
0x18003a123  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x18003a127  lea     r8, [rbp+IsMember]; IsMember
0x18003a12b  mov     rdx, r14; SidToCheck
0x18003a12e  call    cs:__imp_CheckTokenMembership
0x18003a135  nop     dword ptr [rax+rax+00h]
0x18003a13a  test    eax, eax
0x18003a13c  jz      loc_18003A008
0x18003a142  cmp     [rbp+IsMember], r12d
0x18003a146  jz      short loc_18003A198
0x18003a148  mov     r9d, 8; TokenInformationLength
0x18003a14e  lea     rax, [rbp+cbSid]
0x18003a152  lea     r8, [rbp+hObject]; TokenInformation
0x18003a156  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003a15b  mov     rcx, rbx; TokenHandle
0x18003a15e  lea     edx, [r9-0Ah]; TokenInformationClass
0x18003a162  call    cs:__imp_GetTokenInformation
0x18003a169  nop     dword ptr [rax+rax+00h]
0x18003a16e  test    eax, eax
0x18003a170  jz      loc_18003A008
0x18003a176  mov     rdi, [rbp+hObject]
0x18003a17a  jmp     short loc_18003A198
0x18003a17c  call    cs:__imp_GetLastError
0x18003a183  nop     dword ptr [rax+rax+00h]
0x18003a188  mov     ebx, eax
0x18003a18a  cmp     eax, 520h
0x18003a18f  jnz     loc_18003A2D2
0x18003a195  mov     rbx, rdi
0x18003a198  mov     cl, 1; nSubAuthorityCount
0x18003a19a  call    cs:__imp_GetSidLengthRequired
0x18003a1a1  nop     dword ptr [rax+rax+00h]
0x18003a1a6  add     eax, 10h
0x18003a1a9  xor     ecx, ecx; uFlags
0x18003a1ab  mov     edx, eax; uBytes
0x18003a1ad  mov     [rbp+cbSid], eax
0x18003a1b0  call    cs:__imp_LocalAlloc
0x18003a1b7  nop     dword ptr [rax+rax+00h]
0x18003a1bc  mov     rsi, rax
0x18003a1bf  test    rax, rax
0x18003a1c2  jnz     short loc_18003A1CC
0x18003a1c4  lea     ebx, [rax+8]
0x18003a1c7  jmp     loc_18003A2D2
0x18003a1cc  lea     rcx, [rax+10h]; Sid
0x18003a1d0  mov     r8b, 1; nSubAuthorityCount
0x18003a1d3  lea     rdx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18003a1d7  mov     [rax], rcx
0x18003a1da  call    cs:__imp_InitializeSid
0x18003a1e1  nop     dword ptr [rax+rax+00h]
0x18003a1e6  mov     r9d, [rbp+cbSid]; TokenInformationLength
0x18003a1ea  lea     rax, [rbp+cbSid]
0x18003a1ee  mov     r8, rsi; TokenInformation
0x18003a1f1  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003a1f6  mov     edx, 19h; TokenInformationClass
0x18003a1fb  mov     rcx, rbx; TokenHandle
0x18003a1fe  call    cs:__imp_GetTokenInformation
0x18003a205  nop     dword ptr [rax+rax+00h]
0x18003a20a  test    eax, eax
0x18003a20c  jz      loc_18003A008
0x18003a212  mov     cl, 1; nSubAuthorityCount
0x18003a214  call    cs:__imp_GetSidLengthRequired
0x18003a21b  nop     dword ptr [rax+rax+00h]
0x18003a220  add     eax, 10h
0x18003a223  xor     edx, edx; nSubAuthority
0x18003a225  mov     [rbp+cbSid], eax
0x18003a228  mov     rcx, [rsi]; pSid
0x18003a22b  call    cs:__imp_GetSidSubAuthority
0x18003a232  nop     dword ptr [rax+rax+00h]
0x18003a237  mov     rcx, rax
0x18003a23a  mov     edx, 3000h
0x18003a23f  mov     eax, 2000h
0x18003a244  cmp     [rcx], eax
0x18003a246  jb      short loc_18003A24E
0x18003a248  mov     eax, [rcx]
0x18003a24a  cmp     eax, edx
0x18003a24c  jnb     short loc_18003A259
0x18003a24e  add     eax, 10h
0x18003a251  mov     [rcx], eax
0x18003a253  cmp     eax, edx
0x18003a255  jbe     short loc_18003A259
0x18003a257  mov     [rcx], edx
0x18003a259  mov     dword ptr [rsi+8], 60h ; '`'
0x18003a260  mov     r8, rsi; TokenInformation
0x18003a263  mov     r9d, [rbp+cbSid]; TokenInformationLength
0x18003a267  mov     edx, 19h; TokenInformationClass
0x18003a26c  mov     rcx, rdi; TokenHandle
0x18003a26f  call    cs:__imp_SetTokenInformation
0x18003a276  nop     dword ptr [rax+rax+00h]
0x18003a27b  test    eax, eax
0x18003a27d  jz      loc_18003A008
0x18003a283  mov     eax, 4
0x18003a288  mov     [rbp+TokenInformation], 1
0x18003a28f  mov     r9d, eax; TokenInformationLength
0x18003a292  mov     [rbp+cbSid], eax
0x18003a295  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18003a299  mov     rcx, rdi; TokenHandle
0x18003a29c  lea     edx, [rax+16h]; TokenInformationClass
0x18003a29f  call    cs:__imp_SetTokenInformation
0x18003a2a6  nop     dword ptr [rax+rax+00h]
0x18003a2ab  test    eax, eax
0x18003a2ad  jz      loc_18003A008
0x18003a2b3  mov     ebx, r12d
0x18003a2b6  cmp     [rbp+IsMember], r12d
0x18003a2ba  jz      short loc_18003A2D2
0x18003a2bc  mov     rcx, [r15]; hObject
0x18003a2bf  call    cs:__imp_CloseHandle
0x18003a2c6  nop     dword ptr [rax+rax+00h]
0x18003a2cb  mov     [r15], rdi
0x18003a2ce  mov     [rbp+hObject], r12
0x18003a2d2  mov     rcx, [rbp+DuplicateTokenHandle]; hObject
0x18003a2d6  test    rcx, rcx
0x18003a2d9  jz      short loc_18003A2EB
0x18003a2db  call    cs:__imp_CloseHandle
0x18003a2e2  nop     dword ptr [rax+rax+00h]
0x18003a2e7  mov     [rbp+DuplicateTokenHandle], r12
0x18003a2eb  mov     rcx, [rbp+ExistingTokenHandle]; hObject
0x18003a2ef  test    rcx, rcx
0x18003a2f2  jz      short loc_18003A304
0x18003a2f4  call    cs:__imp_CloseHandle
0x18003a2fb  nop     dword ptr [rax+rax+00h]
0x18003a300  mov     [rbp+ExistingTokenHandle], r12
0x18003a304  mov     rcx, [rbp+hObject]; hObject
0x18003a308  test    rcx, rcx
0x18003a30b  jz      short loc_18003A31D
0x18003a30d  call    cs:__imp_CloseHandle
0x18003a314  nop     dword ptr [rax+rax+00h]
0x18003a319  mov     [rbp+hObject], r12
0x18003a31d  mov     rcx, r14; hMem
0x18003a320  call    cs:__imp_LocalFree
0x18003a327  nop     dword ptr [rax+rax+00h]
0x18003a32c  mov     rcx, rsi; hMem
0x18003a32f  call    cs:__imp_LocalFree
0x18003a336  nop     dword ptr [rax+rax+00h]
0x18003a33b  mov     eax, ebx
0x18003a33d  mov     rcx, [rbp+var_10]
0x18003a341  xor     rcx, rsp; StackCookie
0x18003a344  call    __security_check_cookie
0x18003a349  lea     r11, [rsp+70h+var_s0]
0x18003a34e  mov     rbx, [r11+38h]
0x18003a352  mov     rsi, [r11+40h]
0x18003a356  mov     rsp, r11
0x18003a359  pop     r15
0x18003a35b  pop     r14
0x18003a35d  pop     r12
0x18003a35f  pop     rdi
0x18003a360  pop     rbp
0x18003a361  retn
```
