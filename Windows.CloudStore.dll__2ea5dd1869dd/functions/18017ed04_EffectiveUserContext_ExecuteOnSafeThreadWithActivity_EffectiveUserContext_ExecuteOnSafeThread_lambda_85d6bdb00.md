# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_85d6bdb00f12d8be81804bcc9332f94d_>(_lambda_85d6bdb00f12d8be81804bcc9332f94d_ &&)'::`2'::NopActivity const,_lambda_85d6bdb00f12d8be81804bcc9332f94d_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_85d6bdb00f12d8be81804bcc9332f94d_>(_lambda_85d6bdb00f12d8be81804bcc9332f94d_ &&)'::`2'::NopActivity const &,_lambda_85d6bdb00f12d8be81804bcc9332f94d_ &)

- ea: `0x18017ed04`
- end: `0x18017ef1b`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_85d6bdb00f12d8be81804bcc9332f94d_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_85d6bdb00f12d8be81804bcc9332f94d_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_85d6bdb00f12d8be81804bcc9332f94d_@@@0@QEBAX$$QEAV_lambda_85d6bdb00f12d8be81804bcc9332f94d_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180180440`

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
- `0x18017ed04`
- `0x180180dac`
- `0x180181ee4`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18017edcb`
- `SHCORE!SHTaskPoolQueueTask` at `0x18017edcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017edb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017edb1`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017ed3a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017ed3a`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017ee9f`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017ee9f`

## string_xrefs

- `0x18017ed4f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017edf3`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017eeb0`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017eecc`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_85d6bdb00f12d8be81804bcc9332f94d_>'::`2'::NopActivity const,AX$$QEAV_lambda_85d6bdb00f12d8be81804bcc9332f94d_ const * const>(
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
      _lambda_85d6bdb00f12d8be81804bcc9332f94d_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_657090bf81b0b80dc02b59b75c730382_ &>,_lambda_657090bf81b0b80dc02b59b75c730382_ &>(
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
0x18017ed04  push    rbp
0x18017ed06  push    rbx
0x18017ed07  push    rsi
0x18017ed08  push    rdi
0x18017ed09  push    r14
0x18017ed0b  push    r15
0x18017ed0d  lea     rbp, [rsp-2Fh]
0x18017ed12  sub     rsp, 0E8h
0x18017ed19  mov     rdi, r9
0x18017ed1c  mov     rsi, r8
0x18017ed1f  mov     rbx, rdx
0x18017ed22  mov     r14, rcx
0x18017ed25  xor     r15d, r15d
0x18017ed28  mov     [rsp+110h+pAptType], r15d
0x18017ed2d  mov     [rbp+57h+pAptQualifier], r15d
0x18017ed31  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x18017ed35  lea     rcx, [rsp+110h+pAptType]; pAptType
0x18017ed3a  call    cs:__imp_CoGetApartmentType
0x18017ed40  mov     rcx, [rbp+5Fh]; this
0x18017ed44  test    eax, eax
0x18017ed46  jns     loc_18017EE05
0x18017ed4c  mov     r9d, eax; char *
0x18017ed4f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017ed56  lea     edx, [r15+29h]; void *
0x18017ed5a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017ed5f  lea     rcx, [rbp+57h+var_C0]
0x18017ed63  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x18017ed68  nop
0x18017ed69  mov     [rbp+57h+var_C8], r15
0x18017ed6d  mov     [rbp+57h+var_B0], r14
0x18017ed71  mov     [rbp+57h+var_A8], rsi
0x18017ed75  mov     [rbp+57h+var_A0], rdi
0x18017ed79  lea     rax, [rbp+57h+var_C8]
0x18017ed7d  mov     [rbp+57h+var_98], rax
0x18017ed81  lea     rax, [rbp+57h+var_C0]
0x18017ed85  mov     [rbp+57h+var_90], rax
0x18017ed89  lea     rdx, [rbp+57h+var_B0]
0x18017ed8d  lea     rcx, [rsp+110h+var_D8]
0x18017ed92  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_657090bf81b0b80dc02b59b75c730382_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_657090bf81b0b80dc02b59b75c730382_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_657090bf81b0b80dc02b59b75c730382_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_657090bf81b0b80dc02b59b75c730382_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_657090bf81b0b80dc02b59b75c730382_ &>,_lambda_657090bf81b0b80dc02b59b75c730382_ &>(_lambda_657090bf81b0b80dc02b59b75c730382_ &)
0x18017ed97  mov     rdi, [rax]
0x18017ed9a  mov     [rax], r15
0x18017ed9d  mov     rcx, [rsp+110h+var_D8]
0x18017eda2  test    rcx, rcx
0x18017eda5  jz      short loc_18017EDB1
0x18017eda7  mov     [rsp+110h+var_D8], r15
0x18017edac  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18017edb1  call    cs:__imp_GetCurrentThreadId
0x18017edb7  mov     [rsp+110h+var_E8], r15
0x18017edbc  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x18017edc1  xor     r9d, r9d
0x18017edc4  mov     r8d, eax
0x18017edc7  xor     edx, edx
0x18017edc9  xor     ecx, ecx
0x18017edcb  call    cs:__imp_SHTaskPoolQueueTask
0x18017edd1  mov     esi, eax
0x18017edd3  test    rdi, rdi
0x18017edd6  jz      short loc_18017EDE8
0x18017edd8  mov     rdx, [rdi]
0x18017eddb  mov     rcx, rdi
0x18017edde  mov     rax, [rdx+10h]
0x18017ede2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ede7  nop
0x18017ede8  mov     rcx, [rbp+5Fh]; this
0x18017edec  test    esi, esi
0x18017edee  jns     short loc_18017EE5E
0x18017edf0  mov     r9d, esi; char *
0x18017edf3  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017edfa  mov     edx, 46h ; 'F'; void *
0x18017edff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017ee05  mov     eax, [rsp+110h+pAptType]
0x18017ee09  test    eax, eax
0x18017ee0b  jz      loc_18017ED5F
0x18017ee11  cmp     eax, 3
0x18017ee14  jz      loc_18017ED5F
0x18017ee1a  lea     rcx, [rsp+110h+var_D8]
0x18017ee1f  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x18017ee24  nop
0x18017ee25  mov     rcx, rdi
0x18017ee28  call    ??R_lambda_85d6bdb00f12d8be81804bcc9332f94d_@@QEBA@XZ; _lambda_85d6bdb00f12d8be81804bcc9332f94d_::operator()(void)
0x18017ee2d  xorps   xmm0, xmm0
0x18017ee30  movups  xmmword ptr [rbx], xmm0
0x18017ee33  movups  xmmword ptr [rbx+10h], xmm0
0x18017ee37  mov     [rbx+20h], r15
0x18017ee3b  mov     [rbx+28h], r15
0x18017ee3f  mov     [rbx+30h], r15
0x18017ee43  mov     [rbx+38h], r15d
0x18017ee47  mov     [rbx+40h], r15
0x18017ee4b  mov     [rbx+48h], r15b
0x18017ee4f  lea     rcx, [rsp+110h+var_D8]
0x18017ee54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18017ee59  jmp     loc_18017EF08
0x18017ee5e  mov     rcx, [rbp+57h+var_C0]
0x18017ee62  mov     rax, [rcx]
0x18017ee65  xor     edx, edx
0x18017ee67  mov     rax, [rax+10h]
0x18017ee6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ee70  mov     edi, eax
0x18017ee72  xorps   xmm0, xmm0
0x18017ee75  movups  [rbp+57h+var_80], xmm0
0x18017ee79  movups  [rbp+57h+var_70], xmm0
0x18017ee7d  movdqa  [rbp+57h+var_60], xmm0
0x18017ee82  mov     [rbp+57h+var_50], r15
0x18017ee86  mov     [rbp+57h+var_48], r15d
0x18017ee8a  mov     [rbp+57h+var_40], r15
0x18017ee8e  mov     [rbp+57h+var_38], r15b
0x18017ee92  test    eax, eax
0x18017ee94  jns     short loc_18017EEC1
0x18017ee96  mov     rcx, [rbp+57h+var_C8]
0x18017ee9a  test    rcx, rcx
0x18017ee9d  jz      short loc_18017EEC1
0x18017ee9f  call    cs:__imp_SetRestrictedErrorInfo
0x18017eea5  mov     rcx, [rbp+5Fh]; this
0x18017eea9  test    eax, eax
0x18017eeab  jns     short loc_18017EEC1
0x18017eead  mov     r9d, eax; char *
0x18017eeb0  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017eeb7  mov     edx, 4Fh ; 'O'; void *
0x18017eebc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017eec1  mov     rcx, [rbp+5Fh]; this
0x18017eec5  test    edi, edi
0x18017eec7  jns     short loc_18017EEDE
0x18017eec9  mov     r9d, edi; char *
0x18017eecc  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017eed3  mov     edx, 51h ; 'Q'; void *
0x18017eed8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017eede  lea     rdx, [rbp+57h+var_80]
0x18017eee2  mov     rcx, rbx
0x18017eee5  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x18017eeea  nop
0x18017eeeb  lea     rcx, [rbp+57h+var_80]; this
0x18017eeef  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18017eef4  nop
0x18017eef5  lea     rcx, [rbp+57h+var_C8]
0x18017eef9  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18017eefe  nop
0x18017eeff  lea     rcx, [rbp+57h+var_C0]
0x18017ef03  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x18017ef08  mov     rax, rbx
0x18017ef0b  add     rsp, 0E8h
0x18017ef12  pop     r15
0x18017ef14  pop     r14
0x18017ef16  pop     rdi
0x18017ef17  pop     rsi
0x18017ef18  pop     rbx
0x18017ef19  pop     rbp
0x18017ef1a  retn
```
