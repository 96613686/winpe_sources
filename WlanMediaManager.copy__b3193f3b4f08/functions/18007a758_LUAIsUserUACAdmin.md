# LUAIsUserUACAdmin

- ea: `0x18007a758`
- end: `0x18007a861`
- name: `LUAIsUserUACAdmin`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005c610`

## callees

- `0x18007a5cc`
- `0x18007a670`
- `0x18007a6ac`
- `0x18007a758`
- `0x18007a868`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a83e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a83e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a848`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007a774`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007a774`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007a786`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007a786`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a82c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a82c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007a7fb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007a7fb`

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
0x18007a758  push    rbp
0x18007a75a  push    rbx
0x18007a75b  push    rdi
0x18007a75c  mov     rbp, rsp
0x18007a75f  sub     rsp, 30h
0x18007a763  mov     rdi, rcx
0x18007a766  mov     dword ptr [rcx], 0
0x18007a76c  mov     [rbp+TokenHandle], 0
0x18007a774  call    cs:__imp_GetCurrentProcess
0x18007a77a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18007a77e  mov     edx, 0Ah; DesiredAccess
0x18007a783  mov     rcx, rax; ProcessHandle
0x18007a786  call    cs:__imp_OpenProcessToken
0x18007a78c  test    eax, eax
0x18007a78e  jz      loc_18007A834
0x18007a794  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x18007a799  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18007a79d  test    eax, eax
0x18007a79f  jz      short loc_18007A7AD
0x18007a7a1  mov     rdx, rdi
0x18007a7a4  call    LUAIsUserUACAdminEx
0x18007a7a9  mov     ebx, eax
0x18007a7ab  jmp     short loc_18007A828
0x18007a7ad  lea     r8, [rbp+TokenInformation]
0x18007a7b1  mov     [rbp+arg_0], 0
0x18007a7b8  lea     rdx, [rbp+arg_0]
0x18007a7bc  mov     dword ptr [rbp+TokenInformation], 0
0x18007a7c3  call    LUAIsElevatedToken
0x18007a7c8  mov     ebx, eax
0x18007a7ca  test    eax, eax
0x18007a7cc  js      short loc_18007A828
0x18007a7ce  cmp     [rbp+arg_0], 0
0x18007a7d2  mov     rcx, [rbp+TokenHandle]; void *
0x18007a7d6  jnz     short loc_18007A821
0x18007a7d8  mov     r9d, 8; TokenInformationLength
0x18007a7de  mov     [rbp+TokenInformation], 0
0x18007a7e6  lea     rax, [rbp+arg_0]
0x18007a7ea  mov     [rbp+arg_0], r9d
0x18007a7ee  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18007a7f2  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18007a7f7  lea     edx, [r9+0Bh]; TokenInformationClass
0x18007a7fb  call    cs:__imp_GetTokenInformation
0x18007a801  test    eax, eax
0x18007a803  jz      short loc_18007A828
0x18007a805  mov     rcx, [rbp+TokenInformation]; void *
0x18007a809  test    rcx, rcx
0x18007a80c  jz      short loc_18007A828
0x18007a80e  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x18007a813  mov     rcx, [rbp+TokenInformation]; hObject
0x18007a817  mov     [rdi], eax
0x18007a819  call    cs:__imp_CloseHandle
0x18007a81f  jmp     short loc_18007A828
0x18007a821  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x18007a826  mov     [rdi], eax
0x18007a828  mov     rcx, [rbp+TokenHandle]; hObject
0x18007a82c  call    cs:__imp_CloseHandle
0x18007a832  jmp     short loc_18007A857
0x18007a834  call    cs:__imp_GetLastError
0x18007a83a  test    eax, eax
0x18007a83c  jg      short loc_18007A848
0x18007a83e  call    cs:__imp_GetLastError
0x18007a844  mov     ebx, eax
0x18007a846  jmp     short loc_18007A857
0x18007a848  call    cs:__imp_GetLastError
0x18007a84e  movzx   ebx, ax
0x18007a851  or      ebx, 0C0070000h
0x18007a857  mov     eax, ebx
0x18007a859  add     rsp, 30h
0x18007a85d  pop     rdi
0x18007a85e  pop     rbx
0x18007a85f  pop     rbp
0x18007a860  retn
```
