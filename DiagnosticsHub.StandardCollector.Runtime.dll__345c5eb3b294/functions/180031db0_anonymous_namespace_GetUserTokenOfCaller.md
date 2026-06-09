# _anonymous_namespace_::GetUserTokenOfCaller

- ea: `0x180031db0`
- end: `0x180031fe4`
- name: `_anonymous_namespace_::GetUserTokenOfCaller`
- size: `564`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180032470`
- `0x180033e00`
- `0x180034078`
- `0x180034340`
- `0x1800344b0`

## callees

- `0x180031db0`
- `0x18003d864`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180031e21`
- `KERNEL32!GetCurrentThread` at `0x180031e21`
- `KERNEL32!GetCurrentProcess` at `0x180031e82`
- `KERNEL32!GetCurrentProcess` at `0x180031e82`
- `KERNEL32!CloseHandle` at `0x180031fa5`
- `KERNEL32!CloseHandle` at `0x180031fbc`
- `KERNEL32!CloseHandle` at `0x180031fa5`
- `KERNEL32!CloseHandle` at `0x180031fbc`
- `KERNEL32!GetLastError` at `0x180031e3d`
- `KERNEL32!GetLastError` at `0x180031edf`
- `KERNEL32!GetLastError` at `0x180031f22`
- `KERNEL32!GetLastError` at `0x180031e3d`
- `KERNEL32!GetLastError` at `0x180031edf`
- `KERNEL32!GetLastError` at `0x180031f22`
- `ole32!CoGetCallContext` at `0x180031dfa`
- `ole32!CoGetCallContext` at `0x180031dfa`
- `ADVAPI32!DuplicateToken` at `0x180031eaf`
- `ADVAPI32!DuplicateToken` at `0x180031eaf`
- `ADVAPI32!OpenThreadToken` at `0x180031e35`
- `ADVAPI32!OpenThreadToken` at `0x180031e35`
- `ADVAPI32!OpenProcessToken` at `0x180031e94`
- `ADVAPI32!OpenProcessToken` at `0x180031e94`
- `ADVAPI32!GetTokenInformation` at `0x180031ed9`
- `ADVAPI32!GetTokenInformation` at `0x180031f18`
- `ADVAPI32!GetTokenInformation` at `0x180031ed9`
- `ADVAPI32!GetTokenInformation` at `0x180031f18`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180031eed`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180031eed`

## string_xrefs

- `0x180031f73`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\StandardCollectorService.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall anonymous_namespace_::GetUserTokenOfCaller(_QWORD *a1, _QWORD *a2)
{
  unsigned int v4; // eax
  signed int v5; // ebx
  HANDLE CurrentThread; // rax
  BOOL v7; // esi
  signed int LastError; // edi
  HANDLE CurrentProcess; // rax
  signed int v10; // eax
  void *v11; // rax
  HANDLE v12; // rcx
  HANDLE v13; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-30h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-28h] BYREF
  HANDLE DuplicateTokenHandle; // [rsp+40h] [rbp-20h] BYREF
  void *ppInterface; // [rsp+48h] [rbp-18h] BYREF

  TokenHandle = 0;
  DuplicateTokenHandle = 0;
  ppInterface = 0;
  v4 = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 != -2147417833 )
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\StandardCollectorService.cpp",
        L"Getting call context failed. HRESULT: %#08x",
        v4);
      goto LABEL_24;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle)
      || !DuplicateToken(TokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
    {
      goto LABEL_15;
    }
  }
  else
  {
    v5 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
    if ( v5 < 0 )
      goto LABEL_24;
    CurrentThread = GetCurrentThread();
    v7 = OpenThreadToken(CurrentThread, 0xCu, 0, &TokenHandle);
    LastError = GetLastError();
    v5 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 40LL))(ppInterface);
    if ( v5 < 0 )
      goto LABEL_24;
    if ( !v7 )
    {
      v5 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v5 = LastError;
      goto LABEL_24;
    }
  }
  TokenInformationLength = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v10 = GetLastError();
  if ( v10 != 122 )
    goto LABEL_16;
  v11 = malloc(TokenInformationLength);
  *a1 = v11;
  if ( !v11 )
  {
    v5 = -2147024882;
LABEL_24:
    v12 = DuplicateTokenHandle;
    goto LABEL_25;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v11, TokenInformationLength, &TokenInformationLength) )
  {
LABEL_15:
    v10 = GetLastError();
LABEL_16:
    v5 = (unsigned __int16)v10 | 0x80070000;
    if ( v10 <= 0 )
      v5 = v10;
    goto LABEL_24;
  }
  v12 = DuplicateTokenHandle;
  if ( DuplicateTokenHandle )
  {
    v13 = DuplicateTokenHandle;
    v12 = 0;
    DuplicateTokenHandle = 0;
  }
  else
  {
    v13 = TokenHandle;
    TokenHandle = 0;
  }
  *a2 = v13;
  v5 = 0;
LABEL_25:
  if ( ppInterface )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
    v12 = DuplicateTokenHandle;
  }
  if ( v12 )
  {
    CloseHandle(v12);
    DuplicateTokenHandle = 0;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180031db0  mov     [rsp-28h+arg_10], rbx
0x180031db5  push    rbp
0x180031db6  push    rsi
0x180031db7  push    rdi
0x180031db8  push    r14
0x180031dba  push    r15
0x180031dbc  mov     rbp, rsp
0x180031dbf  sub     rsp, 60h
0x180031dc3  mov     rax, cs:__security_cookie
0x180031dca  xor     rax, rsp
0x180031dcd  mov     [rbp+var_10], rax
0x180031dd1  mov     r15, rdx
0x180031dd4  mov     r14, rcx
0x180031dd7  mov     [rbp+TokenHandle], 0
0x180031ddf  mov     [rbp+DuplicateTokenHandle], 0
0x180031de7  mov     [rbp+ppInterface], 0
0x180031def  lea     rdx, [rbp+ppInterface]; ppInterface
0x180031df3  lea     rcx, IID_IServerSecurity; riid
0x180031dfa  call    cs:__imp_CoGetCallContext
0x180031e00  mov     ebx, eax
0x180031e02  test    eax, eax
0x180031e04  jnz     short loc_180031E77
0x180031e06  mov     rcx, [rbp+ppInterface]
0x180031e0a  mov     rax, [rcx]
0x180031e0d  mov     rax, [rax+20h]
0x180031e11  call    cs:__guard_dispatch_icall_fptr
0x180031e17  mov     ebx, eax
0x180031e19  test    eax, eax
0x180031e1b  js      loc_180031F7F
0x180031e21  call    cs:__imp_GetCurrentThread
0x180031e27  mov     rcx, rax; ThreadHandle
0x180031e2a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180031e2e  xor     r8d, r8d; OpenAsSelf
0x180031e31  lea     edx, [r8+0Ch]; DesiredAccess
0x180031e35  call    cs:__imp_OpenThreadToken
0x180031e3b  mov     esi, eax
0x180031e3d  call    cs:__imp_GetLastError
0x180031e43  mov     edi, eax
0x180031e45  mov     rcx, [rbp+ppInterface]
0x180031e49  mov     rdx, [rcx]
0x180031e4c  mov     rax, [rdx+28h]
0x180031e50  call    cs:__guard_dispatch_icall_fptr
0x180031e56  mov     ebx, eax
0x180031e58  test    eax, eax
0x180031e5a  js      loc_180031F7F
0x180031e60  test    esi, esi
0x180031e62  jnz     short loc_180031EB9
0x180031e64  movzx   ebx, di
0x180031e67  or      ebx, 80070000h
0x180031e6d  test    edi, edi
0x180031e6f  cmovle  ebx, edi
0x180031e72  jmp     loc_180031F7F
0x180031e77  cmp     eax, 80010117h
0x180031e7c  jnz     loc_180031F5B
0x180031e82  call    cs:__imp_GetCurrentProcess
0x180031e88  mov     rcx, rax; ProcessHandle
0x180031e8b  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180031e8f  mov     edx, 0Ah; DesiredAccess
0x180031e94  call    cs:__imp_OpenProcessToken
0x180031e9a  test    eax, eax
0x180031e9c  jz      loc_180031F22
0x180031ea2  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x180031ea6  mov     edx, 2; ImpersonationLevel
0x180031eab  mov     rcx, [rbp+TokenHandle]; ExistingTokenHandle
0x180031eaf  call    cs:__imp_DuplicateToken
0x180031eb5  test    eax, eax
0x180031eb7  jz      short loc_180031F22
0x180031eb9  mov     [rbp+TokenInformationLength], 0
0x180031ec0  lea     rax, [rbp+TokenInformationLength]
0x180031ec4  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180031ec9  xor     r9d, r9d; TokenInformationLength
0x180031ecc  xor     r8d, r8d; TokenInformation
0x180031ecf  lea     ebx, [r9+1]
0x180031ed3  mov     edx, ebx; TokenInformationClass
0x180031ed5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180031ed9  call    cs:__imp_GetTokenInformation
0x180031edf  call    cs:__imp_GetLastError
0x180031ee5  cmp     eax, 7Ah ; 'z'
0x180031ee8  jnz     short loc_180031F28
0x180031eea  mov     ecx, [rbp+TokenInformationLength]; Size
0x180031eed  call    cs:__imp_malloc
0x180031ef3  mov     [r14], rax
0x180031ef6  test    rax, rax
0x180031ef9  jnz     short loc_180031F02
0x180031efb  mov     ebx, 8007000Eh
0x180031f00  jmp     short loc_180031F7F
0x180031f02  lea     rcx, [rbp+TokenInformationLength]
0x180031f06  mov     [rsp+60h+ReturnLength], rcx; ReturnLength
0x180031f0b  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180031f0f  mov     r8, rax; TokenInformation
0x180031f12  mov     edx, ebx; TokenInformationClass
0x180031f14  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180031f18  call    cs:__imp_GetTokenInformation
0x180031f1e  test    eax, eax
0x180031f20  jnz     short loc_180031F38
0x180031f22  call    cs:__imp_GetLastError
0x180031f28  movzx   ebx, ax
0x180031f2b  or      ebx, 80070000h
0x180031f31  test    eax, eax
0x180031f33  cmovle  ebx, eax
0x180031f36  jmp     short loc_180031F7F
0x180031f38  mov     rcx, [rbp+DuplicateTokenHandle]
0x180031f3c  test    rcx, rcx
0x180031f3f  jnz     short loc_180031F4B
0x180031f41  mov     rax, [rbp+TokenHandle]
0x180031f45  mov     [rbp+TokenHandle], rcx
0x180031f49  jmp     short loc_180031F54
0x180031f4b  mov     rax, rcx
0x180031f4e  xor     ecx, ecx
0x180031f50  mov     [rbp+DuplicateTokenHandle], rcx
0x180031f54  mov     [r15], rax
0x180031f57  xor     ebx, ebx
0x180031f59  jmp     short loc_180031F83
0x180031f5b  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180031f62  add     rcx, 0A8h; this
0x180031f69  mov     r9d, eax
0x180031f6c  lea     r8, aGettingCallCon; "Getting call context failed. HRESULT: %"...
0x180031f73  lea     rdx, aDAWork1SSource_7; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180031f7a  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180031f7f  mov     rcx, [rbp+DuplicateTokenHandle]
0x180031f83  mov     rdx, [rbp+ppInterface]
0x180031f87  test    rdx, rdx
0x180031f8a  jz      short loc_180031FA0
0x180031f8c  mov     rax, [rdx]
0x180031f8f  mov     rcx, rdx
0x180031f92  mov     rax, [rax+10h]
0x180031f96  call    cs:__guard_dispatch_icall_fptr
0x180031f9c  mov     rcx, [rbp+DuplicateTokenHandle]; hObject
0x180031fa0  test    rcx, rcx
0x180031fa3  jz      short loc_180031FB3
0x180031fa5  call    cs:__imp_CloseHandle
0x180031fab  mov     [rbp+DuplicateTokenHandle], 0
0x180031fb3  mov     rcx, [rbp+TokenHandle]; hObject
0x180031fb7  test    rcx, rcx
0x180031fba  jz      short loc_180031FC2
0x180031fbc  call    cs:__imp_CloseHandle
0x180031fc2  mov     eax, ebx
0x180031fc4  mov     rcx, [rbp+var_10]
0x180031fc8  xor     rcx, rsp; StackCookie
0x180031fcb  call    __security_check_cookie
0x180031fd0  mov     rbx, [rsp+60h+arg_10]
0x180031fd8  add     rsp, 60h
0x180031fdc  pop     r15
0x180031fde  pop     r14
0x180031fe0  pop     rdi
0x180031fe1  pop     rsi
0x180031fe2  pop     rbp
0x180031fe3  retn
```
