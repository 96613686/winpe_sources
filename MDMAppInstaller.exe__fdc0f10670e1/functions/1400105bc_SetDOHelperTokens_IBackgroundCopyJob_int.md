# SetDOHelperTokens(IBackgroundCopyJob *,int)

- ea: `0x1400105bc`
- end: `0x140010690`
- name: `?SetDOHelperTokens@@YAJPEAUIBackgroundCopyJob@@H@Z`
- size: `212`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140010a2c`

## callees

- `0x140007318`
- `0x14000904c`
- `0x14000934c`
- `0x1400105bc`
- `0x140012c58`
- `0x14001c010`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x140010623`
- `ole32!CoSetProxyBlanket` at `0x140010623`

## pseudocode

```c
__int64 __fastcall SetDOHelperTokens(struct IBackgroundCopyJob *a1)
{
  HRESULT v1; // ebx
  void *v2; // rdx
  IUnknown *pProxy; // [rsp+50h] [rbp+10h] BYREF
  void *v5; // [rsp+60h] [rbp+20h] BYREF
  void *v6; // [rsp+68h] [rbp+28h] BYREF

  pProxy = 0;
  v6 = 0;
  v1 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *, IUnknown **))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2,
         &pProxy);
  if ( v1 >= 0 )
  {
    v1 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x40u);
    if ( v1 >= 0 )
    {
      wil::run_as_self_failfast(&v5);
      v1 = ((__int64 (__fastcall *)(IUnknown *))pProxy->lpVtbl[1].Release)(pProxy);
      if ( v1 >= 0 )
        v1 = ((__int64 (__fastcall *)(IUnknown *, __int64))pProxy->lpVtbl[1].QueryInterface)(pProxy, 2);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(
        &v5,
        v2);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v6);
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>((__int64 *)&pProxy);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1400105bc  mov     [rsp-8+arg_8], rbx
0x1400105c1  push    rbp
0x1400105c2  mov     rbp, rsp
0x1400105c5  sub     rsp, 40h
0x1400105c9  mov     [rbp+pProxy], 0
0x1400105d1  mov     [rbp+arg_18], 0
0x1400105d9  mov     rax, [rcx]
0x1400105dc  lea     r8, [rbp+pProxy]
0x1400105e0  lea     rdx, _GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2
0x1400105e7  mov     rax, [rax]
0x1400105ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400105ef  mov     ebx, eax
0x1400105f1  test    eax, eax
0x1400105f3  js      short loc_140010670
0x1400105f5  mov     [rsp+40h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1400105fd  mov     [rsp+40h+pAuthInfo], 0; pAuthInfo
0x140010606  mov     [rsp+40h+dwImpLevel], 3; dwImpLevel
0x14001060e  mov     [rsp+40h+dwAuthnLevel], 0; dwAuthnLevel
0x140010616  xor     r9d, r9d; pServerPrincName
0x140010619  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x14001061c  mov     r8d, edx; dwAuthzSvc
0x14001061f  mov     rcx, [rbp+pProxy]; pProxy
0x140010623  call    cs:__imp_CoSetProxyBlanket
0x140010629  mov     ebx, eax
0x14001062b  test    eax, eax
0x14001062d  js      short loc_140010670
0x14001062f  lea     rcx, [rbp+arg_10]
0x140010633  call    ?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self_failfast(void)
0x140010638  nop
0x140010639  mov     rcx, [rbp+pProxy]
0x14001063d  mov     rax, [rcx]
0x140010640  mov     rax, [rax+28h]
0x140010644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010649  mov     ebx, eax
0x14001064b  test    eax, eax
0x14001064d  js      short loc_140010666
0x14001064f  mov     rcx, [rbp+pProxy]
0x140010653  mov     rax, [rcx]
0x140010656  mov     edx, 2
0x14001065b  mov     rax, [rax+18h]
0x14001065f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010664  mov     ebx, eax
0x140010666  lea     rcx, [rbp+arg_10]
0x14001066a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x14001066f  nop
0x140010670  lea     rcx, [rbp+arg_18]
0x140010674  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140010679  nop
0x14001067a  lea     rcx, [rbp+pProxy]
0x14001067e  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x140010683  mov     eax, ebx
0x140010685  mov     rbx, [rsp+40h+arg_8]
0x14001068a  add     rsp, 40h
0x14001068e  pop     rbp
0x14001068f  retn
```
