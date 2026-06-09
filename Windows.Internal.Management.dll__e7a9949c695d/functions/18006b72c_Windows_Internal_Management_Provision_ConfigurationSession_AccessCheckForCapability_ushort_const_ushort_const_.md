# Windows::Internal::Management::Provision::ConfigurationSession::AccessCheckForCapability(ushort const *,ushort const *,int)

- ea: `0x18006b72c`
- end: `0x18006b8e9`
- name: `?AccessCheckForCapability@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEBG0H@Z`
- size: `445`
- prototype: `__int64 __fastcall(const unsigned __int16 *, wchar_t *SubStr, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006c9d0`

## callees

- `0x18000a284`
- `0x18000a2a4`
- `0x180014af0`
- `0x180017204`
- `0x180017284`
- `0x180018f88`
- `0x1800199f8`
- `0x180019fb8`
- `0x18006b72c`
- `0x18006b8f0`
- `0x18006c4c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006b7ba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006b7ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b7a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b7a4`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18006b75f`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18006b75f`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18006b890`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18006b890`
- `ntdll!RtlIsMultiSessionSku` at `0x18006b820`
- `ntdll!RtlIsMultiSessionSku` at `0x18006b820`

## string_xrefs

- `0x18006b786`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006b7c8`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006b85e`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`

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
0x18006b72c  mov     [rsp-18h+arg_0], rbx
0x18006b731  mov     [rsp-18h+arg_8], rsi
0x18006b736  push    rbp
0x18006b737  push    rdi
0x18006b738  push    r14
0x18006b73a  mov     rbp, rsp
0x18006b73d  sub     rsp, 50h
0x18006b741  mov     edi, r8d
0x18006b744  mov     rsi, rdx
0x18006b747  mov     r14, rcx
0x18006b74a  mov     [rbp+var_18], 0
0x18006b74e  mov     [rbp+var_16], 0
0x18006b752  mov     [rbp+Pid], 0
0x18006b759  lea     rdx, [rbp+Pid]; Pid
0x18006b75d  xor     ecx, ecx; Binding
0x18006b75f  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18006b765  cmp     eax, 6BDh
0x18006b76a  jz      loc_18006B810
0x18006b770  lea     rcx, [rbp+var_18]; this
0x18006b774  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x18006b779  mov     ebx, eax
0x18006b77b  test    eax, eax
0x18006b77d  jns     short loc_18006B79C
0x18006b77f  mov     rcx, [rbp+18h]; this
0x18006b783  mov     r9d, eax; char *
0x18006b786  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006b78d  mov     edx, 181h; void *
0x18006b792  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b797  jmp     loc_18006B8CB
0x18006b79c  mov     [rbp+TokenHandle], 0
0x18006b7a4  call    cs:__imp_GetCurrentThread
0x18006b7aa  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006b7ae  mov     edx, 8; DesiredAccess
0x18006b7b3  lea     r8d, [rdx-7]; OpenAsSelf
0x18006b7b7  mov     rcx, rax; ThreadHandle
0x18006b7ba  call    cs:__imp_OpenThreadToken
0x18006b7c0  test    eax, eax
0x18006b7c2  jnz     short loc_18006B7E9
0x18006b7c4  mov     rcx, [rbp+18h]; this
0x18006b7c8  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006b7cf  mov     edx, 184h; void *
0x18006b7d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006b7d9  mov     ebx, eax
0x18006b7db  lea     rcx, [rbp+TokenHandle]
0x18006b7df  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006b7e4  jmp     loc_18006B8CB
0x18006b7e9  mov     [rbp+var_30], 0
0x18006b7f0  lea     rdx, [rbp+var_30]; int *
0x18006b7f4  mov     rcx, [rbp+TokenHandle]; void *
0x18006b7f8  call    ?CheckThreadAdmin@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEAXPEAH@Z; Windows::Internal::Management::Provision::ConfigurationSession::CheckThreadAdmin(void *,int *)
0x18006b7fd  test    eax, eax
0x18006b7ff  js      short loc_18006B817
0x18006b801  cmp     [rbp+var_30], 1
0x18006b805  jnz     short loc_18006B817
0x18006b807  lea     rcx, [rbp+TokenHandle]
0x18006b80b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006b810  xor     ebx, ebx
0x18006b812  jmp     loc_18006B8CB
0x18006b817  lea     rcx, [rbp+var_18]; this
0x18006b81b  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x18006b820  call    cs:__imp_RtlIsMultiSessionSku
0x18006b826  test    al, al
0x18006b828  jnz     loc_18006B8BD
0x18006b82e  mov     [rbp+var_20], 0
0x18006b836  xor     edx, edx
0x18006b838  lea     rcx, [rbp+var_20]
0x18006b83c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006b841  lea     r9, [rbp+var_20]; unsigned __int16 **
0x18006b845  mov     r8d, edi; int
0x18006b848  mov     rdx, rsi; SubStr
0x18006b84b  mov     rcx, r14; unsigned __int16 *
0x18006b84e  call    ?QueryCapabilityRequired@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEBG0HPEAPEAG@Z; Windows::Internal::Management::Provision::ConfigurationSession::QueryCapabilityRequired(ushort const *,ushort const *,int,ushort * *)
0x18006b853  mov     ebx, eax
0x18006b855  test    eax, eax
0x18006b857  jns     short loc_18006B880
0x18006b859  mov     edx, 199h; void *
0x18006b85e  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006b865  mov     r9d, eax; char *
0x18006b868  mov     rcx, [rbp+18h]; this
0x18006b86c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b871  nop
0x18006b872  lea     rcx, [rbp+var_20]
0x18006b876  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006b87b  jmp     loc_18006B7DB
0x18006b880  mov     [rbp+arg_18], 0
0x18006b884  lea     r8, [rbp+arg_18]
0x18006b888  mov     rdx, [rbp+var_20]
0x18006b88c  mov     rcx, [rbp+TokenHandle]
0x18006b890  call    cs:__imp_CapabilityCheck
0x18006b896  mov     ebx, eax
0x18006b898  test    eax, eax
0x18006b89a  jns     short loc_18006B8A3
0x18006b89c  mov     edx, 19Ch
0x18006b8a1  jmp     short loc_18006B85E
0x18006b8a3  lea     rcx, [rbp+var_20]
0x18006b8a7  cmp     [rbp+arg_18], 1
0x18006b8ab  jnz     short loc_18006B8B7
0x18006b8ad  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006b8b2  jmp     loc_18006B807
0x18006b8b7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006b8bc  nop
0x18006b8bd  lea     rcx, [rbp+TokenHandle]
0x18006b8c1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006b8c6  mov     ebx, 80070005h
0x18006b8cb  lea     rcx, [rbp+var_18]; this
0x18006b8cf  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18006b8d4  mov     eax, ebx
0x18006b8d6  mov     rbx, [rsp+50h+arg_0]
0x18006b8db  mov     rsi, [rsp+50h+arg_8]
0x18006b8e0  add     rsp, 50h
0x18006b8e4  pop     r14
0x18006b8e6  pop     rdi
0x18006b8e7  pop     rbp
0x18006b8e8  retn
```
