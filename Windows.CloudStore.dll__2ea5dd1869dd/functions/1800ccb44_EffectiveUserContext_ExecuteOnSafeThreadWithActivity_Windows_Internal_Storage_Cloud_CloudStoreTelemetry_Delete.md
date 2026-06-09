# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity,_lambda_4c24b8666f3feb888d8af78d8489e62e_>(Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity &,_lambda_4c24b8666f3feb888d8af78d8489e62e_ &&)

- ea: `0x1800ccb44`
- end: `0x1800ccd48`
- name: `??$ExecuteOnSafeThreadWithActivity@VDeleteActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@V_lambda_4c24b8666f3feb888d8af78d8489e62e_@@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEAVDeleteActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$$QEAV_lambda_4c24b8666f3feb888d8af78d8489e62e_@@@Z`
- size: `516`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180114670`

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
- `0x1800ccb44`
- `0x1800ce314`
- `0x1800e93e0`
- `0x180152f50`
- `0x1801655d0`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800ccc0b`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800ccc0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ccbf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ccbf1`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ccb7a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ccb7a`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800ccccc`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800ccccc`

## string_xrefs

- `0x1800ccb8f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800ccc33`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cccdd`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cccf9`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall EffectiveUserContext::ExecuteOnSafeThreadWithActivity<Windows::Internal::Storage::Cloud::CloudStoreTelemetry::DeleteActivity,_lambda_4c24b8666f3feb888d8af78d8489e62e_>(
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
      _lambda_4c24b8666f3feb888d8af78d8489e62e_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_f6dca36db9572341e2d5de0b42fefe18_ &>,_lambda_f6dca36db9572341e2d5de0b42fefe18_ &>(
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
0x1800ccb44  push    rbp
0x1800ccb46  push    rbx
0x1800ccb47  push    rsi
0x1800ccb48  push    rdi
0x1800ccb49  push    r14
0x1800ccb4b  push    r15
0x1800ccb4d  lea     rbp, [rsp-2Fh]
0x1800ccb52  sub     rsp, 0E8h
0x1800ccb59  mov     rdi, r9
0x1800ccb5c  mov     r14, r8
0x1800ccb5f  mov     rbx, rdx
0x1800ccb62  mov     rsi, rcx
0x1800ccb65  xor     r15d, r15d
0x1800ccb68  mov     [rsp+110h+pAptType], r15d
0x1800ccb6d  mov     [rbp+57h+pAptQualifier], r15d
0x1800ccb71  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800ccb75  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800ccb7a  call    cs:__imp_CoGetApartmentType
0x1800ccb80  mov     rcx, [rbp+5Fh]; this
0x1800ccb84  test    eax, eax
0x1800ccb86  jns     loc_1800CCC45
0x1800ccb8c  mov     r9d, eax; char *
0x1800ccb8f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ccb96  lea     edx, [r15+29h]; void *
0x1800ccb9a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ccb9f  lea     rcx, [rbp+57h+var_C0]
0x1800ccba3  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800ccba8  nop
0x1800ccba9  mov     [rbp+57h+var_C8], r15
0x1800ccbad  mov     [rbp+57h+var_B0], rsi
0x1800ccbb1  mov     [rbp+57h+var_A8], r14
0x1800ccbb5  mov     [rbp+57h+var_A0], rdi
0x1800ccbb9  lea     rax, [rbp+57h+var_C8]
0x1800ccbbd  mov     [rbp+57h+var_98], rax
0x1800ccbc1  lea     rax, [rbp+57h+var_C0]
0x1800ccbc5  mov     [rbp+57h+var_90], rax
0x1800ccbc9  lea     rdx, [rbp+57h+var_B0]
0x1800ccbcd  lea     rcx, [rsp+110h+var_D8]
0x1800ccbd2  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_f6dca36db9572341e2d5de0b42fefe18_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_f6dca36db9572341e2d5de0b42fefe18_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_f6dca36db9572341e2d5de0b42fefe18_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_f6dca36db9572341e2d5de0b42fefe18_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_f6dca36db9572341e2d5de0b42fefe18_ &>,_lambda_f6dca36db9572341e2d5de0b42fefe18_ &>(_lambda_f6dca36db9572341e2d5de0b42fefe18_ &)
0x1800ccbd7  mov     rdi, [rax]
0x1800ccbda  mov     [rax], r15
0x1800ccbdd  mov     rcx, [rsp+110h+var_D8]
0x1800ccbe2  test    rcx, rcx
0x1800ccbe5  jz      short loc_1800CCBF1
0x1800ccbe7  mov     [rsp+110h+var_D8], r15
0x1800ccbec  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800ccbf1  call    cs:__imp_GetCurrentThreadId
0x1800ccbf7  mov     [rsp+110h+var_E8], r15
0x1800ccbfc  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800ccc01  xor     r9d, r9d
0x1800ccc04  mov     r8d, eax
0x1800ccc07  xor     edx, edx
0x1800ccc09  xor     ecx, ecx
0x1800ccc0b  call    cs:__imp_SHTaskPoolQueueTask
0x1800ccc11  mov     esi, eax
0x1800ccc13  test    rdi, rdi
0x1800ccc16  jz      short loc_1800CCC28
0x1800ccc18  mov     rdx, [rdi]
0x1800ccc1b  mov     rcx, rdi
0x1800ccc1e  mov     rax, [rdx+10h]
0x1800ccc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccc27  nop
0x1800ccc28  mov     rcx, [rbp+5Fh]; this
0x1800ccc2c  test    esi, esi
0x1800ccc2e  jns     short loc_1800CCC9E
0x1800ccc30  mov     r9d, esi; char *
0x1800ccc33  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ccc3a  mov     edx, 46h ; 'F'; void *
0x1800ccc3f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ccc45  mov     eax, [rsp+110h+pAptType]
0x1800ccc49  test    eax, eax
0x1800ccc4b  jz      loc_1800CCB9F
0x1800ccc51  cmp     eax, 3
0x1800ccc54  jz      loc_1800CCB9F
0x1800ccc5a  lea     rcx, [rsp+110h+var_D8]
0x1800ccc5f  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800ccc64  nop
0x1800ccc65  mov     rcx, rdi
0x1800ccc68  call    ??R_lambda_4c24b8666f3feb888d8af78d8489e62e_@@QEBA@XZ; _lambda_4c24b8666f3feb888d8af78d8489e62e_::operator()(void)
0x1800ccc6d  xorps   xmm0, xmm0
0x1800ccc70  movups  xmmword ptr [rbx], xmm0
0x1800ccc73  movups  xmmword ptr [rbx+10h], xmm0
0x1800ccc77  mov     [rbx+20h], r15
0x1800ccc7b  mov     [rbx+28h], r15
0x1800ccc7f  mov     [rbx+30h], r15
0x1800ccc83  mov     [rbx+38h], r15d
0x1800ccc87  mov     [rbx+40h], r15
0x1800ccc8b  mov     [rbx+48h], r15b
0x1800ccc8f  lea     rcx, [rsp+110h+var_D8]
0x1800ccc94  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800ccc99  jmp     loc_1800CCD35
0x1800ccc9e  mov     rcx, [rbp+57h+var_C0]
0x1800ccca2  mov     rax, [rcx]
0x1800ccca5  xor     edx, edx
0x1800ccca7  mov     rax, [rax+10h]
0x1800cccab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cccb0  mov     edi, eax
0x1800cccb2  lea     rdx, [rbp+57h+var_80]; this
0x1800cccb6  mov     rcx, r14; struct wil::details::IFailureCallback *
0x1800cccb9  call    ?ContinueOnCurrentThread@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x1800cccbe  nop
0x1800cccbf  test    edi, edi
0x1800cccc1  jns     short loc_1800CCCEE
0x1800cccc3  mov     rcx, [rbp+57h+var_C8]
0x1800cccc7  test    rcx, rcx
0x1800cccca  jz      short loc_1800CCCEE
0x1800ccccc  call    cs:__imp_SetRestrictedErrorInfo
0x1800cccd2  mov     rcx, [rbp+5Fh]; this
0x1800cccd6  test    eax, eax
0x1800cccd8  jns     short loc_1800CCCEE
0x1800cccda  mov     r9d, eax; char *
0x1800cccdd  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ccce4  mov     edx, 4Fh ; 'O'; void *
0x1800ccce9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cccee  mov     rcx, [rbp+5Fh]; this
0x1800cccf2  test    edi, edi
0x1800cccf4  jns     short loc_1800CCD0B
0x1800cccf6  mov     r9d, edi; char *
0x1800cccf9  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ccd00  mov     edx, 51h ; 'Q'; void *
0x1800ccd05  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ccd0b  lea     rdx, [rbp+57h+var_80]
0x1800ccd0f  mov     rcx, rbx
0x1800ccd12  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800ccd17  nop
0x1800ccd18  lea     rcx, [rbp+57h+var_80]; this
0x1800ccd1c  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800ccd21  nop
0x1800ccd22  lea     rcx, [rbp+57h+var_C8]
0x1800ccd26  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800ccd2b  nop
0x1800ccd2c  lea     rcx, [rbp+57h+var_C0]
0x1800ccd30  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800ccd35  mov     rax, rbx
0x1800ccd38  add     rsp, 0E8h
0x1800ccd3f  pop     r15
0x1800ccd41  pop     r14
0x1800ccd43  pop     rdi
0x1800ccd44  pop     rsi
0x1800ccd45  pop     rbx
0x1800ccd46  pop     rbp
0x1800ccd47  retn
```
