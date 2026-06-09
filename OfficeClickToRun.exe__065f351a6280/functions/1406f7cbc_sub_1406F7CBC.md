# sub_1406F7CBC

- ea: `0x1406f7cbc`
- end: `0x1406f7eb1`
- name: `sub_1406F7CBC`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1406f8360`

## callees

- `0x1400301bc`
- `0x140046318`
- `0x1400485d0`
- `0x14037e818`
- `0x140385f74`
- `0x1403e1680`
- `0x1403e60fd`
- `0x14053f0d0`
- `0x140547e04`
- `0x1406f7cbc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1406f7d18`
- `KERNEL32!GetLastError` at `0x1406f7dfc`
- `KERNEL32!GetLastError` at `0x1406f7e80`
- `KERNEL32!GetLastError` at `0x1406f7d18`
- `KERNEL32!GetLastError` at `0x1406f7dfc`
- `KERNEL32!GetLastError` at `0x1406f7e80`
- `ADVAPI32!GetTokenInformation` at `0x1406f7d0a`
- `ADVAPI32!GetTokenInformation` at `0x1406f7d86`
- `ADVAPI32!GetTokenInformation` at `0x1406f7d0a`
- `ADVAPI32!GetTokenInformation` at `0x1406f7d86`
- `ADVAPI32!IsValidSid` at `0x1406f7d93`
- `ADVAPI32!IsValidSid` at `0x1406f7d93`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x1406f7da4`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x1406f7da4`
- `ADVAPI32!GetSidSubAuthority` at `0x1406f7dbb`
- `ADVAPI32!GetSidSubAuthority` at `0x1406f7dbb`

## string_xrefs

- `0x1406f7e2d`: `Failed to get token's integrity level information`
- `0x1406f7e58`: `GetTokenInformation returned an invalid sid : IsValidSid failed`
- `0x1406f7e89`: `GetSidSubAuthorityCount failed for a valid sid`
- `0x1406f7e05`: `GetSidSubAuthority failed for a valid sid`

## pseudocode

```c
__int64 __fastcall sub_1406F7CBC(HANDLE *a1)
{
  DWORD v2; // ebx
  DWORD LastError; // eax
  PSID *v4; // rdi
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD TokenInformationLength; // [rsp+38h] [rbp-D0h] BYREF
  DWORD TokenInformationLength_8[4]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B8h]
  _BYTE pExceptionObject[912]; // [rsp+58h] [rbp-B0h] BYREF

  v2 = 0;
  TokenInformationLength = 0;
  if ( !GetTokenInformation(*a1, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      sub_14037E818(pExceptionObject, 15, LastError, L"Failed to get token's integrity level information");
      throw (OException *)pExceptionObject;
    }
    *(_OWORD *)TokenInformationLength_8 = 0;
    v12 = 0;
    if ( TokenInformationLength )
    {
      _mm_lfence();
      sub_1400485D0(TokenInformationLength_8, TokenInformationLength);
    }
    if ( *(_QWORD *)&TokenInformationLength_8[2] == *(_QWORD *)TokenInformationLength_8 )
      v4 = 0;
    else
      v4 = (PSID *)sub_1400301BC(TokenInformationLength_8, 0);
    if ( GetTokenInformation(*a1, TokenIntegrityLevel, v4, TokenInformationLength, &TokenInformationLength) )
    {
      if ( !IsValidSid(*v4) )
      {
        sub_140547E04(pExceptionObject, 88, L"GetTokenInformation returned an invalid sid : IsValidSid failed");
        throw (OException *)pExceptionObject;
      }
      SidSubAuthorityCount = GetSidSubAuthorityCount(*v4);
      if ( !SidSubAuthorityCount )
      {
        v9 = GetLastError();
        sub_140385F74(pExceptionObject, 15, v9, L"GetSidSubAuthorityCount failed for a valid sid");
        throw (OException *)pExceptionObject;
      }
      SidSubAuthority = GetSidSubAuthority(*v4, (unsigned int)*SidSubAuthorityCount - 1);
      if ( !SidSubAuthority )
      {
        v8 = GetLastError();
        sub_14053F0D0(pExceptionObject, 15, v8, L"GetSidSubAuthority failed for a valid sid");
        throw (OException *)pExceptionObject;
      }
      v2 = *SidSubAuthority;
    }
    sub_140046318(TokenInformationLength_8);
  }
  return v2;
}

```

## disassembly

```asm
0x1406f7cbc  mov     rax, rsp
0x1406f7cbf  mov     [rax+10h], rbx
0x1406f7cc3  mov     [rax+18h], rsi
0x1406f7cc7  mov     [rax+20h], rdi
0x1406f7ccb  push    rbp
0x1406f7ccc  lea     rbp, [rax-2F8h]
0x1406f7cd3  sub     rsp, 3F0h
0x1406f7cda  mov     rax, cs:__security_cookie
0x1406f7ce1  xor     rax, rsp
0x1406f7ce4  mov     [rbp+2F0h+var_10], rax
0x1406f7ceb  mov     rsi, rcx
0x1406f7cee  xor     ebx, ebx
0x1406f7cf0  mov     [rsp+3F0h+TokenInformationLength], ebx
0x1406f7cf4  lea     rax, [rsp+3F0h+TokenInformationLength]
0x1406f7cf9  mov     [rsp+3F0h+ReturnLength], rax; ReturnLength
0x1406f7cfe  xor     r9d, r9d; TokenInformationLength
0x1406f7d01  xor     r8d, r8d; TokenInformation
0x1406f7d04  lea     edx, [rbx+19h]; TokenInformationClass
0x1406f7d07  mov     rcx, [rcx]; TokenHandle
0x1406f7d0a  call    cs:GetTokenInformation
0x1406f7d10  test    eax, eax
0x1406f7d12  jnz     loc_1406F7DD2
0x1406f7d18  call    cs:__imp_GetLastError
0x1406f7d1e  cmp     eax, 7Ah ; 'z'
0x1406f7d21  jnz     loc_1406F7E2D
0x1406f7d27  mov     edx, [rsp+3F0h+TokenInformationLength]
0x1406f7d2b  xorps   xmm0, xmm0
0x1406f7d2e  movdqu  xmmword ptr [rsp+3F0h+TokenInformationLength+8], xmm0
0x1406f7d34  mov     [rsp+3F0h+var_3A8], rbx
0x1406f7d39  test    rdx, rdx
0x1406f7d3c  jz      short loc_1406F7D4C
0x1406f7d3e  lfence
0x1406f7d41  lea     rcx, [rsp+3F0h+TokenInformationLength+8]
0x1406f7d46  call    sub_1400485D0
0x1406f7d4b  nop
0x1406f7d4c  mov     rax, [rsp+3F0h+var_3B0]
0x1406f7d51  cmp     rax, qword ptr [rsp+3F0h+TokenInformationLength+8]
0x1406f7d56  jnz     short loc_1406F7D5D
0x1406f7d58  mov     rdi, rbx
0x1406f7d5b  jmp     short loc_1406F7D6C
0x1406f7d5d  xor     edx, edx
0x1406f7d5f  lea     rcx, [rsp+3F0h+TokenInformationLength+8]
0x1406f7d64  call    sub_1400301BC
0x1406f7d69  mov     rdi, rax
0x1406f7d6c  lea     rax, [rsp+3F0h+TokenInformationLength]
0x1406f7d71  mov     [rsp+3F0h+ReturnLength], rax; ReturnLength
0x1406f7d76  mov     r9d, [rsp+3F0h+TokenInformationLength]; TokenInformationLength
0x1406f7d7b  mov     r8, rdi; TokenInformation
0x1406f7d7e  mov     edx, 19h; TokenInformationClass
0x1406f7d83  mov     rcx, [rsi]; TokenHandle
0x1406f7d86  call    cs:GetTokenInformation
0x1406f7d8c  test    eax, eax
0x1406f7d8e  jz      short loc_1406F7DC8
0x1406f7d90  mov     rcx, [rdi]; pSid
0x1406f7d93  call    cs:IsValidSid
0x1406f7d99  test    eax, eax
0x1406f7d9b  jz      loc_1406F7E58
0x1406f7da1  mov     rcx, [rdi]; pSid
0x1406f7da4  call    cs:GetSidSubAuthorityCount
0x1406f7daa  test    rax, rax
0x1406f7dad  jz      loc_1406F7E80
0x1406f7db3  movzx   edx, byte ptr [rax]
0x1406f7db6  dec     edx; nSubAuthority
0x1406f7db8  mov     rcx, [rdi]; pSid
0x1406f7dbb  call    cs:GetSidSubAuthority
0x1406f7dc1  test    rax, rax
0x1406f7dc4  jz      short loc_1406F7DFC
0x1406f7dc6  mov     ebx, [rax]
0x1406f7dc8  lea     rcx, [rsp+3F0h+TokenInformationLength+8]
0x1406f7dcd  call    sub_140046318
0x1406f7dd2  mov     eax, ebx
0x1406f7dd4  mov     rcx, [rbp+2F0h+var_10]
0x1406f7ddb  xor     rcx, rsp; StackCookie
0x1406f7dde  call    __security_check_cookie
0x1406f7de3  lea     r11, [rsp+3F0h+var_s0]
0x1406f7deb  mov     rbx, [r11+18h]
0x1406f7def  mov     rsi, [r11+20h]
0x1406f7df3  mov     rdi, [r11+28h]
0x1406f7df7  mov     rsp, r11
0x1406f7dfa  pop     rbp
0x1406f7dfb  retn
0x1406f7dfc  call    cs:__imp_GetLastError
0x1406f7e02  mov     r8d, eax
0x1406f7e05  lea     r9, aGetsidsubautho_2; "GetSidSubAuthority failed for a valid s"...
0x1406f7e0c  mov     edx, 0Fh
0x1406f7e11  lea     rcx, [rsp+3F0h+pExceptionObject]
0x1406f7e16  call    sub_14053F0D0
0x1406f7e1b  lea     rdx, __TI2?AVOException@@; pThrowInfo
0x1406f7e22  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x1406f7e27  call    _CxxThrowException
0x1406f7e2d  lea     r9, aFailedToGetTok; "Failed to get token's integrity level i"...
0x1406f7e34  mov     r8d, eax
0x1406f7e37  mov     edx, 0Fh
0x1406f7e3c  lea     rcx, [rsp+3F0h+pExceptionObject]
0x1406f7e41  call    sub_14037E818
0x1406f7e46  lea     rdx, __TI2?AVOException@@; pThrowInfo
0x1406f7e4d  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x1406f7e52  call    _CxxThrowException
0x1406f7e58  lea     r8, aGettokeninform_0; "GetTokenInformation returned an invalid"...
0x1406f7e5f  mov     edx, 58h ; 'X'
0x1406f7e64  lea     rcx, [rsp+3F0h+pExceptionObject]
0x1406f7e69  call    sub_140547E04
0x1406f7e6e  lea     rdx, __TI2?AVOException@@; pThrowInfo
0x1406f7e75  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x1406f7e7a  call    _CxxThrowException
0x1406f7e80  call    cs:__imp_GetLastError
0x1406f7e86  mov     r8d, eax
0x1406f7e89  lea     r9, aGetsidsubautho_1; "GetSidSubAuthorityCount failed for a va"...
0x1406f7e90  mov     edx, 0Fh
0x1406f7e95  lea     rcx, [rsp+3F0h+pExceptionObject]
0x1406f7e9a  call    sub_140385F74
0x1406f7e9f  lea     rdx, __TI2?AVOException@@; pThrowInfo
0x1406f7ea6  lea     rcx, [rsp+3F0h+pExceptionObject]; pExceptionObject
0x1406f7eab  call    _CxxThrowException
```
