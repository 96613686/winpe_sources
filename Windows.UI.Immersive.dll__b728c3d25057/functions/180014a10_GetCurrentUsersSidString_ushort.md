# GetCurrentUsersSidString(ushort * *)

- ea: `0x180014a10`
- end: `0x180014bc6`
- name: `?GetCurrentUsersSidString@@YAJPEAPEAG@Z`
- size: `438`
- prototype: `__int64 __fastcall(LPWSTR *ppwsz)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013690`
- `0x180013e00`
- `0x1800140e0`
- `0x180014880`
- `0x180014bd0`
- `0x1800c2fa0`
- `0x1800d38d8`

## callees

- `0x180014a10`
- `0x180030ea4`
- `0x18003aa84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b2c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014a4b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014a4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014a35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014a35`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014a7a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014a7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014a6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014a6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014b63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014b63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014aec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014ba4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014bad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014aec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014b48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014ba4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014bad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014aa4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014aa4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014ad2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014b22`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014ad2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014b22`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014b98`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014b98`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014b7c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014b7c`

## pseudocode

```c
__int64 __fastcall GetCurrentUsersSidString(LPWSTR *ppwsz)
{
  HANDLE CurrentThread; // rax
  int Error; // eax
  int v4; // ebx
  HANDLE CurrentProcess; // rax
  void *v6; // r14
  void **v7; // rsi
  void *v8; // rdi
  signed int LastError; // eax
  void *v10; // rcx
  int v11; // eax
  void *v12; // rcx
  DWORD TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF
  LPVOID TokenInformation; // [rsp+70h] [rbp+40h] BYREF

  *ppwsz = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    Error = ResultFromKnownLastError();
    v4 = Error;
    if ( Error < 0 )
    {
      if ( Error != -2147023888 )
        return (unsigned int)v4;
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        v4 = ResultFromKnownLastError();
        if ( v4 < 0 )
          return (unsigned int)v4;
      }
    }
  }
  v6 = TokenHandle;
  v7 = 0;
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v8 = TokenInformation;
  if ( !TokenInformation )
  {
    v4 = -2147024882;
    goto LABEL_18;
  }
  v4 = 0;
  if ( GetTokenInformation(v6, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_16;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError != 122 )
    goto LABEL_12;
  LocalFree(v8);
  v11 = CTLocalAllocPolicy::Alloc(v10, 0x40u, TokenInformationLength, &TokenInformation);
  v8 = TokenInformation;
  v4 = v11;
  if ( v11 >= 0 )
  {
    if ( GetTokenInformation(v6, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_16;
    LastError = GetLastError();
    v4 = LastError;
LABEL_12:
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_15;
LABEL_16:
    v7 = (void **)v8;
    goto LABEL_18;
  }
LABEL_15:
  LocalFree(v8);
LABEL_18:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v4 >= 0 )
  {
    v12 = *v7;
    TokenInformation = 0;
    if ( ConvertSidToStringSidW(v12, (LPWSTR *)&TokenInformation) || (v4 = ResultFromKnownLastError(), v4 >= 0) )
    {
      v4 = SHStrDupW((LPCWSTR)TokenInformation, ppwsz);
      LocalFree(TokenInformation);
    }
    LocalFree(v7);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014a10  mov     [rsp-28h+arg_18], rbx
0x180014a15  push    rbp
0x180014a16  push    rsi
0x180014a17  push    rdi
0x180014a18  push    r14
0x180014a1a  push    r15
0x180014a1c  mov     rbp, rsp
0x180014a1f  sub     rsp, 30h
0x180014a23  mov     r15, rcx
0x180014a26  mov     qword ptr [rcx], 0
0x180014a2d  mov     [rbp+TokenHandle], 0
0x180014a35  call    cs:__imp_GetCurrentThread
0x180014a3b  xor     r8d, r8d; OpenAsSelf
0x180014a3e  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180014a42  mov     rcx, rax; ThreadHandle
0x180014a45  lea     edi, [r8+8]
0x180014a49  mov     edx, edi; DesiredAccess
0x180014a4b  call    cs:__imp_OpenThreadToken
0x180014a51  test    eax, eax
0x180014a53  jnz     short loc_180014A93
0x180014a55  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014a5a  mov     ebx, eax
0x180014a5c  test    eax, eax
0x180014a5e  jns     short loc_180014A93
0x180014a60  cmp     eax, 800703F0h
0x180014a65  jnz     loc_180014BB3
0x180014a6b  call    cs:__imp_GetCurrentProcess
0x180014a71  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180014a75  mov     edx, edi; DesiredAccess
0x180014a77  mov     rcx, rax; ProcessHandle
0x180014a7a  call    cs:__imp_OpenProcessToken
0x180014a80  test    eax, eax
0x180014a82  jnz     short loc_180014A93
0x180014a84  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014a89  mov     ebx, eax
0x180014a8b  test    eax, eax
0x180014a8d  js      loc_180014BB3
0x180014a93  mov     r14, [rbp+TokenHandle]
0x180014a97  mov     edx, 800h; uBytes
0x180014a9c  xor     esi, esi
0x180014a9e  mov     [rbp+TokenInformationLength], edx
0x180014aa1  lea     ecx, [rsi+40h]; uFlags
0x180014aa4  call    cs:__imp_LocalAlloc
0x180014aaa  mov     [rbp+TokenInformation], rax
0x180014aae  mov     rdi, rax
0x180014ab1  test    rax, rax
0x180014ab4  jz      loc_180014B55
0x180014aba  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180014abe  lea     rax, [rbp+TokenInformationLength]
0x180014ac2  mov     r8, rdi; TokenInformation
0x180014ac5  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180014aca  lea     edx, [rsi+1]; TokenInformationClass
0x180014acd  mov     rcx, r14; TokenHandle
0x180014ad0  xor     ebx, ebx
0x180014ad2  call    cs:__imp_GetTokenInformation
0x180014ad8  test    eax, eax
0x180014ada  jnz     short loc_180014B50
0x180014adc  call    cs:__imp_GetLastError
0x180014ae2  mov     ebx, eax
0x180014ae4  cmp     eax, 7Ah ; 'z'
0x180014ae7  jnz     short loc_180014B34
0x180014ae9  mov     rcx, rdi; hMem
0x180014aec  call    cs:__imp_LocalFree
0x180014af2  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x180014af6  lea     r9, [rbp+TokenInformation]; void **
0x180014afa  lea     edx, [rsi+40h]; unsigned int
0x180014afd  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180014b02  mov     rdi, [rbp+TokenInformation]
0x180014b06  mov     ebx, eax
0x180014b08  test    eax, eax
0x180014b0a  js      short loc_180014B45
0x180014b0c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180014b10  lea     rax, [rbp+TokenInformationLength]
0x180014b14  mov     r8, rdi; TokenInformation
0x180014b17  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180014b1c  lea     edx, [rsi+1]; TokenInformationClass
0x180014b1f  mov     rcx, r14; TokenHandle
0x180014b22  call    cs:__imp_GetTokenInformation
0x180014b28  test    eax, eax
0x180014b2a  jnz     short loc_180014B50
0x180014b2c  call    cs:__imp_GetLastError
0x180014b32  mov     ebx, eax
0x180014b34  test    eax, eax
0x180014b36  jle     short loc_180014B41
0x180014b38  movzx   ebx, ax
0x180014b3b  or      ebx, 80070000h
0x180014b41  test    ebx, ebx
0x180014b43  jns     short loc_180014B50
0x180014b45  mov     rcx, rdi; hMem
0x180014b48  call    cs:__imp_LocalFree
0x180014b4e  jmp     short loc_180014B5A
0x180014b50  mov     rsi, rdi
0x180014b53  jmp     short loc_180014B5A
0x180014b55  mov     ebx, 8007000Eh
0x180014b5a  mov     rcx, [rbp+TokenHandle]; hObject
0x180014b5e  test    rcx, rcx
0x180014b61  jz      short loc_180014B69
0x180014b63  call    cs:__imp_CloseHandle
0x180014b69  test    ebx, ebx
0x180014b6b  js      short loc_180014BB3
0x180014b6d  mov     rcx, [rsi]; Sid
0x180014b70  lea     rdx, [rbp+TokenInformation]; StringSid
0x180014b74  mov     [rbp+TokenInformation], 0
0x180014b7c  call    cs:__imp_ConvertSidToStringSidW
0x180014b82  test    eax, eax
0x180014b84  jnz     short loc_180014B91
0x180014b86  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014b8b  mov     ebx, eax
0x180014b8d  test    eax, eax
0x180014b8f  js      short loc_180014BAA
0x180014b91  mov     rcx, [rbp+TokenInformation]; psz
0x180014b95  mov     rdx, r15; ppwsz
0x180014b98  call    cs:__imp_SHStrDupW
0x180014b9e  mov     rcx, [rbp+TokenInformation]; hMem
0x180014ba2  mov     ebx, eax
0x180014ba4  call    cs:__imp_LocalFree
0x180014baa  mov     rcx, rsi; hMem
0x180014bad  call    cs:__imp_LocalFree
0x180014bb3  mov     eax, ebx
0x180014bb5  mov     rbx, [rsp+30h+arg_18]
0x180014bba  add     rsp, 30h
0x180014bbe  pop     r15
0x180014bc0  pop     r14
0x180014bc2  pop     rdi
0x180014bc3  pop     rsi
0x180014bc4  pop     rbp
0x180014bc5  retn
```
