# BfspGetUserSidString

- ea: `0x14000ea4c`
- end: `0x14000eb8e`
- name: `BfspGetUserSidString`
- size: `322`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14000ec18`

## callees

- `0x14000e628`
- `0x14000ea4c`
- `0x14000eb94`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000eb79`
- `KERNEL32!SetLastError` at `0x14000eb79`
- `KERNEL32!GetLastError` at `0x14000ea7d`
- `KERNEL32!GetLastError` at `0x14000eaaf`
- `KERNEL32!GetLastError` at `0x14000eaba`
- `KERNEL32!GetLastError` at `0x14000eb2e`
- `KERNEL32!GetLastError` at `0x14000ea7d`
- `KERNEL32!GetLastError` at `0x14000eaaf`
- `KERNEL32!GetLastError` at `0x14000eaba`
- `KERNEL32!GetLastError` at `0x14000eb2e`
- `KERNEL32!HeapFree` at `0x14000eb6d`
- `KERNEL32!HeapFree` at `0x14000eb6d`
- `KERNEL32!HeapAlloc` at `0x14000eae0`
- `KERNEL32!HeapAlloc` at `0x14000eae0`
- `KERNEL32!GetProcessHeap` at `0x14000eacd`
- `KERNEL32!GetProcessHeap` at `0x14000eb5f`
- `KERNEL32!GetProcessHeap` at `0x14000eacd`
- `KERNEL32!GetProcessHeap` at `0x14000eb5f`
- `KERNEL32!CloseHandle` at `0x14000eb54`
- `KERNEL32!CloseHandle` at `0x14000eb54`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14000eb22`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14000eb22`
- `ADVAPI32!GetTokenInformation` at `0x14000eaa3`
- `ADVAPI32!GetTokenInformation` at `0x14000eb0e`
- `ADVAPI32!GetTokenInformation` at `0x14000eaa3`
- `ADVAPI32!GetTokenInformation` at `0x14000eb0e`

## string_xrefs

- `0x14000eac0`: `Failed to get token information! Error code = %#x`
- `0x14000eb34`: `Failed to convert user SID! Error code = %#x`

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
0x14000ea4c  mov     rax, rsp
0x14000ea4f  mov     [rax+8], rbx
0x14000ea53  push    rbp
0x14000ea54  push    rsi
0x14000ea55  push    rdi
0x14000ea56  sub     rsp, 30h
0x14000ea5a  mov     rbp, rcx
0x14000ea5d  mov     dword ptr [rax+10h], 0
0x14000ea64  lea     rcx, [rax+18h]; TokenHandle
0x14000ea68  mov     qword ptr [rax+18h], 0
0x14000ea70  xor     esi, esi
0x14000ea72  call    BfspGetUserToken
0x14000ea77  mov     ebx, eax
0x14000ea79  test    eax, eax
0x14000ea7b  jnz     short loc_14000EA8A
0x14000ea7d  call    cs:__imp_GetLastError
0x14000ea83  mov     edi, eax
0x14000ea85  jmp     loc_14000EB4A
0x14000ea8a  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x14000ea8f  lea     rax, [rsp+48h+TokenInformationLength]
0x14000ea94  xor     r9d, r9d; TokenInformationLength
0x14000ea97  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14000ea9c  xor     r8d, r8d; TokenInformation
0x14000ea9f  lea     edx, [r9+1]; TokenInformationClass
0x14000eaa3  call    cs:__imp_GetTokenInformation
0x14000eaa9  mov     ebx, eax
0x14000eaab  test    eax, eax
0x14000eaad  jnz     short loc_14000EAC9
0x14000eaaf  call    cs:__imp_GetLastError
0x14000eab5  cmp     eax, 7Ah ; 'z'
0x14000eab8  jz      short loc_14000EAC9
0x14000eaba  call    cs:__imp_GetLastError
0x14000eac0  lea     rdx, aFailedToGetTok; "Failed to get token information! Error "...
0x14000eac7  jmp     short loc_14000EB3B
0x14000eac9  mov     ebx, [rsp+48h+TokenInformationLength]
0x14000eacd  call    cs:__imp_GetProcessHeap
0x14000ead3  mov     edi, 8
0x14000ead8  mov     r8d, ebx; dwBytes
0x14000eadb  mov     rcx, rax; hHeap
0x14000eade  mov     edx, edi; dwFlags
0x14000eae0  call    cs:__imp_HeapAlloc
0x14000eae6  mov     rsi, rax
0x14000eae9  test    rax, rax
0x14000eaec  jnz     short loc_14000EAF2
0x14000eaee  xor     ebx, ebx
0x14000eaf0  jmp     short loc_14000EB4A
0x14000eaf2  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x14000eaf7  lea     rax, [rsp+48h+TokenInformationLength]
0x14000eafc  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x14000eb01  mov     r8, rsi; TokenInformation
0x14000eb04  mov     edx, 1; TokenInformationClass
0x14000eb09  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14000eb0e  call    cs:__imp_GetTokenInformation
0x14000eb14  mov     ebx, eax
0x14000eb16  test    eax, eax
0x14000eb18  jz      short loc_14000EABA
0x14000eb1a  mov     rcx, [rsi]; Sid
0x14000eb1d  mov     rdx, rbp; StringSid
0x14000eb20  xor     edi, edi
0x14000eb22  call    cs:__imp_ConvertSidToStringSidW
0x14000eb28  mov     ebx, eax
0x14000eb2a  test    eax, eax
0x14000eb2c  jnz     short loc_14000EB4A
0x14000eb2e  call    cs:__imp_GetLastError
0x14000eb34  lea     rdx, aFailedToConver; "Failed to convert user SID! Error code "...
0x14000eb3b  mov     r8d, eax
0x14000eb3e  mov     ecx, 4
0x14000eb43  mov     edi, eax
0x14000eb45  call    BfspLogMessage
0x14000eb4a  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x14000eb4f  test    rcx, rcx
0x14000eb52  jz      short loc_14000EB5A
0x14000eb54  call    cs:__imp_CloseHandle
0x14000eb5a  test    rsi, rsi
0x14000eb5d  jz      short loc_14000EB73
0x14000eb5f  call    cs:__imp_GetProcessHeap
0x14000eb65  mov     r8, rsi; lpMem
0x14000eb68  xor     edx, edx; dwFlags
0x14000eb6a  mov     rcx, rax; hHeap
0x14000eb6d  call    cs:__imp_HeapFree
0x14000eb73  test    ebx, ebx
0x14000eb75  jnz     short loc_14000EB7F
0x14000eb77  mov     ecx, edi; dwErrCode
0x14000eb79  call    cs:__imp_SetLastError
0x14000eb7f  mov     eax, ebx
0x14000eb81  mov     rbx, [rsp+48h+arg_0]
0x14000eb86  add     rsp, 30h
0x14000eb8a  pop     rdi
0x14000eb8b  pop     rsi
0x14000eb8c  pop     rbp
0x14000eb8d  retn
```
