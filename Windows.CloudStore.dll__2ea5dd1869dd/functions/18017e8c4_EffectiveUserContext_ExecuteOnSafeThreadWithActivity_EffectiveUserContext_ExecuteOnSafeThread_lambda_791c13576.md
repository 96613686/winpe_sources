# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_791c135764b78fc6b7ac77b556c39913_>(_lambda_791c135764b78fc6b7ac77b556c39913_ &&)'::`2'::NopActivity const,_lambda_791c135764b78fc6b7ac77b556c39913_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_791c135764b78fc6b7ac77b556c39913_>(_lambda_791c135764b78fc6b7ac77b556c39913_ &&)'::`2'::NopActivity const &,_lambda_791c135764b78fc6b7ac77b556c39913_ &)

- ea: `0x18017e8c4`
- end: `0x18017eadb`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_791c135764b78fc6b7ac77b556c39913_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_791c135764b78fc6b7ac77b556c39913_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_791c135764b78fc6b7ac77b556c39913_@@@0@QEBAX$$QEAV_lambda_791c135764b78fc6b7ac77b556c39913_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18017fe78`

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
- `0x18017e8c4`
- `0x180181370`
- `0x180181cec`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18017e98b`
- `SHCORE!SHTaskPoolQueueTask` at `0x18017e98b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017e971`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017e971`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017e8fa`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017e8fa`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017ea5f`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017ea5f`

## string_xrefs

- `0x18017e90f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017e9b3`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017ea70`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017ea8c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_791c135764b78fc6b7ac77b556c39913_>'::`2'::NopActivity const,AX$$QEAV_lambda_791c135764b78fc6b7ac77b556c39913_ const * const>(
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
      _lambda_791c135764b78fc6b7ac77b556c39913_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_efa1f17c00e4d5309c6ef9dbc614a64f_ &>,_lambda_efa1f17c00e4d5309c6ef9dbc614a64f_ &>(
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
0x18017e8c4  push    rbp
0x18017e8c6  push    rbx
0x18017e8c7  push    rsi
0x18017e8c8  push    rdi
0x18017e8c9  push    r14
0x18017e8cb  push    r15
0x18017e8cd  lea     rbp, [rsp-2Fh]
0x18017e8d2  sub     rsp, 0E8h
0x18017e8d9  mov     rdi, r9
0x18017e8dc  mov     rsi, r8
0x18017e8df  mov     rbx, rdx
0x18017e8e2  mov     r14, rcx
0x18017e8e5  xor     r15d, r15d
0x18017e8e8  mov     [rsp+110h+pAptType], r15d
0x18017e8ed  mov     [rbp+57h+pAptQualifier], r15d
0x18017e8f1  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x18017e8f5  lea     rcx, [rsp+110h+pAptType]; pAptType
0x18017e8fa  call    cs:__imp_CoGetApartmentType
0x18017e900  mov     rcx, [rbp+5Fh]; this
0x18017e904  test    eax, eax
0x18017e906  jns     loc_18017E9C5
0x18017e90c  mov     r9d, eax; char *
0x18017e90f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e916  lea     edx, [r15+29h]; void *
0x18017e91a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017e91f  lea     rcx, [rbp+57h+var_C0]
0x18017e923  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x18017e928  nop
0x18017e929  mov     [rbp+57h+var_C8], r15
0x18017e92d  mov     [rbp+57h+var_B0], r14
0x18017e931  mov     [rbp+57h+var_A8], rsi
0x18017e935  mov     [rbp+57h+var_A0], rdi
0x18017e939  lea     rax, [rbp+57h+var_C8]
0x18017e93d  mov     [rbp+57h+var_98], rax
0x18017e941  lea     rax, [rbp+57h+var_C0]
0x18017e945  mov     [rbp+57h+var_90], rax
0x18017e949  lea     rdx, [rbp+57h+var_B0]
0x18017e94d  lea     rcx, [rsp+110h+var_D8]
0x18017e952  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_efa1f17c00e4d5309c6ef9dbc614a64f_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_efa1f17c00e4d5309c6ef9dbc614a64f_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_efa1f17c00e4d5309c6ef9dbc614a64f_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_efa1f17c00e4d5309c6ef9dbc614a64f_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_efa1f17c00e4d5309c6ef9dbc614a64f_ &>,_lambda_efa1f17c00e4d5309c6ef9dbc614a64f_ &>(_lambda_efa1f17c00e4d5309c6ef9dbc614a64f_ &)
0x18017e957  mov     rdi, [rax]
0x18017e95a  mov     [rax], r15
0x18017e95d  mov     rcx, [rsp+110h+var_D8]
0x18017e962  test    rcx, rcx
0x18017e965  jz      short loc_18017E971
0x18017e967  mov     [rsp+110h+var_D8], r15
0x18017e96c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18017e971  call    cs:__imp_GetCurrentThreadId
0x18017e977  mov     [rsp+110h+var_E8], r15
0x18017e97c  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x18017e981  xor     r9d, r9d
0x18017e984  mov     r8d, eax
0x18017e987  xor     edx, edx
0x18017e989  xor     ecx, ecx
0x18017e98b  call    cs:__imp_SHTaskPoolQueueTask
0x18017e991  mov     esi, eax
0x18017e993  test    rdi, rdi
0x18017e996  jz      short loc_18017E9A8
0x18017e998  mov     rdx, [rdi]
0x18017e99b  mov     rcx, rdi
0x18017e99e  mov     rax, [rdx+10h]
0x18017e9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e9a7  nop
0x18017e9a8  mov     rcx, [rbp+5Fh]; this
0x18017e9ac  test    esi, esi
0x18017e9ae  jns     short loc_18017EA1E
0x18017e9b0  mov     r9d, esi; char *
0x18017e9b3  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e9ba  mov     edx, 46h ; 'F'; void *
0x18017e9bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e9c5  mov     eax, [rsp+110h+pAptType]
0x18017e9c9  test    eax, eax
0x18017e9cb  jz      loc_18017E91F
0x18017e9d1  cmp     eax, 3
0x18017e9d4  jz      loc_18017E91F
0x18017e9da  lea     rcx, [rsp+110h+var_D8]
0x18017e9df  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x18017e9e4  nop
0x18017e9e5  mov     rcx, rdi
0x18017e9e8  call    ??R_lambda_791c135764b78fc6b7ac77b556c39913_@@QEBA@XZ; _lambda_791c135764b78fc6b7ac77b556c39913_::operator()(void)
0x18017e9ed  xorps   xmm0, xmm0
0x18017e9f0  movups  xmmword ptr [rbx], xmm0
0x18017e9f3  movups  xmmword ptr [rbx+10h], xmm0
0x18017e9f7  mov     [rbx+20h], r15
0x18017e9fb  mov     [rbx+28h], r15
0x18017e9ff  mov     [rbx+30h], r15
0x18017ea03  mov     [rbx+38h], r15d
0x18017ea07  mov     [rbx+40h], r15
0x18017ea0b  mov     [rbx+48h], r15b
0x18017ea0f  lea     rcx, [rsp+110h+var_D8]
0x18017ea14  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18017ea19  jmp     loc_18017EAC8
0x18017ea1e  mov     rcx, [rbp+57h+var_C0]
0x18017ea22  mov     rax, [rcx]
0x18017ea25  xor     edx, edx
0x18017ea27  mov     rax, [rax+10h]
0x18017ea2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ea30  mov     edi, eax
0x18017ea32  xorps   xmm0, xmm0
0x18017ea35  movups  [rbp+57h+var_80], xmm0
0x18017ea39  movups  [rbp+57h+var_70], xmm0
0x18017ea3d  movdqa  [rbp+57h+var_60], xmm0
0x18017ea42  mov     [rbp+57h+var_50], r15
0x18017ea46  mov     [rbp+57h+var_48], r15d
0x18017ea4a  mov     [rbp+57h+var_40], r15
0x18017ea4e  mov     [rbp+57h+var_38], r15b
0x18017ea52  test    eax, eax
0x18017ea54  jns     short loc_18017EA81
0x18017ea56  mov     rcx, [rbp+57h+var_C8]
0x18017ea5a  test    rcx, rcx
0x18017ea5d  jz      short loc_18017EA81
0x18017ea5f  call    cs:__imp_SetRestrictedErrorInfo
0x18017ea65  mov     rcx, [rbp+5Fh]; this
0x18017ea69  test    eax, eax
0x18017ea6b  jns     short loc_18017EA81
0x18017ea6d  mov     r9d, eax; char *
0x18017ea70  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017ea77  mov     edx, 4Fh ; 'O'; void *
0x18017ea7c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017ea81  mov     rcx, [rbp+5Fh]; this
0x18017ea85  test    edi, edi
0x18017ea87  jns     short loc_18017EA9E
0x18017ea89  mov     r9d, edi; char *
0x18017ea8c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017ea93  mov     edx, 51h ; 'Q'; void *
0x18017ea98  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017ea9e  lea     rdx, [rbp+57h+var_80]
0x18017eaa2  mov     rcx, rbx
0x18017eaa5  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x18017eaaa  nop
0x18017eaab  lea     rcx, [rbp+57h+var_80]; this
0x18017eaaf  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18017eab4  nop
0x18017eab5  lea     rcx, [rbp+57h+var_C8]
0x18017eab9  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18017eabe  nop
0x18017eabf  lea     rcx, [rbp+57h+var_C0]
0x18017eac3  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x18017eac8  mov     rax, rbx
0x18017eacb  add     rsp, 0E8h
0x18017ead2  pop     r15
0x18017ead4  pop     r14
0x18017ead6  pop     rdi
0x18017ead7  pop     rsi
0x18017ead8  pop     rbx
0x18017ead9  pop     rbp
0x18017eada  retn
```
