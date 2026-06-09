# RunManager::UploadResults(DSKeyValuePair *,int)

- ea: `0x180011b80`
- end: `0x180012218`
- name: `?UploadResults@RunManager@@MEAAJPEAUDSKeyValuePair@@H@Z`
- size: `1688`
- prototype: `__int64 __fastcall(RunManager *__hidden this, struct DSKeyValuePair *, int)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001720`
- `0x180001e7c`
- `0x18000216c`
- `0x180002318`
- `0x180003fc0`
- `0x180004b78`
- `0x18000517c`
- `0x1800083ec`
- `0x18000847c`
- `0x18000851c`
- `0x18000ade0`
- `0x180011390`
- `0x180011b80`
- `0x18001b0dc`
- `0x18001b118`
- `0x18001b7e8`
- `0x18001bde0`
- `0x18001bed0`
- `0x18001c144`
- `0x1800260e0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011c61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011c70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011c7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011c61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011c70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011c7f`

## string_xrefs

- `0x180011bf2`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RunManager::UploadResults(RunManager *this, struct DSKeyValuePair *a2, int a3)
{
  unsigned __int64 v6; // r12
  __int64 v7; // rdx
  __int64 v8; // rcx
  signed int RequestUri; // ebx
  __int64 v10; // r8
  unsigned int i; // edi
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v13; // rbx
  PCWSTR v14; // rax
  int v15; // r9d
  __int64 v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // ecx
  const char *v26; // r8
  int v27; // r9d
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  struct Windows::Web::Http::IHttpClient *v34; // rdi
  __int64 (__fastcall *v35)(struct Windows::Web::Http::IHttpClient *, struct Windows::Foundation::IUriRuntimeClass *, struct Windows::Web::Http::IHttpContent *, char **); // rbx
  signed int v36; // eax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  const char *v40; // rax
  __int16 *v41; // rdx
  int v43; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+64h] [rbp-9Ch] BYREF
  const char *v45; // [rsp+68h] [rbp-98h] BYREF
  const char *v46; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v47; // [rsp+78h] [rbp-88h] BYREF
  const char *v48; // [rsp+80h] [rbp-80h] BYREF
  const char *v49; // [rsp+88h] [rbp-78h] BYREF
  char *v50; // [rsp+90h] [rbp-70h] BYREF
  int v51; // [rsp+98h] [rbp-68h] BYREF
  struct Windows::Web::Http::IHttpClient *v52; // [rsp+A0h] [rbp-60h] BYREF
  struct Windows::Web::Http::IHttpContent *v53; // [rsp+A8h] [rbp-58h] BYREF
  char *v54; // [rsp+B0h] [rbp-50h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v55; // [rsp+B8h] [rbp-48h] BYREF
  struct Windows::Data::Json::IJsonObject *v56; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v58; // [rsp+E0h] [rbp-20h]
  HSTRING_HEADER v59; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v60; // [rsp+100h] [rbp+0h]
  unsigned __int16 v61[2088]; // [rsp+110h] [rbp+10h] BYREF

  v51 = 0;
  v6 = 0;
  v56 = 0;
  v55 = 0;
  memset_0(v61, 0, 0x1048u);
  v58 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  RequestUri = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
                 v58,
                 &v56);
  for ( i = 0; (int)i < a3; ++i )
    HelperClass::SetNamedString(
      v56,
      (const unsigned __int16 *)a2 + 510 * i,
      (const unsigned __int16 *)a2 + 510 * i + 255);
  if ( RequestUri < 0 )
    goto LABEL_34;
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 13), 0);
  v13 = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0);
  v14 = WindowsGetStringRawBuffer(*((HSTRING *)this + 11), 0);
  RequestUri = StringCchPrintfW(
                 v61,
                 0x824u,
                 L"https://%s/api/v1/session/%s/autoheal/%s/results",
                 v14,
                 v13,
                 StringRawBuffer);
  if ( RequestUri < 0 )
    goto LABEL_34;
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v55);
  RequestUri = HelperClass::MakeRequestUri(v61, &v55);
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v8, v7, v10) )
  {
    v47 = v61;
    v54 = (char *)this + 112;
    v43 = 696;
    v53 = (struct Windows::Web::Http::IHttpContent *)"onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\runmanager\\lib\\runmanager.cpp";
    v52 = (struct Windows::Web::Http::IHttpClient *)"RunManager::UploadResults";
    v45 = "Creating the upload url";
    v44 = RequestUri;
    v46 = (char *)this + 241;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      v8,
      (unsigned int)word_18002FD12,
      v10,
      v15,
      (__int64)&v46,
      (__int64)&v44,
      (__int64)&v45,
      (__int64)&v52,
      (__int64)&v53,
      (__int64)&v43,
      (__int64)&v54,
      (__int64)&v47);
  }
  if ( !v55 )
  {
    RequestUri = -2147467259;
    goto LABEL_34;
  }
  if ( RequestUri < 0 )
    goto LABEL_34;
  v54 = 0;
  v47 = 0;
  v52 = 0;
  v53 = 0;
  v60 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v59, L"Windows.Web.Http.HttpClient", 0x1Cu, 0x1Bu);
  v16 = v60;
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v52);
  RequestUri = Windows::Foundation::ActivateInstance<Windows::Web::Http::IHttpClient>(v16, &v52);
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v18, v17, v19) )
  {
    v46 = (char *)this + 112;
    v44 = 717;
    v45 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\runmanager\\lib\\runmanager.cpp";
    v48 = "RunManager::UploadResults";
    v49 = "Activate Http client";
    v43 = RequestUri;
    v50 = (char *)this + 241;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v20,
      (unsigned int)&byte_18002FC9F,
      v21,
      v22,
      (__int64)&v50,
      (__int64)&v43,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v45,
      (__int64)&v44,
      (__int64)&v46);
  }
  if ( RequestUri >= 0 )
  {
    RequestUri = HelperClass::PrepareHttpRequestHeader(v52, (char *)this + 112);
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v24, v23, "Prepare Http request") )
    {
      v50 = (char *)this + 112;
      v44 = 728;
      v49 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\runmanager\\lib\\runmanager.cpp";
      v48 = "RunManager::UploadResults";
      v46 = v26;
      v43 = RequestUri;
      v45 = (char *)this + 241;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v25,
        (unsigned int)&byte_18002FF07,
        (_DWORD)v26,
        v27,
        (__int64)&v45,
        (__int64)&v43,
        (__int64)&v46,
        (__int64)&v48,
        (__int64)&v49,
        (__int64)&v44,
        (__int64)&v50);
    }
    if ( RequestUri >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v53);
      RequestUri = HelperClass::CreateResultHttpRequestContent(v56, &v53);
      if ( (unsigned int)dword_180039000 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(v29, v28, v30) )
        {
          v50 = (char *)this + 112;
          v44 = 741;
          v49 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\runmanager\\lib\\runmanager.cpp";
          v48 = "RunManager::UploadResults";
          v46 = "Prepare Http request";
          v43 = RequestUri;
          v45 = (char *)this + 241;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v31,
            (unsigned int)&word_18003017E,
            v32,
            v33,
            (__int64)&v45,
            (__int64)&v43,
            (__int64)&v46,
            (__int64)&v48,
            (__int64)&v49,
            (__int64)&v44,
            (__int64)&v50);
        }
      }
    }
  }
  TelemetryTimer::TelemetryTimer((TelemetryTimer *)&hstringHeader);
  if ( RequestUri >= 0 )
  {
    v34 = v52;
    v35 = *(__int64 (__fastcall **)(struct Windows::Web::Http::IHttpClient *, struct Windows::Foundation::IUriRuntimeClass *, struct Windows::Web::Http::IHttpContent *, char **))(*(_QWORD *)v52 + 104LL);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v54);
    RequestUri = v35(v34, v55, v53, &v54);
    if ( RequestUri >= 0 )
      RequestUri = BlockOnCompletionAndGetResults<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress,Windows::Web::Http::IHttpResponseMessage>(
                     v54,
                     &v47);
  }
  v6 = TelemetryTimer::ElapsedTimeMs((TelemetryTimer *)&hstringHeader);
  if ( RequestUri >= 0 )
  {
    v36 = (*(__int64 (__fastcall **)(unsigned __int16 *, int *))(*(_QWORD *)v47 + 128LL))(v47, &v51);
    if ( v51 == 200 )
      RequestUri = v36;
    else
      RequestUri = v51 | 0x80190000;
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v47);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v54);
  if ( RequestUri < 0 || v51 != 200 )
  {
LABEL_34:
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v8, v7, v10) )
    {
      v49 = (char *)this + 112;
      v44 = 788;
      v46 = "RunManager::UploadResults";
      v40 = "Failed to upload results";
      v41 = (__int16 *)byte_180030081;
      goto LABEL_37;
    }
    goto LABEL_38;
  }
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v8, v7, v10) )
  {
    v49 = (char *)this + 112;
    v44 = 779;
    v46 = "RunManager::UploadResults";
    v40 = "Upload Succeeded";
    v41 = word_18002FF7A;
LABEL_37:
    v45 = v40;
    v47 = (unsigned __int16 *)((char *)this + 241);
    v50 = (char *)v6;
    v48 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\runmanager\\lib\\runmanager.cpp";
    v43 = RequestUri;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      v37,
      (_DWORD)v41,
      v38,
      v39,
      (__int64)&v47,
      (__int64)&v43,
      (__int64)&v45,
      (__int64)&v46,
      (__int64)&v48,
      (__int64)&v44,
      (__int64)&v49,
      (__int64)&v50);
  }
LABEL_38:
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v56);
  return (unsigned int)RequestUri;
}

```

## disassembly

```asm
0x180011b80  mov     [rsp-8+arg_10], rbx
0x180011b85  mov     [rsp-8+arg_18], rsi
0x180011b8a  push    rbp
0x180011b8b  push    rdi
0x180011b8c  push    r12
0x180011b8e  push    r14
0x180011b90  push    r15
0x180011b92  lea     rbp, [rsp-1070h]
0x180011b9a  mov     eax, 1170h
0x180011b9f  call    _alloca_probe
0x180011ba4  sub     rsp, rax
0x180011ba7  mov     rax, cs:__security_cookie
0x180011bae  xor     rax, rsp
0x180011bb1  mov     [rbp+1090h+var_30], rax
0x180011bb8  mov     r15d, r8d
0x180011bbb  mov     r14, rdx
0x180011bbe  mov     rsi, rcx
0x180011bc1  mov     [rbp+1090h+var_10F8], 0
0x180011bc8  xor     r12d, r12d
0x180011bcb  mov     [rbp+1090h+var_10D0], r12
0x180011bcf  mov     [rbp+1090h+var_10D8], r12
0x180011bd3  xor     edx, edx; Val
0x180011bd5  mov     r8d, 1048h; Size
0x180011bdb  lea     rcx, [rbp+1090h+var_1080]; void *
0x180011bdf  call    memset_0
0x180011be4  mov     [rbp+1090h+var_10B0], r12
0x180011be8  lea     r9d, [r12+1Ch]; unsigned int
0x180011bed  lea     r8d, [r12+1Dh]; unsigned int
0x180011bf2  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180011bf9  lea     rcx, [rbp+1090h+hstringHeader]; hstringHeader
0x180011bfd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011c02  lea     rdx, [rbp+1090h+var_10D0]
0x180011c06  mov     rcx, [rbp+1090h+var_10B0]
0x180011c0a  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x180011c0f  mov     ebx, eax
0x180011c11  xor     edi, edi
0x180011c13  test    r15d, r15d
0x180011c16  jle     short loc_180011C3F
0x180011c18  mov     eax, edi
0x180011c1a  imul    rcx, rax, 3FCh
0x180011c21  lea     r8, [r14+1FEh]
0x180011c28  add     r8, rcx; unsigned __int16 *
0x180011c2b  lea     rdx, [rcx+r14]; unsigned __int16 *
0x180011c2f  mov     rcx, [rbp+1090h+var_10D0]; struct Windows::Data::Json::IJsonObject *
0x180011c33  call    ?SetNamedString@HelperClass@@SAJPEAUIJsonObject@Json@Data@Windows@@PEBG1@Z; HelperClass::SetNamedString(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x180011c38  inc     edi
0x180011c3a  cmp     edi, r15d
0x180011c3d  jl      short loc_180011C18
0x180011c3f  mov     r14d, 5
0x180011c45  lea     r15, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180011c4c  lea     rdi, aRunmanagerUplo; "RunManager::UploadResults"
0x180011c53  test    ebx, ebx
0x180011c55  js      loc_180012129
0x180011c5b  xor     edx, edx; length
0x180011c5d  mov     rcx, [rsi+68h]; string
0x180011c61  call    cs:__imp_WindowsGetStringRawBuffer
0x180011c67  mov     rdi, rax
0x180011c6a  xor     edx, edx; length
0x180011c6c  mov     rcx, [rsi+60h]; string
0x180011c70  call    cs:__imp_WindowsGetStringRawBuffer
0x180011c76  mov     rbx, rax
0x180011c79  xor     edx, edx; length
0x180011c7b  mov     rcx, [rsi+58h]; string
0x180011c7f  call    cs:__imp_WindowsGetStringRawBuffer
0x180011c85  mov     [rsp+1190h+var_1168], rdi
0x180011c8a  mov     [rsp+1190h+var_1170], rbx
0x180011c8f  mov     r9, rax
0x180011c92  lea     r8, aHttpsSApiV1Ses_0; "https://%s/api/v1/session/%s/autoheal/%"...
0x180011c99  mov     edx, 824h; unsigned __int64
0x180011c9e  lea     rcx, [rbp+1090h+var_1080]; unsigned __int16 *
0x180011ca2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011ca7  mov     ebx, eax
0x180011ca9  test    eax, eax
0x180011cab  js      loc_180012122
0x180011cb1  lea     rcx, [rbp+1090h+var_10D8]
0x180011cb5  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180011cba  lea     rdx, [rbp+1090h+var_10D8]; struct Windows::Foundation::IUriRuntimeClass **
0x180011cbe  lea     rcx, [rbp+1090h+var_1080]; unsigned __int16 *
0x180011cc2  call    ?MakeRequestUri@HelperClass@@SAJPEBGPEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; HelperClass::MakeRequestUri(ushort const *,Windows::Foundation::IUriRuntimeClass * *)
0x180011cc7  mov     ebx, eax
0x180011cc9  mov     eax, cs:dword_180039000
0x180011ccf  cmp     eax, r14d
0x180011cd2  jbe     loc_180011D84
0x180011cd8  call    _tlgKeywordOn
0x180011cdd  test    al, al
0x180011cdf  jz      loc_180011D84
0x180011ce5  lea     rax, [rbp+1090h+var_1080]
0x180011ce9  mov     [rsp+1190h+var_1118], rax
0x180011cee  lea     rax, [rsi+70h]
0x180011cf2  mov     [rbp+1090h+var_10E0], rax
0x180011cf6  mov     [rsp+1190h+var_1130], 2B8h
0x180011cfe  mov     [rbp+1090h+var_10E8], r15
0x180011d02  lea     rdi, aRunmanagerUplo; "RunManager::UploadResults"
0x180011d09  mov     [rbp+1090h+var_10F0], rdi
0x180011d0d  lea     rax, aCreatingTheUpl; "Creating the upload url"
0x180011d14  mov     [rsp+1190h+var_1128], rax
0x180011d19  mov     [rsp+1190h+var_112C], ebx
0x180011d1d  lea     rax, [rsi+0F1h]
0x180011d24  mov     [rsp+1190h+var_1120], rax
0x180011d29  lea     rax, [rsp+1190h+var_1118]
0x180011d2e  mov     [rsp+1190h+var_1138], rax
0x180011d33  lea     rax, [rbp+1090h+var_10E0]
0x180011d37  mov     [rsp+1190h+var_1140], rax
0x180011d3c  lea     rax, [rsp+1190h+var_1130]
0x180011d41  mov     [rsp+1190h+var_1148], rax
0x180011d46  lea     rax, [rbp+1090h+var_10E8]
0x180011d4a  mov     [rsp+1190h+var_1150], rax
0x180011d4f  lea     rax, [rbp+1090h+var_10F0]
0x180011d53  mov     [rsp+1190h+var_1158], rax
0x180011d58  lea     rax, [rsp+1190h+var_1128]
0x180011d5d  mov     [rsp+1190h+var_1160], rax
0x180011d62  lea     rax, [rsp+1190h+var_112C]
0x180011d67  mov     [rsp+1190h+var_1168], rax
0x180011d6c  lea     rax, [rsp+1190h+var_1120]
0x180011d71  mov     [rsp+1190h+var_1170], rax
0x180011d76  lea     rdx, word_18002FD12
0x180011d7d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180011d82  jmp     short loc_180011D8B
0x180011d84  lea     rdi, aRunmanagerUplo; "RunManager::UploadResults"
0x180011d8b  cmp     [rbp+1090h+var_10D8], 0
0x180011d90  jnz     short loc_180011D9C
0x180011d92  mov     ebx, 80004005h
0x180011d97  jmp     loc_180012129
0x180011d9c  test    ebx, ebx
0x180011d9e  js      loc_180012129
0x180011da4  mov     [rbp+1090h+var_10E0], 0
0x180011dac  mov     [rsp+1190h+var_1118], 0
0x180011db5  mov     [rbp+1090h+var_10F0], 0
0x180011dbd  mov     [rbp+1090h+var_10E8], 0
0x180011dc5  mov     [rbp+1090h+var_1090], 0
0x180011dcd  mov     r9d, 1Bh; unsigned int
0x180011dd3  lea     r8d, [r9+1]; unsigned int
0x180011dd7  lea     rdx, ?RuntimeClass_Windows_Web_Http_HttpClient@@3QBGB; "Windows.Web.Http.HttpClient"
0x180011dde  lea     rcx, [rbp+1090h+var_10A8]; hstringHeader
0x180011de2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011de7  mov     rbx, [rbp+1090h+var_1090]
0x180011deb  lea     rcx, [rbp+1090h+var_10F0]
0x180011def  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180011df4  lea     rdx, [rbp+1090h+var_10F0]
0x180011df8  mov     rcx, rbx
0x180011dfb  call    ??$ActivateInstance@UIHttpClient@Http@Web@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIHttpClient@Http@Web@1@@Z; Windows::Foundation::ActivateInstance<Windows::Web::Http::IHttpClient>(HSTRING__ *,Windows::Web::Http::IHttpClient * *)
0x180011e00  mov     ebx, eax
0x180011e02  mov     eax, cs:dword_180039000
0x180011e08  cmp     eax, r14d
0x180011e0b  jbe     loc_180011EA1
0x180011e11  call    _tlgKeywordOn
0x180011e16  test    al, al
0x180011e18  jz      loc_180011EA1
0x180011e1e  lea     rax, [rsi+70h]
0x180011e22  mov     [rsp+1190h+var_1120], rax
0x180011e27  mov     [rsp+1190h+var_112C], 2CDh
0x180011e2f  mov     [rsp+1190h+var_1128], r15
0x180011e34  mov     [rbp+1090h+var_1110], rdi
0x180011e38  lea     rax, aActivateHttpCl; "Activate Http client"
0x180011e3f  mov     [rbp+1090h+var_1108], rax
0x180011e43  mov     [rsp+1190h+var_1130], ebx
0x180011e47  lea     rax, [rsi+0F1h]
0x180011e4e  mov     [rbp+1090h+var_1100], rax
0x180011e52  lea     rax, [rsp+1190h+var_1120]
0x180011e57  mov     [rsp+1190h+var_1140], rax
0x180011e5c  lea     rax, [rsp+1190h+var_112C]
0x180011e61  mov     [rsp+1190h+var_1148], rax
0x180011e66  lea     rax, [rsp+1190h+var_1128]
0x180011e6b  mov     [rsp+1190h+var_1150], rax
0x180011e70  lea     rax, [rbp+1090h+var_1110]
0x180011e74  mov     [rsp+1190h+var_1158], rax
0x180011e79  lea     rax, [rbp+1090h+var_1108]
0x180011e7d  mov     [rsp+1190h+var_1160], rax
0x180011e82  lea     rax, [rsp+1190h+var_1130]
0x180011e87  mov     [rsp+1190h+var_1168], rax
0x180011e8c  lea     rax, [rbp+1090h+var_1100]
0x180011e90  mov     [rsp+1190h+var_1170], rax
0x180011e95  lea     rdx, byte_18002FC9F
0x180011e9c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180011ea1  test    ebx, ebx
0x180011ea3  js      loc_18001201D
0x180011ea9  lea     rdi, [rsi+70h]
0x180011ead  mov     rdx, rdi; char *
0x180011eb0  mov     rcx, [rbp+1090h+var_10F0]; struct Windows::Web::Http::IHttpClient *
0x180011eb4  call    ?PrepareHttpRequestHeader@HelperClass@@SAJPEAUIHttpClient@Http@Web@Windows@@PEAD@Z; HelperClass::PrepareHttpRequestHeader(Windows::Web::Http::IHttpClient *,char *)
0x180011eb9  mov     ebx, eax
0x180011ebb  mov     eax, cs:dword_180039000
0x180011ec1  lea     r8, aPrepareHttpReq; "Prepare Http request"
0x180011ec8  cmp     eax, r14d
0x180011ecb  jbe     loc_180011F5F
0x180011ed1  call    _tlgKeywordOn
0x180011ed6  test    al, al
0x180011ed8  jz      loc_180011F5F
0x180011ede  mov     [rbp+1090h+var_1100], rdi
0x180011ee2  mov     [rsp+1190h+var_112C], 2D8h
0x180011eea  mov     [rbp+1090h+var_1108], r15
0x180011eee  lea     r12, aRunmanagerUplo; "RunManager::UploadResults"
0x180011ef5  mov     [rbp+1090h+var_1110], r12
0x180011ef9  mov     [rsp+1190h+var_1120], r8
0x180011efe  mov     [rsp+1190h+var_1130], ebx
0x180011f02  lea     rax, [rsi+0F1h]
0x180011f09  mov     [rsp+1190h+var_1128], rax
0x180011f0e  lea     rax, [rbp+1090h+var_1100]
0x180011f12  mov     [rsp+1190h+var_1140], rax
0x180011f17  lea     rax, [rsp+1190h+var_112C]
0x180011f1c  mov     [rsp+1190h+var_1148], rax
0x180011f21  lea     rax, [rbp+1090h+var_1108]
0x180011f25  mov     [rsp+1190h+var_1150], rax
0x180011f2a  lea     rax, [rbp+1090h+var_1110]
0x180011f2e  mov     [rsp+1190h+var_1158], rax
0x180011f33  lea     rax, [rsp+1190h+var_1120]
0x180011f38  mov     [rsp+1190h+var_1160], rax
0x180011f3d  lea     rax, [rsp+1190h+var_1130]
0x180011f42  mov     [rsp+1190h+var_1168], rax
0x180011f47  lea     rax, [rsp+1190h+var_1128]
0x180011f4c  mov     [rsp+1190h+var_1170], rax
0x180011f51  lea     rdx, byte_18002FF07
0x180011f58  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180011f5d  jmp     short loc_180011F66
0x180011f5f  lea     r12, aRunmanagerUplo; "RunManager::UploadResults"
0x180011f66  test    ebx, ebx
0x180011f68  js      loc_18001201D
0x180011f6e  lea     rcx, [rbp+1090h+var_10E8]
0x180011f72  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180011f77  lea     rdx, [rbp+1090h+var_10E8]; struct Windows::Web::Http::IHttpContent **
0x180011f7b  mov     rcx, [rbp+1090h+var_10D0]; struct Windows::Data::Json::IJsonObject *
0x180011f7f  call    ?CreateResultHttpRequestContent@HelperClass@@SAJPEAUIJsonObject@Json@Data@Windows@@PEAPEAUIHttpContent@Http@Web@5@@Z; HelperClass::CreateResultHttpRequestContent(Windows::Data::Json::IJsonObject *,Windows::Web::Http::IHttpContent * *)
0x180011f84  mov     ebx, eax
0x180011f86  mov     eax, cs:dword_180039000
0x180011f8c  cmp     eax, r14d
0x180011f8f  jbe     loc_18001201D
0x180011f95  call    _tlgKeywordOn
0x180011f9a  test    al, al
0x180011f9c  jz      short loc_18001201D
0x180011f9e  mov     [rbp+1090h+var_1100], rdi
0x180011fa2  mov     [rsp+1190h+var_112C], 2E5h
0x180011faa  mov     [rbp+1090h+var_1108], r15
0x180011fae  mov     [rbp+1090h+var_1110], r12
0x180011fb2  lea     rax, aPrepareHttpReq; "Prepare Http request"
0x180011fb9  mov     [rsp+1190h+var_1120], rax
0x180011fbe  mov     [rsp+1190h+var_1130], ebx
0x180011fc2  lea     rax, [rsi+0F1h]
0x180011fc9  mov     [rsp+1190h+var_1128], rax
0x180011fce  lea     rax, [rbp+1090h+var_1100]
0x180011fd2  mov     [rsp+1190h+var_1140], rax
0x180011fd7  lea     rax, [rsp+1190h+var_112C]
0x180011fdc  mov     [rsp+1190h+var_1148], rax
0x180011fe1  lea     rax, [rbp+1090h+var_1108]
0x180011fe5  mov     [rsp+1190h+var_1150], rax
0x180011fea  lea     rax, [rbp+1090h+var_1110]
0x180011fee  mov     [rsp+1190h+var_1158], rax
0x180011ff3  lea     rax, [rsp+1190h+var_1120]
0x180011ff8  mov     [rsp+1190h+var_1160], rax
0x180011ffd  lea     rax, [rsp+1190h+var_1130]
0x180012002  mov     [rsp+1190h+var_1168], rax
0x180012007  lea     rax, [rsp+1190h+var_1128]
0x18001200c  mov     [rsp+1190h+var_1170], rax
0x180012011  lea     rdx, word_18003017E
0x180012018  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001201d  lea     rcx, [rbp+1090h+hstringHeader]; this
0x180012021  call    ??0TelemetryTimer@@QEAA@XZ; TelemetryTimer::TelemetryTimer(void)
0x180012026  test    ebx, ebx
0x180012028  js      short loc_18001206B
0x18001202a  mov     rdi, [rbp+1090h+var_10F0]
0x18001202e  mov     rax, [rdi]
0x180012031  mov     rbx, [rax+68h]
0x180012035  lea     rcx, [rbp+1090h+var_10E0]
0x180012039  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001203e  lea     r9, [rbp+1090h+var_10E0]
0x180012042  mov     r8, [rbp+1090h+var_10E8]
0x180012046  mov     rdx, [rbp+1090h+var_10D8]
0x18001204a  mov     rcx, rdi
0x18001204d  mov     rax, rbx
0x180012050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012055  mov     ebx, eax
0x180012057  test    eax, eax
0x180012059  js      short loc_18001206B
0x18001205b  lea     rdx, [rsp+1190h+var_1118]
0x180012060  mov     rcx, [rbp+1090h+var_10E0]
0x180012064  call    ??$BlockOnCompletionAndGetResults@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@UIHttpResponseMessage@234@@@YAJPEAU?$IAsyncOperationWithProgress@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIHttpResponseMessage@Http@Web@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress,Windows::Web::Http::IHttpResponseMessage>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Web::Http::IHttpResponseMessage>>,tagCOWAIT_FLAGS,void *)
0x180012069  mov     ebx, eax
0x18001206b  lea     rcx, [rbp+1090h+hstringHeader]; this
0x18001206f  call    ?ElapsedTimeMs@TelemetryTimer@@QEBA_KXZ; TelemetryTimer::ElapsedTimeMs(void)
0x180012074  mov     r12, rax
0x180012077  mov     edi, 0C8h
0x18001207c  test    ebx, ebx
0x18001207e  js      short loc_1800120A9
0x180012080  mov     rcx, [rsp+1190h+var_1118]
0x180012085  mov     rdx, [rcx]
0x180012088  mov     rax, [rdx+80h]
0x18001208f  lea     rdx, [rbp+1090h+var_10F8]
0x180012093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012098  mov     ebx, [rbp+1090h+var_10F8]
0x18001209b  cmp     ebx, edi
0x18001209d  jz      short loc_1800120A7
0x18001209f  or      ebx, 80190000h
0x1800120a5  jmp     short loc_1800120A9
0x1800120a7  mov     ebx, eax
0x1800120a9  lea     rcx, [rbp+1090h+var_10E8]
0x1800120ad  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800120b2  nop
0x1800120b3  lea     rcx, [rbp+1090h+var_10F0]
0x1800120b7  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800120bc  nop
0x1800120bd  lea     rcx, [rsp+1190h+var_1118]
  ... truncated ...
```
