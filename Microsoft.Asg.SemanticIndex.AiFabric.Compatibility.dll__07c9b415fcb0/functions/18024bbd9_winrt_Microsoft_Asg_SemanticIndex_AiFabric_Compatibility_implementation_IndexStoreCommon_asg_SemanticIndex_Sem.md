# _winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::DefaultQueryDistanceThreshold_::_1_::catch$19

- ea: `0x18024bbd9`
- end: `0x18024bca2`
- name: `_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::DefaultQueryDistanceThreshold_::_1_::catch$19`
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

- `0x18024bbfc`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18024bc2c`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18024bc07`: `float __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::Ai`

## pseudocode

```c
void __fastcall __noreturn winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::DefaultQueryDistanceThreshold_::_1_::catch_19(
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
                         "ticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::Semant"
                         "icIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microso"
                         "ft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsof"
                         "t::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::Defau"
                         "ltQueryDistanceThreshold(void)";
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
0x18024bbd9  mov     [rsp+arg_8], rdx
0x18024bbde  push    rbx
0x18024bbdf  push    rbp
0x18024bbe0  sub     rsp, 38h
0x18024bbe4  mov     rbp, rdx
0x18024bbe7  call    asg__SemanticIndex__ResultFromCaughtSemanticIndexException
0x18024bbec  mov     ebx, eax
0x18024bbee  mov     dword ptr [rbp+30h], 1FBh
0x18024bbf5  mov     dword ptr [rbp+34h], 34h ; '4'
0x18024bbfc  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18024bc03  mov     [rbp+38h], rax
0x18024bc07  lea     rax, aFloatCdeclWinr_5; "float __cdecl winrt::Microsoft::Asg::Se"...
0x18024bc0e  mov     [rbp+40h], rax
0x18024bc12  lea     r8, [rbp+30h]
0x18024bc16  mov     edx, ebx
0x18024bc18  lea     rcx, [rbp+108h]
0x18024bc1f  call    asg__SemanticIndex__LogCaughtSemanticIndexException
0x18024bc24  nop
0x18024bc25  mov     dword ptr [rbp+60h], 1FDh
0x18024bc2c  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18024bc33  mov     [rbp+68h], rax
0x18024bc37  mov     qword ptr [rbp+70h], 0
0x18024bc3f  lea     rdx, [rbp+50h]
0x18024bc43  lea     rcx, [rbp+108h]
0x18024bc4a  call    ?View@LogStringView@asg@@QEBA?AV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@XZ; asg::LogStringView::View(void)
0x18024bc4f  mov     rdx, rax
0x18024bc52  lea     rcx, [rbp+30h]
0x18024bc56  call    ?as_u16string_view@asg@@YA?AV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; asg::as_u16string_view(std::wstring_view const &)
0x18024bc5b  mov     rdx, rax
0x18024bc5e  lea     rcx, [rbp+0E8h]
0x18024bc65  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::param::hstring::hstring(std::wstring_view const &)
0x18024bc6a  mov     edx, ebx; int
0x18024bc6c  lea     rcx, [rbp+48h]; this
0x18024bc70  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18024bc75  lea     r9, [rbp+60h]
0x18024bc79  lea     r8, [rbp+0E8h]
0x18024bc80  mov     edx, [rax]
0x18024bc82  lea     rcx, [rbp+0D0h]
0x18024bc89  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18024bc8e  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18024bc95  lea     rcx, [rbp+0D0h]; pExceptionObject
0x18024bc9c  call    _CxxThrowException
```
