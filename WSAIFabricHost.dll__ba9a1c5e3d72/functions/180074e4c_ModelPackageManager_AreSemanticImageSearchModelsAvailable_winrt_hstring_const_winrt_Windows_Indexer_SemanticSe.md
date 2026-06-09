# ModelPackageManager::AreSemanticImageSearchModelsAvailable(winrt::hstring const &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexCreationDisposition)

- ea: `0x180074e4c`
- end: `0x18007505f`
- name: `?AreSemanticImageSearchModelsAvailable@ModelPackageManager@@SA_NAEBUhstring@winrt@@W4SemanticIndexCreationDisposition@SemanticSearch@Indexer@Windows@3@@Z`
- size: `531`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ab30`
- `0x18001b430`
- `0x180076ec0`

## callees

- `0x180008f84`
- `0x18000c478`
- `0x180019c3c`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x18003cf0c`
- `0x18004ba10`
- `0x18004dea8`
- `0x180074048`
- `0x180074e4c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074fb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074fb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074ebb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074f87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074ebb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074f87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074fe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074fe3`

## string_xrefs

- `0x18007503f`: `onecoreuap\base\appmodel\Search\common\AIFabricHostHelper\include\Utils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ModelPackageManager::AreSemanticImageSearchModelsAvailable(__int64 a1, int a2)
{
  int v2; // edx
  __int64 v3; // r8
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  int v5; // eax
  char v6; // si
  _DWORD *v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  const char *v10; // r9
  char result; // al
  const char *v12; // r9
  const char *v13; // [rsp+28h] [rbp-80h]
  int v14; // [rsp+38h] [rbp-70h] BYREF
  __int128 v15; // [rsp+40h] [rbp-68h]
  _BYTE v16[8]; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v17[48]; // [rsp+58h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  char v20; // [rsp+B8h] [rbp+10h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+18h] BYREF
  __int64 *v22; // [rsp+C8h] [rbp+20h] BYREF

  try
  {
    if ( a2 )
    {
      v2 = a2 - 1;
      if ( v2 )
      {
        if ( v2 != 1 )
        {
          v12 = (const char *)(unsigned int)wil::verify_hresult(2147549183LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x20,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\Utils.h",
            v12,
            (int)"Unexpected disposition.",
            v13);
        }
        v3 = 2;
      }
      else
      {
        v3 = 1;
      }
    }
    else
    {
      v3 = 0;
    }
    Utils::GetSemanticImageIndexStoreOptions(&v21, a1, v3);
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v16);
    v4 = (struct _RTL_CRITICAL_SECTION *)pv;
    v22 = (__int64 *)pv;
    if ( pv )
      _InterlockedIncrement((volatile signed __int32 *)pv + 72);
    EnterCriticalSection(v4 + 5);
    ++LODWORD(v4[6].DebugInfo);
    LODWORD(v4[6].SpinCount) = 21;
    tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>((struct _RTL_CRITICAL_SECTION **)&v22);
    v22 = &v21;
    _InterlockedIncrement64(&qword_1800AF658);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> )
    {
      v20 = 0;
      v14 = 0;
      v15 = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>
                                                               + 48LL))(
             winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>,
             v21,
             &v20);
      if ( v5 < 0 )
        winrt::throw_hresult((unsigned int)v5, &v14);
      v6 = v20;
      _InterlockedDecrement64(&qword_1800AF658);
    }
    else
    {
      _InterlockedDecrement64(&qword_1800AF658);
      v6 = winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::call<_lambda_ccaef61b38c6059ad3a532d50ed151f8_ &>(
             0,
             &v22);
    }
    v7 = pv;
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    v7[18] |= 0x300u;
    if ( *((_QWORD *)v7 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper(v7 + 2, 2);
    if ( v8 )
      LeaveCriticalSection(v8);
    v9 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v9);
      CoTaskMemFree(v9);
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v17);
    if ( v21 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v21);
    result = v6;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
      v10);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180074e4c  push    rbx
0x180074e4e  push    rsi
0x180074e4f  push    rdi
0x180074e50  sub     rsp, 90h
0x180074e57  test    edx, edx
0x180074e59  jz      short loc_180074E79
0x180074e5b  sub     edx, 1
0x180074e5e  jz      short loc_180074E71
0x180074e60  cmp     edx, 1
0x180074e63  jnz     loc_18007501E
0x180074e69  mov     r8d, 2
0x180074e6f  jmp     short loc_180074E7C
0x180074e71  mov     r8d, 1
0x180074e77  jmp     short loc_180074E7C
0x180074e79  xor     r8d, r8d
0x180074e7c  mov     rdx, rcx
0x180074e7f  lea     rcx, [rsp+0A8h+arg_10]
0x180074e87  call    ?GetSemanticImageIndexStoreOptions@Utils@@YA?AUSemanticImageIndexStoreOptions@SemanticSearch@Windows@Microsoft@winrt@@AEBUhstring@6@W4IndexCreationDisposition@3456@@Z; Utils::GetSemanticImageIndexStoreOptions(winrt::hstring const &,winrt::Microsoft::Windows::SemanticSearch::IndexCreationDisposition)
0x180074e8c  nop
0x180074e8d  lea     rcx, [rsp+0A8h+var_58]
0x180074e92  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180074e97  nop
0x180074e98  mov     rbx, [rsp+0A8h+pv]
0x180074ea0  mov     [rsp+0A8h+arg_18], rbx
0x180074ea8  test    rbx, rbx
0x180074eab  jz      short loc_180074EB4
0x180074ead  lock inc dword ptr [rbx+120h]
0x180074eb4  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180074ebb  call    cs:__imp_EnterCriticalSection
0x180074ec1  inc     dword ptr [rbx+0F0h]
0x180074ec7  mov     dword ptr [rbx+110h], 15h
0x180074ed1  lea     rcx, [rsp+0A8h+arg_18]
0x180074ed9  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180074ede  lea     rax, [rsp+0A8h+arg_10]
0x180074ee6  mov     [rsp+0A8h+arg_18], rax
0x180074eee  lea     rax, qword_1800AF658
0x180074ef5  mov     [rsp+0A8h+var_78], rax
0x180074efa  lock inc cs:qword_1800AF658
0x180074f02  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>
0x180074f09  test    rcx, rcx
0x180074f0c  jz      short loc_180074F5D
0x180074f0e  mov     [rsp+0A8h+arg_8], 0
0x180074f16  mov     [rsp+0A8h+var_70], 0
0x180074f1e  xorps   xmm0, xmm0
0x180074f21  movdqu  [rsp+0A8h+var_68], xmm0
0x180074f27  mov     rax, [rcx]
0x180074f2a  lea     r8, [rsp+0A8h+arg_8]
0x180074f32  mov     rdx, [rsp+0A8h+arg_10]
0x180074f3a  mov     rax, [rax+30h]
0x180074f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074f43  test    eax, eax
0x180074f45  js      loc_180075051
0x180074f4b  mov     sil, [rsp+0A8h+arg_8]
0x180074f53  lock dec cs:qword_1800AF658
0x180074f5b  jmp     short loc_180074F75
0x180074f5d  lock dec cs:qword_1800AF658
0x180074f65  lea     rdx, [rsp+0A8h+arg_18]
0x180074f6d  call    ??$call@AEAV_lambda_ccaef61b38c6059ad3a532d50ed151f8_@@@?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_ccaef61b38c6059ad3a532d50ed151f8_@@@Z
0x180074f72  mov     sil, al
0x180074f75  mov     rbx, [rsp+0A8h+pv]
0x180074f7d  lea     rdi, [rbx+0C8h]
0x180074f84  mov     rcx, rdi; lpCriticalSection
0x180074f87  call    cs:__imp_EnterCriticalSection
0x180074f8d  or      dword ptr [rbx+48h], 300h
0x180074f94  cmp     qword ptr [rbx+0F8h], 0
0x180074f9c  jz      short loc_180074FAC
0x180074f9e  mov     edx, 2
0x180074fa3  lea     rcx, [rbx+8]
0x180074fa7  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180074fac  test    rdi, rdi
0x180074faf  jz      short loc_180074FBB
0x180074fb1  mov     rcx, rdi; lpCriticalSection
0x180074fb4  call    cs:__imp_LeaveCriticalSection
0x180074fba  nop
0x180074fbb  mov     rbx, [rsp+0A8h+pv]
0x180074fc3  test    rbx, rbx
0x180074fc6  jz      short loc_180074FE9
0x180074fc8  or      eax, 0FFFFFFFFh
0x180074fcb  lock xadd [rbx+120h], eax
0x180074fd3  cmp     eax, 1
0x180074fd6  jnz     short loc_180074FE9
0x180074fd8  mov     rcx, rbx
0x180074fdb  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180074fe0  mov     rcx, rbx; pv
0x180074fe3  call    cs:__imp_CoTaskMemFree
0x180074fe9  lea     rcx, [rsp+0A8h+var_50]; this
0x180074fee  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180074ff3  nop
0x180074ff4  cmp     [rsp+0A8h+arg_10], 0
0x180074ffd  jz      short loc_18007500C
0x180074fff  lea     rcx, [rsp+0A8h+arg_10]
0x180075007  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18007500c  mov     al, sil
0x18007500f  jmp     short loc_180075013
0x180075011  xor     al, al
0x180075013  add     rsp, 90h
0x18007501a  pop     rdi
0x18007501b  pop     rsi
0x18007501c  pop     rbx
0x18007501d  retn
0x18007501e  mov     ecx, 8000FFFFh
0x180075023  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180075028  mov     r9d, eax; char *
0x18007502b  mov     rcx, [rsp+0A8h]; this
0x180075033  lea     rax, aUnexpectedDisp; "Unexpected disposition."
0x18007503a  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18007503f  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180075046  mov     edx, 20h ; ' '; void *
0x18007504b  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180075051  lea     rdx, [rsp+0A8h+var_70]
0x180075056  mov     ecx, eax
0x180075058  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
