# WaasMedic::CAutoThreadPrivilegeHelper::AcquireThreadToken(void)

- ea: `0x180031f54`
- end: `0x18003208e`
- name: `?AcquireThreadToken@CAutoThreadPrivilegeHelper@WaasMedic@@AEAAJXZ`
- size: `314`
- prototype: `__int64 __fastcall(PHANDLE phNewToken)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180032408`

## callees

- `0x18002543c`
- `0x180031f54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032049`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031fea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031fea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031f69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031f69`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180031f7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180031f7e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003203f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003203f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031fbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031fe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003207d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031fbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031fe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003207d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003200f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003200f`

## string_xrefs

- `0x18003202e`: `Failed to duplicate token! hr = 0x%08x`
- `0x180031f9d`: `Failed to get process token: 0x%08X`
- `0x18003205e`: `Failed to set the thread token: 0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::CAutoThreadPrivilegeHelper::AcquireThreadToken(PHANDLE phNewToken)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  void *v6; // rsi
  DWORD v7; // ebx
  void *v8; // rcx
  signed int v9; // eax
  signed int v10; // eax
  char *v11; // rcx
  void *TokenHandle; // [rsp+68h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 2u, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(2u, L"Failed to get process token: 0x%08X", v4);
LABEL_5:
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v4;
  }
  v6 = *phNewToken;
  if ( (char *)*phNewToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v7 = GetLastError();
    CloseHandle(v6);
    SetLastError(v7);
  }
  v8 = TokenHandle;
  *phNewToken = 0;
  if ( !DuplicateTokenEx(v8, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
  {
    v9 = GetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    LogLevelW(2u, L"Failed to duplicate token! hr = 0x%08x", v4);
    goto LABEL_5;
  }
  if ( !SetThreadToken(0, *phNewToken) )
  {
    v10 = GetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    LogLevelW(2u, L"Failed to set the thread token: 0x%08X", v4);
    goto LABEL_5;
  }
  v11 = (char *)TokenHandle;
  *((_BYTE *)phNewToken + 8) = 1;
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v11);
  return 0;
}

```

## disassembly

```asm
0x180031f54  push    rbx
0x180031f56  push    rbp
0x180031f57  push    rsi
0x180031f58  push    rdi
0x180031f59  sub     rsp, 38h
0x180031f5d  mov     rdi, rcx
0x180031f60  mov     [rsp+58h+TokenHandle], 0
0x180031f69  call    cs:__imp_GetCurrentProcess
0x180031f6f  mov     ebp, 2
0x180031f74  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180031f79  mov     edx, ebp; DesiredAccess
0x180031f7b  mov     rcx, rax; ProcessHandle
0x180031f7e  call    cs:__imp_OpenProcessToken
0x180031f84  test    eax, eax
0x180031f86  jnz     short loc_180031FCA
0x180031f88  call    cs:__imp_GetLastError
0x180031f8e  mov     ebx, eax
0x180031f90  test    eax, eax
0x180031f92  jle     short loc_180031F9D
0x180031f94  movzx   ebx, ax
0x180031f97  or      ebx, 80070000h
0x180031f9d  lea     rdx, aFailedToGetPro; "Failed to get process token: 0x%08X"
0x180031fa4  mov     r8d, ebx
0x180031fa7  mov     ecx, ebp; unsigned __int8
0x180031fa9  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180031fae  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180031fb3  lea     rdx, [rcx-1]
0x180031fb7  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180031fbb  ja      short loc_180031FC3
0x180031fbd  call    cs:__imp_CloseHandle
0x180031fc3  mov     eax, ebx
0x180031fc5  jmp     loc_180032085
0x180031fca  mov     rsi, [rdi]
0x180031fcd  lea     rax, [rsi-1]
0x180031fd1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180031fd5  ja      short loc_180031FF0
0x180031fd7  call    cs:__imp_GetLastError
0x180031fdd  mov     rcx, rsi; hObject
0x180031fe0  mov     ebx, eax
0x180031fe2  call    cs:__imp_CloseHandle
0x180031fe8  mov     ecx, ebx; dwErrCode
0x180031fea  call    cs:__imp_SetLastError
0x180031ff0  mov     rcx, [rsp+58h+TokenHandle]; hExistingToken
0x180031ff5  xor     r8d, r8d; lpTokenAttributes
0x180031ff8  mov     [rsp+58h+phNewToken], rdi; phNewToken
0x180031ffd  mov     r9d, ebp; ImpersonationLevel
0x180032000  mov     qword ptr [rdi], 0
0x180032007  mov     [rsp+58h+TokenType], ebp; TokenType
0x18003200b  lea     edx, [r8+2Ch]; dwDesiredAccess
0x18003200f  call    cs:__imp_DuplicateTokenEx
0x180032015  test    eax, eax
0x180032017  jnz     short loc_18003203A
0x180032019  call    cs:__imp_GetLastError
0x18003201f  mov     ebx, eax
0x180032021  test    eax, eax
0x180032023  jle     short loc_18003202E
0x180032025  movzx   ebx, ax
0x180032028  or      ebx, 80070000h
0x18003202e  lea     rdx, aFailedToDuplic; "Failed to duplicate token! hr = 0x%08x"
0x180032035  jmp     loc_180031FA4
0x18003203a  mov     rdx, [rdi]; Token
0x18003203d  xor     ecx, ecx; Thread
0x18003203f  call    cs:__imp_SetThreadToken
0x180032045  test    eax, eax
0x180032047  jnz     short loc_18003206A
0x180032049  call    cs:__imp_GetLastError
0x18003204f  mov     ebx, eax
0x180032051  test    eax, eax
0x180032053  jle     short loc_18003205E
0x180032055  movzx   ebx, ax
0x180032058  or      ebx, 80070000h
0x18003205e  lea     rdx, aFailedToSetThe_0; "Failed to set the thread token: 0x%08X"
0x180032065  jmp     loc_180031FA4
0x18003206a  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18003206f  mov     byte ptr [rdi+8], 1
0x180032073  lea     rax, [rcx-1]
0x180032077  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003207b  ja      short loc_180032083
0x18003207d  call    cs:__imp_CloseHandle
0x180032083  xor     eax, eax
0x180032085  add     rsp, 38h
0x180032089  pop     rdi
0x18003208a  pop     rsi
0x18003208b  pop     rbp
0x18003208c  pop     rbx
0x18003208d  retn
```
