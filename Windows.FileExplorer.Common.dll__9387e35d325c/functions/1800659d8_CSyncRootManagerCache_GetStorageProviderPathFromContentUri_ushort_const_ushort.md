# CSyncRootManagerCache::GetStorageProviderPathFromContentUri(ushort const *,ushort * *)

- ea: `0x1800659d8`
- end: `0x180065d24`
- name: `?GetStorageProviderPathFromContentUri@CSyncRootManagerCache@@QEAAJPEBGPEAPEAG@Z`
- size: `844`
- prototype: `__int64 __fastcall(CSyncRootManagerCache *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180065970`

## callees

- `0x180004a54`
- `0x1800077c8`
- `0x1800092d0`
- `0x18000964c`
- `0x18000bc30`
- `0x1800192a0`
- `0x18001d3e0`
- `0x180024198`
- `0x180032894`
- `0x180037780`
- `0x1800600c8`
- `0x18006052c`
- `0x1800659d8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180065adf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180065aee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180065adf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180065aee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180065a45`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180065a45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065c59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065c59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065c2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065c8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065cbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065c2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065c8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065cbc`

## string_xrefs

- `0x180065a25`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180065ac9`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180065b4c`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180065b9c`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180065c78`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180065b74`: `Windows.Storage.Provider.StorageProviderGetPathForContentUriResult`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSyncRootManagerCache::GetStorageProviderPathFromContentUri(
        RTL_SRWLOCK *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  RTL_SRWLOCK *v9; // rbx
  char *i; // rdi
  __int64 v11; // rax
  CStorageProviderRootsCache *v12; // rdi
  int StorageProviderInfo; // eax
  int v14; // edi
  struct IStorageProviderInfo *v15; // rbx
  __int64 (__fastcall *v16)(struct IStorageProviderInfo *, GUID *, __int64 *); // rdi
  int v17; // eax
  int PathForContentUri; // eax
  __int64 v19; // rdx
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64); // rdi
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  __int64 v27; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  int v31; // [rsp+20h] [rbp-49h] BYREF
  __int64 v32; // [rsp+28h] [rbp-41h] BYREF
  __int64 v33; // [rsp+30h] [rbp-39h] BYREF
  HSTRING string; // [rsp+38h] [rbp-31h] BYREF
  struct IStorageProviderInfo *v35; // [rsp+40h] [rbp-29h] BYREF
  int v36; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v37[2]; // [rsp+50h] [rbp-19h] BYREF
  char v38; // [rsp+60h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  __int64 v40; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v37[0] = a2;
  *a3 = 0;
  v6 = CSyncRootManagerCache::_EnsureCachedValuesReaderModeWrapper(this, 0xFFFFFFFFLL);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1009,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v6,
      v31);
    return v7;
  }
  v35 = 0;
  AcquireSRWLockShared(this + 3);
  v9 = *(RTL_SRWLOCK **)winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,std::vector<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>,winrt::impl::single_threaded_collection_base>,winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>>::abi_guard::abi_guard(
                          &v32,
                          this);
  v37[1] = v9;
  v38 = 1;
  for ( i = 0; ; ++i )
  {
    if ( i >= this[5].Ptr )
      goto LABEL_9;
    string = (HSTRING)a2;
    LOBYTE(v31) = 0;
    v11 = lambda_8fce507a347e82d5712887a44dd2e036_::_lambda_8fce507a347e82d5712887a44dd2e036_(
            &hstringHeader,
            &string,
            *((_QWORD *)this[4].Ptr + (_QWORD)i),
            &v31);
    lambda_8fce507a347e82d5712887a44dd2e036_::operator()(v11);
    if ( (_BYTE)v31 )
      break;
  }
  v12 = (CStorageProviderRootsCache *)*((_QWORD *)this[4].Ptr + (_QWORD)i);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v35);
  StorageProviderInfo = CStorageProviderRootsCache::GetStorageProviderInfo(v12, &v35);
  v14 = StorageProviderInfo;
  if ( StorageProviderInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1015,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)StorageProviderInfo,
      v31);
    ReleaseSRWLockShared(v9 + 3);
LABEL_28:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v35);
    return (unsigned int)v14;
  }
LABEL_9:
  ReleaseSRWLockShared(v9 + 3);
  v15 = v35;
  if ( !v35 )
  {
    v14 = -2147024881;
    goto LABEL_28;
  }
  v33 = 0;
  v16 = *(__int64 (__fastcall **)(struct IStorageProviderInfo *, GUID *, __int64 *))(*(_QWORD *)v35 + 272LL);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v33);
  v17 = v16(v15, &GUID_b29806d1_8be0_4962_8bb6_0d4c2e14d47a, &v33);
  v14 = v17;
  if ( v17 < 0 )
  {
    if ( v17 != -2147023728 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1020,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)(unsigned int)v17,
        v31);
LABEL_27:
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v33);
      goto LABEL_28;
    }
    goto LABEL_30;
  }
  v32 = 0;
  v40 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Storage.Provider.StorageProviderGetPathForContentUriResult",
    0x43u,
    0x42u);
  PathForContentUri = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Provider::IStorageProviderGetPathForContentUriResult>>(
                        v40,
                        &v32);
  v14 = PathForContentUri;
  if ( PathForContentUri < 0 )
  {
    v19 = 4132;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)PathForContentUri,
      v31);
    goto LABEL_26;
  }
  v20 = v33;
  v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v33 + 48LL);
  v22 = v32;
  v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v37);
  v14 = v21(v20, *(_QWORD *)(v23 + 24), v22);
  if ( v14 < 0 )
    goto LABEL_26;
  v36 = 0;
  PathForContentUri = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 48LL))(v32, &v36);
  v14 = PathForContentUri;
  if ( PathForContentUri < 0 )
  {
    v19 = 4136;
    goto LABEL_16;
  }
  if ( !v36 )
  {
    string = 0;
    v24 = v32;
    v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v26 = v25(v24, &string);
    v14 = v26;
    if ( v26 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v26 = _AllocString<CTCoAllocPolicy>(v30, v29, StringRawBuffer, a3);
      v14 = v26;
      if ( v26 >= 0 )
      {
        WindowsDeleteString(string);
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v32);
LABEL_30:
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v35);
        return 0;
      }
      v27 = 4141;
    }
    else
    {
      v27 = 4140;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v26,
      v31);
    WindowsDeleteString(string);
    string = 0;
LABEL_26:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v32);
    goto LABEL_27;
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v35);
  return 2147942402LL;
}

```

## disassembly

```asm
0x1800659d8  push    rbp
0x1800659da  push    rbx
0x1800659db  push    rsi
0x1800659dc  push    rdi
0x1800659dd  push    r12
0x1800659df  push    r14
0x1800659e1  push    r15
0x1800659e3  lea     rbp, [rsp-27h]
0x1800659e8  sub     rsp, 90h
0x1800659ef  mov     rax, cs:__security_cookie
0x1800659f6  xor     rax, rsp
0x1800659f9  mov     [rbp+57h+var_38], rax
0x1800659fd  mov     r15, r8
0x180065a00  mov     r14, rdx
0x180065a03  mov     rsi, rcx
0x180065a06  mov     [rbp+57h+var_70], rdx
0x180065a0a  xor     r12d, r12d
0x180065a0d  mov     [r8], r12
0x180065a10  or      edx, 0FFFFFFFFh
0x180065a13  call    ?_EnsureCachedValuesReaderModeWrapper@CSyncRootManagerCache@@AEAAJW4SPGSP_FLAGS@@@Z; CSyncRootManagerCache::_EnsureCachedValuesReaderModeWrapper(SPGSP_FLAGS)
0x180065a18  mov     ebx, eax
0x180065a1a  test    eax, eax
0x180065a1c  jns     short loc_180065A3D
0x180065a1e  mov     rcx, [rbp+5Fh]; this
0x180065a22  mov     r9d, eax; char *
0x180065a25  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180065a2c  mov     edx, 1009h; void *
0x180065a31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065a36  mov     eax, ebx
0x180065a38  jmp     loc_180065D06
0x180065a3d  mov     [rbp+57h+var_80], r12
0x180065a41  lea     rcx, [rsi+18h]; SRWLock
0x180065a45  call    cs:__imp_AcquireSRWLockShared
0x180065a4b  mov     rdx, rsi
0x180065a4e  lea     rcx, [rbp+57h+var_98]
0x180065a52  call    ??0abi_guard@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@V?$vector@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@V?$allocator@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@3@Ucollection_version@23@@winrt@@U?$IIterator@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@QEAA@AEAUiterator@?$iterable_base@U?$vector_impl@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@V?$vector@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@V?$allocator@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@3@Ucollection_version@23@@3@@Z; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,std::vector<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>,winrt::impl::single_threaded_collection_base>,winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>>::abi_guard::abi_guard(winrt::iterable_base<winrt::impl::vector_impl<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,std::vector<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>,winrt::impl::single_threaded_collection_base>,winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,winrt::impl::collection_version>::iterator &)
0x180065a57  mov     rbx, [rax]
0x180065a5a  mov     [rbp+57h+var_68], rbx
0x180065a5e  mov     [rbp+57h+var_60], 1
0x180065a62  mov     rdi, r12
0x180065a65  cmp     rdi, [rsi+28h]
0x180065a69  jnb     short loc_180065AEA
0x180065a6b  mov     [rbp+57h+string], r14
0x180065a6f  mov     byte ptr [rbp+57h+var_A0], r12b
0x180065a73  mov     r8, [rsi+20h]
0x180065a77  lea     r9, [rbp+57h+var_A0]
0x180065a7b  mov     r8, [r8+rdi*8]
0x180065a7f  lea     rdx, [rbp+57h+string]
0x180065a83  lea     rcx, [rbp+57h+hstringHeader]
0x180065a87  call    _lambda_8fce507a347e82d5712887a44dd2e036____lambda_8fce507a347e82d5712887a44dd2e036_
0x180065a8c  mov     rcx, rax
0x180065a8f  call    _lambda_8fce507a347e82d5712887a44dd2e036___operator__
0x180065a94  cmp     byte ptr [rbp+57h+var_A0], r12b
0x180065a98  jnz     short loc_180065A9F
0x180065a9a  inc     rdi
0x180065a9d  jmp     short loc_180065A65
0x180065a9f  mov     rax, [rsi+20h]
0x180065aa3  mov     rdi, [rax+rdi*8]
0x180065aa7  lea     rcx, [rbp+57h+var_80]
0x180065aab  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065ab0  lea     rdx, [rbp+57h+var_80]; struct IStorageProviderInfo **
0x180065ab4  mov     rcx, rdi; this
0x180065ab7  call    ?GetStorageProviderInfo@CStorageProviderRootsCache@@QEAAJPEAPEAUIStorageProviderInfo@@@Z; CStorageProviderRootsCache::GetStorageProviderInfo(IStorageProviderInfo * *)
0x180065abc  mov     edi, eax
0x180065abe  test    eax, eax
0x180065ac0  jns     short loc_180065AEA
0x180065ac2  mov     rcx, [rbp+5Fh]; this
0x180065ac6  mov     r9d, eax; char *
0x180065ac9  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180065ad0  mov     edx, 1015h; void *
0x180065ad5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065ada  nop
0x180065adb  lea     rcx, [rbx+18h]; SRWLock
0x180065adf  call    cs:__imp_ReleaseSRWLockShared
0x180065ae5  jmp     loc_180065CAB
0x180065aea  lea     rcx, [rbx+18h]; SRWLock
0x180065aee  call    cs:__imp_ReleaseSRWLockShared
0x180065af4  mov     rbx, [rbp+57h+var_80]
0x180065af8  test    rbx, rbx
0x180065afb  jnz     short loc_180065B07
0x180065afd  mov     edi, 8007000Fh
0x180065b02  jmp     loc_180065CAB
0x180065b07  mov     [rbp+57h+var_90], r12
0x180065b0b  mov     rax, [rbx]
0x180065b0e  mov     rdi, [rax+110h]
0x180065b15  lea     rcx, [rbp+57h+var_90]
0x180065b19  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065b1e  lea     r8, [rbp+57h+var_90]
0x180065b22  lea     rdx, _GUID_b29806d1_8be0_4962_8bb6_0d4c2e14d47a
0x180065b29  mov     rcx, rbx
0x180065b2c  mov     rax, rdi
0x180065b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065b34  mov     edi, eax
0x180065b36  test    eax, eax
0x180065b38  jns     short loc_180065B62
0x180065b3a  cmp     eax, 80070490h
0x180065b3f  jz      loc_180065CCD
0x180065b45  mov     rcx, [rbp+5Fh]; this
0x180065b49  mov     r9d, eax; char *
0x180065b4c  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180065b53  mov     edx, 1020h; void *
0x180065b58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065b5d  jmp     loc_180065CA1
0x180065b62  mov     [rbp+57h+var_98], r12
0x180065b66  mov     [rbp+57h+var_40], r12
0x180065b6a  mov     r9d, 42h ; 'B'; unsigned int
0x180065b70  lea     r8d, [r9+1]; unsigned int
0x180065b74  lea     rdx, ?RuntimeClass_Windows_Storage_Provider_StorageProviderGetPathForContentUriResult@@3QBGB; "Windows.Storage.Provider.StorageProvide"...
0x180065b7b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180065b7f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180065b84  lea     rdx, [rbp+57h+var_98]
0x180065b88  mov     rcx, [rbp+57h+var_40]
0x180065b8c  call    ??$ActivateInstance@V?$ComPtr@UIStorageProviderGetPathForContentUriResult@Provider@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIStorageProviderGetPathForContentUriResult@Provider@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Provider::IStorageProviderGetPathForContentUriResult>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Provider::IStorageProviderGetPathForContentUriResult>>)
0x180065b91  mov     edi, eax
0x180065b93  test    eax, eax
0x180065b95  jns     short loc_180065BB4
0x180065b97  mov     edx, 1024h; void *
0x180065b9c  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180065ba3  mov     r9d, eax; char *
0x180065ba6  mov     rcx, [rbp+5Fh]; this
0x180065baa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065baf  jmp     loc_180065C97
0x180065bb4  mov     rsi, [rbp+57h+var_90]
0x180065bb8  mov     rax, [rsi]
0x180065bbb  mov     rdi, [rax+30h]
0x180065bbf  mov     rbx, [rbp+57h+var_98]
0x180065bc3  lea     rdx, [rbp+57h+var_70]
0x180065bc7  lea     rcx, [rbp+57h+hstringHeader]
0x180065bcb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180065bd0  nop
0x180065bd1  mov     r8, rbx
0x180065bd4  mov     rdx, [rax+18h]
0x180065bd8  mov     rcx, rsi
0x180065bdb  mov     rax, rdi
0x180065bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065be3  mov     edi, eax
0x180065be5  test    eax, eax
0x180065be7  js      loc_180065C97
0x180065bed  mov     [rbp+57h+var_78], r12d
0x180065bf1  mov     rcx, [rbp+57h+var_98]
0x180065bf5  mov     rax, [rcx]
0x180065bf8  lea     rdx, [rbp+57h+var_78]
0x180065bfc  mov     rax, [rax+30h]
0x180065c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c05  mov     edi, eax
0x180065c07  test    eax, eax
0x180065c09  jns     short loc_180065C12
0x180065c0b  mov     edx, 1028h
0x180065c10  jmp     short loc_180065B9C
0x180065c12  cmp     [rbp+57h+var_78], r12d
0x180065c16  jnz     loc_180065CE4
0x180065c1c  mov     [rbp+57h+string], r12
0x180065c20  mov     rdi, [rbp+57h+var_98]
0x180065c24  mov     rax, [rdi]
0x180065c27  mov     rbx, [rax+40h]
0x180065c2b  xor     ecx, ecx; string
0x180065c2d  call    cs:__imp_WindowsDeleteString
0x180065c33  mov     [rbp+57h+string], r12
0x180065c37  lea     rdx, [rbp+57h+string]
0x180065c3b  mov     rcx, rdi
0x180065c3e  mov     rax, rbx
0x180065c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c46  mov     edi, eax
0x180065c48  test    eax, eax
0x180065c4a  jns     short loc_180065C53
0x180065c4c  mov     edx, 102Ch
0x180065c51  jmp     short loc_180065C75
0x180065c53  xor     edx, edx; length
0x180065c55  mov     rcx, [rbp+57h+string]; string
0x180065c59  call    cs:__imp_WindowsGetStringRawBuffer
0x180065c5f  mov     r9, r15
0x180065c62  mov     r8, rax
0x180065c65  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180065c6a  mov     edi, eax
0x180065c6c  test    eax, eax
0x180065c6e  jns     short loc_180065CB8
0x180065c70  mov     edx, 102Dh; void *
0x180065c75  mov     r9d, eax; char *
0x180065c78  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180065c7f  mov     rcx, [rbp+5Fh]; this
0x180065c83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065c88  nop
0x180065c89  mov     rcx, [rbp+57h+string]; string
0x180065c8d  call    cs:__imp_WindowsDeleteString
0x180065c93  mov     [rbp+57h+string], r12
0x180065c97  lea     rcx, [rbp+57h+var_98]
0x180065c9b  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065ca0  nop
0x180065ca1  lea     rcx, [rbp+57h+var_90]
0x180065ca5  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065caa  nop
0x180065cab  lea     rcx, [rbp+57h+var_80]
0x180065caf  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065cb4  mov     eax, edi
0x180065cb6  jmp     short loc_180065D06
0x180065cb8  mov     rcx, [rbp+57h+string]; string
0x180065cbc  call    cs:__imp_WindowsDeleteString
0x180065cc2  nop
0x180065cc3  lea     rcx, [rbp+57h+var_98]
0x180065cc7  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065ccc  nop
0x180065ccd  lea     rcx, [rbp+57h+var_90]
0x180065cd1  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065cd6  nop
0x180065cd7  lea     rcx, [rbp+57h+var_80]
0x180065cdb  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065ce0  xor     eax, eax
0x180065ce2  jmp     short loc_180065D06
0x180065ce4  lea     rcx, [rbp+57h+var_98]
0x180065ce8  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065ced  nop
0x180065cee  lea     rcx, [rbp+57h+var_90]
0x180065cf2  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065cf7  nop
0x180065cf8  lea     rcx, [rbp+57h+var_80]
0x180065cfc  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180065d01  mov     eax, 80070002h
0x180065d06  mov     rcx, [rbp+57h+var_38]
0x180065d0a  xor     rcx, rsp; StackCookie
0x180065d0d  call    __security_check_cookie
0x180065d12  add     rsp, 90h
0x180065d19  pop     r15
0x180065d1b  pop     r14
0x180065d1d  pop     r12
0x180065d1f  pop     rdi
0x180065d20  pop     rsi
0x180065d21  pop     rbx
0x180065d22  pop     rbp
0x180065d23  retn
```
