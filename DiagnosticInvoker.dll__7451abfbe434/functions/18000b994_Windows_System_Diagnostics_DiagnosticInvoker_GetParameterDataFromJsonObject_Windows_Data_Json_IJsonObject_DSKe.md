# Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject(Windows::Data::Json::IJsonObject *,DSKeyValuePair * *,int *)

- ea: `0x18000b994`
- end: `0x18000c1dc`
- name: `?GetParameterDataFromJsonObject@DiagnosticInvoker@Diagnostics@System@Windows@@AEAAJPEAUIJsonObject@Json@Data@4@PEAPEAUDSKeyValuePair@@PEAH@Z`
- size: `2120`
- prototype: `__int64 __fastcall(Windows::System::Diagnostics::DiagnosticInvoker *__hidden this, struct Windows::Data::Json::IJsonObject *, struct DSKeyValuePair **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000881c`

## callees

- `0x18000108c`
- `0x180001270`
- `0x1800013c4`
- `0x180001e20`
- `0x18000b994`
- `0x18000d4f0`
- `0x180011010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000bac0`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000bc71`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000bac0`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000bc71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b9ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bb96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bd72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000be55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b9ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bb96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000bd72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000be55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bd48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000be2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c144`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c152`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c15e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c16c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bd48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000be2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c144`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c152`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c15e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c16c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bf18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c010`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bf18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c010`

## string_xrefs

- `0x18000ba3c`: `DiagnosticInvoker::GetParameterDataFromJsonObject`
- `0x18000ba30`: `Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject`
- `0x18000baf4`: `Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject`
- `0x18000bc02`: `Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject`
- `0x18000bcda`: `Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject`
- `0x18000bdc1`: `Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject`
- `0x18000bea4`: `Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject`
- `0x18000bf9c`: `Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject`
- `0x18000c0ba`: `Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject`
- `0x18000bad4`: `Property 'parameters' doesn't exist in Json`
- `0x18000bbe2`: `Get parameter count from Json`

## pseudocode

```c
__int64 __fastcall Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject(
        Windows::System::Diagnostics::DiagnosticInvoker *this,
        struct Windows::Data::Json::IJsonObject *a2,
        struct DSKeyValuePair **a3,
        int *a4)
{
  int v8; // r12d
  __int64 v10; // rbx
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  signed int v14; // eax
  int v15; // r9d
  signed int v16; // ebx
  const char *v17; // rsi
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rcx
  __int64 v22; // rbx
  HRESULT v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // r13d
  int v30; // r14d
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  const char *v34; // rdi
  double v35; // rbx
  __int64 v36; // rsi
  HRESULT v37; // eax
  int v38; // edx
  unsigned int v39; // r8d
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  double v43; // rbx
  __int64 v44; // rsi
  HRESULT v45; // eax
  int v46; // edx
  unsigned int v47; // r8d
  int v48; // ecx
  int v49; // r8d
  int v50; // r9d
  const char *v51; // rsi
  __int64 v52; // rbx
  PCWSTR StringRawBuffer; // rax
  int v54; // r9d
  __int64 v55; // rdi
  WCHAR *v56; // rdx
  WCHAR v57; // cx
  WCHAR *v58; // rcx
  __int64 v59; // rbx
  PCWSTR v60; // rax
  __int64 v61; // r8
  const char *v62; // rdi
  char *v63; // r9
  WCHAR v64; // cx
  char *v65; // rcx
  double v66; // rcx
  __int64 v67; // rcx
  int v68; // [rsp+60h] [rbp-69h] BYREF
  const char *v69; // [rsp+68h] [rbp-61h] BYREF
  HSTRING v70; // [rsp+70h] [rbp-59h] BYREF
  HSTRING v71; // [rsp+78h] [rbp-51h] BYREF
  double v72; // [rsp+80h] [rbp-49h] BYREF
  const char *v73; // [rsp+88h] [rbp-41h] BYREF
  const char *v74; // [rsp+90h] [rbp-39h] BYREF
  const char *v75; // [rsp+98h] [rbp-31h] BYREF
  const char *v76; // [rsp+A0h] [rbp-29h] BYREF
  const char *v77; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v78; // [rsp+B0h] [rbp-19h] BYREF
  const char *v79; // [rsp+B8h] [rbp-11h] BYREF
  int *v80; // [rsp+C0h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-1h] BYREF
  HSTRING string; // [rsp+E0h] [rbp+17h] BYREF

  v80 = a4;
  v8 = 0;
  if ( !a2 )
    return 2147942487LL;
  v78 = 0;
  v10 = *(_QWORD *)a2;
  string = 0;
  v11 = WindowsCreateStringReference(L"parameters", 0xAu, &hstringHeader, &string);
  if ( v11 < 0 )
    goto LABEL_61;
  v14 = (*(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, __int64 *))(v10 + 72))(
          a2,
          string,
          &v78);
  v16 = v14;
  if ( (unsigned int)dword_18001D000 <= 5 )
  {
    v17 = (char *)this + 72;
  }
  else
  {
    v77 = "DiagnosticInvoker::GetParameterDataFromJsonObject";
    LODWORD(v70) = v14;
    v68 = 232;
    v72 = COERCE_DOUBLE("onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp");
    v71 = (HSTRING)"Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject";
    v17 = (char *)this + 72;
    v69 = (char *)this + 72;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_18001D000,
      (unsigned int)word_180018D02,
      (unsigned int)"Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject",
      v15,
      (__int64)&v69,
      (__int64)&v71,
      (__int64)&v72,
      (__int64)&v68,
      (__int64)&v70,
      (__int64)&v77);
  }
  if ( v16 == -2089484279 )
  {
    *a4 = 0;
    *a3 = (struct DSKeyValuePair *)calloc(0, 0x3FCu);
    if ( (unsigned int)dword_18001D000 > 5 )
    {
      v77 = "Property 'parameters' doesn't exist in Json";
      v68 = -2089484279;
      LODWORD(v70) = 240;
      v72 = COERCE_DOUBLE("onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp");
      v71 = (HSTRING)"Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject";
      v69 = v17;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v18,
        (unsigned int)&dword_180018C9C,
        v19,
        v20,
        (__int64)&v69,
        (__int64)&v71,
        (__int64)&v72,
        (__int64)&v70,
        (__int64)&v68,
        (__int64)&v77);
    }
    v21 = v78;
    if ( v78 )
    {
      v78 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    return 0;
  }
  else
  {
    if ( v16 >= 0 )
    {
      v72 = 0.0;
      v22 = *(_QWORD *)a2;
      string = 0;
      v23 = WindowsCreateStringReference(L"parameterCount", 0xEu, &hstringHeader, &string);
      if ( v23 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
        JUMPOUT(0x18000C1DBLL);
      }
      v16 = (*(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, double *))(v22 + 88))(
              a2,
              string,
              &v72);
      v8 = 256;
      if ( (int)v72 < 256 )
        v8 = (int)v72;
      if ( (unsigned int)dword_18001D000 > 5 )
      {
        v68 = *a4;
        v77 = "Get parameter count from Json";
        LODWORD(v70) = v16;
        LODWORD(v69) = 248;
        v71 = (HSTRING)"onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
        v73 = "Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject";
        v74 = v17;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v26,
          (unsigned int)byte_180018C25,
          v27,
          v28,
          (__int64)&v74,
          (__int64)&v73,
          (__int64)&v71,
          (__int64)&v69,
          (__int64)&v70,
          (__int64)&v77,
          (__int64)&v68);
      }
    }
    v29 = 0;
    if ( v16 >= 0 )
    {
      v77 = (const char *)calloc(v8, 0x3FCu);
      *a3 = (struct DSKeyValuePair *)v77;
      v71 = 0;
      v70 = 0;
      v30 = 0;
      while ( v30 < v8 )
      {
        v72 = 0.0;
        v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)v78 + 48LL))(
                v78,
                (unsigned int)v30,
                &v72);
        if ( (unsigned int)dword_18001D000 <= 5 )
        {
          v34 = (char *)this + 72;
        }
        else
        {
          v74 = "Get each parameter object";
          LODWORD(v69) = v16;
          v68 = 263;
          v73 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
          v75 = "Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject";
          v34 = (char *)this + 72;
          v76 = (char *)this + 72;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v31,
            (unsigned int)&byte_180018BBF,
            v32,
            v33,
            (__int64)&v76,
            (__int64)&v75,
            (__int64)&v73,
            (__int64)&v68,
            (__int64)&v69,
            (__int64)&v74);
        }
        if ( v16 >= 0 )
        {
          v35 = v72;
          v36 = **(_QWORD **)&v72;
          WindowsDeleteString(v71);
          v71 = 0;
          string = 0;
          v37 = WindowsCreateStringReference(L"parameterName", 0xDu, &hstringHeader, &string);
          if ( v37 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v37, v38, v39);
LABEL_61:
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
            __debugbreak();
          }
          v16 = (*(__int64 (__fastcall **)(double, HSTRING, HSTRING *))(v36 + 80))(
                  COERCE_DOUBLE(*(_QWORD *)&v35),
                  string,
                  &v71);
          if ( (unsigned int)dword_18001D000 > 5 )
          {
            v76 = "Get parameter name";
            LODWORD(v69) = v16;
            v68 = 270;
            v75 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
            v74 = "Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject";
            v73 = v34;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v40,
              (unsigned int)byte_180018B59,
              v41,
              v42,
              (__int64)&v73,
              (__int64)&v74,
              (__int64)&v75,
              (__int64)&v68,
              (__int64)&v69,
              (__int64)&v76);
            v34 = (char *)this + 72;
          }
          if ( v16 >= 0 )
          {
            v43 = v72;
            v44 = **(_QWORD **)&v72;
            WindowsDeleteString(v70);
            v70 = 0;
            string = 0;
            v45 = WindowsCreateStringReference(L"parameterValue", 0xEu, &hstringHeader, &string);
            if ( v45 < 0 )
            {
              Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v45, v46, v47);
              __debugbreak();
            }
            v16 = (*(__int64 (__fastcall **)(double, HSTRING, HSTRING *))(v44 + 80))(
                    COERCE_DOUBLE(*(_QWORD *)&v43),
                    string,
                    &v70);
            if ( (unsigned int)dword_18001D000 > 5 )
            {
              v76 = "Get parameter value";
              LODWORD(v69) = v16;
              v68 = 278;
              v75 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
              v74 = "Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject";
              v73 = v34;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v48,
                (unsigned int)byte_180018AF3,
                v49,
                v50,
                (__int64)&v73,
                (__int64)&v74,
                (__int64)&v75,
                (__int64)&v68,
                (__int64)&v69,
                (__int64)&v76);
            }
            if ( v16 >= 0 )
            {
              v51 = &v77[1020 * v30];
              v52 = 2147483646;
              StringRawBuffer = WindowsGetStringRawBuffer(v71, 0);
              v55 = 255;
              v56 = (WCHAR *)v51;
              do
              {
                if ( !v52 )
                  break;
                v57 = *StringRawBuffer;
                if ( !*StringRawBuffer )
                  break;
                ++StringRawBuffer;
                *v56++ = v57;
                --v52;
                --v55;
              }
              while ( v55 );
              v16 = v55 == 0 ? 0x8007007A : 0;
              v58 = v56 - 1;
              if ( v55 )
                v58 = v56;
              *v58 = 0;
              if ( (unsigned int)dword_18001D000 > 5 )
              {
                v76 = v51;
                v75 = "Save parameter name";
                LODWORD(v69) = v55 == 0 ? 0x8007007A : 0;
                v68 = 287;
                v74 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
                v73 = "Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject";
                v79 = (char *)this + 72;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                  (_DWORD)v58,
                  (unsigned int)byte_180018A79,
                  0,
                  v54,
                  (__int64)&v79,
                  (__int64)&v73,
                  (__int64)&v74,
                  (__int64)&v68,
                  (__int64)&v69,
                  (__int64)&v75,
                  (__int64)&v76);
              }
              if ( v55 )
              {
                v59 = 2147483646;
                v60 = WindowsGetStringRawBuffer(v70, 0);
                v61 = 255;
                v62 = v77;
                v63 = (char *)&v77[1020 * v30 + 510];
                do
                {
                  if ( !v59 )
                    break;
                  v64 = *v60;
                  if ( !*v60 )
                    break;
                  ++v60;
                  *(_WORD *)v63 = v64;
                  v63 += 2;
                  --v59;
                  --v61;
                }
                while ( v61 );
                v16 = v61 == 0 ? 0x8007007A : 0;
                v65 = v63 - 2;
                if ( v61 )
                  v65 = v63;
                *(_WORD *)v65 = 0;
                if ( (unsigned int)dword_18001D000 > 5 )
                {
                  v79 = &v62[1020 * v30 + 510];
                  v76 = "Save parameter value";
                  LODWORD(v69) = v61 == 0 ? 0x8007007A : 0;
                  v68 = 296;
                  v75 = "onecoreuap\\base\\diagnosis\\winrt\\diaginvoker\\lib\\diagnosticinvoker.cpp";
                  v74 = "Windows::System::Diagnostics::DiagnosticInvoker::GetParameterDataFromJsonObject";
                  v73 = (char *)this + 72;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
                    (_DWORD)v65,
                    (unsigned int)byte_1800189FD,
                    v61,
                    (_DWORD)v63,
                    (__int64)&v73,
                    (__int64)&v74,
                    (__int64)&v75,
                    (__int64)&v68,
                    (__int64)&v69,
                    (__int64)&v76,
                    (__int64)&v79);
                }
                ++v29;
              }
            }
          }
        }
        v66 = v72;
        if ( v72 != 0.0 )
        {
          v72 = 0.0;
          (*(void (__fastcall **)(double))(**(_QWORD **)&v66 + 16LL))(COERCE_DOUBLE(*(_QWORD *)&v66));
        }
        ++v30;
        if ( v16 < 0 )
          break;
      }
      WindowsDeleteString(v71);
      v71 = 0;
      WindowsDeleteString(v70);
      v70 = 0;
      WindowsDeleteString(0);
      v70 = 0;
      WindowsDeleteString(v71);
    }
    *v80 = v29;
    v67 = v78;
    if ( v78 )
    {
      v78 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    }
    return (unsigned int)v16;
  }
}

```

## disassembly

```asm
0x18000b994  mov     [rsp-8+arg_0], rbx
0x18000b999  push    rbp
0x18000b99a  push    rsi
0x18000b99b  push    rdi
0x18000b99c  push    r12
0x18000b99e  push    r13
0x18000b9a0  push    r14
0x18000b9a2  push    r15
0x18000b9a4  lea     rbp, [rsp-27h]
0x18000b9a9  sub     rsp, 0F0h
0x18000b9b0  mov     rax, cs:__security_cookie
0x18000b9b7  xor     rax, rsp
0x18000b9ba  mov     [rbp+57h+var_38], rax
0x18000b9be  mov     r13, r9
0x18000b9c1  mov     [rbp+57h+var_60], r9
0x18000b9c5  mov     r14, r8
0x18000b9c8  mov     rdi, rdx
0x18000b9cb  mov     r15, rcx
0x18000b9ce  xor     r12d, r12d
0x18000b9d1  test    rdx, rdx
0x18000b9d4  jnz     short loc_18000B9E0
0x18000b9d6  mov     eax, 80070057h
0x18000b9db  jmp     loc_18000C195
0x18000b9e0  mov     [rbp+57h+var_70], r12
0x18000b9e4  mov     rbx, [rdx]
0x18000b9e7  mov     [rbp+57h+string], r12
0x18000b9eb  lea     r9, [rbp+57h+string]; string
0x18000b9ef  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000b9f3  mov     edx, 0Ah; length
0x18000b9f8  lea     rcx, aParameters; "parameters"
0x18000b9ff  call    cs:__imp_WindowsCreateStringReference
0x18000ba05  test    eax, eax
0x18000ba07  js      loc_18000C1CC
0x18000ba0d  lea     r8, [rbp+57h+var_70]
0x18000ba11  mov     rdx, [rbp+57h+string]
0x18000ba15  mov     rcx, rdi
0x18000ba18  mov     rax, [rbx+48h]
0x18000ba1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba21  mov     ebx, eax
0x18000ba23  mov     ecx, cs:dword_18001D000
0x18000ba29  lea     rdx, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\winrt\\dia"...
0x18000ba30  lea     r8, aWindowsSystemD_0; "Windows::System::Diagnostics::Diagnosti"...
0x18000ba37  cmp     ecx, 5
0x18000ba3a  jbe     short loc_18000BAA5
0x18000ba3c  lea     rax, aDiagnosticinvo_14; "DiagnosticInvoker::GetParameterDataFrom"...
0x18000ba43  mov     [rbp+57h+var_78], rax
0x18000ba47  mov     dword ptr [rbp+57h+var_B0], ebx
0x18000ba4a  mov     [rbp+57h+var_C0], 0E8h
0x18000ba51  mov     [rbp+57h+var_A0], rdx
0x18000ba55  mov     [rbp+57h+var_A8], r8
0x18000ba59  lea     rsi, [r15+48h]
0x18000ba5d  mov     [rbp+57h+var_B8], rsi
0x18000ba61  lea     rax, [rbp+57h+var_78]
0x18000ba65  mov     [rsp+120h+var_D8], rax
0x18000ba6a  lea     rax, [rbp+57h+var_B0]
0x18000ba6e  mov     [rsp+120h+var_E0], rax
0x18000ba73  lea     rax, [rbp+57h+var_C0]
0x18000ba77  mov     [rsp+120h+var_E8], rax
0x18000ba7c  lea     rax, [rbp+57h+var_A0]
0x18000ba80  mov     [rsp+120h+var_F0], rax
0x18000ba85  lea     rax, [rbp+57h+var_A8]
0x18000ba89  mov     [rsp+120h+var_F8], rax
0x18000ba8e  lea     rax, [rbp+57h+var_B8]
0x18000ba92  mov     [rsp+120h+var_100], rax
0x18000ba97  lea     rdx, word_180018D02
0x18000ba9e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000baa3  jmp     short loc_18000BAA9
0x18000baa5  lea     rsi, [r15+48h]
0x18000baa9  cmp     ebx, 83750009h
0x18000baaf  jnz     loc_18000BB67
0x18000bab5  mov     [r13+0], r12d
0x18000bab9  mov     edx, 3FCh; Size
0x18000babe  xor     ecx, ecx; Count
0x18000bac0  call    cs:__imp_calloc
0x18000bac6  mov     [r14], rax
0x18000bac9  mov     eax, cs:dword_18001D000
0x18000bacf  cmp     eax, 5
0x18000bad2  jbe     short loc_18000BB46
0x18000bad4  lea     rax, aPropertyParame; "Property 'parameters' doesn't exist in "...
0x18000badb  mov     [rbp+57h+var_78], rax
0x18000badf  mov     [rbp+57h+var_C0], ebx
0x18000bae2  mov     dword ptr [rbp+57h+var_B0], 0F0h
0x18000bae9  lea     rax, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\winrt\\dia"...
0x18000baf0  mov     [rbp+57h+var_A0], rax
0x18000baf4  lea     rax, aWindowsSystemD_0; "Windows::System::Diagnostics::Diagnosti"...
0x18000bafb  mov     [rbp+57h+var_A8], rax
0x18000baff  mov     [rbp+57h+var_B8], rsi
0x18000bb03  lea     rax, [rbp+57h+var_78]
0x18000bb07  mov     [rsp+120h+var_D8], rax
0x18000bb0c  lea     rax, [rbp+57h+var_C0]
0x18000bb10  mov     [rsp+120h+var_E0], rax
0x18000bb15  lea     rax, [rbp+57h+var_B0]
0x18000bb19  mov     [rsp+120h+var_E8], rax
0x18000bb1e  lea     rax, [rbp+57h+var_A0]
0x18000bb22  mov     [rsp+120h+var_F0], rax
0x18000bb27  lea     rax, [rbp+57h+var_A8]
0x18000bb2b  mov     [rsp+120h+var_F8], rax
0x18000bb30  lea     rax, [rbp+57h+var_B8]
0x18000bb34  mov     [rsp+120h+var_100], rax
0x18000bb39  lea     rdx, dword_180018C9C
0x18000bb40  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000bb45  nop
0x18000bb46  mov     rcx, [rbp+57h+var_70]
0x18000bb4a  test    rcx, rcx
0x18000bb4d  jz      short loc_18000BB60
0x18000bb4f  mov     [rbp+57h+var_70], r12
0x18000bb53  mov     rax, [rcx]
0x18000bb56  mov     rax, [rax+10h]
0x18000bb5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb5f  nop
0x18000bb60  xor     eax, eax
0x18000bb62  jmp     loc_18000C195
0x18000bb67  test    ebx, ebx
0x18000bb69  js      loc_18000BC5C
0x18000bb6f  xorps   xmm0, xmm0
0x18000bb72  movsd   [rbp+57h+var_A0], xmm0
0x18000bb77  mov     rbx, [rdi]
0x18000bb7a  mov     [rbp+57h+string], 0
0x18000bb82  lea     r9, [rbp+57h+string]; string
0x18000bb86  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000bb8a  mov     edx, 0Eh; length
0x18000bb8f  lea     rcx, aParametercount; "parameterCount"
0x18000bb96  call    cs:__imp_WindowsCreateStringReference
0x18000bb9c  test    eax, eax
0x18000bb9e  js      loc_18000C1D4
0x18000bba4  lea     r8, [rbp+57h+var_A0]
0x18000bba8  mov     rdx, [rbp+57h+string]
0x18000bbac  mov     rcx, rdi
0x18000bbaf  mov     rax, [rbx+58h]
0x18000bbb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbb8  mov     ebx, eax
0x18000bbba  cvttsd2si eax, [rbp+57h+var_A0]
0x18000bbbf  mov     r12d, 100h
0x18000bbc5  cmp     eax, r12d
0x18000bbc8  cmovl   r12d, eax
0x18000bbcc  mov     eax, cs:dword_18001D000
0x18000bbd2  cmp     eax, 5
0x18000bbd5  jbe     loc_18000BC5C
0x18000bbdb  mov     eax, [r13+0]
0x18000bbdf  mov     [rbp+57h+var_C0], eax
0x18000bbe2  lea     rax, aGetParameterCo; "Get parameter count from Json"
0x18000bbe9  mov     [rbp+57h+var_78], rax
0x18000bbed  mov     dword ptr [rbp+57h+var_B0], ebx
0x18000bbf0  mov     dword ptr [rbp+57h+var_B8], 0F8h
0x18000bbf7  lea     rax, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\winrt\\dia"...
0x18000bbfe  mov     [rbp+57h+var_A8], rax
0x18000bc02  lea     rax, aWindowsSystemD_0; "Windows::System::Diagnostics::Diagnosti"...
0x18000bc09  mov     [rbp+57h+var_98], rax
0x18000bc0d  mov     [rbp+57h+var_90], rsi
0x18000bc11  lea     rax, [rbp+57h+var_C0]
0x18000bc15  mov     [rsp+120h+var_D0], rax
0x18000bc1a  lea     rax, [rbp+57h+var_78]
0x18000bc1e  mov     [rsp+120h+var_D8], rax
0x18000bc23  lea     rax, [rbp+57h+var_B0]
0x18000bc27  mov     [rsp+120h+var_E0], rax
0x18000bc2c  lea     rax, [rbp+57h+var_B8]
0x18000bc30  mov     [rsp+120h+var_E8], rax
0x18000bc35  lea     rax, [rbp+57h+var_A8]
0x18000bc39  mov     [rsp+120h+var_F0], rax
0x18000bc3e  lea     rax, [rbp+57h+var_98]
0x18000bc42  mov     [rsp+120h+var_F8], rax
0x18000bc47  lea     rax, [rbp+57h+var_90]
0x18000bc4b  mov     [rsp+120h+var_100], rax
0x18000bc50  lea     rdx, byte_180018C25
0x18000bc57  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000bc5c  xor     esi, esi
0x18000bc5e  mov     r13d, esi
0x18000bc61  test    ebx, ebx
0x18000bc63  js      loc_18000C172
0x18000bc69  movsxd  rcx, r12d; Count
0x18000bc6c  mov     edx, 3FCh; Size
0x18000bc71  call    cs:__imp_calloc
0x18000bc77  mov     [rbp+57h+var_78], rax
0x18000bc7b  mov     [r14], rax
0x18000bc7e  mov     [rbp+57h+var_A8], rsi
0x18000bc82  mov     [rbp+57h+var_B0], rsi
0x18000bc86  mov     r14d, esi
0x18000bc89  cmp     r14d, r12d
0x18000bc8c  jge     loc_18000C140
0x18000bc92  mov     [rbp+57h+var_A0], rsi
0x18000bc96  mov     rcx, [rbp+57h+var_70]
0x18000bc9a  mov     rax, [rcx]
0x18000bc9d  lea     r8, [rbp+57h+var_A0]
0x18000bca1  mov     edx, r14d
0x18000bca4  mov     rax, [rax+30h]
0x18000bca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcad  mov     ebx, eax
0x18000bcaf  mov     eax, cs:dword_18001D000
0x18000bcb5  cmp     eax, 5
0x18000bcb8  jbe     short loc_18000BD31
0x18000bcba  lea     rax, aGetEachParamet; "Get each parameter object"
0x18000bcc1  mov     [rbp+57h+var_90], rax
0x18000bcc5  mov     dword ptr [rbp+57h+var_B8], ebx
0x18000bcc8  mov     [rbp+57h+var_C0], 107h
0x18000bccf  lea     rax, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\winrt\\dia"...
0x18000bcd6  mov     [rbp+57h+var_98], rax
0x18000bcda  lea     rax, aWindowsSystemD_0; "Windows::System::Diagnostics::Diagnosti"...
0x18000bce1  mov     [rbp+57h+var_88], rax
0x18000bce5  lea     rdi, [r15+48h]
0x18000bce9  mov     [rbp+57h+var_80], rdi
0x18000bced  lea     rax, [rbp+57h+var_90]
0x18000bcf1  mov     [rsp+120h+var_D8], rax
0x18000bcf6  lea     rax, [rbp+57h+var_B8]
0x18000bcfa  mov     [rsp+120h+var_E0], rax
0x18000bcff  lea     rax, [rbp+57h+var_C0]
0x18000bd03  mov     [rsp+120h+var_E8], rax
0x18000bd08  lea     rax, [rbp+57h+var_98]
0x18000bd0c  mov     [rsp+120h+var_F0], rax
0x18000bd11  lea     rax, [rbp+57h+var_88]
0x18000bd15  mov     [rsp+120h+var_F8], rax
0x18000bd1a  lea     rax, [rbp+57h+var_80]
0x18000bd1e  mov     [rsp+120h+var_100], rax
0x18000bd23  lea     rdx, byte_180018BBF
0x18000bd2a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000bd2f  jmp     short loc_18000BD35
0x18000bd31  lea     rdi, [r15+48h]
0x18000bd35  test    ebx, ebx
0x18000bd37  js      loc_18000C11B
0x18000bd3d  mov     rbx, [rbp+57h+var_A0]
0x18000bd41  mov     rsi, [rbx]
0x18000bd44  mov     rcx, [rbp+57h+var_A8]; string
0x18000bd48  call    cs:__imp_WindowsDeleteString
0x18000bd4e  mov     [rbp+57h+var_A8], 0
0x18000bd56  mov     [rbp+57h+string], 0
0x18000bd5e  lea     r9, [rbp+57h+string]; string
0x18000bd62  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000bd66  mov     edx, 0Dh; length
0x18000bd6b  lea     rcx, aParametername; "parameterName"
0x18000bd72  call    cs:__imp_WindowsCreateStringReference
0x18000bd78  test    eax, eax
0x18000bd7a  js      loc_18000C1C4
0x18000bd80  lea     r8, [rbp+57h+var_A8]
0x18000bd84  mov     rdx, [rbp+57h+string]
0x18000bd88  mov     rcx, rbx
0x18000bd8b  mov     rax, [rsi+50h]
0x18000bd8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd94  mov     ebx, eax
0x18000bd96  mov     eax, cs:dword_18001D000
0x18000bd9c  cmp     eax, 5
0x18000bd9f  jbe     short loc_18000BE16
0x18000bda1  lea     rax, aGetParameterNa; "Get parameter name"
0x18000bda8  mov     [rbp+57h+var_80], rax
0x18000bdac  mov     dword ptr [rbp+57h+var_B8], ebx
0x18000bdaf  mov     [rbp+57h+var_C0], 10Eh
0x18000bdb6  lea     rax, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\winrt\\dia"...
0x18000bdbd  mov     [rbp+57h+var_88], rax
0x18000bdc1  lea     rax, aWindowsSystemD_0; "Windows::System::Diagnostics::Diagnosti"...
0x18000bdc8  mov     [rbp+57h+var_90], rax
0x18000bdcc  mov     [rbp+57h+var_98], rdi
0x18000bdd0  lea     rax, [rbp+57h+var_80]
0x18000bdd4  mov     [rsp+120h+var_D8], rax
0x18000bdd9  lea     rax, [rbp+57h+var_B8]
0x18000bddd  mov     [rsp+120h+var_E0], rax
0x18000bde2  lea     rax, [rbp+57h+var_C0]
0x18000bde6  mov     [rsp+120h+var_E8], rax
0x18000bdeb  lea     rax, [rbp+57h+var_88]
0x18000bdef  mov     [rsp+120h+var_F0], rax
0x18000bdf4  lea     rax, [rbp+57h+var_90]
0x18000bdf8  mov     [rsp+120h+var_F8], rax
0x18000bdfd  lea     rax, [rbp+57h+var_98]
0x18000be01  mov     [rsp+120h+var_100], rax
0x18000be06  lea     rdx, byte_180018B59
0x18000be0d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000be12  lea     rdi, [r15+48h]
0x18000be16  xor     esi, esi
0x18000be18  test    ebx, ebx
0x18000be1a  js      loc_18000C11B
0x18000be20  mov     rbx, [rbp+57h+var_A0]
0x18000be24  mov     rsi, [rbx]
0x18000be27  mov     rcx, [rbp+57h+var_B0]; string
0x18000be2b  call    cs:__imp_WindowsDeleteString
0x18000be31  mov     [rbp+57h+var_B0], 0
0x18000be39  mov     [rbp+57h+string], 0
0x18000be41  lea     r9, [rbp+57h+string]; string
0x18000be45  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000be49  mov     edx, 0Eh; length
0x18000be4e  lea     rcx, aParametervalue; "parameterValue"
0x18000be55  call    cs:__imp_WindowsCreateStringReference
0x18000be5b  test    eax, eax
0x18000be5d  js      loc_18000C1BC
0x18000be63  lea     r8, [rbp+57h+var_B0]
0x18000be67  mov     rdx, [rbp+57h+string]
0x18000be6b  mov     rcx, rbx
0x18000be6e  mov     rax, [rsi+50h]
0x18000be72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be77  mov     ebx, eax
0x18000be79  mov     eax, cs:dword_18001D000
0x18000be7f  cmp     eax, 5
0x18000be82  jbe     short loc_18000BEF5
0x18000be84  lea     rax, aGetParameterVa; "Get parameter value"
0x18000be8b  mov     [rbp+57h+var_80], rax
0x18000be8f  mov     dword ptr [rbp+57h+var_B8], ebx
0x18000be92  mov     [rbp+57h+var_C0], 116h
0x18000be99  lea     rax, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\winrt\\dia"...
0x18000bea0  mov     [rbp+57h+var_88], rax
0x18000bea4  lea     rax, aWindowsSystemD_0; "Windows::System::Diagnostics::Diagnosti"...
0x18000beab  mov     [rbp+57h+var_90], rax
0x18000beaf  mov     [rbp+57h+var_98], rdi
0x18000beb3  lea     rax, [rbp+57h+var_80]
0x18000beb7  mov     [rsp+120h+var_D8], rax
  ... truncated ...
```
