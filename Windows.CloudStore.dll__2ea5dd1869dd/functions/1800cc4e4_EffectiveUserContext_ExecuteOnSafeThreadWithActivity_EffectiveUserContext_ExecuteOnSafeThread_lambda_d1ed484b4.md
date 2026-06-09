# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_d1ed484b472c71ea2a48250876595783_>(_lambda_d1ed484b472c71ea2a48250876595783_ &&)'::`2'::NopActivity const,_lambda_d1ed484b472c71ea2a48250876595783_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_d1ed484b472c71ea2a48250876595783_>(_lambda_d1ed484b472c71ea2a48250876595783_ &&)'::`2'::NopActivity const &,_lambda_d1ed484b472c71ea2a48250876595783_ &)

- ea: `0x1800cc4e4`
- end: `0x1800cc6fb`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_d1ed484b472c71ea2a48250876595783_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_d1ed484b472c71ea2a48250876595783_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_d1ed484b472c71ea2a48250876595783_@@@0@QEBAX$$QEAV_lambda_d1ed484b472c71ea2a48250876595783_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180180318`

## callees

- `0x18000dfe4`
- `0x180010688`
- `0x180016cf4`
- `0x180035b7c`
- `0x180038db8`
- `0x18005dde0`
- `0x180061e60`
- `0x180064888`
- `0x1800cc4e4`
- `0x1800ce314`
- `0x1800e93e0`
- `0x180180e50`
- `0x180182230`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800cc5ab`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800cc5ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cc591`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cc591`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cc51a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cc51a`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cc67f`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cc67f`

## string_xrefs

- `0x1800cc52f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cc5d3`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cc690`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cc6ac`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_d1ed484b472c71ea2a48250876595783_>'::`2'::NopActivity const,AX$$QEAV_lambda_d1ed484b472c71ea2a48250876595783_ const * const>(
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
      _lambda_d1ed484b472c71ea2a48250876595783_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_690a5c814eeeee8f5947d8a3ecedfa38_ &>,_lambda_690a5c814eeeee8f5947d8a3ecedfa38_ &>(
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
0x1800cc4e4  push    rbp
0x1800cc4e6  push    rbx
0x1800cc4e7  push    rsi
0x1800cc4e8  push    rdi
0x1800cc4e9  push    r14
0x1800cc4eb  push    r15
0x1800cc4ed  lea     rbp, [rsp-2Fh]
0x1800cc4f2  sub     rsp, 0E8h
0x1800cc4f9  mov     rdi, r9
0x1800cc4fc  mov     rsi, r8
0x1800cc4ff  mov     rbx, rdx
0x1800cc502  mov     r14, rcx
0x1800cc505  xor     r15d, r15d
0x1800cc508  mov     [rsp+110h+pAptType], r15d
0x1800cc50d  mov     [rbp+57h+pAptQualifier], r15d
0x1800cc511  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800cc515  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800cc51a  call    cs:__imp_CoGetApartmentType
0x1800cc520  mov     rcx, [rbp+5Fh]; this
0x1800cc524  test    eax, eax
0x1800cc526  jns     loc_1800CC5E5
0x1800cc52c  mov     r9d, eax; char *
0x1800cc52f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cc536  lea     edx, [r15+29h]; void *
0x1800cc53a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cc53f  lea     rcx, [rbp+57h+var_C0]
0x1800cc543  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800cc548  nop
0x1800cc549  mov     [rbp+57h+var_C8], r15
0x1800cc54d  mov     [rbp+57h+var_B0], r14
0x1800cc551  mov     [rbp+57h+var_A8], rsi
0x1800cc555  mov     [rbp+57h+var_A0], rdi
0x1800cc559  lea     rax, [rbp+57h+var_C8]
0x1800cc55d  mov     [rbp+57h+var_98], rax
0x1800cc561  lea     rax, [rbp+57h+var_C0]
0x1800cc565  mov     [rbp+57h+var_90], rax
0x1800cc569  lea     rdx, [rbp+57h+var_B0]
0x1800cc56d  lea     rcx, [rsp+110h+var_D8]
0x1800cc572  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_690a5c814eeeee8f5947d8a3ecedfa38_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_690a5c814eeeee8f5947d8a3ecedfa38_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_690a5c814eeeee8f5947d8a3ecedfa38_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_690a5c814eeeee8f5947d8a3ecedfa38_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_690a5c814eeeee8f5947d8a3ecedfa38_ &>,_lambda_690a5c814eeeee8f5947d8a3ecedfa38_ &>(_lambda_690a5c814eeeee8f5947d8a3ecedfa38_ &)
0x1800cc577  mov     rdi, [rax]
0x1800cc57a  mov     [rax], r15
0x1800cc57d  mov     rcx, [rsp+110h+var_D8]
0x1800cc582  test    rcx, rcx
0x1800cc585  jz      short loc_1800CC591
0x1800cc587  mov     [rsp+110h+var_D8], r15
0x1800cc58c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800cc591  call    cs:__imp_GetCurrentThreadId
0x1800cc597  mov     [rsp+110h+var_E8], r15
0x1800cc59c  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800cc5a1  xor     r9d, r9d
0x1800cc5a4  mov     r8d, eax
0x1800cc5a7  xor     edx, edx
0x1800cc5a9  xor     ecx, ecx
0x1800cc5ab  call    cs:__imp_SHTaskPoolQueueTask
0x1800cc5b1  mov     esi, eax
0x1800cc5b3  test    rdi, rdi
0x1800cc5b6  jz      short loc_1800CC5C8
0x1800cc5b8  mov     rdx, [rdi]
0x1800cc5bb  mov     rcx, rdi
0x1800cc5be  mov     rax, [rdx+10h]
0x1800cc5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc5c7  nop
0x1800cc5c8  mov     rcx, [rbp+5Fh]; this
0x1800cc5cc  test    esi, esi
0x1800cc5ce  jns     short loc_1800CC63E
0x1800cc5d0  mov     r9d, esi; char *
0x1800cc5d3  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cc5da  mov     edx, 46h ; 'F'; void *
0x1800cc5df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cc5e5  mov     eax, [rsp+110h+pAptType]
0x1800cc5e9  test    eax, eax
0x1800cc5eb  jz      loc_1800CC53F
0x1800cc5f1  cmp     eax, 3
0x1800cc5f4  jz      loc_1800CC53F
0x1800cc5fa  lea     rcx, [rsp+110h+var_D8]
0x1800cc5ff  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cc604  nop
0x1800cc605  mov     rcx, rdi
0x1800cc608  call    ??R_lambda_d1ed484b472c71ea2a48250876595783_@@QEBA@XZ; _lambda_d1ed484b472c71ea2a48250876595783_::operator()(void)
0x1800cc60d  xorps   xmm0, xmm0
0x1800cc610  movups  xmmword ptr [rbx], xmm0
0x1800cc613  movups  xmmword ptr [rbx+10h], xmm0
0x1800cc617  mov     [rbx+20h], r15
0x1800cc61b  mov     [rbx+28h], r15
0x1800cc61f  mov     [rbx+30h], r15
0x1800cc623  mov     [rbx+38h], r15d
0x1800cc627  mov     [rbx+40h], r15
0x1800cc62b  mov     [rbx+48h], r15b
0x1800cc62f  lea     rcx, [rsp+110h+var_D8]
0x1800cc634  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800cc639  jmp     loc_1800CC6E8
0x1800cc63e  mov     rcx, [rbp+57h+var_C0]
0x1800cc642  mov     rax, [rcx]
0x1800cc645  xor     edx, edx
0x1800cc647  mov     rax, [rax+10h]
0x1800cc64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc650  mov     edi, eax
0x1800cc652  xorps   xmm0, xmm0
0x1800cc655  movups  [rbp+57h+var_80], xmm0
0x1800cc659  movups  [rbp+57h+var_70], xmm0
0x1800cc65d  movdqa  [rbp+57h+var_60], xmm0
0x1800cc662  mov     [rbp+57h+var_50], r15
0x1800cc666  mov     [rbp+57h+var_48], r15d
0x1800cc66a  mov     [rbp+57h+var_40], r15
0x1800cc66e  mov     [rbp+57h+var_38], r15b
0x1800cc672  test    eax, eax
0x1800cc674  jns     short loc_1800CC6A1
0x1800cc676  mov     rcx, [rbp+57h+var_C8]
0x1800cc67a  test    rcx, rcx
0x1800cc67d  jz      short loc_1800CC6A1
0x1800cc67f  call    cs:__imp_SetRestrictedErrorInfo
0x1800cc685  mov     rcx, [rbp+5Fh]; this
0x1800cc689  test    eax, eax
0x1800cc68b  jns     short loc_1800CC6A1
0x1800cc68d  mov     r9d, eax; char *
0x1800cc690  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cc697  mov     edx, 4Fh ; 'O'; void *
0x1800cc69c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cc6a1  mov     rcx, [rbp+5Fh]; this
0x1800cc6a5  test    edi, edi
0x1800cc6a7  jns     short loc_1800CC6BE
0x1800cc6a9  mov     r9d, edi; char *
0x1800cc6ac  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cc6b3  mov     edx, 51h ; 'Q'; void *
0x1800cc6b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cc6be  lea     rdx, [rbp+57h+var_80]
0x1800cc6c2  mov     rcx, rbx
0x1800cc6c5  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800cc6ca  nop
0x1800cc6cb  lea     rcx, [rbp+57h+var_80]; this
0x1800cc6cf  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800cc6d4  nop
0x1800cc6d5  lea     rcx, [rbp+57h+var_C8]
0x1800cc6d9  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800cc6de  nop
0x1800cc6df  lea     rcx, [rbp+57h+var_C0]
0x1800cc6e3  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800cc6e8  mov     rax, rbx
0x1800cc6eb  add     rsp, 0E8h
0x1800cc6f2  pop     r15
0x1800cc6f4  pop     r14
0x1800cc6f6  pop     rdi
0x1800cc6f7  pop     rsi
0x1800cc6f8  pop     rbx
0x1800cc6f9  pop     rbp
0x1800cc6fa  retn
```
