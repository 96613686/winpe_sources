# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<Windows::Internal::Storage::Cloud::CloudStoreTelemetry::CreateWatcherActivity,_lambda_061383b97839ec58352578f5f7105a46_>(Windows::Internal::Storage::Cloud::CloudStoreTelemetry::CreateWatcherActivity &,_lambda_061383b97839ec58352578f5f7105a46_ &&)

- ea: `0x180107a3c`
- end: `0x180107c40`
- name: `??$ExecuteOnSafeThreadWithActivity@VCreateWatcherActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@V_lambda_061383b97839ec58352578f5f7105a46_@@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEAVCreateWatcherActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$$QEAV_lambda_061383b97839ec58352578f5f7105a46_@@@Z`
- size: `516`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801077c0`

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
- `0x1800e93e0`
- `0x180107a3c`
- `0x1801528e8`
- `0x1801647b4`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x180107b03`
- `SHCORE!SHTaskPoolQueueTask` at `0x180107b03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180107ae9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180107ae9`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180107a72`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180107a72`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x180107bc4`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x180107bc4`

## string_xrefs

- `0x180107a87`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x180107b2b`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x180107bd5`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x180107bf1`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall EffectiveUserContext::ExecuteOnSafeThreadWithActivity<Windows::Internal::Storage::Cloud::CloudStoreTelemetry::CreateWatcherActivity,_lambda_061383b97839ec58352578f5f7105a46_>(
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
      _lambda_061383b97839ec58352578f5f7105a46_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_081922039c5170ed555cfd4a7c7eb3df_ &>,_lambda_081922039c5170ed555cfd4a7c7eb3df_ &>(
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
0x180107a3c  push    rbp
0x180107a3e  push    rbx
0x180107a3f  push    rsi
0x180107a40  push    rdi
0x180107a41  push    r14
0x180107a43  push    r15
0x180107a45  lea     rbp, [rsp-2Fh]
0x180107a4a  sub     rsp, 0E8h
0x180107a51  mov     rdi, r9
0x180107a54  mov     r14, r8
0x180107a57  mov     rbx, rdx
0x180107a5a  mov     rsi, rcx
0x180107a5d  xor     r15d, r15d
0x180107a60  mov     [rsp+110h+pAptType], r15d
0x180107a65  mov     [rbp+57h+pAptQualifier], r15d
0x180107a69  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x180107a6d  lea     rcx, [rsp+110h+pAptType]; pAptType
0x180107a72  call    cs:__imp_CoGetApartmentType
0x180107a78  mov     rcx, [rbp+5Fh]; this
0x180107a7c  test    eax, eax
0x180107a7e  jns     loc_180107B3D
0x180107a84  mov     r9d, eax; char *
0x180107a87  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180107a8e  lea     edx, [r15+29h]; void *
0x180107a92  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180107a97  lea     rcx, [rbp+57h+var_C0]
0x180107a9b  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x180107aa0  nop
0x180107aa1  mov     [rbp+57h+var_C8], r15
0x180107aa5  mov     [rbp+57h+var_B0], rsi
0x180107aa9  mov     [rbp+57h+var_A8], r14
0x180107aad  mov     [rbp+57h+var_A0], rdi
0x180107ab1  lea     rax, [rbp+57h+var_C8]
0x180107ab5  mov     [rbp+57h+var_98], rax
0x180107ab9  lea     rax, [rbp+57h+var_C0]
0x180107abd  mov     [rbp+57h+var_90], rax
0x180107ac1  lea     rdx, [rbp+57h+var_B0]
0x180107ac5  lea     rcx, [rsp+110h+var_D8]
0x180107aca  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_081922039c5170ed555cfd4a7c7eb3df_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_081922039c5170ed555cfd4a7c7eb3df_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_081922039c5170ed555cfd4a7c7eb3df_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_081922039c5170ed555cfd4a7c7eb3df_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_081922039c5170ed555cfd4a7c7eb3df_ &>,_lambda_081922039c5170ed555cfd4a7c7eb3df_ &>(_lambda_081922039c5170ed555cfd4a7c7eb3df_ &)
0x180107acf  mov     rdi, [rax]
0x180107ad2  mov     [rax], r15
0x180107ad5  mov     rcx, [rsp+110h+var_D8]
0x180107ada  test    rcx, rcx
0x180107add  jz      short loc_180107AE9
0x180107adf  mov     [rsp+110h+var_D8], r15
0x180107ae4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180107ae9  call    cs:__imp_GetCurrentThreadId
0x180107aef  mov     [rsp+110h+var_E8], r15
0x180107af4  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x180107af9  xor     r9d, r9d
0x180107afc  mov     r8d, eax
0x180107aff  xor     edx, edx
0x180107b01  xor     ecx, ecx
0x180107b03  call    cs:__imp_SHTaskPoolQueueTask
0x180107b09  mov     esi, eax
0x180107b0b  test    rdi, rdi
0x180107b0e  jz      short loc_180107B20
0x180107b10  mov     rdx, [rdi]
0x180107b13  mov     rcx, rdi
0x180107b16  mov     rax, [rdx+10h]
0x180107b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107b1f  nop
0x180107b20  mov     rcx, [rbp+5Fh]; this
0x180107b24  test    esi, esi
0x180107b26  jns     short loc_180107B96
0x180107b28  mov     r9d, esi; char *
0x180107b2b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180107b32  mov     edx, 46h ; 'F'; void *
0x180107b37  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180107b3d  mov     eax, [rsp+110h+pAptType]
0x180107b41  test    eax, eax
0x180107b43  jz      loc_180107A97
0x180107b49  cmp     eax, 3
0x180107b4c  jz      loc_180107A97
0x180107b52  lea     rcx, [rsp+110h+var_D8]
0x180107b57  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x180107b5c  nop
0x180107b5d  mov     rcx, rdi
0x180107b60  call    ??R_lambda_061383b97839ec58352578f5f7105a46_@@QEBA@XZ; _lambda_061383b97839ec58352578f5f7105a46_::operator()(void)
0x180107b65  xorps   xmm0, xmm0
0x180107b68  movups  xmmword ptr [rbx], xmm0
0x180107b6b  movups  xmmword ptr [rbx+10h], xmm0
0x180107b6f  mov     [rbx+20h], r15
0x180107b73  mov     [rbx+28h], r15
0x180107b77  mov     [rbx+30h], r15
0x180107b7b  mov     [rbx+38h], r15d
0x180107b7f  mov     [rbx+40h], r15
0x180107b83  mov     [rbx+48h], r15b
0x180107b87  lea     rcx, [rsp+110h+var_D8]
0x180107b8c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180107b91  jmp     loc_180107C2D
0x180107b96  mov     rcx, [rbp+57h+var_C0]
0x180107b9a  mov     rax, [rcx]
0x180107b9d  xor     edx, edx
0x180107b9f  mov     rax, [rax+10h]
0x180107ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107ba8  mov     edi, eax
0x180107baa  lea     rdx, [rbp+57h+var_80]; this
0x180107bae  mov     rcx, r14; struct wil::details::IFailureCallback *
0x180107bb1  call    ?ContinueOnCurrentThread@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x180107bb6  nop
0x180107bb7  test    edi, edi
0x180107bb9  jns     short loc_180107BE6
0x180107bbb  mov     rcx, [rbp+57h+var_C8]
0x180107bbf  test    rcx, rcx
0x180107bc2  jz      short loc_180107BE6
0x180107bc4  call    cs:__imp_SetRestrictedErrorInfo
0x180107bca  mov     rcx, [rbp+5Fh]; this
0x180107bce  test    eax, eax
0x180107bd0  jns     short loc_180107BE6
0x180107bd2  mov     r9d, eax; char *
0x180107bd5  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180107bdc  mov     edx, 4Fh ; 'O'; void *
0x180107be1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180107be6  mov     rcx, [rbp+5Fh]; this
0x180107bea  test    edi, edi
0x180107bec  jns     short loc_180107C03
0x180107bee  mov     r9d, edi; char *
0x180107bf1  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180107bf8  mov     edx, 51h ; 'Q'; void *
0x180107bfd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180107c03  lea     rdx, [rbp+57h+var_80]
0x180107c07  mov     rcx, rbx
0x180107c0a  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x180107c0f  nop
0x180107c10  lea     rcx, [rbp+57h+var_80]; this
0x180107c14  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180107c19  nop
0x180107c1a  lea     rcx, [rbp+57h+var_C8]
0x180107c1e  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x180107c23  nop
0x180107c24  lea     rcx, [rbp+57h+var_C0]
0x180107c28  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x180107c2d  mov     rax, rbx
0x180107c30  add     rsp, 0E8h
0x180107c37  pop     r15
0x180107c39  pop     r14
0x180107c3b  pop     rdi
0x180107c3c  pop     rsi
0x180107c3d  pop     rbx
0x180107c3e  pop     rbp
0x180107c3f  retn
```
