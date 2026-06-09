# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_825250b7e8419aaa46f7cd022b100d9c_>(_lambda_825250b7e8419aaa46f7cd022b100d9c_ &&)'::`2'::NopActivity const,_lambda_825250b7e8419aaa46f7cd022b100d9c_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_825250b7e8419aaa46f7cd022b100d9c_>(_lambda_825250b7e8419aaa46f7cd022b100d9c_ &&)'::`2'::NopActivity const &,_lambda_825250b7e8419aaa46f7cd022b100d9c_ &)

- ea: `0x18017eae4`
- end: `0x18017ecfb`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_825250b7e8419aaa46f7cd022b100d9c_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_825250b7e8419aaa46f7cd022b100d9c_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_825250b7e8419aaa46f7cd022b100d9c_@@@0@QEBAX$$QEAV_lambda_825250b7e8419aaa46f7cd022b100d9c_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18017ffa0`

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
- `0x18017eae4`
- `0x180180930`
- `0x180181e54`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18017ebab`
- `SHCORE!SHTaskPoolQueueTask` at `0x18017ebab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017eb91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017eb91`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017eb1a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017eb1a`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017ec7f`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017ec7f`

## string_xrefs

- `0x18017eb2f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017ebd3`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017ec90`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017ecac`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_825250b7e8419aaa46f7cd022b100d9c_>'::`2'::NopActivity const,AX$$QEAV_lambda_825250b7e8419aaa46f7cd022b100d9c_ const * const>(
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
      _lambda_825250b7e8419aaa46f7cd022b100d9c_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_45930467311f4ef95e7b754b541789b0_ &>,_lambda_45930467311f4ef95e7b754b541789b0_ &>(
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
0x18017eae4  push    rbp
0x18017eae6  push    rbx
0x18017eae7  push    rsi
0x18017eae8  push    rdi
0x18017eae9  push    r14
0x18017eaeb  push    r15
0x18017eaed  lea     rbp, [rsp-2Fh]
0x18017eaf2  sub     rsp, 0E8h
0x18017eaf9  mov     rdi, r9
0x18017eafc  mov     rsi, r8
0x18017eaff  mov     rbx, rdx
0x18017eb02  mov     r14, rcx
0x18017eb05  xor     r15d, r15d
0x18017eb08  mov     [rsp+110h+pAptType], r15d
0x18017eb0d  mov     [rbp+57h+pAptQualifier], r15d
0x18017eb11  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x18017eb15  lea     rcx, [rsp+110h+pAptType]; pAptType
0x18017eb1a  call    cs:__imp_CoGetApartmentType
0x18017eb20  mov     rcx, [rbp+5Fh]; this
0x18017eb24  test    eax, eax
0x18017eb26  jns     loc_18017EBE5
0x18017eb2c  mov     r9d, eax; char *
0x18017eb2f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017eb36  lea     edx, [r15+29h]; void *
0x18017eb3a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017eb3f  lea     rcx, [rbp+57h+var_C0]
0x18017eb43  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x18017eb48  nop
0x18017eb49  mov     [rbp+57h+var_C8], r15
0x18017eb4d  mov     [rbp+57h+var_B0], r14
0x18017eb51  mov     [rbp+57h+var_A8], rsi
0x18017eb55  mov     [rbp+57h+var_A0], rdi
0x18017eb59  lea     rax, [rbp+57h+var_C8]
0x18017eb5d  mov     [rbp+57h+var_98], rax
0x18017eb61  lea     rax, [rbp+57h+var_C0]
0x18017eb65  mov     [rbp+57h+var_90], rax
0x18017eb69  lea     rdx, [rbp+57h+var_B0]
0x18017eb6d  lea     rcx, [rsp+110h+var_D8]
0x18017eb72  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_45930467311f4ef95e7b754b541789b0_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_45930467311f4ef95e7b754b541789b0_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_45930467311f4ef95e7b754b541789b0_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_45930467311f4ef95e7b754b541789b0_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_45930467311f4ef95e7b754b541789b0_ &>,_lambda_45930467311f4ef95e7b754b541789b0_ &>(_lambda_45930467311f4ef95e7b754b541789b0_ &)
0x18017eb77  mov     rdi, [rax]
0x18017eb7a  mov     [rax], r15
0x18017eb7d  mov     rcx, [rsp+110h+var_D8]
0x18017eb82  test    rcx, rcx
0x18017eb85  jz      short loc_18017EB91
0x18017eb87  mov     [rsp+110h+var_D8], r15
0x18017eb8c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18017eb91  call    cs:__imp_GetCurrentThreadId
0x18017eb97  mov     [rsp+110h+var_E8], r15
0x18017eb9c  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x18017eba1  xor     r9d, r9d
0x18017eba4  mov     r8d, eax
0x18017eba7  xor     edx, edx
0x18017eba9  xor     ecx, ecx
0x18017ebab  call    cs:__imp_SHTaskPoolQueueTask
0x18017ebb1  mov     esi, eax
0x18017ebb3  test    rdi, rdi
0x18017ebb6  jz      short loc_18017EBC8
0x18017ebb8  mov     rdx, [rdi]
0x18017ebbb  mov     rcx, rdi
0x18017ebbe  mov     rax, [rdx+10h]
0x18017ebc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ebc7  nop
0x18017ebc8  mov     rcx, [rbp+5Fh]; this
0x18017ebcc  test    esi, esi
0x18017ebce  jns     short loc_18017EC3E
0x18017ebd0  mov     r9d, esi; char *
0x18017ebd3  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017ebda  mov     edx, 46h ; 'F'; void *
0x18017ebdf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017ebe5  mov     eax, [rsp+110h+pAptType]
0x18017ebe9  test    eax, eax
0x18017ebeb  jz      loc_18017EB3F
0x18017ebf1  cmp     eax, 3
0x18017ebf4  jz      loc_18017EB3F
0x18017ebfa  lea     rcx, [rsp+110h+var_D8]
0x18017ebff  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x18017ec04  nop
0x18017ec05  mov     rcx, rdi
0x18017ec08  call    ??R_lambda_825250b7e8419aaa46f7cd022b100d9c_@@QEBA@XZ; _lambda_825250b7e8419aaa46f7cd022b100d9c_::operator()(void)
0x18017ec0d  xorps   xmm0, xmm0
0x18017ec10  movups  xmmword ptr [rbx], xmm0
0x18017ec13  movups  xmmword ptr [rbx+10h], xmm0
0x18017ec17  mov     [rbx+20h], r15
0x18017ec1b  mov     [rbx+28h], r15
0x18017ec1f  mov     [rbx+30h], r15
0x18017ec23  mov     [rbx+38h], r15d
0x18017ec27  mov     [rbx+40h], r15
0x18017ec2b  mov     [rbx+48h], r15b
0x18017ec2f  lea     rcx, [rsp+110h+var_D8]
0x18017ec34  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18017ec39  jmp     loc_18017ECE8
0x18017ec3e  mov     rcx, [rbp+57h+var_C0]
0x18017ec42  mov     rax, [rcx]
0x18017ec45  xor     edx, edx
0x18017ec47  mov     rax, [rax+10h]
0x18017ec4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ec50  mov     edi, eax
0x18017ec52  xorps   xmm0, xmm0
0x18017ec55  movups  [rbp+57h+var_80], xmm0
0x18017ec59  movups  [rbp+57h+var_70], xmm0
0x18017ec5d  movdqa  [rbp+57h+var_60], xmm0
0x18017ec62  mov     [rbp+57h+var_50], r15
0x18017ec66  mov     [rbp+57h+var_48], r15d
0x18017ec6a  mov     [rbp+57h+var_40], r15
0x18017ec6e  mov     [rbp+57h+var_38], r15b
0x18017ec72  test    eax, eax
0x18017ec74  jns     short loc_18017ECA1
0x18017ec76  mov     rcx, [rbp+57h+var_C8]
0x18017ec7a  test    rcx, rcx
0x18017ec7d  jz      short loc_18017ECA1
0x18017ec7f  call    cs:__imp_SetRestrictedErrorInfo
0x18017ec85  mov     rcx, [rbp+5Fh]; this
0x18017ec89  test    eax, eax
0x18017ec8b  jns     short loc_18017ECA1
0x18017ec8d  mov     r9d, eax; char *
0x18017ec90  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017ec97  mov     edx, 4Fh ; 'O'; void *
0x18017ec9c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017eca1  mov     rcx, [rbp+5Fh]; this
0x18017eca5  test    edi, edi
0x18017eca7  jns     short loc_18017ECBE
0x18017eca9  mov     r9d, edi; char *
0x18017ecac  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017ecb3  mov     edx, 51h ; 'Q'; void *
0x18017ecb8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017ecbe  lea     rdx, [rbp+57h+var_80]
0x18017ecc2  mov     rcx, rbx
0x18017ecc5  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x18017ecca  nop
0x18017eccb  lea     rcx, [rbp+57h+var_80]; this
0x18017eccf  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18017ecd4  nop
0x18017ecd5  lea     rcx, [rbp+57h+var_C8]
0x18017ecd9  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18017ecde  nop
0x18017ecdf  lea     rcx, [rbp+57h+var_C0]
0x18017ece3  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x18017ece8  mov     rax, rbx
0x18017eceb  add     rsp, 0E8h
0x18017ecf2  pop     r15
0x18017ecf4  pop     r14
0x18017ecf6  pop     rdi
0x18017ecf7  pop     rsi
0x18017ecf8  pop     rbx
0x18017ecf9  pop     rbp
0x18017ecfa  retn
```
