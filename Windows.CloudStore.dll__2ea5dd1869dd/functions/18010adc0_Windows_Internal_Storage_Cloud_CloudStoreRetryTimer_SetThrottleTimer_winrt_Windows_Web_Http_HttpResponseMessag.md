# Windows::Internal::Storage::Cloud::CloudStoreRetryTimer::SetThrottleTimer(winrt::Windows::Web::Http::HttpResponseMessage const &,unsigned __int64,winrt::hstring const &)

- ea: `0x18010adc0`
- end: `0x18010b09e`
- name: `?SetThrottleTimer@CloudStoreRetryTimer@Cloud@Storage@Internal@Windows@@UEAAXAEBUHttpResponseMessage@Http@Web@5winrt@@_KAEBUhstring@9@@Z`
- size: `734`
- prototype: `void(Windows::Internal::Storage::Cloud::CloudStoreRetryTimer *__hidden this, const struct winrt::Windows::Web::Http::HttpResponseMessage *, unsigned __int64, const struct winrt::hstring *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x18006e3e8`
- `0x18006ef0c`
- `0x180079cdc`
- `0x1800ac3a4`
- `0x1800b3588`
- `0x1800c3fac`
- `0x1800c67cc`
- `0x1800c68ac`
- `0x18010adc0`
- `0x18010b0a4`
- `0x18010b0c4`
- `0x180143928`
- `0x180167e58`
- `0x1801b7dd0`
- `0x1801b7f20`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010af7d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010afad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010afe3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010b017`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010af7d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010afad`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010afe3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18010b017`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall Windows::Internal::Storage::Cloud::CloudStoreRetryTimer::SetThrottleTimer(
        Windows::Internal::Storage::Cloud::CloudStoreRetryTimer *this,
        const struct winrt::Windows::Web::Http::HttpResponseMessage *a2,
        __int64 a3,
        const struct winrt::hstring *a4)
{
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // rbx
  int v11; // edi
  __int64 v12; // rax
  char v13; // bl
  __int64 v14; // rax
  __int64 v15; // rsi
  __int64 v16; // rax
  __int64 View; // rbx
  winrt::hstring *v18; // rax
  const WCHAR *v19; // rax
  bool v20; // bl
  winrt::hstring *v21; // rax
  const WCHAR *v22; // rax
  winrt::hstring *v23; // rax
  const WCHAR *v24; // rax
  winrt::hstring *v25; // rax
  const WCHAR *v26; // rax
  int v27; // [rsp+30h] [rbp-59h] BYREF
  __int64 v28; // [rsp+38h] [rbp-51h] BYREF
  _BYTE v29[8]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v30[8]; // [rsp+48h] [rbp-41h] BYREF
  _BYTE v31[8]; // [rsp+50h] [rbp-39h] BYREF
  int v32; // [rsp+58h] [rbp-31h] BYREF
  __int128 v33; // [rsp+60h] [rbp-29h]
  _BYTE v34[8]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v35[8]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v36[96]; // [rsp+80h] [rbp-9h] BYREF

  v27 = 0;
  v28 = 0;
  v8 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>::GetView(
                    a2,
                    v30);
  v32 = 0;
  v33 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 128LL))(v8, &v28);
  winrt::check_hresult(&v27, v9, &v32);
  v10 = v28;
  v11 = 8;
  v27 = 8;
  winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)v30);
  if ( !v10
    || (v12 = winrt::impl::consume_Windows_Internal_Storage_Cloud_Downloader_IDownloadResult<winrt::Windows::Internal::Storage::Cloud::Downloader::IDownloadResult>::ErrorDetails(
                &v28,
                v29),
        v11 = 9,
        v27 = 9,
        v13 = 1,
        *(__int64 *)winrt::impl::consume_Windows_Foundation_IReference<winrt::Windows::Foundation::IReference<std::chrono::duration<__int64,std::ratio<1,10000000>>>,std::chrono::duration<__int64,std::ratio<1,10000000>>>::Value(
                      v12,
                      v31) <= 0) )
  {
    v13 = 0;
  }
  if ( (v11 & 1) != 0 )
  {
    v11 &= ~1u;
    v27 = v11;
    winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)v29);
  }
  if ( v13 )
  {
    v14 = winrt::impl::consume_Windows_Internal_Storage_Cloud_Downloader_IDownloadResult<winrt::Windows::Internal::Storage::Cloud::Downloader::IDownloadResult>::ErrorDetails(
            &v28,
            v31);
    v15 = 864000000000LL;
    if ( *(__int64 *)winrt::impl::consume_Windows_Foundation_IReference<winrt::Windows::Foundation::IReference<std::chrono::duration<__int64,std::ratio<1,10000000>>>,std::chrono::duration<__int64,std::ratio<1,10000000>>>::Value(
                       v14,
                       v34) < 864000000000LL )
    {
      v16 = winrt::impl::consume_Windows_Internal_Storage_Cloud_Downloader_IDownloadResult<winrt::Windows::Internal::Storage::Cloud::Downloader::IDownloadResult>::ErrorDetails(
              &v28,
              v29);
      v11 |= 2u;
      v27 = v11;
      v15 = *(_QWORD *)winrt::impl::consume_Windows_Foundation_IReference<winrt::Windows::Foundation::IReference<std::chrono::duration<__int64,std::ratio<1,10000000>>>,std::chrono::duration<__int64,std::ratio<1,10000000>>>::Value(
                         v16,
                         v35);
    }
    if ( (v11 & 2) != 0 )
    {
      v11 &= ~2u;
      v27 = v11;
      winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)v29);
    }
    winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)v31);
    View = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>::GetView(
             a2,
             v31);
    winrt::param::hstring::hstring((winrt::param::hstring *)v36, L"X-AFS-RetryScope");
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Web::Http::Headers::HttpResponseHeaderCollection,winrt::hstring,winrt::hstring>::TryLookup(
      View,
      &v32,
      v36);
    winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)v31);
    if ( (_BYTE)v33 && *(_QWORD *)std::optional<winrt::hstring>::value(&v32) )
    {
      v18 = (winrt::hstring *)std::optional<winrt::hstring>::value(&v32);
      v19 = winrt::hstring::c_str(v18);
      v20 = 1;
      if ( CompareStringOrdinal(L"GlobalFG", -1, v19, -1, 1) != 2 )
      {
        v21 = (winrt::hstring *)std::optional<winrt::hstring>::value(&v32);
        v22 = winrt::hstring::c_str(v21);
        v20 = CompareStringOrdinal(L"TypeFG", -1, v22, -1, 1) == 2;
      }
      v23 = (winrt::hstring *)std::optional<winrt::hstring>::value(&v32);
      v24 = winrt::hstring::c_str(v23);
      if ( CompareStringOrdinal(L"GlobalFG", -1, v24, -1, 1) == 2
        || (v25 = (winrt::hstring *)std::optional<winrt::hstring>::value(&v32),
            v26 = winrt::hstring::c_str(v25),
            CompareStringOrdinal(L"GlobalBG", -1, v26, -1, 1) == 2) )
      {
        winrt::hstring::hstring((winrt::hstring *)v29, L"Global");
        v11 |= 4u;
        v27 = v11;
        a4 = (const struct winrt::hstring *)v29;
      }
      winrt::hstring::hstring((winrt::hstring *)v30, a4);
      if ( (v11 & 4) != 0 )
        winrt::handle_type<winrt::impl::hstring_traits>::close(v29);
      Windows::Internal::Storage::Cloud::CloudStoreRetryTimer::SetRetryAfter(
        this,
        (const struct winrt::hstring *)v30,
        v20,
        v15 + a3);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v30);
    }
    std::_Optional_destruct_base<winrt::hstring,0>::~_Optional_destruct_base<winrt::hstring,0>(&v32);
  }
  winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory((winrt::Windows::Web::Http::IHttpRequestMessageFactory *)&v28);
}

```

## disassembly

```asm
0x18010adc0  push    rbp
0x18010adc2  push    rbx
0x18010adc3  push    rsi
0x18010adc4  push    rdi
0x18010adc5  push    r12
0x18010adc7  push    r13
0x18010adc9  push    r14
0x18010adcb  push    r15
0x18010adcd  lea     rbp, [rsp-1Fh]
0x18010add2  sub     rsp, 0A8h
0x18010add9  mov     r14, r9
0x18010addc  mov     r12, r8
0x18010addf  mov     r15, rdx
0x18010ade2  mov     r13, rcx
0x18010ade5  xor     esi, esi
0x18010ade7  mov     [rbp+57h+var_B0], esi
0x18010adea  lea     rdx, [rbp+57h+var_98]
0x18010adee  mov     rcx, r15
0x18010adf1  call    ?GetView@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UProfileDataItemDataItem@Downloader@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UProfileDataItemDataItem@Downloader@Cloud@Storage@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>::GetView(void)
0x18010adf6  nop
0x18010adf7  mov     [rbp+57h+var_A8], rsi
0x18010adfb  mov     rcx, [rax]
0x18010adfe  mov     [rbp+57h+var_88], esi
0x18010ae01  xorps   xmm0, xmm0
0x18010ae04  movdqu  [rbp+57h+var_80], xmm0
0x18010ae09  mov     rax, [rcx]
0x18010ae0c  lea     rdx, [rbp+57h+var_A8]
0x18010ae10  mov     rax, [rax+80h]
0x18010ae17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ae1c  lea     r8, [rbp+57h+var_88]
0x18010ae20  mov     edx, eax
0x18010ae22  lea     rcx, [rbp+57h+var_B0]
0x18010ae26  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18010ae2b  mov     rbx, [rbp+57h+var_A8]
0x18010ae2f  mov     [rbp+57h+var_A8], rbx
0x18010ae33  lea     edi, [rsi+8]
0x18010ae36  mov     [rbp+57h+var_B0], edi
0x18010ae39  lea     rcx, [rbp+57h+var_98]; this
0x18010ae3d  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x18010ae42  test    rbx, rbx
0x18010ae45  jz      short loc_18010AE6E
0x18010ae47  lea     rdx, [rbp+57h+var_A0]
0x18010ae4b  lea     rcx, [rbp+57h+var_A8]
0x18010ae4f  call    ?ErrorDetails@?$consume_Windows_Internal_Storage_Cloud_Downloader_IDownloadResult@UIDownloadResult@Downloader@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_Downloader_IDownloadResult<winrt::Windows::Internal::Storage::Cloud::Downloader::IDownloadResult>::ErrorDetails(void)
0x18010ae54  nop
0x18010ae55  lea     edi, [rsi+9]
0x18010ae58  mov     [rbp+57h+var_B0], edi
0x18010ae5b  lea     rdx, [rbp+57h+var_90]
0x18010ae5f  mov     rcx, rax
0x18010ae62  call    ?Value@?$consume_Windows_Foundation_IReference@U?$IReference@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@Foundation@Windows@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IReference<winrt::Windows::Foundation::IReference<std::chrono::duration<__int64,std::ratio<1,10000000>>>,std::chrono::duration<__int64,std::ratio<1,10000000>>>::Value(void)
0x18010ae67  cmp     [rax], rsi
0x18010ae6a  mov     bl, 1
0x18010ae6c  jg      short loc_18010AE71
0x18010ae6e  mov     bl, sil
0x18010ae71  test    dil, 1
0x18010ae75  jz      short loc_18010AE86
0x18010ae77  and     edi, 0FFFFFFFEh
0x18010ae7a  mov     [rbp+57h+var_B0], edi
0x18010ae7d  lea     rcx, [rbp+57h+var_A0]; this
0x18010ae81  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x18010ae86  test    bl, bl
0x18010ae88  jz      loc_18010B081
0x18010ae8e  lea     rdx, [rbp+57h+var_90]
0x18010ae92  lea     rcx, [rbp+57h+var_A8]
0x18010ae96  call    ?ErrorDetails@?$consume_Windows_Internal_Storage_Cloud_Downloader_IDownloadResult@UIDownloadResult@Downloader@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_Downloader_IDownloadResult<winrt::Windows::Internal::Storage::Cloud::Downloader::IDownloadResult>::ErrorDetails(void)
0x18010ae9b  nop
0x18010ae9c  lea     rdx, [rbp+57h+var_70]
0x18010aea0  mov     rcx, rax
0x18010aea3  call    ?Value@?$consume_Windows_Foundation_IReference@U?$IReference@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@Foundation@Windows@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IReference<winrt::Windows::Foundation::IReference<std::chrono::duration<__int64,std::ratio<1,10000000>>>,std::chrono::duration<__int64,std::ratio<1,10000000>>>::Value(void)
0x18010aea8  mov     rsi, 0C92A69C000h
0x18010aeb2  cmp     [rax], rsi
0x18010aeb5  jge     short loc_18010AEDA
0x18010aeb7  lea     rdx, [rbp+57h+var_A0]
0x18010aebb  lea     rcx, [rbp+57h+var_A8]
0x18010aebf  call    ?ErrorDetails@?$consume_Windows_Internal_Storage_Cloud_Downloader_IDownloadResult@UIDownloadResult@Downloader@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_Downloader_IDownloadResult<winrt::Windows::Internal::Storage::Cloud::Downloader::IDownloadResult>::ErrorDetails(void)
0x18010aec4  nop
0x18010aec5  or      edi, 2
0x18010aec8  mov     [rbp+57h+var_B0], edi
0x18010aecb  lea     rdx, [rbp+57h+var_68]
0x18010aecf  mov     rcx, rax
0x18010aed2  call    ?Value@?$consume_Windows_Foundation_IReference@U?$IReference@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@Foundation@Windows@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IReference<winrt::Windows::Foundation::IReference<std::chrono::duration<__int64,std::ratio<1,10000000>>>,std::chrono::duration<__int64,std::ratio<1,10000000>>>::Value(void)
0x18010aed7  mov     rsi, [rax]
0x18010aeda  test    dil, 2
0x18010aede  jz      short loc_18010AEF0
0x18010aee0  and     edi, 0FFFFFFFDh
0x18010aee3  mov     [rbp+57h+var_B0], edi
0x18010aee6  lea     rcx, [rbp+57h+var_A0]; this
0x18010aeea  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x18010aeef  nop
0x18010aef0  lea     rcx, [rbp+57h+var_90]; this
0x18010aef4  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x18010aef9  lea     rdx, [rbp+57h+var_90]
0x18010aefd  mov     rcx, r15
0x18010af00  call    ?GetView@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UProfileDataItemDataItem@Downloader@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UProfileDataItemDataItem@Downloader@Cloud@Storage@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>::GetView(void)
0x18010af05  mov     rbx, rax
0x18010af08  lea     rdx, aXAfsRetryscope; "X-AFS-RetryScope"
0x18010af0f  lea     rcx, [rbp+57h+var_60]; this
0x18010af13  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18010af18  lea     r8, [rbp+57h+var_60]
0x18010af1c  lea     rdx, [rbp+57h+var_88]
0x18010af20  mov     rcx, rbx
0x18010af23  call    ?TryLookup@?$consume_Windows_Foundation_Collections_IMap@UHttpResponseHeaderCollection@Headers@Http@Web@Windows@winrt@@Uhstring@6@U76@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Web::Http::Headers::HttpResponseHeaderCollection,winrt::hstring,winrt::hstring>::TryLookup(winrt::param::hstring const &)
0x18010af28  nop
0x18010af29  lea     rcx, [rbp+57h+var_90]; this
0x18010af2d  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x18010af32  cmp     byte ptr [rbp+57h+var_80], 0
0x18010af36  jz      loc_18010B077
0x18010af3c  lea     rcx, [rbp+57h+var_88]
0x18010af40  call    ?value@?$optional@Uhstring@winrt@@@std@@QEGAAAEAUhstring@winrt@@XZ; std::optional<winrt::hstring>::value(void)
0x18010af45  cmp     qword ptr [rax], 0
0x18010af49  jz      loc_18010B077
0x18010af4f  lea     rcx, [rbp+57h+var_88]
0x18010af53  call    ?value@?$optional@Uhstring@winrt@@@std@@QEGAAAEAUhstring@winrt@@XZ; std::optional<winrt::hstring>::value(void)
0x18010af58  mov     rcx, rax; this
0x18010af5b  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18010af60  mov     ebx, 1
0x18010af65  mov     [rsp+0E0h+bIgnoreCase], ebx; bIgnoreCase
0x18010af69  or      r15d, 0FFFFFFFFh
0x18010af6d  mov     r9d, r15d; cchCount2
0x18010af70  mov     r8, rax; lpString2
0x18010af73  mov     edx, r15d; cchCount1
0x18010af76  lea     rcx, aGlobalfg; "GlobalFG"
0x18010af7d  call    cs:__imp_CompareStringOrdinal
0x18010af83  cmp     eax, 2
0x18010af86  jz      short loc_18010AFBA
0x18010af88  lea     rcx, [rbp+57h+var_88]
0x18010af8c  call    ?value@?$optional@Uhstring@winrt@@@std@@QEGAAAEAUhstring@winrt@@XZ; std::optional<winrt::hstring>::value(void)
0x18010af91  mov     rcx, rax; this
0x18010af94  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18010af99  mov     [rsp+0E0h+bIgnoreCase], ebx; bIgnoreCase
0x18010af9d  mov     r9d, r15d; cchCount2
0x18010afa0  mov     r8, rax; lpString2
0x18010afa3  mov     edx, r15d; cchCount1
0x18010afa6  lea     rcx, aTypefg; "TypeFG"
0x18010afad  call    cs:__imp_CompareStringOrdinal
0x18010afb3  cmp     eax, 2
0x18010afb6  jz      short loc_18010AFBA
0x18010afb8  xor     bl, bl
0x18010afba  lea     rcx, [rbp+57h+var_88]
0x18010afbe  call    ?value@?$optional@Uhstring@winrt@@@std@@QEGAAAEAUhstring@winrt@@XZ; std::optional<winrt::hstring>::value(void)
0x18010afc3  mov     rcx, rax; this
0x18010afc6  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18010afcb  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x18010afd3  mov     r9d, r15d; cchCount2
0x18010afd6  mov     r8, rax; lpString2
0x18010afd9  mov     edx, r15d; cchCount1
0x18010afdc  lea     rcx, aGlobalfg; "GlobalFG"
0x18010afe3  call    cs:__imp_CompareStringOrdinal
0x18010afe9  cmp     eax, 2
0x18010afec  jz      short loc_18010B022
0x18010afee  lea     rcx, [rbp+57h+var_88]
0x18010aff2  call    ?value@?$optional@Uhstring@winrt@@@std@@QEGAAAEAUhstring@winrt@@XZ; std::optional<winrt::hstring>::value(void)
0x18010aff7  mov     rcx, rax; this
0x18010affa  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18010afff  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x18010b007  mov     r9d, r15d; cchCount2
0x18010b00a  mov     r8, rax; lpString2
0x18010b00d  mov     edx, r15d; cchCount1
0x18010b010  lea     rcx, aGlobalbg; "GlobalBG"
0x18010b017  call    cs:__imp_CompareStringOrdinal
0x18010b01d  cmp     eax, 2
0x18010b020  jnz     short loc_18010B03D
0x18010b022  lea     rdx, aGlobal; "Global"
0x18010b029  lea     rcx, [rbp+57h+var_A0]; this
0x18010b02d  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18010b032  nop
0x18010b033  or      edi, 4
0x18010b036  mov     [rbp+57h+var_B0], edi
0x18010b039  lea     r14, [rbp+57h+var_A0]
0x18010b03d  mov     rdx, r14; struct winrt::hstring *
0x18010b040  lea     rcx, [rbp+57h+var_98]; this
0x18010b044  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18010b049  nop
0x18010b04a  test    dil, 4
0x18010b04e  jz      short loc_18010B059
0x18010b050  lea     rcx, [rbp+57h+var_A0]
0x18010b054  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18010b059  lea     r9, [rsi+r12]; unsigned __int64
0x18010b05d  mov     r8b, bl; bool
0x18010b060  lea     rdx, [rbp+57h+var_98]; struct winrt::hstring *
0x18010b064  mov     rcx, r13; this
0x18010b067  call    ?SetRetryAfter@CloudStoreRetryTimer@Cloud@Storage@Internal@Windows@@AEAAXAEBUhstring@winrt@@_N_K@Z; Windows::Internal::Storage::Cloud::CloudStoreRetryTimer::SetRetryAfter(winrt::hstring const &,bool,unsigned __int64)
0x18010b06c  nop
0x18010b06d  lea     rcx, [rbp+57h+var_98]
0x18010b071  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18010b076  nop
0x18010b077  lea     rcx, [rbp+57h+var_88]
0x18010b07b  call    ??1?$_Optional_destruct_base@Uhstring@winrt@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<winrt::hstring,0>::~_Optional_destruct_base<winrt::hstring,0>(void)
0x18010b080  nop
0x18010b081  lea     rcx, [rbp+57h+var_A8]; this
0x18010b085  call    ??1IHttpRequestMessageFactory@Http@Web@Windows@winrt@@QEAA@XZ; winrt::Windows::Web::Http::IHttpRequestMessageFactory::~IHttpRequestMessageFactory(void)
0x18010b08a  add     rsp, 0A8h
0x18010b091  pop     r15
0x18010b093  pop     r14
0x18010b095  pop     r13
0x18010b097  pop     r12
0x18010b099  pop     rdi
0x18010b09a  pop     rsi
0x18010b09b  pop     rbx
0x18010b09c  pop     rbp
0x18010b09d  retn
```
