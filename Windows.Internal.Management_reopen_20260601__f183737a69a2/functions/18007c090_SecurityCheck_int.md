# SecurityCheck(int *)

- ea: `0x18007c090`
- end: `0x18007c1c1`
- name: `?SecurityCheck@@YAJPEAH@Z`
- size: `305`
- prototype: `int(int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180076f60`
- `0x180077240`
- `0x180077f20`
- `0x180078750`

## callees

- `0x18000a5c4`
- `0x1800151e0`
- `0x18007c090`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007c0f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007c0f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007c0d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007c0d4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18007c110`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18007c110`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18007c09b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18007c09b`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18007c153`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18007c153`
- `ext-ms-win-provisioning-platform-l1-1-0!CheckPackageManagerOutOfProc` at `0x18007c17f`
- `ext-ms-win-provisioning-platform-l1-1-0!CheckPackageManagerOutOfProc` at `0x18007c17f`

## string_xrefs

- `0x18007c0b2`: `onecoreuap\admin\prov\provapi\lib\securityhelper.cpp`
- `0x18007c12f`: `onecoreuap\admin\prov\provapi\lib\securityhelper.cpp`

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
0x18007c090  push    rbx
0x18007c092  push    rsi
0x18007c093  push    rdi; int
0x18007c094  sub     rsp, 20h
0x18007c098  mov     rsi, rcx
0x18007c09b  call    cs:__imp_CoImpersonateClient
0x18007c0a2  nop     dword ptr [rax+rax+00h]
0x18007c0a7  mov     ebx, eax
0x18007c0a9  test    eax, eax
0x18007c0ab  jns     short loc_18007C0CB
0x18007c0ad  mov     rcx, [rsp+38h]; this
0x18007c0b2  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007c0b9  mov     r9d, eax; char *
0x18007c0bc  mov     edx, 14h; void *
0x18007c0c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c0c6  jmp     loc_18007C1B6
0x18007c0cb  mov     [rsp+38h+TokenHandle], 0
0x18007c0d4  call    cs:__imp_GetCurrentThread
0x18007c0db  nop     dword ptr [rax+rax+00h]
0x18007c0e0  mov     edi, 1
0x18007c0e5  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18007c0ea  mov     r8d, edi; OpenAsSelf
0x18007c0ed  mov     rcx, rax; ThreadHandle
0x18007c0f0  lea     edx, [rdi+7]; DesiredAccess
0x18007c0f3  call    cs:__imp_OpenThreadToken
0x18007c0fa  nop     dword ptr [rax+rax+00h]
0x18007c0ff  test    eax, eax
0x18007c101  jnz     short loc_18007C110
0x18007c103  mov     ebx, 8000FFFFh
0x18007c108  lea     edx, [rdi+16h]
0x18007c10b  mov     r9d, ebx
0x18007c10e  jmp     short loc_18007C12A
0x18007c110  call    cs:__imp_CoRevertToSelf
0x18007c117  nop     dword ptr [rax+rax+00h]
0x18007c11c  mov     ebx, eax
0x18007c11e  test    eax, eax
0x18007c120  jns     short loc_18007C13D
0x18007c122  mov     edx, 19h; void *
0x18007c127  mov     r9d, eax; char *
0x18007c12a  mov     rcx, [rsp+38h]; this
0x18007c12f  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007c136  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c13b  jmp     short loc_18007C1AC
0x18007c13d  mov     rcx, [rsp+38h+TokenHandle]
0x18007c142  lea     r8, [rsp+38h+arg_8]
0x18007c147  lea     rdx, aIdCapProvision; "ID_CAP_PROVISIONING_PACKAGE_API_ADMIN"
0x18007c14e  mov     [rsp+38h+arg_8], 0
0x18007c153  call    cs:__imp_CapabilityCheck
0x18007c15a  nop     dword ptr [rax+rax+00h]
0x18007c15f  test    eax, eax
0x18007c161  jns     short loc_18007C172
0x18007c163  mov     ebx, 8000FFFFh
0x18007c168  mov     edx, 1Dh
0x18007c16d  mov     r9d, ebx
0x18007c170  jmp     short loc_18007C12A
0x18007c172  lea     rcx, [rsp+38h+arg_10]
0x18007c177  mov     [rsp+38h+arg_10], 0
0x18007c17f  call    cs:__imp_CheckPackageManagerOutOfProc
0x18007c186  nop     dword ptr [rax+rax+00h]
0x18007c18b  mov     ebx, eax
0x18007c18d  test    eax, eax
0x18007c18f  jns     short loc_18007C198
0x18007c191  mov     edx, 20h ; ' '
0x18007c196  jmp     short loc_18007C127
0x18007c198  cmp     [rsp+38h+arg_8], 0
0x18007c19d  jz      short loc_18007C1A6
0x18007c19f  cmp     [rsp+38h+arg_10], 0
0x18007c1a4  jnz     short loc_18007C1A8
0x18007c1a6  xor     edi, edi
0x18007c1a8  mov     [rsi], edi
0x18007c1aa  xor     ebx, ebx
0x18007c1ac  lea     rcx, [rsp+38h+TokenHandle]
0x18007c1b1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007c1b6  mov     eax, ebx
0x18007c1b8  add     rsp, 20h
0x18007c1bc  pop     rdi
0x18007c1bd  pop     rsi
0x18007c1be  pop     rbx
0x18007c1bf  retn
```
