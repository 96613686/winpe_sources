# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x1800a4ae4`
- end: `0x1800a4c3e`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `346`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a49d4`
- `0x1800a4a74`
- `0x1802afbe8`
- `0x180548c6c`
- `0x18059333c`
- `0x180598be0`
- `0x1805bc03c`

## callees

- `0x18009d164`
- `0x1800a4ae4`
- `0x18015adb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180642a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180642aa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180642a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180642aa4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a4b0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a4be2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a4b0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a4be2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a4b5a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a4b5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a4b4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a4b4b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a4b25`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a4bf7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a4b25`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a4bf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a4bbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a4bbd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a4b79`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a4b79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a4c16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180642a5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a4c16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180642a5a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a4ba3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180642a96`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a4ba3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180642a96`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_USER>(__int64 a1, DWORD a2, int a3, _QWORD *a4)
{
  HANDLE CurrentThread; // rax
  __int64 result; // rax
  HANDLE CurrentProcess; // rax
  void *v9; // rsi
  void *v10; // rdi
  signed int v11; // ebx
  HANDLE v12; // rax
  signed int LastError; // eax
  void *v14; // rcx
  int v15; // eax
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  LPVOID TokenInformation; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a2;
  *a4 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    result = ResultFromKnownLastError();
    if ( (int)result < 0 )
    {
      if ( a3 && (_DWORD)result == -2147024891 )
      {
        v12 = GetCurrentThread();
        if ( OpenThreadToken(v12, 8u, 1, &TokenHandle) )
          goto LABEL_6;
        result = ResultFromKnownLastError();
      }
      if ( (_DWORD)result == -2147023888 )
      {
        CurrentProcess = GetCurrentProcess();
        if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
          goto LABEL_6;
        result = ResultFromKnownLastError();
      }
      if ( (int)result < 0 )
        return result;
    }
  }
LABEL_6:
  v9 = TokenHandle;
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v10 = TokenInformation;
  if ( !TokenInformation )
  {
    v11 = -2147024882;
    goto LABEL_9;
  }
  v11 = 0;
  if ( !GetTokenInformation(v9, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v10);
      v15 = CTLocalAllocPolicy::Alloc(v14, 0x40u, TokenInformationLength, &TokenInformation);
      v10 = TokenInformation;
      v11 = v15;
      if ( v15 < 0 )
        goto LABEL_17;
      if ( GetTokenInformation(v9, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_8;
      LastError = GetLastError();
      v11 = LastError;
    }
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 >= 0 )
      goto LABEL_8;
LABEL_17:
    LocalFree(v10);
    goto LABEL_9;
  }
LABEL_8:
  *a4 = v10;
LABEL_9:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800a4ae4  mov     [rsp-28h+TokenInformationLength], edx
0x1800a4ae8  mov     [rsp-28h+TokenHandle], rcx
0x1800a4aed  push    rbp
0x1800a4aee  push    rbx
0x1800a4aef  push    rsi
0x1800a4af0  push    rdi
0x1800a4af1  push    r14
0x1800a4af3  mov     rbp, rsp
0x1800a4af6  sub     rsp, 30h
0x1800a4afa  mov     r14, r9
0x1800a4afd  mov     qword ptr [r9], 0
0x1800a4b04  mov     ebx, r8d
0x1800a4b07  mov     [rbp+TokenHandle], 0
0x1800a4b0f  call    cs:__imp_GetCurrentThread
0x1800a4b15  xor     r8d, r8d; OpenAsSelf
0x1800a4b18  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800a4b1c  mov     rcx, rax; ThreadHandle
0x1800a4b1f  lea     edi, [r8+8]
0x1800a4b23  mov     edx, edi; DesiredAccess
0x1800a4b25  call    cs:__imp_OpenThreadToken
0x1800a4b2b  test    eax, eax
0x1800a4b2d  jnz     short loc_1800A4B68
0x1800a4b2f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800a4b34  test    eax, eax
0x1800a4b36  jns     short loc_1800A4B68
0x1800a4b38  test    ebx, ebx
0x1800a4b3a  jnz     loc_1800A4BD7
0x1800a4b40  cmp     eax, 800703F0h
0x1800a4b45  jnz     loc_1800A4C2D
0x1800a4b4b  call    cs:__imp_GetCurrentProcess
0x1800a4b51  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800a4b55  mov     edx, edi; DesiredAccess
0x1800a4b57  mov     rcx, rax; ProcessHandle
0x1800a4b5a  call    cs:__imp_OpenProcessToken
0x1800a4b60  test    eax, eax
0x1800a4b62  jz      loc_1800A4C37
0x1800a4b68  mov     rsi, [rbp+TokenHandle]
0x1800a4b6c  mov     edx, 800h; uBytes
0x1800a4b71  mov     ecx, 40h ; '@'; uFlags
0x1800a4b76  mov     [rbp+TokenInformationLength], edx
0x1800a4b79  call    cs:__imp_LocalAlloc
0x1800a4b7f  mov     [rbp+TokenInformation], rax
0x1800a4b83  mov     rdi, rax
0x1800a4b86  test    rax, rax
0x1800a4b89  jz      short loc_1800A4BD0
0x1800a4b8b  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800a4b8f  lea     rax, [rbp+TokenInformationLength]
0x1800a4b93  xor     ebx, ebx
0x1800a4b95  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800a4b9a  mov     r8, rdi; TokenInformation
0x1800a4b9d  mov     rcx, rsi; TokenHandle
0x1800a4ba0  lea     edx, [rbx+1]; TokenInformationClass
0x1800a4ba3  call    cs:__imp_GetTokenInformation
0x1800a4ba9  test    eax, eax
0x1800a4bab  jz      loc_180642A46
0x1800a4bb1  mov     [r14], rdi
0x1800a4bb4  mov     rcx, [rbp+TokenHandle]; hObject
0x1800a4bb8  test    rcx, rcx
0x1800a4bbb  jz      short loc_1800A4BC3
0x1800a4bbd  call    cs:__imp_CloseHandle
0x1800a4bc3  mov     eax, ebx
0x1800a4bc5  add     rsp, 30h
0x1800a4bc9  pop     r14
0x1800a4bcb  pop     rdi
0x1800a4bcc  pop     rsi
0x1800a4bcd  pop     rbx
0x1800a4bce  pop     rbp
0x1800a4bcf  retn
0x1800a4bd0  mov     ebx, 8007000Eh
0x1800a4bd5  jmp     short loc_1800A4BB4
0x1800a4bd7  cmp     eax, 80070005h
0x1800a4bdc  jnz     loc_1800A4B40
0x1800a4be2  call    cs:__imp_GetCurrentThread
0x1800a4be8  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800a4bec  mov     r8d, 1; OpenAsSelf
0x1800a4bf2  mov     rcx, rax; ThreadHandle
0x1800a4bf5  mov     edx, edi; DesiredAccess
0x1800a4bf7  call    cs:__imp_OpenThreadToken
0x1800a4bfd  test    eax, eax
0x1800a4bff  jnz     loc_1800A4B68
0x1800a4c05  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800a4c0a  jmp     loc_1800A4B40
0x1800a4c0f  test    ebx, ebx
0x1800a4c11  jns     short loc_1800A4BB1
0x1800a4c13  mov     rcx, rdi; hMem
0x1800a4c16  call    cs:__imp_LocalFree
0x1800a4c1c  jmp     short loc_1800A4BB4
0x1800a4c1e  test    eax, eax
0x1800a4c20  jle     short loc_1800A4C0F
0x1800a4c22  movzx   ebx, ax
0x1800a4c25  or      ebx, 80070000h
0x1800a4c2b  jmp     short loc_1800A4C0F
0x1800a4c2d  test    eax, eax
0x1800a4c2f  jns     loc_1800A4B68
0x1800a4c35  jmp     short loc_1800A4BC5
0x1800a4c37  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800a4c3c  jmp     short loc_1800A4C2D
0x180642a46  call    cs:__imp_GetLastError
0x180642a4c  mov     ebx, eax
0x180642a4e  cmp     eax, 7Ah ; 'z'
0x180642a51  jnz     loc_1800A4C1E
0x180642a57  mov     rcx, rdi; hMem
0x180642a5a  call    cs:__imp_LocalFree
0x180642a60  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x180642a64  lea     r9, [rbp+TokenInformation]; void **
0x180642a68  lea     edx, [rbx-3Ah]; unsigned int
0x180642a6b  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180642a70  mov     rdi, [rbp+TokenInformation]
0x180642a74  mov     ebx, eax
0x180642a76  test    eax, eax
0x180642a78  js      loc_1800A4C13
0x180642a7e  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180642a82  lea     rax, [rbp+TokenInformationLength]
0x180642a86  mov     r8, rdi; TokenInformation
0x180642a89  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180642a8e  mov     edx, 1; TokenInformationClass
0x180642a93  mov     rcx, rsi; TokenHandle
0x180642a96  call    cs:__imp_GetTokenInformation
0x180642a9c  test    eax, eax
0x180642a9e  jnz     loc_1800A4BB1
0x180642aa4  call    cs:__imp_GetLastError
0x180642aaa  mov     ebx, eax
0x180642aac  jmp     loc_1800A4C1E
```
