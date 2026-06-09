# LUAIsUserUACAdmin

- ea: `0x180027434`
- end: `0x18002753d`
- name: `LUAIsUserUACAdmin`
- size: `265`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002354c`
- `0x180025d20`

## callees

- `0x180027260`
- `0x180027344`
- `0x180027388`
- `0x180027434`
- `0x180027544`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002751a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002751a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027524`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180027462`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180027462`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180027450`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180027450`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800274f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027508`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800274f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027508`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800274d7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800274d7`

## pseudocode

```c
__int64 __fastcall LUAIsUserUACAdmin(_DWORD *a1)
{
  HANDLE CurrentProcess; // rax
  int v3; // ebx
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
      v3 = LUAIsElevatedToken(TokenHandle);
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
0x180027434  push    rbp
0x180027436  push    rbx
0x180027437  push    rdi
0x180027438  mov     rbp, rsp
0x18002743b  sub     rsp, 30h
0x18002743f  mov     rdi, rcx
0x180027442  mov     dword ptr [rcx], 0
0x180027448  mov     [rbp+TokenHandle], 0
0x180027450  call    cs:__imp_GetCurrentProcess
0x180027456  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002745a  mov     edx, 0Ah; DesiredAccess
0x18002745f  mov     rcx, rax; ProcessHandle
0x180027462  call    cs:__imp_OpenProcessToken
0x180027468  test    eax, eax
0x18002746a  jz      loc_180027510
0x180027470  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x180027475  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180027479  test    eax, eax
0x18002747b  jz      short loc_180027489
0x18002747d  mov     rdx, rdi
0x180027480  call    LUAIsUserUACAdminEx
0x180027485  mov     ebx, eax
0x180027487  jmp     short loc_180027504
0x180027489  lea     r8, [rbp+TokenInformation]
0x18002748d  mov     [rbp+arg_0], 0
0x180027494  lea     rdx, [rbp+arg_0]
0x180027498  mov     dword ptr [rbp+TokenInformation], 0
0x18002749f  call    LUAIsElevatedToken
0x1800274a4  mov     ebx, eax
0x1800274a6  test    eax, eax
0x1800274a8  js      short loc_180027504
0x1800274aa  cmp     [rbp+arg_0], 0
0x1800274ae  mov     rcx, [rbp+TokenHandle]; void *
0x1800274b2  jnz     short loc_1800274FD
0x1800274b4  mov     r9d, 8; TokenInformationLength
0x1800274ba  mov     [rbp+TokenInformation], 0
0x1800274c2  lea     rax, [rbp+arg_0]
0x1800274c6  mov     [rbp+arg_0], r9d
0x1800274ca  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800274ce  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800274d3  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800274d7  call    cs:__imp_GetTokenInformation
0x1800274dd  test    eax, eax
0x1800274df  jz      short loc_180027504
0x1800274e1  mov     rcx, [rbp+TokenInformation]; void *
0x1800274e5  test    rcx, rcx
0x1800274e8  jz      short loc_180027504
0x1800274ea  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x1800274ef  mov     rcx, [rbp+TokenInformation]; hObject
0x1800274f3  mov     [rdi], eax
0x1800274f5  call    cs:__imp_CloseHandle
0x1800274fb  jmp     short loc_180027504
0x1800274fd  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180027502  mov     [rdi], eax
0x180027504  mov     rcx, [rbp+TokenHandle]; hObject
0x180027508  call    cs:__imp_CloseHandle
0x18002750e  jmp     short loc_180027533
0x180027510  call    cs:__imp_GetLastError
0x180027516  test    eax, eax
0x180027518  jg      short loc_180027524
0x18002751a  call    cs:__imp_GetLastError
0x180027520  mov     ebx, eax
0x180027522  jmp     short loc_180027533
0x180027524  call    cs:__imp_GetLastError
0x18002752a  movzx   ebx, ax
0x18002752d  or      ebx, 0C0070000h
0x180027533  mov     eax, ebx
0x180027535  add     rsp, 30h
0x180027539  pop     rdi
0x18002753a  pop     rbx
0x18002753b  pop     rbp
0x18002753c  retn
```
