# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_4df5b936796f79fe316301562e7cc396_>(_lambda_4df5b936796f79fe316301562e7cc396_ &&)'::`2'::NopActivity const,_lambda_4df5b936796f79fe316301562e7cc396_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_4df5b936796f79fe316301562e7cc396_>(_lambda_4df5b936796f79fe316301562e7cc396_ &&)'::`2'::NopActivity const &,_lambda_4df5b936796f79fe316301562e7cc396_ &)

- ea: `0x18017e6a4`
- end: `0x18017e8bb`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_4df5b936796f79fe316301562e7cc396_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_4df5b936796f79fe316301562e7cc396_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_4df5b936796f79fe316301562e7cc396_@@@0@QEBAX$$QEAV_lambda_4df5b936796f79fe316301562e7cc396_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18017fcbc`

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
- `0x18017e6a4`
- `0x1801812cc`
- `0x180181b64`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18017e76b`
- `SHCORE!SHTaskPoolQueueTask` at `0x18017e76b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017e751`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017e751`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017e6da`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017e6da`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017e83f`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017e83f`

## string_xrefs

- `0x18017e6ef`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017e793`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017e850`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017e86c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_4df5b936796f79fe316301562e7cc396_>'::`2'::NopActivity const,AX$$QEAV_lambda_4df5b936796f79fe316301562e7cc396_ const * const>(
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
      _lambda_4df5b936796f79fe316301562e7cc396_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_e3c425894603b21cc9e09cd05ef99187_ &>,_lambda_e3c425894603b21cc9e09cd05ef99187_ &>(
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
0x18017e6a4  push    rbp
0x18017e6a6  push    rbx
0x18017e6a7  push    rsi
0x18017e6a8  push    rdi
0x18017e6a9  push    r14
0x18017e6ab  push    r15
0x18017e6ad  lea     rbp, [rsp-2Fh]
0x18017e6b2  sub     rsp, 0E8h
0x18017e6b9  mov     rdi, r9
0x18017e6bc  mov     rsi, r8
0x18017e6bf  mov     rbx, rdx
0x18017e6c2  mov     r14, rcx
0x18017e6c5  xor     r15d, r15d
0x18017e6c8  mov     [rsp+110h+pAptType], r15d
0x18017e6cd  mov     [rbp+57h+pAptQualifier], r15d
0x18017e6d1  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x18017e6d5  lea     rcx, [rsp+110h+pAptType]; pAptType
0x18017e6da  call    cs:__imp_CoGetApartmentType
0x18017e6e0  mov     rcx, [rbp+5Fh]; this
0x18017e6e4  test    eax, eax
0x18017e6e6  jns     loc_18017E7A5
0x18017e6ec  mov     r9d, eax; char *
0x18017e6ef  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e6f6  lea     edx, [r15+29h]; void *
0x18017e6fa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017e6ff  lea     rcx, [rbp+57h+var_C0]
0x18017e703  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x18017e708  nop
0x18017e709  mov     [rbp+57h+var_C8], r15
0x18017e70d  mov     [rbp+57h+var_B0], r14
0x18017e711  mov     [rbp+57h+var_A8], rsi
0x18017e715  mov     [rbp+57h+var_A0], rdi
0x18017e719  lea     rax, [rbp+57h+var_C8]
0x18017e71d  mov     [rbp+57h+var_98], rax
0x18017e721  lea     rax, [rbp+57h+var_C0]
0x18017e725  mov     [rbp+57h+var_90], rax
0x18017e729  lea     rdx, [rbp+57h+var_B0]
0x18017e72d  lea     rcx, [rsp+110h+var_D8]
0x18017e732  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_e3c425894603b21cc9e09cd05ef99187_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_e3c425894603b21cc9e09cd05ef99187_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_e3c425894603b21cc9e09cd05ef99187_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_e3c425894603b21cc9e09cd05ef99187_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_e3c425894603b21cc9e09cd05ef99187_ &>,_lambda_e3c425894603b21cc9e09cd05ef99187_ &>(_lambda_e3c425894603b21cc9e09cd05ef99187_ &)
0x18017e737  mov     rdi, [rax]
0x18017e73a  mov     [rax], r15
0x18017e73d  mov     rcx, [rsp+110h+var_D8]
0x18017e742  test    rcx, rcx
0x18017e745  jz      short loc_18017E751
0x18017e747  mov     [rsp+110h+var_D8], r15
0x18017e74c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18017e751  call    cs:__imp_GetCurrentThreadId
0x18017e757  mov     [rsp+110h+var_E8], r15
0x18017e75c  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x18017e761  xor     r9d, r9d
0x18017e764  mov     r8d, eax
0x18017e767  xor     edx, edx
0x18017e769  xor     ecx, ecx
0x18017e76b  call    cs:__imp_SHTaskPoolQueueTask
0x18017e771  mov     esi, eax
0x18017e773  test    rdi, rdi
0x18017e776  jz      short loc_18017E788
0x18017e778  mov     rdx, [rdi]
0x18017e77b  mov     rcx, rdi
0x18017e77e  mov     rax, [rdx+10h]
0x18017e782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e787  nop
0x18017e788  mov     rcx, [rbp+5Fh]; this
0x18017e78c  test    esi, esi
0x18017e78e  jns     short loc_18017E7FE
0x18017e790  mov     r9d, esi; char *
0x18017e793  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e79a  mov     edx, 46h ; 'F'; void *
0x18017e79f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e7a5  mov     eax, [rsp+110h+pAptType]
0x18017e7a9  test    eax, eax
0x18017e7ab  jz      loc_18017E6FF
0x18017e7b1  cmp     eax, 3
0x18017e7b4  jz      loc_18017E6FF
0x18017e7ba  lea     rcx, [rsp+110h+var_D8]
0x18017e7bf  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x18017e7c4  nop
0x18017e7c5  mov     rcx, rdi
0x18017e7c8  call    ??R_lambda_4df5b936796f79fe316301562e7cc396_@@QEBA@XZ; _lambda_4df5b936796f79fe316301562e7cc396_::operator()(void)
0x18017e7cd  xorps   xmm0, xmm0
0x18017e7d0  movups  xmmword ptr [rbx], xmm0
0x18017e7d3  movups  xmmword ptr [rbx+10h], xmm0
0x18017e7d7  mov     [rbx+20h], r15
0x18017e7db  mov     [rbx+28h], r15
0x18017e7df  mov     [rbx+30h], r15
0x18017e7e3  mov     [rbx+38h], r15d
0x18017e7e7  mov     [rbx+40h], r15
0x18017e7eb  mov     [rbx+48h], r15b
0x18017e7ef  lea     rcx, [rsp+110h+var_D8]
0x18017e7f4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18017e7f9  jmp     loc_18017E8A8
0x18017e7fe  mov     rcx, [rbp+57h+var_C0]
0x18017e802  mov     rax, [rcx]
0x18017e805  xor     edx, edx
0x18017e807  mov     rax, [rax+10h]
0x18017e80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e810  mov     edi, eax
0x18017e812  xorps   xmm0, xmm0
0x18017e815  movups  [rbp+57h+var_80], xmm0
0x18017e819  movups  [rbp+57h+var_70], xmm0
0x18017e81d  movdqa  [rbp+57h+var_60], xmm0
0x18017e822  mov     [rbp+57h+var_50], r15
0x18017e826  mov     [rbp+57h+var_48], r15d
0x18017e82a  mov     [rbp+57h+var_40], r15
0x18017e82e  mov     [rbp+57h+var_38], r15b
0x18017e832  test    eax, eax
0x18017e834  jns     short loc_18017E861
0x18017e836  mov     rcx, [rbp+57h+var_C8]
0x18017e83a  test    rcx, rcx
0x18017e83d  jz      short loc_18017E861
0x18017e83f  call    cs:__imp_SetRestrictedErrorInfo
0x18017e845  mov     rcx, [rbp+5Fh]; this
0x18017e849  test    eax, eax
0x18017e84b  jns     short loc_18017E861
0x18017e84d  mov     r9d, eax; char *
0x18017e850  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e857  mov     edx, 4Fh ; 'O'; void *
0x18017e85c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017e861  mov     rcx, [rbp+5Fh]; this
0x18017e865  test    edi, edi
0x18017e867  jns     short loc_18017E87E
0x18017e869  mov     r9d, edi; char *
0x18017e86c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e873  mov     edx, 51h ; 'Q'; void *
0x18017e878  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e87e  lea     rdx, [rbp+57h+var_80]
0x18017e882  mov     rcx, rbx
0x18017e885  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x18017e88a  nop
0x18017e88b  lea     rcx, [rbp+57h+var_80]; this
0x18017e88f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18017e894  nop
0x18017e895  lea     rcx, [rbp+57h+var_C8]
0x18017e899  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18017e89e  nop
0x18017e89f  lea     rcx, [rbp+57h+var_C0]
0x18017e8a3  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x18017e8a8  mov     rax, rbx
0x18017e8ab  add     rsp, 0E8h
0x18017e8b2  pop     r15
0x18017e8b4  pop     r14
0x18017e8b6  pop     rdi
0x18017e8b7  pop     rsi
0x18017e8b8  pop     rbx
0x18017e8b9  pop     rbp
0x18017e8ba  retn
```
