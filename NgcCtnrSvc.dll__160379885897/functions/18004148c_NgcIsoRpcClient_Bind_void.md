# NgcIsoRpcClient::Bind(void)

- ea: `0x18004148c`
- end: `0x18004165d`
- name: `?Bind@NgcIsoRpcClient@@QEAAJXZ`
- size: `465`
- prototype: `__int64 __fastcall(NgcIsoRpcClient *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003db58`
- `0x18003dca8`

## callees

- `0x180012e40`
- `0x180023278`
- `0x1800232a0`
- `0x180028a88`
- `0x180028b20`
- `0x18002c640`
- `0x18004148c`
- `0x1800447c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800414af`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800414af`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800415d2`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800415d2`
- `RPCRT4!RpcEpResolveBinding` at `0x180041575`
- `RPCRT4!RpcEpResolveBinding` at `0x180041575`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180041532`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180041532`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800414e8`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800414e8`

## string_xrefs

- `0x180041592`: `NT Authority\Local Service`
- `0x1800414fe`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x18004154d`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x1800415e6`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`

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
  v4 = RpcEpResolveBinding(Binding, qword_1800845E0);
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
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v12);
  return v3;
}

```

## disassembly

```asm
0x18004148c  mov     [rsp-8+arg_8], rbx
0x180041491  mov     [rsp-8+arg_10], rdi
0x180041496  push    rbp
0x180041497  mov     rbp, rsp
0x18004149a  sub     rsp, 70h
0x18004149e  mov     rax, cs:__security_cookie
0x1800414a5  xor     rax, rsp
0x1800414a8  mov     [rbp+var_8], rax
0x1800414ac  mov     rdi, rcx
0x1800414af  call    cs:__imp_AcquireSRWLockExclusive
0x1800414b6  nop     dword ptr [rax+rax+00h]
0x1800414bb  lea     rax, [rbp+var_28]
0x1800414bf  mov     [rbp+var_20], rdi
0x1800414c3  mov     [rsp+70h+StringBinding], rax; StringBinding
0x1800414c8  lea     rdx, ProtSeq; "ncalrpc"
0x1800414cf  xor     r9d, r9d; Endpoint
0x1800414d2  mov     [rsp+70h+Options], 0; int
0x1800414db  xor     r8d, r8d; NetworkAddr
0x1800414de  mov     [rbp+var_28], 0
0x1800414e6  xor     ecx, ecx; ObjUuid
0x1800414e8  call    cs:__imp_RpcStringBindingComposeW
0x1800414ef  nop     dword ptr [rax+rax+00h]
0x1800414f4  mov     ebx, eax
0x1800414f6  test    eax, eax
0x1800414f8  jns     short loc_180041517
0x1800414fa  mov     rcx, [rbp+8]; this
0x1800414fe  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180041505  mov     r9d, eax; char *
0x180041508  mov     edx, 20h ; ' '; void *
0x18004150d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041512  jmp     loc_18004162A
0x180041517  xor     edx, edx
0x180041519  mov     [rbp+Binding], 0
0x180041521  lea     rcx, [rbp+Binding]
0x180041525  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18004152a  mov     rcx, [rbp+var_28]; StringBinding
0x18004152e  lea     rdx, [rbp+Binding]; Binding
0x180041532  call    cs:__imp_RpcBindingFromStringBindingW
0x180041539  nop     dword ptr [rax+rax+00h]
0x18004153e  mov     ebx, eax
0x180041540  test    eax, eax
0x180041542  jns     short loc_18004156A
0x180041544  mov     edx, 25h ; '%'; void *
0x180041549  mov     rcx, [rbp+8]; this
0x18004154d  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180041554  mov     r9d, eax; char *
0x180041557  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004155c  lea     rcx, [rbp+Binding]
0x180041560  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180041565  jmp     loc_18004162A
0x18004156a  mov     rcx, [rbp+Binding]; Binding
0x18004156e  lea     rdx, qword_1800845E0; IfSpec
0x180041575  call    cs:__imp_RpcEpResolveBinding
0x18004157c  nop     dword ptr [rax+rax+00h]
0x180041581  mov     ebx, eax
0x180041583  test    eax, eax
0x180041585  jns     short loc_18004158E
0x180041587  mov     edx, 29h ; ')'
0x18004158c  jmp     short loc_180041549
0x18004158e  mov     rcx, [rbp+Binding]; Binding
0x180041592  lea     rdx, ServerPrincName; "NT Authority\\Local Service"
0x180041599  mov     eax, 1
0x18004159e  mov     [rbp+var_18.ImpersonationType], 3
0x1800415a5  mov     r9d, 0Ah; AuthnSvc
0x1800415ab  mov     [rbp+var_18.Version], eax
0x1800415ae  mov     [rbp+var_18.Capabilities], eax
0x1800415b1  mov     [rbp+var_18.IdentityTracking], eax
0x1800415b4  lea     rax, [rbp+var_18]
0x1800415b8  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x1800415bd  mov     dword ptr [rsp+70h+StringBinding], 0; AuthzSvc
0x1800415c5  lea     r8d, [r9-4]; AuthnLevel
0x1800415c9  mov     [rsp+70h+Options], 0; unsigned int
0x1800415d2  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800415d9  nop     dword ptr [rax+rax+00h]
0x1800415de  test    eax, eax
0x1800415e0  jz      short loc_180041601
0x1800415e2  mov     rcx, [rbp+8]; this
0x1800415e6  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800415ed  mov     r9d, eax; char *
0x1800415f0  mov     edx, 3Ah ; ':'; void *
0x1800415f5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800415fa  mov     ebx, eax
0x1800415fc  jmp     loc_18004155C
0x180041601  lea     rcx, [rdi+8]
0x180041605  lea     rax, [rbp+Binding]
0x180041609  cmp     rcx, rax
0x18004160c  jz      short loc_18004161F
0x18004160e  mov     rdx, [rbp+Binding]
0x180041612  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180041617  mov     [rbp+Binding], 0
0x18004161f  lea     rcx, [rbp+Binding]
0x180041623  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180041628  xor     ebx, ebx
0x18004162a  lea     rcx, [rbp+var_28]
0x18004162e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180041633  lea     rcx, [rbp+var_20]
0x180041637  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18004163c  mov     eax, ebx
0x18004163e  mov     rcx, [rbp+var_8]
0x180041642  xor     rcx, rsp; StackCookie
0x180041645  call    __security_check_cookie
0x18004164a  lea     r11, [rsp+70h+var_s0]
0x18004164f  mov     rbx, [r11+18h]
0x180041653  mov     rdi, [r11+20h]
0x180041657  mov     rsp, r11
0x18004165a  pop     rbp
0x18004165b  retn
```
