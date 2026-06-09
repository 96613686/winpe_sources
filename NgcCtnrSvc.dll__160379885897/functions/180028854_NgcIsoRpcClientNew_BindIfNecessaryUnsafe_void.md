# NgcIsoRpcClientNew::BindIfNecessaryUnsafe(void)

- ea: `0x180028854`
- end: `0x180028a32`
- name: `?BindIfNecessaryUnsafe@NgcIsoRpcClientNew@@AEAAJXZ`
- size: `478`
- prototype: `__int64 __fastcall(NgcIsoRpcClientNew *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042590`

## callees

- `0x180023278`
- `0x1800232a0`
- `0x180024b80`
- `0x180028854`
- `0x180028a38`
- `0x180028a88`
- `0x180028ab8`
- `0x180028b20`
- `0x18002c640`
- `0x1800447c4`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800289a4`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800289a4`
- `RPCRT4!RpcEpResolveBinding` at `0x180028947`
- `RPCRT4!RpcEpResolveBinding` at `0x180028947`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180028903`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180028903`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800288b9`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800288b9`

## string_xrefs

- `0x180028999`: `NT Authority\Local Service`
- `0x1800288d2`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x18002891a`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`
- `0x1800289bb`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\client\NgcIsoRpcClient.h`

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
      v6 = RpcEpResolveBinding(Binding, qword_1800845E0);
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
          std::shared_ptr<std::wstring>::operator=(v1, v9);
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
0x180028854  mov     [rsp-8+arg_8], rbx
0x180028859  mov     [rsp-8+arg_10], rdi
0x18002885e  push    rbp
0x18002885f  mov     rbp, rsp
0x180028862  sub     rsp, 80h
0x180028869  mov     rax, cs:__security_cookie
0x180028870  xor     rax, rsp
0x180028873  mov     [rbp+var_10], rax
0x180028877  lea     rdi, [rcx+8]
0x18002887b  mov     rax, [rdi]
0x18002887e  test    rax, rax
0x180028881  jz      short loc_180028890
0x180028883  cmp     qword ptr [rax], 0
0x180028887  jz      short loc_180028890
0x180028889  xor     eax, eax
0x18002888b  jmp     loc_180028A10
0x180028890  mov     [rbp+var_38], 0
0x180028898  lea     rax, [rbp+var_38]
0x18002889c  mov     [rsp+80h+StringBinding], rax; StringBinding
0x1800288a1  mov     [rsp+80h+Options], 0; int
0x1800288aa  xor     r9d, r9d; Endpoint
0x1800288ad  xor     r8d, r8d; NetworkAddr
0x1800288b0  lea     rdx, ProtSeq; "ncalrpc"
0x1800288b7  xor     ecx, ecx; ObjUuid
0x1800288b9  call    cs:__imp_RpcStringBindingComposeW
0x1800288c0  nop     dword ptr [rax+rax+00h]
0x1800288c5  mov     ebx, eax
0x1800288c7  test    eax, eax
0x1800288c9  jns     short loc_1800288E8
0x1800288cb  mov     rcx, [rbp+8]; this
0x1800288cf  mov     r9d, eax; char *
0x1800288d2  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800288d9  mov     edx, 99h; void *
0x1800288de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800288e3  jmp     loc_180028A05
0x1800288e8  mov     [rbp+Binding], 0
0x1800288f0  xor     edx, edx
0x1800288f2  lea     rcx, [rbp+Binding]
0x1800288f6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800288fb  lea     rdx, [rbp+Binding]; Binding
0x1800288ff  mov     rcx, [rbp+var_38]; StringBinding
0x180028903  call    cs:__imp_RpcBindingFromStringBindingW
0x18002890a  nop     dword ptr [rax+rax+00h]
0x18002890f  mov     ebx, eax
0x180028911  test    eax, eax
0x180028913  jns     short loc_18002893C
0x180028915  mov     edx, 9Eh; void *
0x18002891a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180028921  mov     r9d, eax; char *
0x180028924  mov     rcx, [rbp+8]; this
0x180028928  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002892d  nop
0x18002892e  lea     rcx, [rbp+Binding]
0x180028932  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180028937  jmp     loc_180028A05
0x18002893c  lea     rdx, qword_1800845E0; IfSpec
0x180028943  mov     rcx, [rbp+Binding]; Binding
0x180028947  call    cs:__imp_RpcEpResolveBinding
0x18002894e  nop     dword ptr [rax+rax+00h]
0x180028953  mov     ebx, eax
0x180028955  test    eax, eax
0x180028957  jns     short loc_180028960
0x180028959  mov     edx, 0A2h
0x18002895e  jmp     short loc_18002891A
0x180028960  mov     eax, 1
0x180028965  mov     [rbp+var_20.Version], eax
0x180028968  mov     [rbp+var_20.Capabilities], eax
0x18002896b  mov     [rbp+var_20.ImpersonationType], 3
0x180028972  mov     [rbp+var_20.IdentityTracking], eax
0x180028975  lea     rax, [rbp+var_20]
0x180028979  mov     [rsp+80h+SecurityQOS], rax; SecurityQOS
0x18002897e  mov     dword ptr [rsp+80h+StringBinding], 0; AuthzSvc
0x180028986  mov     [rsp+80h+Options], 0; unsigned int
0x18002898f  mov     r9d, 0Ah; AuthnSvc
0x180028995  lea     r8d, [r9-4]; AuthnLevel
0x180028999  lea     rdx, ServerPrincName; "NT Authority\\Local Service"
0x1800289a0  mov     rcx, [rbp+Binding]; Binding
0x1800289a4  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800289ab  nop     dword ptr [rax+rax+00h]
0x1800289b0  test    eax, eax
0x1800289b2  jz      short loc_1800289D3
0x1800289b4  mov     rcx, [rbp+8]; this
0x1800289b8  mov     r9d, eax; char *
0x1800289bb  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800289c2  mov     edx, 0B3h; void *
0x1800289c7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800289cc  mov     ebx, eax
0x1800289ce  jmp     loc_18002892E
0x1800289d3  lea     rdx, [rbp+Binding]
0x1800289d7  lea     rcx, [rbp+var_30]
0x1800289db  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1800289e0  mov     rdx, rax
0x1800289e3  mov     rcx, rdi
0x1800289e6  call    ??4?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<std::wstring>::operator=(std::shared_ptr<std::wstring> &&)
0x1800289eb  mov     rcx, [rbp+var_28]; this
0x1800289ef  test    rcx, rcx
0x1800289f2  jz      short loc_1800289FA
0x1800289f4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800289f9  nop
0x1800289fa  lea     rcx, [rbp+Binding]
0x1800289fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180028a03  xor     ebx, ebx
0x180028a05  lea     rcx, [rbp+var_38]
0x180028a09  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180028a0e  mov     eax, ebx
0x180028a10  mov     rcx, [rbp+var_10]
0x180028a14  xor     rcx, rsp; StackCookie
0x180028a17  call    __security_check_cookie
0x180028a1c  lea     r11, [rsp+80h+var_s0]
0x180028a24  mov     rbx, [r11+18h]
0x180028a28  mov     rdi, [r11+20h]
0x180028a2c  mov     rsp, r11
0x180028a2f  pop     rbp
0x180028a30  retn
```
