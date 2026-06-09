# LUAIsUserUACAdmin

- ea: `0x1800582fc`
- end: `0x180058405`
- name: `LUAIsUserUACAdmin`
- size: `265`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180055ae0`
- `0x180055bd0`
- `0x180055cc0`

## callees

- `0x180058168`
- `0x18005820c`
- `0x180058250`
- `0x1800582fc`
- `0x18005840c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800583bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800583d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800583bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800583d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180058318`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180058318`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005832a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005832a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800583d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800583e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800583ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800583d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800583e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800583ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005839f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005839f`

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
0x1800582fc  push    rbp
0x1800582fe  push    rbx
0x1800582ff  push    rdi
0x180058300  mov     rbp, rsp
0x180058303  sub     rsp, 30h
0x180058307  mov     rdi, rcx
0x18005830a  mov     dword ptr [rcx], 0
0x180058310  mov     [rbp+TokenHandle], 0
0x180058318  call    cs:__imp_GetCurrentProcess
0x18005831e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180058322  mov     edx, 0Ah; DesiredAccess
0x180058327  mov     rcx, rax; ProcessHandle
0x18005832a  call    cs:__imp_OpenProcessToken
0x180058330  test    eax, eax
0x180058332  jz      loc_1800583D8
0x180058338  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x18005833d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180058341  test    eax, eax
0x180058343  jz      short loc_180058351
0x180058345  mov     rdx, rdi
0x180058348  call    LUAIsUserUACAdminEx
0x18005834d  mov     ebx, eax
0x18005834f  jmp     short loc_1800583CC
0x180058351  lea     r8, [rbp+TokenInformation]
0x180058355  mov     [rbp+arg_0], 0
0x18005835c  lea     rdx, [rbp+arg_0]
0x180058360  mov     dword ptr [rbp+TokenInformation], 0
0x180058367  call    LUAIsElevatedToken
0x18005836c  mov     ebx, eax
0x18005836e  test    eax, eax
0x180058370  js      short loc_1800583CC
0x180058372  cmp     [rbp+arg_0], 0
0x180058376  mov     rcx, [rbp+TokenHandle]; void *
0x18005837a  jnz     short loc_1800583C5
0x18005837c  mov     r9d, 8; TokenInformationLength
0x180058382  mov     [rbp+TokenInformation], 0
0x18005838a  lea     rax, [rbp+arg_0]
0x18005838e  mov     [rbp+arg_0], r9d
0x180058392  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180058396  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18005839b  lea     edx, [r9+0Bh]; TokenInformationClass
0x18005839f  call    cs:__imp_GetTokenInformation
0x1800583a5  test    eax, eax
0x1800583a7  jz      short loc_1800583CC
0x1800583a9  mov     rcx, [rbp+TokenInformation]; void *
0x1800583ad  test    rcx, rcx
0x1800583b0  jz      short loc_1800583CC
0x1800583b2  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x1800583b7  mov     rcx, [rbp+TokenInformation]; hObject
0x1800583bb  mov     [rdi], eax
0x1800583bd  call    cs:__imp_CloseHandle
0x1800583c3  jmp     short loc_1800583CC
0x1800583c5  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x1800583ca  mov     [rdi], eax
0x1800583cc  mov     rcx, [rbp+TokenHandle]; hObject
0x1800583d0  call    cs:__imp_CloseHandle
0x1800583d6  jmp     short loc_1800583FB
0x1800583d8  call    cs:__imp_GetLastError
0x1800583de  test    eax, eax
0x1800583e0  jg      short loc_1800583EC
0x1800583e2  call    cs:__imp_GetLastError
0x1800583e8  mov     ebx, eax
0x1800583ea  jmp     short loc_1800583FB
0x1800583ec  call    cs:__imp_GetLastError
0x1800583f2  movzx   ebx, ax
0x1800583f5  or      ebx, 0C0070000h
0x1800583fb  mov     eax, ebx
0x1800583fd  add     rsp, 30h
0x180058401  pop     rdi
0x180058402  pop     rbx
0x180058403  pop     rbp
0x180058404  retn
```
