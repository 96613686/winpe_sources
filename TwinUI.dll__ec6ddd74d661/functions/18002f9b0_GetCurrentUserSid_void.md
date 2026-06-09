# GetCurrentUserSid(void * *)

- ea: `0x18002f9b0`
- end: `0x18002fb85`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `469`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002f86c`
- `0x180042adc`

## callees

- `0x18002f9b0`
- `0x18002fc18`
- `0x180142e10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f9ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f9ea`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002fa0b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002fa0b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002fb2a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002fb2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002fb14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002fb14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002facf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002facf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fb60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002fb60`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fa95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002fa95`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002fa7b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002fa7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002fa40`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002fa40`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002fab1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002fab1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002fa68`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002fa68`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  void *v3; // rsi
  int Error; // ebx
  void *v5; // rcx
  DWORD LengthSid; // ebp
  HLOCAL v7; // rax
  void *v8; // rdi
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-98h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-90h] BYREF
  void *TokenInformation; // [rsp+40h] [rbp-88h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_2;
  Error = ResultFromKnownLastError();
  if ( Error == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_2;
    Error = ResultFromKnownLastError();
  }
  if ( Error < 0 )
    return (unsigned int)Error;
LABEL_2:
  ReturnLength = 88;
  if ( !GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x58u, &ReturnLength) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_8;
  }
  v3 = TokenInformation;
  Error = -2147024809;
  v5 = TokenInformation;
  *a1 = 0;
  if ( !IsValidSid(v5) )
    goto LABEL_8;
  LengthSid = GetLengthSid(v3);
  Error = -2147024882;
  v7 = LocalAlloc(0x40u, LengthSid);
  v8 = v7;
  if ( !v7 )
    goto LABEL_8;
  if ( CopySid(LengthSid, v7, v3) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      LocalFree(v8);
      goto LABEL_8;
    }
  }
  *a1 = v8;
LABEL_8:
  CloseHandle(TokenHandle);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002f9b0  mov     [rsp+arg_8], rbx
0x18002f9b5  mov     [rsp+arg_10], rbp
0x18002f9ba  push    rsi
0x18002f9bb  push    rdi
0x18002f9bc  push    r14
0x18002f9be  sub     rsp, 0B0h
0x18002f9c5  mov     rax, cs:__security_cookie
0x18002f9cc  xor     rax, rsp
0x18002f9cf  mov     [rsp+0C8h+var_28], rax
0x18002f9d7  mov     r14, rcx
0x18002f9da  mov     qword ptr [rcx], 0
0x18002f9e1  mov     [rsp+0C8h+TokenHandle], 0
0x18002f9ea  call    cs:__imp_GetCurrentThread
0x18002f9f1  nop     dword ptr [rax+rax+00h]
0x18002f9f6  mov     esi, 1
0x18002f9fb  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x18002fa00  mov     rcx, rax; ThreadHandle
0x18002fa03  mov     r8d, esi; OpenAsSelf
0x18002fa06  lea     edi, [rsi+7]
0x18002fa09  mov     edx, edi; DesiredAccess
0x18002fa0b  call    cs:__imp_OpenThreadToken
0x18002fa12  nop     dword ptr [rax+rax+00h]
0x18002fa17  test    eax, eax
0x18002fa19  jz      loc_18002FB06
0x18002fa1f  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x18002fa24  lea     rax, [rsp+0C8h+var_90]
0x18002fa29  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18002fa2f  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x18002fa34  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x18002fa39  mov     [rsp+0C8h+var_90], r9d
0x18002fa3e  mov     edx, esi; TokenInformationClass
0x18002fa40  call    cs:__imp_GetTokenInformation
0x18002fa47  nop     dword ptr [rax+rax+00h]
0x18002fa4c  test    eax, eax
0x18002fa4e  jz      loc_18002FB71
0x18002fa54  mov     rsi, [rsp+0C8h+TokenInformation]
0x18002fa59  mov     ebx, 80070057h
0x18002fa5e  mov     rcx, rsi; pSid
0x18002fa61  mov     qword ptr [r14], 0
0x18002fa68  call    cs:__imp_IsValidSid
0x18002fa6f  nop     dword ptr [rax+rax+00h]
0x18002fa74  test    eax, eax
0x18002fa76  jz      short loc_18002FACA
0x18002fa78  mov     rcx, rsi; pSid
0x18002fa7b  call    cs:__imp_GetLengthSid
0x18002fa82  nop     dword ptr [rax+rax+00h]
0x18002fa87  mov     edx, eax; uBytes
0x18002fa89  mov     ecx, 40h ; '@'; uFlags
0x18002fa8e  mov     ebp, eax
0x18002fa90  mov     ebx, 8007000Eh
0x18002fa95  call    cs:__imp_LocalAlloc
0x18002fa9c  nop     dword ptr [rax+rax+00h]
0x18002faa1  mov     rdi, rax
0x18002faa4  test    rax, rax
0x18002faa7  jz      short loc_18002FACA
0x18002faa9  mov     r8, rsi; pSourceSid
0x18002faac  mov     rdx, rax; pDestinationSid
0x18002faaf  mov     ecx, ebp; nDestinationSidLength
0x18002fab1  call    cs:__imp_CopySid
0x18002fab8  nop     dword ptr [rax+rax+00h]
0x18002fabd  test    eax, eax
0x18002fabf  jz      loc_18002FB4E
0x18002fac5  xor     ebx, ebx
0x18002fac7  mov     [r14], rdi
0x18002faca  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x18002facf  call    cs:__imp_CloseHandle
0x18002fad6  nop     dword ptr [rax+rax+00h]
0x18002fadb  mov     eax, ebx
0x18002fadd  mov     rcx, [rsp+0C8h+var_28]
0x18002fae5  xor     rcx, rsp; StackCookie
0x18002fae8  call    __security_check_cookie
0x18002faed  lea     r11, [rsp+0C8h+var_18]
0x18002faf5  mov     rbx, [r11+28h]
0x18002faf9  mov     rbp, [r11+30h]
0x18002fafd  mov     rsp, r11
0x18002fb00  pop     r14
0x18002fb02  pop     rdi
0x18002fb03  pop     rsi
0x18002fb04  retn
0x18002fb06  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002fb0b  mov     ebx, eax
0x18002fb0d  cmp     eax, 800703F0h
0x18002fb12  jnz     short loc_18002FB45
0x18002fb14  call    cs:__imp_GetCurrentProcess
0x18002fb1b  nop     dword ptr [rax+rax+00h]
0x18002fb20  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x18002fb25  mov     edx, edi; DesiredAccess
0x18002fb27  mov     rcx, rax; ProcessHandle
0x18002fb2a  call    cs:__imp_OpenProcessToken
0x18002fb31  nop     dword ptr [rax+rax+00h]
0x18002fb36  test    eax, eax
0x18002fb38  jnz     loc_18002FA1F
0x18002fb3e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002fb43  mov     ebx, eax
0x18002fb45  test    ebx, ebx
0x18002fb47  js      short loc_18002FADB
0x18002fb49  jmp     loc_18002FA1F
0x18002fb4e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002fb53  mov     ebx, eax
0x18002fb55  test    eax, eax
0x18002fb57  jns     loc_18002FAC7
0x18002fb5d  mov     rcx, rdi; hMem
0x18002fb60  call    cs:__imp_LocalFree
0x18002fb67  nop     dword ptr [rax+rax+00h]
0x18002fb6c  jmp     loc_18002FACA
0x18002fb71  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002fb76  mov     ebx, eax
0x18002fb78  test    eax, eax
0x18002fb7a  js      loc_18002FACA
0x18002fb80  jmp     loc_18002FA54
```
