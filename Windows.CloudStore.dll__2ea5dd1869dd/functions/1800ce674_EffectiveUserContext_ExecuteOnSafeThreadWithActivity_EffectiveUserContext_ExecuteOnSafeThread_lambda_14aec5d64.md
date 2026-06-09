# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_14aec5d64767596cc75c7e2fad47a2cf_>(_lambda_14aec5d64767596cc75c7e2fad47a2cf_ &&)'::`2'::NopActivity const,_lambda_14aec5d64767596cc75c7e2fad47a2cf_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_14aec5d64767596cc75c7e2fad47a2cf_>(_lambda_14aec5d64767596cc75c7e2fad47a2cf_ &&)'::`2'::NopActivity const &,_lambda_14aec5d64767596cc75c7e2fad47a2cf_ &)

- ea: `0x1800ce674`
- end: `0x1800ce88b`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_14aec5d64767596cc75c7e2fad47a2cf_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_14aec5d64767596cc75c7e2fad47a2cf_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_14aec5d64767596cc75c7e2fad47a2cf_@@@0@QEBAX$$QEAV_lambda_14aec5d64767596cc75c7e2fad47a2cf_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18016af10`

## callees

- `0x18000dfe4`
- `0x180010688`
- `0x180016cf4`
- `0x180035b7c`
- `0x180038db8`
- `0x18005dde0`
- `0x180061e60`
- `0x180064888`
- `0x1800ce314`
- `0x1800ce674`
- `0x1800d38c8`
- `0x1800e93e0`
- `0x18015298c`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800ce73b`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800ce73b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce721`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce721`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ce6aa`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ce6aa`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800ce80f`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800ce80f`

## string_xrefs

- `0x1800ce6bf`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800ce763`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800ce820`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800ce83c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_14aec5d64767596cc75c7e2fad47a2cf_>'::`2'::NopActivity const,AX$$QEAV_lambda_14aec5d64767596cc75c7e2fad47a2cf_ const * const>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
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
  _OWORD v24[3]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v25; // [rsp+C0h] [rbp+7h]
  int v26; // [rsp+C8h] [rbp+Fh]
  __int64 v27; // [rsp+D0h] [rbp+17h]
  char v28; // [rsp+D8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, &pAptQualifier);
  if ( ApartmentType >= 0 )
  {
    if ( pAptType && pAptType != APTTYPE_MAINSTA )
    {
      wil::run_as_self(&v19);
      _lambda_14aec5d64767596cc75c7e2fad47a2cf_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1a350fd44cd1a84b2af43137f811fc81_ &>,_lambda_1a350fd44cd1a84b2af43137f811fc81_ &>(
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
  memset(v24, 0, sizeof(v24));
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
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
0x1800ce674  push    rbp
0x1800ce676  push    rbx
0x1800ce677  push    rsi
0x1800ce678  push    rdi
0x1800ce679  push    r14
0x1800ce67b  push    r15
0x1800ce67d  lea     rbp, [rsp-2Fh]
0x1800ce682  sub     rsp, 0E8h
0x1800ce689  mov     rdi, r9
0x1800ce68c  mov     rsi, r8
0x1800ce68f  mov     rbx, rdx
0x1800ce692  mov     r14, rcx
0x1800ce695  xor     r15d, r15d
0x1800ce698  mov     [rsp+110h+pAptType], r15d
0x1800ce69d  mov     [rbp+57h+pAptQualifier], r15d
0x1800ce6a1  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800ce6a5  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800ce6aa  call    cs:__imp_CoGetApartmentType
0x1800ce6b0  mov     rcx, [rbp+5Fh]; this
0x1800ce6b4  test    eax, eax
0x1800ce6b6  jns     loc_1800CE775
0x1800ce6bc  mov     r9d, eax; char *
0x1800ce6bf  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ce6c6  lea     edx, [r15+29h]; void *
0x1800ce6ca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ce6cf  lea     rcx, [rbp+57h+var_C0]
0x1800ce6d3  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800ce6d8  nop
0x1800ce6d9  mov     [rbp+57h+var_C8], r15
0x1800ce6dd  mov     [rbp+57h+var_B0], r14
0x1800ce6e1  mov     [rbp+57h+var_A8], rsi
0x1800ce6e5  mov     [rbp+57h+var_A0], rdi
0x1800ce6e9  lea     rax, [rbp+57h+var_C8]
0x1800ce6ed  mov     [rbp+57h+var_98], rax
0x1800ce6f1  lea     rax, [rbp+57h+var_C0]
0x1800ce6f5  mov     [rbp+57h+var_90], rax
0x1800ce6f9  lea     rdx, [rbp+57h+var_B0]
0x1800ce6fd  lea     rcx, [rsp+110h+var_D8]
0x1800ce702  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_1a350fd44cd1a84b2af43137f811fc81_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_1a350fd44cd1a84b2af43137f811fc81_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_1a350fd44cd1a84b2af43137f811fc81_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_1a350fd44cd1a84b2af43137f811fc81_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1a350fd44cd1a84b2af43137f811fc81_ &>,_lambda_1a350fd44cd1a84b2af43137f811fc81_ &>(_lambda_1a350fd44cd1a84b2af43137f811fc81_ &)
0x1800ce707  mov     rdi, [rax]
0x1800ce70a  mov     [rax], r15
0x1800ce70d  mov     rcx, [rsp+110h+var_D8]
0x1800ce712  test    rcx, rcx
0x1800ce715  jz      short loc_1800CE721
0x1800ce717  mov     [rsp+110h+var_D8], r15
0x1800ce71c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800ce721  call    cs:__imp_GetCurrentThreadId
0x1800ce727  mov     [rsp+110h+var_E8], r15
0x1800ce72c  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800ce731  xor     r9d, r9d
0x1800ce734  mov     r8d, eax
0x1800ce737  xor     edx, edx
0x1800ce739  xor     ecx, ecx
0x1800ce73b  call    cs:__imp_SHTaskPoolQueueTask
0x1800ce741  mov     esi, eax
0x1800ce743  test    rdi, rdi
0x1800ce746  jz      short loc_1800CE758
0x1800ce748  mov     rdx, [rdi]
0x1800ce74b  mov     rcx, rdi
0x1800ce74e  mov     rax, [rdx+10h]
0x1800ce752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce757  nop
0x1800ce758  mov     rcx, [rbp+5Fh]; this
0x1800ce75c  test    esi, esi
0x1800ce75e  jns     short loc_1800CE7CE
0x1800ce760  mov     r9d, esi; char *
0x1800ce763  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ce76a  mov     edx, 46h ; 'F'; void *
0x1800ce76f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ce775  mov     eax, [rsp+110h+pAptType]
0x1800ce779  test    eax, eax
0x1800ce77b  jz      loc_1800CE6CF
0x1800ce781  cmp     eax, 3
0x1800ce784  jz      loc_1800CE6CF
0x1800ce78a  lea     rcx, [rsp+110h+var_D8]
0x1800ce78f  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800ce794  nop
0x1800ce795  mov     rcx, rdi
0x1800ce798  call    ??R_lambda_14aec5d64767596cc75c7e2fad47a2cf_@@QEBA@XZ; _lambda_14aec5d64767596cc75c7e2fad47a2cf_::operator()(void)
0x1800ce79d  xorps   xmm0, xmm0
0x1800ce7a0  movups  xmmword ptr [rbx], xmm0
0x1800ce7a3  movups  xmmword ptr [rbx+10h], xmm0
0x1800ce7a7  mov     [rbx+20h], r15
0x1800ce7ab  mov     [rbx+28h], r15
0x1800ce7af  mov     [rbx+30h], r15
0x1800ce7b3  mov     [rbx+38h], r15d
0x1800ce7b7  mov     [rbx+40h], r15
0x1800ce7bb  mov     [rbx+48h], r15b
0x1800ce7bf  lea     rcx, [rsp+110h+var_D8]
0x1800ce7c4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800ce7c9  jmp     loc_1800CE878
0x1800ce7ce  mov     rcx, [rbp+57h+var_C0]
0x1800ce7d2  mov     rax, [rcx]
0x1800ce7d5  xor     edx, edx
0x1800ce7d7  mov     rax, [rax+10h]
0x1800ce7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce7e0  mov     edi, eax
0x1800ce7e2  xorps   xmm0, xmm0
0x1800ce7e5  movups  [rbp+57h+var_80], xmm0
0x1800ce7e9  movups  [rbp+57h+var_70], xmm0
0x1800ce7ed  movdqa  [rbp+57h+var_60], xmm0
0x1800ce7f2  mov     [rbp+57h+var_50], r15
0x1800ce7f6  mov     [rbp+57h+var_48], r15d
0x1800ce7fa  mov     [rbp+57h+var_40], r15
0x1800ce7fe  mov     [rbp+57h+var_38], r15b
0x1800ce802  test    eax, eax
0x1800ce804  jns     short loc_1800CE831
0x1800ce806  mov     rcx, [rbp+57h+var_C8]
0x1800ce80a  test    rcx, rcx
0x1800ce80d  jz      short loc_1800CE831
0x1800ce80f  call    cs:__imp_SetRestrictedErrorInfo
0x1800ce815  mov     rcx, [rbp+5Fh]; this
0x1800ce819  test    eax, eax
0x1800ce81b  jns     short loc_1800CE831
0x1800ce81d  mov     r9d, eax; char *
0x1800ce820  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ce827  mov     edx, 4Fh ; 'O'; void *
0x1800ce82c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ce831  mov     rcx, [rbp+5Fh]; this
0x1800ce835  test    edi, edi
0x1800ce837  jns     short loc_1800CE84E
0x1800ce839  mov     r9d, edi; char *
0x1800ce83c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ce843  mov     edx, 51h ; 'Q'; void *
0x1800ce848  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ce84e  lea     rdx, [rbp+57h+var_80]
0x1800ce852  mov     rcx, rbx
0x1800ce855  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800ce85a  nop
0x1800ce85b  lea     rcx, [rbp+57h+var_80]; this
0x1800ce85f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800ce864  nop
0x1800ce865  lea     rcx, [rbp+57h+var_C8]
0x1800ce869  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800ce86e  nop
0x1800ce86f  lea     rcx, [rbp+57h+var_C0]
0x1800ce873  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800ce878  mov     rax, rbx
0x1800ce87b  add     rsp, 0E8h
0x1800ce882  pop     r15
0x1800ce884  pop     r14
0x1800ce886  pop     rdi
0x1800ce887  pop     rsi
0x1800ce888  pop     rbx
0x1800ce889  pop     rbp
0x1800ce88a  retn
```
