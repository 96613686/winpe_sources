# LUASetUIAToken

- ea: `0x180010cc0`
- end: `0x180010f3b`
- name: `LUASetUIAToken`
- size: `635`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014da0`

## callees

- `0x180010cc0`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010d23`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010d59`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010d8b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010e23`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010d23`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010d59`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010d8b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180010e23`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180010dbf`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180010e39`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180010dbf`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180010e39`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180010e50`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180010e50`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180010e9f`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180010ed1`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180010e9f`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180010ed1`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180010dff`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180010dff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ee1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ef8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ef8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010f0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010f0b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010dd5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010dd5`

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
0x180010cc0  mov     [rsp-18h+arg_8], rbx
0x180010cc5  mov     [rsp-18h+arg_10], rsi
0x180010cca  push    rbp
0x180010ccb  push    rdi
0x180010ccc  push    r14
0x180010cce  mov     rbp, rsp
0x180010cd1  sub     rsp, 60h
0x180010cd5  mov     rax, cs:__security_cookie
0x180010cdc  xor     rax, rsp
0x180010cdf  mov     [rbp+var_10], rax
0x180010ce3  xor     r14d, r14d
0x180010ce6  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 1000h
0x180010cec  lea     rax, [rbp+TokenInformationLength]
0x180010cf0  mov     [rbp+TokenHandle], r14
0x180010cf4  mov     ebx, r14d
0x180010cf7  mov     [rbp+var_28], r14d
0x180010cfb  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180010cff  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x180010d02  lea     r9d, [r14+4]; TokenInformationLength
0x180010d06  mov     [rbp+TokenInformationLength], 4
0x180010d0d  lea     edx, [r14+1Ah]; TokenInformationClass
0x180010d11  mov     [rbp+TokenInformation], 1
0x180010d18  mov     rsi, rcx
0x180010d1b  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180010d20  mov     edi, r14d
0x180010d23  call    cs:__imp_GetTokenInformation
0x180010d2a  nop     dword ptr [rax+rax+00h]
0x180010d2f  test    eax, eax
0x180010d31  jz      loc_180010EE1
0x180010d37  cmp     [rbp+TokenInformation], 1
0x180010d3b  jz      loc_180010EEF
0x180010d41  lea     rax, [rbp+TokenInformationLength]
0x180010d45  mov     rcx, rsi; TokenHandle
0x180010d48  lea     r9d, [r14+4]; TokenInformationLength
0x180010d4c  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180010d51  lea     r8, [rbp+var_28]; TokenInformation
0x180010d55  lea     edx, [r14+12h]; TokenInformationClass
0x180010d59  call    cs:__imp_GetTokenInformation
0x180010d60  nop     dword ptr [rax+rax+00h]
0x180010d65  test    eax, eax
0x180010d67  jz      loc_180010EE1
0x180010d6d  cmp     [rbp+var_28], 3
0x180010d71  jnz     short loc_180010DBA
0x180010d73  lea     rax, [rbp+TokenInformationLength]
0x180010d77  mov     rcx, rsi; TokenHandle
0x180010d7a  lea     r9d, [r14+8]; TokenInformationLength
0x180010d7e  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180010d83  lea     r8, [rbp+TokenHandle]; TokenInformation
0x180010d87  lea     edx, [r14+13h]; TokenInformationClass
0x180010d8b  call    cs:__imp_GetTokenInformation
0x180010d92  nop     dword ptr [rax+rax+00h]
0x180010d97  test    eax, eax
0x180010d99  jz      short loc_180010DA1
0x180010d9b  mov     rdi, [rbp+TokenHandle]
0x180010d9f  jmp     short loc_180010DBD
0x180010da1  call    cs:__imp_GetLastError
0x180010da8  nop     dword ptr [rax+rax+00h]
0x180010dad  mov     edi, eax
0x180010daf  cmp     eax, 520h
0x180010db4  jnz     loc_180010EEF
0x180010dba  mov     rdi, rsi
0x180010dbd  mov     cl, 1; nSubAuthorityCount
0x180010dbf  call    cs:__imp_GetSidLengthRequired
0x180010dc6  nop     dword ptr [rax+rax+00h]
0x180010dcb  add     eax, 10h
0x180010dce  xor     ecx, ecx; uFlags
0x180010dd0  mov     edx, eax; uBytes
0x180010dd2  mov     [rbp+TokenInformationLength], eax
0x180010dd5  call    cs:__imp_LocalAlloc
0x180010ddc  nop     dword ptr [rax+rax+00h]
0x180010de1  mov     rbx, rax
0x180010de4  test    rax, rax
0x180010de7  jnz     short loc_180010DF1
0x180010de9  lea     edi, [rax+8]
0x180010dec  jmp     loc_180010EEF
0x180010df1  lea     rcx, [rax+10h]; Sid
0x180010df5  mov     r8b, 1; nSubAuthorityCount
0x180010df8  lea     rdx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180010dfc  mov     [rax], rcx
0x180010dff  call    cs:__imp_InitializeSid
0x180010e06  nop     dword ptr [rax+rax+00h]
0x180010e0b  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180010e0f  lea     rax, [rbp+TokenInformationLength]
0x180010e13  mov     r8, rbx; TokenInformation
0x180010e16  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180010e1b  mov     edx, 19h; TokenInformationClass
0x180010e20  mov     rcx, rdi; TokenHandle
0x180010e23  call    cs:__imp_GetTokenInformation
0x180010e2a  nop     dword ptr [rax+rax+00h]
0x180010e2f  test    eax, eax
0x180010e31  jz      loc_180010EE1
0x180010e37  mov     cl, 1; nSubAuthorityCount
0x180010e39  call    cs:__imp_GetSidLengthRequired
0x180010e40  nop     dword ptr [rax+rax+00h]
0x180010e45  add     eax, 10h
0x180010e48  xor     edx, edx; nSubAuthority
0x180010e4a  mov     [rbp+TokenInformationLength], eax
0x180010e4d  mov     rcx, [rbx]; pSid
0x180010e50  call    cs:__imp_GetSidSubAuthority
0x180010e57  nop     dword ptr [rax+rax+00h]
0x180010e5c  mov     rcx, rax
0x180010e5f  mov     eax, [rax]
0x180010e61  cmp     eax, 2000h
0x180010e66  jnb     short loc_180010E70
0x180010e68  mov     dword ptr [rcx], 2010h
0x180010e6e  jmp     short loc_180010E89
0x180010e70  cmp     eax, 3000h
0x180010e75  jnb     short loc_180010E89
0x180010e77  add     eax, 10h
0x180010e7a  mov     [rcx], eax
0x180010e7c  cmp     eax, 3000h
0x180010e81  jbe     short loc_180010E89
0x180010e83  mov     dword ptr [rcx], 3000h
0x180010e89  mov     dword ptr [rbx+8], 60h ; '`'
0x180010e90  mov     r8, rbx; TokenInformation
0x180010e93  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180010e97  mov     edx, 19h; TokenInformationClass
0x180010e9c  mov     rcx, rsi; TokenHandle
0x180010e9f  call    cs:__imp_SetTokenInformation
0x180010ea6  nop     dword ptr [rax+rax+00h]
0x180010eab  test    eax, eax
0x180010ead  jz      short loc_180010EE1
0x180010eaf  mov     r9d, 4; TokenInformationLength
0x180010eb5  mov     [rbp+TokenInformationLength], 4
0x180010ebc  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180010ec0  mov     [rbp+TokenInformation], 1
0x180010ec7  mov     rcx, rsi; TokenHandle
0x180010eca  mov     edi, r14d
0x180010ecd  lea     edx, [r9+16h]; TokenInformationClass
0x180010ed1  call    cs:__imp_SetTokenInformation
0x180010ed8  nop     dword ptr [rax+rax+00h]
0x180010edd  test    eax, eax
0x180010edf  jnz     short loc_180010EEF
0x180010ee1  call    cs:__imp_GetLastError
0x180010ee8  nop     dword ptr [rax+rax+00h]
0x180010eed  mov     edi, eax
0x180010eef  mov     rcx, [rbp+TokenHandle]; hObject
0x180010ef3  test    rcx, rcx
0x180010ef6  jz      short loc_180010F08
0x180010ef8  call    cs:__imp_CloseHandle
0x180010eff  nop     dword ptr [rax+rax+00h]
0x180010f04  mov     [rbp+TokenHandle], r14
0x180010f08  mov     rcx, rbx; hMem
0x180010f0b  call    cs:__imp_LocalFree
0x180010f12  nop     dword ptr [rax+rax+00h]
0x180010f17  mov     eax, edi
0x180010f19  mov     rcx, [rbp+var_10]
0x180010f1d  xor     rcx, rsp; StackCookie
0x180010f20  call    __security_check_cookie
0x180010f25  lea     r11, [rsp+60h+var_s0]
0x180010f2a  mov     rbx, [r11+28h]
0x180010f2e  mov     rsi, [r11+30h]
0x180010f32  mov     rsp, r11
0x180010f35  pop     r14
0x180010f37  pop     rdi
0x180010f38  pop     rbp
0x180010f39  retn
```
