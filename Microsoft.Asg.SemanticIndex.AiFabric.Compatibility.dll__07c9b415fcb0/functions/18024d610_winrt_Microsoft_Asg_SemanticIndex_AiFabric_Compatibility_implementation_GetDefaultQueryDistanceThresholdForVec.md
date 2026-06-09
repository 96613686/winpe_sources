# _winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDefaultQueryDistanceThresholdForVectorSpace_::_1_::catch$15

- ea: `0x18024d610`
- end: `0x18024d6df`
- name: `_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDefaultQueryDistanceThresholdForVectorSpace_::_1_::catch$15`
- size: `207`
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

- `0x18024d63e`: `float __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDefaultQueryDistanceThresholdForVectorSpace(struct asg::Guid)`
- `0x18024d633`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\VectorSpaces.cpp`
- `0x18024d663`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\VectorSpaces.cpp`

## pseudocode

```c
void __fastcall __noreturn winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDefaultQueryDistanceThresholdForVectorSpace_::_1_::catch_15(
        __int64 a1,
        __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rax
  unsigned int *v6; // rax

  v3 = asg::SemanticIndex::ResultFromCaughtSemanticIndexException();
  *(_DWORD *)(a2 + 64) = 48;
  *(_DWORD *)(a2 + 68) = 48;
  *(_QWORD *)(a2 + 72) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\VectorSpaces.cpp";
  *(_QWORD *)(a2 + 80) = "float __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::Ge"
                         "tDefaultQueryDistanceThresholdForVectorSpace(struct asg::Guid)";
  asg::SemanticIndex::LogCaughtSemanticIndexException(a2 + 248, v3, a2 + 64);
  *(_DWORD *)(a2 + 120) = 50;
  *(_QWORD *)(a2 + 128) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\VectorSpaces.cpp";
  *(_QWORD *)(a2 + 136) = 0;
  v4 = asg::LogStringView::View(a2 + 248, a2 + 64);
  v5 = asg::as_u16string_view(a2 + 96, v4);
  winrt::param::hstring::hstring(a2 + 216, v5);
  v6 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a2 + 48), v3);
  winrt::hresult_error::hresult_error(a2 + 192, *v6, a2 + 216, a2 + 120);
  throw (winrt::hresult_error *)(a2 + 192);
}

```

## disassembly

```asm
0x18024d610  mov     [rsp+arg_8], rdx
0x18024d615  push    rbx
0x18024d616  push    rbp
0x18024d617  sub     rsp, 38h
0x18024d61b  mov     rbp, rdx
0x18024d61e  call    asg__SemanticIndex__ResultFromCaughtSemanticIndexException
0x18024d623  mov     ebx, eax
0x18024d625  mov     dword ptr [rbp+40h], 30h ; '0'
0x18024d62c  mov     dword ptr [rbp+44h], 30h ; '0'
0x18024d633  lea     rax, aCW1SSrcSemanti_39; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18024d63a  mov     [rbp+48h], rax
0x18024d63e  lea     rax, aFloatCdeclWinr_4; "float __cdecl winrt::Microsoft::Asg::Se"...
0x18024d645  mov     [rbp+50h], rax
0x18024d649  lea     r8, [rbp+40h]
0x18024d64d  mov     edx, ebx
0x18024d64f  lea     rcx, [rbp+0F8h]
0x18024d656  call    asg__SemanticIndex__LogCaughtSemanticIndexException
0x18024d65b  nop
0x18024d65c  mov     dword ptr [rbp+78h], 32h ; '2'
0x18024d663  lea     rax, aCW1SSrcSemanti_39; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18024d66a  mov     [rbp+80h], rax
0x18024d671  mov     qword ptr [rbp+88h], 0
0x18024d67c  lea     rdx, [rbp+40h]
0x18024d680  lea     rcx, [rbp+0F8h]
0x18024d687  call    ?View@LogStringView@asg@@QEBA?AV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@XZ; asg::LogStringView::View(void)
0x18024d68c  mov     rdx, rax
0x18024d68f  lea     rcx, [rbp+60h]
0x18024d693  call    ?as_u16string_view@asg@@YA?AV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; asg::as_u16string_view(std::wstring_view const &)
0x18024d698  mov     rdx, rax
0x18024d69b  lea     rcx, [rbp+0D8h]
0x18024d6a2  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::param::hstring::hstring(std::wstring_view const &)
0x18024d6a7  mov     edx, ebx; int
0x18024d6a9  lea     rcx, [rbp+30h]; this
0x18024d6ad  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18024d6b2  lea     r9, [rbp+78h]
0x18024d6b6  lea     r8, [rbp+0D8h]
0x18024d6bd  mov     edx, [rax]
0x18024d6bf  lea     rcx, [rbp+0C0h]
0x18024d6c6  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18024d6cb  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18024d6d2  lea     rcx, [rbp+0C0h]; pExceptionObject
0x18024d6d9  call    _CxxThrowException
```
