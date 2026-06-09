# _winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions::SetEncodedKey_::_1_::catch$20

- ea: `0x18024406e`
- end: `0x180244170`
- name: `_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions::SetEncodedKey_::_1_::catch$20`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180003fb0`
- `0x180004510`
- `0x180008720`
- `0x1800087f0`
- `0x18000cc90`
- `0x18000cca0`
- `0x18000ccc0`
- `0x18000e8d0`
- `0x18000e8f0`
- `0x18000ebd0`
- `0x1801f97e0`

## string_xrefs

- `0x1802440c7`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexEncryptionOptions.cpp`
- `0x1802440f7`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexEncryptionOptions.cpp`
- `0x1802440d2`: `void __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions::SetEncodedKey(enum winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexEncryptionFlags,const struct winrt::Windows::Foundation::Collections::IVectorView<unsigned char> &)`

## pseudocode

```c
void __fastcall __noreturn winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexEncryptionOptions::SetEncodedKey_::_1_::catch_20(
        __int64 a1,
        __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // rax
  unsigned int *v6; // rax

  *(_OWORD *)(a2 + 64) = 0;
  *(_OWORD *)(a2 + 80) = 0;
  asg::Sqlite::DbAesKeyStore::DbAesKeyStore((asg::Sqlite::DbAesKeyStore *)(a2 + 64));
  asg::Sqlite::DbAesKeyStore::operator=(*(_QWORD *)(a2 + 352) + 176LL, a2 + 64);
  std::vector<unsigned char,asg::secure_allocator<unsigned char>>::~vector<unsigned char,asg::secure_allocator<unsigned char>>(a2 + 64);
  v3 = asg::SemanticIndex::ResultFromCaughtSemanticIndexException();
  *(_DWORD *)(a2 + 32) = 60;
  *(_DWORD *)(a2 + 36) = 48;
  *(_QWORD *)(a2 + 40) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexEncryptionOptions.cpp";
  *(_QWORD *)(a2 + 48) = "void __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::Ind"
                         "exEncryptionOptions::SetEncodedKey(enum winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compati"
                         "bility::IndexEncryptionFlags,const struct winrt::Windows::Foundation::Collections::IVectorView<"
                         "unsigned char> &)";
  asg::SemanticIndex::LogCaughtSemanticIndexException(a2 + 240, v3, a2 + 32);
  *(_DWORD *)(a2 + 64) = 61;
  *(_QWORD *)(a2 + 72) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexEncryptionOptions.cpp";
  *(_QWORD *)(a2 + 80) = 0;
  v4 = asg::LogStringView::View(a2 + 240, a2 + 32);
  v5 = asg::as_u16string_view(a2 + 112, v4);
  winrt::param::hstring::hstring(a2 + 208, v5);
  v6 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a2 + 352), v3);
  winrt::hresult_error::hresult_error(a2 + 184, *v6, a2 + 208, a2 + 64);
  throw (winrt::hresult_error *)(a2 + 184);
}

```

## disassembly

```asm
0x18024406e  mov     [rsp+arg_8], rdx
0x180244073  push    rbx
0x180244074  push    rbp
0x180244075  sub     rsp, 28h
0x180244079  mov     rbp, rdx
0x18024407c  xorps   xmm0, xmm0
0x18024407f  movups  xmmword ptr [rbp+40h], xmm0
0x180244083  movups  xmmword ptr [rbp+50h], xmm0
0x180244087  lea     rcx, [rbp+40h]; this
0x18024408b  call    ??0DbAesKeyStore@Sqlite@asg@@QEAA@XZ; asg::Sqlite::DbAesKeyStore::DbAesKeyStore(void)
0x180244090  nop
0x180244091  mov     rcx, [rbp+160h]
0x180244098  add     rcx, 0B0h
0x18024409f  lea     rdx, [rbp+40h]
0x1802440a3  call    ??4DbAesKeyStore@Sqlite@asg@@QEAAAEAU012@$$QEAU012@@Z; asg::Sqlite::DbAesKeyStore::operator=(asg::Sqlite::DbAesKeyStore &&)
0x1802440a8  nop
0x1802440a9  lea     rcx, [rbp+40h]
0x1802440ad  call    ??1?$vector@EU?$secure_allocator@E@asg@@@std@@QEAA@XZ; std::vector<uchar,asg::secure_allocator<uchar>>::~vector<uchar,asg::secure_allocator<uchar>>(void)
0x1802440b2  call    asg__SemanticIndex__ResultFromCaughtSemanticIndexException
0x1802440b7  mov     ebx, eax
0x1802440b9  mov     dword ptr [rbp+20h], 3Ch ; '<'
0x1802440c0  mov     dword ptr [rbp+24h], 30h ; '0'
0x1802440c7  lea     rax, aCW1SSrcSemanti_25; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1802440ce  mov     [rbp+28h], rax
0x1802440d2  lea     rax, aVoidCdeclWinrt_11; "void __cdecl winrt::Microsoft::Asg::Sem"...
0x1802440d9  mov     [rbp+30h], rax
0x1802440dd  lea     r8, [rbp+20h]
0x1802440e1  mov     edx, ebx
0x1802440e3  lea     rcx, [rbp+0F0h]
0x1802440ea  call    asg__SemanticIndex__LogCaughtSemanticIndexException
0x1802440ef  nop
0x1802440f0  mov     dword ptr [rbp+40h], 3Dh ; '='
0x1802440f7  lea     rax, aCW1SSrcSemanti_25; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1802440fe  mov     [rbp+48h], rax
0x180244102  mov     qword ptr [rbp+50h], 0
0x18024410a  lea     rdx, [rbp+20h]
0x18024410e  lea     rcx, [rbp+0F0h]
0x180244115  call    ?View@LogStringView@asg@@QEBA?AV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@XZ; asg::LogStringView::View(void)
0x18024411a  mov     rdx, rax
0x18024411d  lea     rcx, [rbp+70h]
0x180244121  call    ?as_u16string_view@asg@@YA?AV?$basic_string_view@_SU?$char_traits@_S@std@@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; asg::as_u16string_view(std::wstring_view const &)
0x180244126  mov     rdx, rax
0x180244129  lea     rcx, [rbp+0D0h]
0x180244130  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::param::hstring::hstring(std::wstring_view const &)
0x180244135  mov     edx, ebx; int
0x180244137  lea     rcx, [rbp+160h]; this
0x18024413e  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180244143  lea     r9, [rbp+40h]
0x180244147  lea     r8, [rbp+0D0h]
0x18024414e  mov     edx, [rax]
0x180244150  lea     rcx, [rbp+0B8h]
0x180244157  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18024415c  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180244163  lea     rcx, [rbp+0B8h]; pExceptionObject
0x18024416a  call    _CxxThrowException
```
