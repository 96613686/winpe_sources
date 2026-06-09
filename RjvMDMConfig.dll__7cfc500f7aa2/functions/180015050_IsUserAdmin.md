# IsUserAdmin

- ea: `0x180015050`
- end: `0x18001524a`
- name: `IsUserAdmin`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014f14`

## callees

- `0x180001c60`
- `0x1800038c0`
- `0x1800055f4`
- `0x1800129c4`
- `0x180012a0c`
- `0x180015050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800150f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800150f4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001510e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001510e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015170`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015170`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800151f2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800151f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015137`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001519e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180015137`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001519e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800150c6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800150c6`

## pseudocode

```c
__int64 __fastcall IsUserAdmin(_DWORD *a1)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  DWORD *v4; // rbx
  DWORD v5; // edi
  DWORD v6; // esi
  DWORD ReturnLength; // [rsp+60h] [rbp-9h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-1h] BYREF
  PSID pSid1; // [rsp+70h] [rbp+7h] BYREF
  DWORD *v11; // [rsp+78h] [rbp+Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp+17h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *a1 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid1 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid1) || !pSid1 )
    goto LABEL_18;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    ReturnLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &ReturnLength) || GetLastError() == 122 )
    {
      v11 = (DWORD *)LocalAlloc(0x40u, ReturnLength);
      v4 = v11;
      if ( !v11 || !GetTokenInformation(TokenHandle, TokenGroups, v11, ReturnLength, &ReturnLength) )
      {
        LastError = GetLastError();
        CLocalMemPtr<_TOKEN_GROUPS>::~CLocalMemPtr<_TOKEN_GROUPS>(&v11);
        goto LABEL_10;
      }
      v5 = 0;
      v6 = (ReturnLength - 8) >> 4;
      while ( v5 < *v4 && v5 < v6 )
      {
        if ( EqualSid(pSid1, *(PSID *)&v4[4 * v5 + 2]) )
        {
          *a1 = 1;
          break;
        }
        ++v5;
      }
      CLocalMemPtr<_TOKEN_GROUPS>::~CLocalMemPtr<_TOKEN_GROUPS>(&v11);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_18:
      LastError = 0;
      goto LABEL_19;
    }
  }
  LastError = GetLastError();
LABEL_10:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_19:
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid1);
  return LastError;
}

```

## disassembly

```asm
0x180015050  push    rbp
0x180015052  push    rbx
0x180015053  push    rsi
0x180015054  push    rdi
0x180015055  push    r14
0x180015057  push    r15
0x180015059  lea     rbp, [rsp-2Fh]
0x18001505e  sub     rsp, 98h
0x180015065  mov     rax, cs:__security_cookie
0x18001506c  xor     rax, rsp
0x18001506f  mov     [rbp+57h+var_38], rax
0x180015073  xor     r15d, r15d
0x180015076  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001507c  lea     rax, [rbp+57h+pSid1]
0x180015080  mov     [rcx], r15d
0x180015083  mov     [rsp+0C0h+pSid], rax; pSid
0x180015088  mov     r14, rcx
0x18001508b  mov     [rsp+0C0h+nSubAuthority7], r15d; nSubAuthority7
0x180015090  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180015094  mov     [rsp+0C0h+nSubAuthority6], r15d; nSubAuthority6
0x180015099  lea     edi, [r15+2]
0x18001509d  mov     [rsp+0C0h+nSubAuthority5], r15d; nSubAuthority5
0x1800150a2  lea     r8d, [r15+20h]; nSubAuthority0
0x1800150a6  mov     [rsp+0C0h+nSubAuthority4], r15d; nSubAuthority4
0x1800150ab  mov     dl, dil; nSubAuthorityCount
0x1800150ae  mov     [rsp+0C0h+nSubAuthority3], r15d; nSubAuthority3
0x1800150b3  mov     r9d, 220h; nSubAuthority1
0x1800150b9  mov     [rsp+0C0h+nSubAuthority2], r15d; nSubAuthority2
0x1800150be  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x1800150c2  mov     [rbp+57h+pSid1], r15
0x1800150c6  call    cs:__imp_AllocateAndInitializeSid
0x1800150cd  nop     dword ptr [rax+rax+00h]
0x1800150d2  cmp     eax, 1
0x1800150d5  jnz     loc_18001521F
0x1800150db  cmp     [rbp+57h+pSid1], r15
0x1800150df  jz      loc_18001521F
0x1800150e5  xor     edx, edx
0x1800150e7  mov     [rbp+57h+TokenHandle], r15
0x1800150eb  lea     rcx, [rbp+57h+TokenHandle]
0x1800150ef  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800150f4  call    cs:__imp_GetCurrentThread
0x1800150fb  nop     dword ptr [rax+rax+00h]
0x180015100  mov     rcx, rax; ThreadHandle
0x180015103  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180015107  lea     edx, [rdi+6]; DesiredAccess
0x18001510a  lea     r8d, [r15+1]; OpenAsSelf
0x18001510e  call    cs:__imp_OpenThreadToken
0x180015115  nop     dword ptr [rax+rax+00h]
0x18001511a  test    eax, eax
0x18001511c  jz      short loc_180015158
0x18001511e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180015122  lea     rax, [rbp+57h+ReturnLength]
0x180015126  xor     r9d, r9d; TokenInformationLength
0x180015129  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; ReturnLength
0x18001512e  xor     r8d, r8d; TokenInformation
0x180015131  mov     [rbp+57h+ReturnLength], r15d
0x180015135  mov     edx, edi; TokenInformationClass
0x180015137  call    cs:__imp_GetTokenInformation
0x18001513e  nop     dword ptr [rax+rax+00h]
0x180015143  test    eax, eax
0x180015145  jnz     short loc_180015168
0x180015147  call    cs:__imp_GetLastError
0x18001514e  nop     dword ptr [rax+rax+00h]
0x180015153  cmp     eax, 7Ah ; 'z'
0x180015156  jz      short loc_180015168
0x180015158  call    cs:__imp_GetLastError
0x18001515f  nop     dword ptr [rax+rax+00h]
0x180015164  mov     ebx, eax
0x180015166  jmp     short loc_1800151C5
0x180015168  mov     edx, [rbp+57h+ReturnLength]; uBytes
0x18001516b  mov     ecx, 40h ; '@'; uFlags
0x180015170  call    cs:__imp_LocalAlloc
0x180015177  nop     dword ptr [rax+rax+00h]
0x18001517c  mov     [rbp+57h+var_48], rax
0x180015180  mov     rbx, rax
0x180015183  test    rax, rax
0x180015186  jz      short loc_1800151AE
0x180015188  mov     r9d, [rbp+57h+ReturnLength]; TokenInformationLength
0x18001518c  lea     rax, [rbp+57h+ReturnLength]
0x180015190  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180015194  mov     r8, rbx; TokenInformation
0x180015197  mov     edx, edi; TokenInformationClass
0x180015199  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; ReturnLength
0x18001519e  call    cs:__imp_GetTokenInformation
0x1800151a5  nop     dword ptr [rax+rax+00h]
0x1800151aa  test    eax, eax
0x1800151ac  jnz     short loc_1800151D0
0x1800151ae  call    cs:__imp_GetLastError
0x1800151b5  nop     dword ptr [rax+rax+00h]
0x1800151ba  lea     rcx, [rbp+57h+var_48]
0x1800151be  mov     ebx, eax
0x1800151c0  call    ??1?$CLocalMemPtr@U_TOKEN_GROUPS@@@@QEAA@XZ; CLocalMemPtr<_TOKEN_GROUPS>::~CLocalMemPtr<_TOKEN_GROUPS>(void)
0x1800151c5  lea     rcx, [rbp+57h+TokenHandle]
0x1800151c9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800151ce  jmp     short loc_180015222
0x1800151d0  mov     esi, [rbp+57h+ReturnLength]
0x1800151d3  mov     edi, r15d
0x1800151d6  add     esi, 0FFFFFFF8h
0x1800151d9  shr     esi, 4
0x1800151dc  cmp     edi, [rbx]
0x1800151de  jnb     short loc_18001520D
0x1800151e0  cmp     edi, esi
0x1800151e2  jnb     short loc_18001520D
0x1800151e4  mov     rcx, [rbp+57h+pSid1]; pSid1
0x1800151e8  mov     edx, edi
0x1800151ea  add     rdx, rdx
0x1800151ed  mov     rdx, [rbx+rdx*8+8]; pSid2
0x1800151f2  call    cs:__imp_EqualSid
0x1800151f9  nop     dword ptr [rax+rax+00h]
0x1800151fe  test    eax, eax
0x180015200  jnz     short loc_180015206
0x180015202  inc     edi
0x180015204  jmp     short loc_1800151DC
0x180015206  mov     dword ptr [r14], 1
0x18001520d  lea     rcx, [rbp+57h+var_48]
0x180015211  call    ??1?$CLocalMemPtr@U_TOKEN_GROUPS@@@@QEAA@XZ; CLocalMemPtr<_TOKEN_GROUPS>::~CLocalMemPtr<_TOKEN_GROUPS>(void)
0x180015216  lea     rcx, [rbp+57h+TokenHandle]
0x18001521a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001521f  mov     ebx, r15d
0x180015222  lea     rcx, [rbp+57h+pSid1]
0x180015226  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001522b  mov     eax, ebx
0x18001522d  mov     rcx, [rbp+57h+var_38]
0x180015231  xor     rcx, rsp; StackCookie
0x180015234  call    __security_check_cookie
0x180015239  add     rsp, 98h
0x180015240  pop     r15
0x180015242  pop     r14
0x180015244  pop     rdi
0x180015245  pop     rsi
0x180015246  pop     rbx
0x180015247  pop     rbp
0x180015248  retn
```
