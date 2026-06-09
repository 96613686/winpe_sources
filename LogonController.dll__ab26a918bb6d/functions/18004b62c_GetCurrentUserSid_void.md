# GetCurrentUserSid(void * *)

- ea: `0x18004b62c`
- end: `0x18004b76a`
- name: `?GetCurrentUserSid@@YA_NPEAPEAX@Z`
- size: `318`
- prototype: `bool __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005500`

## callees

- `0x18004b62c`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18004b6b2`
- `KERNEL32!LocalAlloc` at `0x18004b70e`
- `KERNEL32!LocalAlloc` at `0x18004b6b2`
- `KERNEL32!LocalAlloc` at `0x18004b70e`
- `KERNEL32!LocalFree` at `0x18004b6e6`
- `KERNEL32!LocalFree` at `0x18004b732`
- `KERNEL32!LocalFree` at `0x18004b73f`
- `KERNEL32!LocalFree` at `0x18004b74f`
- `KERNEL32!LocalFree` at `0x18004b6e6`
- `KERNEL32!LocalFree` at `0x18004b732`
- `KERNEL32!LocalFree` at `0x18004b73f`
- `KERNEL32!LocalFree` at `0x18004b74f`
- `KERNEL32!CloseHandle` at `0x18004b69f`
- `KERNEL32!CloseHandle` at `0x18004b6f2`
- `KERNEL32!CloseHandle` at `0x18004b69f`
- `KERNEL32!CloseHandle` at `0x18004b6f2`
- `KERNEL32!GetLastError` at `0x18004b690`
- `KERNEL32!GetLastError` at `0x18004b690`
- `KERNEL32!GetCurrentProcess` at `0x18004b653`
- `KERNEL32!GetCurrentProcess` at `0x18004b653`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004b665`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004b665`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004b725`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004b725`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004b68a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004b6d9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004b68a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004b6d9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004b6fe`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004b6fe`

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
0x18004b62c  mov     [rsp-18h+arg_0], rbx
0x18004b631  mov     [rsp-18h+arg_18], rsi
0x18004b636  push    rbp
0x18004b637  push    rdi
0x18004b638  push    r14
0x18004b63a  mov     rbp, rsp
0x18004b63d  sub     rsp, 30h
0x18004b641  mov     rdi, rcx
0x18004b644  mov     [rbp+TokenInformationLength], 0
0x18004b64b  mov     [rbp+TokenHandle], 0
0x18004b653  call    cs:__imp_GetCurrentProcess
0x18004b659  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18004b65d  mov     edx, 8; DesiredAccess
0x18004b662  mov     rcx, rax; ProcessHandle
0x18004b665  call    cs:__imp_OpenProcessToken
0x18004b66b  test    eax, eax
0x18004b66d  jz      loc_18004B755
0x18004b673  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004b677  lea     rax, [rbp+TokenInformationLength]
0x18004b67b  xor     r9d, r9d; TokenInformationLength
0x18004b67e  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18004b683  xor     r8d, r8d; TokenInformation
0x18004b686  lea     edx, [r9+1]; TokenInformationClass
0x18004b68a  call    cs:__imp_GetTokenInformation
0x18004b690  call    cs:__imp_GetLastError
0x18004b696  cmp     eax, 7Ah ; 'z'
0x18004b699  jz      short loc_18004B6AA
0x18004b69b  mov     rcx, [rbp+TokenHandle]; hObject
0x18004b69f  call    cs:__imp_CloseHandle
0x18004b6a5  jmp     loc_18004B755
0x18004b6aa  mov     edx, [rbp+TokenInformationLength]; uBytes
0x18004b6ad  mov     ecx, 40h ; '@'; uFlags
0x18004b6b2  call    cs:__imp_LocalAlloc
0x18004b6b8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004b6bc  mov     rbx, rax
0x18004b6bf  test    rax, rax
0x18004b6c2  jz      short loc_18004B69F
0x18004b6c4  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18004b6c8  lea     rax, [rbp+TokenInformationLength]
0x18004b6cc  mov     r8, rbx; TokenInformation
0x18004b6cf  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18004b6d4  mov     edx, 1; TokenInformationClass
0x18004b6d9  call    cs:__imp_GetTokenInformation
0x18004b6df  test    eax, eax
0x18004b6e1  jnz     short loc_18004B6EE
0x18004b6e3  mov     rcx, rbx; hMem
0x18004b6e6  call    cs:__imp_LocalFree
0x18004b6ec  jmp     short loc_18004B69B
0x18004b6ee  mov     rcx, [rbp+TokenHandle]; hObject
0x18004b6f2  call    cs:__imp_CloseHandle
0x18004b6f8  mov     rsi, [rbx]
0x18004b6fb  mov     rcx, rsi; pSid
0x18004b6fe  call    cs:__imp_GetLengthSid
0x18004b704  mov     edx, eax; uBytes
0x18004b706  mov     ecx, 40h ; '@'; uFlags
0x18004b70b  mov     r14d, eax
0x18004b70e  call    cs:__imp_LocalAlloc
0x18004b714  mov     [rdi], rax
0x18004b717  test    rax, rax
0x18004b71a  jz      short loc_18004B73C
0x18004b71c  mov     r8, rsi; pSourceSid
0x18004b71f  mov     rdx, rax; pDestinationSid
0x18004b722  mov     ecx, r14d; nDestinationSidLength
0x18004b725  call    cs:__imp_CopySid
0x18004b72b  test    eax, eax
0x18004b72d  jz      short loc_18004B73C
0x18004b72f  mov     rcx, rbx; hMem
0x18004b732  call    cs:__imp_LocalFree
0x18004b738  mov     al, 1
0x18004b73a  jmp     short loc_18004B757
0x18004b73c  mov     rcx, [rdi]; hMem
0x18004b73f  call    cs:__imp_LocalFree
0x18004b745  mov     rcx, rbx; hMem
0x18004b748  mov     qword ptr [rdi], 0
0x18004b74f  call    cs:__imp_LocalFree
0x18004b755  xor     al, al
0x18004b757  mov     rbx, [rsp+30h+arg_0]
0x18004b75c  mov     rsi, [rsp+30h+arg_18]
0x18004b761  add     rsp, 30h
0x18004b765  pop     r14
0x18004b767  pop     rdi
0x18004b768  pop     rbp
0x18004b769  retn
```
