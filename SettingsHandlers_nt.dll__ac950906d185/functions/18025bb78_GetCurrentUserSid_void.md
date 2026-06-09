# GetCurrentUserSid(void * *)

- ea: `0x18025bb78`
- end: `0x18025bd11`
- name: `?GetCurrentUserSid@@YA_NPEAPEAX@Z`
- size: `409`
- prototype: `bool __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18025bee8`

## callees

- `0x18025bb78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18025bb9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18025bb9f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18025bbb7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18025bbb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18025bbee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18025bbee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18025bc03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18025bc6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18025bc03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18025bc6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18025bc1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18025bc96`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18025bc1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18025bc96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025bc5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025bcc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025bcd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025bcef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025bc5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025bcc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025bcd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18025bcef`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18025bcb3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18025bcb3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18025bc80`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18025bc80`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18025bbe2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18025bc49`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18025bbe2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18025bc49`

## pseudocode

```c
char __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentProcess; // rax
  void *v3; // rcx
  PSID *v4; // rax
  PSID *v5; // rbx
  PSID v6; // rsi
  DWORD LengthSid; // r14d
  HLOCAL v8; // rax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  TokenInformationLength = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    return 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( GetLastError() != 122 )
    goto LABEL_3;
  v4 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
  v3 = TokenHandle;
  v5 = v4;
  if ( !v4 )
    goto LABEL_4;
  if ( !GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
  {
    LocalFree(v5);
LABEL_3:
    v3 = TokenHandle;
LABEL_4:
    CloseHandle(v3);
    return 0;
  }
  CloseHandle(TokenHandle);
  v6 = *v5;
  LengthSid = GetLengthSid(*v5);
  v8 = LocalAlloc(0x40u, LengthSid);
  *a1 = v8;
  if ( v8 && CopySid(LengthSid, v8, v6) )
  {
    LocalFree(v5);
    return 1;
  }
  LocalFree(*a1);
  *a1 = 0;
  LocalFree(v5);
  return 0;
}

```

## disassembly

```asm
0x18025bb78  mov     [rsp-18h+arg_0], rbx
0x18025bb7d  mov     [rsp-18h+arg_18], rsi
0x18025bb82  push    rbp
0x18025bb83  push    rdi
0x18025bb84  push    r14
0x18025bb86  mov     rbp, rsp
0x18025bb89  sub     rsp, 30h
0x18025bb8d  mov     rdi, rcx
0x18025bb90  mov     [rbp+TokenInformationLength], 0
0x18025bb97  mov     [rbp+TokenHandle], 0
0x18025bb9f  call    cs:__imp_GetCurrentProcess
0x18025bba6  nop     dword ptr [rax+rax+00h]
0x18025bbab  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18025bbaf  mov     edx, 8; DesiredAccess
0x18025bbb4  mov     rcx, rax; ProcessHandle
0x18025bbb7  call    cs:__imp_OpenProcessToken
0x18025bbbe  nop     dword ptr [rax+rax+00h]
0x18025bbc3  test    eax, eax
0x18025bbc5  jz      loc_18025BCFB
0x18025bbcb  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18025bbcf  lea     rax, [rbp+TokenInformationLength]
0x18025bbd3  xor     r9d, r9d; TokenInformationLength
0x18025bbd6  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18025bbdb  xor     r8d, r8d; TokenInformation
0x18025bbde  lea     edx, [r9+1]; TokenInformationClass
0x18025bbe2  call    cs:__imp_GetTokenInformation
0x18025bbe9  nop     dword ptr [rax+rax+00h]
0x18025bbee  call    cs:__imp_GetLastError
0x18025bbf5  nop     dword ptr [rax+rax+00h]
0x18025bbfa  cmp     eax, 7Ah ; 'z'
0x18025bbfd  jz      short loc_18025BC14
0x18025bbff  mov     rcx, [rbp+TokenHandle]; hObject
0x18025bc03  call    cs:__imp_CloseHandle
0x18025bc0a  nop     dword ptr [rax+rax+00h]
0x18025bc0f  jmp     loc_18025BCFB
0x18025bc14  mov     edx, [rbp+TokenInformationLength]; uBytes
0x18025bc17  mov     ecx, 40h ; '@'; uFlags
0x18025bc1c  call    cs:__imp_LocalAlloc
0x18025bc23  nop     dword ptr [rax+rax+00h]
0x18025bc28  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18025bc2c  mov     rbx, rax
0x18025bc2f  test    rax, rax
0x18025bc32  jz      short loc_18025BC03
0x18025bc34  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18025bc38  lea     rax, [rbp+TokenInformationLength]
0x18025bc3c  mov     r8, rbx; TokenInformation
0x18025bc3f  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18025bc44  mov     edx, 1; TokenInformationClass
0x18025bc49  call    cs:__imp_GetTokenInformation
0x18025bc50  nop     dword ptr [rax+rax+00h]
0x18025bc55  test    eax, eax
0x18025bc57  jnz     short loc_18025BC6A
0x18025bc59  mov     rcx, rbx; hMem
0x18025bc5c  call    cs:__imp_LocalFree
0x18025bc63  nop     dword ptr [rax+rax+00h]
0x18025bc68  jmp     short loc_18025BBFF
0x18025bc6a  mov     rcx, [rbp+TokenHandle]; hObject
0x18025bc6e  call    cs:__imp_CloseHandle
0x18025bc75  nop     dword ptr [rax+rax+00h]
0x18025bc7a  mov     rsi, [rbx]
0x18025bc7d  mov     rcx, rsi; pSid
0x18025bc80  call    cs:__imp_GetLengthSid
0x18025bc87  nop     dword ptr [rax+rax+00h]
0x18025bc8c  mov     edx, eax; uBytes
0x18025bc8e  mov     ecx, 40h ; '@'; uFlags
0x18025bc93  mov     r14d, eax
0x18025bc96  call    cs:__imp_LocalAlloc
0x18025bc9d  nop     dword ptr [rax+rax+00h]
0x18025bca2  mov     [rdi], rax
0x18025bca5  test    rax, rax
0x18025bca8  jz      short loc_18025BCD6
0x18025bcaa  mov     r8, rsi; pSourceSid
0x18025bcad  mov     rdx, rax; pDestinationSid
0x18025bcb0  mov     ecx, r14d; nDestinationSidLength
0x18025bcb3  call    cs:__imp_CopySid
0x18025bcba  nop     dword ptr [rax+rax+00h]
0x18025bcbf  test    eax, eax
0x18025bcc1  jz      short loc_18025BCD6
0x18025bcc3  mov     rcx, rbx; hMem
0x18025bcc6  call    cs:__imp_LocalFree
0x18025bccd  nop     dword ptr [rax+rax+00h]
0x18025bcd2  mov     al, 1
0x18025bcd4  jmp     short loc_18025BCFD
0x18025bcd6  mov     rcx, [rdi]; hMem
0x18025bcd9  call    cs:__imp_LocalFree
0x18025bce0  nop     dword ptr [rax+rax+00h]
0x18025bce5  mov     rcx, rbx; hMem
0x18025bce8  mov     qword ptr [rdi], 0
0x18025bcef  call    cs:__imp_LocalFree
0x18025bcf6  nop     dword ptr [rax+rax+00h]
0x18025bcfb  xor     al, al
0x18025bcfd  mov     rbx, [rsp+30h+arg_0]
0x18025bd02  mov     rsi, [rsp+30h+arg_18]
0x18025bd07  add     rsp, 30h
0x18025bd0b  pop     r14
0x18025bd0d  pop     rdi
0x18025bd0e  pop     rbp
0x18025bd0f  retn
```
