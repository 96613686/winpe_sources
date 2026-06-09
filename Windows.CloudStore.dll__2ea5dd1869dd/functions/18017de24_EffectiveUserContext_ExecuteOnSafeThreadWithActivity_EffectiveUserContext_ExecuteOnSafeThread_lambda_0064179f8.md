# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_0064179f891be2e2c1ed78418584cbf9_>(_lambda_0064179f891be2e2c1ed78418584cbf9_ &&)'::`2'::NopActivity const,_lambda_0064179f891be2e2c1ed78418584cbf9_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_0064179f891be2e2c1ed78418584cbf9_>(_lambda_0064179f891be2e2c1ed78418584cbf9_ &&)'::`2'::NopActivity const &,_lambda_0064179f891be2e2c1ed78418584cbf9_ &)

- ea: `0x18017de24`
- end: `0x18017e03b`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_0064179f891be2e2c1ed78418584cbf9_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_0064179f891be2e2c1ed78418584cbf9_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_0064179f891be2e2c1ed78418584cbf9_@@@0@QEBAX$$QEAV_lambda_0064179f891be2e2c1ed78418584cbf9_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801804d4`

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
- `0x180102c4c`
- `0x18017de24`
- `0x180180bc0`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18017deeb`
- `SHCORE!SHTaskPoolQueueTask` at `0x18017deeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017ded1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017ded1`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017de5a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017de5a`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017dfbf`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017dfbf`

## string_xrefs

- `0x18017de6f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017df13`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017dfd0`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017dfec`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_0064179f891be2e2c1ed78418584cbf9_>'::`2'::NopActivity const,AX$$QEAV_lambda_0064179f891be2e2c1ed78418584cbf9_ const * const>(
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
      _lambda_0064179f891be2e2c1ed78418584cbf9_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_547369243b05b04b61ab32b04742373c_ &>,_lambda_547369243b05b04b61ab32b04742373c_ &>(
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
0x18017de24  push    rbp
0x18017de26  push    rbx
0x18017de27  push    rsi
0x18017de28  push    rdi
0x18017de29  push    r14
0x18017de2b  push    r15
0x18017de2d  lea     rbp, [rsp-2Fh]
0x18017de32  sub     rsp, 0E8h
0x18017de39  mov     rdi, r9
0x18017de3c  mov     rsi, r8
0x18017de3f  mov     rbx, rdx
0x18017de42  mov     r14, rcx
0x18017de45  xor     r15d, r15d
0x18017de48  mov     [rsp+110h+pAptType], r15d
0x18017de4d  mov     [rbp+57h+pAptQualifier], r15d
0x18017de51  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x18017de55  lea     rcx, [rsp+110h+pAptType]; pAptType
0x18017de5a  call    cs:__imp_CoGetApartmentType
0x18017de60  mov     rcx, [rbp+5Fh]; this
0x18017de64  test    eax, eax
0x18017de66  jns     loc_18017DF25
0x18017de6c  mov     r9d, eax; char *
0x18017de6f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017de76  lea     edx, [r15+29h]; void *
0x18017de7a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017de7f  lea     rcx, [rbp+57h+var_C0]
0x18017de83  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x18017de88  nop
0x18017de89  mov     [rbp+57h+var_C8], r15
0x18017de8d  mov     [rbp+57h+var_B0], r14
0x18017de91  mov     [rbp+57h+var_A8], rsi
0x18017de95  mov     [rbp+57h+var_A0], rdi
0x18017de99  lea     rax, [rbp+57h+var_C8]
0x18017de9d  mov     [rbp+57h+var_98], rax
0x18017dea1  lea     rax, [rbp+57h+var_C0]
0x18017dea5  mov     [rbp+57h+var_90], rax
0x18017dea9  lea     rdx, [rbp+57h+var_B0]
0x18017dead  lea     rcx, [rsp+110h+var_D8]
0x18017deb2  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_547369243b05b04b61ab32b04742373c_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_547369243b05b04b61ab32b04742373c_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_547369243b05b04b61ab32b04742373c_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_547369243b05b04b61ab32b04742373c_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_547369243b05b04b61ab32b04742373c_ &>,_lambda_547369243b05b04b61ab32b04742373c_ &>(_lambda_547369243b05b04b61ab32b04742373c_ &)
0x18017deb7  mov     rdi, [rax]
0x18017deba  mov     [rax], r15
0x18017debd  mov     rcx, [rsp+110h+var_D8]
0x18017dec2  test    rcx, rcx
0x18017dec5  jz      short loc_18017DED1
0x18017dec7  mov     [rsp+110h+var_D8], r15
0x18017decc  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18017ded1  call    cs:__imp_GetCurrentThreadId
0x18017ded7  mov     [rsp+110h+var_E8], r15
0x18017dedc  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x18017dee1  xor     r9d, r9d
0x18017dee4  mov     r8d, eax
0x18017dee7  xor     edx, edx
0x18017dee9  xor     ecx, ecx
0x18017deeb  call    cs:__imp_SHTaskPoolQueueTask
0x18017def1  mov     esi, eax
0x18017def3  test    rdi, rdi
0x18017def6  jz      short loc_18017DF08
0x18017def8  mov     rdx, [rdi]
0x18017defb  mov     rcx, rdi
0x18017defe  mov     rax, [rdx+10h]
0x18017df02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017df07  nop
0x18017df08  mov     rcx, [rbp+5Fh]; this
0x18017df0c  test    esi, esi
0x18017df0e  jns     short loc_18017DF7E
0x18017df10  mov     r9d, esi; char *
0x18017df13  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017df1a  mov     edx, 46h ; 'F'; void *
0x18017df1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017df25  mov     eax, [rsp+110h+pAptType]
0x18017df29  test    eax, eax
0x18017df2b  jz      loc_18017DE7F
0x18017df31  cmp     eax, 3
0x18017df34  jz      loc_18017DE7F
0x18017df3a  lea     rcx, [rsp+110h+var_D8]
0x18017df3f  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x18017df44  nop
0x18017df45  mov     rcx, rdi
0x18017df48  call    ??R_lambda_0064179f891be2e2c1ed78418584cbf9_@@QEBA@XZ; _lambda_0064179f891be2e2c1ed78418584cbf9_::operator()(void)
0x18017df4d  xorps   xmm0, xmm0
0x18017df50  movups  xmmword ptr [rbx], xmm0
0x18017df53  movups  xmmword ptr [rbx+10h], xmm0
0x18017df57  mov     [rbx+20h], r15
0x18017df5b  mov     [rbx+28h], r15
0x18017df5f  mov     [rbx+30h], r15
0x18017df63  mov     [rbx+38h], r15d
0x18017df67  mov     [rbx+40h], r15
0x18017df6b  mov     [rbx+48h], r15b
0x18017df6f  lea     rcx, [rsp+110h+var_D8]
0x18017df74  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18017df79  jmp     loc_18017E028
0x18017df7e  mov     rcx, [rbp+57h+var_C0]
0x18017df82  mov     rax, [rcx]
0x18017df85  xor     edx, edx
0x18017df87  mov     rax, [rax+10h]
0x18017df8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017df90  mov     edi, eax
0x18017df92  xorps   xmm0, xmm0
0x18017df95  movups  [rbp+57h+var_80], xmm0
0x18017df99  movups  [rbp+57h+var_70], xmm0
0x18017df9d  movdqa  [rbp+57h+var_60], xmm0
0x18017dfa2  mov     [rbp+57h+var_50], r15
0x18017dfa6  mov     [rbp+57h+var_48], r15d
0x18017dfaa  mov     [rbp+57h+var_40], r15
0x18017dfae  mov     [rbp+57h+var_38], r15b
0x18017dfb2  test    eax, eax
0x18017dfb4  jns     short loc_18017DFE1
0x18017dfb6  mov     rcx, [rbp+57h+var_C8]
0x18017dfba  test    rcx, rcx
0x18017dfbd  jz      short loc_18017DFE1
0x18017dfbf  call    cs:__imp_SetRestrictedErrorInfo
0x18017dfc5  mov     rcx, [rbp+5Fh]; this
0x18017dfc9  test    eax, eax
0x18017dfcb  jns     short loc_18017DFE1
0x18017dfcd  mov     r9d, eax; char *
0x18017dfd0  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017dfd7  mov     edx, 4Fh ; 'O'; void *
0x18017dfdc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017dfe1  mov     rcx, [rbp+5Fh]; this
0x18017dfe5  test    edi, edi
0x18017dfe7  jns     short loc_18017DFFE
0x18017dfe9  mov     r9d, edi; char *
0x18017dfec  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017dff3  mov     edx, 51h ; 'Q'; void *
0x18017dff8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017dffe  lea     rdx, [rbp+57h+var_80]
0x18017e002  mov     rcx, rbx
0x18017e005  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x18017e00a  nop
0x18017e00b  lea     rcx, [rbp+57h+var_80]; this
0x18017e00f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18017e014  nop
0x18017e015  lea     rcx, [rbp+57h+var_C8]
0x18017e019  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18017e01e  nop
0x18017e01f  lea     rcx, [rbp+57h+var_C0]
0x18017e023  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x18017e028  mov     rax, rbx
0x18017e02b  add     rsp, 0E8h
0x18017e032  pop     r15
0x18017e034  pop     r14
0x18017e036  pop     rdi
0x18017e037  pop     rsi
0x18017e038  pop     rbx
0x18017e039  pop     rbp
0x18017e03a  retn
```
