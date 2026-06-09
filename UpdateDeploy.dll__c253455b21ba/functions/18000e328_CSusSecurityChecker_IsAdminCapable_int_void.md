# CSusSecurityChecker::IsAdminCapable(int *,void *)

- ea: `0x18000e328`
- end: `0x18000e48e`
- name: `?IsAdminCapable@CSusSecurityChecker@@QEAAJPEAHPEAX@Z`
- size: `358`
- prototype: `int(CSusSecurityChecker *__hidden this, int *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800465f0`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000e280`
- `0x18000e328`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e3ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e3ae`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e40a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e40a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e3fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e3fb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e3c6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e3c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e472`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e472`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e439`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e439`

## string_xrefs

- `0x18000e366`: `C:\__w\1\s\src\Client\lib\util\SecurityChecker.cpp`
- `0x18000e44c`: `C:\__w\1\s\src\Client\lib\util\SecurityChecker.cpp`

## pseudocode

```c
__int64 __fastcall CSusSecurityChecker::IsAdminCapable(CSusSecurityChecker *this, int *a2, void *a3)
{
  HANDLE v3; // rbx
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v7; // r9
  __int64 v8; // rdx
  HANDLE CurrentProcess; // rax
  int ReturnLength; // [rsp+20h] [rbp-30h]
  HANDLE hObject; // [rsp+30h] [rbp-20h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-18h] BYREF
  DWORD v14; // [rsp+3Ch] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  hObject = 0;
  v3 = a3;
  TokenInformation = 0;
  v14 = 0;
  if ( !a2 )
  {
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityChecker.cpp",
      (const char *)0x80004003LL,
      ReturnLength);
    goto LABEL_19;
  }
  if ( CSusSecurityChecker::IsAdmin(this, a2, a3) < 0 || !*a2 )
  {
    if ( !v3 )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 8u, 1, &hObject) )
      {
        if ( GetLastError() != 1008 )
        {
          v8 = 182;
LABEL_16:
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)v8,
                        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SecurityChecker.cpp",
                        v7);
          goto LABEL_19;
        }
        if ( hObject )
        {
          CloseHandle(hObject);
          hObject = 0;
        }
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 8u, &hObject) )
        {
          v8 = 185;
          goto LABEL_16;
        }
      }
      v3 = hObject;
    }
    if ( !GetTokenInformation(v3, TokenElevationType, &TokenInformation, 4u, &v14) )
    {
      v8 = 192;
      goto LABEL_16;
    }
    *a2 = TokenInformation == 3;
  }
  LastError = 0;
LABEL_19:
  if ( hObject )
    CloseHandle(hObject);
  return LastError;
}

```

## disassembly

```asm
0x18000e328  push    rbp
0x18000e32a  push    rbx
0x18000e32b  push    rdi
0x18000e32c  mov     rbp, rsp
0x18000e32f  sub     rsp, 50h
0x18000e333  mov     rax, cs:__security_cookie
0x18000e33a  xor     rax, rsp
0x18000e33d  mov     [rbp+var_10], rax
0x18000e341  mov     [rbp+hObject], 0
0x18000e349  mov     rbx, r8
0x18000e34c  mov     [rbp+TokenInformation], 0
0x18000e353  mov     rdi, rdx
0x18000e356  mov     [rbp+var_14], 0
0x18000e35d  test    rdx, rdx
0x18000e360  jnz     short loc_18000E384
0x18000e362  mov     rcx, [rbp+18h]; this
0x18000e366  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e36d  mov     ebx, 80004003h
0x18000e372  mov     edx, 0AFh; void *
0x18000e377  mov     r9d, ebx; char *
0x18000e37a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e37f  jmp     loc_18000E469
0x18000e384  call    ?IsAdmin@CSusSecurityChecker@@QEAAJPEAHPEAX@Z; CSusSecurityChecker::IsAdmin(int *,void *)
0x18000e389  test    eax, eax
0x18000e38b  js      short loc_18000E396
0x18000e38d  cmp     dword ptr [rdi], 0
0x18000e390  jnz     loc_18000E467
0x18000e396  test    rbx, rbx
0x18000e399  jnz     loc_18000E41F
0x18000e39f  mov     rcx, [rbp+hObject]; hObject
0x18000e3a3  test    rcx, rcx
0x18000e3a6  jz      short loc_18000E3AE
0x18000e3a8  call    cs:__imp_CloseHandle
0x18000e3ae  call    cs:__imp_GetCurrentThread
0x18000e3b4  mov     ebx, 8
0x18000e3b9  lea     r9, [rbp+hObject]; TokenHandle
0x18000e3bd  mov     edx, ebx; DesiredAccess
0x18000e3bf  mov     rcx, rax; ThreadHandle
0x18000e3c2  lea     r8d, [rbx-7]; OpenAsSelf
0x18000e3c6  call    cs:__imp_OpenThreadToken
0x18000e3cc  test    eax, eax
0x18000e3ce  jnz     short loc_18000E41B
0x18000e3d0  call    cs:__imp_GetLastError
0x18000e3d6  cmp     eax, 3F0h
0x18000e3db  jz      short loc_18000E3E4
0x18000e3dd  mov     edx, 0B6h
0x18000e3e2  jmp     short loc_18000E448
0x18000e3e4  mov     rcx, [rbp+hObject]; hObject
0x18000e3e8  test    rcx, rcx
0x18000e3eb  jz      short loc_18000E3FB
0x18000e3ed  call    cs:__imp_CloseHandle
0x18000e3f3  mov     [rbp+hObject], 0
0x18000e3fb  call    cs:__imp_GetCurrentProcess
0x18000e401  lea     r8, [rbp+hObject]; TokenHandle
0x18000e405  mov     edx, ebx; DesiredAccess
0x18000e407  mov     rcx, rax; ProcessHandle
0x18000e40a  call    cs:__imp_OpenProcessToken
0x18000e410  test    eax, eax
0x18000e412  jnz     short loc_18000E41B
0x18000e414  mov     edx, 0B9h
0x18000e419  jmp     short loc_18000E448
0x18000e41b  mov     rbx, [rbp+hObject]
0x18000e41f  mov     r9d, 4; TokenInformationLength
0x18000e425  lea     rax, [rbp+var_14]
0x18000e429  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18000e42d  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x18000e432  mov     rcx, rbx; TokenHandle
0x18000e435  lea     edx, [r9+0Eh]; TokenInformationClass
0x18000e439  call    cs:__imp_GetTokenInformation
0x18000e43f  test    eax, eax
0x18000e441  jnz     short loc_18000E45C
0x18000e443  mov     edx, 0C0h; void *
0x18000e448  mov     rcx, [rbp+18h]; this
0x18000e44c  lea     r8, aCW1SSrcClientL_28; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e453  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e458  mov     ebx, eax
0x18000e45a  jmp     short loc_18000E469
0x18000e45c  xor     eax, eax
0x18000e45e  cmp     [rbp+TokenInformation], 3
0x18000e462  setz    al
0x18000e465  mov     [rdi], eax
0x18000e467  xor     ebx, ebx
0x18000e469  mov     rcx, [rbp+hObject]; hObject
0x18000e46d  test    rcx, rcx
0x18000e470  jz      short loc_18000E478
0x18000e472  call    cs:__imp_CloseHandle
0x18000e478  mov     eax, ebx
0x18000e47a  mov     rcx, [rbp+var_10]
0x18000e47e  xor     rcx, rsp; StackCookie
0x18000e481  call    __security_check_cookie
0x18000e486  add     rsp, 50h
0x18000e48a  pop     rdi
0x18000e48b  pop     rbx
0x18000e48c  pop     rbp
0x18000e48d  retn
```
