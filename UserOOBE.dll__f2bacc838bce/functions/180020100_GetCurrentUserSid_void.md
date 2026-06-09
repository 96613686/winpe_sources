# GetCurrentUserSid(void * *)

- ea: `0x180020100`
- end: `0x180020273`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `371`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002027c`

## callees

- `0x1800032b0`
- `0x18001e7b4`
- `0x180020100`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002016d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002016d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020155`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020155`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002013a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002013a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002017d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002017d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020243`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020243`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020238`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020238`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020201`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020201`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180020217`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180020217`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800201ed`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800201ed`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800201e0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800201e0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800201b7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800201b7`

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
0x180020100  mov     [rsp+arg_8], rbx
0x180020105  mov     [rsp+arg_10], rbp
0x18002010a  push    rsi
0x18002010b  push    rdi
0x18002010c  push    r14
0x18002010e  sub     rsp, 0B0h
0x180020115  mov     rax, cs:__security_cookie
0x18002011c  xor     rax, rsp
0x18002011f  mov     [rsp+0C8h+var_28], rax
0x180020127  mov     r14, rcx
0x18002012a  mov     qword ptr [rcx], 0
0x180020131  mov     [rsp+0C8h+TokenHandle], 0
0x18002013a  call    cs:__imp_GetCurrentThread
0x180020140  mov     esi, 1
0x180020145  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x18002014a  mov     rcx, rax; ThreadHandle
0x18002014d  mov     r8d, esi; OpenAsSelf
0x180020150  lea     edi, [rsi+7]
0x180020153  mov     edx, edi; DesiredAccess
0x180020155  call    cs:__imp_OpenThreadToken
0x18002015b  test    eax, eax
0x18002015d  jnz     short loc_180020196
0x18002015f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180020164  mov     ebx, eax
0x180020166  cmp     eax, 800703F0h
0x18002016b  jnz     short loc_18002018E
0x18002016d  call    cs:__imp_GetCurrentProcess
0x180020173  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x180020178  mov     edx, edi; DesiredAccess
0x18002017a  mov     rcx, rax; ProcessHandle
0x18002017d  call    cs:__imp_OpenProcessToken
0x180020183  test    eax, eax
0x180020185  jnz     short loc_180020196
0x180020187  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002018c  mov     ebx, eax
0x18002018e  test    ebx, ebx
0x180020190  js      loc_180020249
0x180020196  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x18002019b  lea     rax, [rsp+0C8h+var_90]
0x1800201a0  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800201a6  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x1800201ab  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x1800201b0  mov     [rsp+0C8h+var_90], r9d
0x1800201b5  mov     edx, esi; TokenInformationClass
0x1800201b7  call    cs:__imp_GetTokenInformation
0x1800201bd  test    eax, eax
0x1800201bf  jnz     short loc_1800201CC
0x1800201c1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800201c6  mov     ebx, eax
0x1800201c8  test    eax, eax
0x1800201ca  js      short loc_18002023E
0x1800201cc  mov     rsi, [rsp+0C8h+TokenInformation]
0x1800201d1  mov     ebx, 80070057h
0x1800201d6  mov     rcx, rsi; pSid
0x1800201d9  mov     qword ptr [r14], 0
0x1800201e0  call    cs:__imp_IsValidSid
0x1800201e6  test    eax, eax
0x1800201e8  jz      short loc_18002023E
0x1800201ea  mov     rcx, rsi; pSid
0x1800201ed  call    cs:__imp_GetLengthSid
0x1800201f3  mov     edx, eax; uBytes
0x1800201f5  mov     ecx, 40h ; '@'; uFlags
0x1800201fa  mov     ebp, eax
0x1800201fc  mov     ebx, 8007000Eh
0x180020201  call    cs:__imp_LocalAlloc
0x180020207  mov     rdi, rax
0x18002020a  test    rax, rax
0x18002020d  jz      short loc_18002023E
0x18002020f  mov     r8, rsi; pSourceSid
0x180020212  mov     rdx, rax; pDestinationSid
0x180020215  mov     ecx, ebp; nDestinationSidLength
0x180020217  call    cs:__imp_CopySid
0x18002021d  test    eax, eax
0x18002021f  jz      short loc_180020225
0x180020221  xor     ebx, ebx
0x180020223  jmp     short loc_180020230
0x180020225  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002022a  mov     ebx, eax
0x18002022c  test    eax, eax
0x18002022e  js      short loc_180020235
0x180020230  mov     [r14], rdi
0x180020233  jmp     short loc_18002023E
0x180020235  mov     rcx, rdi; hMem
0x180020238  call    cs:__imp_LocalFree
0x18002023e  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x180020243  call    cs:__imp_CloseHandle
0x180020249  mov     eax, ebx
0x18002024b  mov     rcx, [rsp+0C8h+var_28]
0x180020253  xor     rcx, rsp; StackCookie
0x180020256  call    __security_check_cookie
0x18002025b  lea     r11, [rsp+0C8h+var_18]
0x180020263  mov     rbx, [r11+28h]
0x180020267  mov     rbp, [r11+30h]
0x18002026b  mov     rsp, r11
0x18002026e  pop     r14
0x180020270  pop     rdi
0x180020271  pop     rsi
0x180020272  retn
```
