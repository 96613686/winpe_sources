# DownloadManager::GetDownloadUriAsync(Windows::Foundation::IAsyncOperation<HSTRING__ *> * *)

- ea: `0x180017e20`
- end: `0x180018190`
- name: `?GetDownloadUriAsync@DownloadManager@@MEAAJPEAPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@Z`
- size: `880`
- prototype: `__int64 __fastcall(HSTRING *, _QWORD *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001720`
- `0x180001e7c`
- `0x18000216c`
- `0x180003fc0`
- `0x180004b78`
- `0x18000517c`
- `0x180010c18`
- `0x180011390`
- `0x180013fd0`
- `0x180014840`
- `0x180017e20`
- `0x18001bde0`
- `0x1800260e0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017e8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017e9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017e8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017e9c`

## string_xrefs

- `0x180017ed3`: `DownloadManager::GetDownloadUriAsync`
- `0x180017f11`: `Create Get Sas uri Endpoint`
- `0x180018007`: `Create Get Sas uri Endpoint Url Object`
- `0x1800180f5`: `Get Sas Uri - async http get operation`

## pseudocode

```c
__int64 __fastcall DownloadManager::GetDownloadUriAsync(HSTRING *a1, _QWORD *a2)
{
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v5; // rbx
  PCWSTR v6; // rax
  __int64 v7; // rdx
  int RequestUri; // ebx
  __int64 v9; // r8
  struct Windows::Foundation::IUriRuntimeClass *v10; // rcx
  int v11; // r9d
  int v12; // r9d
  __int64 v13; // r8
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v18; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v20[12]; // [rsp+68h] [rbp-98h] BYREF
  char *v21; // [rsp+78h] [rbp-88h] BYREF
  const char *v22; // [rsp+80h] [rbp-80h] BYREF
  const char *v23; // [rsp+88h] [rbp-78h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v24; // [rsp+90h] [rbp-70h] BYREF
  WCHAR *v25; // [rsp+98h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR sourceString[2088]; // [rsp+C0h] [rbp-40h] BYREF

  *a2 = 0;
  v24 = 0;
  memset_0(sourceString, 0, 0x1048u);
  StringRawBuffer = WindowsGetStringRawBuffer(a1[10], 0);
  v5 = WindowsGetStringRawBuffer(a1[11], 0);
  v6 = WindowsGetStringRawBuffer(a1[12], 0);
  RequestUri = StringCchPrintfW(
                 sourceString,
                 0x824u,
                 L"https://%s/api/v1/session/%s/autoheal/%s/package/download",
                 v6,
                 v5,
                 StringRawBuffer);
  v10 = (struct Windows::Foundation::IUriRuntimeClass *)(unsigned int)dword_180039000;
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180039000, v7, v9) )
  {
    v25 = sourceString;
    v21 = (char *)a1 + 108;
    v18 = 153;
    v22 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
    v23 = "DownloadManager::GetDownloadUriAsync";
    hstringHeader.Reserved.Reserved1 = "Create Get Sas uri Endpoint";
    v19 = RequestUri;
    *(_QWORD *)v20 = (char *)a1 + 237;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v10,
      (unsigned int)&dword_1800308B4,
      v9,
      v11,
      (__int64)v20,
      (__int64)&v19,
      (__int64)&hstringHeader,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v18,
      (__int64)&v21,
      (__int64)&v25);
  }
  if ( RequestUri >= 0 )
  {
    *(_QWORD *)v20 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                   &hstringHeader,
                                   sourceString)
                               + 24);
    RequestUri = Microsoft::WRL::Wrappers::HString::Set(a1 + 8, (HSTRING *)v20);
    if ( RequestUri >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v24);
      RequestUri = HelperClass::MakeRequestUri(sourceString, &v24);
      if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v10, v7, v9) )
      {
        *(_QWORD *)v20 = (char *)a1 + 108;
        v19 = 167;
        hstringHeader.Reserved.Reserved1 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
        v23 = "DownloadManager::GetDownloadUriAsync";
        v22 = "Create Get Sas uri Endpoint Url Object";
        v18 = RequestUri;
        v21 = (char *)a1 + 237;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)v10,
          (unsigned int)byte_180030841,
          v9,
          v12,
          (__int64)&v21,
          (__int64)&v18,
          (__int64)&v22,
          (__int64)&v23,
          (__int64)&hstringHeader,
          (__int64)&v19,
          (__int64)v20);
      }
      if ( RequestUri >= 0 )
      {
        v10 = v24;
        if ( v24 )
        {
          hstringHeader.Reserved.Reserved1 = a1;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v24;
          (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v24 + 8LL))(v24);
          *(_DWORD *)v20 = 0;
          *(_QWORD *)&v20[4] = 128;
          RequestUri = Windows::Internal::MakeAsyncOperation_Windows::Internal::CHSTRINGResult_HSTRING_____Windows::Internal::ComTaskPoolHandler__lambda_11c473bff872361231d7d8474c20662a___(
                         v20,
                         a2,
                         v13,
                         &hstringHeader);
          Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&hstringHeader.Reserved.Reserved2[8]);
        }
      }
    }
  }
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v10, v7, v9) )
  {
    *(_QWORD *)v20 = (char *)a1 + 108;
    v19 = 308;
    hstringHeader.Reserved.Reserved1 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
    v23 = "DownloadManager::GetDownloadUriAsync";
    v22 = "Get Sas Uri - async http get operation";
    v18 = RequestUri;
    v21 = (char *)a1 + 237;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v14,
      (unsigned int)&word_1800307CE,
      v15,
      v16,
      (__int64)&v21,
      (__int64)&v18,
      (__int64)&v22,
      (__int64)&v23,
      (__int64)&hstringHeader,
      (__int64)&v19,
      (__int64)v20);
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v24);
  return (unsigned int)RequestUri;
}

```

## disassembly

```asm
0x180017e20  mov     [rsp-8+arg_10], rbx
0x180017e25  push    rbp
0x180017e26  push    rsi
0x180017e27  push    rdi
0x180017e28  push    r12
0x180017e2a  push    r14
0x180017e2c  lea     rbp, [rsp-1020h]
0x180017e34  mov     eax, 1120h
0x180017e39  call    _alloca_probe
0x180017e3e  sub     rsp, rax
0x180017e41  mov     rax, cs:__security_cookie
0x180017e48  xor     rax, rsp
0x180017e4b  mov     [rbp+1040h+var_30], rax
0x180017e52  mov     r14, rdx
0x180017e55  mov     rsi, rcx
0x180017e58  mov     qword ptr [rdx], 0
0x180017e5f  mov     [rbp+1040h+var_10B0], 0
0x180017e67  xor     edx, edx; Val
0x180017e69  mov     r8d, 1048h; Size
0x180017e6f  lea     rcx, [rbp+1040h+sourceString]; void *
0x180017e73  call    memset_0
0x180017e78  xor     edx, edx; length
0x180017e7a  mov     rcx, [rsi+50h]; string
0x180017e7e  call    cs:__imp_WindowsGetStringRawBuffer
0x180017e84  mov     rdi, rax
0x180017e87  xor     edx, edx; length
0x180017e89  mov     rcx, [rsi+58h]; string
0x180017e8d  call    cs:__imp_WindowsGetStringRawBuffer
0x180017e93  mov     rbx, rax
0x180017e96  xor     edx, edx; length
0x180017e98  mov     rcx, [rsi+60h]; string
0x180017e9c  call    cs:__imp_WindowsGetStringRawBuffer
0x180017ea2  mov     [rsp+1140h+var_1118], rdi
0x180017ea7  mov     [rsp+1140h+var_1120], rbx
0x180017eac  mov     r9, rax
0x180017eaf  lea     r8, aHttpsSApiV1Ses; "https://%s/api/v1/session/%s/autoheal/%"...
0x180017eb6  mov     edx, 824h; unsigned __int64
0x180017ebb  lea     rcx, [rbp+1040h+sourceString]; unsigned __int16 *
0x180017ebf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017ec4  mov     ebx, eax
0x180017ec6  mov     ecx, cs:dword_180039000
0x180017ecc  lea     rdi, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180017ed3  lea     r12, aDownloadmanage_3; "DownloadManager::GetDownloadUriAsync"
0x180017eda  cmp     ecx, 5
0x180017edd  jbe     loc_180017F84
0x180017ee3  call    _tlgKeywordOn
0x180017ee8  test    al, al
0x180017eea  jz      loc_180017F84
0x180017ef0  lea     rax, [rbp+1040h+sourceString]
0x180017ef4  mov     [rbp+1040h+var_10A8], rax
0x180017ef8  lea     rax, [rsi+6Ch]
0x180017efc  mov     [rsp+1140h+var_10C8], rax
0x180017f01  mov     [rsp+1140h+var_10E0], 99h
0x180017f09  mov     [rbp+1040h+var_10C0], rdi
0x180017f0d  mov     [rbp+1040h+var_10B8], r12
0x180017f11  lea     rax, aCreateGetSasUr; "Create Get Sas uri Endpoint"
0x180017f18  mov     qword ptr [rbp+1040h+hstringHeader.Reserved], rax
0x180017f1c  mov     [rsp+1140h+var_10DC], ebx
0x180017f20  lea     rax, [rsi+0EDh]
0x180017f27  mov     [rsp+1140h+var_10D8], rax
0x180017f2c  lea     rax, [rbp+1040h+var_10A8]
0x180017f30  mov     [rsp+1140h+var_10E8], rax
0x180017f35  lea     rax, [rsp+1140h+var_10C8]
0x180017f3a  mov     [rsp+1140h+var_10F0], rax
0x180017f3f  lea     rax, [rsp+1140h+var_10E0]
0x180017f44  mov     [rsp+1140h+var_10F8], rax
0x180017f49  lea     rax, [rbp+1040h+var_10C0]
0x180017f4d  mov     [rsp+1140h+var_1100], rax
0x180017f52  lea     rax, [rbp+1040h+var_10B8]
0x180017f56  mov     [rsp+1140h+var_1108], rax
0x180017f5b  lea     rax, [rbp+1040h+hstringHeader]
0x180017f5f  mov     [rsp+1140h+var_1110], rax
0x180017f64  lea     rax, [rsp+1140h+var_10DC]
0x180017f69  mov     [rsp+1140h+var_1118], rax
0x180017f6e  lea     rax, [rsp+1140h+var_10D8]
0x180017f73  mov     [rsp+1140h+var_1120], rax
0x180017f78  lea     rdx, dword_1800308B4
0x180017f7f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180017f84  test    ebx, ebx
0x180017f86  js      loc_1800180C0
0x180017f8c  lea     rdx, [rbp+1040h+sourceString]; sourceString
0x180017f90  lea     rcx, [rbp+1040h+hstringHeader]; hstringHeader
0x180017f94  call    ??$?0$0ICE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0ICE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[2084])
0x180017f99  mov     rcx, [rax+18h]
0x180017f9d  mov     [rsp+1140h+var_10D8], rcx
0x180017fa2  lea     rcx, [rsi+40h]; newString
0x180017fa6  lea     rdx, [rsp+1140h+var_10D8]; HSTRING *
0x180017fab  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180017fb0  mov     ebx, eax
0x180017fb2  test    eax, eax
0x180017fb4  js      loc_1800180C0
0x180017fba  lea     rcx, [rbp+1040h+var_10B0]
0x180017fbe  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017fc3  lea     rdx, [rbp+1040h+var_10B0]; struct Windows::Foundation::IUriRuntimeClass **
0x180017fc7  lea     rcx, [rbp+1040h+sourceString]; unsigned __int16 *
0x180017fcb  call    ?MakeRequestUri@HelperClass@@SAJPEBGPEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; HelperClass::MakeRequestUri(ushort const *,Windows::Foundation::IUriRuntimeClass * *)
0x180017fd0  mov     ebx, eax
0x180017fd2  mov     eax, cs:dword_180039000
0x180017fd8  cmp     eax, 5
0x180017fdb  jbe     loc_180018071
0x180017fe1  call    _tlgKeywordOn
0x180017fe6  test    al, al
0x180017fe8  jz      loc_180018071
0x180017fee  lea     rax, [rsi+6Ch]
0x180017ff2  mov     [rsp+1140h+var_10D8], rax
0x180017ff7  mov     [rsp+1140h+var_10DC], 0A7h
0x180017fff  mov     qword ptr [rbp+1040h+hstringHeader.Reserved], rdi
0x180018003  mov     [rbp+1040h+var_10B8], r12
0x180018007  lea     rax, aCreateGetSasUr_1; "Create Get Sas uri Endpoint Url Object"
0x18001800e  mov     [rbp+1040h+var_10C0], rax
0x180018012  mov     [rsp+1140h+var_10E0], ebx
0x180018016  lea     rax, [rsi+0EDh]
0x18001801d  mov     [rsp+1140h+var_10C8], rax
0x180018022  lea     rax, [rsp+1140h+var_10D8]
0x180018027  mov     [rsp+1140h+var_10F0], rax
0x18001802c  lea     rax, [rsp+1140h+var_10DC]
0x180018031  mov     [rsp+1140h+var_10F8], rax
0x180018036  lea     rax, [rbp+1040h+hstringHeader]
0x18001803a  mov     [rsp+1140h+var_1100], rax
0x18001803f  lea     rax, [rbp+1040h+var_10B8]
0x180018043  mov     [rsp+1140h+var_1108], rax
0x180018048  lea     rax, [rbp+1040h+var_10C0]
0x18001804c  mov     [rsp+1140h+var_1110], rax
0x180018051  lea     rax, [rsp+1140h+var_10E0]
0x180018056  mov     [rsp+1140h+var_1118], rax
0x18001805b  lea     rax, [rsp+1140h+var_10C8]
0x180018060  mov     [rsp+1140h+var_1120], rax
0x180018065  lea     rdx, byte_180030841
0x18001806c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180018071  test    ebx, ebx
0x180018073  js      short loc_1800180C0
0x180018075  mov     rcx, [rbp+1040h+var_10B0]
0x180018079  test    rcx, rcx
0x18001807c  jz      short loc_1800180C0
0x18001807e  mov     qword ptr [rbp+1040h+hstringHeader.Reserved], rsi
0x180018082  mov     qword ptr [rbp+1040h+hstringHeader.Reserved+8], rcx
0x180018086  mov     rax, [rcx]
0x180018089  mov     rax, [rax+8]
0x18001808d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018092  nop
0x180018093  mov     dword ptr [rsp+1140h+var_10D8], 0
0x18001809b  mov     [rsp+1140h+var_10D8+4], 80h
0x1800180a4  lea     r9, [rbp+1040h+hstringHeader]
0x1800180a8  mov     rdx, r14
0x1800180ab  lea     rcx, [rsp+1140h+var_10D8]
0x1800180b0  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CHSTRINGResult_HSTRING_____Windows__Internal__ComTaskPoolHandler__lambda_11c473bff872361231d7d8474c20662a___
0x1800180b5  mov     ebx, eax
0x1800180b7  lea     rcx, [rbp+1040h+hstringHeader.Reserved+8]
0x1800180bb  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800180c0  mov     eax, cs:dword_180039000
0x1800180c6  cmp     eax, 5
0x1800180c9  jbe     loc_18001815F
0x1800180cf  call    _tlgKeywordOn
0x1800180d4  test    al, al
0x1800180d6  jz      loc_18001815F
0x1800180dc  lea     rax, [rsi+6Ch]
0x1800180e0  mov     [rsp+1140h+var_10D8], rax
0x1800180e5  mov     [rsp+1140h+var_10DC], 134h
0x1800180ed  mov     qword ptr [rbp+1040h+hstringHeader.Reserved], rdi
0x1800180f1  mov     [rbp+1040h+var_10B8], r12
0x1800180f5  lea     rax, aGetSasUriAsync; "Get Sas Uri - async http get operation"
0x1800180fc  mov     [rbp+1040h+var_10C0], rax
0x180018100  mov     [rsp+1140h+var_10E0], ebx
0x180018104  lea     rax, [rsi+0EDh]
0x18001810b  mov     [rsp+1140h+var_10C8], rax
0x180018110  lea     rax, [rsp+1140h+var_10D8]
0x180018115  mov     [rsp+1140h+var_10F0], rax
0x18001811a  lea     rax, [rsp+1140h+var_10DC]
0x18001811f  mov     [rsp+1140h+var_10F8], rax
0x180018124  lea     rax, [rbp+1040h+hstringHeader]
0x180018128  mov     [rsp+1140h+var_1100], rax
0x18001812d  lea     rax, [rbp+1040h+var_10B8]
0x180018131  mov     [rsp+1140h+var_1108], rax
0x180018136  lea     rax, [rbp+1040h+var_10C0]
0x18001813a  mov     [rsp+1140h+var_1110], rax
0x18001813f  lea     rax, [rsp+1140h+var_10E0]
0x180018144  mov     [rsp+1140h+var_1118], rax
0x180018149  lea     rax, [rsp+1140h+var_10C8]
0x18001814e  mov     [rsp+1140h+var_1120], rax
0x180018153  lea     rdx, word_1800307CE
0x18001815a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001815f  lea     rcx, [rbp+1040h+var_10B0]
0x180018163  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180018168  mov     eax, ebx
0x18001816a  mov     rcx, [rbp+1040h+var_30]
0x180018171  xor     rcx, rsp; StackCookie
0x180018174  call    __security_check_cookie
0x180018179  mov     rbx, [rsp+1140h+arg_10]
0x180018181  add     rsp, 1120h
0x180018188  pop     r14
0x18001818a  pop     r12
0x18001818c  pop     rdi
0x18001818d  pop     rsi
0x18001818e  pop     rbp
0x18001818f  retn
```
