# GetCallerTokenAndRevertToSelf(bool,void * *,void * *)

- ea: `0x18000b73c`
- end: `0x18000b975`
- name: `?GetCallerTokenAndRevertToSelf@@YAJ_NPEAPEAX1@Z`
- size: `569`
- prototype: `__int64 __fastcall(bool, void **, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018124`

## callees

- `0x180002214`
- `0x180003180`
- `0x180007b18`
- `0x180009438`
- `0x18000b73c`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b7a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b839`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b7a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b839`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b7bd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b84f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b7bd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b84f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b859`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000b866`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000b866`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000b7db`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000b7db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b833`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b931`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b833`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b931`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b948`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000b89b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000b89b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000b909`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000b909`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000b7fd`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000b7fd`

## string_xrefs

- `0x18000b787`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x18000b810`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x18000b886`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x18000b8a9`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x18000b8c7`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x18000b917`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

## pseudocode

```c
__int64 __fastcall GetCallerTokenAndRevertToSelf(__int64 a1, void **a2, void **a3)
{
  int v3; // r14d
  int v4; // esi
  unsigned int v7; // ebx
  HANDLE CurrentThread; // rax
  const char *v9; // r9
  __int64 v10; // rdx
  HRESULT v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  DWORD LastError; // edi
  HANDLE v15; // rax
  __int64 v16; // rdx
  const char *v17; // r9
  const char *v18; // r9
  HANDLE hObject; // [rsp+20h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  v3 = 0;
  TokenHandle = 0;
  v4 = 0;
  hObject = 0;
  if ( !a2 )
  {
    v7 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      (const char *)0x80004003LL,
      (int)hObject);
    goto LABEL_35;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
LABEL_13:
    v4 = 1;
LABEL_14:
    LastError = 0;
    v15 = GetCurrentThread();
    if ( !OpenThreadToken(v15, 0xBu, 1, &hObject) )
      LastError = GetLastError();
    if ( v3 )
    {
      v11 = CoRevertToSelf();
      v7 = v11;
      if ( LastError )
      {
        v16 = 272;
LABEL_27:
        v13 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v16,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
                (const char *)LastError,
                (unsigned int)hObject);
        goto LABEL_28;
      }
      if ( v11 < 0 )
      {
        v12 = 273;
        goto LABEL_21;
      }
    }
    else
    {
      if ( v4 && !RevertToSelf() )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x115,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
          v17);
      if ( LastError )
      {
        v16 = 280;
        goto LABEL_27;
      }
    }
    *a2 = hObject;
    hObject = 0;
    if ( a3 )
    {
      *a3 = TokenHandle;
      TokenHandle = 0;
    }
    v7 = 0;
    goto LABEL_32;
  }
  if ( GetLastError() != 1008 )
  {
    v10 = 232;
LABEL_11:
    v13 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v10,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
            v9);
LABEL_28:
    v7 = v13;
    goto LABEL_32;
  }
  v11 = CoImpersonateClient();
  v7 = v11;
  if ( v11 >= 0 )
  {
    v3 = 1;
    goto LABEL_14;
  }
  if ( v11 == -2147417833 )
  {
    if ( !ImpersonateSelf(SecurityImpersonation) )
    {
      v10 = 243;
      goto LABEL_11;
    }
    goto LABEL_13;
  }
  v12 = 239;
LABEL_21:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
    (const char *)(unsigned int)v11,
    (int)hObject);
LABEL_32:
  if ( TokenHandle && !ImpersonateLoggedOnUser(TokenHandle) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0xDE,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      v18);
LABEL_35:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v7;
}

```

## disassembly

```asm
0x18000b73c  mov     [rsp-28h+arg_0], rbx
0x18000b741  mov     [rsp-28h+arg_18], rsi
0x18000b746  push    rbp
0x18000b747  push    rdi
0x18000b748  push    r12
0x18000b74a  push    r14
0x18000b74c  push    r15
0x18000b74e  mov     rbp, rsp
0x18000b751  sub     rsp, 40h
0x18000b755  mov     rax, cs:__security_cookie
0x18000b75c  xor     rax, rsp
0x18000b75f  mov     [rbp+var_10], rax
0x18000b763  xor     r14d, r14d
0x18000b766  mov     [rbp+TokenHandle], 0
0x18000b76e  xor     esi, esi
0x18000b770  mov     [rbp+hObject], 0
0x18000b778  mov     r15, r8
0x18000b77b  mov     r12, rdx
0x18000b77e  test    rdx, rdx
0x18000b781  jnz     short loc_18000B7A5
0x18000b783  mov     rcx, [rbp+28h]; this
0x18000b787  lea     r8, aCW1SSrcClientL_31; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000b78e  mov     ebx, 80004003h
0x18000b793  mov     edx, 0D7h; void *
0x18000b798  mov     r9d, ebx; char *
0x18000b79b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7a0  jmp     loc_18000B928
0x18000b7a5  call    cs:__imp_GetCurrentThread
0x18000b7ab  mov     edi, 1
0x18000b7b0  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000b7b4  mov     r8d, edi; OpenAsSelf
0x18000b7b7  mov     rcx, rax; ThreadHandle
0x18000b7ba  lea     edx, [rdi+0Bh]; DesiredAccess
0x18000b7bd  call    cs:__imp_OpenThreadToken
0x18000b7c3  test    eax, eax
0x18000b7c5  jnz     short loc_18000B826
0x18000b7c7  call    cs:__imp_GetLastError
0x18000b7cd  cmp     eax, 3F0h
0x18000b7d2  jz      short loc_18000B7DB
0x18000b7d4  mov     edx, 0E8h
0x18000b7d9  jmp     short loc_18000B80C
0x18000b7db  call    cs:__imp_CoImpersonateClient
0x18000b7e1  mov     ebx, eax
0x18000b7e3  test    eax, eax
0x18000b7e5  jns     short loc_18000B821
0x18000b7e7  cmp     eax, 80010117h
0x18000b7ec  jz      short loc_18000B7F8
0x18000b7ee  mov     edx, 0EFh
0x18000b7f3  jmp     loc_18000B882
0x18000b7f8  mov     ecx, 2; ImpersonationLevel
0x18000b7fd  call    cs:__imp_ImpersonateSelf
0x18000b803  test    eax, eax
0x18000b805  jnz     short loc_18000B826
0x18000b807  mov     edx, 0F3h; void *
0x18000b80c  mov     rcx, [rbp+28h]; this
0x18000b810  lea     r8, aCW1SSrcClientL_31; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000b817  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b81c  jmp     loc_18000B8D6
0x18000b821  mov     r14d, edi
0x18000b824  jmp     short loc_18000B828
0x18000b826  mov     esi, edi
0x18000b828  mov     rcx, [rbp+hObject]; hObject
0x18000b82c  xor     edi, edi
0x18000b82e  test    rcx, rcx
0x18000b831  jz      short loc_18000B839
0x18000b833  call    cs:__imp_CloseHandle
0x18000b839  call    cs:__imp_GetCurrentThread
0x18000b83f  mov     edx, 0Bh; DesiredAccess
0x18000b844  lea     r9, [rbp+hObject]; TokenHandle
0x18000b848  mov     rcx, rax; ThreadHandle
0x18000b84b  lea     r8d, [rdx-0Ah]; OpenAsSelf
0x18000b84f  call    cs:__imp_OpenThreadToken
0x18000b855  test    eax, eax
0x18000b857  jnz     short loc_18000B861
0x18000b859  call    cs:__imp_GetLastError
0x18000b85f  mov     edi, eax
0x18000b861  test    r14d, r14d
0x18000b864  jz      short loc_18000B897
0x18000b866  call    cs:__imp_CoRevertToSelf
0x18000b86c  mov     ebx, eax
0x18000b86e  test    edi, edi
0x18000b870  jz      short loc_18000B879
0x18000b872  mov     edx, 110h
0x18000b877  jmp     short loc_18000B8C3
0x18000b879  test    eax, eax
0x18000b87b  jns     short loc_18000B8DA
0x18000b87d  mov     edx, 111h; void *
0x18000b882  mov     rcx, [rbp+28h]; this
0x18000b886  lea     r8, aCW1SSrcClientL_31; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000b88d  mov     r9d, eax; char *
0x18000b890  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b895  jmp     short loc_18000B900
0x18000b897  test    esi, esi
0x18000b899  jz      short loc_18000B8BA
0x18000b89b  call    cs:__imp_RevertToSelf
0x18000b8a1  test    eax, eax
0x18000b8a3  jnz     short loc_18000B8BA
0x18000b8a5  mov     rcx, [rbp+28h]; this
0x18000b8a9  lea     r8, aCW1SSrcClientL_31; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000b8b0  mov     edx, 115h; void *
0x18000b8b5  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000b8ba  test    edi, edi
0x18000b8bc  jz      short loc_18000B8DA
0x18000b8be  mov     edx, 118h; void *
0x18000b8c3  mov     rcx, [rbp+28h]; this
0x18000b8c7  lea     r8, aCW1SSrcClientL_31; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000b8ce  mov     r9d, edi; char *
0x18000b8d1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000b8d6  mov     ebx, eax
0x18000b8d8  jmp     short loc_18000B900
0x18000b8da  mov     rax, [rbp+hObject]
0x18000b8de  mov     [r12], rax
0x18000b8e2  mov     [rbp+hObject], 0
0x18000b8ea  test    r15, r15
0x18000b8ed  jz      short loc_18000B8FE
0x18000b8ef  mov     rax, [rbp+TokenHandle]
0x18000b8f3  mov     [r15], rax
0x18000b8f6  mov     [rbp+TokenHandle], 0
0x18000b8fe  xor     ebx, ebx
0x18000b900  mov     rcx, [rbp+TokenHandle]; hToken
0x18000b904  test    rcx, rcx
0x18000b907  jz      short loc_18000B928
0x18000b909  call    cs:__imp_ImpersonateLoggedOnUser
0x18000b90f  test    eax, eax
0x18000b911  jnz     short loc_18000B928
0x18000b913  mov     rcx, [rbp+28h]; this
0x18000b917  lea     r8, aCW1SSrcClientL_31; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000b91e  mov     edx, 0DEh; void *
0x18000b923  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18000b928  mov     rcx, [rbp+hObject]; hObject
0x18000b92c  test    rcx, rcx
0x18000b92f  jz      short loc_18000B93F
0x18000b931  call    cs:__imp_CloseHandle
0x18000b937  mov     [rbp+hObject], 0
0x18000b93f  mov     rcx, [rbp+TokenHandle]; hObject
0x18000b943  test    rcx, rcx
0x18000b946  jz      short loc_18000B94E
0x18000b948  call    cs:__imp_CloseHandle
0x18000b94e  mov     eax, ebx
0x18000b950  mov     rcx, [rbp+var_10]
0x18000b954  xor     rcx, rsp; StackCookie
0x18000b957  call    __security_check_cookie
0x18000b95c  lea     r11, [rsp+40h+var_s0]
0x18000b961  mov     rbx, [r11+30h]
0x18000b965  mov     rsi, [r11+48h]
0x18000b969  mov     rsp, r11
0x18000b96c  pop     r15
0x18000b96e  pop     r14
0x18000b970  pop     r12
0x18000b972  pop     rdi
0x18000b973  pop     rbp
0x18000b974  retn
```
