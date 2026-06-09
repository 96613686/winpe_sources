# LUASetUIAToken

- ea: `0x180010b80`
- end: `0x180010dfb`
- name: `LUASetUIAToken`
- size: `635`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014d40`

## callees

- `0x180010b80`
- `0x180042950`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180010c7f`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180010cf9`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180010c7f`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180010cf9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180010d10`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180010d10`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180010d5f`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180010d91`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180010d5f`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180010d91`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180010cbf`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180010cbf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010be3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010c19`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010c4b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010ce3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010be3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010c19`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010c4b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010ce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010da1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010db8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010db8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010dcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010dcb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010c95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010c95`

## pseudocode

```c
__int64 __fastcall LUASetUIAToken(HANDLE TokenHandle)
{
  PSID *v1; // rbx
  DWORD LastError; // edi
  HANDLE v4; // rdi
  PSID *v5; // rax
  PDWORD SidSubAuthority; // rcx
  unsigned int v7; // eax
  unsigned int v8; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-30h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-2Ch] BYREF
  int v12; // [rsp+38h] [rbp-28h] BYREF
  HANDLE TokenHandlea; // [rsp+40h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+48h] [rbp-18h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  TokenHandlea = 0;
  v1 = 0;
  v12 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  TokenInformationLength = 4;
  TokenInformation = 1;
  LastError = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUIAccess, &TokenInformation, 4u, &TokenInformationLength) )
    goto LABEL_19;
  if ( TokenInformation == 1 )
    goto LABEL_20;
  if ( !GetTokenInformation(TokenHandle, TokenElevationType, &v12, 4u, &TokenInformationLength) )
  {
LABEL_19:
    LastError = GetLastError();
    goto LABEL_20;
  }
  if ( v12 == 3 )
  {
    if ( GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenHandlea, 8u, &TokenInformationLength) )
    {
      v4 = TokenHandlea;
      goto LABEL_9;
    }
    LastError = GetLastError();
    if ( LastError != 1312 )
      goto LABEL_20;
  }
  v4 = TokenHandle;
LABEL_9:
  TokenInformationLength = GetSidLengthRequired(1u) + 16;
  v5 = (PSID *)LocalAlloc(0, TokenInformationLength);
  v1 = v5;
  if ( !v5 )
  {
    LastError = 8;
    goto LABEL_20;
  }
  *v5 = v5 + 2;
  InitializeSid(v5 + 2, &pIdentifierAuthority, 1u);
  if ( !GetTokenInformation(v4, TokenIntegrityLevel, v1, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_19;
  TokenInformationLength = GetSidLengthRequired(1u) + 16;
  SidSubAuthority = GetSidSubAuthority(*v1, 0);
  v7 = *SidSubAuthority;
  if ( *SidSubAuthority >= 0x2000 )
  {
    if ( v7 < 0x3000 )
    {
      v8 = v7 + 16;
      *SidSubAuthority = v8;
      if ( v8 > 0x3000 )
        *SidSubAuthority = 12288;
    }
  }
  else
  {
    *SidSubAuthority = 8208;
  }
  *((_DWORD *)v1 + 2) = 96;
  if ( !SetTokenInformation(TokenHandle, TokenIntegrityLevel, v1, TokenInformationLength) )
    goto LABEL_19;
  TokenInformationLength = 4;
  TokenInformation = 1;
  LastError = 0;
  if ( !SetTokenInformation(TokenHandle, TokenUIAccess, &TokenInformation, 4u) )
    goto LABEL_19;
LABEL_20:
  if ( TokenHandlea )
  {
    CloseHandle(TokenHandlea);
    TokenHandlea = 0;
  }
  LocalFree(v1);
  return LastError;
}

```

## disassembly

```asm
0x180010b80  mov     [rsp-18h+arg_8], rbx
0x180010b85  mov     [rsp-18h+arg_10], rsi
0x180010b8a  push    rbp
0x180010b8b  push    rdi
0x180010b8c  push    r14
0x180010b8e  mov     rbp, rsp
0x180010b91  sub     rsp, 60h
0x180010b95  mov     rax, cs:__security_cookie
0x180010b9c  xor     rax, rsp
0x180010b9f  mov     [rbp+var_10], rax
0x180010ba3  xor     r14d, r14d
0x180010ba6  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 1000h
0x180010bac  lea     rax, [rbp+TokenInformationLength]
0x180010bb0  mov     [rbp+TokenHandle], r14
0x180010bb4  mov     ebx, r14d
0x180010bb7  mov     [rbp+var_28], r14d
0x180010bbb  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180010bbf  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x180010bc2  lea     r9d, [r14+4]; TokenInformationLength
0x180010bc6  mov     [rbp+TokenInformationLength], 4
0x180010bcd  lea     edx, [r14+1Ah]; TokenInformationClass
0x180010bd1  mov     [rbp+TokenInformation], 1
0x180010bd8  mov     rsi, rcx
0x180010bdb  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180010be0  mov     edi, r14d
0x180010be3  call    cs:__imp_GetTokenInformation
0x180010bea  nop     dword ptr [rax+rax+00h]
0x180010bef  test    eax, eax
0x180010bf1  jz      loc_180010DA1
0x180010bf7  cmp     [rbp+TokenInformation], 1
0x180010bfb  jz      loc_180010DAF
0x180010c01  lea     rax, [rbp+TokenInformationLength]
0x180010c05  mov     rcx, rsi; TokenHandle
0x180010c08  lea     r9d, [r14+4]; TokenInformationLength
0x180010c0c  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180010c11  lea     r8, [rbp+var_28]; TokenInformation
0x180010c15  lea     edx, [r14+12h]; TokenInformationClass
0x180010c19  call    cs:__imp_GetTokenInformation
0x180010c20  nop     dword ptr [rax+rax+00h]
0x180010c25  test    eax, eax
0x180010c27  jz      loc_180010DA1
0x180010c2d  cmp     [rbp+var_28], 3
0x180010c31  jnz     short loc_180010C7A
0x180010c33  lea     rax, [rbp+TokenInformationLength]
0x180010c37  mov     rcx, rsi; TokenHandle
0x180010c3a  lea     r9d, [r14+8]; TokenInformationLength
0x180010c3e  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180010c43  lea     r8, [rbp+TokenHandle]; TokenInformation
0x180010c47  lea     edx, [r14+13h]; TokenInformationClass
0x180010c4b  call    cs:__imp_GetTokenInformation
0x180010c52  nop     dword ptr [rax+rax+00h]
0x180010c57  test    eax, eax
0x180010c59  jz      short loc_180010C61
0x180010c5b  mov     rdi, [rbp+TokenHandle]
0x180010c5f  jmp     short loc_180010C7D
0x180010c61  call    cs:__imp_GetLastError
0x180010c68  nop     dword ptr [rax+rax+00h]
0x180010c6d  mov     edi, eax
0x180010c6f  cmp     eax, 520h
0x180010c74  jnz     loc_180010DAF
0x180010c7a  mov     rdi, rsi
0x180010c7d  mov     cl, 1; nSubAuthorityCount
0x180010c7f  call    cs:__imp_GetSidLengthRequired
0x180010c86  nop     dword ptr [rax+rax+00h]
0x180010c8b  add     eax, 10h
0x180010c8e  xor     ecx, ecx; uFlags
0x180010c90  mov     edx, eax; uBytes
0x180010c92  mov     [rbp+TokenInformationLength], eax
0x180010c95  call    cs:__imp_LocalAlloc
0x180010c9c  nop     dword ptr [rax+rax+00h]
0x180010ca1  mov     rbx, rax
0x180010ca4  test    rax, rax
0x180010ca7  jnz     short loc_180010CB1
0x180010ca9  lea     edi, [rax+8]
0x180010cac  jmp     loc_180010DAF
0x180010cb1  lea     rcx, [rax+10h]; Sid
0x180010cb5  mov     r8b, 1; nSubAuthorityCount
0x180010cb8  lea     rdx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180010cbc  mov     [rax], rcx
0x180010cbf  call    cs:__imp_InitializeSid
0x180010cc6  nop     dword ptr [rax+rax+00h]
0x180010ccb  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180010ccf  lea     rax, [rbp+TokenInformationLength]
0x180010cd3  mov     r8, rbx; TokenInformation
0x180010cd6  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180010cdb  mov     edx, 19h; TokenInformationClass
0x180010ce0  mov     rcx, rdi; TokenHandle
0x180010ce3  call    cs:__imp_GetTokenInformation
0x180010cea  nop     dword ptr [rax+rax+00h]
0x180010cef  test    eax, eax
0x180010cf1  jz      loc_180010DA1
0x180010cf7  mov     cl, 1; nSubAuthorityCount
0x180010cf9  call    cs:__imp_GetSidLengthRequired
0x180010d00  nop     dword ptr [rax+rax+00h]
0x180010d05  add     eax, 10h
0x180010d08  xor     edx, edx; nSubAuthority
0x180010d0a  mov     [rbp+TokenInformationLength], eax
0x180010d0d  mov     rcx, [rbx]; pSid
0x180010d10  call    cs:__imp_GetSidSubAuthority
0x180010d17  nop     dword ptr [rax+rax+00h]
0x180010d1c  mov     rcx, rax
0x180010d1f  mov     eax, [rax]
0x180010d21  cmp     eax, 2000h
0x180010d26  jnb     short loc_180010D30
0x180010d28  mov     dword ptr [rcx], 2010h
0x180010d2e  jmp     short loc_180010D49
0x180010d30  cmp     eax, 3000h
0x180010d35  jnb     short loc_180010D49
0x180010d37  add     eax, 10h
0x180010d3a  mov     [rcx], eax
0x180010d3c  cmp     eax, 3000h
0x180010d41  jbe     short loc_180010D49
0x180010d43  mov     dword ptr [rcx], 3000h
0x180010d49  mov     dword ptr [rbx+8], 60h ; '`'
0x180010d50  mov     r8, rbx; TokenInformation
0x180010d53  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180010d57  mov     edx, 19h; TokenInformationClass
0x180010d5c  mov     rcx, rsi; TokenHandle
0x180010d5f  call    cs:__imp_SetTokenInformation
0x180010d66  nop     dword ptr [rax+rax+00h]
0x180010d6b  test    eax, eax
0x180010d6d  jz      short loc_180010DA1
0x180010d6f  mov     r9d, 4; TokenInformationLength
0x180010d75  mov     [rbp+TokenInformationLength], 4
0x180010d7c  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180010d80  mov     [rbp+TokenInformation], 1
0x180010d87  mov     rcx, rsi; TokenHandle
0x180010d8a  mov     edi, r14d
0x180010d8d  lea     edx, [r9+16h]; TokenInformationClass
0x180010d91  call    cs:__imp_SetTokenInformation
0x180010d98  nop     dword ptr [rax+rax+00h]
0x180010d9d  test    eax, eax
0x180010d9f  jnz     short loc_180010DAF
0x180010da1  call    cs:__imp_GetLastError
0x180010da8  nop     dword ptr [rax+rax+00h]
0x180010dad  mov     edi, eax
0x180010daf  mov     rcx, [rbp+TokenHandle]; hObject
0x180010db3  test    rcx, rcx
0x180010db6  jz      short loc_180010DC8
0x180010db8  call    cs:__imp_CloseHandle
0x180010dbf  nop     dword ptr [rax+rax+00h]
0x180010dc4  mov     [rbp+TokenHandle], r14
0x180010dc8  mov     rcx, rbx; hMem
0x180010dcb  call    cs:__imp_LocalFree
0x180010dd2  nop     dword ptr [rax+rax+00h]
0x180010dd7  mov     eax, edi
0x180010dd9  mov     rcx, [rbp+var_10]
0x180010ddd  xor     rcx, rsp; StackCookie
0x180010de0  call    __security_check_cookie
0x180010de5  lea     r11, [rsp+60h+var_s0]
0x180010dea  mov     rbx, [r11+28h]
0x180010dee  mov     rsi, [r11+30h]
0x180010df2  mov     rsp, r11
0x180010df5  pop     r14
0x180010df7  pop     rdi
0x180010df8  pop     rbp
0x180010df9  retn
```
