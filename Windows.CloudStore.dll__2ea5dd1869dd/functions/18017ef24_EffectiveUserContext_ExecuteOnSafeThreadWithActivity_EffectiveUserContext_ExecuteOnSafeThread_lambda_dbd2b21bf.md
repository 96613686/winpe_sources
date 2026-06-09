# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_dbd2b21bf619229f06664256b692357f_>(_lambda_dbd2b21bf619229f06664256b692357f_ &&)'::`2'::NopActivity const,_lambda_dbd2b21bf619229f06664256b692357f_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_dbd2b21bf619229f06664256b692357f_>(_lambda_dbd2b21bf619229f06664256b692357f_ &&)'::`2'::NopActivity const &,_lambda_dbd2b21bf619229f06664256b692357f_ &)

- ea: `0x18017ef24`
- end: `0x18017f13b`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_dbd2b21bf619229f06664256b692357f_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_dbd2b21bf619229f06664256b692357f_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_dbd2b21bf619229f06664256b692357f_@@@0@QEBAX$$QEAV_lambda_dbd2b21bf619229f06664256b692357f_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801800c8`

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
- `0x18017ef24`
- `0x18018088c`
- `0x1801823ac`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18017efeb`
- `SHCORE!SHTaskPoolQueueTask` at `0x18017efeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017efd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017efd1`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017ef5a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017ef5a`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017f0bf`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017f0bf`

## string_xrefs

- `0x18017ef6f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017f013`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017f0d0`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017f0ec`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_dbd2b21bf619229f06664256b692357f_>'::`2'::NopActivity const,AX$$QEAV_lambda_dbd2b21bf619229f06664256b692357f_ const * const>(
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
      _lambda_dbd2b21bf619229f06664256b692357f_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_414debb5bad91e38fa8a0484d8dc226e_ &>,_lambda_414debb5bad91e38fa8a0484d8dc226e_ &>(
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
0x18017ef24  push    rbp
0x18017ef26  push    rbx
0x18017ef27  push    rsi
0x18017ef28  push    rdi
0x18017ef29  push    r14
0x18017ef2b  push    r15
0x18017ef2d  lea     rbp, [rsp-2Fh]
0x18017ef32  sub     rsp, 0E8h
0x18017ef39  mov     rdi, r9
0x18017ef3c  mov     rsi, r8
0x18017ef3f  mov     rbx, rdx
0x18017ef42  mov     r14, rcx
0x18017ef45  xor     r15d, r15d
0x18017ef48  mov     [rsp+110h+pAptType], r15d
0x18017ef4d  mov     [rbp+57h+pAptQualifier], r15d
0x18017ef51  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x18017ef55  lea     rcx, [rsp+110h+pAptType]; pAptType
0x18017ef5a  call    cs:__imp_CoGetApartmentType
0x18017ef60  mov     rcx, [rbp+5Fh]; this
0x18017ef64  test    eax, eax
0x18017ef66  jns     loc_18017F025
0x18017ef6c  mov     r9d, eax; char *
0x18017ef6f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017ef76  lea     edx, [r15+29h]; void *
0x18017ef7a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017ef7f  lea     rcx, [rbp+57h+var_C0]
0x18017ef83  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x18017ef88  nop
0x18017ef89  mov     [rbp+57h+var_C8], r15
0x18017ef8d  mov     [rbp+57h+var_B0], r14
0x18017ef91  mov     [rbp+57h+var_A8], rsi
0x18017ef95  mov     [rbp+57h+var_A0], rdi
0x18017ef99  lea     rax, [rbp+57h+var_C8]
0x18017ef9d  mov     [rbp+57h+var_98], rax
0x18017efa1  lea     rax, [rbp+57h+var_C0]
0x18017efa5  mov     [rbp+57h+var_90], rax
0x18017efa9  lea     rdx, [rbp+57h+var_B0]
0x18017efad  lea     rcx, [rsp+110h+var_D8]
0x18017efb2  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_414debb5bad91e38fa8a0484d8dc226e_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_414debb5bad91e38fa8a0484d8dc226e_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_414debb5bad91e38fa8a0484d8dc226e_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_414debb5bad91e38fa8a0484d8dc226e_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_414debb5bad91e38fa8a0484d8dc226e_ &>,_lambda_414debb5bad91e38fa8a0484d8dc226e_ &>(_lambda_414debb5bad91e38fa8a0484d8dc226e_ &)
0x18017efb7  mov     rdi, [rax]
0x18017efba  mov     [rax], r15
0x18017efbd  mov     rcx, [rsp+110h+var_D8]
0x18017efc2  test    rcx, rcx
0x18017efc5  jz      short loc_18017EFD1
0x18017efc7  mov     [rsp+110h+var_D8], r15
0x18017efcc  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18017efd1  call    cs:__imp_GetCurrentThreadId
0x18017efd7  mov     [rsp+110h+var_E8], r15
0x18017efdc  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x18017efe1  xor     r9d, r9d
0x18017efe4  mov     r8d, eax
0x18017efe7  xor     edx, edx
0x18017efe9  xor     ecx, ecx
0x18017efeb  call    cs:__imp_SHTaskPoolQueueTask
0x18017eff1  mov     esi, eax
0x18017eff3  test    rdi, rdi
0x18017eff6  jz      short loc_18017F008
0x18017eff8  mov     rdx, [rdi]
0x18017effb  mov     rcx, rdi
0x18017effe  mov     rax, [rdx+10h]
0x18017f002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017f007  nop
0x18017f008  mov     rcx, [rbp+5Fh]; this
0x18017f00c  test    esi, esi
0x18017f00e  jns     short loc_18017F07E
0x18017f010  mov     r9d, esi; char *
0x18017f013  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017f01a  mov     edx, 46h ; 'F'; void *
0x18017f01f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017f025  mov     eax, [rsp+110h+pAptType]
0x18017f029  test    eax, eax
0x18017f02b  jz      loc_18017EF7F
0x18017f031  cmp     eax, 3
0x18017f034  jz      loc_18017EF7F
0x18017f03a  lea     rcx, [rsp+110h+var_D8]
0x18017f03f  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x18017f044  nop
0x18017f045  mov     rcx, rdi
0x18017f048  call    ??R_lambda_dbd2b21bf619229f06664256b692357f_@@QEBA@XZ; _lambda_dbd2b21bf619229f06664256b692357f_::operator()(void)
0x18017f04d  xorps   xmm0, xmm0
0x18017f050  movups  xmmword ptr [rbx], xmm0
0x18017f053  movups  xmmword ptr [rbx+10h], xmm0
0x18017f057  mov     [rbx+20h], r15
0x18017f05b  mov     [rbx+28h], r15
0x18017f05f  mov     [rbx+30h], r15
0x18017f063  mov     [rbx+38h], r15d
0x18017f067  mov     [rbx+40h], r15
0x18017f06b  mov     [rbx+48h], r15b
0x18017f06f  lea     rcx, [rsp+110h+var_D8]
0x18017f074  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18017f079  jmp     loc_18017F128
0x18017f07e  mov     rcx, [rbp+57h+var_C0]
0x18017f082  mov     rax, [rcx]
0x18017f085  xor     edx, edx
0x18017f087  mov     rax, [rax+10h]
0x18017f08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017f090  mov     edi, eax
0x18017f092  xorps   xmm0, xmm0
0x18017f095  movups  [rbp+57h+var_80], xmm0
0x18017f099  movups  [rbp+57h+var_70], xmm0
0x18017f09d  movdqa  [rbp+57h+var_60], xmm0
0x18017f0a2  mov     [rbp+57h+var_50], r15
0x18017f0a6  mov     [rbp+57h+var_48], r15d
0x18017f0aa  mov     [rbp+57h+var_40], r15
0x18017f0ae  mov     [rbp+57h+var_38], r15b
0x18017f0b2  test    eax, eax
0x18017f0b4  jns     short loc_18017F0E1
0x18017f0b6  mov     rcx, [rbp+57h+var_C8]
0x18017f0ba  test    rcx, rcx
0x18017f0bd  jz      short loc_18017F0E1
0x18017f0bf  call    cs:__imp_SetRestrictedErrorInfo
0x18017f0c5  mov     rcx, [rbp+5Fh]; this
0x18017f0c9  test    eax, eax
0x18017f0cb  jns     short loc_18017F0E1
0x18017f0cd  mov     r9d, eax; char *
0x18017f0d0  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017f0d7  mov     edx, 4Fh ; 'O'; void *
0x18017f0dc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017f0e1  mov     rcx, [rbp+5Fh]; this
0x18017f0e5  test    edi, edi
0x18017f0e7  jns     short loc_18017F0FE
0x18017f0e9  mov     r9d, edi; char *
0x18017f0ec  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017f0f3  mov     edx, 51h ; 'Q'; void *
0x18017f0f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017f0fe  lea     rdx, [rbp+57h+var_80]
0x18017f102  mov     rcx, rbx
0x18017f105  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x18017f10a  nop
0x18017f10b  lea     rcx, [rbp+57h+var_80]; this
0x18017f10f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18017f114  nop
0x18017f115  lea     rcx, [rbp+57h+var_C8]
0x18017f119  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18017f11e  nop
0x18017f11f  lea     rcx, [rbp+57h+var_C0]
0x18017f123  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x18017f128  mov     rax, rbx
0x18017f12b  add     rsp, 0E8h
0x18017f132  pop     r15
0x18017f134  pop     r14
0x18017f136  pop     rdi
0x18017f137  pop     rsi
0x18017f138  pop     rbx
0x18017f139  pop     rbp
0x18017f13a  retn
```
