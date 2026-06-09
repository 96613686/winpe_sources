# IsUserAdmin

- ea: `0x18006cf10`
- end: `0x18006d10a`
- name: `IsUserAdmin`
- size: `506`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006a9d0`
- `0x18006cdd4`

## callees

- `0x180007270`
- `0x18005d7f8`
- `0x18005e13c`
- `0x180069a44`
- `0x180069b0c`
- `0x18006cf10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d06e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d018`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d06e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006cfce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006cfce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006cfb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006cfb4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006d030`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006d030`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006d0b2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006d0b2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006cf86`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006cf86`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006cff7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006d05e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006cff7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006d05e`

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
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_18:
      LastError = 0;
      goto LABEL_19;
    }
  }
  LastError = GetLastError();
LABEL_10:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_19:
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid1);
  return LastError;
}

```

## disassembly

```asm
0x18006cf10  push    rbp
0x18006cf12  push    rbx
0x18006cf13  push    rsi
0x18006cf14  push    rdi
0x18006cf15  push    r14
0x18006cf17  push    r15
0x18006cf19  lea     rbp, [rsp-2Fh]
0x18006cf1e  sub     rsp, 98h
0x18006cf25  mov     rax, cs:__security_cookie
0x18006cf2c  xor     rax, rsp
0x18006cf2f  mov     [rbp+57h+var_38], rax
0x18006cf33  xor     r15d, r15d
0x18006cf36  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18006cf3c  lea     rax, [rbp+57h+pSid1]
0x18006cf40  mov     [rcx], r15d
0x18006cf43  mov     [rsp+0C0h+pSid], rax; pSid
0x18006cf48  mov     r14, rcx
0x18006cf4b  mov     [rsp+0C0h+nSubAuthority7], r15d; nSubAuthority7
0x18006cf50  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18006cf54  mov     [rsp+0C0h+nSubAuthority6], r15d; nSubAuthority6
0x18006cf59  lea     edi, [r15+2]
0x18006cf5d  mov     [rsp+0C0h+nSubAuthority5], r15d; nSubAuthority5
0x18006cf62  lea     r8d, [r15+20h]; nSubAuthority0
0x18006cf66  mov     [rsp+0C0h+nSubAuthority4], r15d; nSubAuthority4
0x18006cf6b  mov     dl, dil; nSubAuthorityCount
0x18006cf6e  mov     [rsp+0C0h+nSubAuthority3], r15d; nSubAuthority3
0x18006cf73  mov     r9d, 220h; nSubAuthority1
0x18006cf79  mov     [rsp+0C0h+nSubAuthority2], r15d; nSubAuthority2
0x18006cf7e  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x18006cf82  mov     [rbp+57h+pSid1], r15
0x18006cf86  call    cs:__imp_AllocateAndInitializeSid
0x18006cf8d  nop     dword ptr [rax+rax+00h]
0x18006cf92  cmp     eax, 1
0x18006cf95  jnz     loc_18006D0DF
0x18006cf9b  cmp     [rbp+57h+pSid1], r15
0x18006cf9f  jz      loc_18006D0DF
0x18006cfa5  xor     edx, edx
0x18006cfa7  mov     [rbp+57h+TokenHandle], r15
0x18006cfab  lea     rcx, [rbp+57h+TokenHandle]
0x18006cfaf  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006cfb4  call    cs:__imp_GetCurrentThread
0x18006cfbb  nop     dword ptr [rax+rax+00h]
0x18006cfc0  mov     rcx, rax; ThreadHandle
0x18006cfc3  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18006cfc7  lea     edx, [rdi+6]; DesiredAccess
0x18006cfca  lea     r8d, [r15+1]; OpenAsSelf
0x18006cfce  call    cs:__imp_OpenThreadToken
0x18006cfd5  nop     dword ptr [rax+rax+00h]
0x18006cfda  test    eax, eax
0x18006cfdc  jz      short loc_18006D018
0x18006cfde  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18006cfe2  lea     rax, [rbp+57h+ReturnLength]
0x18006cfe6  xor     r9d, r9d; TokenInformationLength
0x18006cfe9  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; ReturnLength
0x18006cfee  xor     r8d, r8d; TokenInformation
0x18006cff1  mov     [rbp+57h+ReturnLength], r15d
0x18006cff5  mov     edx, edi; TokenInformationClass
0x18006cff7  call    cs:__imp_GetTokenInformation
0x18006cffe  nop     dword ptr [rax+rax+00h]
0x18006d003  test    eax, eax
0x18006d005  jnz     short loc_18006D028
0x18006d007  call    cs:__imp_GetLastError
0x18006d00e  nop     dword ptr [rax+rax+00h]
0x18006d013  cmp     eax, 7Ah ; 'z'
0x18006d016  jz      short loc_18006D028
0x18006d018  call    cs:__imp_GetLastError
0x18006d01f  nop     dword ptr [rax+rax+00h]
0x18006d024  mov     ebx, eax
0x18006d026  jmp     short loc_18006D085
0x18006d028  mov     edx, [rbp+57h+ReturnLength]; uBytes
0x18006d02b  mov     ecx, 40h ; '@'; uFlags
0x18006d030  call    cs:__imp_LocalAlloc
0x18006d037  nop     dword ptr [rax+rax+00h]
0x18006d03c  mov     [rbp+57h+var_48], rax
0x18006d040  mov     rbx, rax
0x18006d043  test    rax, rax
0x18006d046  jz      short loc_18006D06E
0x18006d048  mov     r9d, [rbp+57h+ReturnLength]; TokenInformationLength
0x18006d04c  lea     rax, [rbp+57h+ReturnLength]
0x18006d050  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18006d054  mov     r8, rbx; TokenInformation
0x18006d057  mov     edx, edi; TokenInformationClass
0x18006d059  mov     qword ptr [rsp+0C0h+nSubAuthority2], rax; ReturnLength
0x18006d05e  call    cs:__imp_GetTokenInformation
0x18006d065  nop     dword ptr [rax+rax+00h]
0x18006d06a  test    eax, eax
0x18006d06c  jnz     short loc_18006D090
0x18006d06e  call    cs:__imp_GetLastError
0x18006d075  nop     dword ptr [rax+rax+00h]
0x18006d07a  lea     rcx, [rbp+57h+var_48]
0x18006d07e  mov     ebx, eax
0x18006d080  call    ??1?$CLocalMemPtr@U_TOKEN_GROUPS@@@@QEAA@XZ; CLocalMemPtr<_TOKEN_GROUPS>::~CLocalMemPtr<_TOKEN_GROUPS>(void)
0x18006d085  lea     rcx, [rbp+57h+TokenHandle]
0x18006d089  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006d08e  jmp     short loc_18006D0E2
0x18006d090  mov     esi, [rbp+57h+ReturnLength]
0x18006d093  mov     edi, r15d
0x18006d096  add     esi, 0FFFFFFF8h
0x18006d099  shr     esi, 4
0x18006d09c  cmp     edi, [rbx]
0x18006d09e  jnb     short loc_18006D0CD
0x18006d0a0  cmp     edi, esi
0x18006d0a2  jnb     short loc_18006D0CD
0x18006d0a4  mov     rcx, [rbp+57h+pSid1]; pSid1
0x18006d0a8  mov     edx, edi
0x18006d0aa  add     rdx, rdx
0x18006d0ad  mov     rdx, [rbx+rdx*8+8]; pSid2
0x18006d0b2  call    cs:__imp_EqualSid
0x18006d0b9  nop     dword ptr [rax+rax+00h]
0x18006d0be  test    eax, eax
0x18006d0c0  jnz     short loc_18006D0C6
0x18006d0c2  inc     edi
0x18006d0c4  jmp     short loc_18006D09C
0x18006d0c6  mov     dword ptr [r14], 1
0x18006d0cd  lea     rcx, [rbp+57h+var_48]
0x18006d0d1  call    ??1?$CLocalMemPtr@U_TOKEN_GROUPS@@@@QEAA@XZ; CLocalMemPtr<_TOKEN_GROUPS>::~CLocalMemPtr<_TOKEN_GROUPS>(void)
0x18006d0d6  lea     rcx, [rbp+57h+TokenHandle]
0x18006d0da  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006d0df  mov     ebx, r15d
0x18006d0e2  lea     rcx, [rbp+57h+pSid1]
0x18006d0e6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18006d0eb  mov     eax, ebx
0x18006d0ed  mov     rcx, [rbp+57h+var_38]
0x18006d0f1  xor     rcx, rsp; StackCookie
0x18006d0f4  call    __security_check_cookie
0x18006d0f9  add     rsp, 98h
0x18006d100  pop     r15
0x18006d102  pop     r14
0x18006d104  pop     rdi
0x18006d105  pop     rsi
0x18006d106  pop     rbx
0x18006d107  pop     rbp
0x18006d108  retn
```
