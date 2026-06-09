# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetCollectionItemNamesActivity,_lambda_480b7113f048e1bf4eeab7b5e12618fd_>(Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetCollectionItemNamesActivity &,_lambda_480b7113f048e1bf4eeab7b5e12618fd_ &&)

- ea: `0x1800cf320`
- end: `0x1800cf524`
- name: `??$ExecuteOnSafeThreadWithActivity@VGetCollectionItemNamesActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@V_lambda_480b7113f048e1bf4eeab7b5e12618fd_@@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEAVGetCollectionItemNamesActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$$QEAV_lambda_480b7113f048e1bf4eeab7b5e12618fd_@@@Z`
- size: `516`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180169670`

## callees

- `0x18000dfe4`
- `0x180010688`
- `0x180016cf4`
- `0x180035b7c`
- `0x180038db8`
- `0x18005dde0`
- `0x180061e60`
- `0x180064888`
- `0x1800a2834`
- `0x1800ce314`
- `0x1800cf320`
- `0x1800e93e0`
- `0x1801063dc`
- `0x180152cc0`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800cf3e7`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800cf3e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf3cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf3cd`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cf356`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cf356`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cf4a8`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cf4a8`

## string_xrefs

- `0x1800cf36b`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cf40f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cf4b9`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cf4d5`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall EffectiveUserContext::ExecuteOnSafeThreadWithActivity<Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetCollectionItemNamesActivity,_lambda_480b7113f048e1bf4eeab7b5e12618fd_>(
        __int64 a1,
        __int64 a2,
        struct wil::details::IFailureCallback *a3,
        __int64 a4)
{
  HRESULT ApartmentType; // eax
  __int64 *v9; // rax
  __int64 v10; // rdi
  DWORD CurrentThreadId; // eax
  int v12; // esi
  int v13; // edi
  int v14; // eax
  int v16; // [rsp+20h] [rbp-99h]
  int v17; // [rsp+20h] [rbp-99h]
  APTTYPE pAptType; // [rsp+30h] [rbp-89h] BYREF
  __int64 v19; // [rsp+38h] [rbp-81h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+40h] [rbp-79h] BYREF
  __int64 v21; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v23[6]; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v24[128]; // [rsp+90h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, &pAptQualifier);
  if ( ApartmentType >= 0 )
  {
    if ( pAptType && pAptType != APTTYPE_MAINSTA )
    {
      wil::run_as_self(&v19);
      _lambda_480b7113f048e1bf4eeab7b5e12618fd_::operator()(a4);
      *(_OWORD *)a2 = 0;
      *(_OWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 32) = 0;
      *(_QWORD *)(a2 + 40) = 0;
      *(_QWORD *)(a2 + 48) = 0;
      *(_DWORD *)(a2 + 56) = 0;
      *(_QWORD *)(a2 + 64) = 0;
      *(_BYTE *)(a2 + 72) = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v19);
      return a2;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.h",
      (const char *)(unsigned int)ApartmentType,
      v16);
  }
  Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(v22);
  v21 = 0;
  v23[0] = a1;
  v23[1] = a3;
  v23[2] = a4;
  v23[3] = &v21;
  v23[4] = v22;
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_9e28e7cb8907cc070188e6f05ca7cbad_ &>,_lambda_9e28e7cb8907cc070188e6f05ca7cbad_ &>(
                    &v19,
                    v23);
  v10 = *v9;
  *v9 = 0;
  if ( v19 )
  {
    v19 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v17 = v10;
  v12 = SHTaskPoolQueueTask(0, 0, CurrentThreadId, 0);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.h",
      (const char *)(unsigned int)v12,
      v10);
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v22[0] + 16LL))(v22[0], 0);
  wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
    a3,
    (wil::ActivityThreadWatcher *)v24);
  if ( v13 < 0 )
  {
    if ( v21 )
    {
      v14 = SetRestrictedErrorInfo();
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4F,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.h",
          (const char *)(unsigned int)v14,
          v17);
    }
  }
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.h",
      (const char *)(unsigned int)v13,
      v17);
  wil::ActivityThreadWatcher::ActivityThreadWatcher(a2, v24);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v24);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v21);
  std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(v22);
  return a2;
}

```

## disassembly

```asm
0x1800cf320  push    rbp
0x1800cf322  push    rbx
0x1800cf323  push    rsi
0x1800cf324  push    rdi
0x1800cf325  push    r14
0x1800cf327  push    r15
0x1800cf329  lea     rbp, [rsp-2Fh]
0x1800cf32e  sub     rsp, 0E8h
0x1800cf335  mov     rdi, r9
0x1800cf338  mov     r14, r8
0x1800cf33b  mov     rbx, rdx
0x1800cf33e  mov     rsi, rcx
0x1800cf341  xor     r15d, r15d
0x1800cf344  mov     [rsp+110h+pAptType], r15d
0x1800cf349  mov     [rbp+57h+pAptQualifier], r15d
0x1800cf34d  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800cf351  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800cf356  call    cs:__imp_CoGetApartmentType
0x1800cf35c  mov     rcx, [rbp+5Fh]; this
0x1800cf360  test    eax, eax
0x1800cf362  jns     loc_1800CF421
0x1800cf368  mov     r9d, eax; char *
0x1800cf36b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cf372  lea     edx, [r15+29h]; void *
0x1800cf376  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cf37b  lea     rcx, [rbp+57h+var_C0]
0x1800cf37f  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800cf384  nop
0x1800cf385  mov     [rbp+57h+var_C8], r15
0x1800cf389  mov     [rbp+57h+var_B0], rsi
0x1800cf38d  mov     [rbp+57h+var_A8], r14
0x1800cf391  mov     [rbp+57h+var_A0], rdi
0x1800cf395  lea     rax, [rbp+57h+var_C8]
0x1800cf399  mov     [rbp+57h+var_98], rax
0x1800cf39d  lea     rax, [rbp+57h+var_C0]
0x1800cf3a1  mov     [rbp+57h+var_90], rax
0x1800cf3a5  lea     rdx, [rbp+57h+var_B0]
0x1800cf3a9  lea     rcx, [rsp+110h+var_D8]
0x1800cf3ae  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_9e28e7cb8907cc070188e6f05ca7cbad_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_9e28e7cb8907cc070188e6f05ca7cbad_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_9e28e7cb8907cc070188e6f05ca7cbad_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_9e28e7cb8907cc070188e6f05ca7cbad_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_9e28e7cb8907cc070188e6f05ca7cbad_ &>,_lambda_9e28e7cb8907cc070188e6f05ca7cbad_ &>(_lambda_9e28e7cb8907cc070188e6f05ca7cbad_ &)
0x1800cf3b3  mov     rdi, [rax]
0x1800cf3b6  mov     [rax], r15
0x1800cf3b9  mov     rcx, [rsp+110h+var_D8]
0x1800cf3be  test    rcx, rcx
0x1800cf3c1  jz      short loc_1800CF3CD
0x1800cf3c3  mov     [rsp+110h+var_D8], r15
0x1800cf3c8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800cf3cd  call    cs:__imp_GetCurrentThreadId
0x1800cf3d3  mov     [rsp+110h+var_E8], r15
0x1800cf3d8  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800cf3dd  xor     r9d, r9d
0x1800cf3e0  mov     r8d, eax
0x1800cf3e3  xor     edx, edx
0x1800cf3e5  xor     ecx, ecx
0x1800cf3e7  call    cs:__imp_SHTaskPoolQueueTask
0x1800cf3ed  mov     esi, eax
0x1800cf3ef  test    rdi, rdi
0x1800cf3f2  jz      short loc_1800CF404
0x1800cf3f4  mov     rdx, [rdi]
0x1800cf3f7  mov     rcx, rdi
0x1800cf3fa  mov     rax, [rdx+10h]
0x1800cf3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf403  nop
0x1800cf404  mov     rcx, [rbp+5Fh]; this
0x1800cf408  test    esi, esi
0x1800cf40a  jns     short loc_1800CF47A
0x1800cf40c  mov     r9d, esi; char *
0x1800cf40f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cf416  mov     edx, 46h ; 'F'; void *
0x1800cf41b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cf421  mov     eax, [rsp+110h+pAptType]
0x1800cf425  test    eax, eax
0x1800cf427  jz      loc_1800CF37B
0x1800cf42d  cmp     eax, 3
0x1800cf430  jz      loc_1800CF37B
0x1800cf436  lea     rcx, [rsp+110h+var_D8]
0x1800cf43b  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cf440  nop
0x1800cf441  mov     rcx, rdi
0x1800cf444  call    ??R_lambda_480b7113f048e1bf4eeab7b5e12618fd_@@QEBA@XZ; _lambda_480b7113f048e1bf4eeab7b5e12618fd_::operator()(void)
0x1800cf449  xorps   xmm0, xmm0
0x1800cf44c  movups  xmmword ptr [rbx], xmm0
0x1800cf44f  movups  xmmword ptr [rbx+10h], xmm0
0x1800cf453  mov     [rbx+20h], r15
0x1800cf457  mov     [rbx+28h], r15
0x1800cf45b  mov     [rbx+30h], r15
0x1800cf45f  mov     [rbx+38h], r15d
0x1800cf463  mov     [rbx+40h], r15
0x1800cf467  mov     [rbx+48h], r15b
0x1800cf46b  lea     rcx, [rsp+110h+var_D8]
0x1800cf470  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800cf475  jmp     loc_1800CF511
0x1800cf47a  mov     rcx, [rbp+57h+var_C0]
0x1800cf47e  mov     rax, [rcx]
0x1800cf481  xor     edx, edx
0x1800cf483  mov     rax, [rax+10h]
0x1800cf487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf48c  mov     edi, eax
0x1800cf48e  lea     rdx, [rbp+57h+var_80]; this
0x1800cf492  mov     rcx, r14; struct wil::details::IFailureCallback *
0x1800cf495  call    ?ContinueOnCurrentThread@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x1800cf49a  nop
0x1800cf49b  test    edi, edi
0x1800cf49d  jns     short loc_1800CF4CA
0x1800cf49f  mov     rcx, [rbp+57h+var_C8]
0x1800cf4a3  test    rcx, rcx
0x1800cf4a6  jz      short loc_1800CF4CA
0x1800cf4a8  call    cs:__imp_SetRestrictedErrorInfo
0x1800cf4ae  mov     rcx, [rbp+5Fh]; this
0x1800cf4b2  test    eax, eax
0x1800cf4b4  jns     short loc_1800CF4CA
0x1800cf4b6  mov     r9d, eax; char *
0x1800cf4b9  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cf4c0  mov     edx, 4Fh ; 'O'; void *
0x1800cf4c5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cf4ca  mov     rcx, [rbp+5Fh]; this
0x1800cf4ce  test    edi, edi
0x1800cf4d0  jns     short loc_1800CF4E7
0x1800cf4d2  mov     r9d, edi; char *
0x1800cf4d5  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cf4dc  mov     edx, 51h ; 'Q'; void *
0x1800cf4e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cf4e7  lea     rdx, [rbp+57h+var_80]
0x1800cf4eb  mov     rcx, rbx
0x1800cf4ee  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800cf4f3  nop
0x1800cf4f4  lea     rcx, [rbp+57h+var_80]; this
0x1800cf4f8  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800cf4fd  nop
0x1800cf4fe  lea     rcx, [rbp+57h+var_C8]
0x1800cf502  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800cf507  nop
0x1800cf508  lea     rcx, [rbp+57h+var_C0]
0x1800cf50c  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800cf511  mov     rax, rbx
0x1800cf514  add     rsp, 0E8h
0x1800cf51b  pop     r15
0x1800cf51d  pop     r14
0x1800cf51f  pop     rdi
0x1800cf520  pop     rsi
0x1800cf521  pop     rbx
0x1800cf522  pop     rbp
0x1800cf523  retn
```
