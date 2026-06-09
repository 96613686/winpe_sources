# CheckThreadAdmin(int *)

- ea: `0x18007a658`
- end: `0x18007a7dd`
- name: `?CheckThreadAdmin@@YAJPEAH@Z`
- size: `389`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180077fd0`

## callees

- `0x180004d50`
- `0x18000a284`
- `0x18000a2a4`
- `0x180014af0`
- `0x180017204`
- `0x180017264`
- `0x18007a658`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007a6bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007a6bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007a6a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007a6a9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18007a67e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18007a67e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18007a6ed`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18007a6ed`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18007a75f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18007a75f`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18007a797`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18007a797`

## string_xrefs

- `0x18007a68e`: `onecoreuap\admin\prov\provapi\lib\securityhelper.cpp`
- `0x18007a6cd`: `onecoreuap\admin\prov\provapi\lib\securityhelper.cpp`
- `0x18007a6fd`: `onecoreuap\admin\prov\provapi\lib\securityhelper.cpp`
- `0x18007a770`: `onecoreuap\admin\prov\provapi\lib\securityhelper.cpp`

## pseudocode

```c
__int64 __fastcall CheckThreadAdmin(int *a1)
{
  HRESULT v2; // eax
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  HRESULT v5; // eax
  const char *v6; // r9
  __int64 v7; // rdx
  DWORD nSubAuthority2; // [rsp+20h] [rbp-39h]
  PSID pSid; // [rsp+60h] [rbp+7h] BYREF
  __int64 v11; // [rsp+68h] [rbp+Fh] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+17h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a1 = 0;
  v2 = CoImpersonateClient();
  LastError = v2;
  if ( v2 >= 0 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v11 = 0;
      v5 = CoRevertToSelf();
      LastError = v5;
      if ( v5 >= 0 )
      {
        *(_DWORD *)pIdentifierAuthority.Value = 0;
        *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
        pSid = 0;
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
        {
          if ( (unsigned int)CheckTokenMembershipEx(TokenHandle, pSid, 0, a1) )
          {
            wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
            LastError = 0;
            goto LABEL_14;
          }
          v7 = 61;
        }
        else
        {
          v7 = 58;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v7,
                      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\securityhelper.cpp",
                      v6);
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x33,
          (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\securityhelper.cpp",
          (const char *)(unsigned int)v5,
          nSubAuthority2);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
    }
    else
    {
      LastError = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\securityhelper.cpp",
        (const char *)0x8000FFFFLL,
        nSubAuthority2);
    }
LABEL_14:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return LastError;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C,
    (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\securityhelper.cpp",
    (const char *)(unsigned int)v2,
    nSubAuthority2);
  return LastError;
}

```

## disassembly

```asm
0x18007a658  push    rbp
0x18007a65a  push    rbx
0x18007a65b  push    rsi
0x18007a65c  push    rdi
0x18007a65d  lea     rbp, [rsp-3Fh]
0x18007a662  sub     rsp, 98h
0x18007a669  mov     rax, cs:__security_cookie
0x18007a670  xor     rax, rsp
0x18007a673  mov     [rbp+57h+var_30], rax
0x18007a677  xor     esi, esi
0x18007a679  mov     rdi, rcx
0x18007a67c  mov     [rcx], esi
0x18007a67e  call    cs:__imp_CoImpersonateClient
0x18007a684  mov     ebx, eax
0x18007a686  test    eax, eax
0x18007a688  jns     short loc_18007A6A5
0x18007a68a  mov     rcx, [rbp+5Fh]; this
0x18007a68e  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007a695  mov     r9d, eax; char *
0x18007a698  lea     edx, [rsi+2Ch]; void *
0x18007a69b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a6a0  jmp     loc_18007A7C3
0x18007a6a5  mov     [rbp+57h+TokenHandle], rsi
0x18007a6a9  call    cs:__imp_GetCurrentThread
0x18007a6af  mov     edx, 8; DesiredAccess
0x18007a6b4  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18007a6b8  mov     rcx, rax; ThreadHandle
0x18007a6bb  lea     r8d, [rdx-7]; OpenAsSelf
0x18007a6bf  call    cs:__imp_OpenThreadToken
0x18007a6c5  test    eax, eax
0x18007a6c7  jnz     short loc_18007A6E9
0x18007a6c9  mov     rcx, [rbp+5Fh]; this
0x18007a6cd  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007a6d4  mov     ebx, 8000FFFFh
0x18007a6d9  lea     edx, [rax+2Fh]; void *
0x18007a6dc  mov     r9d, ebx; char *
0x18007a6df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a6e4  jmp     loc_18007A7BA
0x18007a6e9  mov     [rbp+57h+var_48], rsi
0x18007a6ed  call    cs:__imp_CoRevertToSelf
0x18007a6f3  mov     ebx, eax
0x18007a6f5  test    eax, eax
0x18007a6f7  jns     short loc_18007A71F
0x18007a6f9  mov     rcx, [rbp+5Fh]; this
0x18007a6fd  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007a704  mov     r9d, eax; char *
0x18007a707  mov     edx, 33h ; '3'; void *
0x18007a70c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a711  lea     rcx, [rbp+57h+var_48]
0x18007a715  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007a71a  jmp     loc_18007A7BA
0x18007a71f  lea     rax, [rbp+57h+var_50]
0x18007a723  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18007a726  mov     [rsp+0B0h+pSid], rax; pSid
0x18007a72b  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18007a72f  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x18007a733  mov     r9d, 220h; nSubAuthority1
0x18007a739  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x18007a73d  mov     r8d, 20h ; ' '; nSubAuthority0
0x18007a743  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x18007a747  mov     dl, 2; nSubAuthorityCount
0x18007a749  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x18007a74d  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x18007a751  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x18007a755  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18007a75b  mov     [rbp+57h+var_50], rsi
0x18007a75f  call    cs:__imp_AllocateAndInitializeSid
0x18007a765  test    eax, eax
0x18007a767  jnz     short loc_18007A789
0x18007a769  lea     edx, [rax+3Ah]; void *
0x18007a76c  mov     rcx, [rbp+5Fh]; this
0x18007a770  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007a777  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007a77c  lea     rcx, [rbp+57h+var_50]
0x18007a780  mov     ebx, eax
0x18007a782  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007a787  jmp     short loc_18007A711
0x18007a789  mov     rdx, [rbp+57h+var_50]
0x18007a78d  mov     r9, rdi
0x18007a790  mov     rcx, [rbp+57h+TokenHandle]
0x18007a794  xor     r8d, r8d
0x18007a797  call    cs:__imp_CheckTokenMembershipEx
0x18007a79d  test    eax, eax
0x18007a79f  jnz     short loc_18007A7A6
0x18007a7a1  lea     edx, [rax+3Dh]
0x18007a7a4  jmp     short loc_18007A76C
0x18007a7a6  lea     rcx, [rbp+57h+var_50]
0x18007a7aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007a7af  lea     rcx, [rbp+57h+var_48]
0x18007a7b3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007a7b8  mov     ebx, esi
0x18007a7ba  lea     rcx, [rbp+57h+TokenHandle]
0x18007a7be  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007a7c3  mov     eax, ebx
0x18007a7c5  mov     rcx, [rbp+57h+var_30]
0x18007a7c9  xor     rcx, rsp; StackCookie
0x18007a7cc  call    __security_check_cookie
0x18007a7d1  add     rsp, 98h
0x18007a7d8  pop     rdi
0x18007a7d9  pop     rsi
0x18007a7da  pop     rbx
0x18007a7db  pop     rbp
0x18007a7dc  retn
```
