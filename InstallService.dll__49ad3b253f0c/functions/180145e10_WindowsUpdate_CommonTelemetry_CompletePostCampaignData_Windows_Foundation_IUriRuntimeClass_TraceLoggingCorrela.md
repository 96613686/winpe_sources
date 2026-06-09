# WindowsUpdate::CommonTelemetry::CompletePostCampaignData(Windows::Foundation::IUriRuntimeClass *,TraceLoggingCorrelationVector *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,unsigned __int64,ulong,long)

- ea: `0x180145e10`
- end: `0x18014646f`
- name: `?CompletePostCampaignData@CommonTelemetry@WindowsUpdate@@YAXPEAUIUriRuntimeClass@Foundation@Windows@@PEAVTraceLoggingCorrelationVector@@PEAUHSTRING__@@22222_KKJ@Z`
- size: `1631`
- prototype: `void(WindowsUpdate::CommonTelemetry *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, struct TraceLoggingCorrelationVector *, HSTRING, HSTRING, HSTRING, HSTRING, HSTRING, HSTRING, unsigned __int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180083240`

## callees

- `0x180001b88`
- `0x1800052f4`
- `0x180009ea0`
- `0x180020868`
- `0x180022298`
- `0x180042b9c`
- `0x18011317c`
- `0x18013cddc`
- `0x180145e10`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180145e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180146446`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180145e7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180146446`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145ed7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145eea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145ef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145f08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145f17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145f26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145f85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801460dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801460fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014611d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180146137`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180146151`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014616b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014625d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145ed7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145eea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145ef9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145f08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145f17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145f26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180145f85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801460dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801460fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014611d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180146137`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180146151`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014616b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014625d`

## string_xrefs

- `0x1801461d7`: `protocol`
- `0x1801461c3`: `protocolStatusCode`
- `0x18014622a`: `serviceErrorCode`
- `0x180146294`: `PartB_Ms.Qos.OutgoingServiceRequest`
- `0x180146263`: `targetUri`
- `0x1801462f5`: `onecoreuap\enduser\winstore\installservice\libqueue2\commontelemetry.cpp`
- `0x1801462e1`: `WindowsUpdate::CommonTelemetry::CompletePostCampaignData`
- `0x1801462c8`: `CompletePostCampaignData`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WindowsUpdate::CommonTelemetry::CompletePostCampaignData(
        WindowsUpdate::CommonTelemetry *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        struct TraceLoggingCorrelationVector *a3,
        HSTRING a4,
        HSTRING a5,
        HSTRING a6,
        HSTRING a7,
        HSTRING a8,
        HSTRING a9,
        unsigned __int64 a10,
        unsigned int a11)
{
  void (__fastcall *v15)(WindowsUpdate::CommonTelemetry *, HSTRING *); // rbx
  HSTRING v16; // rdi
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  PCWSTR v20; // rax
  PCWSTR v21; // rax
  PCWSTR v22; // rax
  PCWSTR v23; // rax
  PCWSTR v24; // rax
  PCWSTR v25; // rax
  PCWSTR v26; // rax
  int v27; // edx
  int v28; // r9d
  bool v29[8]; // [rsp+E0h] [rbp-80h] BYREF
  HSTRING v30; // [rsp+E8h] [rbp-78h] BYREF
  HSTRING StringRawBuffer; // [rsp+F0h] [rbp-70h] BYREF
  int v32; // [rsp+F8h] [rbp-68h]
  unsigned int v33; // [rsp+100h] [rbp-60h] BYREF
  int v34; // [rsp+104h] [rbp-5Ch] BYREF
  int v35; // [rsp+108h] [rbp-58h] BYREF
  int v36; // [rsp+10Ch] [rbp-54h] BYREF
  HSTRING string; // [rsp+110h] [rbp-50h] BYREF
  bool v38; // [rsp+118h] [rbp-48h]
  _QWORD v39[2]; // [rsp+120h] [rbp-40h] BYREF
  _QWORD v40[2]; // [rsp+130h] [rbp-30h] BYREF
  _QWORD v41[2]; // [rsp+140h] [rbp-20h] BYREF
  PCWSTR v42; // [rsp+150h] [rbp-10h] BYREF
  int v43; // [rsp+158h] [rbp-8h]
  _QWORD v44[2]; // [rsp+160h] [rbp+0h] BYREF
  _QWORD v45[2]; // [rsp+170h] [rbp+10h] BYREF
  _QWORD v46[2]; // [rsp+180h] [rbp+20h] BYREF
  _QWORD v47[2]; // [rsp+190h] [rbp+30h] BYREF
  _QWORD v48[2]; // [rsp+1A0h] [rbp+40h] BYREF
  _QWORD v49[2]; // [rsp+1B0h] [rbp+50h] BYREF
  _QWORD v50[2]; // [rsp+1C0h] [rbp+60h] BYREF
  _QWORD v51[2]; // [rsp+1D0h] [rbp+70h] BYREF
  _QWORD v52[2]; // [rsp+1E0h] [rbp+80h] BYREF
  _QWORD v53[2]; // [rsp+1F0h] [rbp+90h] BYREF
  const char *v54; // [rsp+200h] [rbp+A0h] BYREF
  unsigned int v55; // [rsp+208h] [rbp+A8h]
  const char *v56; // [rsp+210h] [rbp+B0h] BYREF
  int v57; // [rsp+218h] [rbp+B8h]
  _QWORD v58[2]; // [rsp+220h] [rbp+C0h] BYREF
  _QWORD v59[2]; // [rsp+230h] [rbp+D0h] BYREF
  const char *v60; // [rsp+240h] [rbp+E0h] BYREF
  int v61; // [rsp+248h] [rbp+E8h]
  _QWORD v62[2]; // [rsp+250h] [rbp+F0h] BYREF
  _QWORD v63[2]; // [rsp+260h] [rbp+100h] BYREF
  _BYTE v64[32]; // [rsp+270h] [rbp+110h] BYREF
  _BYTE v65[32]; // [rsp+290h] [rbp+130h] BYREF
  _BYTE v66[144]; // [rsp+2B0h] [rbp+150h] BYREF
  char v67[144]; // [rsp+340h] [rbp+1E0h] BYREF

  StringRawBuffer = a7;
  string = a8;
  v30 = 0;
  v15 = *(void (__fastcall **)(WindowsUpdate::CommonTelemetry *, HSTRING *))(*(_QWORD *)this + 48LL);
  WindowsDeleteString(0);
  v30 = 0;
  v15(this, &v30);
  if ( (unsigned int)dword_1802C3108 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1802C3108, 0x400000000000LL) )
  {
    v33 = a11;
    v39[0] = WindowsGetStringRawBuffer(string, 0);
    v16 = StringRawBuffer;
    StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(StringRawBuffer, 0);
    v40[0] = WindowsGetStringRawBuffer(a6, 0);
    v41[0] = WindowsGetStringRawBuffer(a5, 0);
    v42 = WindowsGetStringRawBuffer(a4, 0);
    v44[0] = WindowsGetStringRawBuffer((HSTRING)a3, 0);
    v45[0] = 0;
    v46[0] = 0;
    v47[0] = 0;
    v48[0] = 0;
    v34 = a10;
    v49[0] = L"HTTPS";
    v50[0] = L"JSON";
    v51[0] = L"POST";
    v29[0] = a11 == 0;
    v35 = 0;
    v36 = (int)a9;
    v52[0] = WindowsGetStringRawBuffer(v30, 0);
    v53[0] = L"PostCampaignData";
    v54 = (const char *)_TlgCVGetter::_TlgCVGetter((_TlgCVGetter *)v66, a2);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)&dword_18028D614,
      v18,
      v19,
      (__int64)&v54,
      (__int64)v53,
      (__int64)v52,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)v29,
      (__int64)v51,
      (__int64)v50,
      (__int64)v49,
      (__int64)&v34,
      (__int64)v48,
      (__int64)v47,
      (__int64)v46,
      (__int64)v45,
      (__int64)v44,
      (__int64)&v42,
      (__int64)v41,
      (__int64)v40,
      (__int64)&StringRawBuffer,
      (__int64)v39,
      (__int64)&v33);
  }
  else
  {
    v16 = StringRawBuffer;
  }
  TraceLoggingCorrelationVector::ToStringImpl(a2, _InterlockedExchangeAdd64((volatile signed __int64 *)a2 + 17, 0), v67);
  v54 = "HResult";
  v55 = a11;
  v20 = WindowsGetStringRawBuffer(string, 0);
  v53[0] = "ExtendedCampaignId";
  v53[1] = v20;
  v21 = WindowsGetStringRawBuffer(v16, 0);
  v52[0] = "CampaignId";
  v52[1] = v21;
  v22 = WindowsGetStringRawBuffer(a6, 0);
  v51[0] = "ClientId";
  v51[1] = v22;
  v23 = WindowsGetStringRawBuffer(a5, 0);
  v50[0] = "CatalogId";
  v50[1] = v23;
  v24 = WindowsGetStringRawBuffer(a4, 0);
  v49[0] = "SkuId";
  v49[1] = v24;
  v25 = WindowsGetStringRawBuffer((HSTRING)a3, 0);
  v48[0] = "ProductId";
  v48[1] = v25;
  v47[0] = "dependencyType";
  v47[1] = word_18023B3BA;
  v46[0] = "dependencyName";
  v46[1] = word_18023B3BA;
  v45[0] = "dependencyOperationVersion";
  v45[1] = word_18023B3BA;
  v44[0] = "dependencyOperationName";
  v44[1] = word_18023B3BA;
  v42 = (PCWSTR)"protocolStatusCode";
  v43 = a10;
  v41[0] = "protocol";
  v41[1] = L"HTTPS";
  v40[0] = "responseContentType";
  v40[1] = L"JSON";
  v39[0] = "requestMethod";
  v39[1] = L"POST";
  string = (HSTRING)"succeeded";
  v38 = a11 == 0;
  StringRawBuffer = (HSTRING)"serviceErrorCode";
  v32 = 0;
  v56 = "latencyMs";
  v57 = (int)a9;
  v26 = WindowsGetStringRawBuffer(v30, 0);
  v58[0] = "targetUri";
  v58[1] = v26;
  v59[0] = "operationName";
  v59[1] = L"PostCampaignData";
  v60 = "PartB_Ms.Qos.OutgoingServiceRequest";
  v61 = 14;
  v62[0] = "__TlgCV__";
  v62[1] = v67;
  v63[0] = "CompletePostCampaignData";
  v63[1] = 24;
  std::string::string(v65, "WindowsUpdate::CommonTelemetry::CompletePostCampaignData");
  std::string::string(v64, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\commontelemetry.cpp");
  Logging::StoreLoggingWrite<std::pair<char const *,char const *>,std::pair<char const *,int>,std::pair<char const *,unsigned short const *>,std::pair<char const *,unsigned short const *>,std::pair<char const *,int>,std::pair<char const *,int>,std::pair<char const *,bool>,std::pair<char const *,unsigned short const *>,std::pair<char const *,unsigned short const *>,std::pair<char const *,unsigned short const *>,std::pair<char const *,unsigned long>,std::pair<char const *,char const *>,std::pair<char const *,char const *>,std::pair<char const *,char const *>,std::pair<char const *,char const *>,std::pair<char const *,unsigned short const *>,std::pair<char const *,unsigned short const *>,std::pair<char const *,unsigned short const *>,std::pair<char const *,unsigned short const *>,std::pair<char const *,unsigned short const *>,std::pair<char const *,unsigned short const *>,std::pair<char const *,long>>(
    (unsigned int)v64,
    v27,
    (unsigned int)v65,
    v28,
    (__int64)v63,
    (__int64)v62,
    (__int64)&v60,
    (__int64)v59,
    (__int64)v58,
    (__int64)&v56,
    (__int64)&StringRawBuffer,
    (__int64)&string,
    (__int64)v39,
    (__int64)v40,
    (__int64)v41,
    (__int64)&v42,
    (__int64)v44,
    (__int64)v45,
    (__int64)v46,
    (__int64)v47,
    (__int64)v48,
    (__int64)v49,
    (__int64)v50,
    (__int64)v51,
    (__int64)v52,
    (__int64)v53,
    (__int64)&v54);
  std::string::~string(v64);
  std::string::~string(v65);
  WindowsDeleteString(v30);
}

```

## disassembly

```asm
0x180145e10  push    rbp
0x180145e12  push    rbx
0x180145e13  push    rsi
0x180145e14  push    rdi
0x180145e15  push    r12
0x180145e17  push    r13
0x180145e19  push    r14
0x180145e1b  push    r15
0x180145e1d  lea     rbp, [rsp-288h]
0x180145e25  sub     rsp, 3E8h
0x180145e2c  mov     rax, cs:__security_cookie
0x180145e33  xor     rax, rsp
0x180145e36  mov     [rbp+2C0h+var_50], rax
0x180145e3d  mov     r15, r9
0x180145e40  mov     r14, r8
0x180145e43  mov     rsi, rdx
0x180145e46  mov     rdi, rcx
0x180145e49  mov     r12, [rbp+2C0h+arg_20]
0x180145e50  mov     r13, [rbp+2C0h+arg_28]
0x180145e57  mov     rax, [rbp+2C0h+arg_30]
0x180145e5e  mov     [rbp+2C0h+var_330], rax
0x180145e62  mov     rax, [rbp+2C0h+arg_38]
0x180145e69  mov     [rbp+2C0h+string], rax
0x180145e6d  mov     [rbp+2C0h+var_338], 0
0x180145e75  mov     rax, [rcx]
0x180145e78  mov     rbx, [rax+30h]
0x180145e7c  xor     ecx, ecx; string
0x180145e7e  call    cs:__imp_WindowsDeleteString
0x180145e84  mov     [rbp+2C0h+var_338], 0
0x180145e8c  lea     rdx, [rbp+2C0h+var_338]
0x180145e90  mov     rcx, rdi
0x180145e93  mov     rax, rbx
0x180145e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145e9b  mov     eax, cs:dword_1802C3108
0x180145ea1  mov     ebx, [rbp+2C0h+arg_50]
0x180145ea7  cmp     eax, 5
0x180145eaa  jbe     loc_1801460A5
0x180145eb0  mov     rdx, 400000000000h
0x180145eba  lea     rcx, dword_1802C3108
0x180145ec1  call    _tlgKeywordOn
0x180145ec6  test    al, al
0x180145ec8  jz      loc_1801460A5
0x180145ece  mov     [rbp+2C0h+var_320], ebx
0x180145ed1  xor     edx, edx; length
0x180145ed3  mov     rcx, [rbp+2C0h+string]; string
0x180145ed7  call    cs:__imp_WindowsGetStringRawBuffer
0x180145edd  mov     [rbp+2C0h+var_300], rax
0x180145ee1  xor     edx, edx; length
0x180145ee3  mov     rdi, [rbp+2C0h+var_330]
0x180145ee7  mov     rcx, rdi; string
0x180145eea  call    cs:__imp_WindowsGetStringRawBuffer
0x180145ef0  mov     [rbp+2C0h+var_330], rax
0x180145ef4  xor     edx, edx; length
0x180145ef6  mov     rcx, r13; string
0x180145ef9  call    cs:__imp_WindowsGetStringRawBuffer
0x180145eff  mov     [rbp+2C0h+var_2F0], rax
0x180145f03  xor     edx, edx; length
0x180145f05  mov     rcx, r12; string
0x180145f08  call    cs:__imp_WindowsGetStringRawBuffer
0x180145f0e  mov     [rbp+2C0h+var_2E0], rax
0x180145f12  xor     edx, edx; length
0x180145f14  mov     rcx, r15; string
0x180145f17  call    cs:__imp_WindowsGetStringRawBuffer
0x180145f1d  mov     [rbp+2C0h+var_2D0], rax
0x180145f21  xor     edx, edx; length
0x180145f23  mov     rcx, r14; string
0x180145f26  call    cs:__imp_WindowsGetStringRawBuffer
0x180145f2c  mov     [rbp+2C0h+var_2C0], rax
0x180145f30  xor     ecx, ecx
0x180145f32  mov     [rbp+2C0h+var_2B0], rcx
0x180145f36  mov     [rbp+2C0h+var_2A0], rcx
0x180145f3a  mov     [rbp+2C0h+var_290], rcx
0x180145f3e  mov     [rbp+2C0h+var_280], rcx
0x180145f42  mov     eax, dword ptr [rbp+2C0h+arg_48]
0x180145f48  mov     [rbp+2C0h+var_31C], eax
0x180145f4b  lea     rax, aHttps_0; "HTTPS"
0x180145f52  mov     [rbp+2C0h+var_270], rax
0x180145f56  lea     rax, aJson; "JSON"
0x180145f5d  mov     [rbp+2C0h+var_260], rax
0x180145f61  lea     rax, aPost; "POST"
0x180145f68  mov     [rbp+2C0h+var_250], rax
0x180145f6c  test    ebx, ebx
0x180145f6e  setz    [rbp+2C0h+var_340]
0x180145f72  mov     [rbp+2C0h+var_318], ecx
0x180145f75  mov     rax, [rbp+2C0h+arg_40]
0x180145f7c  mov     [rbp+2C0h+var_314], eax
0x180145f7f  xor     edx, edx; length
0x180145f81  mov     rcx, [rbp+2C0h+var_338]; string
0x180145f85  call    cs:__imp_WindowsGetStringRawBuffer
0x180145f8b  mov     [rbp+2C0h+var_240], rax
0x180145f92  lea     rax, aPostcampaignda_0; "PostCampaignData"
0x180145f99  mov     [rbp+2C0h+var_230], rax
0x180145fa0  mov     rdx, rsi; struct TraceLoggingCorrelationVector *
0x180145fa3  lea     rcx, [rbp+2C0h+var_170]; this
0x180145faa  call    ??0_TlgCVGetter@@QEAA@PEAVTraceLoggingCorrelationVector@@@Z; _TlgCVGetter::_TlgCVGetter(TraceLoggingCorrelationVector *)
0x180145faf  mov     [rbp+2C0h+var_220], rax
0x180145fb6  lea     rax, [rbp+2C0h+var_320]
0x180145fba  mov     [rsp+420h+var_360], rax
0x180145fc2  lea     rax, [rbp+2C0h+var_300]
0x180145fc6  mov     [rsp+420h+var_368], rax
0x180145fce  lea     rax, [rbp+2C0h+var_330]
0x180145fd2  mov     [rsp+420h+var_370], rax
0x180145fda  lea     rax, [rbp+2C0h+var_2F0]
0x180145fde  mov     [rsp+420h+var_378], rax
0x180145fe6  lea     rax, [rbp+2C0h+var_2E0]
0x180145fea  mov     [rsp+420h+var_380], rax
0x180145ff2  lea     rax, [rbp+2C0h+var_2D0]
0x180145ff6  mov     [rsp+420h+var_388], rax
0x180145ffe  lea     rax, [rbp+2C0h+var_2C0]
0x180146002  mov     [rsp+420h+var_390], rax
0x18014600a  lea     rax, [rbp+2C0h+var_2B0]
0x18014600e  mov     [rsp+420h+var_398], rax
0x180146016  lea     rax, [rbp+2C0h+var_2A0]
0x18014601a  mov     [rsp+420h+var_3A0], rax
0x180146022  lea     rax, [rbp+2C0h+var_290]
0x180146026  mov     [rsp+420h+var_3A8], rax
0x18014602b  lea     rax, [rbp+2C0h+var_280]
0x18014602f  mov     [rsp+420h+var_3B0], rax
0x180146034  lea     rax, [rbp+2C0h+var_31C]
0x180146038  mov     [rsp+420h+var_3B8], rax
0x18014603d  lea     rax, [rbp+2C0h+var_270]
0x180146041  mov     [rsp+420h+var_3C0], rax
0x180146046  lea     rax, [rbp+2C0h+var_260]
0x18014604a  mov     [rsp+420h+var_3C8], rax
0x18014604f  lea     rax, [rbp+2C0h+var_250]
0x180146053  mov     [rsp+420h+var_3D0], rax
0x180146058  lea     rax, [rbp+2C0h+var_340]
0x18014605c  mov     [rsp+420h+var_3D8], rax
0x180146061  lea     rax, [rbp+2C0h+var_318]
0x180146065  mov     [rsp+420h+var_3E0], rax
0x18014606a  lea     rax, [rbp+2C0h+var_314]
0x18014606e  mov     [rsp+420h+var_3E8], rax
0x180146073  lea     rax, [rbp+2C0h+var_240]
0x18014607a  mov     [rsp+420h+var_3F0], rax
0x18014607f  lea     rax, [rbp+2C0h+var_230]
0x180146086  mov     [rsp+420h+var_3F8], rax
0x18014608b  lea     rax, [rbp+2C0h+var_220]
0x180146092  mov     [rsp+420h+var_400], rax
0x180146097  lea     rdx, dword_18028D614
0x18014609e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByVal@$00@@U2@U2@U2@U3@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByVal@$00@@444544444444445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1801460a3  jmp     short loc_1801460A9
0x1801460a5  mov     rdi, [rbp+2C0h+var_330]
0x1801460a9  xor     edx, edx
0x1801460ab  lock xadd [rsi+88h], rdx; unsigned __int64
0x1801460b4  lea     r8, [rbp+2C0h+var_E0]; char *
0x1801460bb  mov     rcx, rsi; this
0x1801460be  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1801460c3  lea     rax, aHresult_0; "HResult"
0x1801460ca  mov     [rbp+2C0h+var_220], rax
0x1801460d1  mov     [rbp+2C0h+var_218], ebx
0x1801460d7  xor     edx, edx; length
0x1801460d9  mov     rcx, [rbp+2C0h+string]; string
0x1801460dd  call    cs:__imp_WindowsGetStringRawBuffer
0x1801460e3  lea     rcx, aExtendedcampai; "ExtendedCampaignId"
0x1801460ea  mov     [rbp+2C0h+var_230], rcx
0x1801460f1  mov     [rbp+2C0h+var_228], rax
0x1801460f8  xor     edx, edx; length
0x1801460fa  mov     rcx, rdi; string
0x1801460fd  call    cs:__imp_WindowsGetStringRawBuffer
0x180146103  lea     rcx, aCampaignid_0; "CampaignId"
0x18014610a  mov     [rbp+2C0h+var_240], rcx
0x180146111  mov     [rbp+2C0h+var_238], rax
0x180146118  xor     edx, edx; length
0x18014611a  mov     rcx, r13; string
0x18014611d  call    cs:__imp_WindowsGetStringRawBuffer
0x180146123  lea     rcx, aClientid_0; "ClientId"
0x18014612a  mov     [rbp+2C0h+var_250], rcx
0x18014612e  mov     [rbp+2C0h+var_248], rax
0x180146132  xor     edx, edx; length
0x180146134  mov     rcx, r12; string
0x180146137  call    cs:__imp_WindowsGetStringRawBuffer
0x18014613d  lea     rcx, aCatalogid_0; "CatalogId"
0x180146144  mov     [rbp+2C0h+var_260], rcx
0x180146148  mov     [rbp+2C0h+var_258], rax
0x18014614c  xor     edx, edx; length
0x18014614e  mov     rcx, r15; string
0x180146151  call    cs:__imp_WindowsGetStringRawBuffer
0x180146157  lea     rcx, aSkuid; "SkuId"
0x18014615e  mov     [rbp+2C0h+var_270], rcx
0x180146162  mov     [rbp+2C0h+var_268], rax
0x180146166  xor     edx, edx; length
0x180146168  mov     rcx, r14; string
0x18014616b  call    cs:__imp_WindowsGetStringRawBuffer
0x180146171  lea     rcx, aProductid; "ProductId"
0x180146178  mov     [rbp+2C0h+var_280], rcx
0x18014617c  mov     [rbp+2C0h+var_278], rax
0x180146180  lea     rax, aDependencytype; "dependencyType"
0x180146187  mov     [rbp+2C0h+var_290], rax
0x18014618b  lea     rcx, word_18023B3BA
0x180146192  mov     [rbp+2C0h+var_288], rcx
0x180146196  lea     rax, aDependencyname; "dependencyName"
0x18014619d  mov     [rbp+2C0h+var_2A0], rax
0x1801461a1  mov     [rbp+2C0h+var_298], rcx
0x1801461a5  lea     rax, aDependencyoper; "dependencyOperationVersion"
0x1801461ac  mov     [rbp+2C0h+var_2B0], rax
0x1801461b0  mov     [rbp+2C0h+var_2A8], rcx
0x1801461b4  lea     rax, aDependencyoper_0; "dependencyOperationName"
0x1801461bb  mov     [rbp+2C0h+var_2C0], rax
0x1801461bf  mov     [rbp+2C0h+var_2B8], rcx
0x1801461c3  lea     rax, aProtocolstatus; "protocolStatusCode"
0x1801461ca  mov     [rbp+2C0h+var_2D0], rax
0x1801461ce  mov     eax, dword ptr [rbp+2C0h+arg_48]
0x1801461d4  mov     [rbp+2C0h+var_2C8], eax
0x1801461d7  lea     rax, aProtocol; "protocol"
0x1801461de  mov     [rbp+2C0h+var_2E0], rax
0x1801461e2  lea     rax, aHttps_0; "HTTPS"
0x1801461e9  mov     [rbp+2C0h+var_2D8], rax
0x1801461ed  lea     rax, aResponseconten; "responseContentType"
0x1801461f4  mov     [rbp+2C0h+var_2F0], rax
0x1801461f8  lea     rax, aJson; "JSON"
0x1801461ff  mov     [rbp+2C0h+var_2E8], rax
0x180146203  lea     rax, aRequestmethod; "requestMethod"
0x18014620a  mov     [rbp+2C0h+var_300], rax
0x18014620e  lea     rax, aPost; "POST"
0x180146215  mov     [rbp+2C0h+var_2F8], rax
0x180146219  lea     rax, aSucceeded; "succeeded"
0x180146220  mov     [rbp+2C0h+string], rax
0x180146224  test    ebx, ebx
0x180146226  setz    [rbp+2C0h+var_308]
0x18014622a  lea     rax, aServiceerrorco; "serviceErrorCode"
0x180146231  mov     [rbp+2C0h+var_330], rax
0x180146235  mov     [rbp+2C0h+var_328], 0
0x18014623c  lea     rax, aLatencyms; "latencyMs"
0x180146243  mov     [rbp+2C0h+var_210], rax
0x18014624a  mov     rax, [rbp+2C0h+arg_40]
0x180146251  mov     [rbp+2C0h+var_208], eax
0x180146257  xor     edx, edx; length
0x180146259  mov     rcx, [rbp+2C0h+var_338]; string
0x18014625d  call    cs:__imp_WindowsGetStringRawBuffer
0x180146263  lea     rcx, aTargeturi; "targetUri"
0x18014626a  mov     [rbp+2C0h+var_200], rcx
0x180146271  mov     [rbp+2C0h+var_1F8], rax
0x180146278  lea     rax, aOperationname; "operationName"
0x18014627f  mov     [rbp+2C0h+var_1F0], rax
0x180146286  lea     rax, aPostcampaignda_0; "PostCampaignData"
0x18014628d  mov     [rbp+2C0h+var_1E8], rax
0x180146294  lea     rax, aPartbMsQosOutg; "PartB_Ms.Qos.OutgoingServiceRequest"
0x18014629b  mov     [rbp+2C0h+var_1E0], rax
0x1801462a2  mov     [rbp+2C0h+var_1D8], 0Eh
0x1801462ac  lea     rax, aTlgcv; "__TlgCV__"
0x1801462b3  mov     [rbp+2C0h+var_1D0], rax
0x1801462ba  lea     rax, [rbp+2C0h+var_E0]
0x1801462c1  mov     [rbp+2C0h+var_1C8], rax
0x1801462c8  lea     rax, aCompletepostca; "CompletePostCampaignData"
0x1801462cf  mov     [rbp+2C0h+var_1C0], rax
0x1801462d6  mov     [rbp+2C0h+var_1B8], 18h
0x1801462e1  lea     rdx, aWindowsupdateC_11; "WindowsUpdate::CommonTelemetry::Complet"...
0x1801462e8  lea     rcx, [rbp+2C0h+var_190]
0x1801462ef  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801462f4  nop
0x1801462f5  lea     rdx, aOnecoreuapEndu_82; "onecoreuap\\enduser\\winstore\\installs"...
0x1801462fc  lea     rcx, [rbp+2C0h+var_1B0]
0x180146303  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180146308  nop
0x180146309  lea     rax, [rbp+2C0h+var_220]
0x180146310  mov     [rsp+420h+var_350], rax
0x180146318  lea     rax, [rbp+2C0h+var_230]
0x18014631f  mov     [rsp+420h+var_358], rax
0x180146327  lea     rax, [rbp+2C0h+var_240]
0x18014632e  mov     [rsp+420h+var_360], rax
0x180146336  lea     rax, [rbp+2C0h+var_250]
0x18014633a  mov     [rsp+420h+var_368], rax
0x180146342  lea     rax, [rbp+2C0h+var_260]
0x180146346  mov     [rsp+420h+var_370], rax
0x18014634e  lea     rax, [rbp+2C0h+var_270]
0x180146352  mov     [rsp+420h+var_378], rax
0x18014635a  lea     rax, [rbp+2C0h+var_280]
0x18014635e  mov     [rsp+420h+var_380], rax
0x180146366  lea     rax, [rbp+2C0h+var_290]
0x18014636a  mov     [rsp+420h+var_388], rax
0x180146372  lea     rax, [rbp+2C0h+var_2A0]
0x180146376  mov     [rsp+420h+var_390], rax
0x18014637e  lea     rax, [rbp+2C0h+var_2B0]
0x180146382  mov     [rsp+420h+var_398], rax
0x18014638a  lea     rax, [rbp+2C0h+var_2C0]
0x18014638e  mov     [rsp+420h+var_3A0], rax
0x180146396  lea     rax, [rbp+2C0h+var_2D0]
0x18014639a  mov     [rsp+420h+var_3A8], rax
0x18014639f  lea     rax, [rbp+2C0h+var_2E0]
0x1801463a3  mov     [rsp+420h+var_3B0], rax
0x1801463a8  lea     rax, [rbp+2C0h+var_2F0]
0x1801463ac  mov     [rsp+420h+var_3B8], rax
0x1801463b1  lea     rax, [rbp+2C0h+var_300]
0x1801463b5  mov     [rsp+420h+var_3C0], rax
0x1801463ba  lea     rax, [rbp+2C0h+string]
0x1801463be  mov     [rsp+420h+var_3C8], rax
0x1801463c3  lea     rax, [rbp+2C0h+var_330]
0x1801463c7  mov     [rsp+420h+var_3D0], rax
0x1801463cc  lea     rax, [rbp+2C0h+var_210]
0x1801463d3  mov     [rsp+420h+var_3D8], rax
0x1801463d8  lea     rax, [rbp+2C0h+var_200]
0x1801463df  mov     [rsp+420h+var_3E0], rax
0x1801463e4  lea     rax, [rbp+2C0h+var_1F0]
0x1801463eb  mov     [rsp+420h+var_3E8], rax
0x1801463f0  lea     rax, [rbp+2C0h+var_1E0]
0x1801463f7  mov     [rsp+420h+var_3F0], rax
0x1801463fc  lea     rax, [rbp+2C0h+var_1D0]
0x180146403  mov     [rsp+420h+var_3F8], rax
0x180146408  lea     rax, [rbp+2C0h+var_1C0]
0x18014640f  mov     [rsp+420h+var_400], rax
  ... truncated ...
```
