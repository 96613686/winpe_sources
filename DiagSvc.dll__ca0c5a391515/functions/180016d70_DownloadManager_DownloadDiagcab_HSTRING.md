# DownloadManager::DownloadDiagcab(HSTRING__ * *)

- ea: `0x180016d70`
- end: `0x1800176af`
- name: `?DownloadDiagcab@DownloadManager@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `2367`
- prototype: `__int64 __fastcall(HSTRING *this, HSTRING *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001720`
- `0x180001e7c`
- `0x18000216c`
- `0x1800027ac`
- `0x180003fc0`
- `0x18000517c`
- `0x18000959c`
- `0x1800148ac`
- `0x180014d5c`
- `0x1800153b8`
- `0x180016d70`
- `0x180019e34`
- `0x18001a01c`
- `0x18001b0dc`
- `0x18001b118`
- `0x18001bc7c`
- `0x18001bde0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001738b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001738b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016de2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001766b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016de2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001766b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016ed4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016f0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001725e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017297`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017339`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800174da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016ed4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016f0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001725e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017297`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017339`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800174da`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017362`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017362`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180017382`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180017382`

## string_xrefs

- `0x180016e4f`: `Download Cab - Get Sas Uri`
- `0x180017011`: `Download Cab - Create Http Client`
- `0x1800172c2`: `Download Cab - Get Temporary file path`
- `0x1800173f0`: `Download Cab - Write Stream to File`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DownloadManager::DownloadDiagcab(HSTRING *this, HSTRING *a2)
{
  HSTRING v3; // rbx
  HSTRING v4; // rax
  __int64 (__fastcall *v6)(HSTRING *, struct Windows::Storage::Streams::IInputStream **); // rdi
  signed int RequestUri; // edi
  struct Windows::Storage::Streams::IInputStream *v8; // rsi
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  const unsigned __int16 *StringRawBuffer; // rax
  PCWSTR v16; // rax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // r15d
  HSTRING v21; // rax
  __int64 (__fastcall *v22)(HSTRING *, const char **); // rdi
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  const char *v26; // rsi
  __int64 (__fastcall *v27)(const char *, struct Windows::Foundation::IUriRuntimeClass *, const char **); // rdi
  __int64 v28; // rdx
  __int64 v29; // rcx
  int v30; // ecx
  const char *v31; // r8
  int v32; // r9d
  const char *v33; // rsi
  __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // r8d
  int v37; // r9d
  const unsigned __int16 *v38; // rax
  signed int TempFilePath; // eax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  PCWSTR v43; // rax
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  const WCHAR *v47; // rax
  HANDLE FileW; // rax
  DownloadManager *v49; // rcx
  void *v50; // rsi
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // r8
  signed int LastError; // eax
  int v55; // ecx
  int v56; // r8d
  int v57; // r9d
  PCWSTR v58; // rax
  __int64 v59; // rcx
  _QWORD *v60; // rax
  int v61; // ecx
  int v62; // r8d
  int v63; // r9d
  int v65; // [rsp+D0h] [rbp-80h] BYREF
  int v66; // [rsp+D4h] [rbp-7Ch] BYREF
  bool v67[8]; // [rsp+D8h] [rbp-78h] BYREF
  const char *v68; // [rsp+E0h] [rbp-70h] BYREF
  const char *v69; // [rsp+E8h] [rbp-68h] BYREF
  const char *v70; // [rsp+F0h] [rbp-60h] BYREF
  struct Windows::Storage::Streams::IInputStream *v71; // [rsp+F8h] [rbp-58h] BYREF
  const char *v72; // [rsp+100h] [rbp-50h] BYREF
  char *v73; // [rsp+108h] [rbp-48h] BYREF
  const char *v74; // [rsp+110h] [rbp-40h] BYREF
  const char *v75; // [rsp+118h] [rbp-38h] BYREF
  HSTRING string; // [rsp+120h] [rbp-30h] BYREF
  HSTRING v77; // [rsp+128h] [rbp-28h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v78; // [rsp+130h] [rbp-20h] BYREF
  __int64 v79; // [rsp+138h] [rbp-18h] BYREF
  __int64 v80; // [rsp+140h] [rbp-10h] BYREF
  __int64 v81; // [rsp+148h] [rbp-8h] BYREF
  _QWORD *v82; // [rsp+150h] [rbp+0h] BYREF
  const char *v83; // [rsp+158h] [rbp+8h] BYREF
  const char *v84; // [rsp+160h] [rbp+10h] BYREF
  const char *v85; // [rsp+168h] [rbp+18h] BYREF
  const char *v86; // [rsp+170h] [rbp+20h] BYREF
  _QWORD v87[2]; // [rsp+178h] [rbp+28h] BYREF
  __int64 v88; // [rsp+188h] [rbp+38h] BYREF
  __m128i si128; // [rsp+198h] [rbp+48h]
  _QWORD v90[3]; // [rsp+1A8h] [rbp+58h] BYREF
  unsigned __int64 v91; // [rsp+1C0h] [rbp+70h]

  *a2 = 0;
  v3 = 0;
  v4 = *this;
  v78 = 0;
  v77 = 0;
  string = 0;
  v6 = (__int64 (__fastcall *)(HSTRING *, struct Windows::Storage::Streams::IInputStream **))*((_QWORD *)v4 + 6);
  v71 = 0;
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v71);
  RequestUri = v6(this, &v71);
  if ( RequestUri >= 0 )
  {
    WindowsDeleteString(string);
    v8 = v71;
    string = 0;
    RequestUri = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(v71);
    if ( RequestUri >= 0 )
      RequestUri = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IInputStream *, HSTRING *))(*(_QWORD *)v8 + 64LL))(
                     v8,
                     &string);
  }
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)((__int64 (*)(void))tlgKeywordOn)() )
  {
    v65 = 343;
    v75 = (char *)this + 108;
    v74 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
    v69 = "Download Cab - Get Sas Uri";
    v70 = (char *)this + 237;
    v68 = "DownloadManager::DownloadDiagcab";
    v66 = RequestUri;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v9,
      (unsigned int)byte_18003075B,
      v10,
      v11,
      (__int64)&v70,
      (__int64)&v66,
      (__int64)&v69,
      (__int64)&v68,
      (__int64)&v74,
      (__int64)&v65,
      (__int64)&v75);
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v71);
  if ( RequestUri >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v78);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    RequestUri = HelperClass::MakeRequestUri(StringRawBuffer, &v78);
    if ( (unsigned int)dword_180039000 > 5 )
    {
      if ( (unsigned __int8)((__int64 (*)(void))tlgKeywordOn)() )
      {
        v16 = WindowsGetStringRawBuffer(string, 0);
        v66 = 354;
        v70 = (const char *)v16;
        v69 = (char *)this + 108;
        v75 = "Download Cab - Make Request Url";
        v74 = (char *)this + 237;
        v68 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
        v71 = (struct Windows::Storage::Streams::IInputStream *)"DownloadManager::DownloadDiagcab";
        v65 = RequestUri;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v17,
          (unsigned int)&unk_1800306E0,
          v18,
          v19,
          (__int64)&v74,
          (__int64)&v65,
          (__int64)&v75,
          (__int64)&v71,
          (__int64)&v68,
          (__int64)&v66,
          (__int64)&v69,
          (__int64)&v70);
      }
    }
  }
  v20 = 0;
  if ( RequestUri >= 0 )
  {
    v21 = *this;
    v74 = 0;
    v75 = 0;
    v71 = 0;
    v22 = (__int64 (__fastcall *)(HSTRING *, const char **))*((_QWORD *)v21 + 8);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v74);
    RequestUri = v22(this, &v74);
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)((__int64 (*)(void))tlgKeywordOn)() )
    {
      v66 = 370;
      v70 = (char *)this + 108;
      v69 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
      v68 = "DownloadManager::DownloadDiagcab";
      v72 = "Download Cab - Create Http Client";
      v73 = (char *)this + 237;
      v65 = RequestUri;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v23,
        (unsigned int)byte_18003066D,
        v24,
        v25,
        (__int64)&v73,
        (__int64)&v65,
        (__int64)&v72,
        (__int64)&v68,
        (__int64)&v69,
        (__int64)&v66,
        (__int64)&v70);
    }
    TelemetryTimer::TelemetryTimer((TelemetryTimer *)v87);
    if ( RequestUri >= 0 )
    {
      v26 = v74;
      v27 = *(__int64 (__fastcall **)(const char *, struct Windows::Foundation::IUriRuntimeClass *, const char **))(*(_QWORD *)v74 + 80LL);
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v75);
      RequestUri = v27(v26, v78, &v75);
      if ( (unsigned int)dword_180039000 > 5
        && (unsigned __int8)tlgKeywordOn(v29, v28, "Download Cab - Get Input Stream Async") )
      {
        v66 = 381;
        v73 = (char *)this + 108;
        v72 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
        v70 = "DownloadManager::DownloadDiagcab";
        v69 = v31;
        v68 = (char *)this + 237;
        v65 = RequestUri;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v30,
          (unsigned int)word_1800305FA,
          (_DWORD)v31,
          v32,
          (__int64)&v68,
          (__int64)&v65,
          (__int64)&v69,
          (__int64)&v70,
          (__int64)&v72,
          (__int64)&v66,
          (__int64)&v73);
      }
      if ( RequestUri >= 0 )
      {
        v33 = v75;
        Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v71);
        RequestUri = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>(v33);
        if ( RequestUri >= 0 )
          RequestUri = (*(__int64 (__fastcall **)(const char *, struct Windows::Storage::Streams::IInputStream **))(*(_QWORD *)v33 + 80LL))(
                         v33,
                         &v71);
        v20 = TelemetryTimer::ElapsedTimeMs((TelemetryTimer *)v87);
        if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180039000, v34, v35) )
        {
          v66 = 392;
          v70 = "DownloadManager::DownloadDiagcab";
          v73 = (char *)this + 108;
          v69 = "Download Cab - Get Input Stream Async";
          v72 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
          v68 = (char *)this + 237;
          v65 = RequestUri;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)this + 108,
            (unsigned int)&byte_180030587,
            v36,
            v37,
            (__int64)&v68,
            (__int64)&v65,
            (__int64)&v69,
            (__int64)&v70,
            (__int64)&v72,
            (__int64)&v66,
            (__int64)&v73);
        }
        if ( RequestUri >= 0 )
        {
          WindowsDeleteString(0);
          v38 = WindowsGetStringRawBuffer(this[9], 0);
          TempFilePath = HelperClass::GetTempFilePath(v38, &v77);
          v3 = v77;
          RequestUri = TempFilePath;
          if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v41, v40, v42) )
          {
            v43 = WindowsGetStringRawBuffer(v3, 0);
            v66 = 403;
            v73 = (char *)v43;
            v72 = (char *)this + 108;
            v69 = "DownloadManager::DownloadDiagcab";
            v68 = "Download Cab - Get Temporary file path";
            v77 = (HSTRING)((char *)this + 237);
            v70 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
            v65 = RequestUri;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              v44,
              (unsigned int)&byte_180030507,
              v45,
              v46,
              (__int64)&v77,
              (__int64)&v65,
              (__int64)&v68,
              (__int64)&v69,
              (__int64)&v70,
              (__int64)&v66,
              (__int64)&v72,
              (__int64)&v73);
          }
          if ( RequestUri >= 0 )
          {
            v47 = WindowsGetStringRawBuffer(v3, 0);
            FileW = CreateFileW(v47, 0x40000000u, 0, 0, 2u, 0x100u, 0);
            v50 = FileW;
            if ( FileW == (HANDLE)-1LL )
            {
              LastError = GetLastError();
              RequestUri = LastError;
              if ( LastError > 0 )
                RequestUri = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              RequestUri = DownloadManager::WriteStreamToFile(v49, v71, FileW);
              SetEndOfFile(v50);
              CloseHandle(v50);
            }
            if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v52, v51, v53) )
            {
              v66 = 424;
              v73 = (char *)this + 108;
              v72 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
              v70 = "DownloadManager::DownloadDiagcab";
              v65 = RequestUri;
              v69 = "Download Cab - Write Stream to File";
              v68 = (char *)this + 237;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v55,
                (unsigned int)&dword_180030494,
                v56,
                v57,
                (__int64)&v68,
                (__int64)&v65,
                (__int64)&v69,
                (__int64)&v70,
                (__int64)&v72,
                (__int64)&v66,
                (__int64)&v73);
            }
          }
        }
      }
    }
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v71);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v74);
    if ( v3 )
      *a2 = v3;
  }
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v13, v12, v14) )
  {
    v73 = (char *)this + 108;
    v66 = 0;
    v72 = 0;
    v67[0] = RequestUri >= 0;
    v70 = 0;
    v69 = 0;
    v68 = 0;
    v77 = 0;
    v79 = 0;
    v80 = 0;
    v81 = 0;
    v65 = 0;
    LODWORD(v74) = v20;
    v58 = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(v90, v58);
    v60 = (_QWORD *)DownloadManager::WideStrToCStr(v59, &v88, v90);
    if ( v60[3] > 0xFu )
      v60 = (_QWORD *)*v60;
    v82 = v60;
    LODWORD(v75) = 441;
    v83 = "DownloadDiagCab";
    v85 = "DownloadManager::DownloadDiagcab";
    v86 = "Download Cab";
    v87[0] = (char *)this + 237;
    v84 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\downloadmanager\\lib\\downloadmanager.cpp";
    LODWORD(v71) = RequestUri;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v61,
      (unsigned int)&word_18003030E,
      v62,
      v63,
      (__int64)v87,
      (__int64)&v71,
      (__int64)&v86,
      (__int64)&v85,
      (__int64)&v84,
      (__int64)&v75,
      (__int64)&v83,
      (__int64)&v82,
      (__int64)&v74,
      (__int64)&v65,
      (__int64)v67,
      (__int64)&v81,
      (__int64)&v80,
      (__int64)&v79,
      (__int64)&v77,
      (__int64)&v68,
      (__int64)&v69,
      (__int64)&v70,
      (__int64)&v72,
      (__int64)&v66,
      (__int64)&v73);
    if ( si128.m128i_i64[1] > 0xFuLL )
      std::_Deallocate<16>(v88, si128.m128i_i64[1] + 1);
    LOBYTE(v88) = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    if ( v91 > 7 )
      std::_Deallocate<16>(v90[0], 2 * v91 + 2);
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(0);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v78);
  return (unsigned int)RequestUri;
}

```

## disassembly

```asm
0x180016d70  mov     [rsp-8+arg_10], rbx
0x180016d75  push    rbp
0x180016d76  push    rsi
0x180016d77  push    rdi
0x180016d78  push    r12
0x180016d7a  push    r13
0x180016d7c  push    r14
0x180016d7e  push    r15
0x180016d80  lea     rbp, [rsp-80h]
0x180016d85  sub     rsp, 1D0h
0x180016d8c  mov     rax, cs:__security_cookie
0x180016d93  xor     rax, rsp
0x180016d96  mov     [rbp+0B0h+var_38], rax
0x180016d9a  xor     r13d, r13d
0x180016d9d  mov     r14, rcx
0x180016da0  mov     [rdx], r13
0x180016da3  mov     ebx, r13d
0x180016da6  mov     rax, [rcx]
0x180016da9  mov     r12, rdx
0x180016dac  lea     rcx, [rbp+0B0h+var_108]
0x180016db0  mov     [rbp+0B0h+var_D0], r13
0x180016db4  mov     [rbp+0B0h+var_D8], rbx
0x180016db8  mov     [rbp+0B0h+string], r13
0x180016dbc  mov     rdi, [rax+30h]
0x180016dc0  mov     [rbp+0B0h+var_108], r13
0x180016dc4  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180016dc9  lea     rdx, [rbp+0B0h+var_108]
0x180016dcd  mov     rcx, r14
0x180016dd0  mov     rax, rdi
0x180016dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016dd8  mov     edi, eax
0x180016dda  test    eax, eax
0x180016ddc  js      short loc_180016E13
0x180016dde  mov     rcx, [rbp+0B0h+string]; string
0x180016de2  call    cs:__imp_WindowsDeleteString
0x180016de8  mov     rsi, [rbp+0B0h+var_108]
0x180016dec  mov     rcx, rsi
0x180016def  mov     [rbp+0B0h+string], r13
0x180016df3  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)
0x180016df8  mov     edi, eax
0x180016dfa  test    eax, eax
0x180016dfc  js      short loc_180016E13
0x180016dfe  mov     rax, [rsi]
0x180016e01  lea     rdx, [rbp+0B0h+string]
0x180016e05  mov     rcx, rsi
0x180016e08  mov     rax, [rax+40h]
0x180016e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e11  mov     edi, eax
0x180016e13  mov     eax, cs:dword_180039000
0x180016e19  lea     rsi, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180016e20  lea     r15, aDownloadmanage; "DownloadManager::DownloadDiagcab"
0x180016e27  cmp     eax, 5
0x180016e2a  jbe     loc_180016EB4
0x180016e30  call    _tlgKeywordOn
0x180016e35  test    al, al
0x180016e37  jz      short loc_180016EB4
0x180016e39  lea     rax, [r14+6Ch]
0x180016e3d  mov     [rbp+0B0h+var_130], 157h
0x180016e44  mov     [rbp+0B0h+var_E8], rax
0x180016e48  lea     rdx, byte_18003075B
0x180016e4f  lea     rax, aDownloadCabGet_0; "Download Cab - Get Sas Uri"
0x180016e56  mov     [rbp+0B0h+var_F0], rsi
0x180016e5a  mov     [rbp+0B0h+var_118], rax
0x180016e5e  lea     rax, [r14+0EDh]
0x180016e65  mov     [rbp+0B0h+var_110], rax
0x180016e69  lea     rax, [rbp+0B0h+var_E8]
0x180016e6d  mov     [rsp+200h+var_1B0], rax
0x180016e72  lea     rax, [rbp+0B0h+var_130]
0x180016e76  mov     [rsp+200h+var_1B8], rax
0x180016e7b  lea     rax, [rbp+0B0h+var_F0]
0x180016e7f  mov     [rsp+200h+var_1C0], rax
0x180016e84  lea     rax, [rbp+0B0h+var_120]
0x180016e88  mov     [rsp+200h+var_1C8], rax
0x180016e8d  lea     rax, [rbp+0B0h+var_118]
0x180016e91  mov     [rsp+200h+hTemplateFile], rax
0x180016e96  lea     rax, [rbp+0B0h+var_12C]
0x180016e9a  mov     qword ptr [rsp+200h+dwFlagsAndAttributes], rax
0x180016e9f  lea     rax, [rbp+0B0h+var_110]
0x180016ea3  mov     qword ptr [rsp+200h+dwCreationDisposition], rax
0x180016ea8  mov     [rbp+0B0h+var_120], r15
0x180016eac  mov     [rbp+0B0h+var_12C], edi
0x180016eaf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180016eb4  lea     rcx, [rbp+0B0h+var_108]
0x180016eb8  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180016ebd  test    edi, edi
0x180016ebf  js      loc_180016F98
0x180016ec5  lea     rcx, [rbp+0B0h+var_D0]
0x180016ec9  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180016ece  mov     rcx, [rbp+0B0h+string]; string
0x180016ed2  xor     edx, edx; length
0x180016ed4  call    cs:__imp_WindowsGetStringRawBuffer
0x180016eda  mov     rcx, rax; unsigned __int16 *
0x180016edd  lea     rdx, [rbp+0B0h+var_D0]; struct Windows::Foundation::IUriRuntimeClass **
0x180016ee1  call    ?MakeRequestUri@HelperClass@@SAJPEBGPEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; HelperClass::MakeRequestUri(ushort const *,Windows::Foundation::IUriRuntimeClass * *)
0x180016ee6  mov     edi, eax
0x180016ee8  mov     eax, cs:dword_180039000
0x180016eee  cmp     eax, 5
0x180016ef1  jbe     loc_180016F98
0x180016ef7  call    _tlgKeywordOn
0x180016efc  test    al, al
0x180016efe  jz      loc_180016F98
0x180016f04  mov     rcx, [rbp+0B0h+string]; string
0x180016f08  xor     edx, edx; length
0x180016f0a  call    cs:__imp_WindowsGetStringRawBuffer
0x180016f10  lea     rdx, unk_1800306E0
0x180016f17  mov     [rbp+0B0h+var_12C], 162h
0x180016f1e  mov     [rbp+0B0h+var_110], rax
0x180016f22  lea     rax, [r14+6Ch]
0x180016f26  mov     [rbp+0B0h+var_118], rax
0x180016f2a  lea     rax, aDownloadCabMak; "Download Cab - Make Request Url"
0x180016f31  mov     [rbp+0B0h+var_E8], rax
0x180016f35  lea     rax, [r14+0EDh]
0x180016f3c  mov     [rbp+0B0h+var_F0], rax
0x180016f40  lea     rax, [rbp+0B0h+var_110]
0x180016f44  mov     [rsp+200h+var_1A8], rax
0x180016f49  lea     rax, [rbp+0B0h+var_118]
0x180016f4d  mov     [rsp+200h+var_1B0], rax
0x180016f52  lea     rax, [rbp+0B0h+var_12C]
0x180016f56  mov     [rsp+200h+var_1B8], rax
0x180016f5b  lea     rax, [rbp+0B0h+var_120]
0x180016f5f  mov     [rsp+200h+var_1C0], rax
0x180016f64  lea     rax, [rbp+0B0h+var_108]
0x180016f68  mov     [rsp+200h+var_1C8], rax
0x180016f6d  lea     rax, [rbp+0B0h+var_E8]
0x180016f71  mov     [rsp+200h+hTemplateFile], rax
0x180016f76  lea     rax, [rbp+0B0h+var_130]
0x180016f7a  mov     qword ptr [rsp+200h+dwFlagsAndAttributes], rax
0x180016f7f  lea     rax, [rbp+0B0h+var_F0]
0x180016f83  mov     qword ptr [rsp+200h+dwCreationDisposition], rax
0x180016f88  mov     [rbp+0B0h+var_120], rsi
0x180016f8c  mov     [rbp+0B0h+var_108], r15
0x180016f90  mov     [rbp+0B0h+var_130], edi
0x180016f93  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180016f98  mov     r15, r13
0x180016f9b  test    edi, edi
0x180016f9d  js      loc_18001747A
0x180016fa3  mov     rax, [r14]
0x180016fa6  lea     rcx, [rbp+0B0h+var_F0]
0x180016faa  mov     [rbp+0B0h+var_F0], r13
0x180016fae  mov     [rbp+0B0h+var_E8], r13
0x180016fb2  mov     [rbp+0B0h+var_108], r13
0x180016fb6  mov     rdi, [rax+40h]
0x180016fba  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180016fbf  lea     rdx, [rbp+0B0h+var_F0]
0x180016fc3  mov     rcx, r14
0x180016fc6  mov     rax, rdi
0x180016fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fce  mov     edi, eax
0x180016fd0  mov     eax, cs:dword_180039000
0x180016fd6  cmp     eax, 5
0x180016fd9  jbe     loc_18001706E
0x180016fdf  call    _tlgKeywordOn
0x180016fe4  test    al, al
0x180016fe6  jz      loc_18001706E
0x180016fec  lea     rax, [r14+6Ch]
0x180016ff0  mov     [rbp+0B0h+var_12C], 172h
0x180016ff7  mov     [rbp+0B0h+var_110], rax
0x180016ffb  lea     rdx, byte_18003066D
0x180017002  lea     rax, aDownloadmanage; "DownloadManager::DownloadDiagcab"
0x180017009  mov     [rbp+0B0h+var_118], rsi
0x18001700d  mov     [rbp+0B0h+var_120], rax
0x180017011  lea     rax, aDownloadCabCre; "Download Cab - Create Http Client"
0x180017018  mov     [rbp+0B0h+var_100], rax
0x18001701c  lea     rax, [r14+0EDh]
0x180017023  mov     [rbp+0B0h+var_F8], rax
0x180017027  lea     rax, [rbp+0B0h+var_110]
0x18001702b  mov     [rsp+200h+var_1B0], rax
0x180017030  lea     rax, [rbp+0B0h+var_12C]
0x180017034  mov     [rsp+200h+var_1B8], rax
0x180017039  lea     rax, [rbp+0B0h+var_118]
0x18001703d  mov     [rsp+200h+var_1C0], rax
0x180017042  lea     rax, [rbp+0B0h+var_120]
0x180017046  mov     [rsp+200h+var_1C8], rax
0x18001704b  lea     rax, [rbp+0B0h+var_100]
0x18001704f  mov     [rsp+200h+hTemplateFile], rax
0x180017054  lea     rax, [rbp+0B0h+var_130]
0x180017058  mov     qword ptr [rsp+200h+dwFlagsAndAttributes], rax
0x18001705d  lea     rax, [rbp+0B0h+var_F8]
0x180017061  mov     qword ptr [rsp+200h+dwCreationDisposition], rax
0x180017066  mov     [rbp+0B0h+var_130], edi
0x180017069  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001706e  lea     rcx, [rbp+0B0h+var_88]; this
0x180017072  call    ??0TelemetryTimer@@QEAA@XZ; TelemetryTimer::TelemetryTimer(void)
0x180017077  test    edi, edi
0x180017079  js      loc_180017456
0x18001707f  mov     rsi, [rbp+0B0h+var_F0]
0x180017083  lea     rcx, [rbp+0B0h+var_E8]
0x180017087  mov     rax, [rsi]
0x18001708a  mov     rdi, [rax+50h]
0x18001708e  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017093  mov     rdx, [rbp+0B0h+var_D0]
0x180017097  lea     r8, [rbp+0B0h+var_E8]
0x18001709b  mov     rcx, rsi
0x18001709e  mov     rax, rdi
0x1800170a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170a6  mov     edi, eax
0x1800170a8  lea     r8, aDownloadCabGet_1; "Download Cab - Get Input Stream Async"
0x1800170af  mov     eax, cs:dword_180039000
0x1800170b5  cmp     eax, 5
0x1800170b8  jbe     loc_18001714F
0x1800170be  call    _tlgKeywordOn
0x1800170c3  test    al, al
0x1800170c5  jz      loc_18001714F
0x1800170cb  lea     rax, [r14+6Ch]
0x1800170cf  mov     [rbp+0B0h+var_12C], 17Dh
0x1800170d6  mov     [rbp+0B0h+var_F8], rax
0x1800170da  lea     rsi, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x1800170e1  lea     rax, aDownloadmanage; "DownloadManager::DownloadDiagcab"
0x1800170e8  mov     [rbp+0B0h+var_100], rsi
0x1800170ec  mov     [rbp+0B0h+var_110], rax
0x1800170f0  lea     rdx, word_1800305FA
0x1800170f7  lea     rax, [r14+0EDh]
0x1800170fe  mov     [rbp+0B0h+var_118], r8
0x180017102  mov     [rbp+0B0h+var_120], rax
0x180017106  lea     rax, [rbp+0B0h+var_F8]
0x18001710a  mov     [rsp+200h+var_1B0], rax
0x18001710f  lea     rax, [rbp+0B0h+var_12C]
0x180017113  mov     [rsp+200h+var_1B8], rax
0x180017118  lea     rax, [rbp+0B0h+var_100]
0x18001711c  mov     [rsp+200h+var_1C0], rax
0x180017121  lea     rax, [rbp+0B0h+var_110]
0x180017125  mov     [rsp+200h+var_1C8], rax
0x18001712a  lea     rax, [rbp+0B0h+var_118]
0x18001712e  mov     [rsp+200h+hTemplateFile], rax
0x180017133  lea     rax, [rbp+0B0h+var_130]
0x180017137  mov     qword ptr [rsp+200h+dwFlagsAndAttributes], rax
0x18001713c  lea     rax, [rbp+0B0h+var_120]
0x180017140  mov     qword ptr [rsp+200h+dwCreationDisposition], rax
0x180017145  mov     [rbp+0B0h+var_130], edi
0x180017148  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001714d  jmp     short loc_180017156
0x18001714f  lea     rsi, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180017156  test    edi, edi
0x180017158  js      loc_180017456
0x18001715e  mov     rsi, [rbp+0B0h+var_E8]
0x180017162  lea     rcx, [rbp+0B0h+var_108]
0x180017166  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001716b  mov     rcx, rsi
0x18001716e  call    ??$WaitForCompletion@U?$IAsyncOperationWithProgressCompletedHandler@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@U?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@23@@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIInputStream@Streams@Storage@Windows@@UHttpProgress@Http@Web@4@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>,Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress>>(Windows::Foundation::IAsyncOperationWithProgress<Windows::Storage::Streams::IInputStream *,Windows::Web::Http::HttpProgress> *,tagCOWAIT_FLAGS,void *)
0x180017173  mov     edi, eax
0x180017175  test    eax, eax
0x180017177  js      short loc_18001718E
0x180017179  mov     rax, [rsi]
0x18001717c  lea     rdx, [rbp+0B0h+var_108]
0x180017180  mov     rcx, rsi
0x180017183  mov     rax, [rax+50h]
0x180017187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001718c  mov     edi, eax
0x18001718e  lea     rcx, [rbp+0B0h+var_88]; this
0x180017192  call    ?ElapsedTimeMs@TelemetryTimer@@QEBA_KXZ; TelemetryTimer::ElapsedTimeMs(void)
0x180017197  mov     ecx, cs:dword_180039000
0x18001719d  mov     r15, rax
0x1800171a0  cmp     ecx, 5
0x1800171a3  jbe     loc_180017241
0x1800171a9  call    _tlgKeywordOn
0x1800171ae  test    al, al
0x1800171b0  jz      loc_180017241
0x1800171b6  lea     rax, aDownloadmanage; "DownloadManager::DownloadDiagcab"
0x1800171bd  mov     [rbp+0B0h+var_12C], 188h
0x1800171c4  mov     [rbp+0B0h+var_110], rax
0x1800171c8  lea     rcx, [r14+6Ch]
0x1800171cc  lea     rax, aDownloadCabGet_1; "Download Cab - Get Input Stream Async"
0x1800171d3  mov     [rbp+0B0h+var_F8], rcx
0x1800171d7  mov     [rbp+0B0h+var_118], rax
0x1800171db  lea     rsi, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x1800171e2  lea     rax, [r14+0EDh]
0x1800171e9  mov     [rbp+0B0h+var_100], rsi
0x1800171ed  mov     [rbp+0B0h+var_120], rax
0x1800171f1  lea     rdx, byte_180030587
0x1800171f8  lea     rax, [rbp+0B0h+var_F8]
0x1800171fc  mov     [rbp+0B0h+var_130], edi
0x1800171ff  mov     [rsp+200h+var_1B0], rax
0x180017204  lea     rax, [rbp+0B0h+var_12C]
0x180017208  mov     [rsp+200h+var_1B8], rax
0x18001720d  lea     rax, [rbp+0B0h+var_100]
0x180017211  mov     [rsp+200h+var_1C0], rax
0x180017216  lea     rax, [rbp+0B0h+var_110]
0x18001721a  mov     [rsp+200h+var_1C8], rax
0x18001721f  lea     rax, [rbp+0B0h+var_118]
0x180017223  mov     [rsp+200h+hTemplateFile], rax
0x180017228  lea     rax, [rbp+0B0h+var_130]
0x18001722c  mov     qword ptr [rsp+200h+dwFlagsAndAttributes], rax
0x180017231  lea     rax, [rbp+0B0h+var_120]
0x180017235  mov     qword ptr [rsp+200h+dwCreationDisposition], rax
0x18001723a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001723f  jmp     short loc_180017248
0x180017241  lea     rsi, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180017248  test    edi, edi
0x18001724a  js      loc_180017456
0x180017250  xor     ecx, ecx; string
0x180017252  call    cs:__imp_WindowsDeleteString
0x180017258  mov     rcx, [r14+48h]; string
0x18001725c  xor     edx, edx; length
0x18001725e  call    cs:__imp_WindowsGetStringRawBuffer
0x180017264  mov     rcx, rax; unsigned __int16 *
0x180017267  lea     rdx, [rbp+0B0h+var_D8]; HSTRING *
0x18001726b  call    ?GetTempFilePath@HelperClass@@SAJPEBGPEAPEAUHSTRING__@@@Z; HelperClass::GetTempFilePath(ushort const *,HSTRING__ * *)
0x180017270  mov     rbx, [rbp+0B0h+var_D8]
0x180017274  mov     edi, eax
0x180017276  mov     eax, cs:dword_180039000
  ... truncated ...
```
