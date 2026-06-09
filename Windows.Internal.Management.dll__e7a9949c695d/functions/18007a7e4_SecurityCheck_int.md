# SecurityCheck(int *)

- ea: `0x18007a7e4`
- end: `0x18007a8f0`
- name: `?SecurityCheck@@YAJPEAH@Z`
- size: `268`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180075860`
- `0x180075b40`
- `0x1800767b0`
- `0x180076fd0`

## callees

- `0x18000a2a4`
- `0x180014af0`
- `0x18007a7e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007a83b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007a83b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007a822`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007a822`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18007a7ef`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18007a7ef`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18007a852`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18007a852`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18007a88f`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18007a88f`
- `ext-ms-win-provisioning-platform-l1-1-0!CheckPackageManagerOutOfProc` at `0x18007a8b5`
- `ext-ms-win-provisioning-platform-l1-1-0!CheckPackageManagerOutOfProc` at `0x18007a8b5`

## string_xrefs

- `0x18007a800`: `onecoreuap\admin\prov\provapi\lib\securityhelper.cpp`
- `0x18007a86b`: `onecoreuap\admin\prov\provapi\lib\securityhelper.cpp`

## pseudocode

```c
__int64 __fastcall SecurityCheck(int *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // r9
  HRESULT v8; // eax
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v12; // [rsp+48h] [rbp+10h] BYREF
  int v13; // [rsp+50h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  v2 = CoImpersonateClient();
  v3 = v2;
  if ( v2 >= 0 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    v5 = 1;
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v8 = CoRevertToSelf();
      v3 = v8;
      if ( v8 >= 0 )
      {
        v12 = 0;
        if ( (int)CapabilityCheck(TokenHandle, L"ID_CAP_PROVISIONING_PACKAGE_API_ADMIN", &v12) < 0 )
        {
          v3 = -2147418113;
          v6 = 29;
          v7 = 2147549183LL;
          goto LABEL_8;
        }
        v13 = 0;
        v8 = CheckPackageManagerOutOfProc(&v13);
        v3 = v8;
        if ( v8 >= 0 )
        {
          if ( !v12 || !v13 )
            v5 = 0;
          *a1 = v5;
          v3 = 0;
          goto LABEL_17;
        }
        v6 = 32;
      }
      else
      {
        v6 = 25;
      }
      v7 = (unsigned int)v8;
    }
    else
    {
      v3 = -2147418113;
      v6 = 23;
      v7 = 2147549183LL;
    }
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\securityhelper.cpp",
      (const char *)v7,
      v10);
LABEL_17:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v3;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14,
    (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\securityhelper.cpp",
    (const char *)(unsigned int)v2,
    v10);
  return v3;
}

```

## disassembly

```asm
0x18007a7e4  push    rbx
0x18007a7e6  push    rsi
0x18007a7e7  push    rdi; int
0x18007a7e8  sub     rsp, 20h
0x18007a7ec  mov     rsi, rcx
0x18007a7ef  call    cs:__imp_CoImpersonateClient
0x18007a7f5  mov     ebx, eax
0x18007a7f7  test    eax, eax
0x18007a7f9  jns     short loc_18007A819
0x18007a7fb  mov     rcx, [rsp+38h]; this
0x18007a800  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007a807  mov     r9d, eax; char *
0x18007a80a  mov     edx, 14h; void *
0x18007a80f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a814  jmp     loc_18007A8E6
0x18007a819  mov     [rsp+38h+TokenHandle], 0
0x18007a822  call    cs:__imp_GetCurrentThread
0x18007a828  mov     edi, 1
0x18007a82d  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18007a832  mov     r8d, edi; OpenAsSelf
0x18007a835  mov     rcx, rax; ThreadHandle
0x18007a838  lea     edx, [rdi+7]; DesiredAccess
0x18007a83b  call    cs:__imp_OpenThreadToken
0x18007a841  test    eax, eax
0x18007a843  jnz     short loc_18007A852
0x18007a845  mov     ebx, 8000FFFFh
0x18007a84a  lea     edx, [rdi+16h]
0x18007a84d  mov     r9d, ebx
0x18007a850  jmp     short loc_18007A866
0x18007a852  call    cs:__imp_CoRevertToSelf
0x18007a858  mov     ebx, eax
0x18007a85a  test    eax, eax
0x18007a85c  jns     short loc_18007A879
0x18007a85e  mov     edx, 19h; void *
0x18007a863  mov     r9d, eax; char *
0x18007a866  mov     rcx, [rsp+38h]; this
0x18007a86b  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007a872  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a877  jmp     short loc_18007A8DC
0x18007a879  mov     rcx, [rsp+38h+TokenHandle]
0x18007a87e  lea     r8, [rsp+38h+arg_8]
0x18007a883  lea     rdx, aIdCapProvision; "ID_CAP_PROVISIONING_PACKAGE_API_ADMIN"
0x18007a88a  mov     [rsp+38h+arg_8], 0
0x18007a88f  call    cs:__imp_CapabilityCheck
0x18007a895  test    eax, eax
0x18007a897  jns     short loc_18007A8A8
0x18007a899  mov     ebx, 8000FFFFh
0x18007a89e  mov     edx, 1Dh
0x18007a8a3  mov     r9d, ebx
0x18007a8a6  jmp     short loc_18007A866
0x18007a8a8  lea     rcx, [rsp+38h+arg_10]
0x18007a8ad  mov     [rsp+38h+arg_10], 0
0x18007a8b5  call    cs:__imp_CheckPackageManagerOutOfProc
0x18007a8bb  mov     ebx, eax
0x18007a8bd  test    eax, eax
0x18007a8bf  jns     short loc_18007A8C8
0x18007a8c1  mov     edx, 20h ; ' '
0x18007a8c6  jmp     short loc_18007A863
0x18007a8c8  cmp     [rsp+38h+arg_8], 0
0x18007a8cd  jz      short loc_18007A8D6
0x18007a8cf  cmp     [rsp+38h+arg_10], 0
0x18007a8d4  jnz     short loc_18007A8D8
0x18007a8d6  xor     edi, edi
0x18007a8d8  mov     [rsi], edi
0x18007a8da  xor     ebx, ebx
0x18007a8dc  lea     rcx, [rsp+38h+TokenHandle]
0x18007a8e1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007a8e6  mov     eax, ebx
0x18007a8e8  add     rsp, 20h
0x18007a8ec  pop     rdi
0x18007a8ed  pop     rsi
0x18007a8ee  pop     rbx
0x18007a8ef  retn
```
