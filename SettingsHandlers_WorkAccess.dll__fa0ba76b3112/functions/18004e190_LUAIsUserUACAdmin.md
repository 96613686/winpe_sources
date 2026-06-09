# LUAIsUserUACAdmin

- ea: `0x18004e190`
- end: `0x18004e2cd`
- name: `LUAIsUserUACAdmin`
- size: `317`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026be8`
- `0x180029400`
- `0x180040fa0`

## callees

- `0x18004dfd8`
- `0x18004e094`
- `0x18004e0d4`
- `0x18004e190`
- `0x18004e2d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e29d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e2ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e29d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e2ad`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004e1c4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004e1c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004e1ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004e1ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e266`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e27f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e266`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e27f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e242`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004e242`

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
0x18004e190  push    rbp
0x18004e192  push    rbx
0x18004e193  push    rdi
0x18004e194  mov     rbp, rsp
0x18004e197  sub     rsp, 30h
0x18004e19b  mov     rdi, rcx
0x18004e19e  mov     dword ptr [rcx], 0
0x18004e1a4  mov     [rbp+TokenHandle], 0
0x18004e1ac  call    cs:__imp_GetCurrentProcess
0x18004e1b3  nop     dword ptr [rax+rax+00h]
0x18004e1b8  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18004e1bc  mov     edx, 0Ah; DesiredAccess
0x18004e1c1  mov     rcx, rax; ProcessHandle
0x18004e1c4  call    cs:__imp_OpenProcessToken
0x18004e1cb  nop     dword ptr [rax+rax+00h]
0x18004e1d0  test    eax, eax
0x18004e1d2  jz      loc_18004E28D
0x18004e1d8  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x18004e1dd  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004e1e1  test    eax, eax
0x18004e1e3  jz      short loc_18004E1F4
0x18004e1e5  mov     rdx, rdi
0x18004e1e8  call    LUAIsUserUACAdminEx
0x18004e1ed  mov     ebx, eax
0x18004e1ef  jmp     loc_18004E27B
0x18004e1f4  lea     r8, [rbp+TokenInformation]
0x18004e1f8  mov     [rbp+arg_0], 0
0x18004e1ff  lea     rdx, [rbp+arg_0]
0x18004e203  mov     dword ptr [rbp+TokenInformation], 0
0x18004e20a  call    LUAIsElevatedToken
0x18004e20f  mov     ebx, eax
0x18004e211  test    eax, eax
0x18004e213  js      short loc_18004E27B
0x18004e215  cmp     [rbp+arg_0], 0
0x18004e219  mov     rcx, [rbp+TokenHandle]; void *
0x18004e21d  jnz     short loc_18004E274
0x18004e21f  mov     r9d, 8; TokenInformationLength
0x18004e225  mov     [rbp+TokenInformation], 0
0x18004e22d  lea     rax, [rbp+arg_0]
0x18004e231  mov     [rbp+arg_0], r9d
0x18004e235  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18004e239  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18004e23e  lea     edx, [r9+0Bh]; TokenInformationClass
0x18004e242  call    cs:__imp_GetTokenInformation
0x18004e249  nop     dword ptr [rax+rax+00h]
0x18004e24e  test    eax, eax
0x18004e250  jz      short loc_18004E27B
0x18004e252  mov     rcx, [rbp+TokenInformation]; void *
0x18004e256  test    rcx, rcx
0x18004e259  jz      short loc_18004E27B
0x18004e25b  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x18004e260  mov     rcx, [rbp+TokenInformation]; hObject
0x18004e264  mov     [rdi], eax
0x18004e266  call    cs:__imp_CloseHandle
0x18004e26d  nop     dword ptr [rax+rax+00h]
0x18004e272  jmp     short loc_18004E27B
0x18004e274  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x18004e279  mov     [rdi], eax
0x18004e27b  mov     rcx, [rbp+TokenHandle]; hObject
0x18004e27f  call    cs:__imp_CloseHandle
0x18004e286  nop     dword ptr [rax+rax+00h]
0x18004e28b  jmp     short loc_18004E2C2
0x18004e28d  call    cs:__imp_GetLastError
0x18004e294  nop     dword ptr [rax+rax+00h]
0x18004e299  test    eax, eax
0x18004e29b  jg      short loc_18004E2AD
0x18004e29d  call    cs:__imp_GetLastError
0x18004e2a4  nop     dword ptr [rax+rax+00h]
0x18004e2a9  mov     ebx, eax
0x18004e2ab  jmp     short loc_18004E2C2
0x18004e2ad  call    cs:__imp_GetLastError
0x18004e2b4  nop     dword ptr [rax+rax+00h]
0x18004e2b9  movzx   ebx, ax
0x18004e2bc  or      ebx, 0C0070000h
0x18004e2c2  mov     eax, ebx
0x18004e2c4  add     rsp, 30h
0x18004e2c8  pop     rdi
0x18004e2c9  pop     rbx
0x18004e2ca  pop     rbp
0x18004e2cb  retn
```
