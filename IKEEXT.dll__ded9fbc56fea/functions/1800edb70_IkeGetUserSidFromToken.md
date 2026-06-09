# IkeGetUserSidFromToken

- ea: `0x1800edb70`
- end: `0x1800edc91`
- name: `IkeGetUserSidFromToken`
- size: `289`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000296c`
- `0x1800ed4f0`
- `0x1800ed5a8`

## callees

- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x18004aa3c`
- `0x180050850`
- `0x1800edb70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edbda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edc74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edbda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edc74`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800edbd2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800edc1e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800edbd2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800edc1e`

## string_xrefs

- `0x1800edc7d`: `GetTokenInformation`
- `0x1800edb9c`: `IkeGetUserSidFromToken`
- `0x1800edc41`: `IkeGetUserSidFromToken`

## pseudocode

```c
__int64 __fastcall IkeGetUserSidFromToken(HANDLE TokenHandle, _QWORD *a2)
{
  void *v2; // rbx
  __int64 result; // rax
  BOOL v6; // ebp
  DWORD LastError; // eax
  __int64 v8; // rcx
  LPVOID TokenInformation; // [rsp+30h] [rbp-48h]
  DWORD TokenInformationLength; // [rsp+38h] [rbp-40h] BYREF

  v2 = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  result = TraceLogHelper("IkeGetUserSidFromToken", 1);
  if ( TokenHandle )
  {
    v6 = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( GetLastError() == 122 )
    {
      v2 = TokenInformation;
      if ( WfpMemAlloc(TokenInformationLength, 0) )
        return TraceLogHelper("IkeGetUserSidFromToken", 0);
    }
    else if ( !v6 )
    {
      goto LABEL_9;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
    {
      *a2 = v2;
      return TraceLogHelper("IkeGetUserSidFromToken", 0);
    }
LABEL_9:
    LastError = GetLastError();
    WfpReportSysErrorAsWinError(v8, "GetTokenInformation", LastError, 1);
    return TraceLogHelper("IkeGetUserSidFromToken", 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800edb70  mov     [rsp+arg_10], rbx
0x1800edb75  push    rbp
0x1800edb76  push    rsi
0x1800edb77  push    rdi
0x1800edb78  push    r14
0x1800edb7a  push    r15
0x1800edb7c  sub     rsp, 50h
0x1800edb80  mov     rax, cs:__security_cookie
0x1800edb87  xor     rax, rsp
0x1800edb8a  mov     [rsp+78h+var_38], rax
0x1800edb8f  xor     ebx, ebx
0x1800edb91  mov     r14, rdx
0x1800edb94  mov     rsi, rcx
0x1800edb97  mov     [rsp+78h+TokenInformation], rbx
0x1800edb9c  lea     rcx, aIkegetusersidf; "IkeGetUserSidFromToken"
0x1800edba3  mov     [rsp+78h+TokenInformationLength], ebx
0x1800edba7  lea     r15d, [rbx+1]
0x1800edbab  mov     edx, r15d
0x1800edbae  call    TraceLogHelper
0x1800edbb3  test    rsi, rsi
0x1800edbb6  jz      loc_1800EDC4D
0x1800edbbc  lea     rax, [rsp+78h+TokenInformationLength]
0x1800edbc1  xor     r9d, r9d; TokenInformationLength
0x1800edbc4  xor     r8d, r8d; TokenInformation
0x1800edbc7  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1800edbcc  mov     edx, r15d; TokenInformationClass
0x1800edbcf  mov     rcx, rsi; TokenHandle
0x1800edbd2  call    cs:__imp_GetTokenInformation
0x1800edbd8  mov     ebp, eax
0x1800edbda  call    cs:__imp_GetLastError
0x1800edbe0  cmp     eax, 7Ah ; 'z'
0x1800edbe3  jnz     loc_1800EDC6E
0x1800edbe9  mov     ecx, [rsp+78h+TokenInformationLength]; dwBytes
0x1800edbed  lea     r8, [rsp+78h+TokenInformation]
0x1800edbf2  xor     edx, edx; dwFlags
0x1800edbf4  call    WfpMemAlloc
0x1800edbf9  mov     rbx, [rsp+78h+TokenInformation]
0x1800edbfe  mov     rdi, rax
0x1800edc01  test    rax, rax
0x1800edc04  jnz     short loc_1800EDC30
0x1800edc06  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x1800edc0b  lea     rax, [rsp+78h+TokenInformationLength]
0x1800edc10  mov     r8, rbx; TokenInformation
0x1800edc13  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1800edc18  mov     edx, r15d; TokenInformationClass
0x1800edc1b  mov     rcx, rsi; TokenHandle
0x1800edc1e  call    cs:__imp_GetTokenInformation
0x1800edc24  test    eax, eax
0x1800edc26  jz      short loc_1800EDC74
0x1800edc28  mov     [r14], rbx
0x1800edc2b  test    rdi, rdi
0x1800edc2e  jz      short loc_1800EDC3F
0x1800edc30  test    rbx, rbx
0x1800edc33  jz      short loc_1800EDC3F
0x1800edc35  lea     rcx, [rsp+78h+TokenInformation]
0x1800edc3a  call    WfpMemFree
0x1800edc3f  xor     edx, edx
0x1800edc41  lea     rcx, aIkegetusersidf; "IkeGetUserSidFromToken"
0x1800edc48  call    TraceLogHelper
0x1800edc4d  mov     rcx, [rsp+78h+var_38]
0x1800edc52  xor     rcx, rsp; StackCookie
0x1800edc55  call    __security_check_cookie
0x1800edc5a  mov     rbx, [rsp+78h+arg_10]
0x1800edc62  add     rsp, 50h
0x1800edc66  pop     r15
0x1800edc68  pop     r14
0x1800edc6a  pop     rdi
0x1800edc6b  pop     rsi
0x1800edc6c  pop     rbp
0x1800edc6d  retn
0x1800edc6e  xor     edi, edi
0x1800edc70  test    ebp, ebp
0x1800edc72  jnz     short loc_1800EDC06
0x1800edc74  call    cs:__imp_GetLastError
0x1800edc7a  mov     r9d, r15d
0x1800edc7d  lea     rdx, aGettokeninform; "GetTokenInformation"
0x1800edc84  mov     r8d, eax
0x1800edc87  call    WfpReportSysErrorAsWinError
0x1800edc8c  mov     rdi, rax
0x1800edc8f  jmp     short loc_1800EDC2B
```
