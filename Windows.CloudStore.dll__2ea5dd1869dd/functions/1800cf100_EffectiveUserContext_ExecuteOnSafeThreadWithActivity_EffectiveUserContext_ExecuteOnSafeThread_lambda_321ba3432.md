# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_321ba3432076d86253fe4fb8349c1503_>(_lambda_321ba3432076d86253fe4fb8349c1503_ &&)'::`2'::NopActivity const,_lambda_321ba3432076d86253fe4fb8349c1503_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_321ba3432076d86253fe4fb8349c1503_>(_lambda_321ba3432076d86253fe4fb8349c1503_ &&)'::`2'::NopActivity const &,_lambda_321ba3432076d86253fe4fb8349c1503_ &)

- ea: `0x1800cf100`
- end: `0x1800cf317`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_321ba3432076d86253fe4fb8349c1503_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_321ba3432076d86253fe4fb8349c1503_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_321ba3432076d86253fe4fb8349c1503_@@@0@QEBAX$$QEAV_lambda_321ba3432076d86253fe4fb8349c1503_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18017fd50`

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
- `0x1800cf100`
- `0x1800e93e0`
- `0x1801809d4`
- `0x180181890`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800cf1c7`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800cf1c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf1ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf1ad`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cf136`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800cf136`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cf29b`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cf29b`

## string_xrefs

- `0x1800cf14b`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cf1ef`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cf2ac`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cf2c8`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_321ba3432076d86253fe4fb8349c1503_>'::`2'::NopActivity const,AX$$QEAV_lambda_321ba3432076d86253fe4fb8349c1503_ const * const>(
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
      _lambda_321ba3432076d86253fe4fb8349c1503_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_4737f7eaabf3e2dd219c6693f5274943_ &>,_lambda_4737f7eaabf3e2dd219c6693f5274943_ &>(
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
0x1800cf100  push    rbp
0x1800cf102  push    rbx
0x1800cf103  push    rsi
0x1800cf104  push    rdi
0x1800cf105  push    r14
0x1800cf107  push    r15
0x1800cf109  lea     rbp, [rsp-2Fh]
0x1800cf10e  sub     rsp, 0E8h
0x1800cf115  mov     rdi, r9
0x1800cf118  mov     rsi, r8
0x1800cf11b  mov     rbx, rdx
0x1800cf11e  mov     r14, rcx
0x1800cf121  xor     r15d, r15d
0x1800cf124  mov     [rsp+110h+pAptType], r15d
0x1800cf129  mov     [rbp+57h+pAptQualifier], r15d
0x1800cf12d  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800cf131  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800cf136  call    cs:__imp_CoGetApartmentType
0x1800cf13c  mov     rcx, [rbp+5Fh]; this
0x1800cf140  test    eax, eax
0x1800cf142  jns     loc_1800CF201
0x1800cf148  mov     r9d, eax; char *
0x1800cf14b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cf152  lea     edx, [r15+29h]; void *
0x1800cf156  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cf15b  lea     rcx, [rbp+57h+var_C0]
0x1800cf15f  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800cf164  nop
0x1800cf165  mov     [rbp+57h+var_C8], r15
0x1800cf169  mov     [rbp+57h+var_B0], r14
0x1800cf16d  mov     [rbp+57h+var_A8], rsi
0x1800cf171  mov     [rbp+57h+var_A0], rdi
0x1800cf175  lea     rax, [rbp+57h+var_C8]
0x1800cf179  mov     [rbp+57h+var_98], rax
0x1800cf17d  lea     rax, [rbp+57h+var_C0]
0x1800cf181  mov     [rbp+57h+var_90], rax
0x1800cf185  lea     rdx, [rbp+57h+var_B0]
0x1800cf189  lea     rcx, [rsp+110h+var_D8]
0x1800cf18e  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_4737f7eaabf3e2dd219c6693f5274943_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_4737f7eaabf3e2dd219c6693f5274943_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_4737f7eaabf3e2dd219c6693f5274943_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_4737f7eaabf3e2dd219c6693f5274943_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_4737f7eaabf3e2dd219c6693f5274943_ &>,_lambda_4737f7eaabf3e2dd219c6693f5274943_ &>(_lambda_4737f7eaabf3e2dd219c6693f5274943_ &)
0x1800cf193  mov     rdi, [rax]
0x1800cf196  mov     [rax], r15
0x1800cf199  mov     rcx, [rsp+110h+var_D8]
0x1800cf19e  test    rcx, rcx
0x1800cf1a1  jz      short loc_1800CF1AD
0x1800cf1a3  mov     [rsp+110h+var_D8], r15
0x1800cf1a8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800cf1ad  call    cs:__imp_GetCurrentThreadId
0x1800cf1b3  mov     [rsp+110h+var_E8], r15
0x1800cf1b8  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800cf1bd  xor     r9d, r9d
0x1800cf1c0  mov     r8d, eax
0x1800cf1c3  xor     edx, edx
0x1800cf1c5  xor     ecx, ecx
0x1800cf1c7  call    cs:__imp_SHTaskPoolQueueTask
0x1800cf1cd  mov     esi, eax
0x1800cf1cf  test    rdi, rdi
0x1800cf1d2  jz      short loc_1800CF1E4
0x1800cf1d4  mov     rdx, [rdi]
0x1800cf1d7  mov     rcx, rdi
0x1800cf1da  mov     rax, [rdx+10h]
0x1800cf1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf1e3  nop
0x1800cf1e4  mov     rcx, [rbp+5Fh]; this
0x1800cf1e8  test    esi, esi
0x1800cf1ea  jns     short loc_1800CF25A
0x1800cf1ec  mov     r9d, esi; char *
0x1800cf1ef  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cf1f6  mov     edx, 46h ; 'F'; void *
0x1800cf1fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cf201  mov     eax, [rsp+110h+pAptType]
0x1800cf205  test    eax, eax
0x1800cf207  jz      loc_1800CF15B
0x1800cf20d  cmp     eax, 3
0x1800cf210  jz      loc_1800CF15B
0x1800cf216  lea     rcx, [rsp+110h+var_D8]
0x1800cf21b  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cf220  nop
0x1800cf221  mov     rcx, rdi
0x1800cf224  call    ??R_lambda_321ba3432076d86253fe4fb8349c1503_@@QEBA@XZ; _lambda_321ba3432076d86253fe4fb8349c1503_::operator()(void)
0x1800cf229  xorps   xmm0, xmm0
0x1800cf22c  movups  xmmword ptr [rbx], xmm0
0x1800cf22f  movups  xmmword ptr [rbx+10h], xmm0
0x1800cf233  mov     [rbx+20h], r15
0x1800cf237  mov     [rbx+28h], r15
0x1800cf23b  mov     [rbx+30h], r15
0x1800cf23f  mov     [rbx+38h], r15d
0x1800cf243  mov     [rbx+40h], r15
0x1800cf247  mov     [rbx+48h], r15b
0x1800cf24b  lea     rcx, [rsp+110h+var_D8]
0x1800cf250  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800cf255  jmp     loc_1800CF304
0x1800cf25a  mov     rcx, [rbp+57h+var_C0]
0x1800cf25e  mov     rax, [rcx]
0x1800cf261  xor     edx, edx
0x1800cf263  mov     rax, [rax+10h]
0x1800cf267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf26c  mov     edi, eax
0x1800cf26e  xorps   xmm0, xmm0
0x1800cf271  movups  [rbp+57h+var_80], xmm0
0x1800cf275  movups  [rbp+57h+var_70], xmm0
0x1800cf279  movdqa  [rbp+57h+var_60], xmm0
0x1800cf27e  mov     [rbp+57h+var_50], r15
0x1800cf282  mov     [rbp+57h+var_48], r15d
0x1800cf286  mov     [rbp+57h+var_40], r15
0x1800cf28a  mov     [rbp+57h+var_38], r15b
0x1800cf28e  test    eax, eax
0x1800cf290  jns     short loc_1800CF2BD
0x1800cf292  mov     rcx, [rbp+57h+var_C8]
0x1800cf296  test    rcx, rcx
0x1800cf299  jz      short loc_1800CF2BD
0x1800cf29b  call    cs:__imp_SetRestrictedErrorInfo
0x1800cf2a1  mov     rcx, [rbp+5Fh]; this
0x1800cf2a5  test    eax, eax
0x1800cf2a7  jns     short loc_1800CF2BD
0x1800cf2a9  mov     r9d, eax; char *
0x1800cf2ac  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cf2b3  mov     edx, 4Fh ; 'O'; void *
0x1800cf2b8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cf2bd  mov     rcx, [rbp+5Fh]; this
0x1800cf2c1  test    edi, edi
0x1800cf2c3  jns     short loc_1800CF2DA
0x1800cf2c5  mov     r9d, edi; char *
0x1800cf2c8  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cf2cf  mov     edx, 51h ; 'Q'; void *
0x1800cf2d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cf2da  lea     rdx, [rbp+57h+var_80]
0x1800cf2de  mov     rcx, rbx
0x1800cf2e1  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800cf2e6  nop
0x1800cf2e7  lea     rcx, [rbp+57h+var_80]; this
0x1800cf2eb  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800cf2f0  nop
0x1800cf2f1  lea     rcx, [rbp+57h+var_C8]
0x1800cf2f5  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800cf2fa  nop
0x1800cf2fb  lea     rcx, [rbp+57h+var_C0]
0x1800cf2ff  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800cf304  mov     rax, rbx
0x1800cf307  add     rsp, 0E8h
0x1800cf30e  pop     r15
0x1800cf310  pop     r14
0x1800cf312  pop     rdi
0x1800cf313  pop     rsi
0x1800cf314  pop     rbx
0x1800cf315  pop     rbp
0x1800cf316  retn
```
