# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity,_lambda_420a4041fff2a18089b4d78ca947a01c_>(Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity &,_lambda_420a4041fff2a18089b4d78ca947a01c_ &&)

- ea: `0x1800cecd4`
- end: `0x1800ceed8`
- name: `??$ExecuteOnSafeThreadWithActivity@VSaveActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@V_lambda_420a4041fff2a18089b4d78ca947a01c_@@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEAVSaveActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$$QEAV_lambda_420a4041fff2a18089b4d78ca947a01c_@@@Z`
- size: `516`
- prototype: `__int64 __fastcall(__int64, __int64, struct wil::details::IFailureCallback *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18016ebd0`

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
- `0x1800cecd4`
- `0x1800d4704`
- `0x1800e93e0`
- `0x180152d64`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800ced9b`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800ced9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ced81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ced81`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ced0a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ced0a`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cee5c`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cee5c`

## string_xrefs

- `0x1800ced1f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cedc3`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cee6d`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cee89`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall EffectiveUserContext::ExecuteOnSafeThreadWithActivity<Windows::Internal::Storage::Cloud::CloudStoreTelemetry::SaveActivity,_lambda_420a4041fff2a18089b4d78ca947a01c_>(
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
      _lambda_420a4041fff2a18089b4d78ca947a01c_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ad1741df12a6df0d9631069da82c42ac_ &>,_lambda_ad1741df12a6df0d9631069da82c42ac_ &>(
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
0x1800cecd4  push    rbp
0x1800cecd6  push    rbx
0x1800cecd7  push    rsi
0x1800cecd8  push    rdi
0x1800cecd9  push    r14
0x1800cecdb  push    r15
0x1800cecdd  lea     rbp, [rsp-2Fh]
0x1800cece2  sub     rsp, 0E8h
0x1800cece9  mov     rdi, r9
0x1800cecec  mov     r14, r8
0x1800cecef  mov     rbx, rdx
0x1800cecf2  mov     rsi, rcx
0x1800cecf5  xor     r15d, r15d
0x1800cecf8  mov     [rsp+110h+pAptType], r15d
0x1800cecfd  mov     [rbp+57h+pAptQualifier], r15d
0x1800ced01  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800ced05  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800ced0a  call    cs:__imp_CoGetApartmentType
0x1800ced10  mov     rcx, [rbp+5Fh]; this
0x1800ced14  test    eax, eax
0x1800ced16  jns     loc_1800CEDD5
0x1800ced1c  mov     r9d, eax; char *
0x1800ced1f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ced26  lea     edx, [r15+29h]; void *
0x1800ced2a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ced2f  lea     rcx, [rbp+57h+var_C0]
0x1800ced33  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800ced38  nop
0x1800ced39  mov     [rbp+57h+var_C8], r15
0x1800ced3d  mov     [rbp+57h+var_B0], rsi
0x1800ced41  mov     [rbp+57h+var_A8], r14
0x1800ced45  mov     [rbp+57h+var_A0], rdi
0x1800ced49  lea     rax, [rbp+57h+var_C8]
0x1800ced4d  mov     [rbp+57h+var_98], rax
0x1800ced51  lea     rax, [rbp+57h+var_C0]
0x1800ced55  mov     [rbp+57h+var_90], rax
0x1800ced59  lea     rdx, [rbp+57h+var_B0]
0x1800ced5d  lea     rcx, [rsp+110h+var_D8]
0x1800ced62  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_ad1741df12a6df0d9631069da82c42ac_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_ad1741df12a6df0d9631069da82c42ac_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_ad1741df12a6df0d9631069da82c42ac_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_ad1741df12a6df0d9631069da82c42ac_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_ad1741df12a6df0d9631069da82c42ac_ &>,_lambda_ad1741df12a6df0d9631069da82c42ac_ &>(_lambda_ad1741df12a6df0d9631069da82c42ac_ &)
0x1800ced67  mov     rdi, [rax]
0x1800ced6a  mov     [rax], r15
0x1800ced6d  mov     rcx, [rsp+110h+var_D8]
0x1800ced72  test    rcx, rcx
0x1800ced75  jz      short loc_1800CED81
0x1800ced77  mov     [rsp+110h+var_D8], r15
0x1800ced7c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800ced81  call    cs:__imp_GetCurrentThreadId
0x1800ced87  mov     [rsp+110h+var_E8], r15
0x1800ced8c  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800ced91  xor     r9d, r9d
0x1800ced94  mov     r8d, eax
0x1800ced97  xor     edx, edx
0x1800ced99  xor     ecx, ecx
0x1800ced9b  call    cs:__imp_SHTaskPoolQueueTask
0x1800ceda1  mov     esi, eax
0x1800ceda3  test    rdi, rdi
0x1800ceda6  jz      short loc_1800CEDB8
0x1800ceda8  mov     rdx, [rdi]
0x1800cedab  mov     rcx, rdi
0x1800cedae  mov     rax, [rdx+10h]
0x1800cedb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cedb7  nop
0x1800cedb8  mov     rcx, [rbp+5Fh]; this
0x1800cedbc  test    esi, esi
0x1800cedbe  jns     short loc_1800CEE2E
0x1800cedc0  mov     r9d, esi; char *
0x1800cedc3  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cedca  mov     edx, 46h ; 'F'; void *
0x1800cedcf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cedd5  mov     eax, [rsp+110h+pAptType]
0x1800cedd9  test    eax, eax
0x1800ceddb  jz      loc_1800CED2F
0x1800cede1  cmp     eax, 3
0x1800cede4  jz      loc_1800CED2F
0x1800cedea  lea     rcx, [rsp+110h+var_D8]
0x1800cedef  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cedf4  nop
0x1800cedf5  mov     rcx, rdi
0x1800cedf8  call    ??R_lambda_420a4041fff2a18089b4d78ca947a01c_@@QEBA@XZ; _lambda_420a4041fff2a18089b4d78ca947a01c_::operator()(void)
0x1800cedfd  xorps   xmm0, xmm0
0x1800cee00  movups  xmmword ptr [rbx], xmm0
0x1800cee03  movups  xmmword ptr [rbx+10h], xmm0
0x1800cee07  mov     [rbx+20h], r15
0x1800cee0b  mov     [rbx+28h], r15
0x1800cee0f  mov     [rbx+30h], r15
0x1800cee13  mov     [rbx+38h], r15d
0x1800cee17  mov     [rbx+40h], r15
0x1800cee1b  mov     [rbx+48h], r15b
0x1800cee1f  lea     rcx, [rsp+110h+var_D8]
0x1800cee24  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800cee29  jmp     loc_1800CEEC5
0x1800cee2e  mov     rcx, [rbp+57h+var_C0]
0x1800cee32  mov     rax, [rcx]
0x1800cee35  xor     edx, edx
0x1800cee37  mov     rax, [rax+10h]
0x1800cee3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cee40  mov     edi, eax
0x1800cee42  lea     rdx, [rbp+57h+var_80]; this
0x1800cee46  mov     rcx, r14; struct wil::details::IFailureCallback *
0x1800cee49  call    ?ContinueOnCurrentThread@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x1800cee4e  nop
0x1800cee4f  test    edi, edi
0x1800cee51  jns     short loc_1800CEE7E
0x1800cee53  mov     rcx, [rbp+57h+var_C8]
0x1800cee57  test    rcx, rcx
0x1800cee5a  jz      short loc_1800CEE7E
0x1800cee5c  call    cs:__imp_SetRestrictedErrorInfo
0x1800cee62  mov     rcx, [rbp+5Fh]; this
0x1800cee66  test    eax, eax
0x1800cee68  jns     short loc_1800CEE7E
0x1800cee6a  mov     r9d, eax; char *
0x1800cee6d  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cee74  mov     edx, 4Fh ; 'O'; void *
0x1800cee79  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cee7e  mov     rcx, [rbp+5Fh]; this
0x1800cee82  test    edi, edi
0x1800cee84  jns     short loc_1800CEE9B
0x1800cee86  mov     r9d, edi; char *
0x1800cee89  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cee90  mov     edx, 51h ; 'Q'; void *
0x1800cee95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cee9b  lea     rdx, [rbp+57h+var_80]
0x1800cee9f  mov     rcx, rbx
0x1800ceea2  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800ceea7  nop
0x1800ceea8  lea     rcx, [rbp+57h+var_80]; this
0x1800ceeac  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800ceeb1  nop
0x1800ceeb2  lea     rcx, [rbp+57h+var_C8]
0x1800ceeb6  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800ceebb  nop
0x1800ceebc  lea     rcx, [rbp+57h+var_C0]
0x1800ceec0  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800ceec5  mov     rax, rbx
0x1800ceec8  add     rsp, 0E8h
0x1800ceecf  pop     r15
0x1800ceed1  pop     r14
0x1800ceed3  pop     rdi
0x1800ceed4  pop     rsi
0x1800ceed5  pop     rbx
0x1800ceed6  pop     rbp
0x1800ceed7  retn
```
