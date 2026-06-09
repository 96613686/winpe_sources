# Windows::Internal::Management::Provision::ConfigurationSession::AccessCheckForCapability(ushort const *,ushort const *,int)

- ea: `0x18006c9cc`
- end: `0x18006cba8`
- name: `?AccessCheckForCapability@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEBG0H@Z`
- size: `476`
- prototype: `__int64 __fastcall(const unsigned __int16 *, wchar_t *SubStr, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006dd20`

## callees

- `0x18000a5a4`
- `0x18000a5c4`
- `0x1800151e0`
- `0x1800179f8`
- `0x180017a88`
- `0x1800181cc`
- `0x1800183bc`
- `0x1800187d4`
- `0x18006c9cc`
- `0x18006cbb0`
- `0x18006d7fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006ca66`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006ca66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006ca4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006ca4a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18006c9ff`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18006c9ff`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18006cb48`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18006cb48`
- `ntdll!RtlIsMultiSessionSku` at `0x18006cad2`
- `ntdll!RtlIsMultiSessionSku` at `0x18006cad2`

## string_xrefs

- `0x18006ca2c`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006ca7a`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006cb16`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Management::Provision::ConfigurationSession::AccessCheckForCapability(
        const unsigned __int16 *a1,
        wchar_t *SubStr,
        int a3)
{
  int v6; // eax
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v9; // r9
  int v10; // eax
  __int64 v11; // rdx
  int v13; // [rsp+20h] [rbp-30h] BYREF
  unsigned int Pid; // [rsp+24h] [rbp-2Ch] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-28h] BYREF
  unsigned __int16 *v16; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v17[24]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  char v19; // [rsp+88h] [rbp+38h] BYREF

  v17[0] = 0;
  v17[2] = 0;
  Pid = 0;
  if ( I_RpcBindingInqLocalClientPID(0, &Pid) == 1725 )
    goto LABEL_10;
  v6 = AutoImpersonate::ImpersonateClient((AutoImpersonate *)v17);
  LastError = v6;
  if ( v6 >= 0 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x184,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
                    v9);
LABEL_6:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      goto LABEL_21;
    }
    v13 = 0;
    if ( (int)Windows::Internal::Management::Provision::ConfigurationSession::CheckThreadAdmin(TokenHandle, &v13) >= 0
      && v13 == 1 )
    {
      goto LABEL_9;
    }
    AutoImpersonate::RevertToSelf((AutoImpersonate *)v17);
    if ( !(unsigned __int8)RtlIsMultiSessionSku() )
    {
      v16 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v16,
        0);
      v10 = Windows::Internal::Management::Provision::ConfigurationSession::QueryCapabilityRequired(
              a1,
              SubStr,
              a3,
              &v16);
      LastError = v10;
      if ( v10 < 0 )
      {
        v11 = 409;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
          (const char *)(unsigned int)v10,
          v13);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
        goto LABEL_6;
      }
      v19 = 0;
      v10 = CapabilityCheck(TokenHandle, v16, &v19);
      LastError = v10;
      if ( v10 < 0 )
      {
        v11 = 412;
        goto LABEL_14;
      }
      if ( v19 == 1 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
LABEL_9:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_10:
        LastError = 0;
        goto LABEL_21;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    LastError = -2147024891;
    goto LABEL_21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x181,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
    (const char *)(unsigned int)v6,
    v13);
LABEL_21:
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v17);
  return LastError;
}

```

## disassembly

```asm
0x18006c9cc  mov     [rsp-18h+arg_0], rbx
0x18006c9d1  mov     [rsp-18h+arg_8], rsi
0x18006c9d6  push    rbp
0x18006c9d7  push    rdi
0x18006c9d8  push    r14
0x18006c9da  mov     rbp, rsp
0x18006c9dd  sub     rsp, 50h
0x18006c9e1  mov     edi, r8d
0x18006c9e4  mov     rsi, rdx
0x18006c9e7  mov     r14, rcx
0x18006c9ea  mov     [rbp+var_18], 0
0x18006c9ee  mov     [rbp+var_16], 0
0x18006c9f2  mov     [rbp+Pid], 0
0x18006c9f9  lea     rdx, [rbp+Pid]; Pid
0x18006c9fd  xor     ecx, ecx; Binding
0x18006c9ff  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18006ca06  nop     dword ptr [rax+rax+00h]
0x18006ca0b  cmp     eax, 6BDh
0x18006ca10  jz      loc_18006CAC2
0x18006ca16  lea     rcx, [rbp+var_18]; this
0x18006ca1a  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x18006ca1f  mov     ebx, eax
0x18006ca21  test    eax, eax
0x18006ca23  jns     short loc_18006CA42
0x18006ca25  mov     rcx, [rbp+18h]; this
0x18006ca29  mov     r9d, eax; char *
0x18006ca2c  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006ca33  mov     edx, 181h; void *
0x18006ca38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ca3d  jmp     loc_18006CB89
0x18006ca42  mov     [rbp+TokenHandle], 0
0x18006ca4a  call    cs:__imp_GetCurrentThread
0x18006ca51  nop     dword ptr [rax+rax+00h]
0x18006ca56  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006ca5a  mov     edx, 8; DesiredAccess
0x18006ca5f  lea     r8d, [rdx-7]; OpenAsSelf
0x18006ca63  mov     rcx, rax; ThreadHandle
0x18006ca66  call    cs:__imp_OpenThreadToken
0x18006ca6d  nop     dword ptr [rax+rax+00h]
0x18006ca72  test    eax, eax
0x18006ca74  jnz     short loc_18006CA9B
0x18006ca76  mov     rcx, [rbp+18h]; this
0x18006ca7a  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006ca81  mov     edx, 184h; void *
0x18006ca86  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006ca8b  mov     ebx, eax
0x18006ca8d  lea     rcx, [rbp+TokenHandle]
0x18006ca91  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006ca96  jmp     loc_18006CB89
0x18006ca9b  mov     [rbp+var_30], 0
0x18006caa2  lea     rdx, [rbp+var_30]; int *
0x18006caa6  mov     rcx, [rbp+TokenHandle]; void *
0x18006caaa  call    ?CheckThreadAdmin@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEAXPEAH@Z; Windows::Internal::Management::Provision::ConfigurationSession::CheckThreadAdmin(void *,int *)
0x18006caaf  test    eax, eax
0x18006cab1  js      short loc_18006CAC9
0x18006cab3  cmp     [rbp+var_30], 1
0x18006cab7  jnz     short loc_18006CAC9
0x18006cab9  lea     rcx, [rbp+TokenHandle]
0x18006cabd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006cac2  xor     ebx, ebx
0x18006cac4  jmp     loc_18006CB89
0x18006cac9  lea     rcx, [rbp+var_18]; this
0x18006cacd  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x18006cad2  call    cs:__imp_RtlIsMultiSessionSku
0x18006cad9  nop     dword ptr [rax+rax+00h]
0x18006cade  test    al, al
0x18006cae0  jnz     loc_18006CB7B
0x18006cae6  mov     [rbp+var_20], 0
0x18006caee  xor     edx, edx
0x18006caf0  lea     rcx, [rbp+var_20]
0x18006caf4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006caf9  lea     r9, [rbp+var_20]; unsigned __int16 **
0x18006cafd  mov     r8d, edi; int
0x18006cb00  mov     rdx, rsi; SubStr
0x18006cb03  mov     rcx, r14; unsigned __int16 *
0x18006cb06  call    ?QueryCapabilityRequired@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEBG0HPEAPEAG@Z; Windows::Internal::Management::Provision::ConfigurationSession::QueryCapabilityRequired(ushort const *,ushort const *,int,ushort * *)
0x18006cb0b  mov     ebx, eax
0x18006cb0d  test    eax, eax
0x18006cb0f  jns     short loc_18006CB38
0x18006cb11  mov     edx, 199h; void *
0x18006cb16  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006cb1d  mov     r9d, eax; char *
0x18006cb20  mov     rcx, [rbp+18h]; this
0x18006cb24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cb29  nop
0x18006cb2a  lea     rcx, [rbp+var_20]
0x18006cb2e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006cb33  jmp     loc_18006CA8D
0x18006cb38  mov     [rbp+arg_18], 0
0x18006cb3c  lea     r8, [rbp+arg_18]
0x18006cb40  mov     rdx, [rbp+var_20]
0x18006cb44  mov     rcx, [rbp+TokenHandle]
0x18006cb48  call    cs:__imp_CapabilityCheck
0x18006cb4f  nop     dword ptr [rax+rax+00h]
0x18006cb54  mov     ebx, eax
0x18006cb56  test    eax, eax
0x18006cb58  jns     short loc_18006CB61
0x18006cb5a  mov     edx, 19Ch
0x18006cb5f  jmp     short loc_18006CB16
0x18006cb61  lea     rcx, [rbp+var_20]
0x18006cb65  cmp     [rbp+arg_18], 1
0x18006cb69  jnz     short loc_18006CB75
0x18006cb6b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006cb70  jmp     loc_18006CAB9
0x18006cb75  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006cb7a  nop
0x18006cb7b  lea     rcx, [rbp+TokenHandle]
0x18006cb7f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006cb84  mov     ebx, 80070005h
0x18006cb89  lea     rcx, [rbp+var_18]; this
0x18006cb8d  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18006cb92  mov     eax, ebx
0x18006cb94  mov     rbx, [rsp+50h+arg_0]
0x18006cb99  mov     rsi, [rsp+50h+arg_8]
0x18006cb9e  add     rsp, 50h
0x18006cba2  pop     r14
0x18006cba4  pop     rdi
0x18006cba5  pop     rbp
0x18006cba6  retn
```
