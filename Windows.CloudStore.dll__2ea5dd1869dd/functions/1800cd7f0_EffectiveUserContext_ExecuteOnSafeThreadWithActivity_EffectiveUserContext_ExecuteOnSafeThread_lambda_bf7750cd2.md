# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_bf7750cd22eb885a435476ce25fdc8bb_>(_lambda_bf7750cd22eb885a435476ce25fdc8bb_ &&)'::`2'::NopActivity const,_lambda_bf7750cd22eb885a435476ce25fdc8bb_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_bf7750cd22eb885a435476ce25fdc8bb_>(_lambda_bf7750cd22eb885a435476ce25fdc8bb_ &&)'::`2'::NopActivity const &,_lambda_bf7750cd22eb885a435476ce25fdc8bb_ &)

- ea: `0x1800cd7f0`
- end: `0x1800cda07`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_bf7750cd22eb885a435476ce25fdc8bb_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_bf7750cd22eb885a435476ce25fdc8bb_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_bf7750cd22eb885a435476ce25fdc8bb_@@@0@QEBAX$$QEAV_lambda_bf7750cd22eb885a435476ce25fdc8bb_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180180284`

## callees

- `0x18000dfe4`
- `0x180010688`
- `0x180016cf4`
- `0x180035b7c`
- `0x180038db8`
- `0x18005dde0`
- `0x180061e60`
- `0x180064888`
- `0x1800cd7f0`
- `0x1800ce314`
- `0x1800e93e0`
- `0x1801805fc`
- `0x180182014`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800cd8b7`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800cd8b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd89d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd89d`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cd826`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cd826`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cd98b`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cd98b`

## string_xrefs

- `0x1800cd83b`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cd8df`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cd99c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cd9b8`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_bf7750cd22eb885a435476ce25fdc8bb_>'::`2'::NopActivity const,AX$$QEAV_lambda_bf7750cd22eb885a435476ce25fdc8bb_ const * const>(
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
      _lambda_bf7750cd22eb885a435476ce25fdc8bb_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_0a8f1cff0d25de1f587f5b3709055dc3_ &>,_lambda_0a8f1cff0d25de1f587f5b3709055dc3_ &>(
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
0x1800cd7f0  push    rbp
0x1800cd7f2  push    rbx
0x1800cd7f3  push    rsi
0x1800cd7f4  push    rdi
0x1800cd7f5  push    r14
0x1800cd7f7  push    r15
0x1800cd7f9  lea     rbp, [rsp-2Fh]
0x1800cd7fe  sub     rsp, 0E8h
0x1800cd805  mov     rdi, r9
0x1800cd808  mov     rsi, r8
0x1800cd80b  mov     rbx, rdx
0x1800cd80e  mov     r14, rcx
0x1800cd811  xor     r15d, r15d
0x1800cd814  mov     [rsp+110h+pAptType], r15d
0x1800cd819  mov     [rbp+57h+pAptQualifier], r15d
0x1800cd81d  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800cd821  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800cd826  call    cs:__imp_CoGetApartmentType
0x1800cd82c  mov     rcx, [rbp+5Fh]; this
0x1800cd830  test    eax, eax
0x1800cd832  jns     loc_1800CD8F1
0x1800cd838  mov     r9d, eax; char *
0x1800cd83b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd842  lea     edx, [r15+29h]; void *
0x1800cd846  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cd84b  lea     rcx, [rbp+57h+var_C0]
0x1800cd84f  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800cd854  nop
0x1800cd855  mov     [rbp+57h+var_C8], r15
0x1800cd859  mov     [rbp+57h+var_B0], r14
0x1800cd85d  mov     [rbp+57h+var_A8], rsi
0x1800cd861  mov     [rbp+57h+var_A0], rdi
0x1800cd865  lea     rax, [rbp+57h+var_C8]
0x1800cd869  mov     [rbp+57h+var_98], rax
0x1800cd86d  lea     rax, [rbp+57h+var_C0]
0x1800cd871  mov     [rbp+57h+var_90], rax
0x1800cd875  lea     rdx, [rbp+57h+var_B0]
0x1800cd879  lea     rcx, [rsp+110h+var_D8]
0x1800cd87e  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_0a8f1cff0d25de1f587f5b3709055dc3_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_0a8f1cff0d25de1f587f5b3709055dc3_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_0a8f1cff0d25de1f587f5b3709055dc3_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_0a8f1cff0d25de1f587f5b3709055dc3_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_0a8f1cff0d25de1f587f5b3709055dc3_ &>,_lambda_0a8f1cff0d25de1f587f5b3709055dc3_ &>(_lambda_0a8f1cff0d25de1f587f5b3709055dc3_ &)
0x1800cd883  mov     rdi, [rax]
0x1800cd886  mov     [rax], r15
0x1800cd889  mov     rcx, [rsp+110h+var_D8]
0x1800cd88e  test    rcx, rcx
0x1800cd891  jz      short loc_1800CD89D
0x1800cd893  mov     [rsp+110h+var_D8], r15
0x1800cd898  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800cd89d  call    cs:__imp_GetCurrentThreadId
0x1800cd8a3  mov     [rsp+110h+var_E8], r15
0x1800cd8a8  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800cd8ad  xor     r9d, r9d
0x1800cd8b0  mov     r8d, eax
0x1800cd8b3  xor     edx, edx
0x1800cd8b5  xor     ecx, ecx
0x1800cd8b7  call    cs:__imp_SHTaskPoolQueueTask
0x1800cd8bd  mov     esi, eax
0x1800cd8bf  test    rdi, rdi
0x1800cd8c2  jz      short loc_1800CD8D4
0x1800cd8c4  mov     rdx, [rdi]
0x1800cd8c7  mov     rcx, rdi
0x1800cd8ca  mov     rax, [rdx+10h]
0x1800cd8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd8d3  nop
0x1800cd8d4  mov     rcx, [rbp+5Fh]; this
0x1800cd8d8  test    esi, esi
0x1800cd8da  jns     short loc_1800CD94A
0x1800cd8dc  mov     r9d, esi; char *
0x1800cd8df  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd8e6  mov     edx, 46h ; 'F'; void *
0x1800cd8eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cd8f1  mov     eax, [rsp+110h+pAptType]
0x1800cd8f5  test    eax, eax
0x1800cd8f7  jz      loc_1800CD84B
0x1800cd8fd  cmp     eax, 3
0x1800cd900  jz      loc_1800CD84B
0x1800cd906  lea     rcx, [rsp+110h+var_D8]
0x1800cd90b  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cd910  nop
0x1800cd911  mov     rcx, rdi
0x1800cd914  call    ??R_lambda_bf7750cd22eb885a435476ce25fdc8bb_@@QEBA@XZ; _lambda_bf7750cd22eb885a435476ce25fdc8bb_::operator()(void)
0x1800cd919  xorps   xmm0, xmm0
0x1800cd91c  movups  xmmword ptr [rbx], xmm0
0x1800cd91f  movups  xmmword ptr [rbx+10h], xmm0
0x1800cd923  mov     [rbx+20h], r15
0x1800cd927  mov     [rbx+28h], r15
0x1800cd92b  mov     [rbx+30h], r15
0x1800cd92f  mov     [rbx+38h], r15d
0x1800cd933  mov     [rbx+40h], r15
0x1800cd937  mov     [rbx+48h], r15b
0x1800cd93b  lea     rcx, [rsp+110h+var_D8]
0x1800cd940  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800cd945  jmp     loc_1800CD9F4
0x1800cd94a  mov     rcx, [rbp+57h+var_C0]
0x1800cd94e  mov     rax, [rcx]
0x1800cd951  xor     edx, edx
0x1800cd953  mov     rax, [rax+10h]
0x1800cd957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd95c  mov     edi, eax
0x1800cd95e  xorps   xmm0, xmm0
0x1800cd961  movups  [rbp+57h+var_80], xmm0
0x1800cd965  movups  [rbp+57h+var_70], xmm0
0x1800cd969  movdqa  [rbp+57h+var_60], xmm0
0x1800cd96e  mov     [rbp+57h+var_50], r15
0x1800cd972  mov     [rbp+57h+var_48], r15d
0x1800cd976  mov     [rbp+57h+var_40], r15
0x1800cd97a  mov     [rbp+57h+var_38], r15b
0x1800cd97e  test    eax, eax
0x1800cd980  jns     short loc_1800CD9AD
0x1800cd982  mov     rcx, [rbp+57h+var_C8]
0x1800cd986  test    rcx, rcx
0x1800cd989  jz      short loc_1800CD9AD
0x1800cd98b  call    cs:__imp_SetRestrictedErrorInfo
0x1800cd991  mov     rcx, [rbp+5Fh]; this
0x1800cd995  test    eax, eax
0x1800cd997  jns     short loc_1800CD9AD
0x1800cd999  mov     r9d, eax; char *
0x1800cd99c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd9a3  mov     edx, 4Fh ; 'O'; void *
0x1800cd9a8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cd9ad  mov     rcx, [rbp+5Fh]; this
0x1800cd9b1  test    edi, edi
0x1800cd9b3  jns     short loc_1800CD9CA
0x1800cd9b5  mov     r9d, edi; char *
0x1800cd9b8  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd9bf  mov     edx, 51h ; 'Q'; void *
0x1800cd9c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cd9ca  lea     rdx, [rbp+57h+var_80]
0x1800cd9ce  mov     rcx, rbx
0x1800cd9d1  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800cd9d6  nop
0x1800cd9d7  lea     rcx, [rbp+57h+var_80]; this
0x1800cd9db  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800cd9e0  nop
0x1800cd9e1  lea     rcx, [rbp+57h+var_C8]
0x1800cd9e5  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800cd9ea  nop
0x1800cd9eb  lea     rcx, [rbp+57h+var_C0]
0x1800cd9ef  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800cd9f4  mov     rax, rbx
0x1800cd9f7  add     rsp, 0E8h
0x1800cd9fe  pop     r15
0x1800cda00  pop     r14
0x1800cda02  pop     rdi
0x1800cda03  pop     rsi
0x1800cda04  pop     rbx
0x1800cda05  pop     rbp
0x1800cda06  retn
```
