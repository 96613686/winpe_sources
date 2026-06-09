# GetUserSid(void * *,uint *)

- ea: `0x180028e90`
- end: `0x1800290c4`
- name: `?GetUserSid@@YAJPEAPEAXPEAI@Z`
- size: `564`
- prototype: `signed int __fastcall(void **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180028c90`

## callees

- `0x1800016d0`
- `0x180028e90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180028ed9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180028ed9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180028f32`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180028f32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028f23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028f23`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028eee`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029065`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028feb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028feb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002905b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002905b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028f5e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028fc3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028f5e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028fc3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180029030`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180029030`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002900b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002900b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002907d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029093`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002907d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029093`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028f90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002903d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028f90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002903d`

## pseudocode

```c
signed int __fastcall GetUserSid(void **a1, unsigned int *a2)
{
  signed int v2; // ebx
  int v5; // r15d
  HANDLE CurrentThread; // rax
  signed int result; // eax
  HANDLE CurrentProcess; // rax
  int v9; // r13d
  PSID *v10; // rsi
  DWORD v11; // eax
  signed int LastError; // eax
  signed int v13; // eax
  HLOCAL v14; // rax
  signed int v15; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-59h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-51h] BYREF
  _BYTE TokenInformation[112]; // [rsp+40h] [rbp-49h] BYREF

  v2 = 0;
  *a2 = 2;
  TokenHandle = 0;
  *a1 = 0;
  TokenInformationLength = 0;
  v5 = 1;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xAu, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008
      || (v5 = 0, CurrentProcess = GetCurrentProcess(), !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle)) )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
  }
  v9 = 0;
  v10 = (PSID *)TokenInformation;
  if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x64u, &TokenInformationLength) )
  {
    v11 = TokenInformationLength;
    if ( TokenInformationLength <= 0x64 )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( v2 < 0 )
        goto LABEL_17;
      v11 = TokenInformationLength;
    }
    v10 = (PSID *)LocalAlloc(0, v11);
    if ( v10 )
    {
      v9 = 1;
      if ( !GetTokenInformation(TokenHandle, TokenUser, v10, TokenInformationLength, &TokenInformationLength) )
      {
        v13 = GetLastError();
        v2 = v13;
        if ( v13 > 0 )
          v2 = (unsigned __int16)v13 | 0x80070000;
      }
    }
    else
    {
      v2 = -2147024882;
    }
  }
LABEL_17:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v2 >= 0 )
  {
    if ( EqualSid(*v10, &LocalSystemSid) )
      *a2 = 1;
    else
      *a2 = (v5 != 0) + 2;
    TokenInformationLength = GetLengthSid(*v10);
    v14 = LocalAlloc(0, TokenInformationLength);
    *a1 = v14;
    if ( v14 )
    {
      if ( !CopySid(TokenInformationLength, v14, *v10) )
      {
        v15 = GetLastError();
        v2 = v15;
        if ( v15 > 0 )
          v2 = (unsigned __int16)v15 | 0x80070000;
        LocalFree(*a1);
        *a1 = 0;
      }
    }
    else
    {
      v2 = -2147024882;
    }
  }
  if ( v9 == 1 )
    LocalFree(v10);
  return v2;
}

```

## disassembly

```asm
0x180028e90  mov     [rsp-8+arg_10], rbx
0x180028e95  mov     [rsp-8+arg_18], rsi
0x180028e9a  push    rbp
0x180028e9b  push    r12
0x180028e9d  push    r13
0x180028e9f  push    r14
0x180028ea1  push    r15
0x180028ea3  lea     rbp, [rsp-37h]
0x180028ea8  sub     rsp, 0C0h
0x180028eaf  mov     rax, cs:__security_cookie
0x180028eb6  xor     rax, rsp
0x180028eb9  mov     [rbp+57h+var_30], rax
0x180028ebd  xor     ebx, ebx
0x180028ebf  mov     dword ptr [rdx], 2
0x180028ec5  mov     r12, rdx
0x180028ec8  mov     [rbp+57h+TokenHandle], rbx
0x180028ecc  mov     r14, rcx
0x180028ecf  mov     [rcx], rbx
0x180028ed2  mov     [rbp+57h+TokenInformationLength], ebx
0x180028ed5  lea     r15d, [rbx+1]
0x180028ed9  call    cs:__imp_GetCurrentThread
0x180028edf  lea     esi, [rbx+0Ah]
0x180028ee2  mov     r8d, r15d; OpenAsSelf
0x180028ee5  mov     rcx, rax; ThreadHandle
0x180028ee8  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180028eec  mov     edx, esi; DesiredAccess
0x180028eee  call    cs:__imp_OpenThreadToken
0x180028ef4  test    eax, eax
0x180028ef6  jnz     short loc_180028F3C
0x180028ef8  call    cs:__imp_GetLastError
0x180028efe  cmp     eax, 3F0h
0x180028f03  jz      short loc_180028F20
0x180028f05  call    cs:__imp_GetLastError
0x180028f0b  test    eax, eax
0x180028f0d  jle     loc_18002909B
0x180028f13  movzx   eax, ax
0x180028f16  or      eax, 80070000h
0x180028f1b  jmp     loc_18002909B
0x180028f20  mov     r15d, ebx
0x180028f23  call    cs:__imp_GetCurrentProcess
0x180028f29  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180028f2d  mov     edx, esi; DesiredAccess
0x180028f2f  mov     rcx, rax; ProcessHandle
0x180028f32  call    cs:__imp_OpenProcessToken
0x180028f38  test    eax, eax
0x180028f3a  jz      short loc_180028F05
0x180028f3c  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180028f40  lea     rax, [rbp+57h+TokenInformationLength]
0x180028f44  mov     r9d, 64h ; 'd'; TokenInformationLength
0x180028f4a  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180028f4f  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180028f53  mov     r13d, ebx
0x180028f56  lea     rsi, [rbp+57h+TokenInformation]
0x180028f5a  lea     edx, [r9-63h]; TokenInformationClass
0x180028f5e  call    cs:__imp_GetTokenInformation
0x180028f64  test    eax, eax
0x180028f66  jnz     short loc_180028FE2
0x180028f68  mov     eax, [rbp+57h+TokenInformationLength]
0x180028f6b  cmp     eax, 64h ; 'd'
0x180028f6e  ja      short loc_180028F8C
0x180028f70  call    cs:__imp_GetLastError
0x180028f76  mov     ebx, eax
0x180028f78  test    eax, eax
0x180028f7a  jle     short loc_180028F85
0x180028f7c  movzx   ebx, ax
0x180028f7f  or      ebx, 80070000h
0x180028f85  test    ebx, ebx
0x180028f87  js      short loc_180028FE2
0x180028f89  mov     eax, [rbp+57h+TokenInformationLength]
0x180028f8c  mov     edx, eax; uBytes
0x180028f8e  xor     ecx, ecx; uFlags
0x180028f90  call    cs:__imp_LocalAlloc
0x180028f96  mov     rsi, rax
0x180028f99  test    rax, rax
0x180028f9c  jnz     short loc_180028FA5
0x180028f9e  mov     ebx, 8007000Eh
0x180028fa3  jmp     short loc_180028FE2
0x180028fa5  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180028fa9  lea     rax, [rbp+57h+TokenInformationLength]
0x180028fad  mov     ecx, 1
0x180028fb2  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180028fb7  mov     r13d, ecx
0x180028fba  mov     edx, ecx; TokenInformationClass
0x180028fbc  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180028fc0  mov     r8, rsi; TokenInformation
0x180028fc3  call    cs:__imp_GetTokenInformation
0x180028fc9  test    eax, eax
0x180028fcb  jnz     short loc_180028FE2
0x180028fcd  call    cs:__imp_GetLastError
0x180028fd3  mov     ebx, eax
0x180028fd5  test    eax, eax
0x180028fd7  jle     short loc_180028FE2
0x180028fd9  movzx   ebx, ax
0x180028fdc  or      ebx, 80070000h
0x180028fe2  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180028fe6  test    rcx, rcx
0x180028fe9  jz      short loc_180028FF9
0x180028feb  call    cs:__imp_CloseHandle
0x180028ff1  mov     [rbp+57h+TokenHandle], 0
0x180028ff9  test    ebx, ebx
0x180028ffb  js      loc_18002908A
0x180029001  mov     rcx, [rsi]; pSid1
0x180029004  lea     rdx, ?LocalSystemSid@@3U_SID@@A; pSid2
0x18002900b  call    cs:__imp_EqualSid
0x180029011  test    eax, eax
0x180029013  jz      short loc_18002901F
0x180029015  mov     dword ptr [r12], 1
0x18002901d  jmp     short loc_18002902D
0x18002901f  neg     r15d
0x180029022  sbb     eax, eax
0x180029024  neg     eax
0x180029026  add     eax, 2
0x180029029  mov     [r12], eax
0x18002902d  mov     rcx, [rsi]; pSid
0x180029030  call    cs:__imp_GetLengthSid
0x180029036  mov     edx, eax; uBytes
0x180029038  xor     ecx, ecx; uFlags
0x18002903a  mov     [rbp+57h+TokenInformationLength], edx
0x18002903d  call    cs:__imp_LocalAlloc
0x180029043  mov     [r14], rax
0x180029046  test    rax, rax
0x180029049  jnz     short loc_180029052
0x18002904b  mov     ebx, 8007000Eh
0x180029050  jmp     short loc_18002908A
0x180029052  mov     r8, [rsi]; pSourceSid
0x180029055  mov     rdx, rax; pDestinationSid
0x180029058  mov     ecx, [rbp+57h+TokenInformationLength]; nDestinationSidLength
0x18002905b  call    cs:__imp_CopySid
0x180029061  test    eax, eax
0x180029063  jnz     short loc_18002908A
0x180029065  call    cs:__imp_GetLastError
0x18002906b  mov     ebx, eax
0x18002906d  test    eax, eax
0x18002906f  jle     short loc_18002907A
0x180029071  movzx   ebx, ax
0x180029074  or      ebx, 80070000h
0x18002907a  mov     rcx, [r14]; hMem
0x18002907d  call    cs:__imp_LocalFree
0x180029083  mov     qword ptr [r14], 0
0x18002908a  cmp     r13d, 1
0x18002908e  jnz     short loc_180029099
0x180029090  mov     rcx, rsi; hMem
0x180029093  call    cs:__imp_LocalFree
0x180029099  mov     eax, ebx
0x18002909b  mov     rcx, [rbp+57h+var_30]
0x18002909f  xor     rcx, rsp; StackCookie
0x1800290a2  call    __security_check_cookie
0x1800290a7  lea     r11, [rsp+0E0h+var_20]
0x1800290af  mov     rbx, [r11+40h]
0x1800290b3  mov     rsi, [r11+48h]
0x1800290b7  mov     rsp, r11
0x1800290ba  pop     r15
0x1800290bc  pop     r14
0x1800290be  pop     r13
0x1800290c0  pop     r12
0x1800290c2  pop     rbp
0x1800290c3  retn
```
