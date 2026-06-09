# UWAInstallWork::_UpdateIntentStrings(void)

- ea: `0x1800fcd50`
- end: `0x1800fcfd0`
- name: `?_UpdateIntentStrings@UWAInstallWork@@AEAAXXZ`
- size: `640`
- prototype: `void __fastcall(UWAInstallWork *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800e2b80`
- `0x1800e57e0`

## callees

- `0x180071be4`
- `0x180072484`
- `0x1800dd634`
- `0x1800dd710`
- `0x1800dd7ec`
- `0x1800dd8c8`
- `0x1800e2a58`
- `0x1800fcd50`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcd71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcd87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcd9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcdaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcf13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcf5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcfa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcd71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcd87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcd9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcdaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcecc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcf13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcf5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fcfa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fcdeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fce0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fce32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fce54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fcdeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fce0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fce32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fce54`

## pseudocode

```c
void __fastcall UWAInstallWork::_UpdateIntentStrings(HSTRING *this)
{
  char *v2; // r14
  HSTRING v3; // r15
  __int64 v4; // r12
  __int64 v5; // r13
  __int64 v6; // rsi
  HSTRING v7; // rbx
  __int64 v8; // r14
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rcx
  PCWSTR v11; // rax
  __int64 v12; // rcx
  PCWSTR v13; // rax
  __int64 v14; // rcx
  PCWSTR v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  HSTRING *v18; // rax
  HSTRING v19; // rbx
  __int64 v20; // rax
  HSTRING *v21; // rax
  HSTRING v22; // rbx
  __int64 v23; // rax
  HSTRING *v24; // rax
  HSTRING v25; // rbx
  __int64 v26; // rax
  HSTRING *v27; // rax
  HSTRING v28; // rbx
  char v29; // [rsp+20h] [rbp-30h]
  int v30; // [rsp+20h] [rbp-30h]
  int v31; // [rsp+20h] [rbp-30h]
  int v32; // [rsp+20h] [rbp-30h]
  _BYTE v33[32]; // [rsp+30h] [rbp-20h] BYREF
  char v34; // [rsp+90h] [rbp+40h] BYREF
  __int64 v35; // [rsp+98h] [rbp+48h]
  char v36; // [rsp+A0h] [rbp+50h] BYREF

  WindowsDeleteString(this[59]);
  this[59] = 0;
  WindowsDeleteString(this[57]);
  this[57] = 0;
  WindowsDeleteString(this[58]);
  this[58] = 0;
  WindowsDeleteString(this[60]);
  v2 = (char *)(this + 146);
  this[60] = 0;
  v3 = this[147];
  v4 = 0;
  v5 = 0;
  v35 = 0;
  v6 = 0;
  v7 = this[146];
  if ( v7 != v3 )
  {
    v8 = 0;
    do
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(*(_QWORD *)v7 + 88LL), 0);
      v10 = -1;
      do
        ++v10;
      while ( StringRawBuffer[v10] );
      v4 += v10 + 1;
      v11 = WindowsGetStringRawBuffer(*(HSTRING *)(*(_QWORD *)v7 + 112LL), 0);
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      v5 += v12 + 1;
      v13 = WindowsGetStringRawBuffer(*(HSTRING *)(*(_QWORD *)v7 + 144LL), 0);
      v14 = -1;
      do
        ++v14;
      while ( v13[v14] );
      v8 += v14 + 1;
      v15 = WindowsGetStringRawBuffer(*(HSTRING *)(*(_QWORD *)v7 + 120LL), 0);
      v16 = -1;
      do
        ++v16;
      while ( v15[v16] );
      if ( v16 )
        v6 += v16 + 1;
      v7 += 2;
    }
    while ( v7 != v3 );
    v35 = v8;
    v2 = (char *)(this + 146);
  }
  winrt::impl::root_implements<winrt::iterable_base<winrt::impl::input_iterable<enum winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature,std::vector<enum winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature>>,enum winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<enum winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature>>::abi_guard::abi_guard(
    &v34,
    this);
  v17 = std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>(
          v33,
          v2);
  v29 = 0;
  v18 = (HSTRING *)lambda_a34907c0591b24a770ce58799b827756_::operator()_std::vector_Microsoft::WRL::ComPtr_WindowsUpdate::Internal::FulfillmentDataInfo__std::allocator_Microsoft::WRL::ComPtr_WindowsUpdate::Internal::FulfillmentDataInfo_______lambda_479ca54db40646ca08554bcde6dc8cf8___(
                     &v34,
                     &v36,
                     v4,
                     v17,
                     v29);
  v19 = *v18;
  *v18 = 0;
  WindowsDeleteString(this[59]);
  this[59] = v19;
  Windows::Internal::String::~String((Windows::Internal::String *)&v36);
  v20 = std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>(
          v33,
          v2);
  LOBYTE(v30) = 0;
  v21 = (HSTRING *)lambda_a34907c0591b24a770ce58799b827756_::operator()_std::vector_Microsoft::WRL::ComPtr_WindowsUpdate::Internal::FulfillmentDataInfo__std::allocator_Microsoft::WRL::ComPtr_WindowsUpdate::Internal::FulfillmentDataInfo_______lambda_a79e14d6ab7f8650301fa86b55f17c9a___(
                     &v34,
                     &v36,
                     v5,
                     v20,
                     v30);
  v22 = *v21;
  *v21 = 0;
  WindowsDeleteString(this[57]);
  this[57] = v22;
  Windows::Internal::String::~String((Windows::Internal::String *)&v36);
  v23 = std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>(
          v33,
          v2);
  LOBYTE(v31) = 0;
  v24 = (HSTRING *)lambda_a34907c0591b24a770ce58799b827756_::operator()_std::vector_Microsoft::WRL::ComPtr_WindowsUpdate::Internal::FulfillmentDataInfo__std::allocator_Microsoft::WRL::ComPtr_WindowsUpdate::Internal::FulfillmentDataInfo_______lambda_c6cf5d1d65bda51241d118baab488d48___(
                     &v34,
                     &v36,
                     v6,
                     v23,
                     v31);
  v25 = *v24;
  *v24 = 0;
  WindowsDeleteString(this[58]);
  this[58] = v25;
  Windows::Internal::String::~String((Windows::Internal::String *)&v36);
  v26 = std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>(
          v33,
          v2);
  LOBYTE(v32) = 0;
  v27 = (HSTRING *)lambda_a34907c0591b24a770ce58799b827756_::operator()_std::vector_Microsoft::WRL::ComPtr_WindowsUpdate::Internal::FulfillmentDataInfo__std::allocator_Microsoft::WRL::ComPtr_WindowsUpdate::Internal::FulfillmentDataInfo_______lambda_9308f9474e273e348d118dea8d704b75___(
                     &v34,
                     &v36,
                     v35,
                     v26,
                     v32);
  v28 = *v27;
  *v27 = 0;
  WindowsDeleteString(this[60]);
  this[60] = v28;
  Windows::Internal::String::~String((Windows::Internal::String *)&v36);
}

```

## disassembly

```asm
0x1800fcd50  mov     [rsp-38h+arg_18], rbx
0x1800fcd55  push    rbp
0x1800fcd56  push    rsi
0x1800fcd57  push    rdi
0x1800fcd58  push    r12
0x1800fcd5a  push    r13
0x1800fcd5c  push    r14
0x1800fcd5e  push    r15
0x1800fcd60  mov     rbp, rsp
0x1800fcd63  sub     rsp, 50h
0x1800fcd67  mov     rdi, rcx
0x1800fcd6a  mov     rcx, [rcx+1D8h]; string
0x1800fcd71  call    cs:__imp_WindowsDeleteString
0x1800fcd77  xor     ebx, ebx
0x1800fcd79  mov     [rdi+1D8h], rbx
0x1800fcd80  mov     rcx, [rdi+1C8h]; string
0x1800fcd87  call    cs:__imp_WindowsDeleteString
0x1800fcd8d  mov     [rdi+1C8h], rbx
0x1800fcd94  mov     rcx, [rdi+1D0h]; string
0x1800fcd9b  call    cs:__imp_WindowsDeleteString
0x1800fcda1  mov     [rdi+1D0h], rbx
0x1800fcda8  mov     rcx, [rdi+1E0h]; string
0x1800fcdaf  call    cs:__imp_WindowsDeleteString
0x1800fcdb5  lea     r14, [rdi+490h]
0x1800fcdbc  mov     [rdi+1E0h], rbx
0x1800fcdc3  mov     r15, [r14+8]
0x1800fcdc7  mov     r12d, ebx
0x1800fcdca  mov     r13d, ebx
0x1800fcdcd  mov     [rbp+arg_8], rbx
0x1800fcdd1  mov     esi, ebx
0x1800fcdd3  mov     rbx, [r14]
0x1800fcdd6  cmp     rbx, r15
0x1800fcdd9  jz      loc_1800FCE8C
0x1800fcddf  mov     r14d, esi
0x1800fcde2  mov     rcx, [rbx]
0x1800fcde5  xor     edx, edx; length
0x1800fcde7  mov     rcx, [rcx+58h]; string
0x1800fcdeb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fcdf1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800fcdf5  xor     edx, edx; length
0x1800fcdf7  inc     rcx
0x1800fcdfa  cmp     [rax+rcx*2], dx
0x1800fcdfe  jnz     short loc_1800FCDF7
0x1800fce00  inc     rcx
0x1800fce03  add     r12, rcx
0x1800fce06  mov     rcx, [rbx]
0x1800fce09  mov     rcx, [rcx+70h]; string
0x1800fce0d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fce13  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800fce17  xor     edx, edx; length
0x1800fce19  inc     rcx
0x1800fce1c  cmp     [rax+rcx*2], dx
0x1800fce20  jnz     short loc_1800FCE19
0x1800fce22  inc     rcx
0x1800fce25  add     r13, rcx
0x1800fce28  mov     rcx, [rbx]
0x1800fce2b  mov     rcx, [rcx+90h]; string
0x1800fce32  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fce38  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800fce3c  xor     edx, edx; length
0x1800fce3e  inc     rcx
0x1800fce41  cmp     [rax+rcx*2], dx
0x1800fce45  jnz     short loc_1800FCE3E
0x1800fce47  inc     rcx
0x1800fce4a  add     r14, rcx
0x1800fce4d  mov     rcx, [rbx]
0x1800fce50  mov     rcx, [rcx+78h]; string
0x1800fce54  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fce5a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800fce5e  xor     edx, edx
0x1800fce60  inc     rcx
0x1800fce63  cmp     [rax+rcx*2], dx
0x1800fce67  jnz     short loc_1800FCE60
0x1800fce69  test    rcx, rcx
0x1800fce6c  jz      short loc_1800FCE74
0x1800fce6e  inc     rsi
0x1800fce71  add     rsi, rcx
0x1800fce74  add     rbx, 8
0x1800fce78  cmp     rbx, r15
0x1800fce7b  jnz     loc_1800FCDE2
0x1800fce81  mov     [rbp+arg_8], r14
0x1800fce85  lea     r14, [rdi+490h]
0x1800fce8c  mov     rdx, rdi
0x1800fce8f  lea     rcx, [rbp+arg_0]
0x1800fce93  call    ??0abi_guard@?$root_implements@Uiterator@?$iterable_base@U?$input_iterable@W4StoreSystemFeature@Preview@Store@ApplicationModel@Windows@winrt@@V?$vector@W4StoreSystemFeature@Preview@Store@ApplicationModel@Windows@winrt@@V?$allocator@W4StoreSystemFeature@Preview@Store@ApplicationModel@Windows@winrt@@@std@@@std@@@impl@winrt@@W4StoreSystemFeature@Preview@Store@ApplicationModel@Windows@3@Uno_collection_version@23@@winrt@@U?$IIterator@W4StoreSystemFeature@Preview@Store@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@QEAA@AEAUiterator@?$iterable_base@U?$input_iterable@W4StoreSystemFeature@Preview@Store@ApplicationModel@Windows@winrt@@V?$vector@W4StoreSystemFeature@Preview@Store@ApplicationModel@Windows@winrt@@V?$allocator@W4StoreSystemFeature@Preview@Store@ApplicationModel@Windows@winrt@@@std@@@std@@@impl@winrt@@W4StoreSystemFeature@Preview@Store@ApplicationModel@Windows@3@Uno_collection_version@23@@3@@Z; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::input_iterable<winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature,std::vector<winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature>>,winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature,winrt::impl::no_collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature>>::abi_guard::abi_guard(winrt::iterable_base<winrt::impl::input_iterable<winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature,std::vector<winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature>>,winrt::Windows::ApplicationModel::Store::Preview::StoreSystemFeature,winrt::impl::no_collection_version>::iterator &)
0x1800fce98  mov     rdx, r14
0x1800fce9b  lea     rcx, [rbp+var_20]
0x1800fce9f  xor     r15d, r15d
0x1800fcea2  call    ??0?$vector@V?$ComPtr@VFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>(std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>> const &)
0x1800fcea7  mov     r9, rax
0x1800fceaa  mov     byte ptr [rsp+50h+var_30], r15b
0x1800fceaf  mov     r8, r12
0x1800fceb2  lea     rdx, [rbp+arg_10]
0x1800fceb6  lea     rcx, [rbp+arg_0]
0x1800fceba  call    _lambda_a34907c0591b24a770ce58799b827756___operator___std__vector_Microsoft__WRL__ComPtr_WindowsUpdate__Internal__FulfillmentDataInfo__std__allocator_Microsoft__WRL__ComPtr_WindowsUpdate__Internal__FulfillmentDataInfo_______lambda_479ca54db40646ca08554bcde6dc8cf8___
0x1800fcebf  mov     rbx, [rax]
0x1800fcec2  mov     [rax], r15
0x1800fcec5  mov     rcx, [rdi+1D8h]; string
0x1800fcecc  call    cs:__imp_WindowsDeleteString
0x1800fced2  lea     rcx, [rbp+arg_10]; this
0x1800fced6  mov     [rdi+1D8h], rbx
0x1800fcedd  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800fcee2  mov     rdx, r14
0x1800fcee5  lea     rcx, [rbp+var_20]
0x1800fcee9  call    ??0?$vector@V?$ComPtr@VFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>(std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>> const &)
0x1800fceee  mov     r9, rax
0x1800fcef1  mov     byte ptr [rsp+50h+var_30], r15b
0x1800fcef6  mov     r8, r13
0x1800fcef9  lea     rdx, [rbp+arg_10]
0x1800fcefd  lea     rcx, [rbp+arg_0]
0x1800fcf01  call    _lambda_a34907c0591b24a770ce58799b827756___operator___std__vector_Microsoft__WRL__ComPtr_WindowsUpdate__Internal__FulfillmentDataInfo__std__allocator_Microsoft__WRL__ComPtr_WindowsUpdate__Internal__FulfillmentDataInfo_______lambda_a79e14d6ab7f8650301fa86b55f17c9a___
0x1800fcf06  mov     rbx, [rax]
0x1800fcf09  mov     [rax], r15
0x1800fcf0c  mov     rcx, [rdi+1C8h]; string
0x1800fcf13  call    cs:__imp_WindowsDeleteString
0x1800fcf19  lea     rcx, [rbp+arg_10]; this
0x1800fcf1d  mov     [rdi+1C8h], rbx
0x1800fcf24  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800fcf29  mov     rdx, r14
0x1800fcf2c  lea     rcx, [rbp+var_20]
0x1800fcf30  call    ??0?$vector@V?$ComPtr@VFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>(std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>> const &)
0x1800fcf35  mov     r9, rax
0x1800fcf38  mov     byte ptr [rsp+50h+var_30], r15b
0x1800fcf3d  mov     r8, rsi
0x1800fcf40  lea     rdx, [rbp+arg_10]
0x1800fcf44  lea     rcx, [rbp+arg_0]
0x1800fcf48  call    _lambda_a34907c0591b24a770ce58799b827756___operator___std__vector_Microsoft__WRL__ComPtr_WindowsUpdate__Internal__FulfillmentDataInfo__std__allocator_Microsoft__WRL__ComPtr_WindowsUpdate__Internal__FulfillmentDataInfo_______lambda_c6cf5d1d65bda51241d118baab488d48___
0x1800fcf4d  mov     rbx, [rax]
0x1800fcf50  mov     [rax], r15
0x1800fcf53  mov     rcx, [rdi+1D0h]; string
0x1800fcf5a  call    cs:__imp_WindowsDeleteString
0x1800fcf60  lea     rcx, [rbp+arg_10]; this
0x1800fcf64  mov     [rdi+1D0h], rbx
0x1800fcf6b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800fcf70  mov     rdx, r14
0x1800fcf73  lea     rcx, [rbp+var_20]
0x1800fcf77  call    ??0?$vector@V?$ComPtr@VFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>(std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>> const &)
0x1800fcf7c  mov     r8, [rbp+arg_8]
0x1800fcf80  lea     rdx, [rbp+arg_10]
0x1800fcf84  mov     r9, rax
0x1800fcf87  mov     byte ptr [rsp+50h+var_30], r15b
0x1800fcf8c  lea     rcx, [rbp+arg_0]
0x1800fcf90  call    _lambda_a34907c0591b24a770ce58799b827756___operator___std__vector_Microsoft__WRL__ComPtr_WindowsUpdate__Internal__FulfillmentDataInfo__std__allocator_Microsoft__WRL__ComPtr_WindowsUpdate__Internal__FulfillmentDataInfo_______lambda_9308f9474e273e348d118dea8d704b75___
0x1800fcf95  mov     rbx, [rax]
0x1800fcf98  mov     [rax], r15
0x1800fcf9b  mov     rcx, [rdi+1E0h]; string
0x1800fcfa2  call    cs:__imp_WindowsDeleteString
0x1800fcfa8  lea     rcx, [rbp+arg_10]; this
0x1800fcfac  mov     [rdi+1E0h], rbx
0x1800fcfb3  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800fcfb8  mov     rbx, [rsp+50h+arg_18]
0x1800fcfc0  add     rsp, 50h
0x1800fcfc4  pop     r15
0x1800fcfc6  pop     r14
0x1800fcfc8  pop     r13
0x1800fcfca  pop     r12
0x1800fcfcc  pop     rdi
0x1800fcfcd  pop     rsi
0x1800fcfce  pop     rbp
0x1800fcfcf  retn
```
