# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_cc139dda8f3a65b5c184000ce26bf861_>(_lambda_cc139dda8f3a65b5c184000ce26bf861_ &&)'::`2'::NopActivity const,_lambda_cc139dda8f3a65b5c184000ce26bf861_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_cc139dda8f3a65b5c184000ce26bf861_>(_lambda_cc139dda8f3a65b5c184000ce26bf861_ &&)'::`2'::NopActivity const &,_lambda_cc139dda8f3a65b5c184000ce26bf861_ &)

- ea: `0x1800cd190`
- end: `0x1800cd3a7`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_cc139dda8f3a65b5c184000ce26bf861_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_cc139dda8f3a65b5c184000ce26bf861_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_cc139dda8f3a65b5c184000ce26bf861_@@@0@QEBAX$$QEAV_lambda_cc139dda8f3a65b5c184000ce26bf861_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18017fc28`

## callees

- `0x18000dfe4`
- `0x180010688`
- `0x180016cf4`
- `0x180035b7c`
- `0x180038db8`
- `0x18005dde0`
- `0x180061e60`
- `0x180064888`
- `0x1800cd190`
- `0x1800ce314`
- `0x1800e93e0`
- `0x180180d08`
- `0x1801820f8`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800cd257`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800cd257`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd23d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd23d`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cd1c6`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cd1c6`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cd32b`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cd32b`

## string_xrefs

- `0x1800cd1db`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cd27f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cd33c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cd358`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_cc139dda8f3a65b5c184000ce26bf861_>'::`2'::NopActivity const,AX$$QEAV_lambda_cc139dda8f3a65b5c184000ce26bf861_ const * const>(
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
      _lambda_cc139dda8f3a65b5c184000ce26bf861_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_6512956e71c1df8f2be310bb30fb709c_ &>,_lambda_6512956e71c1df8f2be310bb30fb709c_ &>(
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
0x1800cd190  push    rbp
0x1800cd192  push    rbx
0x1800cd193  push    rsi
0x1800cd194  push    rdi
0x1800cd195  push    r14
0x1800cd197  push    r15
0x1800cd199  lea     rbp, [rsp-2Fh]
0x1800cd19e  sub     rsp, 0E8h
0x1800cd1a5  mov     rdi, r9
0x1800cd1a8  mov     rsi, r8
0x1800cd1ab  mov     rbx, rdx
0x1800cd1ae  mov     r14, rcx
0x1800cd1b1  xor     r15d, r15d
0x1800cd1b4  mov     [rsp+110h+pAptType], r15d
0x1800cd1b9  mov     [rbp+57h+pAptQualifier], r15d
0x1800cd1bd  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800cd1c1  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800cd1c6  call    cs:__imp_CoGetApartmentType
0x1800cd1cc  mov     rcx, [rbp+5Fh]; this
0x1800cd1d0  test    eax, eax
0x1800cd1d2  jns     loc_1800CD291
0x1800cd1d8  mov     r9d, eax; char *
0x1800cd1db  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd1e2  lea     edx, [r15+29h]; void *
0x1800cd1e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cd1eb  lea     rcx, [rbp+57h+var_C0]
0x1800cd1ef  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800cd1f4  nop
0x1800cd1f5  mov     [rbp+57h+var_C8], r15
0x1800cd1f9  mov     [rbp+57h+var_B0], r14
0x1800cd1fd  mov     [rbp+57h+var_A8], rsi
0x1800cd201  mov     [rbp+57h+var_A0], rdi
0x1800cd205  lea     rax, [rbp+57h+var_C8]
0x1800cd209  mov     [rbp+57h+var_98], rax
0x1800cd20d  lea     rax, [rbp+57h+var_C0]
0x1800cd211  mov     [rbp+57h+var_90], rax
0x1800cd215  lea     rdx, [rbp+57h+var_B0]
0x1800cd219  lea     rcx, [rsp+110h+var_D8]
0x1800cd21e  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_6512956e71c1df8f2be310bb30fb709c_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_6512956e71c1df8f2be310bb30fb709c_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_6512956e71c1df8f2be310bb30fb709c_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_6512956e71c1df8f2be310bb30fb709c_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_6512956e71c1df8f2be310bb30fb709c_ &>,_lambda_6512956e71c1df8f2be310bb30fb709c_ &>(_lambda_6512956e71c1df8f2be310bb30fb709c_ &)
0x1800cd223  mov     rdi, [rax]
0x1800cd226  mov     [rax], r15
0x1800cd229  mov     rcx, [rsp+110h+var_D8]
0x1800cd22e  test    rcx, rcx
0x1800cd231  jz      short loc_1800CD23D
0x1800cd233  mov     [rsp+110h+var_D8], r15
0x1800cd238  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800cd23d  call    cs:__imp_GetCurrentThreadId
0x1800cd243  mov     [rsp+110h+var_E8], r15
0x1800cd248  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800cd24d  xor     r9d, r9d
0x1800cd250  mov     r8d, eax
0x1800cd253  xor     edx, edx
0x1800cd255  xor     ecx, ecx
0x1800cd257  call    cs:__imp_SHTaskPoolQueueTask
0x1800cd25d  mov     esi, eax
0x1800cd25f  test    rdi, rdi
0x1800cd262  jz      short loc_1800CD274
0x1800cd264  mov     rdx, [rdi]
0x1800cd267  mov     rcx, rdi
0x1800cd26a  mov     rax, [rdx+10h]
0x1800cd26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd273  nop
0x1800cd274  mov     rcx, [rbp+5Fh]; this
0x1800cd278  test    esi, esi
0x1800cd27a  jns     short loc_1800CD2EA
0x1800cd27c  mov     r9d, esi; char *
0x1800cd27f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd286  mov     edx, 46h ; 'F'; void *
0x1800cd28b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cd291  mov     eax, [rsp+110h+pAptType]
0x1800cd295  test    eax, eax
0x1800cd297  jz      loc_1800CD1EB
0x1800cd29d  cmp     eax, 3
0x1800cd2a0  jz      loc_1800CD1EB
0x1800cd2a6  lea     rcx, [rsp+110h+var_D8]
0x1800cd2ab  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cd2b0  nop
0x1800cd2b1  mov     rcx, rdi
0x1800cd2b4  call    ??R_lambda_cc139dda8f3a65b5c184000ce26bf861_@@QEBA@XZ; _lambda_cc139dda8f3a65b5c184000ce26bf861_::operator()(void)
0x1800cd2b9  xorps   xmm0, xmm0
0x1800cd2bc  movups  xmmword ptr [rbx], xmm0
0x1800cd2bf  movups  xmmword ptr [rbx+10h], xmm0
0x1800cd2c3  mov     [rbx+20h], r15
0x1800cd2c7  mov     [rbx+28h], r15
0x1800cd2cb  mov     [rbx+30h], r15
0x1800cd2cf  mov     [rbx+38h], r15d
0x1800cd2d3  mov     [rbx+40h], r15
0x1800cd2d7  mov     [rbx+48h], r15b
0x1800cd2db  lea     rcx, [rsp+110h+var_D8]
0x1800cd2e0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800cd2e5  jmp     loc_1800CD394
0x1800cd2ea  mov     rcx, [rbp+57h+var_C0]
0x1800cd2ee  mov     rax, [rcx]
0x1800cd2f1  xor     edx, edx
0x1800cd2f3  mov     rax, [rax+10h]
0x1800cd2f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd2fc  mov     edi, eax
0x1800cd2fe  xorps   xmm0, xmm0
0x1800cd301  movups  [rbp+57h+var_80], xmm0
0x1800cd305  movups  [rbp+57h+var_70], xmm0
0x1800cd309  movdqa  [rbp+57h+var_60], xmm0
0x1800cd30e  mov     [rbp+57h+var_50], r15
0x1800cd312  mov     [rbp+57h+var_48], r15d
0x1800cd316  mov     [rbp+57h+var_40], r15
0x1800cd31a  mov     [rbp+57h+var_38], r15b
0x1800cd31e  test    eax, eax
0x1800cd320  jns     short loc_1800CD34D
0x1800cd322  mov     rcx, [rbp+57h+var_C8]
0x1800cd326  test    rcx, rcx
0x1800cd329  jz      short loc_1800CD34D
0x1800cd32b  call    cs:__imp_SetRestrictedErrorInfo
0x1800cd331  mov     rcx, [rbp+5Fh]; this
0x1800cd335  test    eax, eax
0x1800cd337  jns     short loc_1800CD34D
0x1800cd339  mov     r9d, eax; char *
0x1800cd33c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd343  mov     edx, 4Fh ; 'O'; void *
0x1800cd348  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cd34d  mov     rcx, [rbp+5Fh]; this
0x1800cd351  test    edi, edi
0x1800cd353  jns     short loc_1800CD36A
0x1800cd355  mov     r9d, edi; char *
0x1800cd358  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd35f  mov     edx, 51h ; 'Q'; void *
0x1800cd364  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cd36a  lea     rdx, [rbp+57h+var_80]
0x1800cd36e  mov     rcx, rbx
0x1800cd371  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800cd376  nop
0x1800cd377  lea     rcx, [rbp+57h+var_80]; this
0x1800cd37b  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800cd380  nop
0x1800cd381  lea     rcx, [rbp+57h+var_C8]
0x1800cd385  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800cd38a  nop
0x1800cd38b  lea     rcx, [rbp+57h+var_C0]
0x1800cd38f  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800cd394  mov     rax, rbx
0x1800cd397  add     rsp, 0E8h
0x1800cd39e  pop     r15
0x1800cd3a0  pop     r14
0x1800cd3a2  pop     rdi
0x1800cd3a3  pop     rsi
0x1800cd3a4  pop     rbx
0x1800cd3a5  pop     rbp
0x1800cd3a6  retn
```
