# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_614d86cc28371282e2cb43dfe985a128_>(_lambda_614d86cc28371282e2cb43dfe985a128_ &&)'::`2'::NopActivity const,_lambda_614d86cc28371282e2cb43dfe985a128_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_614d86cc28371282e2cb43dfe985a128_>(_lambda_614d86cc28371282e2cb43dfe985a128_ &&)'::`2'::NopActivity const &,_lambda_614d86cc28371282e2cb43dfe985a128_ &)

- ea: `0x1800cfbdc`
- end: `0x1800cfdf3`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_614d86cc28371282e2cb43dfe985a128_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_614d86cc28371282e2cb43dfe985a128_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_614d86cc28371282e2cb43dfe985a128_@@@0@QEBAX$$QEAV_lambda_614d86cc28371282e2cb43dfe985a128_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800cfdfc`

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
- `0x1800cfbdc`
- `0x1800e2ed4`
- `0x1800e93e0`
- `0x180196868`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800cfca3`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800cfca3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cfc89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cfc89`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cfc12`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cfc12`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cfd77`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cfd77`

## string_xrefs

- `0x1800cfc27`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cfccb`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cfd88`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cfda4`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_614d86cc28371282e2cb43dfe985a128_>'::`2'::NopActivity const,AX$$QEAV_lambda_614d86cc28371282e2cb43dfe985a128_ const * const>(
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
      _lambda_614d86cc28371282e2cb43dfe985a128_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_d76017c5ee2c87169503e0006cdd8f3e_ &>,_lambda_d76017c5ee2c87169503e0006cdd8f3e_ &>(
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
0x1800cfbdc  push    rbp
0x1800cfbde  push    rbx
0x1800cfbdf  push    rsi
0x1800cfbe0  push    rdi
0x1800cfbe1  push    r14
0x1800cfbe3  push    r15
0x1800cfbe5  lea     rbp, [rsp-2Fh]
0x1800cfbea  sub     rsp, 0E8h
0x1800cfbf1  mov     rdi, r9
0x1800cfbf4  mov     rsi, r8
0x1800cfbf7  mov     rbx, rdx
0x1800cfbfa  mov     r14, rcx
0x1800cfbfd  xor     r15d, r15d
0x1800cfc00  mov     [rsp+110h+pAptType], r15d
0x1800cfc05  mov     [rbp+57h+pAptQualifier], r15d
0x1800cfc09  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800cfc0d  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800cfc12  call    cs:__imp_CoGetApartmentType
0x1800cfc18  mov     rcx, [rbp+5Fh]; this
0x1800cfc1c  test    eax, eax
0x1800cfc1e  jns     loc_1800CFCDD
0x1800cfc24  mov     r9d, eax; char *
0x1800cfc27  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cfc2e  lea     edx, [r15+29h]; void *
0x1800cfc32  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cfc37  lea     rcx, [rbp+57h+var_C0]
0x1800cfc3b  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800cfc40  nop
0x1800cfc41  mov     [rbp+57h+var_C8], r15
0x1800cfc45  mov     [rbp+57h+var_B0], r14
0x1800cfc49  mov     [rbp+57h+var_A8], rsi
0x1800cfc4d  mov     [rbp+57h+var_A0], rdi
0x1800cfc51  lea     rax, [rbp+57h+var_C8]
0x1800cfc55  mov     [rbp+57h+var_98], rax
0x1800cfc59  lea     rax, [rbp+57h+var_C0]
0x1800cfc5d  mov     [rbp+57h+var_90], rax
0x1800cfc61  lea     rdx, [rbp+57h+var_B0]
0x1800cfc65  lea     rcx, [rsp+110h+var_D8]
0x1800cfc6a  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_d76017c5ee2c87169503e0006cdd8f3e_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_d76017c5ee2c87169503e0006cdd8f3e_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_d76017c5ee2c87169503e0006cdd8f3e_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_d76017c5ee2c87169503e0006cdd8f3e_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_d76017c5ee2c87169503e0006cdd8f3e_ &>,_lambda_d76017c5ee2c87169503e0006cdd8f3e_ &>(_lambda_d76017c5ee2c87169503e0006cdd8f3e_ &)
0x1800cfc6f  mov     rdi, [rax]
0x1800cfc72  mov     [rax], r15
0x1800cfc75  mov     rcx, [rsp+110h+var_D8]
0x1800cfc7a  test    rcx, rcx
0x1800cfc7d  jz      short loc_1800CFC89
0x1800cfc7f  mov     [rsp+110h+var_D8], r15
0x1800cfc84  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800cfc89  call    cs:__imp_GetCurrentThreadId
0x1800cfc8f  mov     [rsp+110h+var_E8], r15
0x1800cfc94  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800cfc99  xor     r9d, r9d
0x1800cfc9c  mov     r8d, eax
0x1800cfc9f  xor     edx, edx
0x1800cfca1  xor     ecx, ecx
0x1800cfca3  call    cs:__imp_SHTaskPoolQueueTask
0x1800cfca9  mov     esi, eax
0x1800cfcab  test    rdi, rdi
0x1800cfcae  jz      short loc_1800CFCC0
0x1800cfcb0  mov     rdx, [rdi]
0x1800cfcb3  mov     rcx, rdi
0x1800cfcb6  mov     rax, [rdx+10h]
0x1800cfcba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cfcbf  nop
0x1800cfcc0  mov     rcx, [rbp+5Fh]; this
0x1800cfcc4  test    esi, esi
0x1800cfcc6  jns     short loc_1800CFD36
0x1800cfcc8  mov     r9d, esi; char *
0x1800cfccb  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cfcd2  mov     edx, 46h ; 'F'; void *
0x1800cfcd7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cfcdd  mov     eax, [rsp+110h+pAptType]
0x1800cfce1  test    eax, eax
0x1800cfce3  jz      loc_1800CFC37
0x1800cfce9  cmp     eax, 3
0x1800cfcec  jz      loc_1800CFC37
0x1800cfcf2  lea     rcx, [rsp+110h+var_D8]
0x1800cfcf7  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cfcfc  nop
0x1800cfcfd  mov     rcx, rdi
0x1800cfd00  call    ??R_lambda_614d86cc28371282e2cb43dfe985a128_@@QEBA@XZ; _lambda_614d86cc28371282e2cb43dfe985a128_::operator()(void)
0x1800cfd05  xorps   xmm0, xmm0
0x1800cfd08  movups  xmmword ptr [rbx], xmm0
0x1800cfd0b  movups  xmmword ptr [rbx+10h], xmm0
0x1800cfd0f  mov     [rbx+20h], r15
0x1800cfd13  mov     [rbx+28h], r15
0x1800cfd17  mov     [rbx+30h], r15
0x1800cfd1b  mov     [rbx+38h], r15d
0x1800cfd1f  mov     [rbx+40h], r15
0x1800cfd23  mov     [rbx+48h], r15b
0x1800cfd27  lea     rcx, [rsp+110h+var_D8]
0x1800cfd2c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800cfd31  jmp     loc_1800CFDE0
0x1800cfd36  mov     rcx, [rbp+57h+var_C0]
0x1800cfd3a  mov     rax, [rcx]
0x1800cfd3d  xor     edx, edx
0x1800cfd3f  mov     rax, [rax+10h]
0x1800cfd43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cfd48  mov     edi, eax
0x1800cfd4a  xorps   xmm0, xmm0
0x1800cfd4d  movups  [rbp+57h+var_80], xmm0
0x1800cfd51  movups  [rbp+57h+var_70], xmm0
0x1800cfd55  movdqa  [rbp+57h+var_60], xmm0
0x1800cfd5a  mov     [rbp+57h+var_50], r15
0x1800cfd5e  mov     [rbp+57h+var_48], r15d
0x1800cfd62  mov     [rbp+57h+var_40], r15
0x1800cfd66  mov     [rbp+57h+var_38], r15b
0x1800cfd6a  test    eax, eax
0x1800cfd6c  jns     short loc_1800CFD99
0x1800cfd6e  mov     rcx, [rbp+57h+var_C8]
0x1800cfd72  test    rcx, rcx
0x1800cfd75  jz      short loc_1800CFD99
0x1800cfd77  call    cs:__imp_SetRestrictedErrorInfo
0x1800cfd7d  mov     rcx, [rbp+5Fh]; this
0x1800cfd81  test    eax, eax
0x1800cfd83  jns     short loc_1800CFD99
0x1800cfd85  mov     r9d, eax; char *
0x1800cfd88  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cfd8f  mov     edx, 4Fh ; 'O'; void *
0x1800cfd94  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cfd99  mov     rcx, [rbp+5Fh]; this
0x1800cfd9d  test    edi, edi
0x1800cfd9f  jns     short loc_1800CFDB6
0x1800cfda1  mov     r9d, edi; char *
0x1800cfda4  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cfdab  mov     edx, 51h ; 'Q'; void *
0x1800cfdb0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cfdb6  lea     rdx, [rbp+57h+var_80]
0x1800cfdba  mov     rcx, rbx
0x1800cfdbd  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800cfdc2  nop
0x1800cfdc3  lea     rcx, [rbp+57h+var_80]; this
0x1800cfdc7  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800cfdcc  nop
0x1800cfdcd  lea     rcx, [rbp+57h+var_C8]
0x1800cfdd1  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800cfdd6  nop
0x1800cfdd7  lea     rcx, [rbp+57h+var_C0]
0x1800cfddb  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800cfde0  mov     rax, rbx
0x1800cfde3  add     rsp, 0E8h
0x1800cfdea  pop     r15
0x1800cfdec  pop     r14
0x1800cfdee  pop     rdi
0x1800cfdef  pop     rsi
0x1800cfdf0  pop     rbx
0x1800cfdf1  pop     rbp
0x1800cfdf2  retn
```
