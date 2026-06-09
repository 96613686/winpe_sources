# InstallOfficeScheduledTaskImpl::Start(IUnknown *,ushort *)

- ea: `0x1800146c0`
- end: `0x1800147f6`
- name: `?Start@InstallOfficeScheduledTaskImpl@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `310`
- prototype: `__int64 __fastcall(InstallOfficeScheduledTaskImpl *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x180010740`
- `0x180012120`
- `0x180013740`
- `0x180013944`
- `0x180013aa0`
- `0x1800145c0`
- `0x1800146c0`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800147ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800147ac`

## string_xrefs

- `0x18001470f`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\installofficescheduledtask.cpp`
- `0x18001476a`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\installofficescheduledtask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InstallOfficeScheduledTaskImpl::Start(
        InstallOfficeScheduledTaskImpl *this,
        struct IUnknown *a2,
        unsigned __int16 *a3)
{
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  volatile int *v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v23; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v24[3]; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  InstallOfficeScheduledTaskImpl *v26; // [rsp+68h] [rbp+28h] BYREF
  __int64 v27; // [rsp+78h] [rbp+38h] BYREF

  v23 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23, a2, a3);
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
         &v23);
  v9 = v6;
  if ( v6 >= 0 )
  {
    v27 = 0;
    LODWORD(v26) = 2;
    v24[0] = v23;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27, v7, v8);
    v12 = Microsoft::WRL::Details::MakeAndInitialize<CMarshaledInterface::CMarshalStream,CMarshaledInterface::CMarshalStream,_GUID const &,IUnknown * &,enum MARSHAL_KIND &>(
            &v27,
            &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
            v24,
            &v26);
    v9 = v12;
    if ( v12 >= 0 )
    {
      v26 = this;
      if ( this )
        Microsoft::WRL::Details::SafeUnknownIncrementReference(
          (InstallOfficeScheduledTaskImpl *)((char *)this + 44),
          v13);
      v16 = _lambda_9326158e853d60310880745f3c3138b0_::_lambda_9326158e853d60310880745f3c3138b0_(v24, &v27, &v26);
      CurrentThreadId = GetCurrentThreadId();
      Windows::Internal::ComTaskPool::QueueTask<_lambda_9326158e853d60310880745f3c3138b0_>(
        v19,
        v18,
        CurrentThreadId,
        v16);
      _lambda_9326158e853d60310880745f3c3138b0_::~_lambda_9326158e853d60310880745f3c3138b0_((_lambda_9326158e853d60310880745f3c3138b0_ *)v24);
      if ( this )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler,Microsoft::WRL::FtmBase>::Release(this);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27, v20, v21);
      v9 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\installofficescheduledtask.cpp",
        (const char *)(unsigned int)v12,
        v23);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27, v14, v15);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\installofficescheduledtask.cpp",
      (const char *)(unsigned int)v6,
      v23);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23, v10, v11);
  return v9;
}

```

## disassembly

```asm
0x1800146c0  mov     [rsp-18h+arg_0], rbx
0x1800146c5  push    rbp
0x1800146c6  push    rsi
0x1800146c7  push    rdi
0x1800146c8  mov     rbp, rsp
0x1800146cb  sub     rsp, 40h
0x1800146cf  mov     rdi, rdx
0x1800146d2  mov     rsi, rcx
0x1800146d5  mov     [rbp+var_20], 0
0x1800146dd  mov     rax, [rdx]
0x1800146e0  mov     rbx, [rax]
0x1800146e3  lea     rcx, [rbp+var_20]
0x1800146e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800146ec  lea     r8, [rbp+var_20]
0x1800146f0  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x1800146f7  mov     rcx, rdi
0x1800146fa  mov     rax, rbx
0x1800146fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014702  mov     ebx, eax
0x180014704  test    eax, eax
0x180014706  jns     short loc_180014725
0x180014708  mov     rcx, [rbp+18h]; this
0x18001470c  mov     r9d, eax; char *
0x18001470f  lea     r8, aPcshellShellRe_30; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180014716  mov     edx, 14h; void *
0x18001471b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014720  jmp     loc_1800147DE
0x180014725  mov     [rbp+arg_18], 0
0x18001472d  mov     dword ptr [rbp+arg_8], 2
0x180014734  mov     rax, [rbp+var_20]
0x180014738  mov     [rbp+var_18], rax
0x18001473c  lea     rcx, [rbp+arg_18]
0x180014740  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014745  lea     r9, [rbp+arg_8]
0x180014749  lea     r8, [rbp+var_18]
0x18001474d  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180014754  lea     rcx, [rbp+arg_18]
0x180014758  call    ??$MakeAndInitialize@VCMarshalStream@CMarshaledInterface@@V12@AEBU_GUID@@AEAPEAUIUnknown@@AEAW4MARSHAL_KIND@@@Details@WRL@Microsoft@@YAJPEAPEAVCMarshalStream@CMarshaledInterface@@AEBU_GUID@@AEAPEAUIUnknown@@AEAW4MARSHAL_KIND@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMarshaledInterface::CMarshalStream,CMarshaledInterface::CMarshalStream,_GUID const &,IUnknown * &,MARSHAL_KIND &>(CMarshaledInterface::CMarshalStream * *,_GUID const &,IUnknown * &,MARSHAL_KIND &)
0x18001475d  mov     ebx, eax
0x18001475f  test    eax, eax
0x180014761  jns     short loc_180014786
0x180014763  mov     rcx, [rbp+18h]; this
0x180014767  mov     r9d, eax; char *
0x18001476a  lea     r8, aPcshellShellRe_30; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180014771  mov     edx, 16h; void *
0x180014776  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001477b  lea     rcx, [rbp+arg_18]
0x18001477f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014784  jmp     short loc_1800147DE
0x180014786  mov     [rbp+arg_8], rsi
0x18001478a  test    rsi, rsi
0x18001478d  jz      short loc_180014798
0x18001478f  lea     rcx, [rsi+2Ch]; this
0x180014793  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180014798  lea     r8, [rbp+arg_8]
0x18001479c  lea     rdx, [rbp+arg_18]
0x1800147a0  lea     rcx, [rbp+var_18]
0x1800147a4  call    ??0_lambda_9326158e853d60310880745f3c3138b0_@@QEAA@AEBVCMarshaledInterface@@AEBV?$ComPtr@VInstallOfficeScheduledTaskImpl@@@WRL@Microsoft@@@Z; _lambda_9326158e853d60310880745f3c3138b0_::_lambda_9326158e853d60310880745f3c3138b0_(CMarshaledInterface const &,Microsoft::WRL::ComPtr<InstallOfficeScheduledTaskImpl> const &)
0x1800147a9  mov     rbx, rax
0x1800147ac  call    cs:__imp_GetCurrentThreadId
0x1800147b2  mov     r9, rbx
0x1800147b5  mov     r8d, eax
0x1800147b8  call    ??$QueueTask@V_lambda_9326158e853d60310880745f3c3138b0_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@W4TaskOptions@12@K$$QEAV_lambda_9326158e853d60310880745f3c3138b0_@@@Z; Windows::Internal::ComTaskPool::QueueTask<_lambda_9326158e853d60310880745f3c3138b0_>(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,_lambda_9326158e853d60310880745f3c3138b0_ &&)
0x1800147bd  lea     rcx, [rbp+var_18]; this
0x1800147c1  call    ??1_lambda_9326158e853d60310880745f3c3138b0_@@QEAA@XZ; _lambda_9326158e853d60310880745f3c3138b0_::~_lambda_9326158e853d60310880745f3c3138b0_(void)
0x1800147c6  test    rsi, rsi
0x1800147c9  jz      short loc_1800147D3
0x1800147cb  mov     rcx, rsi
0x1800147ce  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UITaskHandler@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITaskHandler,Microsoft::WRL::FtmBase>::Release(void)
0x1800147d3  lea     rcx, [rbp+arg_18]
0x1800147d7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800147dc  xor     ebx, ebx
0x1800147de  lea     rcx, [rbp+var_20]
0x1800147e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800147e7  mov     eax, ebx
0x1800147e9  mov     rbx, [rsp+40h+arg_0]
0x1800147ee  add     rsp, 40h
0x1800147f2  pop     rdi
0x1800147f3  pop     rsi
0x1800147f4  pop     rbp
0x1800147f5  retn
```
