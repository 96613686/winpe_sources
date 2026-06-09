# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_2b4cf9d25fcbe3d76b1c31b75a588132_>(_lambda_2b4cf9d25fcbe3d76b1c31b75a588132_ &&)'::`2'::NopActivity const,_lambda_2b4cf9d25fcbe3d76b1c31b75a588132_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_2b4cf9d25fcbe3d76b1c31b75a588132_>(_lambda_2b4cf9d25fcbe3d76b1c31b75a588132_ &&)'::`2'::NopActivity const &,_lambda_2b4cf9d25fcbe3d76b1c31b75a588132_ &)

- ea: `0x1800ceee0`
- end: `0x1800cf0f7`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_2b4cf9d25fcbe3d76b1c31b75a588132_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_2b4cf9d25fcbe3d76b1c31b75a588132_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_2b4cf9d25fcbe3d76b1c31b75a588132_@@@0@QEBAX$$QEAV_lambda_2b4cf9d25fcbe3d76b1c31b75a588132_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18017fb00`

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
- `0x1800ceee0`
- `0x1800e93e0`
- `0x180181228`
- `0x180181808`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800cefa7`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800cefa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cef8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cef8d`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cef16`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cef16`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cf07b`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cf07b`

## string_xrefs

- `0x1800cef2b`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cefcf`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cf08c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cf0a8`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_2b4cf9d25fcbe3d76b1c31b75a588132_>'::`2'::NopActivity const,AX$$QEAV_lambda_2b4cf9d25fcbe3d76b1c31b75a588132_ const * const>(
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
      _lambda_2b4cf9d25fcbe3d76b1c31b75a588132_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c6be028f6c69d59537b60c18d040c1fe_ &>,_lambda_c6be028f6c69d59537b60c18d040c1fe_ &>(
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
0x1800ceee0  push    rbp
0x1800ceee2  push    rbx
0x1800ceee3  push    rsi
0x1800ceee4  push    rdi
0x1800ceee5  push    r14
0x1800ceee7  push    r15
0x1800ceee9  lea     rbp, [rsp-2Fh]
0x1800ceeee  sub     rsp, 0E8h
0x1800ceef5  mov     rdi, r9
0x1800ceef8  mov     rsi, r8
0x1800ceefb  mov     rbx, rdx
0x1800ceefe  mov     r14, rcx
0x1800cef01  xor     r15d, r15d
0x1800cef04  mov     [rsp+110h+pAptType], r15d
0x1800cef09  mov     [rbp+57h+pAptQualifier], r15d
0x1800cef0d  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800cef11  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800cef16  call    cs:__imp_CoGetApartmentType
0x1800cef1c  mov     rcx, [rbp+5Fh]; this
0x1800cef20  test    eax, eax
0x1800cef22  jns     loc_1800CEFE1
0x1800cef28  mov     r9d, eax; char *
0x1800cef2b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cef32  lea     edx, [r15+29h]; void *
0x1800cef36  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cef3b  lea     rcx, [rbp+57h+var_C0]
0x1800cef3f  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800cef44  nop
0x1800cef45  mov     [rbp+57h+var_C8], r15
0x1800cef49  mov     [rbp+57h+var_B0], r14
0x1800cef4d  mov     [rbp+57h+var_A8], rsi
0x1800cef51  mov     [rbp+57h+var_A0], rdi
0x1800cef55  lea     rax, [rbp+57h+var_C8]
0x1800cef59  mov     [rbp+57h+var_98], rax
0x1800cef5d  lea     rax, [rbp+57h+var_C0]
0x1800cef61  mov     [rbp+57h+var_90], rax
0x1800cef65  lea     rdx, [rbp+57h+var_B0]
0x1800cef69  lea     rcx, [rsp+110h+var_D8]
0x1800cef6e  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_c6be028f6c69d59537b60c18d040c1fe_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_c6be028f6c69d59537b60c18d040c1fe_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_c6be028f6c69d59537b60c18d040c1fe_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_c6be028f6c69d59537b60c18d040c1fe_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c6be028f6c69d59537b60c18d040c1fe_ &>,_lambda_c6be028f6c69d59537b60c18d040c1fe_ &>(_lambda_c6be028f6c69d59537b60c18d040c1fe_ &)
0x1800cef73  mov     rdi, [rax]
0x1800cef76  mov     [rax], r15
0x1800cef79  mov     rcx, [rsp+110h+var_D8]
0x1800cef7e  test    rcx, rcx
0x1800cef81  jz      short loc_1800CEF8D
0x1800cef83  mov     [rsp+110h+var_D8], r15
0x1800cef88  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800cef8d  call    cs:__imp_GetCurrentThreadId
0x1800cef93  mov     [rsp+110h+var_E8], r15
0x1800cef98  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800cef9d  xor     r9d, r9d
0x1800cefa0  mov     r8d, eax
0x1800cefa3  xor     edx, edx
0x1800cefa5  xor     ecx, ecx
0x1800cefa7  call    cs:__imp_SHTaskPoolQueueTask
0x1800cefad  mov     esi, eax
0x1800cefaf  test    rdi, rdi
0x1800cefb2  jz      short loc_1800CEFC4
0x1800cefb4  mov     rdx, [rdi]
0x1800cefb7  mov     rcx, rdi
0x1800cefba  mov     rax, [rdx+10h]
0x1800cefbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cefc3  nop
0x1800cefc4  mov     rcx, [rbp+5Fh]; this
0x1800cefc8  test    esi, esi
0x1800cefca  jns     short loc_1800CF03A
0x1800cefcc  mov     r9d, esi; char *
0x1800cefcf  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cefd6  mov     edx, 46h ; 'F'; void *
0x1800cefdb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cefe1  mov     eax, [rsp+110h+pAptType]
0x1800cefe5  test    eax, eax
0x1800cefe7  jz      loc_1800CEF3B
0x1800cefed  cmp     eax, 3
0x1800ceff0  jz      loc_1800CEF3B
0x1800ceff6  lea     rcx, [rsp+110h+var_D8]
0x1800ceffb  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cf000  nop
0x1800cf001  mov     rcx, rdi
0x1800cf004  call    ??R_lambda_2b4cf9d25fcbe3d76b1c31b75a588132_@@QEBA@XZ; _lambda_2b4cf9d25fcbe3d76b1c31b75a588132_::operator()(void)
0x1800cf009  xorps   xmm0, xmm0
0x1800cf00c  movups  xmmword ptr [rbx], xmm0
0x1800cf00f  movups  xmmword ptr [rbx+10h], xmm0
0x1800cf013  mov     [rbx+20h], r15
0x1800cf017  mov     [rbx+28h], r15
0x1800cf01b  mov     [rbx+30h], r15
0x1800cf01f  mov     [rbx+38h], r15d
0x1800cf023  mov     [rbx+40h], r15
0x1800cf027  mov     [rbx+48h], r15b
0x1800cf02b  lea     rcx, [rsp+110h+var_D8]
0x1800cf030  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800cf035  jmp     loc_1800CF0E4
0x1800cf03a  mov     rcx, [rbp+57h+var_C0]
0x1800cf03e  mov     rax, [rcx]
0x1800cf041  xor     edx, edx
0x1800cf043  mov     rax, [rax+10h]
0x1800cf047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf04c  mov     edi, eax
0x1800cf04e  xorps   xmm0, xmm0
0x1800cf051  movups  [rbp+57h+var_80], xmm0
0x1800cf055  movups  [rbp+57h+var_70], xmm0
0x1800cf059  movdqa  [rbp+57h+var_60], xmm0
0x1800cf05e  mov     [rbp+57h+var_50], r15
0x1800cf062  mov     [rbp+57h+var_48], r15d
0x1800cf066  mov     [rbp+57h+var_40], r15
0x1800cf06a  mov     [rbp+57h+var_38], r15b
0x1800cf06e  test    eax, eax
0x1800cf070  jns     short loc_1800CF09D
0x1800cf072  mov     rcx, [rbp+57h+var_C8]
0x1800cf076  test    rcx, rcx
0x1800cf079  jz      short loc_1800CF09D
0x1800cf07b  call    cs:__imp_SetRestrictedErrorInfo
0x1800cf081  mov     rcx, [rbp+5Fh]; this
0x1800cf085  test    eax, eax
0x1800cf087  jns     short loc_1800CF09D
0x1800cf089  mov     r9d, eax; char *
0x1800cf08c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cf093  mov     edx, 4Fh ; 'O'; void *
0x1800cf098  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cf09d  mov     rcx, [rbp+5Fh]; this
0x1800cf0a1  test    edi, edi
0x1800cf0a3  jns     short loc_1800CF0BA
0x1800cf0a5  mov     r9d, edi; char *
0x1800cf0a8  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cf0af  mov     edx, 51h ; 'Q'; void *
0x1800cf0b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cf0ba  lea     rdx, [rbp+57h+var_80]
0x1800cf0be  mov     rcx, rbx
0x1800cf0c1  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800cf0c6  nop
0x1800cf0c7  lea     rcx, [rbp+57h+var_80]; this
0x1800cf0cb  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800cf0d0  nop
0x1800cf0d1  lea     rcx, [rbp+57h+var_C8]
0x1800cf0d5  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800cf0da  nop
0x1800cf0db  lea     rcx, [rbp+57h+var_C0]
0x1800cf0df  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800cf0e4  mov     rax, rbx
0x1800cf0e7  add     rsp, 0E8h
0x1800cf0ee  pop     r15
0x1800cf0f0  pop     r14
0x1800cf0f2  pop     rdi
0x1800cf0f3  pop     rsi
0x1800cf0f4  pop     rbx
0x1800cf0f5  pop     rbp
0x1800cf0f6  retn
```
