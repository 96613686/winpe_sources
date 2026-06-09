# LUASetUIAToken2

- ea: `0x18003c77c`
- end: `0x18003cacc`
- name: `LUASetUIAToken2`
- size: `848`
- prototype: `__int64 __fastcall(HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d8fc`

## callees

- `0x18003c77c`
- `0x1800461e8`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c7ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c7ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c940`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ca4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ca63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ca76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ca89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ca4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ca63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ca76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ca89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ca96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ca9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ca96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ca9f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c8a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c968`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c8a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c968`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003c890`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003c8cb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003c890`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003c8cb`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003c958`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003c9ba`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003c958`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18003c9ba`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003c9cb`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18003c9cb`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18003ca09`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18003ca33`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18003ca09`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18003ca33`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003c8fe`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003c8fe`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003c8e5`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18003c8e5`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18003c98c`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x18003c98c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c7f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c833`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c861`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c92c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c9aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c7f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c833`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c861`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c92c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c9aa`

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
0x18003c77c  mov     [rsp-28h+arg_8], rbx
0x18003c781  mov     [rsp-28h+arg_10], rsi
0x18003c786  push    rbp
0x18003c787  push    rdi
0x18003c788  push    r12
0x18003c78a  push    r14
0x18003c78c  push    r15
0x18003c78e  mov     rbp, rsp
0x18003c791  sub     rsp, 70h
0x18003c795  mov     rax, cs:__security_cookie
0x18003c79c  xor     rax, rsp
0x18003c79f  mov     [rbp+var_10], rax
0x18003c7a3  mov     rdi, [rcx]
0x18003c7a6  lea     rax, [rbp+cbSid]
0x18003c7aa  xor     r12d, r12d
0x18003c7ad  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 1000h
0x18003c7b3  mov     r15, rcx
0x18003c7b6  mov     [rbp+ExistingTokenHandle], r12
0x18003c7ba  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18003c7be  mov     [rbp+var_34], r12d
0x18003c7c2  mov     esi, r12d
0x18003c7c5  mov     dword ptr [rbp+pIdentifierAuthority.Value], r12d
0x18003c7c9  lea     ecx, [r12+4]
0x18003c7ce  mov     [rbp+DuplicateTokenHandle], r12
0x18003c7d2  mov     [rbp+cbSid], ecx
0x18003c7d5  lea     edx, [rcx+16h]; TokenInformationClass
0x18003c7d8  mov     r9d, ecx; TokenInformationLength
0x18003c7db  mov     [rbp+hObject], r12
0x18003c7df  mov     rcx, rdi; TokenHandle
0x18003c7e2  mov     [rbp+IsMember], r12d
0x18003c7e6  mov     r14d, r12d
0x18003c7e9  mov     [rbp+TokenInformation], 1
0x18003c7f0  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003c7f5  call    cs:__imp_GetTokenInformation
0x18003c7fb  test    eax, eax
0x18003c7fd  jnz     short loc_18003C80C
0x18003c7ff  call    cs:__imp_GetLastError
0x18003c805  mov     ebx, eax
0x18003c807  jmp     loc_18003CA5A
0x18003c80c  cmp     [rbp+TokenInformation], 1
0x18003c810  mov     ebx, r12d
0x18003c813  jz      loc_18003CA5A
0x18003c819  mov     r9d, 4; TokenInformationLength
0x18003c81f  lea     rax, [rbp+cbSid]
0x18003c823  lea     r8, [rbp+var_34]; TokenInformation
0x18003c827  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003c82c  mov     rcx, rdi; TokenHandle
0x18003c82f  lea     edx, [r9+0Eh]; TokenInformationClass
0x18003c833  call    cs:__imp_GetTokenInformation
0x18003c839  test    eax, eax
0x18003c83b  jz      short loc_18003C7FF
0x18003c83d  cmp     [rbp+var_34], 3
0x18003c841  jnz     loc_18003C953
0x18003c847  mov     r9d, 8; TokenInformationLength
0x18003c84d  lea     rax, [rbp+cbSid]
0x18003c851  lea     r8, [rbp+ExistingTokenHandle]; TokenInformation
0x18003c855  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003c85a  mov     rcx, rdi; TokenHandle
0x18003c85d  lea     edx, [r9+0Bh]; TokenInformationClass
0x18003c861  call    cs:__imp_GetTokenInformation
0x18003c867  test    eax, eax
0x18003c869  jz      loc_18003C940
0x18003c86f  mov     rbx, [rbp+ExistingTokenHandle]
0x18003c873  call    LUAIsShadowAdminEnabled
0x18003c878  test    eax, eax
0x18003c87a  jz      loc_18003C956
0x18003c880  xor     edx, edx; DomainSid
0x18003c882  mov     [rbp+cbSid], r12d
0x18003c886  lea     r9, [rbp+cbSid]; cbSid
0x18003c88a  xor     r8d, r8d; pSid
0x18003c88d  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18003c890  call    cs:__imp_CreateWellKnownSid
0x18003c896  test    eax, eax
0x18003c898  jz      short loc_18003C8A4
0x18003c89a  mov     ebx, 7Ah ; 'z'
0x18003c89f  jmp     loc_18003CA5A
0x18003c8a4  mov     edx, [rbp+cbSid]; uBytes
0x18003c8a7  xor     ecx, ecx; uFlags
0x18003c8a9  call    cs:__imp_LocalAlloc
0x18003c8af  mov     r14, rax
0x18003c8b2  test    rax, rax
0x18003c8b5  jnz     short loc_18003C8BF
0x18003c8b7  lea     ebx, [rax+0Eh]
0x18003c8ba  jmp     loc_18003CA5A
0x18003c8bf  xor     edx, edx; DomainSid
0x18003c8c1  lea     r9, [rbp+cbSid]; cbSid
0x18003c8c5  mov     r8, r14; pSid
0x18003c8c8  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18003c8cb  call    cs:__imp_CreateWellKnownSid
0x18003c8d1  test    eax, eax
0x18003c8d3  jz      loc_18003C7FF
0x18003c8d9  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x18003c8dd  mov     edx, 1; ImpersonationLevel
0x18003c8e2  mov     rcx, rbx; ExistingTokenHandle
0x18003c8e5  call    cs:__imp_DuplicateToken
0x18003c8eb  test    eax, eax
0x18003c8ed  jz      loc_18003C7FF
0x18003c8f3  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x18003c8f7  lea     r8, [rbp+IsMember]; IsMember
0x18003c8fb  mov     rdx, r14; SidToCheck
0x18003c8fe  call    cs:__imp_CheckTokenMembership
0x18003c904  test    eax, eax
0x18003c906  jz      loc_18003C7FF
0x18003c90c  cmp     [rbp+IsMember], r12d
0x18003c910  jz      short loc_18003C956
0x18003c912  mov     r9d, 8; TokenInformationLength
0x18003c918  lea     rax, [rbp+cbSid]
0x18003c91c  lea     r8, [rbp+hObject]; TokenInformation
0x18003c920  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003c925  mov     rcx, rbx; TokenHandle
0x18003c928  lea     edx, [r9-0Ah]; TokenInformationClass
0x18003c92c  call    cs:__imp_GetTokenInformation
0x18003c932  test    eax, eax
0x18003c934  jz      loc_18003C7FF
0x18003c93a  mov     rdi, [rbp+hObject]
0x18003c93e  jmp     short loc_18003C956
0x18003c940  call    cs:__imp_GetLastError
0x18003c946  mov     ebx, eax
0x18003c948  cmp     eax, 520h
0x18003c94d  jnz     loc_18003CA5A
0x18003c953  mov     rbx, rdi
0x18003c956  mov     cl, 1; nSubAuthorityCount
0x18003c958  call    cs:__imp_GetSidLengthRequired
0x18003c95e  add     eax, 10h
0x18003c961  xor     ecx, ecx; uFlags
0x18003c963  mov     edx, eax; uBytes
0x18003c965  mov     [rbp+cbSid], eax
0x18003c968  call    cs:__imp_LocalAlloc
0x18003c96e  mov     rsi, rax
0x18003c971  test    rax, rax
0x18003c974  jnz     short loc_18003C97E
0x18003c976  lea     ebx, [rax+8]
0x18003c979  jmp     loc_18003CA5A
0x18003c97e  lea     rcx, [rax+10h]; Sid
0x18003c982  mov     r8b, 1; nSubAuthorityCount
0x18003c985  lea     rdx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18003c989  mov     [rax], rcx
0x18003c98c  call    cs:__imp_InitializeSid
0x18003c992  mov     r9d, [rbp+cbSid]; TokenInformationLength
0x18003c996  lea     rax, [rbp+cbSid]
0x18003c99a  mov     r8, rsi; TokenInformation
0x18003c99d  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18003c9a2  mov     edx, 19h; TokenInformationClass
0x18003c9a7  mov     rcx, rbx; TokenHandle
0x18003c9aa  call    cs:__imp_GetTokenInformation
0x18003c9b0  test    eax, eax
0x18003c9b2  jz      loc_18003C7FF
0x18003c9b8  mov     cl, 1; nSubAuthorityCount
0x18003c9ba  call    cs:__imp_GetSidLengthRequired
0x18003c9c0  add     eax, 10h
0x18003c9c3  xor     edx, edx; nSubAuthority
0x18003c9c5  mov     [rbp+cbSid], eax
0x18003c9c8  mov     rcx, [rsi]; pSid
0x18003c9cb  call    cs:__imp_GetSidSubAuthority
0x18003c9d1  mov     rcx, rax
0x18003c9d4  mov     edx, 3000h
0x18003c9d9  mov     eax, 2000h
0x18003c9de  cmp     [rcx], eax
0x18003c9e0  jb      short loc_18003C9E8
0x18003c9e2  cmp     [rcx], edx
0x18003c9e4  jnb     short loc_18003C9F3
0x18003c9e6  mov     eax, [rcx]
0x18003c9e8  add     eax, 10h
0x18003c9eb  mov     [rcx], eax
0x18003c9ed  cmp     eax, edx
0x18003c9ef  jbe     short loc_18003C9F3
0x18003c9f1  mov     [rcx], edx
0x18003c9f3  mov     dword ptr [rsi+8], 60h ; '`'
0x18003c9fa  mov     r8, rsi; TokenInformation
0x18003c9fd  mov     r9d, [rbp+cbSid]; TokenInformationLength
0x18003ca01  mov     edx, 19h; TokenInformationClass
0x18003ca06  mov     rcx, rdi; TokenHandle
0x18003ca09  call    cs:__imp_SetTokenInformation
0x18003ca0f  test    eax, eax
0x18003ca11  jz      loc_18003C7FF
0x18003ca17  mov     eax, 4
0x18003ca1c  mov     [rbp+TokenInformation], 1
0x18003ca23  mov     r9d, eax; TokenInformationLength
0x18003ca26  mov     [rbp+cbSid], eax
0x18003ca29  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18003ca2d  mov     rcx, rdi; TokenHandle
0x18003ca30  lea     edx, [rax+16h]; TokenInformationClass
0x18003ca33  call    cs:__imp_SetTokenInformation
0x18003ca39  test    eax, eax
0x18003ca3b  jz      loc_18003C7FF
0x18003ca41  mov     ebx, r12d
0x18003ca44  cmp     [rbp+IsMember], r12d
0x18003ca48  jz      short loc_18003CA5A
0x18003ca4a  mov     rcx, [r15]; hObject
0x18003ca4d  call    cs:__imp_CloseHandle
0x18003ca53  mov     [r15], rdi
0x18003ca56  mov     [rbp+hObject], r12
0x18003ca5a  mov     rcx, [rbp+DuplicateTokenHandle]; hObject
0x18003ca5e  test    rcx, rcx
0x18003ca61  jz      short loc_18003CA6D
0x18003ca63  call    cs:__imp_CloseHandle
0x18003ca69  mov     [rbp+DuplicateTokenHandle], r12
0x18003ca6d  mov     rcx, [rbp+ExistingTokenHandle]; hObject
0x18003ca71  test    rcx, rcx
0x18003ca74  jz      short loc_18003CA80
0x18003ca76  call    cs:__imp_CloseHandle
0x18003ca7c  mov     [rbp+ExistingTokenHandle], r12
0x18003ca80  mov     rcx, [rbp+hObject]; hObject
0x18003ca84  test    rcx, rcx
0x18003ca87  jz      short loc_18003CA93
0x18003ca89  call    cs:__imp_CloseHandle
0x18003ca8f  mov     [rbp+hObject], r12
0x18003ca93  mov     rcx, r14; hMem
0x18003ca96  call    cs:__imp_LocalFree
0x18003ca9c  mov     rcx, rsi; hMem
0x18003ca9f  call    cs:__imp_LocalFree
0x18003caa5  mov     eax, ebx
0x18003caa7  mov     rcx, [rbp+var_10]
0x18003caab  xor     rcx, rsp; StackCookie
0x18003caae  call    __security_check_cookie
0x18003cab3  lea     r11, [rsp+70h+var_s0]
0x18003cab8  mov     rbx, [r11+38h]
0x18003cabc  mov     rsi, [r11+40h]
0x18003cac0  mov     rsp, r11
0x18003cac3  pop     r15
0x18003cac5  pop     r14
0x18003cac7  pop     r12
0x18003cac9  pop     rdi
0x18003caca  pop     rbp
0x18003cacb  retn
```
