# IsUserInAdminGroup(void)

- ea: `0x18010b020`
- end: `0x18010b1a4`
- name: `?IsUserInAdminGroup@@YAHXZ`
- size: `388`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180101f00`
- `0x180103310`

## callees

- `0x18010b020`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18010b07f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18010b07f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010b061`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010b061`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18010b08f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18010b08f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010b075`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010b075`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010b168`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010b17f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010b168`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010b17f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18010b128`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18010b128`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010b0be`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010b0ed`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010b0be`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010b0ed`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18010b141`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18010b141`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18010b10a`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18010b10a`

## pseudocode

```c
__int64 IsUserInAdminGroup(void)
{
  __int64 result; // rax
  unsigned int v1; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-39h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-31h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp-2Dh] BYREF
  WINBOOL IsMember; // [rsp+40h] [rbp-29h] BYREF
  void *DuplicateTokenHandle; // [rsp+48h] [rbp-21h] BYREF
  DWORD cbSid[4]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE pSid[80]; // [rsp+60h] [rbp-9h] BYREF

  result = (unsigned int)dword_18015A4A8;
  DuplicateTokenHandle = 0;
  TokenHandle = 0;
  if ( dword_18015A4A8 == 2 )
  {
    v1 = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xAu, 1, &TokenHandle)
      || (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle)) )
    {
      TokenInformation = 0;
      ReturnLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
      {
        if ( (TokenInformation != 3
           || GetTokenInformation(TokenHandle, TokenLinkedToken, &DuplicateTokenHandle, 8u, &ReturnLength))
          && (DuplicateTokenHandle || DuplicateToken(TokenHandle, SecurityIdentification, &DuplicateTokenHandle)) )
        {
          cbSid[0] = 68;
          if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid) )
          {
            IsMember = 0;
            if ( CheckTokenMembership(DuplicateTokenHandle, pSid, &IsMember) )
            {
              if ( IsMember )
              {
                dword_18015A4A8 = 1;
                v1 = 1;
              }
            }
          }
        }
      }
    }
    if ( TokenHandle )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    if ( DuplicateTokenHandle )
      CloseHandle(DuplicateTokenHandle);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x18010b020  mov     [rsp-8+arg_0], rbx
0x18010b025  push    rbp
0x18010b026  lea     rbp, [rsp-57h]
0x18010b02b  sub     rsp, 0C0h
0x18010b032  mov     rax, cs:__security_cookie
0x18010b039  xor     rax, rsp
0x18010b03c  mov     [rbp+57h+var_10], rax
0x18010b040  mov     eax, cs:dword_18015A4A8
0x18010b046  mov     [rbp+57h+DuplicateTokenHandle], 0
0x18010b04e  mov     [rbp+57h+TokenHandle], 0
0x18010b056  cmp     eax, 2
0x18010b059  jnz     loc_18010B187
0x18010b05f  xor     ebx, ebx
0x18010b061  call    cs:__imp_GetCurrentThread
0x18010b067  mov     rcx, rax; ThreadHandle
0x18010b06a  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18010b06e  lea     edx, [rbx+0Ah]; DesiredAccess
0x18010b071  lea     r8d, [rbx+1]; OpenAsSelf
0x18010b075  call    cs:__imp_OpenThreadToken
0x18010b07b  test    eax, eax
0x18010b07d  jnz     short loc_18010B09D
0x18010b07f  call    cs:__imp_GetCurrentProcess
0x18010b085  mov     rcx, rax; ProcessHandle
0x18010b088  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18010b08c  lea     edx, [rbx+0Ah]; DesiredAccess
0x18010b08f  call    cs:__imp_OpenProcessToken
0x18010b095  test    eax, eax
0x18010b097  jz      loc_18010B15F
0x18010b09d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18010b0a1  lea     rax, [rbp+57h+var_84]
0x18010b0a5  mov     r9d, 4; TokenInformationLength
0x18010b0ab  mov     [rbp+57h+TokenInformation], ebx
0x18010b0ae  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18010b0b2  mov     [rbp+57h+var_84], ebx
0x18010b0b5  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18010b0ba  lea     edx, [r9+0Eh]; TokenInformationClass
0x18010b0be  call    cs:__imp_GetTokenInformation
0x18010b0c4  test    eax, eax
0x18010b0c6  jz      loc_18010B15F
0x18010b0cc  cmp     [rbp+57h+TokenInformation], 3
0x18010b0d0  jnz     short loc_18010B0F7
0x18010b0d2  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18010b0d6  lea     rax, [rbp+57h+var_84]
0x18010b0da  mov     r9d, 8; TokenInformationLength
0x18010b0e0  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18010b0e5  lea     r8, [rbp+57h+DuplicateTokenHandle]; TokenInformation
0x18010b0e9  lea     edx, [r9+0Bh]; TokenInformationClass
0x18010b0ed  call    cs:__imp_GetTokenInformation
0x18010b0f3  test    eax, eax
0x18010b0f5  jz      short loc_18010B15F
0x18010b0f7  cmp     [rbp+57h+DuplicateTokenHandle], rbx
0x18010b0fb  jnz     short loc_18010B114
0x18010b0fd  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x18010b101  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18010b105  mov     edx, 1; ImpersonationLevel
0x18010b10a  call    cs:__imp_DuplicateToken
0x18010b110  test    eax, eax
0x18010b112  jz      short loc_18010B15F
0x18010b114  xor     edx, edx; DomainSid
0x18010b116  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18010b11d  lea     r9, [rbp+57h+cbSid]; cbSid
0x18010b121  lea     r8, [rbp+57h+pSid]; pSid
0x18010b125  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18010b128  call    cs:__imp_CreateWellKnownSid
0x18010b12e  test    eax, eax
0x18010b130  jz      short loc_18010B15F
0x18010b132  mov     rcx, [rbp+57h+DuplicateTokenHandle]; TokenHandle
0x18010b136  lea     r8, [rbp+57h+IsMember]; IsMember
0x18010b13a  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x18010b13e  mov     [rbp+57h+IsMember], ebx
0x18010b141  call    cs:__imp_CheckTokenMembership
0x18010b147  test    eax, eax
0x18010b149  jz      short loc_18010B15F
0x18010b14b  cmp     [rbp+57h+IsMember], ebx
0x18010b14e  jz      short loc_18010B15F
0x18010b150  mov     cs:dword_18015A4A8, 1
0x18010b15a  mov     ebx, 1
0x18010b15f  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18010b163  test    rcx, rcx
0x18010b166  jz      short loc_18010B176
0x18010b168  call    cs:__imp_CloseHandle
0x18010b16e  mov     [rbp+57h+TokenHandle], 0
0x18010b176  mov     rcx, [rbp+57h+DuplicateTokenHandle]; hObject
0x18010b17a  test    rcx, rcx
0x18010b17d  jz      short loc_18010B185
0x18010b17f  call    cs:__imp_CloseHandle
0x18010b185  mov     eax, ebx
0x18010b187  mov     rcx, [rbp+57h+var_10]
0x18010b18b  xor     rcx, rsp; StackCookie
0x18010b18e  call    __security_check_cookie
0x18010b193  mov     rbx, [rsp+0C0h+arg_0]
0x18010b19b  add     rsp, 0C0h
0x18010b1a2  pop     rbp
0x18010b1a3  retn
```
