# SHQueryToken<_TOKEN_MANDATORY_LABEL>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_MANDATORY_LABEL * *)

- ea: `0x18002f244`
- end: `0x18002f3b2`
- name: `??$SHQueryToken@U_TOKEN_MANDATORY_LABEL@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003aab0`

## callees

- `0x18002f244`
- `0x180030ea4`
- `0x18003aa84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f36f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f36f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002f285`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002f285`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f270`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f270`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002f2b2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002f2b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f2a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002f2a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f39f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f39f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f32d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f38b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f32d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f38b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f313`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f365`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f313`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f365`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_MANDATORY_LABEL>(HANDLE TokenHandle, __int64 a2, DWORD a3, _QWORD *a4)
{
  HANDLE v5; // rsi
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE CurrentProcess; // rax
  signed int v9; // ebx
  void *v10; // rdi
  signed int LastError; // eax
  void *v12; // rcx
  int v13; // eax
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+40h] BYREF
  void *TokenHandlea; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a3;
  *a4 = 0;
  TokenHandlea = 0;
  v5 = TokenHandle;
  if ( !TokenHandle )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandlea) )
    {
      result = ResultFromKnownLastError();
      if ( (int)result < 0 )
      {
        if ( (_DWORD)result != -2147023888 )
          return result;
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandlea) )
        {
          result = ResultFromKnownLastError();
          if ( (int)result < 0 )
            return result;
        }
      }
    }
    v5 = TokenHandlea;
  }
  TokenInformation = 0;
  TokenInformationLength = 2048;
  v9 = CTLocalAllocPolicy::Alloc(TokenHandle, 0x40u, 0x800u, &TokenInformation);
  if ( v9 >= 0 )
  {
    v10 = TokenInformation;
    if ( GetTokenInformation(v5, TokenIntegrityLevel, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_18;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v10);
      v13 = CTLocalAllocPolicy::Alloc(v12, 0x40u, TokenInformationLength, &TokenInformation);
      v10 = TokenInformation;
      v9 = v13;
      if ( v13 < 0 )
      {
LABEL_17:
        LocalFree(v10);
        goto LABEL_19;
      }
      if ( GetTokenInformation(
             v5,
             TokenIntegrityLevel,
             TokenInformation,
             TokenInformationLength,
             &TokenInformationLength) )
      {
LABEL_18:
        *a4 = v10;
        goto LABEL_19;
      }
      LastError = GetLastError();
      v9 = LastError;
    }
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_17;
    goto LABEL_18;
  }
LABEL_19:
  if ( TokenHandlea )
    CloseHandle(TokenHandlea);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002f244  mov     [rsp-28h+TokenInformationLength], r8d
0x18002f249  push    rbp
0x18002f24a  push    rbx
0x18002f24b  push    rsi
0x18002f24c  push    rdi
0x18002f24d  push    r14
0x18002f24f  mov     rbp, rsp
0x18002f252  sub     rsp, 30h
0x18002f256  mov     qword ptr [r9], 0
0x18002f25d  mov     r14, r9
0x18002f260  mov     [rbp+TokenHandle], 0
0x18002f268  mov     rsi, rcx
0x18002f26b  test    rcx, rcx
0x18002f26e  jnz     short loc_18002F2CD
0x18002f270  call    cs:__imp_GetCurrentThread
0x18002f276  lea     ebx, [rsi+8]
0x18002f279  xor     r8d, r8d; OpenAsSelf
0x18002f27c  mov     rcx, rax; ThreadHandle
0x18002f27f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002f283  mov     edx, ebx; DesiredAccess
0x18002f285  call    cs:__imp_OpenThreadToken
0x18002f28b  test    eax, eax
0x18002f28d  jnz     short loc_18002F2C9
0x18002f28f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002f294  test    eax, eax
0x18002f296  jns     short loc_18002F2C9
0x18002f298  cmp     eax, 800703F0h
0x18002f29d  jnz     loc_18002F3A7
0x18002f2a3  call    cs:__imp_GetCurrentProcess
0x18002f2a9  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002f2ad  mov     edx, ebx; DesiredAccess
0x18002f2af  mov     rcx, rax; ProcessHandle
0x18002f2b2  call    cs:__imp_OpenProcessToken
0x18002f2b8  test    eax, eax
0x18002f2ba  jnz     short loc_18002F2C9
0x18002f2bc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002f2c1  test    eax, eax
0x18002f2c3  js      loc_18002F3A7
0x18002f2c9  mov     rsi, [rbp+TokenHandle]
0x18002f2cd  mov     r8d, 800h; unsigned __int64
0x18002f2d3  mov     [rbp+TokenInformation], 0
0x18002f2db  lea     r9, [rbp+TokenInformation]; void **
0x18002f2df  mov     [rbp+TokenInformationLength], r8d
0x18002f2e3  mov     edx, 40h ; '@'; unsigned int
0x18002f2e8  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002f2ed  mov     ebx, eax
0x18002f2ef  test    eax, eax
0x18002f2f1  js      loc_18002F396
0x18002f2f7  mov     rdi, [rbp+TokenInformation]
0x18002f2fb  lea     rax, [rbp+TokenInformationLength]
0x18002f2ff  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002f303  mov     r8, rdi; TokenInformation
0x18002f306  mov     edx, 19h; TokenInformationClass
0x18002f30b  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002f310  mov     rcx, rsi; TokenHandle
0x18002f313  call    cs:__imp_GetTokenInformation
0x18002f319  test    eax, eax
0x18002f31b  jnz     short loc_18002F393
0x18002f31d  call    cs:__imp_GetLastError
0x18002f323  mov     ebx, eax
0x18002f325  cmp     eax, 7Ah ; 'z'
0x18002f328  jnz     short loc_18002F377
0x18002f32a  mov     rcx, rdi; hMem
0x18002f32d  call    cs:__imp_LocalFree
0x18002f333  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x18002f337  lea     r9, [rbp+TokenInformation]; void **
0x18002f33b  lea     edx, [rbx-3Ah]; unsigned int
0x18002f33e  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002f343  mov     rdi, [rbp+TokenInformation]
0x18002f347  mov     ebx, eax
0x18002f349  test    eax, eax
0x18002f34b  js      short loc_18002F388
0x18002f34d  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002f351  lea     rax, [rbp+TokenInformationLength]
0x18002f355  mov     r8, rdi; TokenInformation
0x18002f358  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002f35d  mov     edx, 19h; TokenInformationClass
0x18002f362  mov     rcx, rsi; TokenHandle
0x18002f365  call    cs:__imp_GetTokenInformation
0x18002f36b  test    eax, eax
0x18002f36d  jnz     short loc_18002F393
0x18002f36f  call    cs:__imp_GetLastError
0x18002f375  mov     ebx, eax
0x18002f377  test    eax, eax
0x18002f379  jle     short loc_18002F384
0x18002f37b  movzx   ebx, ax
0x18002f37e  or      ebx, 80070000h
0x18002f384  test    ebx, ebx
0x18002f386  jns     short loc_18002F393
0x18002f388  mov     rcx, rdi; hMem
0x18002f38b  call    cs:__imp_LocalFree
0x18002f391  jmp     short loc_18002F396
0x18002f393  mov     [r14], rdi
0x18002f396  mov     rcx, [rbp+TokenHandle]; hObject
0x18002f39a  test    rcx, rcx
0x18002f39d  jz      short loc_18002F3A5
0x18002f39f  call    cs:__imp_CloseHandle
0x18002f3a5  mov     eax, ebx
0x18002f3a7  add     rsp, 30h
0x18002f3ab  pop     r14
0x18002f3ad  pop     rdi
0x18002f3ae  pop     rsi
0x18002f3af  pop     rbx
0x18002f3b0  pop     rbp
0x18002f3b1  retn
```
