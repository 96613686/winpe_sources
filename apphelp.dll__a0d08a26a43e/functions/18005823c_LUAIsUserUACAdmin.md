# LUAIsUserUACAdmin

- ea: `0x18005823c`
- end: `0x180058345`
- name: `LUAIsUserUACAdmin`
- size: `265`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180055ae0`
- `0x180055bd0`
- `0x180055cc0`

## callees

- `0x1800580a8`
- `0x18005814c`
- `0x180058190`
- `0x18005823c`
- `0x18005834c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800582fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800582fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058310`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180058258`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180058258`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005826a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005826a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005832c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005832c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800582df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800582df`

## pseudocode

```c
__int64 __fastcall LUAIsUserUACAdmin(_DWORD *a1)
{
  HANDLE CurrentProcess; // rax
  NTSTATUS v3; // ebx
  int v4; // eax
  void *v5; // rcx
  DWORD ReturnLength; // [rsp+50h] [rbp+20h] BYREF
  void *TokenInformation; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
  {
    if ( (unsigned int)Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline() )
    {
      v3 = LUAIsUserUACAdminEx(TokenHandle);
    }
    else
    {
      ReturnLength = 0;
      LODWORD(TokenInformation) = 0;
      v3 = LUAIsElevatedToken(TokenHandle, &ReturnLength, &TokenInformation);
      if ( v3 >= 0 )
      {
        if ( ReturnLength )
        {
          *a1 = _LUAIsTokenAdmin(TokenHandle);
        }
        else
        {
          TokenInformation = 0;
          ReturnLength = 8;
          if ( GetTokenInformation(TokenHandle, TokenLinkedToken, &TokenInformation, 8u, &ReturnLength)
            && TokenInformation )
          {
            v4 = _LUAIsTokenAdmin(TokenInformation);
            v5 = TokenInformation;
            *a1 = v4;
            CloseHandle(v5);
          }
        }
      }
    }
    CloseHandle(TokenHandle);
  }
  else if ( (int)GetLastError() > 0 )
  {
    return (unsigned __int16)GetLastError() | 0xC0070000;
  }
  else
  {
    return GetLastError();
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18005823c  push    rbp
0x18005823e  push    rbx
0x18005823f  push    rdi
0x180058240  mov     rbp, rsp
0x180058243  sub     rsp, 30h
0x180058247  mov     rdi, rcx
0x18005824a  mov     dword ptr [rcx], 0
0x180058250  mov     [rbp+TokenHandle], 0
0x180058258  call    cs:__imp_GetCurrentProcess
0x18005825e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180058262  mov     edx, 0Ah; DesiredAccess
0x180058267  mov     rcx, rax; ProcessHandle
0x18005826a  call    cs:__imp_OpenProcessToken
0x180058270  test    eax, eax
0x180058272  jz      loc_180058318
0x180058278  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x18005827d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180058281  test    eax, eax
0x180058283  jz      short loc_180058291
0x180058285  mov     rdx, rdi
0x180058288  call    LUAIsUserUACAdminEx
0x18005828d  mov     ebx, eax
0x18005828f  jmp     short loc_18005830C
0x180058291  lea     r8, [rbp+TokenInformation]
0x180058295  mov     [rbp+arg_0], 0
0x18005829c  lea     rdx, [rbp+arg_0]
0x1800582a0  mov     dword ptr [rbp+TokenInformation], 0
0x1800582a7  call    LUAIsElevatedToken
0x1800582ac  mov     ebx, eax
0x1800582ae  test    eax, eax
0x1800582b0  js      short loc_18005830C
0x1800582b2  cmp     [rbp+arg_0], 0
0x1800582b6  mov     rcx, [rbp+TokenHandle]; void *
0x1800582ba  jnz     short loc_180058305
0x1800582bc  mov     r9d, 8; TokenInformationLength
0x1800582c2  mov     [rbp+TokenInformation], 0
0x1800582ca  lea     rax, [rbp+arg_0]
0x1800582ce  mov     [rbp+arg_0], r9d
0x1800582d2  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800582d6  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800582db  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800582df  call    cs:__imp_GetTokenInformation
0x1800582e5  test    eax, eax
0x1800582e7  jz      short loc_18005830C
0x1800582e9  mov     rcx, [rbp+TokenInformation]; void *
0x1800582ed  test    rcx, rcx
0x1800582f0  jz      short loc_18005830C
0x1800582f2  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x1800582f7  mov     rcx, [rbp+TokenInformation]; hObject
0x1800582fb  mov     [rdi], eax
0x1800582fd  call    cs:__imp_CloseHandle
0x180058303  jmp     short loc_18005830C
0x180058305  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x18005830a  mov     [rdi], eax
0x18005830c  mov     rcx, [rbp+TokenHandle]; hObject
0x180058310  call    cs:__imp_CloseHandle
0x180058316  jmp     short loc_18005833B
0x180058318  call    cs:__imp_GetLastError
0x18005831e  test    eax, eax
0x180058320  jg      short loc_18005832C
0x180058322  call    cs:__imp_GetLastError
0x180058328  mov     ebx, eax
0x18005832a  jmp     short loc_18005833B
0x18005832c  call    cs:__imp_GetLastError
0x180058332  movzx   ebx, ax
0x180058335  or      ebx, 0C0070000h
0x18005833b  mov     eax, ebx
0x18005833d  add     rsp, 30h
0x180058341  pop     rdi
0x180058342  pop     rbx
0x180058343  pop     rbp
0x180058344  retn
```
