# GetCurrentUserSid(void * *)

- ea: `0x1800454a0`
- end: `0x180045613`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `371`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046bf8`

## callees

- `0x18000c668`
- `0x180037780`
- `0x1800454a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004551d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004551d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800454f5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800454f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004550d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004550d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800454da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800454da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800455e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800455e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800455d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800455d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800455a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800455a1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180045580`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180045580`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800455b7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800455b7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045557`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045557`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004558d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004558d`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  int Error; // ebx
  HANDLE CurrentProcess; // rax
  void *v5; // rsi
  void *v6; // rcx
  DWORD LengthSid; // ebp
  HLOCAL v8; // rax
  void *v9; // rdi
  void *TokenHandle; // [rsp+30h] [rbp-98h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-90h] BYREF
  void *TokenInformation; // [rsp+40h] [rbp-88h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_6;
  Error = ResultFromKnownLastError();
  if ( Error == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_6;
    Error = ResultFromKnownLastError();
  }
  if ( Error >= 0 )
  {
LABEL_6:
    ReturnLength = 88;
    if ( !GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x58u, &ReturnLength) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_15;
    }
    v5 = TokenInformation;
    Error = -2147024809;
    v6 = TokenInformation;
    *a1 = 0;
    if ( !IsValidSid(v6) )
      goto LABEL_15;
    LengthSid = GetLengthSid(v5);
    Error = -2147024882;
    v8 = LocalAlloc(0x40u, LengthSid);
    v9 = v8;
    if ( !v8 )
      goto LABEL_15;
    if ( CopySid(LengthSid, v8, v5) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        LocalFree(v9);
        goto LABEL_15;
      }
    }
    *a1 = v9;
LABEL_15:
    CloseHandle(TokenHandle);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800454a0  mov     [rsp+arg_8], rbx
0x1800454a5  mov     [rsp+arg_10], rbp
0x1800454aa  push    rsi
0x1800454ab  push    rdi
0x1800454ac  push    r14
0x1800454ae  sub     rsp, 0B0h
0x1800454b5  mov     rax, cs:__security_cookie
0x1800454bc  xor     rax, rsp
0x1800454bf  mov     [rsp+0C8h+var_28], rax
0x1800454c7  mov     r14, rcx
0x1800454ca  mov     qword ptr [rcx], 0
0x1800454d1  mov     [rsp+0C8h+TokenHandle], 0
0x1800454da  call    cs:__imp_GetCurrentThread
0x1800454e0  mov     esi, 1
0x1800454e5  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x1800454ea  mov     rcx, rax; ThreadHandle
0x1800454ed  mov     r8d, esi; OpenAsSelf
0x1800454f0  lea     edi, [rsi+7]
0x1800454f3  mov     edx, edi; DesiredAccess
0x1800454f5  call    cs:__imp_OpenThreadToken
0x1800454fb  test    eax, eax
0x1800454fd  jnz     short loc_180045536
0x1800454ff  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180045504  mov     ebx, eax
0x180045506  cmp     eax, 800703F0h
0x18004550b  jnz     short loc_18004552E
0x18004550d  call    cs:__imp_GetCurrentProcess
0x180045513  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x180045518  mov     edx, edi; DesiredAccess
0x18004551a  mov     rcx, rax; ProcessHandle
0x18004551d  call    cs:__imp_OpenProcessToken
0x180045523  test    eax, eax
0x180045525  jnz     short loc_180045536
0x180045527  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004552c  mov     ebx, eax
0x18004552e  test    ebx, ebx
0x180045530  js      loc_1800455E9
0x180045536  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x18004553b  lea     rax, [rsp+0C8h+var_90]
0x180045540  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180045546  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x18004554b  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x180045550  mov     [rsp+0C8h+var_90], r9d
0x180045555  mov     edx, esi; TokenInformationClass
0x180045557  call    cs:__imp_GetTokenInformation
0x18004555d  test    eax, eax
0x18004555f  jnz     short loc_18004556C
0x180045561  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180045566  mov     ebx, eax
0x180045568  test    eax, eax
0x18004556a  js      short loc_1800455DE
0x18004556c  mov     rsi, [rsp+0C8h+TokenInformation]
0x180045571  mov     ebx, 80070057h
0x180045576  mov     rcx, rsi; pSid
0x180045579  mov     qword ptr [r14], 0
0x180045580  call    cs:__imp_IsValidSid
0x180045586  test    eax, eax
0x180045588  jz      short loc_1800455DE
0x18004558a  mov     rcx, rsi; pSid
0x18004558d  call    cs:__imp_GetLengthSid
0x180045593  mov     edx, eax; uBytes
0x180045595  mov     ecx, 40h ; '@'; uFlags
0x18004559a  mov     ebp, eax
0x18004559c  mov     ebx, 8007000Eh
0x1800455a1  call    cs:__imp_LocalAlloc
0x1800455a7  mov     rdi, rax
0x1800455aa  test    rax, rax
0x1800455ad  jz      short loc_1800455DE
0x1800455af  mov     r8, rsi; pSourceSid
0x1800455b2  mov     rdx, rax; pDestinationSid
0x1800455b5  mov     ecx, ebp; nDestinationSidLength
0x1800455b7  call    cs:__imp_CopySid
0x1800455bd  test    eax, eax
0x1800455bf  jz      short loc_1800455C5
0x1800455c1  xor     ebx, ebx
0x1800455c3  jmp     short loc_1800455D0
0x1800455c5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800455ca  mov     ebx, eax
0x1800455cc  test    eax, eax
0x1800455ce  js      short loc_1800455D5
0x1800455d0  mov     [r14], rdi
0x1800455d3  jmp     short loc_1800455DE
0x1800455d5  mov     rcx, rdi; hMem
0x1800455d8  call    cs:__imp_LocalFree
0x1800455de  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x1800455e3  call    cs:__imp_CloseHandle
0x1800455e9  mov     eax, ebx
0x1800455eb  mov     rcx, [rsp+0C8h+var_28]
0x1800455f3  xor     rcx, rsp; StackCookie
0x1800455f6  call    __security_check_cookie
0x1800455fb  lea     r11, [rsp+0C8h+var_18]
0x180045603  mov     rbx, [r11+28h]
0x180045607  mov     rbp, [r11+30h]
0x18004560b  mov     rsp, r11
0x18004560e  pop     r14
0x180045610  pop     rdi
0x180045611  pop     rsi
0x180045612  retn
```
