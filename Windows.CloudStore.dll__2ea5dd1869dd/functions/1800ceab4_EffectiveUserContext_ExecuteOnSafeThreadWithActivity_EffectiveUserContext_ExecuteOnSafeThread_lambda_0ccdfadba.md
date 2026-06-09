# EffectiveUserContext::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_0ccdfadba8355924fd4b46f478e83c09_>(_lambda_0ccdfadba8355924fd4b46f478e83c09_ &&)'::`2'::NopActivity const,_lambda_0ccdfadba8355924fd4b46f478e83c09_ &>(`EffectiveUserContext::ExecuteOnSafeThread<_lambda_0ccdfadba8355924fd4b46f478e83c09_>(_lambda_0ccdfadba8355924fd4b46f478e83c09_ &&)'::`2'::NopActivity const &,_lambda_0ccdfadba8355924fd4b46f478e83c09_ &)

- ea: `0x1800ceab4`
- end: `0x1800ceccb`
- name: `??$ExecuteOnSafeThreadWithActivity@$$CBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_0ccdfadba8355924fd4b46f478e83c09_@@@EffectiveUserContext@@QEBAX$$QEAV_lambda_0ccdfadba8355924fd4b46f478e83c09_@@@Z@AEAV3@@EffectiveUserContext@@QEBA?AVActivityThreadWatcher@wil@@AEBUNopActivity@?1???$ExecuteOnSafeThread@V_lambda_0ccdfadba8355924fd4b46f478e83c09_@@@0@QEBAX$$QEAV_lambda_0ccdfadba8355924fd4b46f478e83c09_@@@Z@AEAV4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180181f84`

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
- `0x1800ceab4`
- `0x1800e93e0`
- `0x18018103c`
- `0x1801817c0`
- `0x180208010`

## import_xrefs

- `SHCORE!SHTaskPoolQueueTask` at `0x1800ceb7b`
- `SHCORE!SHTaskPoolQueueTask` at `0x1800ceb7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ceb61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ceb61`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ceaea`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800ceaea`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cec4f`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x1800cec4f`

## string_xrefs

- `0x1800ceaff`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800ceba3`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cec60`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`
- `0x1800cec7c`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.h`

## pseudocode

```c
__int64 __fastcall AEAV3::Z::ExecuteOnSafeThreadWithActivity<`EffectiveUserContext::ExecuteOnSafeThread<_lambda_0ccdfadba8355924fd4b46f478e83c09_>'::`2'::NopActivity const,AX$$QEAV_lambda_0ccdfadba8355924fd4b46f478e83c09_ const * const>(
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
      _lambda_0ccdfadba8355924fd4b46f478e83c09_::operator()(a4);
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
  v9 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_a23c9ce87ff03278956e505124f262c8_ &>,_lambda_a23c9ce87ff03278956e505124f262c8_ &>(
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
0x1800ceab4  push    rbp
0x1800ceab6  push    rbx
0x1800ceab7  push    rsi
0x1800ceab8  push    rdi
0x1800ceab9  push    r14
0x1800ceabb  push    r15
0x1800ceabd  lea     rbp, [rsp-2Fh]
0x1800ceac2  sub     rsp, 0E8h
0x1800ceac9  mov     rdi, r9
0x1800ceacc  mov     rsi, r8
0x1800ceacf  mov     rbx, rdx
0x1800cead2  mov     r14, rcx
0x1800cead5  xor     r15d, r15d
0x1800cead8  mov     [rsp+110h+pAptType], r15d
0x1800ceadd  mov     [rbp+57h+pAptQualifier], r15d
0x1800ceae1  lea     rdx, [rbp+57h+pAptQualifier]; pAptQualifier
0x1800ceae5  lea     rcx, [rsp+110h+pAptType]; pAptType
0x1800ceaea  call    cs:__imp_CoGetApartmentType
0x1800ceaf0  mov     rcx, [rbp+5Fh]; this
0x1800ceaf4  test    eax, eax
0x1800ceaf6  jns     loc_1800CEBB5
0x1800ceafc  mov     r9d, eax; char *
0x1800ceaff  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800ceb06  lea     edx, [r15+29h]; void *
0x1800ceb0a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ceb0f  lea     rcx, [rbp+57h+var_C0]
0x1800ceb13  call    ?WaitForThreadResult_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$unique_ptr@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@U?$default_delete@VWaitForThreadResult@Core@Cloud@Storage@Internal@Windows@@@std@@@std@@XZ; Windows::Internal::Storage::Cloud::Core::WaitForThreadResult_CreateInstance(void)
0x1800ceb18  nop
0x1800ceb19  mov     [rbp+57h+var_C8], r15
0x1800ceb1d  mov     [rbp+57h+var_B0], r14
0x1800ceb21  mov     [rbp+57h+var_A8], rsi
0x1800ceb25  mov     [rbp+57h+var_A0], rdi
0x1800ceb29  lea     rax, [rbp+57h+var_C8]
0x1800ceb2d  mov     [rbp+57h+var_98], rax
0x1800ceb31  lea     rax, [rbp+57h+var_C0]
0x1800ceb35  mov     [rbp+57h+var_90], rax
0x1800ceb39  lea     rdx, [rbp+57h+var_B0]
0x1800ceb3d  lea     rcx, [rsp+110h+var_D8]
0x1800ceb42  call    ??$Make@V?$CTaskWrapper@AEAV_lambda_a23c9ce87ff03278956e505124f262c8_@@@ComTaskPool@Internal@Windows@@AEAV_lambda_a23c9ce87ff03278956e505124f262c8_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@AEAV_lambda_a23c9ce87ff03278956e505124f262c8_@@@ComTaskPool@Internal@Windows@@@12@AEAV_lambda_a23c9ce87ff03278956e505124f262c8_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_a23c9ce87ff03278956e505124f262c8_ &>,_lambda_a23c9ce87ff03278956e505124f262c8_ &>(_lambda_a23c9ce87ff03278956e505124f262c8_ &)
0x1800ceb47  mov     rdi, [rax]
0x1800ceb4a  mov     [rax], r15
0x1800ceb4d  mov     rcx, [rsp+110h+var_D8]
0x1800ceb52  test    rcx, rcx
0x1800ceb55  jz      short loc_1800CEB61
0x1800ceb57  mov     [rsp+110h+var_D8], r15
0x1800ceb5c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800ceb61  call    cs:__imp_GetCurrentThreadId
0x1800ceb67  mov     [rsp+110h+var_E8], r15
0x1800ceb6c  mov     qword ptr [rsp+110h+var_F0], rdi; int
0x1800ceb71  xor     r9d, r9d
0x1800ceb74  mov     r8d, eax
0x1800ceb77  xor     edx, edx
0x1800ceb79  xor     ecx, ecx
0x1800ceb7b  call    cs:__imp_SHTaskPoolQueueTask
0x1800ceb81  mov     esi, eax
0x1800ceb83  test    rdi, rdi
0x1800ceb86  jz      short loc_1800CEB98
0x1800ceb88  mov     rdx, [rdi]
0x1800ceb8b  mov     rcx, rdi
0x1800ceb8e  mov     rax, [rdx+10h]
0x1800ceb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ceb97  nop
0x1800ceb98  mov     rcx, [rbp+5Fh]; this
0x1800ceb9c  test    esi, esi
0x1800ceb9e  jns     short loc_1800CEC0E
0x1800ceba0  mov     r9d, esi; char *
0x1800ceba3  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cebaa  mov     edx, 46h ; 'F'; void *
0x1800cebaf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cebb5  mov     eax, [rsp+110h+pAptType]
0x1800cebb9  test    eax, eax
0x1800cebbb  jz      loc_1800CEB0F
0x1800cebc1  cmp     eax, 3
0x1800cebc4  jz      loc_1800CEB0F
0x1800cebca  lea     rcx, [rsp+110h+var_D8]
0x1800cebcf  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x1800cebd4  nop
0x1800cebd5  mov     rcx, rdi
0x1800cebd8  call    ??R_lambda_0ccdfadba8355924fd4b46f478e83c09_@@QEBA@XZ; _lambda_0ccdfadba8355924fd4b46f478e83c09_::operator()(void)
0x1800cebdd  xorps   xmm0, xmm0
0x1800cebe0  movups  xmmword ptr [rbx], xmm0
0x1800cebe3  movups  xmmword ptr [rbx+10h], xmm0
0x1800cebe7  mov     [rbx+20h], r15
0x1800cebeb  mov     [rbx+28h], r15
0x1800cebef  mov     [rbx+30h], r15
0x1800cebf3  mov     [rbx+38h], r15d
0x1800cebf7  mov     [rbx+40h], r15
0x1800cebfb  mov     [rbx+48h], r15b
0x1800cebff  lea     rcx, [rsp+110h+var_D8]
0x1800cec04  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800cec09  jmp     loc_1800CECB8
0x1800cec0e  mov     rcx, [rbp+57h+var_C0]
0x1800cec12  mov     rax, [rcx]
0x1800cec15  xor     edx, edx
0x1800cec17  mov     rax, [rax+10h]
0x1800cec1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cec20  mov     edi, eax
0x1800cec22  xorps   xmm0, xmm0
0x1800cec25  movups  [rbp+57h+var_80], xmm0
0x1800cec29  movups  [rbp+57h+var_70], xmm0
0x1800cec2d  movdqa  [rbp+57h+var_60], xmm0
0x1800cec32  mov     [rbp+57h+var_50], r15
0x1800cec36  mov     [rbp+57h+var_48], r15d
0x1800cec3a  mov     [rbp+57h+var_40], r15
0x1800cec3e  mov     [rbp+57h+var_38], r15b
0x1800cec42  test    eax, eax
0x1800cec44  jns     short loc_1800CEC71
0x1800cec46  mov     rcx, [rbp+57h+var_C8]
0x1800cec4a  test    rcx, rcx
0x1800cec4d  jz      short loc_1800CEC71
0x1800cec4f  call    cs:__imp_SetRestrictedErrorInfo
0x1800cec55  mov     rcx, [rbp+5Fh]; this
0x1800cec59  test    eax, eax
0x1800cec5b  jns     short loc_1800CEC71
0x1800cec5d  mov     r9d, eax; char *
0x1800cec60  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cec67  mov     edx, 4Fh ; 'O'; void *
0x1800cec6c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cec71  mov     rcx, [rbp+5Fh]; this
0x1800cec75  test    edi, edi
0x1800cec77  jns     short loc_1800CEC8E
0x1800cec79  mov     r9d, edi; char *
0x1800cec7c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800cec83  mov     edx, 51h ; 'Q'; void *
0x1800cec88  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cec8e  lea     rdx, [rbp+57h+var_80]
0x1800cec92  mov     rcx, rbx
0x1800cec95  call    ??0ActivityThreadWatcher@wil@@QEAA@$$QEAV01@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::ActivityThreadWatcher &&)
0x1800cec9a  nop
0x1800cec9b  lea     rcx, [rbp+57h+var_80]; this
0x1800cec9f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800ceca4  nop
0x1800ceca5  lea     rcx, [rbp+57h+var_C8]
0x1800ceca9  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800cecae  nop
0x1800cecaf  lea     rcx, [rbp+57h+var_C0]
0x1800cecb3  call    ??1?$unique_ptr@VPartitionMetadataFactory@@U?$default_delete@VPartitionMetadataFactory@@@std@@@std@@QEAA@XZ; std::unique_ptr<PartitionMetadataFactory>::~unique_ptr<PartitionMetadataFactory>(void)
0x1800cecb8  mov     rax, rbx
0x1800cecbb  add     rsp, 0E8h
0x1800cecc2  pop     r15
0x1800cecc4  pop     r14
0x1800cecc6  pop     rdi
0x1800cecc7  pop     rsi
0x1800cecc8  pop     rbx
0x1800cecc9  pop     rbp
0x1800cecca  retn
```
