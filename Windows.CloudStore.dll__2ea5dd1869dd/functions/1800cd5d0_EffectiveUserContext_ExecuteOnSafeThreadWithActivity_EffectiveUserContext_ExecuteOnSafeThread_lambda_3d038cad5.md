# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_3d038cad510be8612f5a7b70112a19ca_>(_lambda_3d038cad510be8612f5a7b70112a19ca_ &&)'::`2'::NopActivity const,_lambda_3d038cad510be8612f5a7b70112a19ca_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_3d038cad510be8612f5a7b70112a19ca_>(_lambda_3d038cad510be8612f5a7b70112a19ca_ &&)'::`2'::NopActivity const &,_lambda_3d038cad510be8612f5a7b70112a19ca_ &)

- ea: `0x1800cd5d0`
- end: `0x1800cd7e7`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_3d038cad510be8612f5a7b70112a19ca_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_3d038cad510be8612f5a7b70112a19ca_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_3d038cad510be8612f5a7b70112a19ca_@@@0@QEBAX$$QEAV_lambda_3d038cad510be8612f5a7b70112a19ca_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180197200`

## callees

- `0x18000dfe4`
- `0x180010688`
- `0x180016cf4`
- `0x180035b7c`
- `0x180038db8`
- `0x18005dde0`
- `0x180061e60`
- `0x180064888`
- `0x1800cd5d0`
- `0x1800ce314`
- `0x1800e93e0`
- `0x1800f7b14`
- `0x1801967c4`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800cd697`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800cd697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd67d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd67d`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cd606`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cd606`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cd76b`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cd76b`

## string_xrefs

- `0x1800cd61b`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cd6bf`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cd77c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cd798`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_3d038cad510be8612f5a7b70112a19ca_>'::`2'::NopActivity const,AX$$QEAV_lambda_3d038cad510be8612f5a7b70112a19ca_ const * const>(
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
      _lambda_3d038cad510be8612f5a7b70112a19ca_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c737f2e76682c9e250a50d00ddf15dad_ &>,_lambda_c737f2e76682c9e250a50d00ddf15dad_ &>(
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
0x1800cd5d0  push    rbp
0x1800cd5d2  push    rbx
0x1800cd5d3  push    rsi
0x1800cd5d4  push    rdi
0x1800cd5d5  push    r14
0x1800cd5d7  push    r15
0x1800cd5d9  lea     rbp, [rsp-2Fh]
0x1800cd5de  sub     rsp, 0E8h
0x1800cd5e5  mov     rdi, r9
0x1800cd5e8  mov     rsi, r8
0x1800cd5eb  mov     rbx, rdx
0x1800cd5ee  mov     r14, rcx
0x1800cd5f1  xor     r15d, r15d
0x1800cd5f4  mov     [rsp+110h+pAptType], r15d
0x1800cd5f9  mov     [rbp+57h+pAptQualifier], r15d
0x1800cd5fd  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800cd601  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800cd606  call    cs:__imp_CoGetApartmentType
0x1800cd60c  mov     rcx, [rbp+5Fh]; this
0x1800cd610  test    eax, eax
0x1800cd612  jns     loc_1800CD6D1
0x1800cd618  mov     r9d, eax; char *
0x1800cd61b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd622  lea     edx, [r15+29h]; void *
0x1800cd626  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cd62b  lea     rcx, [rbp+57h+var_C0]
0x1800cd62f  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800cd634  nop
0x1800cd635  mov     [rbp+57h+var_C8], r15
0x1800cd639  mov     [rbp+57h+var_B0], r14
0x1800cd63d  mov     [rbp+57h+var_A8], rsi
0x1800cd641  mov     [rbp+57h+var_A0], rdi
0x1800cd645  lea     rax, [rbp+57h+var_C8]
0x1800cd649  mov     [rbp+57h+var_98], rax
0x1800cd64d  lea     rax, [rbp+57h+var_C0]
0x1800cd651  mov     [rbp+57h+var_90], rax
0x1800cd655  lea     rdx, [rbp+57h+var_B0]
0x1800cd659  lea     rcx, [rsp+110h+var_D8]
0x1800cd65e  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_c737f2e76682c9e250a50d00ddf15dad_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_c737f2e76682c9e250a50d00ddf15dad_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_c737f2e76682c9e250a50d00ddf15dad_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_c737f2e76682c9e250a50d00ddf15dad_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c737f2e76682c9e250a50d00ddf15dad_ &>,_lambda_c737f2e76682c9e250a50d00ddf15dad_ &>(_lambda_c737f2e76682c9e250a50d00ddf15dad_ &)
0x1800cd663  mov     rdi, [rax]
0x1800cd666  mov     [rax], r15
0x1800cd669  mov     rcx, [rsp+110h+var_D8]
0x1800cd66e  test    rcx, rcx
0x1800cd671  jz      short loc_1800CD67D
0x1800cd673  mov     [rsp+110h+var_D8], r15
0x1800cd678  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800cd67d  call    cs:__imp_GetCurrentThreadId
0x1800cd683  mov     [rsp+110h+var_E8], r15
0x1800cd688  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800cd68d  xor     r9d, r9d
0x1800cd690  mov     r8d, eax
0x1800cd693  xor     edx, edx
0x1800cd695  xor     ecx, ecx
0x1800cd697  call    cs:__imp_SHTaskPoolQueueTask
0x1800cd69d  mov     esi, eax
0x1800cd69f  test    rdi, rdi
0x1800cd6a2  jz      short loc_1800CD6B4
0x1800cd6a4  mov     rdx, [rdi]
0x1800cd6a7  mov     rcx, rdi
0x1800cd6aa  mov     rax, [rdx+10h]
0x1800cd6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd6b3  nop
0x1800cd6b4  mov     rcx, [rbp+5Fh]; this
0x1800cd6b8  test    esi, esi
0x1800cd6ba  jns     short loc_1800CD72A
0x1800cd6bc  mov     r9d, esi; char *
0x1800cd6bf  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd6c6  mov     edx, 46h ; 'F'; void *
0x1800cd6cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cd6d1  mov     eax, [rsp+110h+pAptType]
0x1800cd6d5  test    eax, eax
0x1800cd6d7  jz      loc_1800CD62B
0x1800cd6dd  cmp     eax, 3
0x1800cd6e0  jz      loc_1800CD62B
0x1800cd6e6  lea     rcx, [rsp+110h+var_D8]
0x1800cd6eb  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cd6f0  nop
0x1800cd6f1  mov     rcx, rdi
0x1800cd6f4  call    ??R_lambda_3d038cad510be8612f5a7b70112a19ca_@@QEBA@XZ; _lambda_3d038cad510be8612f5a7b70112a19ca_::operator()(void)
0x1800cd6f9  xorps   xmm0, xmm0
0x1800cd6fc  movups  xmmword ptr [rbx], xmm0
0x1800cd6ff  movups  xmmword ptr [rbx+10h], xmm0
0x1800cd703  mov     [rbx+20h], r15
0x1800cd707  mov     [rbx+28h], r15
0x1800cd70b  mov     [rbx+30h], r15
0x1800cd70f  mov     [rbx+38h], r15d
0x1800cd713  mov     [rbx+40h], r15
0x1800cd717  mov     [rbx+48h], r15b
0x1800cd71b  lea     rcx, [rsp+110h+var_D8]
0x1800cd720  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800cd725  jmp     loc_1800CD7D4
0x1800cd72a  mov     rcx, [rbp+57h+var_C0]
0x1800cd72e  mov     rax, [rcx]
0x1800cd731  xor     edx, edx
0x1800cd733  mov     rax, [rax+10h]
0x1800cd737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd73c  mov     edi, eax
0x1800cd73e  xorps   xmm0, xmm0
0x1800cd741  movups  [rbp+57h+var_80], xmm0
0x1800cd745  movups  [rbp+57h+var_70], xmm0
0x1800cd749  movdqa  [rbp+57h+var_60], xmm0
0x1800cd74e  mov     [rbp+57h+var_50], r15
0x1800cd752  mov     [rbp+57h+var_48], r15d
0x1800cd756  mov     [rbp+57h+var_40], r15
0x1800cd75a  mov     [rbp+57h+var_38], r15b
0x1800cd75e  test    eax, eax
0x1800cd760  jns     short loc_1800CD78D
0x1800cd762  mov     rcx, [rbp+57h+var_C8]
0x1800cd766  test    rcx, rcx
0x1800cd769  jz      short loc_1800CD78D
0x1800cd76b  call    cs:__imp_SetRestrictedErrorInfo
0x1800cd771  mov     rcx, [rbp+5Fh]; this
0x1800cd775  test    eax, eax
0x1800cd777  jns     short loc_1800CD78D
0x1800cd779  mov     r9d, eax; char *
0x1800cd77c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd783  mov     edx, 4Fh ; 'O'; void *
0x1800cd788  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cd78d  mov     rcx, [rbp+5Fh]; this
0x1800cd791  test    edi, edi
0x1800cd793  jns     short loc_1800CD7AA
0x1800cd795  mov     r9d, edi; char *
0x1800cd798  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cd79f  mov     edx, 51h ; 'Q'; void *
0x1800cd7a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cd7aa  lea     rdx, [rbp+57h+var_80]
0x1800cd7ae  mov     rcx, rbx
0x1800cd7b1  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800cd7b6  nop
0x1800cd7b7  lea     rcx, [rbp+57h+var_80]; this
0x1800cd7bb  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800cd7c0  nop
0x1800cd7c1  lea     rcx, [rbp+57h+var_C8]
0x1800cd7c5  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800cd7ca  nop
0x1800cd7cb  lea     rcx, [rbp+57h+var_C0]
0x1800cd7cf  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800cd7d4  mov     rax, rbx
0x1800cd7d7  add     rsp, 0E8h
0x1800cd7de  pop     r15
0x1800cd7e0  pop     r14
0x1800cd7e2  pop     rdi
0x1800cd7e3  pop     rsi
0x1800cd7e4  pop     rbx
0x1800cd7e5  pop     rbp
0x1800cd7e6  retn
```
