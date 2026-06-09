# _winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::GetDefaultQueryDistanceThresholdForVectorSpaceKind_::_1_::catch$14

- ea: `0x18024cd92`
- end: `0x18024ce6d`
- name: `_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::GetDefaultQueryDistanceThresholdForVectorSpaceKind_::_1_::catch$14`
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

- `0x18024cdbb`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\TextEmbeddingsGenerator.cpp`
- `0x18024cdf4`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\TextEmbeddingsGenerator.cpp`
- `0x18024cdc9`: `float __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::GetDefaultQueryDistanceThresholdForVectorSpaceKind(enum winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::VectorSpaceKind)`

## pseudocode

```c
void __fastcall __noreturn winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::GetDefaultQueryDistanceThresholdForVectorSpaceKind_::_1_::catch_14(
        __int64 a1,
        __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rax
  unsigned int *v6; // rax

  v3 = asg::SemanticIndex::ResultFromCaughtSemanticIndexException();
  *(_DWORD *)(a2 + 304) = 225;
  *(_DWORD *)(a2 + 308) = 48;
  *(_QWORD *)(a2 + 312) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\TextEmbeddingsGenerator.cpp";
  *(_QWORD *)(a2 + 320) = "float __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::T"
                          "extEmbeddingsGenerator::GetDefaultQueryDistanceThresholdForVectorSpaceKind(enum winrt::Microso"
                          "ft::Asg::SemanticIndex::AiFabric::Compatibility::VectorSpaceKind)";
  asg::SemanticIndex::LogCaughtSemanticIndexException(a2 + 208, v3, a2 + 304);
  *(_DWORD *)(a2 + 104) = 227;
  *(_QWORD *)(a2 + 112) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\TextEmbeddingsGenerator.cpp";
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
0x18024cd92  mov     [rsp+arg_8], rdx
0x18024cd97  push    rbx
0x18024cd98  push    rbp
0x18024cd99  sub     rsp, 38h
0x18024cd9d  mov     rbp, rdx
0x18024cda0  call    asg__SemanticIndex__ResultFromCaughtSemanticIndexException
0x18024cda5  mov     ebx, eax
0x18024cda7  mov     dword ptr [rbp+130h], 0E1h
0x18024cdb1  mov     dword ptr [rbp+134h], 30h ; '0'
0x18024cdbb  lea     rax, aCW1SSrcSemanti_1; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18024cdc2  mov     [rbp+138h], rax
0x18024cdc9  lea     rax, aFloatCdeclWinr_1; "float __cdecl winrt::Microsoft::Asg::Se"...
0x18024cdd0  mov     [rbp+140h], rax
0x18024cdd7  lea     r8, [rbp+130h]
0x18024cdde  mov     edx, ebx
0x18024cde0  lea     rcx, [rbp+0D0h]
0x18024cde7  call    asg__SemanticIndex__LogCaughtSemanticIndexException
0x18024cdec  nop
0x18024cded  mov     dword ptr [rbp+68h], 0E3h
0x18024cdf4  lea     rax, aCW1SSrcSemanti_1; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18024cdfb  mov     [rbp+70h], rax
0x18024cdff  mov     qword ptr [rbp+78h], 0
0x18024ce07  lea     rdx, [rbp+130h]
0x18024ce0e  lea     rcx, [rbp+0D0h]
0x18024ce15  call    ?View@LogStringView@asg@@QEBA?AV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@XZ; asg::LogStringView::View(void)
0x18024ce1a  mov     rdx, rax
0x18024ce1d  lea     rcx, [rbp+40h]
0x18024ce21  call    ?as_u16string_view@asg@@YA?AV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; asg::as_u16string_view(std::wstring_view const &)
0x18024ce26  mov     rdx, rax
0x18024ce29  lea     rcx, [rbp+110h]
0x18024ce30  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::param::hstring::hstring(std::wstring_view const &)
0x18024ce35  mov     edx, ebx; int
0x18024ce37  lea     rcx, [rbp+30h]; this
0x18024ce3b  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18024ce40  lea     r9, [rbp+68h]
0x18024ce44  lea     r8, [rbp+110h]
0x18024ce4b  mov     edx, [rax]
0x18024ce4d  lea     rcx, [rbp+0B0h]
0x18024ce54  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18024ce59  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18024ce60  lea     rcx, [rbp+0B0h]; pExceptionObject
0x18024ce67  call    _CxxThrowException
```
