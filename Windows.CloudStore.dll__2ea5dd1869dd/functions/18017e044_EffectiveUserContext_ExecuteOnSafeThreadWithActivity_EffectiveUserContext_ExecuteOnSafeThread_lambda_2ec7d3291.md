# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_2ec7d32914dc0838c3dcc8c4120598c2_>(_lambda_2ec7d32914dc0838c3dcc8c4120598c2_ &&)'::`2'::NopActivity const,_lambda_2ec7d32914dc0838c3dcc8c4120598c2_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_2ec7d32914dc0838c3dcc8c4120598c2_>(_lambda_2ec7d32914dc0838c3dcc8c4120598c2_ &&)'::`2'::NopActivity const &,_lambda_2ec7d32914dc0838c3dcc8c4120598c2_ &)

- ea: `0x18017e044`
- end: `0x18017e25b`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_2ec7d32914dc0838c3dcc8c4120598c2_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_2ec7d32914dc0838c3dcc8c4120598c2_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_2ec7d32914dc0838c3dcc8c4120598c2_@@@0@QEBAX$$QEAV_lambda_2ec7d32914dc0838c3dcc8c4120598c2_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18017fa40`

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
- `0x18010cf8c`
- `0x18017e044`
- `0x1801810e0`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18017e10b`
- `SHCORE!SHTaskPoolQueueTask` at `0x18017e10b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017e0f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017e0f1`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017e07a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017e07a`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017e1df`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017e1df`

## string_xrefs

- `0x18017e08f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017e133`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017e1f0`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017e20c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_2ec7d32914dc0838c3dcc8c4120598c2_>'::`2'::NopActivity const,AX$$QEAV_lambda_2ec7d32914dc0838c3dcc8c4120598c2_ const * const>(
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
      _lambda_2ec7d32914dc0838c3dcc8c4120598c2_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_b8093afbb2db965bc86adbc0df89dd6c_ &>,_lambda_b8093afbb2db965bc86adbc0df89dd6c_ &>(
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
0x18017e044  push    rbp
0x18017e046  push    rbx
0x18017e047  push    rsi
0x18017e048  push    rdi
0x18017e049  push    r14
0x18017e04b  push    r15
0x18017e04d  lea     rbp, [rsp-2Fh]
0x18017e052  sub     rsp, 0E8h
0x18017e059  mov     rdi, r9
0x18017e05c  mov     rsi, r8
0x18017e05f  mov     rbx, rdx
0x18017e062  mov     r14, rcx
0x18017e065  xor     r15d, r15d
0x18017e068  mov     [rsp+110h+pAptType], r15d
0x18017e06d  mov     [rbp+57h+pAptQualifier], r15d
0x18017e071  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x18017e075  lea     rcx, [rsp+110h+pAptType]; pAptType
0x18017e07a  call    cs:__imp_CoGetApartmentType
0x18017e080  mov     rcx, [rbp+5Fh]; this
0x18017e084  test    eax, eax
0x18017e086  jns     loc_18017E145
0x18017e08c  mov     r9d, eax; char *
0x18017e08f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e096  lea     edx, [r15+29h]; void *
0x18017e09a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017e09f  lea     rcx, [rbp+57h+var_C0]
0x18017e0a3  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x18017e0a8  nop
0x18017e0a9  mov     [rbp+57h+var_C8], r15
0x18017e0ad  mov     [rbp+57h+var_B0], r14
0x18017e0b1  mov     [rbp+57h+var_A8], rsi
0x18017e0b5  mov     [rbp+57h+var_A0], rdi
0x18017e0b9  lea     rax, [rbp+57h+var_C8]
0x18017e0bd  mov     [rbp+57h+var_98], rax
0x18017e0c1  lea     rax, [rbp+57h+var_C0]
0x18017e0c5  mov     [rbp+57h+var_90], rax
0x18017e0c9  lea     rdx, [rbp+57h+var_B0]
0x18017e0cd  lea     rcx, [rsp+110h+var_D8]
0x18017e0d2  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_b8093afbb2db965bc86adbc0df89dd6c_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_b8093afbb2db965bc86adbc0df89dd6c_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_b8093afbb2db965bc86adbc0df89dd6c_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_b8093afbb2db965bc86adbc0df89dd6c_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_b8093afbb2db965bc86adbc0df89dd6c_ &>,_lambda_b8093afbb2db965bc86adbc0df89dd6c_ &>(_lambda_b8093afbb2db965bc86adbc0df89dd6c_ &)
0x18017e0d7  mov     rdi, [rax]
0x18017e0da  mov     [rax], r15
0x18017e0dd  mov     rcx, [rsp+110h+var_D8]
0x18017e0e2  test    rcx, rcx
0x18017e0e5  jz      short loc_18017E0F1
0x18017e0e7  mov     [rsp+110h+var_D8], r15
0x18017e0ec  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18017e0f1  call    cs:__imp_GetCurrentThreadId
0x18017e0f7  mov     [rsp+110h+var_E8], r15
0x18017e0fc  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x18017e101  xor     r9d, r9d
0x18017e104  mov     r8d, eax
0x18017e107  xor     edx, edx
0x18017e109  xor     ecx, ecx
0x18017e10b  call    cs:__imp_SHTaskPoolQueueTask
0x18017e111  mov     esi, eax
0x18017e113  test    rdi, rdi
0x18017e116  jz      short loc_18017E128
0x18017e118  mov     rdx, [rdi]
0x18017e11b  mov     rcx, rdi
0x18017e11e  mov     rax, [rdx+10h]
0x18017e122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e127  nop
0x18017e128  mov     rcx, [rbp+5Fh]; this
0x18017e12c  test    esi, esi
0x18017e12e  jns     short loc_18017E19E
0x18017e130  mov     r9d, esi; char *
0x18017e133  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e13a  mov     edx, 46h ; 'F'; void *
0x18017e13f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e145  mov     eax, [rsp+110h+pAptType]
0x18017e149  test    eax, eax
0x18017e14b  jz      loc_18017E09F
0x18017e151  cmp     eax, 3
0x18017e154  jz      loc_18017E09F
0x18017e15a  lea     rcx, [rsp+110h+var_D8]
0x18017e15f  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x18017e164  nop
0x18017e165  mov     rcx, rdi
0x18017e168  call    ??R_lambda_2ec7d32914dc0838c3dcc8c4120598c2_@@QEBA@XZ; _lambda_2ec7d32914dc0838c3dcc8c4120598c2_::operator()(void)
0x18017e16d  xorps   xmm0, xmm0
0x18017e170  movups  xmmword ptr [rbx], xmm0
0x18017e173  movups  xmmword ptr [rbx+10h], xmm0
0x18017e177  mov     [rbx+20h], r15
0x18017e17b  mov     [rbx+28h], r15
0x18017e17f  mov     [rbx+30h], r15
0x18017e183  mov     [rbx+38h], r15d
0x18017e187  mov     [rbx+40h], r15
0x18017e18b  mov     [rbx+48h], r15b
0x18017e18f  lea     rcx, [rsp+110h+var_D8]
0x18017e194  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18017e199  jmp     loc_18017E248
0x18017e19e  mov     rcx, [rbp+57h+var_C0]
0x18017e1a2  mov     rax, [rcx]
0x18017e1a5  xor     edx, edx
0x18017e1a7  mov     rax, [rax+10h]
0x18017e1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e1b0  mov     edi, eax
0x18017e1b2  xorps   xmm0, xmm0
0x18017e1b5  movups  [rbp+57h+var_80], xmm0
0x18017e1b9  movups  [rbp+57h+var_70], xmm0
0x18017e1bd  movdqa  [rbp+57h+var_60], xmm0
0x18017e1c2  mov     [rbp+57h+var_50], r15
0x18017e1c6  mov     [rbp+57h+var_48], r15d
0x18017e1ca  mov     [rbp+57h+var_40], r15
0x18017e1ce  mov     [rbp+57h+var_38], r15b
0x18017e1d2  test    eax, eax
0x18017e1d4  jns     short loc_18017E201
0x18017e1d6  mov     rcx, [rbp+57h+var_C8]
0x18017e1da  test    rcx, rcx
0x18017e1dd  jz      short loc_18017E201
0x18017e1df  call    cs:__imp_SetRestrictedErrorInfo
0x18017e1e5  mov     rcx, [rbp+5Fh]; this
0x18017e1e9  test    eax, eax
0x18017e1eb  jns     short loc_18017E201
0x18017e1ed  mov     r9d, eax; char *
0x18017e1f0  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e1f7  mov     edx, 4Fh ; 'O'; void *
0x18017e1fc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017e201  mov     rcx, [rbp+5Fh]; this
0x18017e205  test    edi, edi
0x18017e207  jns     short loc_18017E21E
0x18017e209  mov     r9d, edi; char *
0x18017e20c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e213  mov     edx, 51h ; 'Q'; void *
0x18017e218  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e21e  lea     rdx, [rbp+57h+var_80]
0x18017e222  mov     rcx, rbx
0x18017e225  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x18017e22a  nop
0x18017e22b  lea     rcx, [rbp+57h+var_80]; this
0x18017e22f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18017e234  nop
0x18017e235  lea     rcx, [rbp+57h+var_C8]
0x18017e239  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18017e23e  nop
0x18017e23f  lea     rcx, [rbp+57h+var_C0]
0x18017e243  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x18017e248  mov     rax, rbx
0x18017e24b  add     rsp, 0E8h
0x18017e252  pop     r15
0x18017e254  pop     r14
0x18017e256  pop     rdi
0x18017e257  pop     rsi
0x18017e258  pop     rbx
0x18017e259  pop     rbp
0x18017e25a  retn
```
