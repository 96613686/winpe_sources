# CINetEdge::CheckIsAADTokenBrokerPlugin(void)

- ea: `0x180004270`
- end: `0x1800044aa`
- name: `?CheckIsAADTokenBrokerPlugin@CINetEdge@@AEAA_NXZ`
- size: `570`
- prototype: `bool __fastcall(CINetEdge *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800040ec`

## callees

- `0x180004270`
- `0x1800044b0`
- `0x18009d920`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800043c0`
- `msvcrt!_wcsicmp` at `0x1800043d5`
- `msvcrt!_wcsicmp` at `0x1800043c0`
- `msvcrt!_wcsicmp` at `0x1800043d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004287`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000429b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000432c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004347`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004287`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000429b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000432c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004347`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004454`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000448f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004454`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000448f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000440c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000442a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000440c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000442a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004478`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000449f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004478`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000449f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800043ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800043ab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800042e1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800042e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800043e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800043e8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000439c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000439c`

## pseudocode

```c
char __fastcall CINetEdge::CheckIsAADTokenBrokerPlugin(CINetEdge *this)
{
  char v1; // si
  HANDLE CurrentProcess; // rax
  bool v3; // di
  void *v4; // rbx
  signed int Error; // ebx
  char *v6; // rcx
  HANDLE v7; // rax
  HANDLE v8; // rdi
  void *v9; // rbx
  void **v10; // r8
  signed int v11; // ebx
  signed int PackageSidFromProcessToken; // eax
  char *v13; // rcx
  int v14; // ebx
  signed int LastError; // eax
  signed int v17; // eax
  __int64 TokenInformation; // [rsp+50h] [rbp+20h] BYREF
  LPWSTR ReturnLength; // [rsp+58h] [rbp+28h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  TokenInformation = (__int64)this;
  v1 = 0;
  CurrentProcess = GetCurrentProcess();
  v3 = 0;
  TokenHandle = 0;
  v4 = CurrentProcess;
  if ( CurrentProcess == GetCurrentProcess() )
  {
    TokenHandle = (HANDLE)-4LL;
LABEL_3:
    Error = 0;
    goto LABEL_4;
  }
  if ( OpenProcessToken(v4, 8u, &TokenHandle) )
    goto LABEL_3;
  LastError = GetLastError();
  Error = LastError;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
LABEL_4:
  if ( Error < 0 )
    goto LABEL_8;
  LODWORD(ReturnLength) = 0;
  LODWORD(TokenInformation) = 0;
  if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, (PDWORD)&ReturnLength) )
  {
    Error = 0;
LABEL_7:
    v3 = (_DWORD)TokenInformation != 0;
    goto LABEL_8;
  }
  Error = ResultFromKnownLastError();
  if ( Error >= 0 )
    goto LABEL_7;
LABEL_8:
  v6 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  if ( Error >= 0 && v3 )
  {
    ReturnLength = 0;
    v7 = GetCurrentProcess();
    v8 = 0;
    ReturnLength = 0;
    v9 = v7;
    TokenHandle = 0;
    TokenInformation = 0;
    if ( v7 == GetCurrentProcess() )
    {
      TokenInformation = -4;
    }
    else if ( !OpenProcessToken(v9, 8u, (PHANDLE)&TokenInformation) )
    {
      v17 = GetLastError();
      v11 = v17;
      if ( v17 > 0 )
        v11 = (unsigned __int16)v17 | 0x80070000;
      goto LABEL_15;
    }
    v11 = 0;
LABEL_15:
    if ( v11 >= 0 )
    {
      PackageSidFromProcessToken = CallerIdentity::GetPackageSidFromProcessToken(
                                     (HANDLE)TokenInformation,
                                     &TokenHandle,
                                     v10);
      v8 = TokenHandle;
      v11 = PackageSidFromProcessToken;
    }
    v13 = (char *)TokenInformation;
    TokenInformation = 0;
    if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v13);
    if ( v11 >= 0 )
    {
      v14 = ConvertSidToStringSidW(v8, &ReturnLength) ? 0 : ResultFromKnownLastError();
      LocalFree(v8);
      if ( v14 >= 0
        && (!_wcsicmp(
               L"S-1-15-2-1910091885-1573563583-1104941280-2418270861-3411158377-2822700936-2990310272",
               ReturnLength)
         || !_wcsicmp(
               L"S-1-15-2-2867405820-2738857118-4021800865-410975764-3768480088-1705603374-2243483066",
               ReturnLength)) )
      {
        v1 = 1;
      }
    }
    if ( ReturnLength )
      CoTaskMemFree(ReturnLength);
  }
  return v1;
}

```

## disassembly

```asm
0x180004270  mov     [rsp-18h+arg_18], rbx
0x180004275  mov     [rsp-18h+TokenInformation], rcx
0x18000427a  push    rbp
0x18000427b  push    rsi
0x18000427c  push    rdi
0x18000427d  mov     rbp, rsp
0x180004280  sub     rsp, 30h
0x180004284  xor     sil, sil
0x180004287  call    cs:__imp_GetCurrentProcess
0x18000428d  xor     dil, dil
0x180004290  mov     [rbp+TokenHandle], 0
0x180004298  mov     rbx, rax
0x18000429b  call    cs:__imp_GetCurrentProcess
0x1800042a1  cmp     rbx, rax
0x1800042a4  jnz     loc_180004448
0x1800042aa  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFCh
0x1800042b2  xor     ebx, ebx
0x1800042b4  test    ebx, ebx
0x1800042b6  js      short loc_1800042F9
0x1800042b8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800042bc  lea     rax, [rbp+arg_8]
0x1800042c0  mov     r9d, 4; TokenInformationLength
0x1800042c6  mov     dword ptr [rbp+arg_8], 0
0x1800042cd  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800042d1  mov     dword ptr [rbp+TokenInformation], 0
0x1800042d8  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800042dd  lea     edx, [r9+19h]; TokenInformationClass
0x1800042e1  call    cs:__imp_GetTokenInformation
0x1800042e7  test    eax, eax
0x1800042e9  jz      loc_180004464
0x1800042ef  xor     ebx, ebx
0x1800042f1  cmp     dword ptr [rbp+TokenInformation], 0
0x1800042f5  setnz   dil
0x1800042f9  mov     rcx, [rbp+TokenHandle]; hObject
0x1800042fd  mov     [rbp+TokenHandle], 0
0x180004305  lea     rax, [rcx-1]
0x180004309  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000430d  jbe     loc_180004478
0x180004313  test    ebx, ebx
0x180004315  js      loc_1800043EE
0x18000431b  test    dil, dil
0x18000431e  jz      loc_1800043EE
0x180004324  mov     [rbp+arg_8], 0
0x18000432c  call    cs:__imp_GetCurrentProcess
0x180004332  xor     edi, edi
0x180004334  mov     [rbp+arg_8], 0
0x18000433c  mov     rbx, rax
0x18000433f  mov     [rbp+TokenHandle], rdi
0x180004343  mov     [rbp+TokenInformation], rdi
0x180004347  call    cs:__imp_GetCurrentProcess
0x18000434d  cmp     rbx, rax
0x180004350  jnz     loc_180004483
0x180004356  mov     [rbp+TokenInformation], 0FFFFFFFFFFFFFFFCh
0x18000435e  xor     ebx, ebx
0x180004360  test    ebx, ebx
0x180004362  js      short loc_180004377
0x180004364  mov     rcx, [rbp+TokenInformation]; TokenHandle
0x180004368  lea     rdx, [rbp+TokenHandle]; void *
0x18000436c  call    ?GetPackageSidFromProcessToken@CallerIdentity@@YAJPEAXPEAPEAX@Z; CallerIdentity::GetPackageSidFromProcessToken(void *,void * *)
0x180004371  mov     rdi, [rbp+TokenHandle]
0x180004375  mov     ebx, eax
0x180004377  mov     rcx, [rbp+TokenInformation]; hObject
0x18000437b  mov     [rbp+TokenInformation], 0
0x180004383  lea     rax, [rcx-1]
0x180004387  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000438b  jbe     loc_18000449F
0x180004391  test    ebx, ebx
0x180004393  js      short loc_1800043DF
0x180004395  lea     rdx, [rbp+arg_8]; StringSid
0x180004399  mov     rcx, rdi; Sid
0x18000439c  call    cs:__imp_ConvertSidToStringSidW
0x1800043a2  test    eax, eax
0x1800043a4  jz      short loc_180004403
0x1800043a6  xor     ebx, ebx
0x1800043a8  mov     rcx, rdi; hMem
0x1800043ab  call    cs:__imp_LocalFree
0x1800043b1  test    ebx, ebx
0x1800043b3  js      short loc_1800043DF
0x1800043b5  mov     rdx, [rbp+arg_8]; String2
0x1800043b9  lea     rcx, aS1152191009188; "S-1-15-2-1910091885-1573563583-11049412"...
0x1800043c0  call    cs:__imp__wcsicmp
0x1800043c6  test    eax, eax
0x1800043c8  jz      short loc_1800043FE
0x1800043ca  mov     rdx, [rbp+arg_8]; String2
0x1800043ce  lea     rcx, aS1152286740582; "S-1-15-2-2867405820-2738857118-40218008"...
0x1800043d5  call    cs:__imp__wcsicmp
0x1800043db  test    eax, eax
0x1800043dd  jz      short loc_1800043FE
0x1800043df  mov     rcx, [rbp+arg_8]; pv
0x1800043e3  test    rcx, rcx
0x1800043e6  jz      short loc_1800043EE
0x1800043e8  call    cs:__imp_CoTaskMemFree
0x1800043ee  mov     rbx, [rsp+30h+arg_18]
0x1800043f3  mov     al, sil
0x1800043f6  add     rsp, 30h
0x1800043fa  pop     rdi
0x1800043fb  pop     rsi
0x1800043fc  pop     rbp
0x1800043fd  retn
0x1800043fe  mov     sil, 1
0x180004401  jmp     short loc_1800043DF
0x180004403  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004408  mov     ebx, eax
0x18000440a  jmp     short loc_1800043A8
0x18000440c  call    cs:__imp_GetLastError
0x180004412  mov     ebx, eax
0x180004414  test    eax, eax
0x180004416  jle     loc_1800042B4
0x18000441c  movzx   ebx, ax
0x18000441f  or      ebx, 80070000h
0x180004425  jmp     loc_1800042B4
0x18000442a  call    cs:__imp_GetLastError
0x180004430  mov     ebx, eax
0x180004432  test    eax, eax
0x180004434  jle     loc_180004360
0x18000443a  movzx   ebx, ax
0x18000443d  or      ebx, 80070000h
0x180004443  jmp     loc_180004360
0x180004448  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000444c  mov     edx, 8; DesiredAccess
0x180004451  mov     rcx, rbx; ProcessHandle
0x180004454  call    cs:__imp_OpenProcessToken
0x18000445a  test    eax, eax
0x18000445c  jnz     loc_1800042B2
0x180004462  jmp     short loc_18000440C
0x180004464  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004469  mov     ebx, eax
0x18000446b  test    eax, eax
0x18000446d  js      loc_1800042F9
0x180004473  jmp     loc_1800042F1
0x180004478  call    cs:__imp_CloseHandle
0x18000447e  jmp     loc_180004313
0x180004483  lea     r8, [rbp+TokenInformation]; TokenHandle
0x180004487  mov     edx, 8; DesiredAccess
0x18000448c  mov     rcx, rbx; ProcessHandle
0x18000448f  call    cs:__imp_OpenProcessToken
0x180004495  test    eax, eax
0x180004497  jnz     loc_18000435E
0x18000449d  jmp     short loc_18000442A
0x18000449f  call    cs:__imp_CloseHandle
0x1800044a5  jmp     loc_180004391
```
