# IkeInitializeTokenInformation

- ea: `0x180073b74`
- end: `0x180073d3e`
- name: `IkeInitializeTokenInformation`
- size: `458`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180073284`

## callees

- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x1800163b0`
- `0x180050850`
- `0x180073b74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073bd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073bd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073c89`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180073bd2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180073c15`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180073bd2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180073c15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073cbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073cbe`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180073c7f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180073c7f`

## string_xrefs

- `0x180073c25`: `GetTokenInformation`
- `0x180073c8f`: `ConvertStringSidToSidW`
- `0x180073ccd`: `IkeInitializeTokenInformation`

## pseudocode

```c
__int64 __fastcall IkeInitializeTokenInformation(HANDLE TokenHandle, __int64 a2, _QWORD *a3, int a4)
{
  __int64 v8; // rdi
  unsigned int *v9; // rbx
  __int64 v10; // r8
  DWORD LastError; // eax
  __int64 v12; // rcx
  const char *v13; // rdx
  __int64 v14; // r14
  unsigned int i; // edx
  __int64 v16; // rcx
  int v18; // eax
  __int64 v19; // [rsp+30h] [rbp-30h] BYREF
  LPVOID TokenInformation; // [rsp+38h] [rbp-28h] BYREF
  DWORD TokenInformationLength; // [rsp+40h] [rbp-20h] BYREF
  PSID Sid; // [rsp+48h] [rbp-18h] BYREF

  TokenInformationLength = 0;
  TokenInformation = 0;
  v19 = 0;
  Sid = 0;
  GetTokenInformation(TokenHandle, TokenGroupsAndPrivileges, 0, 0, &TokenInformationLength);
  GetLastError();
  v8 = WfpMemAlloc(TokenInformationLength, 8u);
  if ( !v8 )
  {
    v9 = (unsigned int *)TokenInformation;
    if ( !GetTokenInformation(
            TokenHandle,
            TokenGroupsAndPrivileges,
            TokenInformation,
            TokenInformationLength,
            &TokenInformationLength) )
    {
      LastError = GetLastError();
      v13 = "GetTokenInformation";
      goto LABEL_10;
    }
    if ( !a4 )
    {
      *(_DWORD *)a2 = *(_DWORD *)TokenInformation;
      *(_QWORD *)(a2 + 8) = *((_QWORD *)v9 + 1);
      goto LABEL_17;
    }
    v8 = WfpMemAllocArray((unsigned int)(*(_DWORD *)TokenInformation + 1), 16, v10, &v19);
    if ( !v8 )
    {
      v14 = v19;
      for ( i = 0; i < *v9; *(_OWORD *)(v14 + 16 * v16) = *(_OWORD *)(*((_QWORD *)v9 + 1) + 16 * v16) )
        v16 = i++;
      if ( !ConvertStringSidToSidW(L"S-1-5-65-1", &Sid) )
      {
        LastError = GetLastError();
        v13 = "ConvertStringSidToSidW";
LABEL_10:
        v8 = WfpReportSysErrorAsWinError(v12, v13, LastError, 1);
        if ( !v8 )
          return IkeReturnError(v8, "IkeInitializeTokenInformation");
        goto LABEL_11;
      }
      *(_QWORD *)(v14 + 16LL * *v9) = Sid;
      *(_DWORD *)(v14 + 16LL * *v9 + 8) = 6;
      v18 = *v9 + 1;
      *(_QWORD *)(a2 + 8) = v14;
      *(_DWORD *)a2 = v18;
LABEL_17:
      *(_DWORD *)(a2 + 16) = v9[4];
      *(_QWORD *)(a2 + 24) = *((_QWORD *)v9 + 3);
      *a3 = v9;
      return IkeReturnError(v8, "IkeInitializeTokenInformation");
    }
  }
LABEL_11:
  WfpMemFree(&v19);
  if ( Sid )
    LocalFree(Sid);
  WfpMemFree(&TokenInformation);
  return IkeReturnError(v8, "IkeInitializeTokenInformation");
}

```

## disassembly

```asm
0x180073b74  push    rbp
0x180073b76  push    rbx
0x180073b77  push    rsi
0x180073b78  push    rdi
0x180073b79  push    r12
0x180073b7b  push    r14
0x180073b7d  push    r15
0x180073b7f  mov     rbp, rsp
0x180073b82  sub     rsp, 60h
0x180073b86  mov     rax, cs:__security_cookie
0x180073b8d  xor     rax, rsp
0x180073b90  mov     [rbp+var_10], rax
0x180073b94  mov     r14d, r9d
0x180073b97  mov     [rbp+TokenInformationLength], 0
0x180073b9e  xor     r9d, r9d; TokenInformationLength
0x180073ba1  mov     [rbp+TokenInformation], 0
0x180073ba9  mov     r12, r8
0x180073bac  mov     [rbp+var_30], 0
0x180073bb4  mov     rsi, rdx
0x180073bb7  mov     [rbp+Sid], 0
0x180073bbf  lea     rax, [rbp+TokenInformationLength]
0x180073bc3  xor     r8d, r8d; TokenInformation
0x180073bc6  lea     edx, [r9+0Dh]; TokenInformationClass
0x180073bca  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180073bcf  mov     r15, rcx
0x180073bd2  call    cs:__imp_GetTokenInformation
0x180073bd8  call    cs:__imp_GetLastError
0x180073bde  mov     ecx, [rbp+TokenInformationLength]; dwBytes
0x180073be1  lea     r8, [rbp+TokenInformation]
0x180073be5  mov     edx, 8; dwFlags
0x180073bea  call    WfpMemAlloc
0x180073bef  mov     rdi, rax
0x180073bf2  test    rax, rax
0x180073bf5  jnz     loc_180073CAC
0x180073bfb  mov     rbx, [rbp+TokenInformation]
0x180073bff  lea     rax, [rbp+TokenInformationLength]
0x180073c03  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180073c07  lea     edx, [rdi+0Dh]; TokenInformationClass
0x180073c0a  mov     r8, rbx; TokenInformation
0x180073c0d  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180073c12  mov     rcx, r15; TokenHandle
0x180073c15  call    cs:__imp_GetTokenInformation
0x180073c1b  test    eax, eax
0x180073c1d  jnz     short loc_180073C2E
0x180073c1f  call    cs:__imp_GetLastError
0x180073c25  lea     rdx, aGettokeninform; "GetTokenInformation"
0x180073c2c  jmp     short loc_180073C96
0x180073c2e  test    r14d, r14d
0x180073c31  jz      loc_180073D1E
0x180073c37  mov     ecx, [rbx]
0x180073c39  lea     r9, [rbp+var_30]
0x180073c3d  inc     ecx
0x180073c3f  mov     edx, 10h
0x180073c44  call    WfpMemAllocArray
0x180073c49  mov     rdi, rax
0x180073c4c  test    rax, rax
0x180073c4f  jnz     short loc_180073CAC
0x180073c51  mov     r14, [rbp+var_30]
0x180073c55  xor     edx, edx
0x180073c57  cmp     [rbx], edx
0x180073c59  jbe     short loc_180073C74
0x180073c5b  mov     rax, [rbx+8]
0x180073c5f  mov     ecx, edx
0x180073c61  inc     edx
0x180073c63  add     rcx, rcx
0x180073c66  movups  xmm0, xmmword ptr [rax+rcx*8]
0x180073c6a  movdqu  xmmword ptr [r14+rcx*8], xmm0
0x180073c70  cmp     edx, [rbx]
0x180073c72  jb      short loc_180073C5B
0x180073c74  lea     rdx, [rbp+Sid]; Sid
0x180073c78  lea     rcx, StringSid; "S-1-5-65-1"
0x180073c7f  call    cs:__imp_ConvertStringSidToSidW
0x180073c85  test    eax, eax
0x180073c87  jnz     short loc_180073CF7
0x180073c89  call    cs:__imp_GetLastError
0x180073c8f  lea     rdx, aConvertstrings_1; "ConvertStringSidToSidW"
0x180073c96  mov     r9d, 1
0x180073c9c  mov     r8d, eax
0x180073c9f  call    WfpReportSysErrorAsWinError
0x180073ca4  mov     rdi, rax
0x180073ca7  test    rax, rax
0x180073caa  jz      short loc_180073CCD
0x180073cac  lea     rcx, [rbp+var_30]
0x180073cb0  call    WfpMemFree
0x180073cb5  mov     rcx, [rbp+Sid]; hMem
0x180073cb9  test    rcx, rcx
0x180073cbc  jz      short loc_180073CC4
0x180073cbe  call    cs:__imp_LocalFree
0x180073cc4  lea     rcx, [rbp+TokenInformation]
0x180073cc8  call    WfpMemFree
0x180073ccd  lea     rdx, aIkeinitializet; "IkeInitializeTokenInformation"
0x180073cd4  mov     rcx, rdi
0x180073cd7  call    IkeReturnError
0x180073cdc  mov     rcx, [rbp+var_10]
0x180073ce0  xor     rcx, rsp; StackCookie
0x180073ce3  call    __security_check_cookie
0x180073ce8  add     rsp, 60h
0x180073cec  pop     r15
0x180073cee  pop     r14
0x180073cf0  pop     r12
0x180073cf2  pop     rdi
0x180073cf3  pop     rsi
0x180073cf4  pop     rbx
0x180073cf5  pop     rbp
0x180073cf6  retn
0x180073cf7  mov     ecx, [rbx]
0x180073cf9  mov     rax, [rbp+Sid]
0x180073cfd  add     rcx, rcx
0x180073d00  mov     [r14+rcx*8], rax
0x180073d04  mov     eax, [rbx]
0x180073d06  add     rax, rax
0x180073d09  mov     dword ptr [r14+rax*8+8], 6
0x180073d12  mov     eax, [rbx]
0x180073d14  inc     eax
0x180073d16  mov     [rsi+8], r14
0x180073d1a  mov     [rsi], eax
0x180073d1c  jmp     short loc_180073D2A
0x180073d1e  mov     eax, [rbx]
0x180073d20  mov     [rsi], eax
0x180073d22  mov     rax, [rbx+8]
0x180073d26  mov     [rsi+8], rax
0x180073d2a  mov     eax, [rbx+10h]
0x180073d2d  mov     [rsi+10h], eax
0x180073d30  mov     rax, [rbx+18h]
0x180073d34  mov     [rsi+18h], rax
0x180073d38  mov     [r12], rbx
0x180073d3c  jmp     short loc_180073CCD
```
