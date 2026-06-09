# Windows::Globalization::Spelling::IsRunningUnderAppContainer

- ea: `0x140003e24`
- end: `0x140003f2c`
- name: `Windows::Globalization::Spelling::IsRunningUnderAppContainer`
- size: `264`
- prototype: `char __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140006b20`

## callees

- `0x140003e24`
- `0x140003f34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140003eb2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140003eb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140003ea2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140003ea2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140003e72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140003e72`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140003e89`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140003e89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ef6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140003ee1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140003ee1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003f02`

## pseudocode

```c
char __fastcall Windows::Globalization::Spelling::IsRunningUnderAppContainer(int a1)
{
  char v2; // di
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  HANDLE CurrentProcess; // rax
  bool v6; // sf
  int TokenInformation; // [rsp+50h] [rbp+20h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+28h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  TokenInformation = a1;
  LOBYTE(TokenInformation) = 0;
  if ( (int)Windows::Globalization::Spelling::IsWindows8OrLater(&TokenInformation) >= 0 )
  {
    if ( !(_BYTE)TokenInformation )
      return 0;
    TokenInformation = 0;
    v2 = 0;
    TokenHandle = 0;
    ReturnLength = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      goto LABEL_21;
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_14;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
LABEL_21:
      if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
      {
        if ( TokenInformation )
          v2 = 1;
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
      }
      CloseHandle(TokenHandle);
    }
    else
    {
      LastError = GetLastError();
    }
LABEL_14:
    v6 = LastError < 0;
    if ( LastError > 0 )
      v6 = 1;
    if ( !v6 )
      return v2;
  }
  return 0;
}

```

## disassembly

```asm
0x140003e24  mov     [rsp-18h+arg_18], rbx
0x140003e29  mov     [rsp-18h+TokenInformation], ecx
0x140003e2d  push    rbp
0x140003e2e  push    rdi
0x140003e2f  push    r14
0x140003e31  mov     rbp, rsp
0x140003e34  sub     rsp, 30h
0x140003e38  lea     rcx, [rbp+TokenInformation]
0x140003e3c  mov     byte ptr [rbp+TokenInformation], 0
0x140003e40  call    Windows__Globalization__Spelling__IsWindows8OrLater
0x140003e45  test    eax, eax
0x140003e47  js      loc_140003F19
0x140003e4d  cmp     byte ptr [rbp+TokenInformation], 0
0x140003e51  jnz     short loc_140003E5A
0x140003e53  xor     al, al
0x140003e55  jmp     loc_140003F1E
0x140003e5a  mov     [rbp+TokenInformation], 0
0x140003e61  xor     edi, edi
0x140003e63  mov     [rbp+TokenHandle], 0
0x140003e6b  mov     [rbp+arg_8], 0
0x140003e72  call    cs:__imp_GetCurrentThread
0x140003e78  lea     r14d, [rdi+1]
0x140003e7c  mov     rcx, rax; ThreadHandle
0x140003e7f  mov     r8d, r14d; OpenAsSelf
0x140003e82  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140003e86  lea     edx, [rdi+8]; DesiredAccess
0x140003e89  call    cs:__imp_OpenThreadToken
0x140003e8f  test    eax, eax
0x140003e91  jnz     short loc_140003EC6
0x140003e93  call    cs:__imp_GetLastError
0x140003e99  mov     ebx, eax
0x140003e9b  cmp     eax, 3F0h
0x140003ea0  jnz     short loc_140003F08
0x140003ea2  call    cs:__imp_GetCurrentProcess
0x140003ea8  mov     rcx, rax; ProcessHandle
0x140003eab  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140003eaf  lea     edx, [rdi+8]; DesiredAccess
0x140003eb2  call    cs:__imp_OpenProcessToken
0x140003eb8  test    eax, eax
0x140003eba  jnz     short loc_140003EC6
0x140003ebc  call    cs:__imp_GetLastError
0x140003ec2  mov     ebx, eax
0x140003ec4  jmp     short loc_140003F08
0x140003ec6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140003eca  lea     rax, [rbp+arg_8]
0x140003ece  mov     r9d, 4; TokenInformationLength
0x140003ed4  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140003ed9  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140003edd  lea     edx, [r9+19h]; TokenInformationClass
0x140003ee1  call    cs:__imp_GetTokenInformation
0x140003ee7  test    eax, eax
0x140003ee9  jz      short loc_140003EF6
0x140003eeb  cmp     [rbp+TokenInformation], edi
0x140003eee  cmovnz  edi, r14d
0x140003ef2  xor     ebx, ebx
0x140003ef4  jmp     short loc_140003EFE
0x140003ef6  call    cs:__imp_GetLastError
0x140003efc  mov     ebx, eax
0x140003efe  mov     rcx, [rbp+TokenHandle]; hObject
0x140003f02  call    cs:__imp_CloseHandle
0x140003f08  test    ebx, ebx
0x140003f0a  jle     short loc_140003F17
0x140003f0c  movzx   ebx, bx
0x140003f0f  or      ebx, 80070000h
0x140003f15  test    ebx, ebx
0x140003f17  jns     short loc_140003F1B
0x140003f19  xor     edi, edi
0x140003f1b  mov     al, dil
0x140003f1e  mov     rbx, [rsp+30h+arg_18]
0x140003f23  add     rsp, 30h
0x140003f27  pop     r14
0x140003f29  pop     rdi
0x140003f2a  pop     rbp
0x140003f2b  retn
```
