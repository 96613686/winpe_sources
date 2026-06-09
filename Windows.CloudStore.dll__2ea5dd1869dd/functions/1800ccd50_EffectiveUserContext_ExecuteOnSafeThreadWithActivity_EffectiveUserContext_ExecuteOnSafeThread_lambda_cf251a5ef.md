# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_cf251a5ef29e080451e17a9a89954c32_>(_lambda_cf251a5ef29e080451e17a9a89954c32_ &&)'::`2'::NopActivity const,_lambda_cf251a5ef29e080451e17a9a89954c32_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_cf251a5ef29e080451e17a9a89954c32_>(_lambda_cf251a5ef29e080451e17a9a89954c32_ &&)'::`2'::NopActivity const &,_lambda_cf251a5ef29e080451e17a9a89954c32_ &)

- ea: `0x1800ccd50`
- end: `0x1800ccf67`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_cf251a5ef29e080451e17a9a89954c32_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_cf251a5ef29e080451e17a9a89954c32_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_cf251a5ef29e080451e17a9a89954c32_@@@0@QEBAX$$QEAV_lambda_cf251a5ef29e080451e17a9a89954c32_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18017ff0c`

## callees

- `0x18000dfe4`
- `0x180010688`
- `0x180016cf4`
- `0x180035b7c`
- `0x180038db8`
- `0x18005dde0`
- `0x180061e60`
- `0x180064888`
- `0x1800ccd50`
- `0x1800ce314`
- `0x1800e93e0`
- `0x180180f98`
- `0x180182194`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800cce17`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800cce17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ccdfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ccdfd`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ccd86`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ccd86`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cceeb`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cceeb`

## string_xrefs

- `0x1800ccd9b`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cce3f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800ccefc`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800ccf18`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_cf251a5ef29e080451e17a9a89954c32_>'::`2'::NopActivity const,AX$$QEAV_lambda_cf251a5ef29e080451e17a9a89954c32_ const * const>(
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
      _lambda_cf251a5ef29e080451e17a9a89954c32_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_852e8f1f589d04139e95dd01ee3607ab_ &>,_lambda_852e8f1f589d04139e95dd01ee3607ab_ &>(
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
0x1800ccd50  push    rbp
0x1800ccd52  push    rbx
0x1800ccd53  push    rsi
0x1800ccd54  push    rdi
0x1800ccd55  push    r14
0x1800ccd57  push    r15
0x1800ccd59  lea     rbp, [rsp-2Fh]
0x1800ccd5e  sub     rsp, 0E8h
0x1800ccd65  mov     rdi, r9
0x1800ccd68  mov     rsi, r8
0x1800ccd6b  mov     rbx, rdx
0x1800ccd6e  mov     r14, rcx
0x1800ccd71  xor     r15d, r15d
0x1800ccd74  mov     [rsp+110h+pAptType], r15d
0x1800ccd79  mov     [rbp+57h+pAptQualifier], r15d
0x1800ccd7d  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800ccd81  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800ccd86  call    cs:__imp_CoGetApartmentType
0x1800ccd8c  mov     rcx, [rbp+5Fh]; this
0x1800ccd90  test    eax, eax
0x1800ccd92  jns     loc_1800CCE51
0x1800ccd98  mov     r9d, eax; char *
0x1800ccd9b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ccda2  lea     edx, [r15+29h]; void *
0x1800ccda6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ccdab  lea     rcx, [rbp+57h+var_C0]
0x1800ccdaf  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800ccdb4  nop
0x1800ccdb5  mov     [rbp+57h+var_C8], r15
0x1800ccdb9  mov     [rbp+57h+var_B0], r14
0x1800ccdbd  mov     [rbp+57h+var_A8], rsi
0x1800ccdc1  mov     [rbp+57h+var_A0], rdi
0x1800ccdc5  lea     rax, [rbp+57h+var_C8]
0x1800ccdc9  mov     [rbp+57h+var_98], rax
0x1800ccdcd  lea     rax, [rbp+57h+var_C0]
0x1800ccdd1  mov     [rbp+57h+var_90], rax
0x1800ccdd5  lea     rdx, [rbp+57h+var_B0]
0x1800ccdd9  lea     rcx, [rsp+110h+var_D8]
0x1800ccdde  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_852e8f1f589d04139e95dd01ee3607ab_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_852e8f1f589d04139e95dd01ee3607ab_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_852e8f1f589d04139e95dd01ee3607ab_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_852e8f1f589d04139e95dd01ee3607ab_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_852e8f1f589d04139e95dd01ee3607ab_ &>,_lambda_852e8f1f589d04139e95dd01ee3607ab_ &>(_lambda_852e8f1f589d04139e95dd01ee3607ab_ &)
0x1800ccde3  mov     rdi, [rax]
0x1800ccde6  mov     [rax], r15
0x1800ccde9  mov     rcx, [rsp+110h+var_D8]
0x1800ccdee  test    rcx, rcx
0x1800ccdf1  jz      short loc_1800CCDFD
0x1800ccdf3  mov     [rsp+110h+var_D8], r15
0x1800ccdf8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800ccdfd  call    cs:__imp_GetCurrentThreadId
0x1800cce03  mov     [rsp+110h+var_E8], r15
0x1800cce08  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800cce0d  xor     r9d, r9d
0x1800cce10  mov     r8d, eax
0x1800cce13  xor     edx, edx
0x1800cce15  xor     ecx, ecx
0x1800cce17  call    cs:__imp_SHTaskPoolQueueTask
0x1800cce1d  mov     esi, eax
0x1800cce1f  test    rdi, rdi
0x1800cce22  jz      short loc_1800CCE34
0x1800cce24  mov     rdx, [rdi]
0x1800cce27  mov     rcx, rdi
0x1800cce2a  mov     rax, [rdx+10h]
0x1800cce2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cce33  nop
0x1800cce34  mov     rcx, [rbp+5Fh]; this
0x1800cce38  test    esi, esi
0x1800cce3a  jns     short loc_1800CCEAA
0x1800cce3c  mov     r9d, esi; char *
0x1800cce3f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cce46  mov     edx, 46h ; 'F'; void *
0x1800cce4b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cce51  mov     eax, [rsp+110h+pAptType]
0x1800cce55  test    eax, eax
0x1800cce57  jz      loc_1800CCDAB
0x1800cce5d  cmp     eax, 3
0x1800cce60  jz      loc_1800CCDAB
0x1800cce66  lea     rcx, [rsp+110h+var_D8]
0x1800cce6b  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cce70  nop
0x1800cce71  mov     rcx, rdi
0x1800cce74  call    ??R_lambda_cf251a5ef29e080451e17a9a89954c32_@@QEBA@XZ; _lambda_cf251a5ef29e080451e17a9a89954c32_::operator()(void)
0x1800cce79  xorps   xmm0, xmm0
0x1800cce7c  movups  xmmword ptr [rbx], xmm0
0x1800cce7f  movups  xmmword ptr [rbx+10h], xmm0
0x1800cce83  mov     [rbx+20h], r15
0x1800cce87  mov     [rbx+28h], r15
0x1800cce8b  mov     [rbx+30h], r15
0x1800cce8f  mov     [rbx+38h], r15d
0x1800cce93  mov     [rbx+40h], r15
0x1800cce97  mov     [rbx+48h], r15b
0x1800cce9b  lea     rcx, [rsp+110h+var_D8]
0x1800ccea0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800ccea5  jmp     loc_1800CCF54
0x1800cceaa  mov     rcx, [rbp+57h+var_C0]
0x1800cceae  mov     rax, [rcx]
0x1800cceb1  xor     edx, edx
0x1800cceb3  mov     rax, [rax+10h]
0x1800cceb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ccebc  mov     edi, eax
0x1800ccebe  xorps   xmm0, xmm0
0x1800ccec1  movups  [rbp+57h+var_80], xmm0
0x1800ccec5  movups  [rbp+57h+var_70], xmm0
0x1800ccec9  movdqa  [rbp+57h+var_60], xmm0
0x1800ccece  mov     [rbp+57h+var_50], r15
0x1800cced2  mov     [rbp+57h+var_48], r15d
0x1800cced6  mov     [rbp+57h+var_40], r15
0x1800cceda  mov     [rbp+57h+var_38], r15b
0x1800ccede  test    eax, eax
0x1800ccee0  jns     short loc_1800CCF0D
0x1800ccee2  mov     rcx, [rbp+57h+var_C8]
0x1800ccee6  test    rcx, rcx
0x1800ccee9  jz      short loc_1800CCF0D
0x1800cceeb  call    cs:__imp_SetRestrictedErrorInfo
0x1800ccef1  mov     rcx, [rbp+5Fh]; this
0x1800ccef5  test    eax, eax
0x1800ccef7  jns     short loc_1800CCF0D
0x1800ccef9  mov     r9d, eax; char *
0x1800ccefc  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ccf03  mov     edx, 4Fh ; 'O'; void *
0x1800ccf08  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ccf0d  mov     rcx, [rbp+5Fh]; this
0x1800ccf11  test    edi, edi
0x1800ccf13  jns     short loc_1800CCF2A
0x1800ccf15  mov     r9d, edi; char *
0x1800ccf18  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ccf1f  mov     edx, 51h ; 'Q'; void *
0x1800ccf24  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ccf2a  lea     rdx, [rbp+57h+var_80]
0x1800ccf2e  mov     rcx, rbx
0x1800ccf31  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800ccf36  nop
0x1800ccf37  lea     rcx, [rbp+57h+var_80]; this
0x1800ccf3b  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800ccf40  nop
0x1800ccf41  lea     rcx, [rbp+57h+var_C8]
0x1800ccf45  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800ccf4a  nop
0x1800ccf4b  lea     rcx, [rbp+57h+var_C0]
0x1800ccf4f  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800ccf54  mov     rax, rbx
0x1800ccf57  add     rsp, 0E8h
0x1800ccf5e  pop     r15
0x1800ccf60  pop     r14
0x1800ccf62  pop     rdi
0x1800ccf63  pop     rsi
0x1800ccf64  pop     rbx
0x1800ccf65  pop     rbp
0x1800ccf66  retn
```
