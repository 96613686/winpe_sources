# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_7b4a3c6cfb441a7447355f7171503257_>(_lambda_7b4a3c6cfb441a7447355f7171503257_ &&)'::`2'::NopActivity const,_lambda_7b4a3c6cfb441a7447355f7171503257_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_7b4a3c6cfb441a7447355f7171503257_>(_lambda_7b4a3c6cfb441a7447355f7171503257_ &&)'::`2'::NopActivity const &,_lambda_7b4a3c6cfb441a7447355f7171503257_ &)

- ea: `0x1800cc704`
- end: `0x1800cc91b`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_7b4a3c6cfb441a7447355f7171503257_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_7b4a3c6cfb441a7447355f7171503257_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_7b4a3c6cfb441a7447355f7171503257_@@@0@QEBAX$$QEAV_lambda_7b4a3c6cfb441a7447355f7171503257_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801801f0`

## callees

- `0x18000dfe4`
- `0x180010688`
- `0x180016cf4`
- `0x180035b7c`
- `0x180038db8`
- `0x18005dde0`
- `0x180061e60`
- `0x180064888`
- `0x1800cc704`
- `0x1800ce314`
- `0x1800e93e0`
- `0x180180744`
- `0x180181dc4`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800cc7cb`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800cc7cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cc7b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cc7b1`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cc73a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cc73a`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cc89f`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cc89f`

## string_xrefs

- `0x1800cc74f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cc7f3`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cc8b0`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cc8cc`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_7b4a3c6cfb441a7447355f7171503257_>'::`2'::NopActivity const,AX$$QEAV_lambda_7b4a3c6cfb441a7447355f7171503257_ const * const>(
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
      _lambda_7b4a3c6cfb441a7447355f7171503257_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_33df8ae52dd5eae9ff95d047520d6ee2_ &>,_lambda_33df8ae52dd5eae9ff95d047520d6ee2_ &>(
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
0x1800cc704  push    rbp
0x1800cc706  push    rbx
0x1800cc707  push    rsi
0x1800cc708  push    rdi
0x1800cc709  push    r14
0x1800cc70b  push    r15
0x1800cc70d  lea     rbp, [rsp-2Fh]
0x1800cc712  sub     rsp, 0E8h
0x1800cc719  mov     rdi, r9
0x1800cc71c  mov     rsi, r8
0x1800cc71f  mov     rbx, rdx
0x1800cc722  mov     r14, rcx
0x1800cc725  xor     r15d, r15d
0x1800cc728  mov     [rsp+110h+pAptType], r15d
0x1800cc72d  mov     [rbp+57h+pAptQualifier], r15d
0x1800cc731  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800cc735  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800cc73a  call    cs:__imp_CoGetApartmentType
0x1800cc740  mov     rcx, [rbp+5Fh]; this
0x1800cc744  test    eax, eax
0x1800cc746  jns     loc_1800CC805
0x1800cc74c  mov     r9d, eax; char *
0x1800cc74f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cc756  lea     edx, [r15+29h]; void *
0x1800cc75a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cc75f  lea     rcx, [rbp+57h+var_C0]
0x1800cc763  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800cc768  nop
0x1800cc769  mov     [rbp+57h+var_C8], r15
0x1800cc76d  mov     [rbp+57h+var_B0], r14
0x1800cc771  mov     [rbp+57h+var_A8], rsi
0x1800cc775  mov     [rbp+57h+var_A0], rdi
0x1800cc779  lea     rax, [rbp+57h+var_C8]
0x1800cc77d  mov     [rbp+57h+var_98], rax
0x1800cc781  lea     rax, [rbp+57h+var_C0]
0x1800cc785  mov     [rbp+57h+var_90], rax
0x1800cc789  lea     rdx, [rbp+57h+var_B0]
0x1800cc78d  lea     rcx, [rsp+110h+var_D8]
0x1800cc792  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_33df8ae52dd5eae9ff95d047520d6ee2_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_33df8ae52dd5eae9ff95d047520d6ee2_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_33df8ae52dd5eae9ff95d047520d6ee2_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_33df8ae52dd5eae9ff95d047520d6ee2_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_33df8ae52dd5eae9ff95d047520d6ee2_ &>,_lambda_33df8ae52dd5eae9ff95d047520d6ee2_ &>(_lambda_33df8ae52dd5eae9ff95d047520d6ee2_ &)
0x1800cc797  mov     rdi, [rax]
0x1800cc79a  mov     [rax], r15
0x1800cc79d  mov     rcx, [rsp+110h+var_D8]
0x1800cc7a2  test    rcx, rcx
0x1800cc7a5  jz      short loc_1800CC7B1
0x1800cc7a7  mov     [rsp+110h+var_D8], r15
0x1800cc7ac  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800cc7b1  call    cs:__imp_GetCurrentThreadId
0x1800cc7b7  mov     [rsp+110h+var_E8], r15
0x1800cc7bc  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800cc7c1  xor     r9d, r9d
0x1800cc7c4  mov     r8d, eax
0x1800cc7c7  xor     edx, edx
0x1800cc7c9  xor     ecx, ecx
0x1800cc7cb  call    cs:__imp_SHTaskPoolQueueTask
0x1800cc7d1  mov     esi, eax
0x1800cc7d3  test    rdi, rdi
0x1800cc7d6  jz      short loc_1800CC7E8
0x1800cc7d8  mov     rdx, [rdi]
0x1800cc7db  mov     rcx, rdi
0x1800cc7de  mov     rax, [rdx+10h]
0x1800cc7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc7e7  nop
0x1800cc7e8  mov     rcx, [rbp+5Fh]; this
0x1800cc7ec  test    esi, esi
0x1800cc7ee  jns     short loc_1800CC85E
0x1800cc7f0  mov     r9d, esi; char *
0x1800cc7f3  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cc7fa  mov     edx, 46h ; 'F'; void *
0x1800cc7ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cc805  mov     eax, [rsp+110h+pAptType]
0x1800cc809  test    eax, eax
0x1800cc80b  jz      loc_1800CC75F
0x1800cc811  cmp     eax, 3
0x1800cc814  jz      loc_1800CC75F
0x1800cc81a  lea     rcx, [rsp+110h+var_D8]
0x1800cc81f  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cc824  nop
0x1800cc825  mov     rcx, rdi
0x1800cc828  call    ??R_lambda_7b4a3c6cfb441a7447355f7171503257_@@QEBA@XZ; _lambda_7b4a3c6cfb441a7447355f7171503257_::operator()(void)
0x1800cc82d  xorps   xmm0, xmm0
0x1800cc830  movups  xmmword ptr [rbx], xmm0
0x1800cc833  movups  xmmword ptr [rbx+10h], xmm0
0x1800cc837  mov     [rbx+20h], r15
0x1800cc83b  mov     [rbx+28h], r15
0x1800cc83f  mov     [rbx+30h], r15
0x1800cc843  mov     [rbx+38h], r15d
0x1800cc847  mov     [rbx+40h], r15
0x1800cc84b  mov     [rbx+48h], r15b
0x1800cc84f  lea     rcx, [rsp+110h+var_D8]
0x1800cc854  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800cc859  jmp     loc_1800CC908
0x1800cc85e  mov     rcx, [rbp+57h+var_C0]
0x1800cc862  mov     rax, [rcx]
0x1800cc865  xor     edx, edx
0x1800cc867  mov     rax, [rax+10h]
0x1800cc86b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc870  mov     edi, eax
0x1800cc872  xorps   xmm0, xmm0
0x1800cc875  movups  [rbp+57h+var_80], xmm0
0x1800cc879  movups  [rbp+57h+var_70], xmm0
0x1800cc87d  movdqa  [rbp+57h+var_60], xmm0
0x1800cc882  mov     [rbp+57h+var_50], r15
0x1800cc886  mov     [rbp+57h+var_48], r15d
0x1800cc88a  mov     [rbp+57h+var_40], r15
0x1800cc88e  mov     [rbp+57h+var_38], r15b
0x1800cc892  test    eax, eax
0x1800cc894  jns     short loc_1800CC8C1
0x1800cc896  mov     rcx, [rbp+57h+var_C8]
0x1800cc89a  test    rcx, rcx
0x1800cc89d  jz      short loc_1800CC8C1
0x1800cc89f  call    cs:__imp_SetRestrictedErrorInfo
0x1800cc8a5  mov     rcx, [rbp+5Fh]; this
0x1800cc8a9  test    eax, eax
0x1800cc8ab  jns     short loc_1800CC8C1
0x1800cc8ad  mov     r9d, eax; char *
0x1800cc8b0  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cc8b7  mov     edx, 4Fh ; 'O'; void *
0x1800cc8bc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cc8c1  mov     rcx, [rbp+5Fh]; this
0x1800cc8c5  test    edi, edi
0x1800cc8c7  jns     short loc_1800CC8DE
0x1800cc8c9  mov     r9d, edi; char *
0x1800cc8cc  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cc8d3  mov     edx, 51h ; 'Q'; void *
0x1800cc8d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cc8de  lea     rdx, [rbp+57h+var_80]
0x1800cc8e2  mov     rcx, rbx
0x1800cc8e5  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800cc8ea  nop
0x1800cc8eb  lea     rcx, [rbp+57h+var_80]; this
0x1800cc8ef  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800cc8f4  nop
0x1800cc8f5  lea     rcx, [rbp+57h+var_C8]
0x1800cc8f9  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800cc8fe  nop
0x1800cc8ff  lea     rcx, [rbp+57h+var_C0]
0x1800cc903  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800cc908  mov     rax, rbx
0x1800cc90b  add     rsp, 0E8h
0x1800cc912  pop     r15
0x1800cc914  pop     r14
0x1800cc916  pop     rdi
0x1800cc917  pop     rsi
0x1800cc918  pop     rbx
0x1800cc919  pop     rbp
0x1800cc91a  retn
```
