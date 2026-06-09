# _winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::GetDefaultQueryDistanceThresholdForVectorSpaceKind_::_1_::catch$14

- ea: `0x18024dc32`
- end: `0x18024dd0d`
- name: `_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::GetDefaultQueryDistanceThresholdForVectorSpaceKind_::_1_::catch$14`
- size: `219`
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

- `0x18024dc5b`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\ImageEmbeddingsGenerator.cpp`
- `0x18024dc94`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\ImageEmbeddingsGenerator.cpp`
- `0x18024dc69`: `float __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::GetDefaultQueryDistanceThresholdForVectorSpaceKind(enum winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::VectorSpaceKind)`

## pseudocode

```c
void __fastcall __noreturn winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::GetDefaultQueryDistanceThresholdForVectorSpaceKind_::_1_::catch_14(
        __int64 a1,
        __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rax
  unsigned int *v6; // rax

  v3 = asg::SemanticIndex::ResultFromCaughtSemanticIndexException();
  *(_DWORD *)(a2 + 304) = 474;
  *(_DWORD *)(a2 + 308) = 48;
  *(_QWORD *)(a2 + 312) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\ImageEmbeddingsGenerator.cpp";
  *(_QWORD *)(a2 + 320) = "float __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::I"
                          "mageEmbeddingsGenerator::GetDefaultQueryDistanceThresholdForVectorSpaceKind(enum winrt::Micros"
                          "oft::Asg::SemanticIndex::AiFabric::Compatibility::VectorSpaceKind)";
  asg::SemanticIndex::LogCaughtSemanticIndexException(a2 + 208, v3, a2 + 304);
  *(_DWORD *)(a2 + 104) = 476;
  *(_QWORD *)(a2 + 112) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\ImageEmbeddingsGenerator.cpp";
  *(_QWORD *)(a2 + 120) = 0;
  v4 = asg::LogStringView::View(a2 + 208, a2 + 304);
  v5 = asg::as_u16string_view(a2 + 64, v4);
  winrt::param::hstring::hstring(a2 + 272, v5);
  v6 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a2 + 48), v3);
  winrt::hresult_error::hresult_error(a2 + 176, *v6, a2 + 272, a2 + 104);
  throw (winrt::hresult_error *)(a2 + 176);
}

```

## disassembly

```asm
0x18024dc32  mov     [rsp+arg_8], rdx
0x18024dc37  push    rbx
0x18024dc38  push    rbp
0x18024dc39  sub     rsp, 38h
0x18024dc3d  mov     rbp, rdx
0x18024dc40  call    asg__SemanticIndex__ResultFromCaughtSemanticIndexException
0x18024dc45  mov     ebx, eax
0x18024dc47  mov     dword ptr [rbp+130h], 1DAh
0x18024dc51  mov     dword ptr [rbp+134h], 30h ; '0'
0x18024dc5b  lea     rax, aCW1SSrcSemanti_10; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18024dc62  mov     [rbp+138h], rax
0x18024dc69  lea     rax, aFloatCdeclWinr_2; "float __cdecl winrt::Microsoft::Asg::Se"...
0x18024dc70  mov     [rbp+140h], rax
0x18024dc77  lea     r8, [rbp+130h]
0x18024dc7e  mov     edx, ebx
0x18024dc80  lea     rcx, [rbp+0D0h]
0x18024dc87  call    asg__SemanticIndex__LogCaughtSemanticIndexException
0x18024dc8c  nop
0x18024dc8d  mov     dword ptr [rbp+68h], 1DCh
0x18024dc94  lea     rax, aCW1SSrcSemanti_10; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18024dc9b  mov     [rbp+70h], rax
0x18024dc9f  mov     qword ptr [rbp+78h], 0
0x18024dca7  lea     rdx, [rbp+130h]
0x18024dcae  lea     rcx, [rbp+0D0h]
0x18024dcb5  call    ?View@LogStringView@asg@@QEBA?AV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@XZ; asg::LogStringView::View(void)
0x18024dcba  mov     rdx, rax
0x18024dcbd  lea     rcx, [rbp+40h]
0x18024dcc1  call    ?as_u16string_view@asg@@YA?AV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; asg::as_u16string_view(std::wstring_view const &)
0x18024dcc6  mov     rdx, rax
0x18024dcc9  lea     rcx, [rbp+110h]
0x18024dcd0  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::param::hstring::hstring(std::wstring_view const &)
0x18024dcd5  mov     edx, ebx; int
0x18024dcd7  lea     rcx, [rbp+30h]; this
0x18024dcdb  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18024dce0  lea     r9, [rbp+68h]
0x18024dce4  lea     r8, [rbp+110h]
0x18024dceb  mov     edx, [rax]
0x18024dced  lea     rcx, [rbp+0B0h]
0x18024dcf4  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18024dcf9  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18024dd00  lea     rcx, [rbp+0B0h]; pExceptionObject
0x18024dd07  call    _CxxThrowException
```
