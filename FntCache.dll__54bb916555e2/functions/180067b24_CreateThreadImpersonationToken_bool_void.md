# CreateThreadImpersonationToken(bool,void * *)

- ea: `0x180067b24`
- end: `0x180067bf3`
- name: `?CreateThreadImpersonationToken@@YAJ_NPEAPEAX@Z`
- size: `207`
- prototype: `int(bool, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180067cbc`
- `0x1800b9ef0`

## callees

- `0x180067b24`
- `0x180067bfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180067b62`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180067b62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180067b4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180067b4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067b85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067be0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067b85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067be0`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x180067bc5`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x180067bc5`

## pseudocode

```c
__int64 __fastcall CreateThreadImpersonationToken(__int64 a1, void **a2)
{
  HANDLE CurrentThread; // rax
  __int64 v4; // rdx
  unsigned int Error; // ebx
  void *TokenHandle; // [rsp+68h] [rbp+10h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    v4 = 176;
LABEL_3:
    Error = LogLastError(0x6E656B6F74LL, v4);
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return Error;
  }
  if ( !CreateRestrictedToken(TokenHandle, 4u, 0, 0, 0, 0, 0, 0, a2) )
  {
    v4 = 192;
    goto LABEL_3;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180067b24  mov     [rsp+arg_0], rbx
0x180067b29  push    rdi
0x180067b2a  sub     rsp, 50h
0x180067b2e  mov     rdi, rdx
0x180067b31  mov     qword ptr [rdx], 0
0x180067b38  mov     rbx, 6E656B6F74h
0x180067b42  mov     [rsp+58h+TokenHandle], 0
0x180067b4b  call    cs:__imp_GetCurrentThread
0x180067b51  mov     edx, 0Eh; DesiredAccess
0x180067b56  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180067b5b  mov     rcx, rax; ThreadHandle
0x180067b5e  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180067b62  call    cs:__imp_OpenThreadToken
0x180067b68  test    eax, eax
0x180067b6a  jnz     short loc_180067B8F
0x180067b6c  mov     edx, 0B0h
0x180067b71  mov     rcx, rbx
0x180067b74  call    ?LogLastError@@YAJVEventTag@@I@Z; LogLastError(EventTag,uint)
0x180067b79  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180067b7e  mov     ebx, eax
0x180067b80  test    rcx, rcx
0x180067b83  jz      short loc_180067B8B
0x180067b85  call    cs:__imp_CloseHandle
0x180067b8b  mov     eax, ebx
0x180067b8d  jmp     short loc_180067BE8
0x180067b8f  mov     rcx, [rsp+58h+TokenHandle]; ExistingTokenHandle
0x180067b94  xor     r9d, r9d; SidsToDisable
0x180067b97  mov     [rsp+58h+NewTokenHandle], rdi; NewTokenHandle
0x180067b9c  xor     r8d, r8d; DisableSidCount
0x180067b9f  mov     [rsp+58h+SidsToRestrict], 0; SidsToRestrict
0x180067ba8  mov     [rsp+58h+RestrictedSidCount], 0; RestrictedSidCount
0x180067bb0  lea     edx, [r9+4]; Flags
0x180067bb4  mov     [rsp+58h+PrivilegesToDelete], 0; PrivilegesToDelete
0x180067bbd  mov     [rsp+58h+DeletePrivilegeCount], 0; DeletePrivilegeCount
0x180067bc5  call    cs:__imp_CreateRestrictedToken
0x180067bcb  test    eax, eax
0x180067bcd  jnz     short loc_180067BD6
0x180067bcf  mov     edx, 0C0h
0x180067bd4  jmp     short loc_180067B71
0x180067bd6  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180067bdb  test    rcx, rcx
0x180067bde  jz      short loc_180067BE6
0x180067be0  call    cs:__imp_CloseHandle
0x180067be6  xor     eax, eax
0x180067be8  mov     rbx, [rsp+58h+arg_0]
0x180067bed  add     rsp, 50h
0x180067bf1  pop     rdi
0x180067bf2  retn
```
