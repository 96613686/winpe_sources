# RetailDemoUserAgent::EnsureForegroundPrivilegeInitialized(void)

- ea: `0x18003ac20`
- end: `0x18003ad29`
- name: `?EnsureForegroundPrivilegeInitialized@RetailDemoUserAgent@@AEAAJXZ`
- size: `265`
- prototype: `int(RetailDemoUserAgent *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003e178`

## callees

- `0x1800068f0`
- `0x180006cf4`
- `0x180007114`
- `0x1800076b0`
- `0x180008bbc`
- `0x18000aa7c`
- `0x18001c904`
- `0x18003ac20`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003ac62`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003ac62`
- `SHCORE!IUnknown_QueryService` at `0x18003acab`
- `SHCORE!IUnknown_QueryService` at `0x18003acab`

## string_xrefs

- `0x18003acef`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RetailDemoUserAgent::EnsureForegroundPrivilegeInitialized(RetailDemoUserAgent *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  RTL_SRWLOCK *v4; // rbx
  IUnknown **v5; // rax
  HRESULT v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  void *ppvOut; // [rsp+48h] [rbp+28h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp+30h] BYREF
  char v21; // [rsp+58h] [rbp+38h] BYREF

  wil::AcquireSRWLockShared(&SRWLock, &RetailDemoUserAgent::s_lockForegroundControl);
  if ( RetailDemoUserAgent::s_foregroundControl )
    goto LABEL_10;
  v4 = SRWLock;
  if ( SRWLock )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&SRWLock);
    ReleaseSRWLockShared(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&SRWLock);
  }
  SRWLock = 0;
  ppvOut = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v2, v3);
  v5 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk(this, &v21);
  v6 = IUnknown_QueryService(
         *v5,
         &IID_IRequestTrustedComponentForegroundControlInitialization,
         &GUID_2a239388_fc85_4077_981e_9e4205cf9451,
         &ppvOut);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21, v7, v8);
  if ( v6 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(void *, GUID *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &CLSID_RetailDemoUserAgent);
    v6 = v11;
    if ( v11 < 0 )
    {
      v9 = (unsigned int)v11;
      v10 = 575;
      goto LABEL_8;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v12, v13);
LABEL_10:
    v6 = 0;
    goto LABEL_11;
  }
  v9 = (unsigned int)v6;
  v10 = 574;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
    (const char *)v9,
    savedregs);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvOut, v14, v15);
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&SRWLock);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003ac20  push    rbp
0x18003ac22  push    rbx
0x18003ac23  push    rdi; int
0x18003ac24  mov     rbp, rsp
0x18003ac27  sub     rsp, 20h
0x18003ac2b  mov     rdi, rcx
0x18003ac2e  lea     rdx, ?s_lockForegroundControl@RetailDemoUserAgent@@0Vsrwlock@wil@@A; wil::srwlock RetailDemoUserAgent::s_lockForegroundControl
0x18003ac35  lea     rcx, [rbp+SRWLock]
0x18003ac39  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x18003ac3e  nop
0x18003ac3f  cmp     cs:?s_foregroundControl@RetailDemoUserAgent@@0V?$ComPtr@UITrustedComponentForegroundControl@@@WRL@Microsoft@@A, 0; Microsoft::WRL::ComPtr<ITrustedComponentForegroundControl> RetailDemoUserAgent::s_foregroundControl
0x18003ac47  jnz     loc_18003AD14
0x18003ac4d  mov     rbx, [rbp+SRWLock]
0x18003ac51  test    rbx, rbx
0x18003ac54  jz      short loc_18003AC71
0x18003ac56  lea     rcx, [rbp+SRWLock]; this
0x18003ac5a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003ac5f  mov     rcx, rbx; SRWLock
0x18003ac62  call    cs:__imp_ReleaseSRWLockShared
0x18003ac68  lea     rcx, [rbp+SRWLock]; this
0x18003ac6c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003ac71  mov     [rbp+SRWLock], 0
0x18003ac79  mov     [rbp+ppvOut], 0
0x18003ac81  lea     rcx, [rbp+ppvOut]
0x18003ac85  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ac8a  lea     rdx, [rbp+arg_18]
0x18003ac8e  mov     rcx, rdi
0x18003ac91  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x18003ac96  lea     r9, [rbp+ppvOut]; ppvOut
0x18003ac9a  lea     r8, _GUID_2a239388_fc85_4077_981e_9e4205cf9451; riid
0x18003aca1  lea     rdx, IID_IRequestTrustedComponentForegroundControlInitialization; guidService
0x18003aca8  mov     rcx, [rax]; punk
0x18003acab  call    cs:__imp_IUnknown_QueryService
0x18003acb1  mov     ebx, eax
0x18003acb3  lea     rcx, [rbp+arg_18]
0x18003acb7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003acbc  test    ebx, ebx
0x18003acbe  jns     short loc_18003ACCA
0x18003acc0  mov     r9d, ebx
0x18003acc3  mov     edx, 23Eh
0x18003acc8  jmp     short loc_18003ACEF
0x18003acca  mov     rcx, [rbp+ppvOut]
0x18003acce  mov     rax, [rcx]
0x18003acd1  lea     rdx, CLSID_RetailDemoUserAgent
0x18003acd8  mov     rax, [rax+18h]
0x18003acdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ace1  mov     ebx, eax
0x18003ace3  test    eax, eax
0x18003ace5  jns     short loc_18003AD0B
0x18003ace7  mov     r9d, eax; char *
0x18003acea  mov     edx, 23Fh; void *
0x18003acef  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003acf6  mov     rcx, [rbp+18h]; this
0x18003acfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003acff  nop
0x18003ad00  lea     rcx, [rbp+ppvOut]
0x18003ad04  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ad09  jmp     short loc_18003AD16
0x18003ad0b  lea     rcx, [rbp+ppvOut]
0x18003ad0f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ad14  xor     ebx, ebx
0x18003ad16  lea     rcx, [rbp+SRWLock]
0x18003ad1a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003ad1f  mov     eax, ebx
0x18003ad21  add     rsp, 20h
0x18003ad25  pop     rdi
0x18003ad26  pop     rbx
0x18003ad27  pop     rbp
0x18003ad28  retn
```
