# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_51e61674b39b3e6cf28446a5ad5c761f_>(_lambda_51e61674b39b3e6cf28446a5ad5c761f_ &&)'::`2'::NopActivity const,_lambda_51e61674b39b3e6cf28446a5ad5c761f_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_51e61674b39b3e6cf28446a5ad5c761f_>(_lambda_51e61674b39b3e6cf28446a5ad5c761f_ &&)'::`2'::NopActivity const &,_lambda_51e61674b39b3e6cf28446a5ad5c761f_ &)

- ea: `0x1800ce894`
- end: `0x1800ceaab`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_51e61674b39b3e6cf28446a5ad5c761f_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_51e61674b39b3e6cf28446a5ad5c761f_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_51e61674b39b3e6cf28446a5ad5c761f_@@@0@QEBAX$$QEAV_lambda_51e61674b39b3e6cf28446a5ad5c761f_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18018015c`

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
- `0x1800ce894`
- `0x1800e93e0`
- `0x180181184`
- `0x180181c08`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800ce95b`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800ce95b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce941`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ce941`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ce8ca`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ce8ca`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cea2f`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cea2f`

## string_xrefs

- `0x1800ce8df`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800ce983`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cea40`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cea5c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_51e61674b39b3e6cf28446a5ad5c761f_>'::`2'::NopActivity const,AX$$QEAV_lambda_51e61674b39b3e6cf28446a5ad5c761f_ const * const>(
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
      _lambda_51e61674b39b3e6cf28446a5ad5c761f_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_bbb91582f8bbe97f3de3000215336942_ &>,_lambda_bbb91582f8bbe97f3de3000215336942_ &>(
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
0x1800ce894  push    rbp
0x1800ce896  push    rbx
0x1800ce897  push    rsi
0x1800ce898  push    rdi
0x1800ce899  push    r14
0x1800ce89b  push    r15
0x1800ce89d  lea     rbp, [rsp-2Fh]
0x1800ce8a2  sub     rsp, 0E8h
0x1800ce8a9  mov     rdi, r9
0x1800ce8ac  mov     rsi, r8
0x1800ce8af  mov     rbx, rdx
0x1800ce8b2  mov     r14, rcx
0x1800ce8b5  xor     r15d, r15d
0x1800ce8b8  mov     [rsp+110h+pAptType], r15d
0x1800ce8bd  mov     [rbp+57h+pAptQualifier], r15d
0x1800ce8c1  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800ce8c5  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800ce8ca  call    cs:__imp_CoGetApartmentType
0x1800ce8d0  mov     rcx, [rbp+5Fh]; this
0x1800ce8d4  test    eax, eax
0x1800ce8d6  jns     loc_1800CE995
0x1800ce8dc  mov     r9d, eax; char *
0x1800ce8df  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ce8e6  lea     edx, [r15+29h]; void *
0x1800ce8ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ce8ef  lea     rcx, [rbp+57h+var_C0]
0x1800ce8f3  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800ce8f8  nop
0x1800ce8f9  mov     [rbp+57h+var_C8], r15
0x1800ce8fd  mov     [rbp+57h+var_B0], r14
0x1800ce901  mov     [rbp+57h+var_A8], rsi
0x1800ce905  mov     [rbp+57h+var_A0], rdi
0x1800ce909  lea     rax, [rbp+57h+var_C8]
0x1800ce90d  mov     [rbp+57h+var_98], rax
0x1800ce911  lea     rax, [rbp+57h+var_C0]
0x1800ce915  mov     [rbp+57h+var_90], rax
0x1800ce919  lea     rdx, [rbp+57h+var_B0]
0x1800ce91d  lea     rcx, [rsp+110h+var_D8]
0x1800ce922  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_bbb91582f8bbe97f3de3000215336942_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_bbb91582f8bbe97f3de3000215336942_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_bbb91582f8bbe97f3de3000215336942_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_bbb91582f8bbe97f3de3000215336942_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_bbb91582f8bbe97f3de3000215336942_ &>,_lambda_bbb91582f8bbe97f3de3000215336942_ &>(_lambda_bbb91582f8bbe97f3de3000215336942_ &)
0x1800ce927  mov     rdi, [rax]
0x1800ce92a  mov     [rax], r15
0x1800ce92d  mov     rcx, [rsp+110h+var_D8]
0x1800ce932  test    rcx, rcx
0x1800ce935  jz      short loc_1800CE941
0x1800ce937  mov     [rsp+110h+var_D8], r15
0x1800ce93c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800ce941  call    cs:__imp_GetCurrentThreadId
0x1800ce947  mov     [rsp+110h+var_E8], r15
0x1800ce94c  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800ce951  xor     r9d, r9d
0x1800ce954  mov     r8d, eax
0x1800ce957  xor     edx, edx
0x1800ce959  xor     ecx, ecx
0x1800ce95b  call    cs:__imp_SHTaskPoolQueueTask
0x1800ce961  mov     esi, eax
0x1800ce963  test    rdi, rdi
0x1800ce966  jz      short loc_1800CE978
0x1800ce968  mov     rdx, [rdi]
0x1800ce96b  mov     rcx, rdi
0x1800ce96e  mov     rax, [rdx+10h]
0x1800ce972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce977  nop
0x1800ce978  mov     rcx, [rbp+5Fh]; this
0x1800ce97c  test    esi, esi
0x1800ce97e  jns     short loc_1800CE9EE
0x1800ce980  mov     r9d, esi; char *
0x1800ce983  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ce98a  mov     edx, 46h ; 'F'; void *
0x1800ce98f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ce995  mov     eax, [rsp+110h+pAptType]
0x1800ce999  test    eax, eax
0x1800ce99b  jz      loc_1800CE8EF
0x1800ce9a1  cmp     eax, 3
0x1800ce9a4  jz      loc_1800CE8EF
0x1800ce9aa  lea     rcx, [rsp+110h+var_D8]
0x1800ce9af  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800ce9b4  nop
0x1800ce9b5  mov     rcx, rdi
0x1800ce9b8  call    ??R_lambda_51e61674b39b3e6cf28446a5ad5c761f_@@QEBA@XZ; _lambda_51e61674b39b3e6cf28446a5ad5c761f_::operator()(void)
0x1800ce9bd  xorps   xmm0, xmm0
0x1800ce9c0  movups  xmmword ptr [rbx], xmm0
0x1800ce9c3  movups  xmmword ptr [rbx+10h], xmm0
0x1800ce9c7  mov     [rbx+20h], r15
0x1800ce9cb  mov     [rbx+28h], r15
0x1800ce9cf  mov     [rbx+30h], r15
0x1800ce9d3  mov     [rbx+38h], r15d
0x1800ce9d7  mov     [rbx+40h], r15
0x1800ce9db  mov     [rbx+48h], r15b
0x1800ce9df  lea     rcx, [rsp+110h+var_D8]
0x1800ce9e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800ce9e9  jmp     loc_1800CEA98
0x1800ce9ee  mov     rcx, [rbp+57h+var_C0]
0x1800ce9f2  mov     rax, [rcx]
0x1800ce9f5  xor     edx, edx
0x1800ce9f7  mov     rax, [rax+10h]
0x1800ce9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cea00  mov     edi, eax
0x1800cea02  xorps   xmm0, xmm0
0x1800cea05  movups  [rbp+57h+var_80], xmm0
0x1800cea09  movups  [rbp+57h+var_70], xmm0
0x1800cea0d  movdqa  [rbp+57h+var_60], xmm0
0x1800cea12  mov     [rbp+57h+var_50], r15
0x1800cea16  mov     [rbp+57h+var_48], r15d
0x1800cea1a  mov     [rbp+57h+var_40], r15
0x1800cea1e  mov     [rbp+57h+var_38], r15b
0x1800cea22  test    eax, eax
0x1800cea24  jns     short loc_1800CEA51
0x1800cea26  mov     rcx, [rbp+57h+var_C8]
0x1800cea2a  test    rcx, rcx
0x1800cea2d  jz      short loc_1800CEA51
0x1800cea2f  call    cs:__imp_SetRestrictedErrorInfo
0x1800cea35  mov     rcx, [rbp+5Fh]; this
0x1800cea39  test    eax, eax
0x1800cea3b  jns     short loc_1800CEA51
0x1800cea3d  mov     r9d, eax; char *
0x1800cea40  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cea47  mov     edx, 4Fh ; 'O'; void *
0x1800cea4c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cea51  mov     rcx, [rbp+5Fh]; this
0x1800cea55  test    edi, edi
0x1800cea57  jns     short loc_1800CEA6E
0x1800cea59  mov     r9d, edi; char *
0x1800cea5c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cea63  mov     edx, 51h ; 'Q'; void *
0x1800cea68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cea6e  lea     rdx, [rbp+57h+var_80]
0x1800cea72  mov     rcx, rbx
0x1800cea75  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800cea7a  nop
0x1800cea7b  lea     rcx, [rbp+57h+var_80]; this
0x1800cea7f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800cea84  nop
0x1800cea85  lea     rcx, [rbp+57h+var_C8]
0x1800cea89  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800cea8e  nop
0x1800cea8f  lea     rcx, [rbp+57h+var_C0]
0x1800cea93  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800cea98  mov     rax, rbx
0x1800cea9b  add     rsp, 0E8h
0x1800ceaa2  pop     r15
0x1800ceaa4  pop     r14
0x1800ceaa6  pop     rdi
0x1800ceaa7  pop     rsi
0x1800ceaa8  pop     rbx
0x1800ceaa9  pop     rbp
0x1800ceaaa  retn
```
