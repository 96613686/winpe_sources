# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_1de91bf676356cef32234193c108c07d_>(_lambda_1de91bf676356cef32234193c108c07d_ &&)'::`2'::NopActivity const,_lambda_1de91bf676356cef32234193c108c07d_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_1de91bf676356cef32234193c108c07d_>(_lambda_1de91bf676356cef32234193c108c07d_ &&)'::`2'::NopActivity const &,_lambda_1de91bf676356cef32234193c108c07d_ &)

- ea: `0x1800cc2c4`
- end: `0x1800cc4db`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_1de91bf676356cef32234193c108c07d_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_1de91bf676356cef32234193c108c07d_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_1de91bf676356cef32234193c108c07d_@@@0@QEBAX$$QEAV_lambda_1de91bf676356cef32234193c108c07d_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801803ac`

## callees

- `0x18000dfe4`
- `0x180010688`
- `0x180016cf4`
- `0x180035b7c`
- `0x180038db8`
- `0x18005dde0`
- `0x180061e60`
- `0x180064888`
- `0x1800cc2c4`
- `0x1800ce314`
- `0x1800e93e0`
- `0x180116a38`
- `0x180180ef4`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800cc38b`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800cc38b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cc371`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cc371`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cc2fa`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cc2fa`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cc45f`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cc45f`

## string_xrefs

- `0x1800cc30f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cc3b3`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cc470`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cc48c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_1de91bf676356cef32234193c108c07d_>'::`2'::NopActivity const,AX$$QEAV_lambda_1de91bf676356cef32234193c108c07d_ const * const>(
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
      _lambda_1de91bf676356cef32234193c108c07d_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_75a4d26c8ddd69d14bbc61f6a6ccc451_ &>,_lambda_75a4d26c8ddd69d14bbc61f6a6ccc451_ &>(
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
0x1800cc2c4  push    rbp
0x1800cc2c6  push    rbx
0x1800cc2c7  push    rsi
0x1800cc2c8  push    rdi
0x1800cc2c9  push    r14
0x1800cc2cb  push    r15
0x1800cc2cd  lea     rbp, [rsp-2Fh]
0x1800cc2d2  sub     rsp, 0E8h
0x1800cc2d9  mov     rdi, r9
0x1800cc2dc  mov     rsi, r8
0x1800cc2df  mov     rbx, rdx
0x1800cc2e2  mov     r14, rcx
0x1800cc2e5  xor     r15d, r15d
0x1800cc2e8  mov     [rsp+110h+pAptType], r15d
0x1800cc2ed  mov     [rbp+57h+pAptQualifier], r15d
0x1800cc2f1  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800cc2f5  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800cc2fa  call    cs:__imp_CoGetApartmentType
0x1800cc300  mov     rcx, [rbp+5Fh]; this
0x1800cc304  test    eax, eax
0x1800cc306  jns     loc_1800CC3C5
0x1800cc30c  mov     r9d, eax; char *
0x1800cc30f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cc316  lea     edx, [r15+29h]; void *
0x1800cc31a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cc31f  lea     rcx, [rbp+57h+var_C0]
0x1800cc323  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800cc328  nop
0x1800cc329  mov     [rbp+57h+var_C8], r15
0x1800cc32d  mov     [rbp+57h+var_B0], r14
0x1800cc331  mov     [rbp+57h+var_A8], rsi
0x1800cc335  mov     [rbp+57h+var_A0], rdi
0x1800cc339  lea     rax, [rbp+57h+var_C8]
0x1800cc33d  mov     [rbp+57h+var_98], rax
0x1800cc341  lea     rax, [rbp+57h+var_C0]
0x1800cc345  mov     [rbp+57h+var_90], rax
0x1800cc349  lea     rdx, [rbp+57h+var_B0]
0x1800cc34d  lea     rcx, [rsp+110h+var_D8]
0x1800cc352  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_75a4d26c8ddd69d14bbc61f6a6ccc451_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_75a4d26c8ddd69d14bbc61f6a6ccc451_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_75a4d26c8ddd69d14bbc61f6a6ccc451_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_75a4d26c8ddd69d14bbc61f6a6ccc451_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_75a4d26c8ddd69d14bbc61f6a6ccc451_ &>,_lambda_75a4d26c8ddd69d14bbc61f6a6ccc451_ &>(_lambda_75a4d26c8ddd69d14bbc61f6a6ccc451_ &)
0x1800cc357  mov     rdi, [rax]
0x1800cc35a  mov     [rax], r15
0x1800cc35d  mov     rcx, [rsp+110h+var_D8]
0x1800cc362  test    rcx, rcx
0x1800cc365  jz      short loc_1800CC371
0x1800cc367  mov     [rsp+110h+var_D8], r15
0x1800cc36c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800cc371  call    cs:__imp_GetCurrentThreadId
0x1800cc377  mov     [rsp+110h+var_E8], r15
0x1800cc37c  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800cc381  xor     r9d, r9d
0x1800cc384  mov     r8d, eax
0x1800cc387  xor     edx, edx
0x1800cc389  xor     ecx, ecx
0x1800cc38b  call    cs:__imp_SHTaskPoolQueueTask
0x1800cc391  mov     esi, eax
0x1800cc393  test    rdi, rdi
0x1800cc396  jz      short loc_1800CC3A8
0x1800cc398  mov     rdx, [rdi]
0x1800cc39b  mov     rcx, rdi
0x1800cc39e  mov     rax, [rdx+10h]
0x1800cc3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc3a7  nop
0x1800cc3a8  mov     rcx, [rbp+5Fh]; this
0x1800cc3ac  test    esi, esi
0x1800cc3ae  jns     short loc_1800CC41E
0x1800cc3b0  mov     r9d, esi; char *
0x1800cc3b3  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cc3ba  mov     edx, 46h ; 'F'; void *
0x1800cc3bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cc3c5  mov     eax, [rsp+110h+pAptType]
0x1800cc3c9  test    eax, eax
0x1800cc3cb  jz      loc_1800CC31F
0x1800cc3d1  cmp     eax, 3
0x1800cc3d4  jz      loc_1800CC31F
0x1800cc3da  lea     rcx, [rsp+110h+var_D8]
0x1800cc3df  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cc3e4  nop
0x1800cc3e5  mov     rcx, rdi
0x1800cc3e8  call    ??R_lambda_1de91bf676356cef32234193c108c07d_@@QEBA@XZ; _lambda_1de91bf676356cef32234193c108c07d_::operator()(void)
0x1800cc3ed  xorps   xmm0, xmm0
0x1800cc3f0  movups  xmmword ptr [rbx], xmm0
0x1800cc3f3  movups  xmmword ptr [rbx+10h], xmm0
0x1800cc3f7  mov     [rbx+20h], r15
0x1800cc3fb  mov     [rbx+28h], r15
0x1800cc3ff  mov     [rbx+30h], r15
0x1800cc403  mov     [rbx+38h], r15d
0x1800cc407  mov     [rbx+40h], r15
0x1800cc40b  mov     [rbx+48h], r15b
0x1800cc40f  lea     rcx, [rsp+110h+var_D8]
0x1800cc414  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800cc419  jmp     loc_1800CC4C8
0x1800cc41e  mov     rcx, [rbp+57h+var_C0]
0x1800cc422  mov     rax, [rcx]
0x1800cc425  xor     edx, edx
0x1800cc427  mov     rax, [rax+10h]
0x1800cc42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc430  mov     edi, eax
0x1800cc432  xorps   xmm0, xmm0
0x1800cc435  movups  [rbp+57h+var_80], xmm0
0x1800cc439  movups  [rbp+57h+var_70], xmm0
0x1800cc43d  movdqa  [rbp+57h+var_60], xmm0
0x1800cc442  mov     [rbp+57h+var_50], r15
0x1800cc446  mov     [rbp+57h+var_48], r15d
0x1800cc44a  mov     [rbp+57h+var_40], r15
0x1800cc44e  mov     [rbp+57h+var_38], r15b
0x1800cc452  test    eax, eax
0x1800cc454  jns     short loc_1800CC481
0x1800cc456  mov     rcx, [rbp+57h+var_C8]
0x1800cc45a  test    rcx, rcx
0x1800cc45d  jz      short loc_1800CC481
0x1800cc45f  call    cs:__imp_SetRestrictedErrorInfo
0x1800cc465  mov     rcx, [rbp+5Fh]; this
0x1800cc469  test    eax, eax
0x1800cc46b  jns     short loc_1800CC481
0x1800cc46d  mov     r9d, eax; char *
0x1800cc470  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cc477  mov     edx, 4Fh ; 'O'; void *
0x1800cc47c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cc481  mov     rcx, [rbp+5Fh]; this
0x1800cc485  test    edi, edi
0x1800cc487  jns     short loc_1800CC49E
0x1800cc489  mov     r9d, edi; char *
0x1800cc48c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cc493  mov     edx, 51h ; 'Q'; void *
0x1800cc498  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cc49e  lea     rdx, [rbp+57h+var_80]
0x1800cc4a2  mov     rcx, rbx
0x1800cc4a5  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800cc4aa  nop
0x1800cc4ab  lea     rcx, [rbp+57h+var_80]; this
0x1800cc4af  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800cc4b4  nop
0x1800cc4b5  lea     rcx, [rbp+57h+var_C8]
0x1800cc4b9  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800cc4be  nop
0x1800cc4bf  lea     rcx, [rbp+57h+var_C0]
0x1800cc4c3  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800cc4c8  mov     rax, rbx
0x1800cc4cb  add     rsp, 0E8h
0x1800cc4d2  pop     r15
0x1800cc4d4  pop     r14
0x1800cc4d6  pop     rdi
0x1800cc4d7  pop     rsi
0x1800cc4d8  pop     rbx
0x1800cc4d9  pop     rbp
0x1800cc4da  retn
```
