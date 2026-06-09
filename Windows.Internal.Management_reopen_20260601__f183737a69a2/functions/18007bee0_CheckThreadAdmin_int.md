# CheckThreadAdmin(int *)

- ea: `0x18007bee0`
- end: `0x18007c08a`
- name: `?CheckThreadAdmin@@YAJPEAH@Z`
- size: `426`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180079790`

## callees

- `0x180004eb0`
- `0x18000a5a4`
- `0x18000a5c4`
- `0x1800151e0`
- `0x1800179f8`
- `0x180017a64`
- `0x18007bee0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007bf53`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007bf53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007bf37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007bf37`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18007bf87`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18007bf87`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18007bf06`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18007bf06`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18007bfff`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18007bfff`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18007c03d`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18007c03d`

## string_xrefs

- `0x18007bf1c`: `onecoreuap\admin\prov\provapi\lib\securityhelper.cpp`
- `0x18007bf67`: `onecoreuap\admin\prov\provapi\lib\securityhelper.cpp`
- `0x18007bf9d`: `onecoreuap\admin\prov\provapi\lib\securityhelper.cpp`
- `0x18007c016`: `onecoreuap\admin\prov\provapi\lib\securityhelper.cpp`

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
0x18007bee0  push    rbp
0x18007bee2  push    rbx
0x18007bee3  push    rsi
0x18007bee4  push    rdi
0x18007bee5  lea     rbp, [rsp-3Fh]
0x18007beea  sub     rsp, 98h
0x18007bef1  mov     rax, cs:__security_cookie
0x18007bef8  xor     rax, rsp
0x18007befb  mov     [rbp+57h+var_30], rax
0x18007beff  xor     esi, esi
0x18007bf01  mov     rdi, rcx
0x18007bf04  mov     [rcx], esi
0x18007bf06  call    cs:__imp_CoImpersonateClient
0x18007bf0d  nop     dword ptr [rax+rax+00h]
0x18007bf12  mov     ebx, eax
0x18007bf14  test    eax, eax
0x18007bf16  jns     short loc_18007BF33
0x18007bf18  mov     rcx, [rbp+5Fh]; this
0x18007bf1c  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007bf23  mov     r9d, eax; char *
0x18007bf26  lea     edx, [rsi+2Ch]; void *
0x18007bf29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007bf2e  jmp     loc_18007C06F
0x18007bf33  mov     [rbp+57h+TokenHandle], rsi
0x18007bf37  call    cs:__imp_GetCurrentThread
0x18007bf3e  nop     dword ptr [rax+rax+00h]
0x18007bf43  mov     edx, 8; DesiredAccess
0x18007bf48  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18007bf4c  mov     rcx, rax; ThreadHandle
0x18007bf4f  lea     r8d, [rdx-7]; OpenAsSelf
0x18007bf53  call    cs:__imp_OpenThreadToken
0x18007bf5a  nop     dword ptr [rax+rax+00h]
0x18007bf5f  test    eax, eax
0x18007bf61  jnz     short loc_18007BF83
0x18007bf63  mov     rcx, [rbp+5Fh]; this
0x18007bf67  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007bf6e  mov     ebx, 8000FFFFh
0x18007bf73  lea     edx, [rax+2Fh]; void *
0x18007bf76  mov     r9d, ebx; char *
0x18007bf79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007bf7e  jmp     loc_18007C066
0x18007bf83  mov     [rbp+57h+var_48], rsi
0x18007bf87  call    cs:__imp_CoRevertToSelf
0x18007bf8e  nop     dword ptr [rax+rax+00h]
0x18007bf93  mov     ebx, eax
0x18007bf95  test    eax, eax
0x18007bf97  jns     short loc_18007BFBF
0x18007bf99  mov     rcx, [rbp+5Fh]; this
0x18007bf9d  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007bfa4  mov     r9d, eax; char *
0x18007bfa7  mov     edx, 33h ; '3'; void *
0x18007bfac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007bfb1  lea     rcx, [rbp+57h+var_48]
0x18007bfb5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007bfba  jmp     loc_18007C066
0x18007bfbf  lea     rax, [rbp+57h+var_50]
0x18007bfc3  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18007bfc6  mov     [rsp+0B0h+pSid], rax; pSid
0x18007bfcb  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18007bfcf  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x18007bfd3  mov     r9d, 220h; nSubAuthority1
0x18007bfd9  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x18007bfdd  mov     r8d, 20h ; ' '; nSubAuthority0
0x18007bfe3  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x18007bfe7  mov     dl, 2; nSubAuthorityCount
0x18007bfe9  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x18007bfed  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x18007bff1  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x18007bff5  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18007bffb  mov     [rbp+57h+var_50], rsi
0x18007bfff  call    cs:__imp_AllocateAndInitializeSid
0x18007c006  nop     dword ptr [rax+rax+00h]
0x18007c00b  test    eax, eax
0x18007c00d  jnz     short loc_18007C02F
0x18007c00f  lea     edx, [rax+3Ah]; void *
0x18007c012  mov     rcx, [rbp+5Fh]; this
0x18007c016  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007c01d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007c022  lea     rcx, [rbp+57h+var_50]
0x18007c026  mov     ebx, eax
0x18007c028  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007c02d  jmp     short loc_18007BFB1
0x18007c02f  mov     rdx, [rbp+57h+var_50]
0x18007c033  mov     r9, rdi
0x18007c036  mov     rcx, [rbp+57h+TokenHandle]
0x18007c03a  xor     r8d, r8d
0x18007c03d  call    cs:__imp_CheckTokenMembershipEx
0x18007c044  nop     dword ptr [rax+rax+00h]
0x18007c049  test    eax, eax
0x18007c04b  jnz     short loc_18007C052
0x18007c04d  lea     edx, [rax+3Dh]
0x18007c050  jmp     short loc_18007C012
0x18007c052  lea     rcx, [rbp+57h+var_50]
0x18007c056  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007c05b  lea     rcx, [rbp+57h+var_48]
0x18007c05f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007c064  mov     ebx, esi
0x18007c066  lea     rcx, [rbp+57h+TokenHandle]
0x18007c06a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007c06f  mov     eax, ebx
0x18007c071  mov     rcx, [rbp+57h+var_30]
0x18007c075  xor     rcx, rsp; StackCookie
0x18007c078  call    __security_check_cookie
0x18007c07d  add     rsp, 98h
0x18007c084  pop     rdi
0x18007c085  pop     rsi
0x18007c086  pop     rbx
0x18007c087  pop     rbp
0x18007c088  retn
```
