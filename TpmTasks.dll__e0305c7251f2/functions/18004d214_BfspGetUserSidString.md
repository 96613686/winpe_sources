# BfspGetUserSidString

- ea: `0x18004d214`
- end: `0x18004d356`
- name: `BfspGetUserSidString`
- size: `322`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004d3e0`

## callees

- `0x18004cdd4`
- `0x18004d214`
- `0x18004d35c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d335`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d335`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d295`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d327`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d295`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d327`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d2a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d2a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d341`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004d341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d2f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d2f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d31c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d31c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004d26b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004d2d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004d26b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004d2d6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004d2ea`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004d2ea`

## string_xrefs

- `0x18004d2fc`: `Failed to convert user SID! Error code = %#x`
- `0x18004d288`: `Failed to get token information! Error code = %#x`

## pseudocode

```c
__int64 __fastcall BfspGetUserSidString(LPWSTR *StringSid)
{
  PSID *v2; // rsi
  unsigned int UserToken; // ebx
  DWORD LastError; // edi
  DWORD v5; // eax
  const wchar_t *v6; // rdx
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v9; // rax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  TokenHandle = 0;
  v2 = 0;
  UserToken = BfspGetUserToken(&TokenHandle);
  if ( !UserToken )
  {
    LastError = GetLastError();
    goto LABEL_12;
  }
  UserToken = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( !UserToken && GetLastError() != 122 )
    goto LABEL_5;
  v7 = TokenInformationLength;
  ProcessHeap = GetProcessHeap();
  LastError = 8;
  v2 = (PSID *)HeapAlloc(ProcessHeap, 8u, v7);
  if ( !v2 )
  {
    UserToken = 0;
    goto LABEL_12;
  }
  UserToken = GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength);
  if ( UserToken )
  {
    LastError = 0;
    UserToken = ConvertSidToStringSidW(*v2, StringSid);
    if ( UserToken )
      goto LABEL_12;
    v5 = GetLastError();
    v6 = L"Failed to convert user SID! Error code = %#x";
  }
  else
  {
LABEL_5:
    v5 = GetLastError();
    v6 = L"Failed to get token information! Error code = %#x";
  }
  LastError = v5;
  BfspLogMessage(4, v6, v5);
LABEL_12:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v2 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v2);
  }
  if ( !UserToken )
    SetLastError(LastError);
  return UserToken;
}

```

## disassembly

```asm
0x18004d214  mov     rax, rsp
0x18004d217  mov     [rax+8], rbx
0x18004d21b  push    rbp
0x18004d21c  push    rsi
0x18004d21d  push    rdi
0x18004d21e  sub     rsp, 30h
0x18004d222  mov     rbp, rcx
0x18004d225  mov     dword ptr [rax+10h], 0
0x18004d22c  lea     rcx, [rax+18h]; TokenHandle
0x18004d230  mov     qword ptr [rax+18h], 0
0x18004d238  xor     esi, esi
0x18004d23a  call    BfspGetUserToken
0x18004d23f  mov     ebx, eax
0x18004d241  test    eax, eax
0x18004d243  jnz     short loc_18004D252
0x18004d245  call    cs:__imp_GetLastError
0x18004d24b  mov     edi, eax
0x18004d24d  jmp     loc_18004D312
0x18004d252  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18004d257  lea     rax, [rsp+48h+TokenInformationLength]
0x18004d25c  xor     r9d, r9d; TokenInformationLength
0x18004d25f  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18004d264  xor     r8d, r8d; TokenInformation
0x18004d267  lea     edx, [r9+1]; TokenInformationClass
0x18004d26b  call    cs:__imp_GetTokenInformation
0x18004d271  mov     ebx, eax
0x18004d273  test    eax, eax
0x18004d275  jnz     short loc_18004D291
0x18004d277  call    cs:__imp_GetLastError
0x18004d27d  cmp     eax, 7Ah ; 'z'
0x18004d280  jz      short loc_18004D291
0x18004d282  call    cs:__imp_GetLastError
0x18004d288  lea     rdx, aFailedToGetTok; "Failed to get token information! Error "...
0x18004d28f  jmp     short loc_18004D303
0x18004d291  mov     ebx, [rsp+48h+TokenInformationLength]
0x18004d295  call    cs:__imp_GetProcessHeap
0x18004d29b  mov     edi, 8
0x18004d2a0  mov     r8d, ebx; dwBytes
0x18004d2a3  mov     rcx, rax; hHeap
0x18004d2a6  mov     edx, edi; dwFlags
0x18004d2a8  call    cs:__imp_HeapAlloc
0x18004d2ae  mov     rsi, rax
0x18004d2b1  test    rax, rax
0x18004d2b4  jnz     short loc_18004D2BA
0x18004d2b6  xor     ebx, ebx
0x18004d2b8  jmp     short loc_18004D312
0x18004d2ba  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18004d2bf  lea     rax, [rsp+48h+TokenInformationLength]
0x18004d2c4  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18004d2c9  mov     r8, rsi; TokenInformation
0x18004d2cc  mov     edx, 1; TokenInformationClass
0x18004d2d1  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18004d2d6  call    cs:__imp_GetTokenInformation
0x18004d2dc  mov     ebx, eax
0x18004d2de  test    eax, eax
0x18004d2e0  jz      short loc_18004D282
0x18004d2e2  mov     rcx, [rsi]; Sid
0x18004d2e5  mov     rdx, rbp; StringSid
0x18004d2e8  xor     edi, edi
0x18004d2ea  call    cs:__imp_ConvertSidToStringSidW
0x18004d2f0  mov     ebx, eax
0x18004d2f2  test    eax, eax
0x18004d2f4  jnz     short loc_18004D312
0x18004d2f6  call    cs:__imp_GetLastError
0x18004d2fc  lea     rdx, aFailedToConver; "Failed to convert user SID! Error code "...
0x18004d303  mov     r8d, eax
0x18004d306  mov     ecx, 4
0x18004d30b  mov     edi, eax
0x18004d30d  call    BfspLogMessage
0x18004d312  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18004d317  test    rcx, rcx
0x18004d31a  jz      short loc_18004D322
0x18004d31c  call    cs:__imp_CloseHandle
0x18004d322  test    rsi, rsi
0x18004d325  jz      short loc_18004D33B
0x18004d327  call    cs:__imp_GetProcessHeap
0x18004d32d  mov     r8, rsi; lpMem
0x18004d330  xor     edx, edx; dwFlags
0x18004d332  mov     rcx, rax; hHeap
0x18004d335  call    cs:__imp_HeapFree
0x18004d33b  test    ebx, ebx
0x18004d33d  jnz     short loc_18004D347
0x18004d33f  mov     ecx, edi; dwErrCode
0x18004d341  call    cs:__imp_SetLastError
0x18004d347  mov     eax, ebx
0x18004d349  mov     rbx, [rsp+48h+arg_0]
0x18004d34e  add     rsp, 30h
0x18004d352  pop     rdi
0x18004d353  pop     rsi
0x18004d354  pop     rbp
0x18004d355  retn
```
