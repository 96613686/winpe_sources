# NgcIsoRpcClientNew::BindIfNecessaryUnsafe(void)

- ea: `0x1800650bc`
- end: `0x180065281`
- name: `?BindIfNecessaryUnsafe@NgcIsoRpcClientNew@@AEAAJXZ`
- size: `453`
- prototype: `__int64 __fastcall(NgcIsoRpcClientNew *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800695a4`

## callees

- `0x180007670`
- `0x18000d62c`
- `0x18003f5a8`
- `0x18006469c`
- `0x1800647c4`
- `0x1800647ec`
- `0x18006482c`
- `0x1800650bc`
- `0x180069140`
- `0x18006af18`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180065121`
- `RPCRT4!RpcStringBindingComposeW` at `0x180065121`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180065165`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180065165`
- `RPCRT4!RpcEpResolveBinding` at `0x1800651a3`
- `RPCRT4!RpcEpResolveBinding` at `0x1800651a3`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800651fa`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800651fa`

## string_xrefs

- `0x1800651ef`: `NT Authority\Local Service`
- `0x180065134`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x180065176`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x18006520b`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcIsoRpcClientNew::BindIfNecessaryUnsafe(NgcIsoRpcClientNew *this)
{
  char *v1; // rdi
  _QWORD *v2; // rax
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  RPC_STATUS v6; // eax
  __int64 v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rax
  int Options; // [rsp+20h] [rbp-60h]
  unsigned int Optionsa; // [rsp+20h] [rbp-60h]
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-40h] BYREF
  RPC_WSTR StringBinding; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v14[8]; // [rsp+50h] [rbp-30h] BYREF
  std::_Ref_count_base *v15; // [rsp+58h] [rbp-28h]
  RPC_SECURITY_QOS SecurityQOS; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v1 = (char *)this + 8;
  v2 = (_QWORD *)*((_QWORD *)this + 1);
  if ( v2 && *v2 )
    return 0;
  StringBinding = 0;
  v4 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &StringBinding);
  v5 = v4;
  if ( v4 >= 0 )
  {
    Binding = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &Binding,
      0);
    v6 = RpcBindingFromStringBindingW(StringBinding, &Binding);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v6 = RpcEpResolveBinding(Binding, qword_18008F070);
      v5 = v6;
      if ( v6 >= 0 )
      {
        SecurityQOS.Version = 1;
        SecurityQOS.Capabilities = 1;
        SecurityQOS.ImpersonationType = 3;
        SecurityQOS.IdentityTracking = 1;
        v8 = RpcBindingSetAuthInfoExW(Binding, (RPC_WSTR)L"NT Authority\\Local Service", 6u, 0xAu, 0, 0, &SecurityQOS);
        if ( !v8 )
        {
          v9 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
                 v14,
                 &Binding);
          std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(
            v1,
            v9);
          if ( v15 )
            std::_Ref_count_base::_Decref(v15);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Binding);
          v5 = 0;
          goto LABEL_17;
        }
        v5 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xB3,
               (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\NgcIsoRpcClient.h",
               (const char *)v8,
               Optionsa);
        goto LABEL_9;
      }
      v7 = 162;
    }
    else
    {
      v7 = 158;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\NgcIsoRpcClient.h",
      (const char *)(unsigned int)v6,
      Options);
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Binding);
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x99,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\client\\NgcIsoRpcClient.h",
    (const char *)(unsigned int)v4,
    Options);
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringBinding);
  return v5;
}

```

## disassembly

```asm
0x1800650bc  mov     [rsp-8+arg_8], rbx
0x1800650c1  mov     [rsp-8+arg_10], rdi
0x1800650c6  push    rbp
0x1800650c7  mov     rbp, rsp
0x1800650ca  sub     rsp, 80h
0x1800650d1  mov     rax, cs:__security_cookie
0x1800650d8  xor     rax, rsp
0x1800650db  mov     [rbp+var_10], rax
0x1800650df  lea     rdi, [rcx+8]
0x1800650e3  mov     rax, [rdi]
0x1800650e6  test    rax, rax
0x1800650e9  jz      short loc_1800650F8
0x1800650eb  cmp     qword ptr [rax], 0
0x1800650ef  jz      short loc_1800650F8
0x1800650f1  xor     eax, eax
0x1800650f3  jmp     loc_180065260
0x1800650f8  mov     [rbp+var_38], 0
0x180065100  lea     rax, [rbp+var_38]
0x180065104  mov     [rsp+80h+StringBinding], rax; StringBinding
0x180065109  mov     [rsp+80h+Options], 0; int
0x180065112  xor     r9d, r9d; Endpoint
0x180065115  xor     r8d, r8d; NetworkAddr
0x180065118  lea     rdx, ProtSeq; "ncalrpc"
0x18006511f  xor     ecx, ecx; ObjUuid
0x180065121  call    cs:__imp_RpcStringBindingComposeW
0x180065127  mov     ebx, eax
0x180065129  test    eax, eax
0x18006512b  jns     short loc_18006514A
0x18006512d  mov     rcx, [rbp+8]; this
0x180065131  mov     r9d, eax; char *
0x180065134  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18006513b  mov     edx, 99h; void *
0x180065140  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065145  jmp     loc_180065255
0x18006514a  mov     [rbp+Binding], 0
0x180065152  xor     edx, edx
0x180065154  lea     rcx, [rbp+Binding]
0x180065158  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18006515d  lea     rdx, [rbp+Binding]; Binding
0x180065161  mov     rcx, [rbp+var_38]; StringBinding
0x180065165  call    cs:__imp_RpcBindingFromStringBindingW
0x18006516b  mov     ebx, eax
0x18006516d  test    eax, eax
0x18006516f  jns     short loc_180065198
0x180065171  mov     edx, 9Eh; void *
0x180065176  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18006517d  mov     r9d, eax; char *
0x180065180  mov     rcx, [rbp+8]; this
0x180065184  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065189  nop
0x18006518a  lea     rcx, [rbp+Binding]
0x18006518e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180065193  jmp     loc_180065255
0x180065198  lea     rdx, qword_18008F070; IfSpec
0x18006519f  mov     rcx, [rbp+Binding]; Binding
0x1800651a3  call    cs:__imp_RpcEpResolveBinding
0x1800651a9  mov     ebx, eax
0x1800651ab  test    eax, eax
0x1800651ad  jns     short loc_1800651B6
0x1800651af  mov     edx, 0A2h
0x1800651b4  jmp     short loc_180065176
0x1800651b6  mov     eax, 1
0x1800651bb  mov     [rbp+var_20.Version], eax
0x1800651be  mov     [rbp+var_20.Capabilities], eax
0x1800651c1  mov     [rbp+var_20.ImpersonationType], 3
0x1800651c8  mov     [rbp+var_20.IdentityTracking], eax
0x1800651cb  lea     rax, [rbp+var_20]
0x1800651cf  mov     [rsp+80h+SecurityQOS], rax; SecurityQOS
0x1800651d4  mov     dword ptr [rsp+80h+StringBinding], 0; AuthzSvc
0x1800651dc  mov     [rsp+80h+Options], 0; unsigned int
0x1800651e5  mov     r9d, 0Ah; AuthnSvc
0x1800651eb  lea     r8d, [r9-4]; AuthnLevel
0x1800651ef  lea     rdx, ServerPrincName; "NT Authority\\Local Service"
0x1800651f6  mov     rcx, [rbp+Binding]; Binding
0x1800651fa  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180065200  test    eax, eax
0x180065202  jz      short loc_180065223
0x180065204  mov     rcx, [rbp+8]; this
0x180065208  mov     r9d, eax; char *
0x18006520b  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180065212  mov     edx, 0B3h; void *
0x180065217  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006521c  mov     ebx, eax
0x18006521e  jmp     loc_18006518A
0x180065223  lea     rdx, [rbp+Binding]
0x180065227  lea     rcx, [rbp+var_30]
0x18006522b  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x180065230  mov     rdx, rax
0x180065233  mov     rcx, rdi
0x180065236  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x18006523b  mov     rcx, [rbp+var_28]; this
0x18006523f  test    rcx, rcx
0x180065242  jz      short loc_18006524A
0x180065244  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180065249  nop
0x18006524a  lea     rcx, [rbp+Binding]
0x18006524e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180065253  xor     ebx, ebx
0x180065255  lea     rcx, [rbp+var_38]
0x180065259  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006525e  mov     eax, ebx
0x180065260  mov     rcx, [rbp+var_10]
0x180065264  xor     rcx, rsp; StackCookie
0x180065267  call    __security_check_cookie
0x18006526c  lea     r11, [rsp+80h+var_s0]
0x180065274  mov     rbx, [r11+18h]
0x180065278  mov     rdi, [r11+20h]
0x18006527c  mov     rsp, r11
0x18006527f  pop     rbp
0x180065280  retn
```
