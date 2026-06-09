# NgcIsoRpcClient::Bind(void)

- ea: `0x180064f04`
- end: `0x1800650b6`
- name: `?Bind@NgcIsoRpcClient@@QEAAJXZ`
- size: `434`
- prototype: `__int64 __fastcall(NgcIsoRpcClient *__hidden this)`
- caller_count: `44`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005e7c8`
- `0x18005e960`
- `0x18005eb04`
- `0x18005ec98`
- `0x18005ee08`
- `0x18005ef84`
- `0x18005f100`
- `0x18005f2d4`
- `0x18005f4b8`
- `0x18005f614`
- `0x18005f790`
- `0x18005f964`
- `0x18005fc2c`
- `0x18005fe14`
- `0x18005ffa4`
- `0x180060168`
- `0x180060348`
- `0x180060614`
- `0x1800607bc`
- `0x180060980`
- `0x180060b28`
- `0x180060d3c`
- `0x180060ed4`
- `0x180061104`
- `0x180061280`
- `0x1800613fc`
- `0x180061594`
- `0x180061830`
- `0x1800619c8`
- `0x180061b44`
- `0x180061d38`
- `0x180061f4c`
- `0x180062134`
- `0x1800622b0`
- `0x180062594`
- `0x18006293c`
- `0x180062c00`
- `0x180062e34`
- `0x180063028`
- `0x1800631d0`
- `0x18006346c`
- `0x180063604`
- `0x180063780`
- `0x180063928`

## callees

- `0x180007670`
- `0x18000a168`
- `0x18000d62c`
- `0x1800647c4`
- `0x1800647ec`
- `0x180064f04`
- `0x180069140`
- `0x18006af18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180064f27`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180064f27`
- `RPCRT4!RpcStringBindingComposeW` at `0x180064f5a`
- `RPCRT4!RpcStringBindingComposeW` at `0x180064f5a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180064f9e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180064f9e`
- `RPCRT4!RpcEpResolveBinding` at `0x180064fdb`
- `RPCRT4!RpcEpResolveBinding` at `0x180064fdb`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180065032`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180065032`

## string_xrefs

- `0x180064ff2`: `NT Authority\Local Service`
- `0x180064f6a`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x180064fb3`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x180065040`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`

## pseudocode

```c
__int64 __fastcall NgcIsoRpcClient::Bind(RTL_SRWLOCK *this)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  RPC_STATUS v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // eax
  int Options; // [rsp+20h] [rbp-50h]
  unsigned int Optionsa; // [rsp+20h] [rbp-50h]
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-30h] BYREF
  RPC_WSTR StringBinding; // [rsp+48h] [rbp-28h] BYREF
  RTL_SRWLOCK *v12; // [rsp+50h] [rbp-20h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  AcquireSRWLockExclusive(this);
  v12 = this;
  StringBinding = 0;
  v2 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &StringBinding);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\NgcIsoRpcClient.h",
      (const char *)(unsigned int)v2,
      Options);
    goto LABEL_14;
  }
  Binding = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &Binding,
    0);
  v4 = RpcBindingFromStringBindingW(StringBinding, &Binding);
  v3 = v4;
  if ( v4 < 0 )
  {
    v5 = 37;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\NgcIsoRpcClient.h",
      (const char *)(unsigned int)v4,
      Options);
LABEL_6:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Binding);
    goto LABEL_14;
  }
  v4 = RpcEpResolveBinding(Binding, qword_18008F070);
  v3 = v4;
  if ( v4 < 0 )
  {
    v5 = 41;
    goto LABEL_5;
  }
  SecurityQOS.ImpersonationType = 3;
  SecurityQOS.Version = 1;
  SecurityQOS.Capabilities = 1;
  SecurityQOS.IdentityTracking = 1;
  v6 = RpcBindingSetAuthInfoExW(Binding, (RPC_WSTR)L"NT Authority\\Local Service", 6u, 0xAu, 0, 0, &SecurityQOS);
  if ( v6 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x3A,
           (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\NgcIsoRpcClient.h",
           (const char *)v6,
           Optionsa);
    goto LABEL_6;
  }
  if ( &this[1] != (RTL_SRWLOCK *)&Binding )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &this[1],
      Binding);
    Binding = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Binding);
  v3 = 0;
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringBinding);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  return v3;
}

```

## disassembly

```asm
0x180064f04  mov     [rsp-8+arg_8], rbx
0x180064f09  mov     [rsp-8+arg_10], rdi
0x180064f0e  push    rbp
0x180064f0f  mov     rbp, rsp
0x180064f12  sub     rsp, 70h
0x180064f16  mov     rax, cs:__security_cookie
0x180064f1d  xor     rax, rsp
0x180064f20  mov     [rbp+var_8], rax
0x180064f24  mov     rdi, rcx
0x180064f27  call    cs:__imp_AcquireSRWLockExclusive
0x180064f2d  lea     rax, [rbp+var_28]
0x180064f31  mov     [rbp+var_20], rdi
0x180064f35  mov     [rsp+70h+StringBinding], rax; StringBinding
0x180064f3a  lea     rdx, ProtSeq; "ncalrpc"
0x180064f41  xor     r9d, r9d; Endpoint
0x180064f44  mov     [rsp+70h+Options], 0; int
0x180064f4d  xor     r8d, r8d; NetworkAddr
0x180064f50  mov     [rbp+var_28], 0
0x180064f58  xor     ecx, ecx; ObjUuid
0x180064f5a  call    cs:__imp_RpcStringBindingComposeW
0x180064f60  mov     ebx, eax
0x180064f62  test    eax, eax
0x180064f64  jns     short loc_180064F83
0x180064f66  mov     rcx, [rbp+8]; this
0x180064f6a  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180064f71  mov     r9d, eax; char *
0x180064f74  mov     edx, 20h ; ' '; void *
0x180064f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064f7e  jmp     loc_180065084
0x180064f83  xor     edx, edx
0x180064f85  mov     [rbp+Binding], 0
0x180064f8d  lea     rcx, [rbp+Binding]
0x180064f91  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180064f96  mov     rcx, [rbp+var_28]; StringBinding
0x180064f9a  lea     rdx, [rbp+Binding]; Binding
0x180064f9e  call    cs:__imp_RpcBindingFromStringBindingW
0x180064fa4  mov     ebx, eax
0x180064fa6  test    eax, eax
0x180064fa8  jns     short loc_180064FD0
0x180064faa  mov     edx, 25h ; '%'; void *
0x180064faf  mov     rcx, [rbp+8]; this
0x180064fb3  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180064fba  mov     r9d, eax; char *
0x180064fbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064fc2  lea     rcx, [rbp+Binding]
0x180064fc6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180064fcb  jmp     loc_180065084
0x180064fd0  mov     rcx, [rbp+Binding]; Binding
0x180064fd4  lea     rdx, qword_18008F070; IfSpec
0x180064fdb  call    cs:__imp_RpcEpResolveBinding
0x180064fe1  mov     ebx, eax
0x180064fe3  test    eax, eax
0x180064fe5  jns     short loc_180064FEE
0x180064fe7  mov     edx, 29h ; ')'
0x180064fec  jmp     short loc_180064FAF
0x180064fee  mov     rcx, [rbp+Binding]; Binding
0x180064ff2  lea     rdx, ServerPrincName; "NT Authority\\Local Service"
0x180064ff9  mov     eax, 1
0x180064ffe  mov     [rbp+var_18.ImpersonationType], 3
0x180065005  mov     r9d, 0Ah; AuthnSvc
0x18006500b  mov     [rbp+var_18.Version], eax
0x18006500e  mov     [rbp+var_18.Capabilities], eax
0x180065011  mov     [rbp+var_18.IdentityTracking], eax
0x180065014  lea     rax, [rbp+var_18]
0x180065018  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x18006501d  mov     dword ptr [rsp+70h+StringBinding], 0; AuthzSvc
0x180065025  lea     r8d, [r9-4]; AuthnLevel
0x180065029  mov     [rsp+70h+Options], 0; unsigned int
0x180065032  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180065038  test    eax, eax
0x18006503a  jz      short loc_18006505B
0x18006503c  mov     rcx, [rbp+8]; this
0x180065040  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180065047  mov     r9d, eax; char *
0x18006504a  mov     edx, 3Ah ; ':'; void *
0x18006504f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180065054  mov     ebx, eax
0x180065056  jmp     loc_180064FC2
0x18006505b  lea     rcx, [rdi+8]
0x18006505f  lea     rax, [rbp+Binding]
0x180065063  cmp     rcx, rax
0x180065066  jz      short loc_180065079
0x180065068  mov     rdx, [rbp+Binding]
0x18006506c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180065071  mov     [rbp+Binding], 0
0x180065079  lea     rcx, [rbp+Binding]
0x18006507d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180065082  xor     ebx, ebx
0x180065084  lea     rcx, [rbp+var_28]
0x180065088  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006508d  lea     rcx, [rbp+var_20]
0x180065091  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180065096  mov     eax, ebx
0x180065098  mov     rcx, [rbp+var_8]
0x18006509c  xor     rcx, rsp; StackCookie
0x18006509f  call    __security_check_cookie
0x1800650a4  lea     r11, [rsp+70h+var_s0]
0x1800650a9  mov     rbx, [r11+18h]
0x1800650ad  mov     rdi, [r11+20h]
0x1800650b1  mov     rsp, r11
0x1800650b4  pop     rbp
0x1800650b5  retn
```
