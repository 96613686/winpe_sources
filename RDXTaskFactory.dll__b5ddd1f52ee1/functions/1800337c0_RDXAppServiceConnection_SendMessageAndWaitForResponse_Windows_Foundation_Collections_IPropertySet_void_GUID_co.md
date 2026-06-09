# RDXAppServiceConnection::SendMessageAndWaitForResponse(Windows::Foundation::Collections::IPropertySet *,void *,_GUID const &,void * *)

- ea: `0x1800337c0`
- end: `0x180033a05`
- name: `?SendMessageAndWaitForResponse@RDXAppServiceConnection@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@PEAXAEBU_GUID@@PEAPEAX@Z`
- size: `581`
- prototype: `__int64 __fastcall(RDXAppServiceConnection *__hidden this, struct Windows::Foundation::Collections::IPropertySet *, void *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180033a10`

## callees

- `0x180006cf4`
- `0x1800076b0`
- `0x18000e330`
- `0x18001094c`
- `0x180032b98`
- `0x180032fe0`
- `0x1800337c0`
- `0x180050010`

## string_xrefs

- `0x1800339b2`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180033839`: `shellcommon\shell\retaildemo\util\rdxappserviceconnection.cpp`
- `0x18003387f`: `shellcommon\shell\retaildemo\util\rdxappserviceconnection.cpp`
- `0x1800338ce`: `shellcommon\shell\retaildemo\util\rdxappserviceconnection.cpp`
- `0x180033913`: `shellcommon\shell\retaildemo\util\rdxappserviceconnection.cpp`
- `0x180033954`: `shellcommon\shell\retaildemo\util\rdxappserviceconnection.cpp`
- `0x18003397f`: `shellcommon\shell\retaildemo\util\rdxappserviceconnection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RDXAppServiceConnection::SendMessageAndWaitForResponse(
        RDXAppServiceConnection *this,
        struct Windows::Foundation::Collections::IPropertySet *a2,
        void *a3,
        const struct _GUID *a4,
        void **a5)
{
  void **v9; // rsi
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  const char *v14; // r9
  __int64 result; // rax
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 *v21; // [rsp+28h] [rbp-30h] BYREF
  _BYTE v22[40]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 *v24; // [rsp+60h] [rbp+8h] BYREF

  v9 = a5;
  *a5 = 0;
  v21 = 0;
  wil::AcquireSRWLockShared(v22, (char *)this + 120);
  wil::com_ptr_t<Windows::ApplicationModel::AppService::IAppServiceConnection,wil::err_exception_policy>::operator=(
    &v21,
    (char *)this + 128);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v22);
  try
  {
    if ( !v21 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\rdxappserviceconnection.cpp",
        (const char *)0x800704D4LL,
        v20[0]);
    v24 = 0;
    v10 = *v21;
    v24 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, struct Windows::Foundation::Collections::IPropertySet *, __int64 **))(v10 + 88))(
            v21,
            a2,
            &v24);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\rdxappserviceconnection.cpp",
        (const char *)(unsigned int)v11,
        v20[0]);
    v13 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(
            (int (__fastcall ***)(_QWORD, GUID *, __int64 *))v24,
            v12,
            a3);
    if ( v13 == -2147023673 )
    {
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v24);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v21);
      result = 2147943623LL;
    }
    else
    {
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"shellcommon\\shell\\retaildemo\\util\\rdxappserviceconnection.cpp",
          (const char *)(unsigned int)v13,
          v20[0]);
      *(_QWORD *)v20 = 0;
      v16 = *v24;
      *(_QWORD *)v20 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64 *, int *))(v16 + 64))(v24, v20);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"shellcommon\\shell\\retaildemo\\util\\rdxappserviceconnection.cpp",
          (const char *)(unsigned int)v17,
          v20[0]);
      LODWORD(a5) = 0;
      v18 = (*(__int64 (__fastcall **)(_QWORD, void ***))(**(_QWORD **)v20 + 56LL))(*(_QWORD *)v20, &a5);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"shellcommon\\shell\\retaildemo\\util\\rdxappserviceconnection.cpp",
          (const char *)(unsigned int)v18,
          v20[0]);
      if ( (_DWORD)a5 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x92,
          (unsigned int)"shellcommon\\shell\\retaildemo\\util\\rdxappserviceconnection.cpp",
          (const char *)0x800704D4LL,
          v20[0]);
      v19 = (***(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))v20)(*(_QWORD *)v20, a4, v9);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v19,
          v20[0]);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(v20);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v24);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v21);
      result = 0;
    }
  }
  catch ( ... )
  {
    LODWORD(a5) = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0x95,
                    (unsigned int)"shellcommon\\shell\\retaildemo\\util\\rdxappserviceconnection.cpp",
                    v14);
    return (unsigned int)a5;
  }
  return result;
}

```

## disassembly

```asm
0x1800337c0  mov     rax, rsp
0x1800337c3  mov     [rax+10h], rbx
0x1800337c7  mov     [rax+18h], rsi
0x1800337cb  push    rdi
0x1800337cc  push    r14
0x1800337ce  push    r15
0x1800337d0  sub     rsp, 40h
0x1800337d4  mov     r15, r9
0x1800337d7  mov     rdi, r8
0x1800337da  mov     r14, rdx
0x1800337dd  mov     rbx, rcx
0x1800337e0  mov     rsi, [rsp+58h+arg_20]
0x1800337e8  mov     qword ptr [rsi], 0
0x1800337ef  mov     qword ptr [rax-30h], 0
0x1800337f7  lea     rdx, [rcx+78h]
0x1800337fb  lea     rcx, [rax-28h]
0x1800337ff  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x180033804  lea     rdx, [rbx+80h]
0x18003380b  lea     rcx, [rsp+58h+var_30]
0x180033810  call    ??4?$com_ptr_t@UIAppServiceConnection@AppService@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<Windows::ApplicationModel::AppService::IAppServiceConnection,wil::err_exception_policy>::operator=(wil::com_ptr_t<Windows::ApplicationModel::AppService::IAppServiceConnection,wil::err_exception_policy> const &)
0x180033815  lea     rcx, [rsp+58h+var_28]
0x18003381a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003381f  mov     rcx, [rsp+58h+var_30]
0x180033824  test    rcx, rcx
0x180033827  setz    al
0x18003382a  mov     r10, [rsp+58h]
0x18003382f  test    al, al
0x180033831  jz      short loc_18003384D
0x180033833  mov     r9d, 800704D4h; char *
0x180033839  lea     r8, aShellcommonShe; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180033840  mov     edx, 85h; void *
0x180033845  mov     rcx, r10; this
0x180033848  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003384d  mov     [rsp+58h+arg_0], 0
0x180033856  mov     rax, [rcx]
0x180033859  mov     [rsp+58h+arg_0], 0
0x180033862  lea     r8, [rsp+58h+arg_0]
0x180033867  mov     rdx, r14
0x18003386a  mov     rax, [rax+58h]
0x18003386e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033873  mov     rcx, [rsp+58h]; this
0x180033878  test    eax, eax
0x18003387a  jns     short loc_180033890
0x18003387c  mov     r9d, eax; char *
0x18003387f  lea     r8, aShellcommonShe; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180033886  mov     edx, 88h; void *
0x18003388b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033890  mov     r8, rdi
0x180033893  mov     rcx, [rsp+58h+arg_0]
0x180033898  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)
0x18003389d  mov     ebx, 800704C7h
0x1800338a2  cmp     eax, ebx
0x1800338a4  jnz     short loc_1800338C2
0x1800338a6  lea     rcx, [rsp+58h+arg_0]
0x1800338ab  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800338b0  nop
0x1800338b1  lea     rcx, [rsp+58h+var_30]
0x1800338b6  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800338bb  mov     eax, ebx
0x1800338bd  jmp     loc_1800339F0
0x1800338c2  mov     rcx, [rsp+58h]; this
0x1800338c7  test    eax, eax
0x1800338c9  jns     short loc_1800338DF
0x1800338cb  mov     r9d, eax; char *
0x1800338ce  lea     r8, aShellcommonShe; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800338d5  mov     edx, 8Bh; void *
0x1800338da  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800338df  mov     qword ptr [rsp+58h+var_38], 0
0x1800338e8  mov     rcx, [rsp+58h+arg_0]
0x1800338ed  mov     rax, [rcx]
0x1800338f0  mov     qword ptr [rsp+58h+var_38], 0; int
0x1800338f9  lea     rdx, [rsp+58h+var_38]
0x1800338fe  mov     rax, [rax+40h]
0x180033902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033907  mov     rcx, [rsp+58h]; this
0x18003390c  test    eax, eax
0x18003390e  jns     short loc_180033924
0x180033910  mov     r9d, eax; char *
0x180033913  lea     r8, aShellcommonShe; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003391a  mov     edx, 8Dh; void *
0x18003391f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033924  mov     dword ptr [rsp+58h+arg_20], 0
0x18003392f  mov     rcx, qword ptr [rsp+58h+var_38]
0x180033934  mov     rax, [rcx]
0x180033937  lea     rdx, [rsp+58h+arg_20]
0x18003393f  mov     rax, [rax+38h]
0x180033943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033948  mov     rcx, [rsp+58h]; this
0x18003394d  test    eax, eax
0x18003394f  jns     short loc_180033965
0x180033951  mov     r9d, eax; char *
0x180033954  lea     r8, aShellcommonShe; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003395b  mov     edx, 91h; void *
0x180033960  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033965  cmp     dword ptr [rsp+58h+arg_20], 0
0x18003396d  setnz   al
0x180033970  mov     rcx, [rsp+58h]; this
0x180033975  test    al, al
0x180033977  jz      short loc_180033990
0x180033979  mov     r9d, 800704D4h; char *
0x18003397f  lea     r8, aShellcommonShe; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180033986  mov     edx, 92h; void *
0x18003398b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033990  mov     rcx, qword ptr [rsp+58h+var_38]
0x180033995  mov     rax, [rcx]
0x180033998  mov     r8, rsi
0x18003399b  mov     rdx, r15
0x18003399e  mov     rax, [rax]
0x1800339a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339a6  mov     rcx, [rsp+58h]; this
0x1800339ab  test    eax, eax
0x1800339ad  jns     short loc_1800339C4
0x1800339af  mov     r9d, eax; char *
0x1800339b2  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800339b9  mov     edx, 1CBEh; void *
0x1800339be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800339c4  lea     rcx, [rsp+58h+var_38]
0x1800339c9  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800339ce  nop
0x1800339cf  lea     rcx, [rsp+58h+arg_0]
0x1800339d4  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800339d9  nop
0x1800339da  lea     rcx, [rsp+58h+var_30]
0x1800339df  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x1800339e4  nop
0x1800339e5  xor     eax, eax
0x1800339e7  jmp     short loc_1800339F0
0x1800339e9  mov     eax, dword ptr [rsp+58h+arg_20]
0x1800339f0  mov     rbx, [rsp+58h+arg_8]
0x1800339f5  mov     rsi, [rsp+58h+arg_10]
0x1800339fa  add     rsp, 40h
0x1800339fe  pop     r15
0x180033a00  pop     r14
0x180033a02  pop     rdi
0x180033a03  retn
```
