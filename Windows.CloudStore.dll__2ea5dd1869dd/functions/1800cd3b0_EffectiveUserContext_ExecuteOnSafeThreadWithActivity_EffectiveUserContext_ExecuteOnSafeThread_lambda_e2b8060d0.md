# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_e2b8060d0c7157fdb370b6269026234e_>(_lambda_e2b8060d0c7157fdb370b6269026234e_ &&)'::`2'::NopActivity const,_lambda_e2b8060d0c7157fdb370b6269026234e_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_e2b8060d0c7157fdb370b6269026234e_>(_lambda_e2b8060d0c7157fdb370b6269026234e_ &&)'::`2'::NopActivity const &,_lambda_e2b8060d0c7157fdb370b6269026234e_ &)

- ea: `0x1800cd3b0`
- end: `0x1800cd5c7`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_e2b8060d0c7157fdb370b6269026234e_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_e2b8060d0c7157fdb370b6269026234e_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_e2b8060d0c7157fdb370b6269026234e_@@@0@QEBAX$$QEAV_lambda_e2b8060d0c7157fdb370b6269026234e_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180181730`

## callees

- `0x18000dfe4`
- `0x180010688`
- `0x180016cf4`
- `0x180035b7c`
- `0x180038db8`
- `0x18005dde0`
- `0x180061e60`
- `0x180064888`
- `0x1800cd3b0`
- `0x1800ce314`
- `0x1800e93e0`
- `0x180180a78`
- `0x180182450`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800cd477`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800cd477`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd45d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd45d`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cd3e6`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cd3e6`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cd54b`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cd54b`

## string_xrefs

- `0x1800cd3fb`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cd49f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cd55c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cd578`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_e2b8060d0c7157fdb370b6269026234e_>'::`2'::NopActivity const,AX$$QEAV_lambda_e2b8060d0c7157fdb370b6269026234e_ const * const>(
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
      _lambda_e2b8060d0c7157fdb370b6269026234e_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_485a6b5c3e2bb4c360d2344e8501d6d6_ &>,_lambda_485a6b5c3e2bb4c360d2344e8501d6d6_ &>(
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
0x1800cd3b0  push    rbp
0x1800cd3b2  push    rbx
0x1800cd3b3  push    rsi
0x1800cd3b4  push    rdi
0x1800cd3b5  push    r14
0x1800cd3b7  push    r15
0x1800cd3b9  lea     rbp, [rsp-2Fh]
0x1800cd3be  sub     rsp, 0E8h
0x1800cd3c5  mov     rdi, r9
0x1800cd3c8  mov     rsi, r8
0x1800cd3cb  mov     rbx, rdx
0x1800cd3ce  mov     r14, rcx
0x1800cd3d1  xor     r15d, r15d
0x1800cd3d4  mov     [rsp+110h+pAptType], r15d
0x1800cd3d9  mov     [rbp+57h+pAptQualifier], r15d
0x1800cd3dd  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800cd3e1  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800cd3e6  call    cs:__imp_CoGetApartmentType
0x1800cd3ec  mov     rcx, [rbp+5Fh]; this
0x1800cd3f0  test    eax, eax
0x1800cd3f2  jns     loc_1800CD4B1
0x1800cd3f8  mov     r9d, eax; char *
0x1800cd3fb  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd402  lea     edx, [r15+29h]; void *
0x1800cd406  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cd40b  lea     rcx, [rbp+57h+var_C0]
0x1800cd40f  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800cd414  nop
0x1800cd415  mov     [rbp+57h+var_C8], r15
0x1800cd419  mov     [rbp+57h+var_B0], r14
0x1800cd41d  mov     [rbp+57h+var_A8], rsi
0x1800cd421  mov     [rbp+57h+var_A0], rdi
0x1800cd425  lea     rax, [rbp+57h+var_C8]
0x1800cd429  mov     [rbp+57h+var_98], rax
0x1800cd42d  lea     rax, [rbp+57h+var_C0]
0x1800cd431  mov     [rbp+57h+var_90], rax
0x1800cd435  lea     rdx, [rbp+57h+var_B0]
0x1800cd439  lea     rcx, [rsp+110h+var_D8]
0x1800cd43e  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_485a6b5c3e2bb4c360d2344e8501d6d6_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_485a6b5c3e2bb4c360d2344e8501d6d6_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_485a6b5c3e2bb4c360d2344e8501d6d6_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_485a6b5c3e2bb4c360d2344e8501d6d6_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_485a6b5c3e2bb4c360d2344e8501d6d6_ &>,_lambda_485a6b5c3e2bb4c360d2344e8501d6d6_ &>(_lambda_485a6b5c3e2bb4c360d2344e8501d6d6_ &)
0x1800cd443  mov     rdi, [rax]
0x1800cd446  mov     [rax], r15
0x1800cd449  mov     rcx, [rsp+110h+var_D8]
0x1800cd44e  test    rcx, rcx
0x1800cd451  jz      short loc_1800CD45D
0x1800cd453  mov     [rsp+110h+var_D8], r15
0x1800cd458  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800cd45d  call    cs:__imp_GetCurrentThreadId
0x1800cd463  mov     [rsp+110h+var_E8], r15
0x1800cd468  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800cd46d  xor     r9d, r9d
0x1800cd470  mov     r8d, eax
0x1800cd473  xor     edx, edx
0x1800cd475  xor     ecx, ecx
0x1800cd477  call    cs:__imp_SHTaskPoolQueueTask
0x1800cd47d  mov     esi, eax
0x1800cd47f  test    rdi, rdi
0x1800cd482  jz      short loc_1800CD494
0x1800cd484  mov     rdx, [rdi]
0x1800cd487  mov     rcx, rdi
0x1800cd48a  mov     rax, [rdx+10h]
0x1800cd48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd493  nop
0x1800cd494  mov     rcx, [rbp+5Fh]; this
0x1800cd498  test    esi, esi
0x1800cd49a  jns     short loc_1800CD50A
0x1800cd49c  mov     r9d, esi; char *
0x1800cd49f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd4a6  mov     edx, 46h ; 'F'; void *
0x1800cd4ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cd4b1  mov     eax, [rsp+110h+pAptType]
0x1800cd4b5  test    eax, eax
0x1800cd4b7  jz      loc_1800CD40B
0x1800cd4bd  cmp     eax, 3
0x1800cd4c0  jz      loc_1800CD40B
0x1800cd4c6  lea     rcx, [rsp+110h+var_D8]
0x1800cd4cb  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cd4d0  nop
0x1800cd4d1  mov     rcx, rdi
0x1800cd4d4  call    ??R_lambda_e2b8060d0c7157fdb370b6269026234e_@@QEBA@XZ; _lambda_e2b8060d0c7157fdb370b6269026234e_::operator()(void)
0x1800cd4d9  xorps   xmm0, xmm0
0x1800cd4dc  movups  xmmword ptr [rbx], xmm0
0x1800cd4df  movups  xmmword ptr [rbx+10h], xmm0
0x1800cd4e3  mov     [rbx+20h], r15
0x1800cd4e7  mov     [rbx+28h], r15
0x1800cd4eb  mov     [rbx+30h], r15
0x1800cd4ef  mov     [rbx+38h], r15d
0x1800cd4f3  mov     [rbx+40h], r15
0x1800cd4f7  mov     [rbx+48h], r15b
0x1800cd4fb  lea     rcx, [rsp+110h+var_D8]
0x1800cd500  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800cd505  jmp     loc_1800CD5B4
0x1800cd50a  mov     rcx, [rbp+57h+var_C0]
0x1800cd50e  mov     rax, [rcx]
0x1800cd511  xor     edx, edx
0x1800cd513  mov     rax, [rax+10h]
0x1800cd517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd51c  mov     edi, eax
0x1800cd51e  xorps   xmm0, xmm0
0x1800cd521  movups  [rbp+57h+var_80], xmm0
0x1800cd525  movups  [rbp+57h+var_70], xmm0
0x1800cd529  movdqa  [rbp+57h+var_60], xmm0
0x1800cd52e  mov     [rbp+57h+var_50], r15
0x1800cd532  mov     [rbp+57h+var_48], r15d
0x1800cd536  mov     [rbp+57h+var_40], r15
0x1800cd53a  mov     [rbp+57h+var_38], r15b
0x1800cd53e  test    eax, eax
0x1800cd540  jns     short loc_1800CD56D
0x1800cd542  mov     rcx, [rbp+57h+var_C8]
0x1800cd546  test    rcx, rcx
0x1800cd549  jz      short loc_1800CD56D
0x1800cd54b  call    cs:__imp_SetRestrictedErrorInfo
0x1800cd551  mov     rcx, [rbp+5Fh]; this
0x1800cd555  test    eax, eax
0x1800cd557  jns     short loc_1800CD56D
0x1800cd559  mov     r9d, eax; char *
0x1800cd55c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd563  mov     edx, 4Fh ; 'O'; void *
0x1800cd568  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cd56d  mov     rcx, [rbp+5Fh]; this
0x1800cd571  test    edi, edi
0x1800cd573  jns     short loc_1800CD58A
0x1800cd575  mov     r9d, edi; char *
0x1800cd578  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd57f  mov     edx, 51h ; 'Q'; void *
0x1800cd584  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cd58a  lea     rdx, [rbp+57h+var_80]
0x1800cd58e  mov     rcx, rbx
0x1800cd591  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800cd596  nop
0x1800cd597  lea     rcx, [rbp+57h+var_80]; this
0x1800cd59b  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800cd5a0  nop
0x1800cd5a1  lea     rcx, [rbp+57h+var_C8]
0x1800cd5a5  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800cd5aa  nop
0x1800cd5ab  lea     rcx, [rbp+57h+var_C0]
0x1800cd5af  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800cd5b4  mov     rax, rbx
0x1800cd5b7  add     rsp, 0E8h
0x1800cd5be  pop     r15
0x1800cd5c0  pop     r14
0x1800cd5c2  pop     rdi
0x1800cd5c3  pop     rsi
0x1800cd5c4  pop     rbx
0x1800cd5c5  pop     rbp
0x1800cd5c6  retn
```
