# Windows::Globalization::Spelling::IsRunningUnderAppContainer

- ea: `0x18003627c`
- end: `0x180036387`
- name: `Windows::Globalization::Spelling::IsRunningUnderAppContainer`
- size: `267`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f858`
- `0x180086380`

## callees

- `0x18003627c`
- `0x180036390`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800362e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800362e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800362fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800362fc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003630c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003630c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800362d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800362d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036350`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003635c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003635c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003633b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003633b`

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
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF

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
  return 1;
}

```

## disassembly

```asm
0x18003627c  mov     [rsp-18h+arg_18], rbx
0x180036281  mov     [rsp-18h+TokenInformation], ecx
0x180036285  push    rbp
0x180036286  push    rdi
0x180036287  push    r14
0x180036289  mov     rbp, rsp
0x18003628c  sub     rsp, 30h
0x180036290  lea     rcx, [rbp+TokenInformation]
0x180036294  mov     byte ptr [rbp+TokenInformation], 0
0x180036298  call    Windows__Globalization__Spelling__IsWindows8OrLater
0x18003629d  mov     r14d, 1
0x1800362a3  test    eax, eax
0x1800362a5  js      loc_180036373
0x1800362ab  cmp     byte ptr [rbp+TokenInformation], 0
0x1800362af  jnz     short loc_1800362B8
0x1800362b1  xor     al, al
0x1800362b3  jmp     loc_180036379
0x1800362b8  mov     [rbp+TokenInformation], 0
0x1800362bf  xor     edi, edi
0x1800362c1  mov     [rbp+TokenHandle], 0
0x1800362c9  mov     [rbp+arg_8], 0
0x1800362d0  call    cs:__imp_GetCurrentThread
0x1800362d6  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800362da  mov     r8d, r14d; OpenAsSelf
0x1800362dd  mov     rcx, rax; ThreadHandle
0x1800362e0  lea     edx, [rdi+8]; DesiredAccess
0x1800362e3  call    cs:__imp_OpenThreadToken
0x1800362e9  test    eax, eax
0x1800362eb  jnz     short loc_180036320
0x1800362ed  call    cs:__imp_GetLastError
0x1800362f3  mov     ebx, eax
0x1800362f5  cmp     eax, 3F0h
0x1800362fa  jnz     short loc_180036362
0x1800362fc  call    cs:__imp_GetCurrentProcess
0x180036302  mov     rcx, rax; ProcessHandle
0x180036305  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180036309  lea     edx, [rdi+8]; DesiredAccess
0x18003630c  call    cs:__imp_OpenProcessToken
0x180036312  test    eax, eax
0x180036314  jnz     short loc_180036320
0x180036316  call    cs:__imp_GetLastError
0x18003631c  mov     ebx, eax
0x18003631e  jmp     short loc_180036362
0x180036320  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180036324  lea     rax, [rbp+arg_8]
0x180036328  mov     r9d, 4; TokenInformationLength
0x18003632e  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180036333  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180036337  lea     edx, [r9+19h]; TokenInformationClass
0x18003633b  call    cs:__imp_GetTokenInformation
0x180036341  test    eax, eax
0x180036343  jz      short loc_180036350
0x180036345  cmp     [rbp+TokenInformation], edi
0x180036348  cmovnz  edi, r14d
0x18003634c  xor     ebx, ebx
0x18003634e  jmp     short loc_180036358
0x180036350  call    cs:__imp_GetLastError
0x180036356  mov     ebx, eax
0x180036358  mov     rcx, [rbp+TokenHandle]; hObject
0x18003635c  call    cs:__imp_CloseHandle
0x180036362  test    ebx, ebx
0x180036364  jle     short loc_180036371
0x180036366  movzx   ebx, bx
0x180036369  or      ebx, 80070000h
0x18003636f  test    ebx, ebx
0x180036371  jns     short loc_180036376
0x180036373  mov     edi, r14d
0x180036376  mov     al, dil
0x180036379  mov     rbx, [rsp+30h+arg_18]
0x18003637e  add     rsp, 30h
0x180036382  pop     r14
0x180036384  pop     rdi
0x180036385  pop     rbp
0x180036386  retn
```
