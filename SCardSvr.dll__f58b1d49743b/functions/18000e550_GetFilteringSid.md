# GetFilteringSid

- ea: `0x18000e550`
- end: `0x18000e7de`
- name: `GetFilteringSid`
- size: `654`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dca0`

## callees

- `0x18000e550`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e703`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e703`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e660`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e6c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e660`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e6c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e64f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e6b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e6f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e64f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e6b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e6f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e75b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e78f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e79c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e75b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e78f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e79c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e5a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000e5a3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e5bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000e5bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e722`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e722`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e6df`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e6df`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000e5db`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000e5f6`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000e5db`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000e5f6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e63a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e694`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e63a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e694`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e6aa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e6aa`
- `RPCRT4!RpcImpersonateClient` at `0x18000e590`
- `RPCRT4!RpcImpersonateClient` at `0x18000e590`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000e74b`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000e74b`

## pseudocode

```c
__int64 __fastcall GetFilteringSid(RPC_BINDING_HANDLE BindingHandle, _QWORD *a2)
{
  char v3; // si
  PSID *v4; // rdi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  DWORD v8; // edi
  HANDLE ProcessHeap; // rax
  PSID *v10; // r14
  DWORD LengthSid; // r12d
  HANDLE v12; // rax
  void *v13; // rax
  void *v14; // rdi
  HANDLE v15; // rax
  RPC_STATUS v17; // eax
  HANDLE v18; // rax
  WINBOOL v19; // [rsp+30h] [rbp-48h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-40h] BYREF
  DWORD TokenInformationLength; // [rsp+90h] [rbp+18h] BYREF
  WINBOOL IsMember; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  v4 = (PSID *)qword_18004BFA0;
  TokenHandle = 0;
  IsMember = 0;
  v19 = 0;
  TokenInformationLength = 0;
  LastError = RpcImpersonateClient(BindingHandle);
  if ( !LastError )
  {
    v3 = 1;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) && CheckTokenMembership(TokenHandle, v4[1], &IsMember) )
    {
      if ( CheckTokenMembership(TokenHandle, *v4, &v19) )
      {
        if ( IsMember || v19 )
        {
          *a2 = 0;
        }
        else
        {
          if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
          {
            LastError = GetLastError();
            if ( LastError != 122 )
              goto LABEL_14;
            LastError = 0;
          }
          v8 = TokenInformationLength;
          ProcessHeap = GetProcessHeap();
          v10 = (PSID *)HeapAlloc(ProcessHeap, 8u, v8);
          if ( v10 )
          {
            if ( GetTokenInformation(TokenHandle, TokenUser, v10, TokenInformationLength, &TokenInformationLength) )
            {
              LengthSid = GetLengthSid(*v10);
              v12 = GetProcessHeap();
              v13 = HeapAlloc(v12, 8u, LengthSid);
              v14 = v13;
              if ( v13 )
              {
                if ( CopySid(LengthSid, v13, *v10) )
                {
                  *a2 = v14;
                }
                else
                {
                  LastError = GetLastError();
                  v18 = GetProcessHeap();
                  HeapFree(v18, 0, v14);
                }
              }
              else
              {
                LastError = -2146435066;
              }
            }
            else
            {
              LastError = GetLastError();
            }
            v15 = GetProcessHeap();
            HeapFree(v15, 0, v10);
          }
          else
          {
            LastError = -2146435066;
          }
        }
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = GetLastError();
    }
  }
LABEL_14:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v3 )
  {
    v17 = RpcRevertToSelfEx(BindingHandle);
    if ( v17 )
      __fastfail(v17);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000e550  mov     rax, rsp
0x18000e553  push    rbx
0x18000e554  push    rbp
0x18000e555  sub     rsp, 68h
0x18000e559  mov     [rax+8], rsi
0x18000e55d  mov     rbp, rcx
0x18000e560  mov     [rax-18h], rdi
0x18000e564  xor     sil, sil
0x18000e567  mov     rdi, cs:qword_18004BFA0
0x18000e56e  mov     [rax-28h], r13
0x18000e572  xor     r13d, r13d
0x18000e575  mov     [rax-30h], r14
0x18000e579  mov     [rax-38h], r15
0x18000e57d  mov     r15, rdx
0x18000e580  mov     [rax-40h], r13
0x18000e584  mov     [rax+20h], r13d
0x18000e588  mov     [rax-48h], r13d
0x18000e58c  mov     [rax+18h], r13d
0x18000e590  call    cs:__imp_RpcImpersonateClient
0x18000e596  mov     ebx, eax
0x18000e598  test    eax, eax
0x18000e59a  jnz     loc_18000E709
0x18000e5a0  mov     sil, 1
0x18000e5a3  call    cs:__imp_GetCurrentThread
0x18000e5a9  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x18000e5ae  mov     edx, 8; DesiredAccess
0x18000e5b3  mov     rcx, rax; ThreadHandle
0x18000e5b6  mov     r8d, 1; OpenAsSelf
0x18000e5bc  call    cs:__imp_OpenThreadToken
0x18000e5c2  test    eax, eax
0x18000e5c4  jz      loc_18000E782
0x18000e5ca  mov     rdx, [rdi+8]; SidToCheck
0x18000e5ce  lea     r8, [rsp+78h+IsMember]; IsMember
0x18000e5d6  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x18000e5db  call    cs:__imp_CheckTokenMembership
0x18000e5e1  test    eax, eax
0x18000e5e3  jz      loc_18000E78F
0x18000e5e9  mov     rdx, [rdi]; SidToCheck
0x18000e5ec  lea     r8, [rsp+78h+var_48]; IsMember
0x18000e5f1  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x18000e5f6  call    cs:__imp_CheckTokenMembership
0x18000e5fc  test    eax, eax
0x18000e5fe  jz      loc_18000E79C
0x18000e604  cmp     [rsp+78h+IsMember], r13d
0x18000e60c  jnz     loc_18000E77D
0x18000e612  cmp     [rsp+78h+var_48], r13d
0x18000e617  jnz     loc_18000E77D
0x18000e61d  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x18000e622  lea     rax, [rsp+78h+TokenInformationLength]
0x18000e62a  xor     r9d, r9d; TokenInformationLength
0x18000e62d  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18000e632  xor     r8d, r8d; TokenInformation
0x18000e635  mov     edx, 1; TokenInformationClass
0x18000e63a  call    cs:__imp_GetTokenInformation
0x18000e640  test    eax, eax
0x18000e642  jz      loc_18000E75B
0x18000e648  mov     edi, [rsp+78h+TokenInformationLength]
0x18000e64f  call    cs:__imp_GetProcessHeap
0x18000e655  mov     r8d, edi; dwBytes
0x18000e658  mov     edx, 8; dwFlags
0x18000e65d  mov     rcx, rax; hHeap
0x18000e660  call    cs:__imp_HeapAlloc
0x18000e666  mov     r14, rax
0x18000e669  test    rax, rax
0x18000e66c  jz      loc_18000E7A9
0x18000e672  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x18000e67a  lea     rax, [rsp+78h+TokenInformationLength]
0x18000e682  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x18000e687  mov     r8, r14; TokenInformation
0x18000e68a  mov     edx, 1; TokenInformationClass
0x18000e68f  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18000e694  call    cs:__imp_GetTokenInformation
0x18000e69a  test    eax, eax
0x18000e69c  jz      loc_18000E770
0x18000e6a2  mov     rcx, [r14]; pSid
0x18000e6a5  mov     [rsp+78h+var_20], r12
0x18000e6aa  call    cs:__imp_GetLengthSid
0x18000e6b0  mov     r12d, eax
0x18000e6b3  call    cs:__imp_GetProcessHeap
0x18000e6b9  mov     r8d, r12d; dwBytes
0x18000e6bc  mov     edx, 8; dwFlags
0x18000e6c1  mov     rcx, rax; hHeap
0x18000e6c4  call    cs:__imp_HeapAlloc
0x18000e6ca  mov     rdi, rax
0x18000e6cd  test    rax, rax
0x18000e6d0  jz      loc_18000E7B3
0x18000e6d6  mov     r8, [r14]; pSourceSid
0x18000e6d9  mov     rdx, rax; pDestinationSid
0x18000e6dc  mov     ecx, r12d; nDestinationSidLength
0x18000e6df  call    cs:__imp_CopySid
0x18000e6e5  test    eax, eax
0x18000e6e7  jz      loc_18000E7BD
0x18000e6ed  mov     [r15], rdi
0x18000e6f0  mov     r12, [rsp+78h+var_20]
0x18000e6f5  call    cs:__imp_GetProcessHeap
0x18000e6fb  mov     r8, r14; lpMem
0x18000e6fe  xor     edx, edx; dwFlags
0x18000e700  mov     rcx, rax; hHeap
0x18000e703  call    cs:__imp_HeapFree
0x18000e709  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x18000e70e  mov     r15, [rsp+78h+var_38]
0x18000e713  mov     r14, [rsp+78h+var_30]
0x18000e718  mov     rdi, [rsp+78h+var_18]
0x18000e71d  test    rcx, rcx
0x18000e720  jz      short loc_18000E72D
0x18000e722  call    cs:__imp_CloseHandle
0x18000e728  mov     [rsp+78h+TokenHandle], r13
0x18000e72d  mov     r13, [rsp+78h+var_28]
0x18000e732  test    sil, sil
0x18000e735  mov     rsi, [rsp+78h+arg_0]
0x18000e73d  jnz     short loc_18000E748
0x18000e73f  mov     eax, ebx
0x18000e741  add     rsp, 68h
0x18000e745  pop     rbp
0x18000e746  pop     rbx
0x18000e747  retn
0x18000e748  mov     rcx, rbp; BindingHandle
0x18000e74b  call    cs:__imp_RpcRevertToSelfEx
0x18000e751  test    eax, eax
0x18000e753  jz      short loc_18000E73F
0x18000e755  mov     ecx, eax
0x18000e757  int     29h; Win8: RtlFailFast(ecx)
0x18000e759  jmp     short loc_18000E73F
0x18000e75b  call    cs:__imp_GetLastError
0x18000e761  mov     ebx, eax
0x18000e763  cmp     eax, 7Ah ; 'z'
0x18000e766  jnz     short loc_18000E709
0x18000e768  mov     ebx, r13d
0x18000e76b  jmp     loc_18000E648
0x18000e770  call    cs:__imp_GetLastError
0x18000e776  mov     ebx, eax
0x18000e778  jmp     loc_18000E6F5
0x18000e77d  mov     [r15], r13
0x18000e780  jmp     short loc_18000E709
0x18000e782  call    cs:__imp_GetLastError
0x18000e788  mov     ebx, eax
0x18000e78a  jmp     loc_18000E709
0x18000e78f  call    cs:__imp_GetLastError
0x18000e795  mov     ebx, eax
0x18000e797  jmp     loc_18000E709
0x18000e79c  call    cs:__imp_GetLastError
0x18000e7a2  mov     ebx, eax
0x18000e7a4  jmp     loc_18000E709
0x18000e7a9  mov     ebx, 80100006h
0x18000e7ae  jmp     loc_18000E709
0x18000e7b3  mov     ebx, 80100006h
0x18000e7b8  jmp     loc_18000E6F0
0x18000e7bd  call    cs:__imp_GetLastError
0x18000e7c3  mov     ebx, eax
0x18000e7c5  call    cs:__imp_GetProcessHeap
0x18000e7cb  mov     r8, rdi; lpMem
0x18000e7ce  xor     edx, edx; dwFlags
0x18000e7d0  mov     rcx, rax; hHeap
0x18000e7d3  call    cs:__imp_HeapFree
0x18000e7d9  jmp     loc_18000E6F0
```
