# SetHelperTokens(IBackgroundCopyJob *,int)

- ea: `0x18012c5d0`
- end: `0x18012c775`
- name: `?SetHelperTokens@@YAJPEAUIBackgroundCopyJob@@H@Z`
- size: `421`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18012a874`

## callees

- `0x1800117dc`
- `0x18001c9a4`
- `0x18001d090`
- `0x18004d158`
- `0x18012c5d0`
- `0x18012c888`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18012c645`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18012c645`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18012c6ae`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18012c6ae`
- `DMCmnUtils!DmRevertToSelf` at `0x18012c707`
- `DMCmnUtils!DmRevertToSelf` at `0x18012c707`
- `DMCmnUtils!DmImpersonate` at `0x18012c6c5`
- `DMCmnUtils!DmImpersonate` at `0x18012c6c5`

## string_xrefs

- `0x18012c71d`: `SetHelperTokens: Reverted succeeded`
- `0x18012c693`: `SetHelperTokens: Impersonating`
- `0x18012c6db`: `SetHelperTokens: Impersonating succeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetHelperTokens(struct IBackgroundCopyJob *a1, int a2)
{
  HRESULT ActiveUserSid; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  IUnknown *pProxy; // [rsp+50h] [rbp+10h] BYREF
  unsigned __int16 *v10; // [rsp+60h] [rbp+20h] BYREF

  pProxy = 0;
  v10 = 0;
  ActiveUserSid = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *, IUnknown **))a1->lpVtbl->QueryInterface)(
                    a1,
                    &GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2,
                    &pProxy);
  v4 = ActiveUserSid;
  if ( ActiveUserSid >= 0 )
  {
    ActiveUserSid = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x40u);
    v4 = ActiveUserSid;
    if ( ActiveUserSid >= 0 )
    {
      if ( a2 )
      {
        ActiveUserSid = ((__int64 (__fastcall *)(IUnknown *))pProxy->lpVtbl[1].Release)(pProxy);
        v4 = ActiveUserSid;
        if ( ActiveUserSid < 0 )
        {
          v5 = 438;
          goto LABEL_5;
        }
      }
      else
      {
        LogTelemetryInfo(L"SetHelperTokens: Impersonating");
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v10,
          0);
        ActiveUserSid = DmGetActiveUserSid(&v10);
        v4 = ActiveUserSid;
        if ( ActiveUserSid < 0 )
        {
          v5 = 443;
          goto LABEL_5;
        }
        ActiveUserSid = DmImpersonate(v10);
        v4 = ActiveUserSid;
        if ( ActiveUserSid < 0 )
        {
          v5 = 444;
          goto LABEL_5;
        }
        LogTelemetryInfo(L"SetHelperTokens: Impersonating succeeded");
        ActiveUserSid = ((__int64 (__fastcall *)(IUnknown *))pProxy->lpVtbl[1].Release)(pProxy);
        v4 = ActiveUserSid;
        if ( ActiveUserSid < 0 )
        {
          v5 = 446;
          goto LABEL_5;
        }
        ActiveUserSid = DmRevertToSelf();
        v4 = ActiveUserSid;
        if ( ActiveUserSid < 0 )
        {
          v5 = 447;
          goto LABEL_5;
        }
        LogTelemetryInfo(L"SetHelperTokens: Reverted succeeded");
      }
      ActiveUserSid = ((__int64 (__fastcall *)(IUnknown *, __int64))pProxy->lpVtbl[1].QueryInterface)(pProxy, 2);
      v4 = ActiveUserSid;
      if ( ActiveUserSid >= 0 )
      {
        v4 = 0;
        goto LABEL_21;
      }
      v5 = 451;
    }
    else
    {
      v5 = 432;
    }
  }
  else
  {
    v5 = 418;
  }
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\bitshelper.cpp",
    (const char *)(unsigned int)ActiveUserSid,
    dwAuthnLevel);
LABEL_21:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&pProxy);
  return v4;
}

```

## disassembly

```asm
0x18012c5d0  mov     [rsp-8+arg_8], rbx
0x18012c5d5  mov     [rsp-8+arg_18], rdi
0x18012c5da  push    rbp
0x18012c5db  mov     rbp, rsp
0x18012c5de  sub     rsp, 40h
0x18012c5e2  mov     edi, edx
0x18012c5e4  mov     [rbp+pProxy], 0
0x18012c5ec  mov     [rbp+arg_10], 0
0x18012c5f4  mov     rax, [rcx]
0x18012c5f7  lea     r8, [rbp+pProxy]
0x18012c5fb  lea     rdx, _GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2
0x18012c602  mov     rax, [rax]
0x18012c605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012c60a  mov     ebx, eax
0x18012c60c  test    eax, eax
0x18012c60e  jns     short loc_18012C617
0x18012c610  mov     edx, 1A2h
0x18012c615  jmp     short loc_18012C656
0x18012c617  mov     [rsp+40h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18012c61f  mov     [rsp+40h+pAuthInfo], 0; pAuthInfo
0x18012c628  mov     [rsp+40h+dwImpLevel], 3; dwImpLevel
0x18012c630  mov     [rsp+40h+dwAuthnLevel], 0; int
0x18012c638  xor     r9d, r9d; pServerPrincName
0x18012c63b  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18012c63e  mov     r8d, edx; dwAuthzSvc
0x18012c641  mov     rcx, [rbp+pProxy]; pProxy
0x18012c645  call    cs:__imp_CoSetProxyBlanket
0x18012c64b  mov     ebx, eax
0x18012c64d  test    eax, eax
0x18012c64f  jns     short loc_18012C66E
0x18012c651  mov     edx, 1B0h; void *
0x18012c656  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x18012c65d  mov     r9d, eax; char *
0x18012c660  mov     rcx, [rbp+8]; this
0x18012c664  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012c669  jmp     loc_18012C750
0x18012c66e  test    edi, edi
0x18012c670  jz      short loc_18012C693
0x18012c672  mov     rcx, [rbp+pProxy]
0x18012c676  mov     rax, [rcx]
0x18012c679  mov     rax, [rax+28h]
0x18012c67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012c682  mov     ebx, eax
0x18012c684  test    eax, eax
0x18012c686  jns     loc_18012C729
0x18012c68c  mov     edx, 1B6h
0x18012c691  jmp     short loc_18012C656
0x18012c693  lea     rcx, aSethelpertoken_1; "SetHelperTokens: Impersonating"
0x18012c69a  call    ?LogTelemetryInfo@@YAXPEBGZZ; LogTelemetryInfo(ushort const *,...)
0x18012c69f  xor     edx, edx
0x18012c6a1  lea     rcx, [rbp+arg_10]
0x18012c6a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18012c6aa  lea     rcx, [rbp+arg_10]
0x18012c6ae  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18012c6b4  mov     ebx, eax
0x18012c6b6  test    eax, eax
0x18012c6b8  jns     short loc_18012C6C1
0x18012c6ba  mov     edx, 1BBh
0x18012c6bf  jmp     short loc_18012C656
0x18012c6c1  mov     rcx, [rbp+arg_10]
0x18012c6c5  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18012c6cb  mov     ebx, eax
0x18012c6cd  test    eax, eax
0x18012c6cf  jns     short loc_18012C6DB
0x18012c6d1  mov     edx, 1BCh
0x18012c6d6  jmp     loc_18012C656
0x18012c6db  lea     rcx, aSethelpertoken_0; "SetHelperTokens: Impersonating succeede"...
0x18012c6e2  call    ?LogTelemetryInfo@@YAXPEBGZZ; LogTelemetryInfo(ushort const *,...)
0x18012c6e7  mov     rcx, [rbp+pProxy]
0x18012c6eb  mov     rax, [rcx]
0x18012c6ee  mov     rax, [rax+28h]
0x18012c6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012c6f7  mov     ebx, eax
0x18012c6f9  test    eax, eax
0x18012c6fb  jns     short loc_18012C707
0x18012c6fd  mov     edx, 1BEh
0x18012c702  jmp     loc_18012C656
0x18012c707  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18012c70d  mov     ebx, eax
0x18012c70f  test    eax, eax
0x18012c711  jns     short loc_18012C71D
0x18012c713  mov     edx, 1BFh
0x18012c718  jmp     loc_18012C656
0x18012c71d  lea     rcx, aSethelpertoken; "SetHelperTokens: Reverted succeeded"
0x18012c724  call    ?LogTelemetryInfo@@YAXPEBGZZ; LogTelemetryInfo(ushort const *,...)
0x18012c729  mov     rcx, [rbp+pProxy]
0x18012c72d  mov     rax, [rcx]
0x18012c730  mov     edx, 2
0x18012c735  mov     rax, [rax+18h]
0x18012c739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012c73e  mov     ebx, eax
0x18012c740  test    eax, eax
0x18012c742  jns     short loc_18012C74E
0x18012c744  mov     edx, 1C3h
0x18012c749  jmp     loc_18012C656
0x18012c74e  xor     ebx, ebx
0x18012c750  lea     rcx, [rbp+arg_10]
0x18012c754  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18012c759  nop
0x18012c75a  lea     rcx, [rbp+pProxy]
0x18012c75e  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x18012c763  mov     eax, ebx
0x18012c765  mov     rbx, [rsp+40h+arg_8]
0x18012c76a  mov     rdi, [rsp+40h+arg_18]
0x18012c76f  add     rsp, 40h
0x18012c773  pop     rbp
0x18012c774  retn
```
