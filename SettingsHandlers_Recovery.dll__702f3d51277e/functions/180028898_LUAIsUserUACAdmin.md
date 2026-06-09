# LUAIsUserUACAdmin

- ea: `0x180028898`
- end: `0x1800289a1`
- name: `LUAIsUserUACAdmin`
- size: `265`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025c88`

## callees

- `0x18002870c`
- `0x1800287b0`
- `0x1800287ec`
- `0x180028898`
- `0x1800289a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002897e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002897e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028988`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800288c6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800288c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800288b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800288b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028959`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002896c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028959`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002896c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002893b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002893b`

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
0x180028898  push    rbp
0x18002889a  push    rbx
0x18002889b  push    rdi
0x18002889c  mov     rbp, rsp
0x18002889f  sub     rsp, 30h
0x1800288a3  mov     rdi, rcx
0x1800288a6  mov     dword ptr [rcx], 0
0x1800288ac  mov     [rbp+TokenHandle], 0
0x1800288b4  call    cs:__imp_GetCurrentProcess
0x1800288ba  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800288be  mov     edx, 0Ah; DesiredAccess
0x1800288c3  mov     rcx, rax; ProcessHandle
0x1800288c6  call    cs:__imp_OpenProcessToken
0x1800288cc  test    eax, eax
0x1800288ce  jz      loc_180028974
0x1800288d4  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x1800288d9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800288dd  test    eax, eax
0x1800288df  jz      short loc_1800288ED
0x1800288e1  mov     rdx, rdi
0x1800288e4  call    LUAIsUserUACAdminEx
0x1800288e9  mov     ebx, eax
0x1800288eb  jmp     short loc_180028968
0x1800288ed  lea     r8, [rbp+TokenInformation]
0x1800288f1  mov     [rbp+arg_0], 0
0x1800288f8  lea     rdx, [rbp+arg_0]
0x1800288fc  mov     dword ptr [rbp+TokenInformation], 0
0x180028903  call    LUAIsElevatedToken
0x180028908  mov     ebx, eax
0x18002890a  test    eax, eax
0x18002890c  js      short loc_180028968
0x18002890e  cmp     [rbp+arg_0], 0
0x180028912  mov     rcx, [rbp+TokenHandle]; void *
0x180028916  jnz     short loc_180028961
0x180028918  mov     r9d, 8; TokenInformationLength
0x18002891e  mov     [rbp+TokenInformation], 0
0x180028926  lea     rax, [rbp+arg_0]
0x18002892a  mov     [rbp+arg_0], r9d
0x18002892e  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180028932  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180028937  lea     edx, [r9+0Bh]; TokenInformationClass
0x18002893b  call    cs:__imp_GetTokenInformation
0x180028941  test    eax, eax
0x180028943  jz      short loc_180028968
0x180028945  mov     rcx, [rbp+TokenInformation]; void *
0x180028949  test    rcx, rcx
0x18002894c  jz      short loc_180028968
0x18002894e  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180028953  mov     rcx, [rbp+TokenInformation]; hObject
0x180028957  mov     [rdi], eax
0x180028959  call    cs:__imp_CloseHandle
0x18002895f  jmp     short loc_180028968
0x180028961  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180028966  mov     [rdi], eax
0x180028968  mov     rcx, [rbp+TokenHandle]; hObject
0x18002896c  call    cs:__imp_CloseHandle
0x180028972  jmp     short loc_180028997
0x180028974  call    cs:__imp_GetLastError
0x18002897a  test    eax, eax
0x18002897c  jg      short loc_180028988
0x18002897e  call    cs:__imp_GetLastError
0x180028984  mov     ebx, eax
0x180028986  jmp     short loc_180028997
0x180028988  call    cs:__imp_GetLastError
0x18002898e  movzx   ebx, ax
0x180028991  or      ebx, 0C0070000h
0x180028997  mov     eax, ebx
0x180028999  add     rsp, 30h
0x18002899d  pop     rdi
0x18002899e  pop     rbx
0x18002899f  pop     rbp
0x1800289a0  retn
```
