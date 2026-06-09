# IndexerSemanticStore::AreModelsLoaded(winrt::Windows::Indexer::SemanticSearch::ModelKind const &)

- ea: `0x18003418c`
- end: `0x18003439d`
- name: `?AreModelsLoaded@IndexerSemanticStore@@QEAA_NAEBW4ModelKind@SemanticSearch@Indexer@Windows@winrt@@@Z`
- size: `529`
- prototype: `bool __fastcall(IndexerSemanticStore *__hidden this, const enum winrt::Windows::Indexer::SemanticSearch::ModelKind *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034150`
- `0x18004bb40`

## callees

- `0x180008f84`
- `0x180009cf0`
- `0x180018b14`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x18003418c`
- `0x18003f408`
- `0x18003f4bc`
- `0x18004ba10`
- `0x18004dea8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800342df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800342df`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800341e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034249`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800342b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800341e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034249`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800342b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003430a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003430a`

## string_xrefs

- `0x180034346`: `onecoreuap\base\appmodel\Search\common\AIFabricHostHelper\include\Utils.h`
- `0x180034375`: `onecoreuap\base\appmodel\Search\common\AIFabricHostHelper\include\Utils.h`
- `0x18003438b`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall IndexerSemanticStore::AreModelsLoaded(
        IndexerSemanticStore *this,
        const enum winrt::Windows::Indexer::SemanticSearch::ModelKind *a2)
{
  const char *v4; // r9
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  int v6; // ebx
  char IsLoaded; // al
  char v8; // si
  _DWORD *v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  unsigned int v13; // eax
  unsigned int v14; // eax
  const char *v15; // [rsp+28h] [rbp-50h]
  _BYTE v16[8]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v17[48]; // [rsp+38h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  struct _RTL_CRITICAL_SECTION *v20; // [rsp+C0h] [rbp+48h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::FailFast_Unexpected(
      retaddr,
      (void *)0x915,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      v4);
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v16);
  v5 = (struct _RTL_CRITICAL_SECTION *)pv;
  v6 = 1;
  v20 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( *((_QWORD *)this + 5) )
  {
    if ( pv )
      _InterlockedAdd((volatile signed __int32 *)pv + 72, 1u);
    EnterCriticalSection(v5 + 5);
    ++LODWORD(v5[6].DebugInfo);
    LODWORD(v5[6].SpinCount) = 31;
    tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v20);
    if ( *(_DWORD *)a2 == -1 )
    {
      v6 = -1;
    }
    else if ( *(_DWORD *)a2 )
    {
      if ( *(_DWORD *)a2 != 1 )
      {
        v14 = wil::verify_hresult(2147549183LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0xE7,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\Utils.h",
          (const char *)v14,
          (int)"Unexpected model kind.",
          v15);
      }
    }
    else
    {
      v6 = 0;
    }
    LODWORD(v20) = v6;
    IsLoaded = winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStore2<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>::IsLoaded(
                 (char *)this + 40,
                 &v20);
  }
  else
  {
    if ( pv )
      _InterlockedAdd((volatile signed __int32 *)pv + 72, 1u);
    EnterCriticalSection(v5 + 5);
    ++LODWORD(v5[6].DebugInfo);
    LODWORD(v5[6].SpinCount) = 30;
    tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v20);
    if ( *(_DWORD *)a2 == -1 )
    {
      v6 = -1;
    }
    else if ( *(_DWORD *)a2 )
    {
      if ( *(_DWORD *)a2 != 1 )
      {
        if ( *(_DWORD *)a2 != 2 )
        {
          v13 = wil::verify_hresult(2147549183LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0xFC,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\Utils.h",
            (const char *)v13,
            (int)"Unexpected model kind.",
            v15);
        }
        v6 = 2;
      }
    }
    else
    {
      v6 = 0;
    }
    LODWORD(v20) = v6;
    IsLoaded = winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticImageIndexStore2<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>::IsLoaded(
                 (char *)this + 48,
                 &v20);
  }
  v8 = IsLoaded;
  v9 = pv;
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
  v9[18] |= 0x300u;
  if ( *((_QWORD *)v9 + 31) )
    tip2::details::shared_data<0,0,0>::complete_helper(v9 + 2, 2);
  if ( v10 )
    LeaveCriticalSection(v10);
  v11 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v11);
    CoTaskMemFree(v11);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v17);
  return v8;
}

```

## disassembly

```asm
0x18003418c  push    rbp
0x18003418e  push    rbx
0x18003418f  push    rsi
0x180034190  push    rdi
0x180034191  push    r14
0x180034193  push    r15
0x180034195  mov     rbp, rsp
0x180034198  sub     rsp, 78h
0x18003419c  mov     r15, rdx
0x18003419f  mov     r14, rcx
0x1800341a2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x1800341a9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x1800341ae  test    al, al
0x1800341b0  jz      loc_180034387
0x1800341b6  lea     rcx, [rbp+var_48]
0x1800341ba  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1800341bf  nop
0x1800341c0  mov     rdi, [rbp+pv]
0x1800341c4  mov     ebx, 1
0x1800341c9  mov     [rbp+arg_10], rdi
0x1800341cd  cmp     qword ptr [r14+28h], 0
0x1800341d2  jz      short loc_180034236
0x1800341d4  test    rdi, rdi
0x1800341d7  jz      short loc_1800341E0
0x1800341d9  lock add [rdi+120h], ebx
0x1800341e0  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x1800341e7  call    cs:__imp_EnterCriticalSection
0x1800341ed  add     [rdi+0F0h], ebx
0x1800341f3  mov     dword ptr [rdi+110h], 1Fh
0x1800341fd  lea     rcx, [rbp+arg_10]
0x180034201  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180034206  cmp     dword ptr [r15], 0FFFFFFFFh
0x18003420a  jz      short loc_180034221
0x18003420c  cmp     dword ptr [r15], 0
0x180034210  jz      short loc_18003421D
0x180034212  cmp     [r15], ebx
0x180034215  jnz     loc_180034358
0x18003421b  jmp     short loc_180034224
0x18003421d  xor     ebx, ebx
0x18003421f  jmp     short loc_180034224
0x180034221  or      ebx, 0FFFFFFFFh
0x180034224  mov     dword ptr [rbp+arg_10], ebx
0x180034227  lea     rdx, [rbp+arg_10]
0x18003422b  lea     rcx, [r14+28h]
0x18003422f  call    ?IsLoaded@?$consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStore2@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@AEBW4TextIndexModelKind@SemanticSearch@Windows@Microsoft@3@@Z; winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndexStore2<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>::IsLoaded(winrt::Microsoft::Windows::SemanticSearch::TextIndexModelKind const &)
0x180034234  jmp     short loc_1800342A1
0x180034236  test    rdi, rdi
0x180034239  jz      short loc_180034242
0x18003423b  lock add [rdi+120h], ebx
0x180034242  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180034249  call    cs:__imp_EnterCriticalSection
0x18003424f  add     [rdi+0F0h], ebx
0x180034255  mov     dword ptr [rdi+110h], 1Eh
0x18003425f  lea     rcx, [rbp+arg_10]
0x180034263  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180034268  cmp     dword ptr [r15], 0FFFFFFFFh
0x18003426c  jz      short loc_18003428E
0x18003426e  cmp     dword ptr [r15], 0
0x180034272  jz      short loc_18003428A
0x180034274  cmp     [r15], ebx
0x180034277  jz      short loc_180034291
0x180034279  cmp     dword ptr [r15], 2
0x18003427d  jnz     loc_180034329
0x180034283  mov     ebx, 2
0x180034288  jmp     short loc_180034291
0x18003428a  xor     ebx, ebx
0x18003428c  jmp     short loc_180034291
0x18003428e  or      ebx, 0FFFFFFFFh
0x180034291  mov     dword ptr [rbp+arg_10], ebx
0x180034294  lea     rcx, [r14+30h]
0x180034298  lea     rdx, [rbp+arg_10]
0x18003429c  call    ?IsLoaded@?$consume_Microsoft_Windows_SemanticSearch_ISemanticImageIndexStore2@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@AEBW4ImageIndexModelKind@SemanticSearch@Windows@Microsoft@3@@Z; winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticImageIndexStore2<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>::IsLoaded(winrt::Microsoft::Windows::SemanticSearch::ImageIndexModelKind const &)
0x1800342a1  mov     sil, al
0x1800342a4  mov     rbx, [rbp+pv]
0x1800342a8  lea     rdi, [rbx+0C8h]
0x1800342af  mov     rcx, rdi; lpCriticalSection
0x1800342b2  call    cs:__imp_EnterCriticalSection
0x1800342b8  or      dword ptr [rbx+48h], 300h
0x1800342bf  cmp     qword ptr [rbx+0F8h], 0
0x1800342c7  jz      short loc_1800342D7
0x1800342c9  mov     edx, 2
0x1800342ce  lea     rcx, [rbx+8]
0x1800342d2  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x1800342d7  test    rdi, rdi
0x1800342da  jz      short loc_1800342E6
0x1800342dc  mov     rcx, rdi; lpCriticalSection
0x1800342df  call    cs:__imp_LeaveCriticalSection
0x1800342e5  nop
0x1800342e6  mov     rbx, [rbp+pv]
0x1800342ea  test    rbx, rbx
0x1800342ed  jz      short loc_180034310
0x1800342ef  or      eax, 0FFFFFFFFh
0x1800342f2  lock xadd [rbx+120h], eax
0x1800342fa  cmp     eax, 1
0x1800342fd  jnz     short loc_180034310
0x1800342ff  mov     rcx, rbx
0x180034302  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180034307  mov     rcx, rbx; pv
0x18003430a  call    cs:__imp_CoTaskMemFree
0x180034310  lea     rcx, [rbp+var_40]; this
0x180034314  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180034319  mov     al, sil
0x18003431c  add     rsp, 78h
0x180034320  pop     r15
0x180034322  pop     r14
0x180034324  pop     rdi
0x180034325  pop     rsi
0x180034326  pop     rbx
0x180034327  pop     rbp
0x180034328  retn
0x180034329  mov     ecx, 8000FFFFh
0x18003432e  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180034333  mov     r9d, eax; char *
0x180034336  mov     rcx, [rbp+30h]; this
0x18003433a  lea     rax, aUnexpectedMode; "Unexpected model kind."
0x180034341  mov     qword ptr [rsp+78h+var_58], rax; int
0x180034346  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18003434d  mov     edx, 0FCh; void *
0x180034352  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180034358  mov     ecx, 8000FFFFh
0x18003435d  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x180034362  mov     r9d, eax; char *
0x180034365  mov     rcx, [rbp+30h]; this
0x180034369  lea     rax, aUnexpectedMode; "Unexpected model kind."
0x180034370  mov     qword ptr [rsp+78h+var_58], rax; int
0x180034375  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18003437c  mov     edx, 0E7h; void *
0x180034381  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180034387  mov     rcx, [rbp+30h]; this
0x18003438b  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x180034392  mov     edx, 915h; void *
0x180034397  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
