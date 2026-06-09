# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_3cd0db17946d540aabfc59ef6dc86937_>(_lambda_3cd0db17946d540aabfc59ef6dc86937_ &&)'::`2'::NopActivity const,_lambda_3cd0db17946d540aabfc59ef6dc86937_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_3cd0db17946d540aabfc59ef6dc86937_>(_lambda_3cd0db17946d540aabfc59ef6dc86937_ &&)'::`2'::NopActivity const &,_lambda_3cd0db17946d540aabfc59ef6dc86937_ &)

- ea: `0x18017e484`
- end: `0x18017e69b`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_3cd0db17946d540aabfc59ef6dc86937_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_3cd0db17946d540aabfc59ef6dc86937_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_3cd0db17946d540aabfc59ef6dc86937_@@@0@QEBAX$$QEAV_lambda_3cd0db17946d540aabfc59ef6dc86937_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180180034`

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
- `0x18017e484`
- `0x1801807e8`
- `0x180181ad0`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x18017e54b`
- `SHCORE!SHTaskPoolQueueTask` at `0x18017e54b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017e531`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18017e531`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017e4ba`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18017e4ba`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017e61f`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18017e61f`

## string_xrefs

- `0x18017e4cf`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017e573`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017e630`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x18017e64c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_3cd0db17946d540aabfc59ef6dc86937_>'::`2'::NopActivity const,AX$$QEAV_lambda_3cd0db17946d540aabfc59ef6dc86937_ const * const>(
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
      _lambda_3cd0db17946d540aabfc59ef6dc86937_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_3f40b81cbdddf3e3220f9cad0709fc3d_ &>,_lambda_3f40b81cbdddf3e3220f9cad0709fc3d_ &>(
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
0x18017e484  push    rbp
0x18017e486  push    rbx
0x18017e487  push    rsi
0x18017e488  push    rdi
0x18017e489  push    r14
0x18017e48b  push    r15
0x18017e48d  lea     rbp, [rsp-2Fh]
0x18017e492  sub     rsp, 0E8h
0x18017e499  mov     rdi, r9
0x18017e49c  mov     rsi, r8
0x18017e49f  mov     rbx, rdx
0x18017e4a2  mov     r14, rcx
0x18017e4a5  xor     r15d, r15d
0x18017e4a8  mov     [rsp+110h+pAptType], r15d
0x18017e4ad  mov     [rbp+57h+pAptQualifier], r15d
0x18017e4b1  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x18017e4b5  lea     rcx, [rsp+110h+pAptType]; pAptType
0x18017e4ba  call    cs:__imp_CoGetApartmentType
0x18017e4c0  mov     rcx, [rbp+5Fh]; this
0x18017e4c4  test    eax, eax
0x18017e4c6  jns     loc_18017E585
0x18017e4cc  mov     r9d, eax; char *
0x18017e4cf  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e4d6  lea     edx, [r15+29h]; void *
0x18017e4da  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017e4df  lea     rcx, [rbp+57h+var_C0]
0x18017e4e3  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x18017e4e8  nop
0x18017e4e9  mov     [rbp+57h+var_C8], r15
0x18017e4ed  mov     [rbp+57h+var_B0], r14
0x18017e4f1  mov     [rbp+57h+var_A8], rsi
0x18017e4f5  mov     [rbp+57h+var_A0], rdi
0x18017e4f9  lea     rax, [rbp+57h+var_C8]
0x18017e4fd  mov     [rbp+57h+var_98], rax
0x18017e501  lea     rax, [rbp+57h+var_C0]
0x18017e505  mov     [rbp+57h+var_90], rax
0x18017e509  lea     rdx, [rbp+57h+var_B0]
0x18017e50d  lea     rcx, [rsp+110h+var_D8]
0x18017e512  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_3f40b81cbdddf3e3220f9cad0709fc3d_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_3f40b81cbdddf3e3220f9cad0709fc3d_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_3f40b81cbdddf3e3220f9cad0709fc3d_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_3f40b81cbdddf3e3220f9cad0709fc3d_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_3f40b81cbdddf3e3220f9cad0709fc3d_ &>,_lambda_3f40b81cbdddf3e3220f9cad0709fc3d_ &>(_lambda_3f40b81cbdddf3e3220f9cad0709fc3d_ &)
0x18017e517  mov     rdi, [rax]
0x18017e51a  mov     [rax], r15
0x18017e51d  mov     rcx, [rsp+110h+var_D8]
0x18017e522  test    rcx, rcx
0x18017e525  jz      short loc_18017E531
0x18017e527  mov     [rsp+110h+var_D8], r15
0x18017e52c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18017e531  call    cs:__imp_GetCurrentThreadId
0x18017e537  mov     [rsp+110h+var_E8], r15
0x18017e53c  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x18017e541  xor     r9d, r9d
0x18017e544  mov     r8d, eax
0x18017e547  xor     edx, edx
0x18017e549  xor     ecx, ecx
0x18017e54b  call    cs:__imp_SHTaskPoolQueueTask
0x18017e551  mov     esi, eax
0x18017e553  test    rdi, rdi
0x18017e556  jz      short loc_18017E568
0x18017e558  mov     rdx, [rdi]
0x18017e55b  mov     rcx, rdi
0x18017e55e  mov     rax, [rdx+10h]
0x18017e562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e567  nop
0x18017e568  mov     rcx, [rbp+5Fh]; this
0x18017e56c  test    esi, esi
0x18017e56e  jns     short loc_18017E5DE
0x18017e570  mov     r9d, esi; char *
0x18017e573  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e57a  mov     edx, 46h ; 'F'; void *
0x18017e57f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e585  mov     eax, [rsp+110h+pAptType]
0x18017e589  test    eax, eax
0x18017e58b  jz      loc_18017E4DF
0x18017e591  cmp     eax, 3
0x18017e594  jz      loc_18017E4DF
0x18017e59a  lea     rcx, [rsp+110h+var_D8]
0x18017e59f  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x18017e5a4  nop
0x18017e5a5  mov     rcx, rdi
0x18017e5a8  call    ??R_lambda_3cd0db17946d540aabfc59ef6dc86937_@@QEBA@XZ; _lambda_3cd0db17946d540aabfc59ef6dc86937_::operator()(void)
0x18017e5ad  xorps   xmm0, xmm0
0x18017e5b0  movups  xmmword ptr [rbx], xmm0
0x18017e5b3  movups  xmmword ptr [rbx+10h], xmm0
0x18017e5b7  mov     [rbx+20h], r15
0x18017e5bb  mov     [rbx+28h], r15
0x18017e5bf  mov     [rbx+30h], r15
0x18017e5c3  mov     [rbx+38h], r15d
0x18017e5c7  mov     [rbx+40h], r15
0x18017e5cb  mov     [rbx+48h], r15b
0x18017e5cf  lea     rcx, [rsp+110h+var_D8]
0x18017e5d4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18017e5d9  jmp     loc_18017E688
0x18017e5de  mov     rcx, [rbp+57h+var_C0]
0x18017e5e2  mov     rax, [rcx]
0x18017e5e5  xor     edx, edx
0x18017e5e7  mov     rax, [rax+10h]
0x18017e5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e5f0  mov     edi, eax
0x18017e5f2  xorps   xmm0, xmm0
0x18017e5f5  movups  [rbp+57h+var_80], xmm0
0x18017e5f9  movups  [rbp+57h+var_70], xmm0
0x18017e5fd  movdqa  [rbp+57h+var_60], xmm0
0x18017e602  mov     [rbp+57h+var_50], r15
0x18017e606  mov     [rbp+57h+var_48], r15d
0x18017e60a  mov     [rbp+57h+var_40], r15
0x18017e60e  mov     [rbp+57h+var_38], r15b
0x18017e612  test    eax, eax
0x18017e614  jns     short loc_18017E641
0x18017e616  mov     rcx, [rbp+57h+var_C8]
0x18017e61a  test    rcx, rcx
0x18017e61d  jz      short loc_18017E641
0x18017e61f  call    cs:__imp_SetRestrictedErrorInfo
0x18017e625  mov     rcx, [rbp+5Fh]; this
0x18017e629  test    eax, eax
0x18017e62b  jns     short loc_18017E641
0x18017e62d  mov     r9d, eax; char *
0x18017e630  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e637  mov     edx, 4Fh ; 'O'; void *
0x18017e63c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017e641  mov     rcx, [rbp+5Fh]; this
0x18017e645  test    edi, edi
0x18017e647  jns     short loc_18017E65E
0x18017e649  mov     r9d, edi; char *
0x18017e64c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18017e653  mov     edx, 51h ; 'Q'; void *
0x18017e658  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017e65e  lea     rdx, [rbp+57h+var_80]
0x18017e662  mov     rcx, rbx
0x18017e665  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x18017e66a  nop
0x18017e66b  lea     rcx, [rbp+57h+var_80]; this
0x18017e66f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18017e674  nop
0x18017e675  lea     rcx, [rbp+57h+var_C8]
0x18017e679  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18017e67e  nop
0x18017e67f  lea     rcx, [rbp+57h+var_C0]
0x18017e683  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x18017e688  mov     rax, rbx
0x18017e68b  add     rsp, 0E8h
0x18017e692  pop     r15
0x18017e694  pop     r14
0x18017e696  pop     rdi
0x18017e697  pop     rsi
0x18017e698  pop     rbx
0x18017e699  pop     rbp
0x18017e69a  retn
```
