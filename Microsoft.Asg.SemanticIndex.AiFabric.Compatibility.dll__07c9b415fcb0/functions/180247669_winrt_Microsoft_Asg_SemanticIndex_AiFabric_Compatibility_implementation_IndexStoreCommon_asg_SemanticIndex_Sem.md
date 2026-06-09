# _winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::DefaultQueryDistanceThreshold_::_1_::catch$19

- ea: `0x180247669`
- end: `0x180247732`
- name: `_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::DefaultQueryDistanceThreshold_::_1_::catch$19`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003fb0`
- `0x180004510`
- `0x180008720`
- `0x1800087f0`
- `0x18000cc90`
- `0x18000cca0`
- `0x18000ccc0`
- `0x1801f97e0`

## string_xrefs

- `0x18024768c`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x1802476bc`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180247697`: `float __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::`

## pseudocode

```c
void __fastcall __noreturn winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::DefaultQueryDistanceThreshold_::_1_::catch_19(
        __int64 a1,
        __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rax
  unsigned int *v6; // rax

  v3 = asg::SemanticIndex::ResultFromCaughtSemanticIndexException();
  *(_DWORD *)(a2 + 48) = 507;
  *(_DWORD *)(a2 + 52) = 52;
  *(_QWORD *)(a2 + 56) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
  *(_QWORD *)(a2 + 64) = "float __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::In"
                         "dexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::Seman"
                         "ticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::Seman"
                         "ticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt::Micro"
                         "soft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Micros"
                         "oft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::Def"
                         "aultQueryDistanceThreshold(void)";
  asg::SemanticIndex::LogCaughtSemanticIndexException(a2 + 264, v3, a2 + 48);
  *(_DWORD *)(a2 + 96) = 509;
  *(_QWORD *)(a2 + 104) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
  *(_QWORD *)(a2 + 112) = 0;
  v4 = asg::LogStringView::View(a2 + 264, a2 + 80);
  v5 = asg::as_u16string_view(a2 + 48, v4);
  winrt::param::hstring::hstring(a2 + 232, v5);
  v6 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a2 + 72), v3);
  winrt::hresult_error::hresult_error(a2 + 208, *v6, a2 + 232, a2 + 96);
  throw (winrt::hresult_error *)(a2 + 208);
}

```

## disassembly

```asm
0x180247669  mov     [rsp+arg_8], rdx
0x18024766e  push    rbx
0x18024766f  push    rbp
0x180247670  sub     rsp, 38h
0x180247674  mov     rbp, rdx
0x180247677  call    asg__SemanticIndex__ResultFromCaughtSemanticIndexException
0x18024767c  mov     ebx, eax
0x18024767e  mov     dword ptr [rbp+30h], 1FBh
0x180247685  mov     dword ptr [rbp+34h], 34h ; '4'
0x18024768c  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180247693  mov     [rbp+38h], rax
0x180247697  lea     rax, aFloatCdeclWinr_3; "float __cdecl winrt::Microsoft::Asg::Se"...
0x18024769e  mov     [rbp+40h], rax
0x1802476a2  lea     r8, [rbp+30h]
0x1802476a6  mov     edx, ebx
0x1802476a8  lea     rcx, [rbp+108h]
0x1802476af  call    asg__SemanticIndex__LogCaughtSemanticIndexException
0x1802476b4  nop
0x1802476b5  mov     dword ptr [rbp+60h], 1FDh
0x1802476bc  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1802476c3  mov     [rbp+68h], rax
0x1802476c7  mov     qword ptr [rbp+70h], 0
0x1802476cf  lea     rdx, [rbp+50h]
0x1802476d3  lea     rcx, [rbp+108h]
0x1802476da  call    ?View@LogStringView@asg@@QEBA?AV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@XZ; asg::LogStringView::View(void)
0x1802476df  mov     rdx, rax
0x1802476e2  lea     rcx, [rbp+30h]
0x1802476e6  call    ?as_u16string_view@asg@@YA?AV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; asg::as_u16string_view(std::wstring_view const &)
0x1802476eb  mov     rdx, rax
0x1802476ee  lea     rcx, [rbp+0E8h]
0x1802476f5  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::param::hstring::hstring(std::wstring_view const &)
0x1802476fa  mov     edx, ebx; int
0x1802476fc  lea     rcx, [rbp+48h]; this
0x180247700  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180247705  lea     r9, [rbp+60h]
0x180247709  lea     r8, [rbp+0E8h]
0x180247710  mov     edx, [rax]
0x180247712  lea     rcx, [rbp+0D0h]
0x180247719  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18024771e  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180247725  lea     rcx, [rbp+0D0h]; pExceptionObject
0x18024772c  call    _CxxThrowException
```
