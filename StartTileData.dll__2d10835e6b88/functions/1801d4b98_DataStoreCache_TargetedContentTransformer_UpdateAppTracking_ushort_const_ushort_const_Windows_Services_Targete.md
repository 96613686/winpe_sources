# DataStoreCache::TargetedContentTransformer::UpdateAppTracking(ushort const *,ushort const *,Windows::Services::TargetedContent::ITargetedContentItem *)

- ea: `0x1801d4b98`
- end: `0x1801d4fae`
- name: `?UpdateAppTracking@TargetedContentTransformer@DataStoreCache@@AEAAXPEBG0PEAUITargetedContentItem@TargetedContent@Services@Windows@@@Z`
- size: `1046`
- prototype: `void __fastcall(DataStoreCache::TargetedContentTransformer *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Services::TargetedContent::ITargetedContentItem *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180377748`

## callees

- `0x18001dac0`
- `0x18002dde0`
- `0x18002f1fc`
- `0x1800301cc`
- `0x18004ffc0`
- `0x1800756e4`
- `0x18007ae80`
- `0x18007bc14`
- `0x180095c24`
- `0x1800c5b3c`
- `0x1800d8e48`
- `0x1800f0854`
- `0x1801d4b98`
- `0x1801d4fb4`
- `0x1801d50e0`
- `0x1801d51e0`
- `0x180201e50`
- `0x180379cd0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801d4f60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801d4f60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d4c30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d4d57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d4db9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d4e4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d4e77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d4f6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d4c30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d4d57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d4db9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d4e4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d4e77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d4f6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d4c82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d4eed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d4c82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d4eed`

## string_xrefs

- `0x1801d4c06`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1801d4c59`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1801d4ca4`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1801d4d35`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1801d4d95`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1801d4de3`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1801d4e30`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1801d4ea1`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall DataStoreCache::TargetedContentTransformer::UpdateAppTracking(
        DataStoreCache::TargetedContentTransformer *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 (__fastcall ***a4)(struct Windows::Services::TargetedContent::ITargetedContentItem *, GUID *, HSTRING *))
{
  __int64 v8; // rbx
  __int64 (__fastcall **v9)(struct Windows::Services::TargetedContent::ITargetedContentItem *, GUID *, HSTRING *); // rax
  __int64 (*v10)(void); // rax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r8
  int v14; // eax
  EdgeTileUtils *StringRawBuffer; // rax
  unsigned __int16 **v16; // r8
  int TileIdforNavigationUrl; // eax
  int v18; // eax
  __int64 (__fastcall **v19)(struct Windows::Services::TargetedContent::ITargetedContentItem *, GUID *, HSTRING *); // rax
  int v20; // eax
  HSTRING v21; // rsi
  __int64 (__fastcall *v22)(HSTRING, HSTRING *); // rdi
  int v23; // eax
  HSTRING v24; // rcx
  int v25; // eax
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rdi
  int v27; // eax
  PCWSTR v28; // rax
  __int64 v29; // rbx
  wil *v30; // rcx
  HSTRING string; // [rsp+20h] [rbp-F8h] BYREF
  HSTRING v32; // [rsp+28h] [rbp-F0h] BYREF
  __int64 v33; // [rsp+30h] [rbp-E8h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v35; // [rsp+40h] [rbp-D8h] BYREF
  const WCHAR *v36[2]; // [rsp+48h] [rbp-D0h] BYREF
  const unsigned __int16 *v37; // [rsp+58h] [rbp-C0h] BYREF
  const unsigned __int16 *v38; // [rsp+60h] [rbp-B8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-B0h] BYREF
  RTL_SRWLOCK *v40; // [rsp+80h] [rbp-98h]
  HSTRING_HEADER v41; // [rsp+90h] [rbp-88h] BYREF
  _BYTE v42[32]; // [rsp+B0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v38 = a2;
  v37 = a3;
  v8 = 0;
  v33 = 0;
  v9 = *a4;
  v35 = 0;
  v10 = (__int64 (*)(void))v9[10];
  try
  {
    v11 = v10();
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8B4,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
        (const char *)(unsigned int)v11,
        (int)string);
    if ( (unsigned __int8)DataStoreCache::TargetedContentTransformer::IsEdgeSecondaryTile(retaddr, v35) )
    {
      WindowsDeleteString(0);
      string = 0;
      v14 = DataStoreCache::TargetedContentTransformer::ExtractStringProperty(v12, v35, v13, &string);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8BA,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedconte"
                        "nttransformer.cpp",
          (const char *)(unsigned int)v14,
          (int)string);
      v32 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v32,
        0);
      StringRawBuffer = (EdgeTileUtils *)WindowsGetStringRawBuffer(string, 0);
      TileIdforNavigationUrl = EdgeTileUtils::GetTileIdforNavigationUrl(
                                 StringRawBuffer,
                                 (const unsigned __int16 *)&v32,
                                 v16);
      if ( TileIdforNavigationUrl < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8BC,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedconte"
                        "nttransformer.cpp",
          (const char *)(unsigned int)TileIdforNavigationUrl,
          (int)string);
      v33 = 0;
      v36[0] = (const WCHAR *)v32;
      v36[0] = (const WCHAR *)Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v41, v36)[1].Reserved.Reserved1;
      v40 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge",
        0x34u,
        0x33u);
      SRWLock = v40;
      v18 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,HSTRING__ * &,HSTRING__ * &>(
              &v33,
              &SRWLock,
              v36);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8BE,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedconte"
                        "nttransformer.cpp",
          (const char *)(unsigned int)v18,
          (int)string);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v32);
      WindowsDeleteString(string);
      v8 = v33;
    }
    else
    {
      v19 = *a4;
      string = 0;
      v20 = (*v19)(
              (struct Windows::Services::TargetedContent::ITargetedContentItem *)a4,
              &GUID_2b3a823f_4d5a_4980_a36f_107ca5a7ddbd,
              &string);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8C3,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedconte"
                        "nttransformer.cpp",
          (const char *)(unsigned int)v20,
          (int)string);
      v32 = 0;
      v21 = string;
      v22 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 48LL);
      WindowsDeleteString(0);
      v32 = 0;
      v23 = v22(v21, &v32);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8C6,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedconte"
                        "nttransformer.cpp",
          (const char *)(unsigned int)v23,
          (int)string);
      v24 = v32;
      if ( v32 )
      {
        v33 = 0;
        v36[0] = (const WCHAR *)v32;
        SRWLock = 0;
        v25 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,HSTRING__ * &,HSTRING__ * &>(
                &v33,
                v36,
                &SRWLock);
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x8C9,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcon"
                          "tenttransformer.cpp",
            (const char *)(unsigned int)v25,
            (int)string);
        v8 = v33;
        v24 = v32;
      }
      WindowsDeleteString(v24);
      v32 = 0;
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&string);
    }
    if ( v8 )
    {
      string = 0;
      v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v8 + 56LL);
      WindowsDeleteString(0);
      string = 0;
      v27 = v26(v8, &string);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8D0,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedconte"
                        "nttransformer.cpp",
          (const char *)(unsigned int)v27,
          (int)string);
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 128);
      std::wstring::wstring(&v41, a2);
      std::wstring::wstring(v42, a3);
      v28 = WindowsGetStringRawBuffer(string, 0);
      std::wstring::wstring(&hstringHeader, v28);
      v29 = *(_QWORD *)std::map<std::wstring,DataStoreCache::TargetedContentTransformer::TargetedContentTileInfo>::_Try_emplace<std::wstring,>(
                         (char *)this + 224,
                         v36,
                         &hstringHeader);
      std::wstring::operator=(v29 + 64, &v41);
      std::wstring::operator=(v29 + 96, v42);
      std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(&hstringHeader);
      Windows::Data::Platform::ItemReference<Windows::Data::CuratedTileCollection::TileCollectionContainer>::~ItemReference<Windows::Data::CuratedTileCollection::TileCollectionContainer>(&v41);
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      WindowsDeleteString(string);
    }
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v35);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v33);
  }
  catch ( ... )
  {
    LODWORD(v33) = wil::ResultFromCaughtException(v30);
    DataStoreTransformerTelemetry::TargetedContentTransformer_AppTrackingUpdateFailed<unsigned short const * &,unsigned short const * &,long>(
      &v38,
      &v37,
      &v33);
  }
}

```

## disassembly

```asm
0x1801d4b98  push    rbx
0x1801d4b9a  push    rsi
0x1801d4b9b  push    rdi
0x1801d4b9c  push    r12
0x1801d4b9e  push    r13
0x1801d4ba0  push    r14
0x1801d4ba2  push    r15
0x1801d4ba4  sub     rsp, 0E0h
0x1801d4bab  mov     rax, cs:__security_cookie
0x1801d4bb2  xor     rax, rsp
0x1801d4bb5  mov     [rsp+118h+var_48], rax
0x1801d4bbd  mov     rdi, r9
0x1801d4bc0  mov     r15, r8
0x1801d4bc3  mov     r12, rdx
0x1801d4bc6  mov     r14, rcx
0x1801d4bc9  mov     [rsp+118h+var_B8], rdx
0x1801d4bce  mov     [rsp+118h+var_C0], r8
0x1801d4bd3  xor     r13d, r13d
0x1801d4bd6  mov     ebx, r13d
0x1801d4bd9  mov     [rsp+118h+var_E8], rbx
0x1801d4bde  mov     rax, [r9]
0x1801d4be1  mov     [rsp+118h+var_D8], r13
0x1801d4be6  lea     rdx, [rsp+118h+var_D8]
0x1801d4beb  mov     rcx, r9
0x1801d4bee  mov     rax, [rax+50h]
0x1801d4bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d4bf7  mov     rcx, [rsp+118h]; this
0x1801d4bff  test    eax, eax
0x1801d4c01  jns     short loc_1801D4C17
0x1801d4c03  mov     r9d, eax; char *
0x1801d4c06  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x1801d4c0d  mov     edx, 8B4h; void *
0x1801d4c12  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801d4c17  mov     rdx, [rsp+118h+var_D8]
0x1801d4c1c  call    ?IsEdgeSecondaryTile@TargetedContentTransformer@DataStoreCache@@AEAA_NPEAU?$IMapView@PEAUHSTRING__@@PEAVTargetedContentValue@TargetedContent@Services@Windows@@@Collections@Foundation@Windows@@@Z; DataStoreCache::TargetedContentTransformer::IsEdgeSecondaryTile(Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Services::TargetedContent::TargetedContentValue *> *)
0x1801d4c21  test    al, al
0x1801d4c23  jz      loc_1801D4D67
0x1801d4c29  mov     [rsp+118h+string], r13
0x1801d4c2e  xor     ecx, ecx; string
0x1801d4c30  call    cs:__imp_WindowsDeleteString
0x1801d4c36  mov     [rsp+118h+string], r13; int
0x1801d4c3b  lea     r9, [rsp+118h+string]
0x1801d4c40  mov     rdx, [rsp+118h+var_D8]
0x1801d4c45  call    ?ExtractStringProperty@TargetedContentTransformer@DataStoreCache@@AEAAJPEAU?$IMapView@PEAUHSTRING__@@PEAVTargetedContentValue@TargetedContent@Services@Windows@@@Collections@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z; DataStoreCache::TargetedContentTransformer::ExtractStringProperty(Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Services::TargetedContent::TargetedContentValue *> *,ushort const *,HSTRING__ * *)
0x1801d4c4a  mov     rcx, [rsp+118h]; this
0x1801d4c52  test    eax, eax
0x1801d4c54  jns     short loc_1801D4C6A
0x1801d4c56  mov     r9d, eax; char *
0x1801d4c59  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x1801d4c60  mov     edx, 8BAh; void *
0x1801d4c65  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801d4c6a  mov     [rsp+118h+var_F0], r13
0x1801d4c6f  xor     edx, edx
0x1801d4c71  lea     rcx, [rsp+118h+var_F0]
0x1801d4c76  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801d4c7b  xor     edx, edx; length
0x1801d4c7d  mov     rcx, [rsp+118h+string]; string
0x1801d4c82  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d4c88  lea     rdx, [rsp+118h+var_F0]; unsigned __int16 *
0x1801d4c8d  mov     rcx, rax; this
0x1801d4c90  call    ?GetTileIdforNavigationUrl@EdgeTileUtils@@YAJPEBGPEAPEAG@Z; EdgeTileUtils::GetTileIdforNavigationUrl(ushort const *,ushort * *)
0x1801d4c95  mov     rcx, [rsp+118h]; this
0x1801d4c9d  test    eax, eax
0x1801d4c9f  jns     short loc_1801D4CB6
0x1801d4ca1  mov     r9d, eax; char *
0x1801d4ca4  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x1801d4cab  mov     edx, 8BCh; void *
0x1801d4cb0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801d4cb6  mov     [rsp+118h+var_E8], r13
0x1801d4cbb  mov     rax, [rsp+118h+var_F0]
0x1801d4cc0  mov     [rsp+118h+var_D0], rax
0x1801d4cc5  lea     rdx, [rsp+118h+var_D0]
0x1801d4cca  lea     rcx, [rsp+118h+var_88]
0x1801d4cd2  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1801d4cd7  nop
0x1801d4cd8  mov     rax, [rax+18h]
0x1801d4cdc  mov     [rsp+118h+var_D0], rax
0x1801d4ce1  mov     [rsp+118h+var_98], r13
0x1801d4ce9  mov     r9d, 33h ; '3'; unsigned int
0x1801d4cef  lea     r8d, [r9+1]; unsigned int
0x1801d4cf3  lea     rdx, aMicrosoftMicro_8; "Microsoft.MicrosoftEdge_8wekyb3d8bbwe!M"...
0x1801d4cfa  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x1801d4cff  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801d4d04  nop
0x1801d4d05  mov     rax, [rsp+118h+var_98]
0x1801d4d0d  mov     [rsp+118h+SRWLock], rax
0x1801d4d12  lea     r8, [rsp+118h+var_D0]
0x1801d4d17  lea     rdx, [rsp+118h+SRWLock]
0x1801d4d1c  lea     rcx, [rsp+118h+var_E8]
0x1801d4d21  call    ??$MakeAndInitialize@VPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTileIdentifier@234@AEAPEAUHSTRING__@@AEAPEAU6@@Details@WRL@Microsoft@@YAJPEAPEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@AEAPEAUHSTRING__@@1@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,HSTRING__ * &,HSTRING__ * &>(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier * *,HSTRING__ * &,HSTRING__ * &)
0x1801d4d26  mov     rcx, [rsp+118h]; this
0x1801d4d2e  test    eax, eax
0x1801d4d30  jns     short loc_1801D4D47
0x1801d4d32  mov     r9d, eax; char *
0x1801d4d35  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x1801d4d3c  mov     edx, 8BEh; void *
0x1801d4d41  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801d4d47  lea     rcx, [rsp+118h+var_F0]
0x1801d4d4c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801d4d51  nop
0x1801d4d52  mov     rcx, [rsp+118h+string]; string
0x1801d4d57  call    cs:__imp_WindowsDeleteString
0x1801d4d5d  mov     rbx, [rsp+118h+var_E8]
0x1801d4d62  jmp     loc_1801D4E60
0x1801d4d67  mov     rax, [rdi]
0x1801d4d6a  mov     [rsp+118h+string], r13; int
0x1801d4d6f  lea     r8, [rsp+118h+string]
0x1801d4d74  lea     rdx, _GUID_2b3a823f_4d5a_4980_a36f_107ca5a7ddbd
0x1801d4d7b  mov     rcx, rdi
0x1801d4d7e  mov     rax, [rax]
0x1801d4d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d4d86  mov     rcx, [rsp+118h]; this
0x1801d4d8e  test    eax, eax
0x1801d4d90  jns     short loc_1801D4DA6
0x1801d4d92  mov     r9d, eax; char *
0x1801d4d95  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x1801d4d9c  mov     edx, 8C3h; void *
0x1801d4da1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801d4da6  mov     [rsp+118h+var_F0], r13
0x1801d4dab  mov     rsi, [rsp+118h+string]
0x1801d4db0  mov     rax, [rsi]
0x1801d4db3  mov     rdi, [rax+30h]
0x1801d4db7  xor     ecx, ecx; string
0x1801d4db9  call    cs:__imp_WindowsDeleteString
0x1801d4dbf  mov     [rsp+118h+var_F0], r13
0x1801d4dc4  lea     rdx, [rsp+118h+var_F0]
0x1801d4dc9  mov     rcx, rsi
0x1801d4dcc  mov     rax, rdi
0x1801d4dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d4dd4  mov     rcx, [rsp+118h]; this
0x1801d4ddc  test    eax, eax
0x1801d4dde  jns     short loc_1801D4DF4
0x1801d4de0  mov     r9d, eax; char *
0x1801d4de3  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x1801d4dea  mov     edx, 8C6h; void *
0x1801d4def  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801d4df4  mov     rcx, [rsp+118h+var_F0]
0x1801d4df9  test    rcx, rcx
0x1801d4dfc  jz      short loc_1801D4E4B
0x1801d4dfe  mov     [rsp+118h+var_E8], r13
0x1801d4e03  mov     [rsp+118h+var_D0], rcx
0x1801d4e08  mov     [rsp+118h+SRWLock], r13
0x1801d4e0d  lea     r8, [rsp+118h+SRWLock]
0x1801d4e12  lea     rdx, [rsp+118h+var_D0]
0x1801d4e17  lea     rcx, [rsp+118h+var_E8]
0x1801d4e1c  call    ??$MakeAndInitialize@VPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTileIdentifier@234@AEAPEAUHSTRING__@@AEAPEAU6@@Details@WRL@Microsoft@@YAJPEAPEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@AEAPEAUHSTRING__@@1@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,HSTRING__ * &,HSTRING__ * &>(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier * *,HSTRING__ * &,HSTRING__ * &)
0x1801d4e21  mov     rcx, [rsp+118h]; this
0x1801d4e29  test    eax, eax
0x1801d4e2b  jns     short loc_1801D4E41
0x1801d4e2d  mov     r9d, eax; char *
0x1801d4e30  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x1801d4e37  mov     edx, 8C9h; void *
0x1801d4e3c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801d4e41  mov     rbx, [rsp+118h+var_E8]
0x1801d4e46  mov     rcx, [rsp+118h+var_F0]; string
0x1801d4e4b  call    cs:__imp_WindowsDeleteString
0x1801d4e51  mov     [rsp+118h+var_F0], r13
0x1801d4e56  lea     rcx, [rsp+118h+string]; void *
0x1801d4e5b  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801d4e60  test    rbx, rbx
0x1801d4e63  jz      loc_1801D4F73
0x1801d4e69  mov     [rsp+118h+string], r13
0x1801d4e6e  mov     rax, [rbx]
0x1801d4e71  mov     rdi, [rax+38h]
0x1801d4e75  xor     ecx, ecx; string
0x1801d4e77  call    cs:__imp_WindowsDeleteString
0x1801d4e7d  mov     [rsp+118h+string], r13; int
0x1801d4e82  lea     rdx, [rsp+118h+string]
0x1801d4e87  mov     rcx, rbx
0x1801d4e8a  mov     rax, rdi
0x1801d4e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d4e92  mov     rcx, [rsp+118h]; this
0x1801d4e9a  test    eax, eax
0x1801d4e9c  jns     short loc_1801D4EB2
0x1801d4e9e  mov     r9d, eax; char *
0x1801d4ea1  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x1801d4ea8  mov     edx, 8D0h; void *
0x1801d4ead  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801d4eb2  lea     rdx, [r14+80h]
0x1801d4eb9  lea     rcx, [rsp+118h+SRWLock]
0x1801d4ebe  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1801d4ec3  nop
0x1801d4ec4  mov     rdx, r12
0x1801d4ec7  lea     rcx, [rsp+118h+var_88]
0x1801d4ecf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801d4ed4  nop
0x1801d4ed5  mov     rdx, r15
0x1801d4ed8  lea     rcx, [rsp+118h+var_68]
0x1801d4ee0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801d4ee5  nop
0x1801d4ee6  xor     edx, edx; length
0x1801d4ee8  mov     rcx, [rsp+118h+string]; string
0x1801d4eed  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d4ef3  mov     rdx, rax
0x1801d4ef6  lea     rcx, [rsp+118h+hstringHeader]
0x1801d4efb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801d4f00  nop
0x1801d4f01  lea     rcx, [r14+0E0h]
0x1801d4f08  lea     r8, [rsp+118h+hstringHeader]
0x1801d4f0d  lea     rdx, [rsp+118h+var_D0]
0x1801d4f12  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UTargetedContentTileInfo@TargetedContentTransformer@DataStoreCache@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UTargetedContentTileInfo@TargetedContentTransformer@DataStoreCache@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UTargetedContentTileInfo@TargetedContentTransformer@DataStoreCache@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,DataStoreCache::TargetedContentTransformer::TargetedContentTileInfo>::_Try_emplace<std::wstring,>(std::wstring &&)
0x1801d4f17  mov     rbx, [rax]
0x1801d4f1a  lea     rdx, [rsp+118h+var_88]
0x1801d4f22  lea     rcx, [rbx+40h]
0x1801d4f26  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801d4f2b  lea     rcx, [rbx+60h]
0x1801d4f2f  lea     rdx, [rsp+118h+var_68]
0x1801d4f37  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801d4f3c  nop
0x1801d4f3d  lea     rcx, [rsp+118h+hstringHeader]; void *
0x1801d4f42  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x1801d4f47  nop
0x1801d4f48  lea     rcx, [rsp+118h+var_88]
0x1801d4f50  call    ??1?$ItemReference@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@@Platform@Data@Windows@@QEAA@XZ; Windows::Data::Platform::ItemReference<Windows::Data::CuratedTileCollection::TileCollectionContainer>::~ItemReference<Windows::Data::CuratedTileCollection::TileCollectionContainer>(void)
0x1801d4f55  nop
0x1801d4f56  mov     rcx, [rsp+118h+SRWLock]; SRWLock
0x1801d4f5b  test    rcx, rcx
0x1801d4f5e  jz      short loc_1801D4F67
0x1801d4f60  call    cs:__imp_ReleaseSRWLockExclusive
0x1801d4f66  nop
0x1801d4f67  mov     rcx, [rsp+118h+string]; string
0x1801d4f6c  call    cs:__imp_WindowsDeleteString
0x1801d4f72  nop
0x1801d4f73  lea     rcx, [rsp+118h+var_D8]; void *
0x1801d4f78  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801d4f7d  nop
0x1801d4f7e  lea     rcx, [rsp+118h+var_E8]; void *
0x1801d4f83  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801d4f88  nop
0x1801d4f89  jmp     short $+2
0x1801d4f8b  mov     rcx, [rsp+118h+var_48]
0x1801d4f93  xor     rcx, rsp; StackCookie
0x1801d4f96  call    __security_check_cookie
0x1801d4f9b  add     rsp, 0E0h
0x1801d4fa2  pop     r15
0x1801d4fa4  pop     r14
0x1801d4fa6  pop     r13
0x1801d4fa8  pop     r12
0x1801d4faa  pop     rdi
0x1801d4fab  pop     rsi
0x1801d4fac  pop     rbx
0x1801d4fad  retn
```
