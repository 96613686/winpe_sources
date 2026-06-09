# ModelPackageManager::AreSemanticTextSearchModelsAvailable(winrt::hstring const &,winrt::Windows::Indexer::SemanticSearch::SemanticIndexCreationDisposition)

- ea: `0x180075068`
- end: `0x18007527b`
- name: `?AreSemanticTextSearchModelsAvailable@ModelPackageManager@@SA_NAEBUhstring@winrt@@W4SemanticIndexCreationDisposition@SemanticSearch@Indexer@Windows@3@@Z`
- size: `531`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001abd0`
- `0x18001bde0`
- `0x180077570`

## callees

- `0x180008f84`
- `0x18000c478`
- `0x180019c3c`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x18003d008`
- `0x18004ba10`
- `0x18004dea8`
- `0x1800741c4`
- `0x180075068`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800751d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800751d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800750d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800751a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800750d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800751a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800751ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800751ff`

## string_xrefs

- `0x18007525b`: `onecoreuap\base\appmodel\Search\common\AIFabricHostHelper\include\Utils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ModelPackageManager::AreSemanticTextSearchModelsAvailable(__int64 a1, int a2)
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
    Utils::GetSemanticTextIndexStoreOptions(&v21, a1, v3);
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v16);
    v4 = (struct _RTL_CRITICAL_SECTION *)pv;
    v22 = (__int64 *)pv;
    if ( pv )
      _InterlockedIncrement((volatile signed __int32 *)pv + 72);
    EnterCriticalSection(v4 + 5);
    ++LODWORD(v4[6].DebugInfo);
    LODWORD(v4[6].SpinCount) = 20;
    tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>((struct _RTL_CRITICAL_SECTION **)&v22);
    v22 = &v21;
    _InterlockedIncrement64(&qword_1800AF6D8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics> )
    {
      v20 = 0;
      v14 = 0;
      v15 = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>
                                                               + 48LL))(
             winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>,
             v21,
             &v20);
      if ( v5 < 0 )
        winrt::throw_hresult((unsigned int)v5, &v14);
      v6 = v20;
      _InterlockedDecrement64(&qword_1800AF6D8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1800AF6D8);
      v6 = winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>::call<_lambda_d3c3ea3528af8ff6d2cd2420d1deeb84_ &>(
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
      (void *)0x136,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
      v10);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180075068  push    rbx
0x18007506a  push    rsi
0x18007506b  push    rdi
0x18007506c  sub     rsp, 90h
0x180075073  test    edx, edx
0x180075075  jz      short loc_180075095
0x180075077  sub     edx, 1
0x18007507a  jz      short loc_18007508D
0x18007507c  cmp     edx, 1
0x18007507f  jnz     loc_18007523A
0x180075085  mov     r8d, 2
0x18007508b  jmp     short loc_180075098
0x18007508d  mov     r8d, 1
0x180075093  jmp     short loc_180075098
0x180075095  xor     r8d, r8d
0x180075098  mov     rdx, rcx
0x18007509b  lea     rcx, [rsp+0A8h+arg_10]
0x1800750a3  call    ?GetSemanticTextIndexStoreOptions@Utils@@YA?AUSemanticTextIndexStoreOptions@SemanticSearch@Windows@Microsoft@winrt@@AEBUhstring@6@W4IndexCreationDisposition@3456@@Z; Utils::GetSemanticTextIndexStoreOptions(winrt::hstring const &,winrt::Microsoft::Windows::SemanticSearch::IndexCreationDisposition)
0x1800750a8  nop
0x1800750a9  lea     rcx, [rsp+0A8h+var_58]
0x1800750ae  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1800750b3  nop
0x1800750b4  mov     rbx, [rsp+0A8h+pv]
0x1800750bc  mov     [rsp+0A8h+arg_18], rbx
0x1800750c4  test    rbx, rbx
0x1800750c7  jz      short loc_1800750D0
0x1800750c9  lock inc dword ptr [rbx+120h]
0x1800750d0  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800750d7  call    cs:__imp_EnterCriticalSection
0x1800750dd  inc     dword ptr [rbx+0F0h]
0x1800750e3  mov     dword ptr [rbx+110h], 14h
0x1800750ed  lea     rcx, [rsp+0A8h+arg_18]
0x1800750f5  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x1800750fa  lea     rax, [rsp+0A8h+arg_10]
0x180075102  mov     [rsp+0A8h+arg_18], rax
0x18007510a  lea     rax, qword_1800AF6D8
0x180075111  mov     [rsp+0A8h+var_78], rax
0x180075116  lock inc cs:qword_1800AF6D8
0x18007511e  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>
0x180075125  test    rcx, rcx
0x180075128  jz      short loc_180075179
0x18007512a  mov     [rsp+0A8h+arg_8], 0
0x180075132  mov     [rsp+0A8h+var_70], 0
0x18007513a  xorps   xmm0, xmm0
0x18007513d  movdqu  [rsp+0A8h+var_68], xmm0
0x180075143  mov     rax, [rcx]
0x180075146  lea     r8, [rsp+0A8h+arg_8]
0x18007514e  mov     rdx, [rsp+0A8h+arg_10]
0x180075156  mov     rax, [rax+30h]
0x18007515a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007515f  test    eax, eax
0x180075161  js      loc_18007526D
0x180075167  mov     sil, [rsp+0A8h+arg_8]
0x18007516f  lock dec cs:qword_1800AF6D8
0x180075177  jmp     short loc_180075191
0x180075179  lock dec cs:qword_1800AF6D8
0x180075181  lea     rdx, [rsp+0A8h+arg_18]
0x180075189  call    ??$call@AEAV_lambda_d3c3ea3528af8ff6d2cd2420d1deeb84_@@@?$factory_cache_entry@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_d3c3ea3528af8ff6d2cd2420d1deeb84_@@@Z
0x18007518e  mov     sil, al
0x180075191  mov     rbx, [rsp+0A8h+pv]
0x180075199  lea     rdi, [rbx+0C8h]
0x1800751a0  mov     rcx, rdi; lpCriticalSection
0x1800751a3  call    cs:__imp_EnterCriticalSection
0x1800751a9  or      dword ptr [rbx+48h], 300h
0x1800751b0  cmp     qword ptr [rbx+0F8h], 0
0x1800751b8  jz      short loc_1800751C8
0x1800751ba  mov     edx, 2
0x1800751bf  lea     rcx, [rbx+8]
0x1800751c3  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800751c8  test    rdi, rdi
0x1800751cb  jz      short loc_1800751D7
0x1800751cd  mov     rcx, rdi; lpCriticalSection
0x1800751d0  call    cs:__imp_LeaveCriticalSection
0x1800751d6  nop
0x1800751d7  mov     rbx, [rsp+0A8h+pv]
0x1800751df  test    rbx, rbx
0x1800751e2  jz      short loc_180075205
0x1800751e4  or      eax, 0FFFFFFFFh
0x1800751e7  lock xadd [rbx+120h], eax
0x1800751ef  cmp     eax, 1
0x1800751f2  jnz     short loc_180075205
0x1800751f4  mov     rcx, rbx
0x1800751f7  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x1800751fc  mov     rcx, rbx; pv
0x1800751ff  call    cs:__imp_CoTaskMemFree
0x180075205  lea     rcx, [rsp+0A8h+var_50]; this
0x18007520a  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18007520f  nop
0x180075210  cmp     [rsp+0A8h+arg_10], 0
0x180075219  jz      short loc_180075228
0x18007521b  lea     rcx, [rsp+0A8h+arg_10]
0x180075223  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180075228  mov     al, sil
0x18007522b  jmp     short loc_18007522F
0x18007522d  xor     al, al
0x18007522f  add     rsp, 90h
0x180075236  pop     rdi
0x180075237  pop     rsi
0x180075238  pop     rbx
0x180075239  retn
0x18007523a  mov     ecx, 8000FFFFh
0x18007523f  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180075244  mov     r9d, eax; char *
0x180075247  mov     rcx, [rsp+0A8h]; this
0x18007524f  lea     rax, aUnexpectedDisp; "Unexpected disposition."
0x180075256  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x18007525b  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180075262  mov     edx, 20h ; ' '; void *
0x180075267  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007526d  lea     rdx, [rsp+0A8h+var_70]
0x180075272  mov     ecx, eax
0x180075274  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
