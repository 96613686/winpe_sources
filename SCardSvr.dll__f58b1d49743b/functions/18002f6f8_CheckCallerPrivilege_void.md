# CheckCallerPrivilege(void)

- ea: `0x18002f6f8`
- end: `0x18002f803`
- name: `?CheckCallerPrivilege@@YAKXZ`
- size: `267`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f5f0`

## callees

- `0x18002f6f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f747`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f727`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f727`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002f73d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002f73d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f7f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f7f3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002f792`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002f7ac`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002f792`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002f7ac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f76f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f76f`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18002f7d2`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18002f7d2`
- `ntdll!RtlGetActiveConsoleId` at `0x18002f77b`
- `ntdll!RtlGetActiveConsoleId` at `0x18002f77b`

## pseudocode

```c
__int64 CheckCallerPrivilege(void)
{
  struct _SERVICE_THREAD_SECURITY_INFO *v0; // rdi
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  char v5; // [rsp+60h] [rbp+20h] BYREF
  WINBOOL IsMember; // [rsp+68h] [rbp+28h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+30h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+38h] BYREF

  v0 = qword_18004BFA0;
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  IsMember = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
    || !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
  {
    goto LABEL_2;
  }
  LastError = 0;
  if ( TokenInformation == (unsigned int)RtlGetActiveConsoleId() )
    goto LABEL_13;
  if ( !CheckTokenMembership(TokenHandle, *((PSID *)v0 + 1), &IsMember) )
    goto LABEL_2;
  if ( IsMember )
    goto LABEL_13;
  if ( !CheckTokenMembership(TokenHandle, *(PSID *)v0, &IsMember) )
    goto LABEL_2;
  if ( IsMember )
    goto LABEL_13;
  if ( *((_BYTE *)v0 + 32) )
  {
    v5 = 0;
    if ( (int)CapabilityCheck(TokenHandle, L"secondaryAuthenticationFactor", &v5) >= 0 )
    {
      if ( v5 )
        goto LABEL_13;
      goto LABEL_12;
    }
LABEL_2:
    LastError = GetLastError();
    goto LABEL_13;
  }
LABEL_12:
  LastError = 5;
LABEL_13:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18002f6f8  push    rbp
0x18002f6fa  push    rbx
0x18002f6fb  push    rdi
0x18002f6fc  mov     rbp, rsp
0x18002f6ff  sub     rsp, 40h
0x18002f703  mov     rdi, cs:qword_18004BFA0
0x18002f70a  mov     [rbp+TokenHandle], 0
0x18002f712  mov     [rbp+TokenInformation], 0
0x18002f719  mov     [rbp+arg_18], 0
0x18002f720  mov     [rbp+IsMember], 0
0x18002f727  call    cs:__imp_GetCurrentThread
0x18002f72d  mov     edx, 8; DesiredAccess
0x18002f732  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002f736  mov     rcx, rax; ThreadHandle
0x18002f739  lea     r8d, [rdx-7]; OpenAsSelf
0x18002f73d  call    cs:__imp_OpenThreadToken
0x18002f743  test    eax, eax
0x18002f745  jnz     short loc_18002F754
0x18002f747  call    cs:__imp_GetLastError
0x18002f74d  mov     ebx, eax
0x18002f74f  jmp     loc_18002F7EA
0x18002f754  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002f758  lea     rax, [rbp+arg_18]
0x18002f75c  mov     r9d, 4; TokenInformationLength
0x18002f762  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x18002f767  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002f76b  lea     edx, [r9+8]; TokenInformationClass
0x18002f76f  call    cs:__imp_GetTokenInformation
0x18002f775  test    eax, eax
0x18002f777  jz      short loc_18002F747
0x18002f779  xor     ebx, ebx
0x18002f77b  call    cs:__imp_RtlGetActiveConsoleId
0x18002f781  cmp     [rbp+TokenInformation], eax
0x18002f784  jz      short loc_18002F7EA
0x18002f786  mov     rdx, [rdi+8]; SidToCheck
0x18002f78a  lea     r8, [rbp+IsMember]; IsMember
0x18002f78e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002f792  call    cs:__imp_CheckTokenMembership
0x18002f798  test    eax, eax
0x18002f79a  jz      short loc_18002F747
0x18002f79c  cmp     [rbp+IsMember], ebx
0x18002f79f  jnz     short loc_18002F7EA
0x18002f7a1  mov     rdx, [rdi]; SidToCheck
0x18002f7a4  lea     r8, [rbp+IsMember]; IsMember
0x18002f7a8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002f7ac  call    cs:__imp_CheckTokenMembership
0x18002f7b2  test    eax, eax
0x18002f7b4  jz      short loc_18002F747
0x18002f7b6  cmp     [rbp+IsMember], ebx
0x18002f7b9  jnz     short loc_18002F7EA
0x18002f7bb  cmp     [rdi+20h], bl
0x18002f7be  jz      short loc_18002F7E5
0x18002f7c0  mov     rcx, [rbp+TokenHandle]
0x18002f7c4  lea     r8, [rbp+arg_0]
0x18002f7c8  lea     rdx, aSecondaryauthe; "secondaryAuthenticationFactor"
0x18002f7cf  mov     [rbp+arg_0], bl
0x18002f7d2  call    cs:__imp_CapabilityCheck
0x18002f7d8  test    eax, eax
0x18002f7da  js      loc_18002F747
0x18002f7e0  cmp     [rbp+arg_0], bl
0x18002f7e3  jnz     short loc_18002F7EA
0x18002f7e5  mov     ebx, 5
0x18002f7ea  mov     rcx, [rbp+TokenHandle]; hObject
0x18002f7ee  test    rcx, rcx
0x18002f7f1  jz      short loc_18002F7F9
0x18002f7f3  call    cs:__imp_CloseHandle
0x18002f7f9  mov     eax, ebx
0x18002f7fb  add     rsp, 40h
0x18002f7ff  pop     rdi
0x18002f800  pop     rbx
0x18002f801  pop     rbp
0x18002f802  retn
```
