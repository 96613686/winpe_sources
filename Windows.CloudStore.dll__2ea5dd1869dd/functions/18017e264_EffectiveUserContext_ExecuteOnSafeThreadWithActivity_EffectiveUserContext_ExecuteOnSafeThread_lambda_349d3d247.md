# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_349d3d247dd79cd0d5443630e41fb716_>(_lambda_349d3d247dd79cd0d5443630e41fb716_ &&)'::`2'::NopActivity const,_lambda_349d3d247dd79cd0d5443630e41fb716_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_349d3d247dd79cd0d5443630e41fb716_>(_lambda_349d3d247dd79cd0d5443630e41fb716_ &&)'::`2'::NopActivity const &,_lambda_349d3d247dd79cd0d5443630e41fb716_ &)

- ea: `0x18017e264`
- end: `0x18017e47b`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_349d3d247dd79cd0d5443630e41fb716_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_349d3d247dd79cd0d5443630e41fb716_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_349d3d247dd79cd0d5443630e41fb716_@@@0@QEBAX$$QEAV_lambda_349d3d247dd79cd0d5443630e41fb716_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18017fde4`

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
- `0x1800e93e0`
- `0x18017e264`
- `0x180180b1c`
- `0x18018199c`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18017e32b`
- `SHCORE!SHTaskPoolQueueTask` at `0x18017e32b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017e311`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017e311`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017e29a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017e29a`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017e3ff`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017e3ff`

## string_xrefs

- `0x18017e2af`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017e353`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017e410`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017e42c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_349d3d247dd79cd0d5443630e41fb716_>'::`2'::NopActivity const,AX$$QEAV_lambda_349d3d247dd79cd0d5443630e41fb716_ const * const>(
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
      _lambda_349d3d247dd79cd0d5443630e41fb716_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_4d2353c299f4b0535b54e9793e2a183c_ &>,_lambda_4d2353c299f4b0535b54e9793e2a183c_ &>(
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
0x18017e264  push    rbp
0x18017e266  push    rbx
0x18017e267  push    rsi
0x18017e268  push    rdi
0x18017e269  push    r14
0x18017e26b  push    r15
0x18017e26d  lea     rbp, [rsp-2Fh]
0x18017e272  sub     rsp, 0E8h
0x18017e279  mov     rdi, r9
0x18017e27c  mov     rsi, r8
0x18017e27f  mov     rbx, rdx
0x18017e282  mov     r14, rcx
0x18017e285  xor     r15d, r15d
0x18017e288  mov     [rsp+110h+pAptType], r15d
0x18017e28d  mov     [rbp+57h+pAptQualifier], r15d
0x18017e291  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x18017e295  lea     rcx, [rsp+110h+pAptType]; pAptType
0x18017e29a  call    cs:__imp_CoGetApartmentType
0x18017e2a0  mov     rcx, [rbp+5Fh]; this
0x18017e2a4  test    eax, eax
0x18017e2a6  jns     loc_18017E365
0x18017e2ac  mov     r9d, eax; char *
0x18017e2af  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e2b6  lea     edx, [r15+29h]; void *
0x18017e2ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017e2bf  lea     rcx, [rbp+57h+var_C0]
0x18017e2c3  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x18017e2c8  nop
0x18017e2c9  mov     [rbp+57h+var_C8], r15
0x18017e2cd  mov     [rbp+57h+var_B0], r14
0x18017e2d1  mov     [rbp+57h+var_A8], rsi
0x18017e2d5  mov     [rbp+57h+var_A0], rdi
0x18017e2d9  lea     rax, [rbp+57h+var_C8]
0x18017e2dd  mov     [rbp+57h+var_98], rax
0x18017e2e1  lea     rax, [rbp+57h+var_C0]
0x18017e2e5  mov     [rbp+57h+var_90], rax
0x18017e2e9  lea     rdx, [rbp+57h+var_B0]
0x18017e2ed  lea     rcx, [rsp+110h+var_D8]
0x18017e2f2  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_4d2353c299f4b0535b54e9793e2a183c_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_4d2353c299f4b0535b54e9793e2a183c_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_4d2353c299f4b0535b54e9793e2a183c_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_4d2353c299f4b0535b54e9793e2a183c_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_4d2353c299f4b0535b54e9793e2a183c_ &>,_lambda_4d2353c299f4b0535b54e9793e2a183c_ &>(_lambda_4d2353c299f4b0535b54e9793e2a183c_ &)
0x18017e2f7  mov     rdi, [rax]
0x18017e2fa  mov     [rax], r15
0x18017e2fd  mov     rcx, [rsp+110h+var_D8]
0x18017e302  test    rcx, rcx
0x18017e305  jz      short loc_18017E311
0x18017e307  mov     [rsp+110h+var_D8], r15
0x18017e30c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18017e311  call    cs:__imp_GetCurrentThreadId
0x18017e317  mov     [rsp+110h+var_E8], r15
0x18017e31c  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x18017e321  xor     r9d, r9d
0x18017e324  mov     r8d, eax
0x18017e327  xor     edx, edx
0x18017e329  xor     ecx, ecx
0x18017e32b  call    cs:__imp_SHTaskPoolQueueTask
0x18017e331  mov     esi, eax
0x18017e333  test    rdi, rdi
0x18017e336  jz      short loc_18017E348
0x18017e338  mov     rdx, [rdi]
0x18017e33b  mov     rcx, rdi
0x18017e33e  mov     rax, [rdx+10h]
0x18017e342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e347  nop
0x18017e348  mov     rcx, [rbp+5Fh]; this
0x18017e34c  test    esi, esi
0x18017e34e  jns     short loc_18017E3BE
0x18017e350  mov     r9d, esi; char *
0x18017e353  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e35a  mov     edx, 46h ; 'F'; void *
0x18017e35f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e365  mov     eax, [rsp+110h+pAptType]
0x18017e369  test    eax, eax
0x18017e36b  jz      loc_18017E2BF
0x18017e371  cmp     eax, 3
0x18017e374  jz      loc_18017E2BF
0x18017e37a  lea     rcx, [rsp+110h+var_D8]
0x18017e37f  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x18017e384  nop
0x18017e385  mov     rcx, rdi
0x18017e388  call    ??R_lambda_349d3d247dd79cd0d5443630e41fb716_@@QEBA@XZ; _lambda_349d3d247dd79cd0d5443630e41fb716_::operator()(void)
0x18017e38d  xorps   xmm0, xmm0
0x18017e390  movups  xmmword ptr [rbx], xmm0
0x18017e393  movups  xmmword ptr [rbx+10h], xmm0
0x18017e397  mov     [rbx+20h], r15
0x18017e39b  mov     [rbx+28h], r15
0x18017e39f  mov     [rbx+30h], r15
0x18017e3a3  mov     [rbx+38h], r15d
0x18017e3a7  mov     [rbx+40h], r15
0x18017e3ab  mov     [rbx+48h], r15b
0x18017e3af  lea     rcx, [rsp+110h+var_D8]
0x18017e3b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18017e3b9  jmp     loc_18017E468
0x18017e3be  mov     rcx, [rbp+57h+var_C0]
0x18017e3c2  mov     rax, [rcx]
0x18017e3c5  xor     edx, edx
0x18017e3c7  mov     rax, [rax+10h]
0x18017e3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e3d0  mov     edi, eax
0x18017e3d2  xorps   xmm0, xmm0
0x18017e3d5  movups  [rbp+57h+var_80], xmm0
0x18017e3d9  movups  [rbp+57h+var_70], xmm0
0x18017e3dd  movdqa  [rbp+57h+var_60], xmm0
0x18017e3e2  mov     [rbp+57h+var_50], r15
0x18017e3e6  mov     [rbp+57h+var_48], r15d
0x18017e3ea  mov     [rbp+57h+var_40], r15
0x18017e3ee  mov     [rbp+57h+var_38], r15b
0x18017e3f2  test    eax, eax
0x18017e3f4  jns     short loc_18017E421
0x18017e3f6  mov     rcx, [rbp+57h+var_C8]
0x18017e3fa  test    rcx, rcx
0x18017e3fd  jz      short loc_18017E421
0x18017e3ff  call    cs:__imp_SetRestrictedErrorInfo
0x18017e405  mov     rcx, [rbp+5Fh]; this
0x18017e409  test    eax, eax
0x18017e40b  jns     short loc_18017E421
0x18017e40d  mov     r9d, eax; char *
0x18017e410  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e417  mov     edx, 4Fh ; 'O'; void *
0x18017e41c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017e421  mov     rcx, [rbp+5Fh]; this
0x18017e425  test    edi, edi
0x18017e427  jns     short loc_18017E43E
0x18017e429  mov     r9d, edi; char *
0x18017e42c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e433  mov     edx, 51h ; 'Q'; void *
0x18017e438  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e43e  lea     rdx, [rbp+57h+var_80]
0x18017e442  mov     rcx, rbx
0x18017e445  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x18017e44a  nop
0x18017e44b  lea     rcx, [rbp+57h+var_80]; this
0x18017e44f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18017e454  nop
0x18017e455  lea     rcx, [rbp+57h+var_C8]
0x18017e459  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18017e45e  nop
0x18017e45f  lea     rcx, [rbp+57h+var_C0]
0x18017e463  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x18017e468  mov     rax, rbx
0x18017e46b  add     rsp, 0E8h
0x18017e472  pop     r15
0x18017e474  pop     r14
0x18017e476  pop     rdi
0x18017e477  pop     rsi
0x18017e478  pop     rbx
0x18017e479  pop     rbp
0x18017e47a  retn
```
