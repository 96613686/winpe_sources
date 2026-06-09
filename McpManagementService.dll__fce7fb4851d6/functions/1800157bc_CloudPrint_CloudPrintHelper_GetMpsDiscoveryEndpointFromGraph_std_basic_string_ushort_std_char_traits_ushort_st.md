# CloudPrint::CloudPrintHelper::GetMpsDiscoveryEndpointFromGraph(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool,bool,HWND__ *)

- ea: `0x1800157bc`
- end: `0x180015f59`
- name: `?GetMpsDiscoveryEndpointFromGraph@CloudPrintHelper@CloudPrint@@IEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV34@1_N2PEAUHWND__@@@Z`
- size: `1949`
- prototype: `__int64 __fastcall(CloudPrint::CloudPrintHelper *this, __int64, __int64, __int64, __int64, char, char)`
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001963c`

## callees

- `0x180003a60`
- `0x180003aa0`
- `0x180004d4c`
- `0x1800067a4`
- `0x180006b70`
- `0x18000c4cc`
- `0x18000e164`
- `0x18000e208`
- `0x18000e2dc`
- `0x18000e5e8`
- `0x18000f804`
- `0x18000f848`
- `0x18000f8ec`
- `0x18000f958`
- `0x180011d98`
- `0x180011de0`
- `0x180011f68`
- `0x1800120a0`
- `0x18001227c`
- `0x180012668`
- `0x1800129c4`
- `0x180012a44`
- `0x180012bc0`
- `0x180012e90`
- `0x180012f08`
- `0x180013948`
- `0x1800157bc`
- `0x180016920`
- `0x180018668`
- `0x18001aab4`
- `0x18001aaf4`
- `0x18001ac7c`
- `0x18001b8c4`
- `0x18001c0a8`
- `0x18001c298`
- `0x18001db04`
- `0x18001db44`
- `0x18001ddb4`
- `0x18001df80`
- `0x18001f77c`
- `0x180020e9c`

## string_xrefs

- `0x180015a53`: `/.well-known/openid-configuration`
- `0x180015c46`: `/print/services/f4cfee8b-4117-4773-a2f0-3807beb282b9?$expand=endpoints`
- `0x1800158f8`: `application/json`
- `0x180015b93`: `Failed to parse AAD OpenID Connect metadata document response with %#x, using GCC High USGov endpoint.`
- `0x180015ba8`: `Failed to parse AAD OpenID Connect metadata document response with %#x, using GCC High USGov endpoint.`
- `0x180015be6`: `Failure response trying to get AAD OpenID Connect metadata document, using GCC High USGov endpoint. HttpStatus=%u`
- `0x180015bfb`: `Failure response trying to get AAD OpenID Connect metadata document, using GCC High USGov endpoint. HttpStatus=%u`
- `0x180015e9e`: `Failed to parse MS Graph Services response with %#x`
- `0x180015eb3`: `Failed to parse MS Graph Services response with %#x`

## pseudocode

```c
__int64 __fastcall CloudPrint::CloudPrintHelper::GetMpsDiscoveryEndpointFromGraph(
        CloudPrint::CloudPrintHelper *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        char a7)
{
  CloudPrint::CloudPrintHelper *v8; // rsi
  __int64 v9; // r14
  int v10; // edx
  int v11; // r8d
  __int64 v12; // r9
  int AuthorizationHeaderInternal; // ebx
  void *v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rdx
  struct PrintCore::HttpRestChannel *v18; // rbx
  int v19; // eax
  int v20; // edi
  int v21; // eax
  unsigned int v22; // edi
  __int64 v23; // rax
  __int64 v24; // rax
  const char *v25; // r9
  int v26; // eax
  int v27; // ebx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // r8
  int v31; // eax
  unsigned int v32; // ebx
  int v33; // [rsp+20h] [rbp-2A8h]
  int v34; // [rsp+20h] [rbp-2A8h]
  int v35; // [rsp+28h] [rbp-2A0h]
  __int64 v36; // [rsp+60h] [rbp-268h] BYREF
  struct PrintCore::HttpRestChannel *v37; // [rsp+68h] [rbp-260h] BYREF
  int v38[2]; // [rsp+70h] [rbp-258h] BYREF
  __int64 v39; // [rsp+78h] [rbp-250h]
  CloudPrint::CloudPrintHelper *v40; // [rsp+88h] [rbp-240h]
  __int64 v41; // [rsp+90h] [rbp-238h]
  __int64 v42; // [rsp+A0h] [rbp-228h] BYREF
  int v43; // [rsp+A8h] [rbp-220h]
  void *v44; // [rsp+B0h] [rbp-218h]
  _BYTE v45[32]; // [rsp+B8h] [rbp-210h] BYREF
  _BYTE v46[32]; // [rsp+D8h] [rbp-1F0h] BYREF
  _BYTE v47[32]; // [rsp+F8h] [rbp-1D0h] BYREF
  _BYTE v48[32]; // [rsp+118h] [rbp-1B0h] BYREF
  _BYTE v49[32]; // [rsp+138h] [rbp-190h] BYREF
  _BYTE v50[32]; // [rsp+158h] [rbp-170h] BYREF
  _BYTE v51[40]; // [rsp+178h] [rbp-150h] BYREF
  _OWORD v52[3]; // [rsp+1A0h] [rbp-128h] BYREF
  _BYTE v53[32]; // [rsp+1D0h] [rbp-F8h] BYREF
  __int64 v54; // [rsp+1F0h] [rbp-D8h]
  _BYTE v55[32]; // [rsp+200h] [rbp-C8h] BYREF
  _BYTE v56[32]; // [rsp+220h] [rbp-A8h] BYREF
  _BYTE v57[32]; // [rsp+240h] [rbp-88h] BYREF
  _BYTE v58[32]; // [rsp+260h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  v8 = this;
  v40 = this;
  v9 = a5;
  v41 = a5;
  LODWORD(v36) = 0;
  std::wstring::wstring(v49);
  std::wstring::wstring(v48);
  AuthorizationHeaderInternal = CloudPrint::CloudPrintHelper::GetAuthorizationHeaderInternal(
                                  (_DWORD)v8,
                                  v10,
                                  v11,
                                  a4,
                                  a6,
                                  a7,
                                  v12,
                                  (__int64)v49);
  if ( AuthorizationHeaderInternal >= 0 )
  {
    v37 = 0;
    CloudPrint::ImpersonateClientRAII::ImpersonateClientRAII(
      (CloudPrint::ImpersonateClientRAII *)v47,
      *((int (**)(void *))v8 + 2),
      *((int (**)(void *))v8 + 3),
      *((void **)v8 + 4));
    v15 = operator new(0xC8u);
    v44 = v15;
    std::wstring::wstring(v46, L"Cloud Print Helper");
    std::wstring::wstring(v51, L"application/json");
    std::wstring::wstring(v45, L"GET");
    v42 = 7730941132860000LL;
    v43 = 1800000;
    v36 = PrintCore::HttpRestChannel::HttpRestChannel(
            (__int64)v15,
            (__int64)v45,
            (__int64)v51,
            (__int64)v46,
            v33,
            v35,
            (__int64)&v42);
    std::unique_ptr<PrintCore::HttpRestChannel>::operator=<std::default_delete<PrintCore::HttpRestChannel>,0>(
      &v37,
      &v36);
    std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v36);
    std::wstring::_Tidy_deallocate(v45);
    std::wstring::_Tidy_deallocate(v51);
    std::wstring::_Tidy_deallocate(v46);
    CloudPrint::ImpersonateClientRAII::~ImpersonateClientRAII((CloudPrint::ImpersonateClientRAII *)v47);
    memset(v52, 0, sizeof(v52));
    std::wstring::wstring(v53);
    v54 = 0;
    std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(v38);
    if ( std::wstring::find(a4, L"https://login.microsoftonline.us/", 0) == -1 )
    {
LABEL_12:
      v18 = v37;
    }
    else
    {
      std::_WChar_traits<unsigned short>::length(L"https://graph.microsoft.us/v1.0");
      std::wstring::_Assign<unsigned short>(a5, v16);
      try
      {
        std::wstring::wstring(v45, L"https://login.microsoftonline.us/");
        v17 = std::operator+<unsigned short>(v46, v48, L"/.well-known/openid-configuration");
        std::wstring::append(v45, v17);
        std::wstring::_Tidy_deallocate(v46);
        v18 = v37;
        v19 = std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(v47);
        v20 = PrintCore::HttpRestChannel::SendRequestAndReceiveReply(
                (_DWORD)v18,
                (unsigned int)v45,
                v19,
                (unsigned int)v52,
                (__int64)v38);
        std::vector<unsigned char>::_Tidy(v47);
        if ( v20 < 0 )
        {
          CloudPrintHelperTelemetry::WriteDbgTraceWarning(
            "CloudPrint::CloudPrintHelper::GetMpsDiscoveryEndpointFromGraph",
            L"Failure response trying to get AAD OpenID Connect metadata document, using GCC High USGov endpoint. HttpStatus=%u",
            (unsigned __int16)v20);
          PrintCore::McpEvtSrc::ReportErrorEvent(
            L"Failure response trying to get AAD OpenID Connect metadata document, using GCC High USGov endpoint. HttpStatus=%u",
            (unsigned __int16)v20);
        }
        else
        {
          std::string::string(v51, *(_QWORD *)v38, v39);
          PrintCore::Serialization::AsciiToUnicode(v46, v51);
          std::wstring::wstring(v47);
          v21 = CloudPrint::AadParser::ParseAadDiscoveryMetadataDocumentForMsGraphHost(v46, v47);
          v22 = v21;
          if ( v21 < 0 )
          {
            CloudPrintHelperTelemetry::WriteDbgTraceWarning(
              "CloudPrint::CloudPrintHelper::GetMpsDiscoveryEndpointFromGraph",
              L"Failed to parse AAD OpenID Connect metadata document response with %#x, using GCC High USGov endpoint.",
              (unsigned int)v21);
            PrintCore::McpEvtSrc::ReportErrorEvent(
              L"Failed to parse AAD OpenID Connect metadata document response with %#x, using GCC High USGov endpoint.",
              v22);
          }
          else
          {
            v23 = std::operator+<unsigned short>(v58, L"https://", v47);
            v24 = std::operator+<unsigned short>(v57, v23, L"/v1.0");
            std::wstring::operator=(a5, v24);
            std::wstring::_Tidy_deallocate(v57);
            std::wstring::_Tidy_deallocate(v58);
          }
          std::wstring::_Tidy_deallocate(v47);
          std::wstring::_Tidy_deallocate(v46);
          std::string::_Tidy_deallocate(v51);
        }
        std::wstring::_Tidy_deallocate(v45);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x5F0,
          (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
          v25);
        v8 = v40;
        v9 = v41;
        goto LABEL_12;
      }
    }
    CloudPrint::CloudPrintHelper::RemoveTrailingForwardSlash(v9);
    std::wstring::wstring(v50, v9);
    std::wstring::append(v50, L"/print/services/f4cfee8b-4117-4773-a2f0-3807beb282b9?$expand=endpoints");
    std::wstring::wstring(v46, L"Authorization");
    PrintCore::HttpRestChannel::AddRequestHeader(v18, v46, v49);
    std::wstring::_Tidy_deallocate(v46);
    CloudPrint::CloudPrintHelper::IncrementAndAddCorrelationVectorHeader(v8, v18);
    if ( *(_QWORD *)v38 != v39 )
      v39 = *(_QWORD *)v38;
    v26 = std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(v47);
    v27 = PrintCore::HttpRestChannel::SendRequestAndReceiveReply(
            (_DWORD)v18,
            (unsigned int)v50,
            v26,
            (unsigned int)v52,
            (__int64)v38);
    std::vector<unsigned char>::_Tidy(v47);
    if ( v27 >= 0 )
    {
      std::string::string(v56, *(_QWORD *)v38, v39);
      PrintCore::Serialization::AsciiToUnicode(v55, v56);
      v31 = CloudPrint::MpsParser::ParseMpsMsGraphServicesResponseForDiscoveryEndpoint(v55, (char *)v8 + 40);
      v32 = v31;
      if ( v31 < 0 )
      {
        CloudPrintHelperTelemetry::WriteDbgTraceWarning(
          "CloudPrint::CloudPrintHelper::GetMpsDiscoveryEndpointFromGraph",
          L"Failed to parse MS Graph Services response with %#x",
          (unsigned int)v31);
        PrintCore::McpEvtSrc::ReportErrorEvent(L"Failed to parse MS Graph Services response with %#x", v32);
      }
      std::wstring::_Tidy_deallocate(v55);
      std::string::_Tidy_deallocate(v56);
      std::wstring::_Tidy_deallocate(v50);
      std::vector<unsigned char>::_Tidy(v38);
      PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v52);
      std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v37);
      std::wstring::_Tidy_deallocate(v48);
      std::wstring::_Tidy_deallocate(v49);
      return v32;
    }
    else if ( v27 == -2145844845 )
    {
      CloudPrintHelperTelemetry::WriteDbgTraceInfo(
        "CloudPrint::CloudPrintHelper::GetMpsDiscoveryEndpointFromGraph",
        L"UP is not enabled in the user's tenant.");
      PrintCore::McpEvtSrc::ReportInfoEvent(L"Universal Print is not enabled in the user's tenant.");
      std::wstring::_Tidy_deallocate(v50);
      std::vector<unsigned char>::_Tidy(v38);
      PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v52);
      std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v37);
      std::wstring::_Tidy_deallocate(v48);
      std::wstring::_Tidy_deallocate(v49);
      return 1;
    }
    else
    {
      CloudPrint::CloudPrintHelper::GetResponseTraceId(v28, v45, v52);
      v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::GetMpsDiscoveryEndpointFromGraph",
        L"Failure response trying to get MPS Discovery Endpoint from MS Graph. HttpStatus=%u, TraceId: ",
        (unsigned __int16)v27,
        v29);
      v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
      PrintCore::McpEvtSrc::ReportErrorEvent(
        L"Failure response trying to get MPS Discovery Endpoint from MS Graph. HttpStatus=%u, TraceId: %s",
        (unsigned __int16)v27,
        v30);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60A,
        (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
        (const char *)(unsigned int)v27,
        v34);
      std::wstring::_Tidy_deallocate(v45);
      std::wstring::_Tidy_deallocate(v50);
      std::vector<unsigned char>::_Tidy(v38);
      PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v52);
      std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v37);
      std::wstring::_Tidy_deallocate(v48);
      std::wstring::_Tidy_deallocate(v49);
      return (unsigned int)v27;
    }
  }
  else
  {
    std::wstring::_Tidy_deallocate(v48);
    std::wstring::_Tidy_deallocate(v49);
    return (unsigned int)AuthorizationHeaderInternal;
  }
}

```

## disassembly

```asm
0x1800157bc  mov     rax, rsp
0x1800157bf  push    rbx
0x1800157c0  push    rsi
0x1800157c1  push    rdi
0x1800157c2  push    r14
0x1800157c4  push    r15
0x1800157c6  sub     rsp, 2A0h
0x1800157cd  movaps  xmmword ptr [rax-38h], xmm6
0x1800157d1  mov     rax, cs:__security_cookie
0x1800157d8  xor     rax, rsp
0x1800157db  mov     [rsp+2C8h+var_48], rax
0x1800157e3  mov     r15, r9
0x1800157e6  mov     rsi, rcx
0x1800157e9  mov     [rsp+2C8h+var_240], rcx
0x1800157f1  mov     r14, [rsp+2C8h+arg_20]
0x1800157f9  mov     [rsp+2C8h+var_238], r14
0x180015801  mov     r9, [rsp+2C8h+arg_38]
0x180015809  mov     dword ptr [rsp+2C8h+var_268], 0
0x180015811  lea     rcx, [rsp+2C8h+var_190]
0x180015819  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001581e  nop
0x18001581f  lea     rcx, [rsp+2C8h+var_1B0]
0x180015827  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001582c  nop
0x18001582d  lea     rax, [rsp+2C8h+var_1B0]
0x180015835  mov     [rsp+2C8h+var_278], rax
0x18001583a  lea     rax, [rsp+2C8h+var_190]
0x180015842  mov     [rsp+2C8h+var_290], rax
0x180015847  mov     [rsp+2C8h+var_298], r9
0x18001584c  mov     al, [rsp+2C8h+arg_30]
0x180015853  mov     [rsp+2C8h+var_2A0], al
0x180015857  mov     al, [rsp+2C8h+arg_28]
0x18001585e  mov     byte ptr [rsp+2C8h+var_2A8], al
0x180015862  mov     r9, r15
0x180015865  mov     rcx, rsi
0x180015868  call    ?GetAuthorizationHeaderInternal@CloudPrintHelper@CloudPrint@@IEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV34@_N2PEAUHWND__@@PEAV34@444@Z; CloudPrint::CloudPrintHelper::GetAuthorizationHeaderInternal(std::wstring const &,std::wstring const &,std::wstring &,bool,bool,HWND__ *,std::wstring *,std::wstring *,std::wstring *,std::wstring *)
0x18001586d  mov     ebx, eax
0x18001586f  test    eax, eax
0x180015871  jns     short loc_180015895
0x180015873  lea     rcx, [rsp+2C8h+var_1B0]
0x18001587b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015880  nop
0x180015881  lea     rcx, [rsp+2C8h+var_190]
0x180015889  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001588e  mov     eax, ebx
0x180015890  jmp     loc_180015F31
0x180015895  mov     [rsp+2C8h+var_260], 0
0x18001589e  mov     r9, [rsi+20h]; void *
0x1800158a2  mov     r8, [rsi+18h]; int (*)(void *)
0x1800158a6  mov     rdx, [rsi+10h]; int (*)(void *)
0x1800158aa  lea     rcx, [rsp+2C8h+var_1D0]; this
0x1800158b2  call    ??0ImpersonateClientRAII@CloudPrint@@QEAA@P6AJPEAX@Z10@Z; CloudPrint::ImpersonateClientRAII::ImpersonateClientRAII(long (*)(void *),long (*)(void *),void *)
0x1800158b7  nop
0x1800158b8  mov     ecx, 0C8h; Size
0x1800158bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800158c2  mov     rbx, rax
0x1800158c5  mov     [rsp+2C8h+var_218], rax
0x1800158cd  movsd   xmm6, cs:qword_18002F010
0x1800158d5  mov     edi, cs:dword_18002F018
0x1800158db  lea     rdx, aCloudPrintHelp; "Cloud Print Helper"
0x1800158e2  lea     rcx, [rsp+2C8h+var_1F0]
0x1800158ea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800158ef  nop
0x1800158f0  mov     dword ptr [rsp+2C8h+var_268], 1
0x1800158f8  lea     rdx, aApplicationJso; "application/json"
0x1800158ff  lea     rcx, [rsp+2C8h+var_150]
0x180015907  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001590c  nop
0x18001590d  mov     dword ptr [rsp+2C8h+var_268], 3
0x180015915  lea     rdx, aGet; "GET"
0x18001591c  lea     rcx, [rsp+2C8h+var_210]
0x180015924  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015929  nop
0x18001592a  mov     dword ptr [rsp+2C8h+var_268], 7
0x180015932  movsd   [rsp+2C8h+var_228], xmm6
0x18001593b  mov     [rsp+2C8h+var_220], edi
0x180015942  lea     rax, [rsp+2C8h+var_228]
0x18001594a  mov     [rsp+2C8h+var_298], rax
0x18001594f  lea     r9, [rsp+2C8h+var_1F0]
0x180015957  lea     r8, [rsp+2C8h+var_150]
0x18001595f  lea     rdx, [rsp+2C8h+var_210]
0x180015967  mov     rcx, rbx
0x18001596a  call    ??0HttpRestChannel@PrintCore@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00_NKUHttpTimeouts@1@@Z; PrintCore::HttpRestChannel::HttpRestChannel(std::wstring const &,std::wstring const &,std::wstring const &,bool,ulong,PrintCore::HttpTimeouts)
0x18001596f  nop
0x180015970  mov     [rsp+2C8h+var_268], rax
0x180015975  lea     rdx, [rsp+2C8h+var_268]
0x18001597a  lea     rcx, [rsp+2C8h+var_260]
0x18001597f  call    ??$?4U?$default_delete@VHttpRestChannel@PrintCore@@@std@@$0A@@?$unique_ptr@VHttpRestChannel@PrintCore@@U?$default_delete@VHttpRestChannel@PrintCore@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<PrintCore::HttpRestChannel>::operator=<std::default_delete<PrintCore::HttpRestChannel>,0>(std::unique_ptr<PrintCore::HttpRestChannel> &&)
0x180015984  lea     rcx, [rsp+2C8h+var_268]
0x180015989  call    ??1?$unique_ptr@VHttpRestChannel@PrintCore@@U?$default_delete@VHttpRestChannel@PrintCore@@@std@@@std@@QEAA@XZ; std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(void)
0x18001598e  nop
0x18001598f  lea     rcx, [rsp+2C8h+var_210]
0x180015997  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001599c  nop
0x18001599d  lea     rcx, [rsp+2C8h+var_150]
0x1800159a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800159aa  nop
0x1800159ab  lea     rcx, [rsp+2C8h+var_1F0]
0x1800159b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800159b8  nop
0x1800159b9  lea     rcx, [rsp+2C8h+var_1D0]; this
0x1800159c1  call    ??1ImpersonateClientRAII@CloudPrint@@QEAA@XZ; CloudPrint::ImpersonateClientRAII::~ImpersonateClientRAII(void)
0x1800159c6  xorps   xmm1, xmm1
0x1800159c9  movdqa  [rsp+2C8h+var_128], xmm1
0x1800159d2  movdqa  [rsp+2C8h+var_118], xmm1
0x1800159db  movdqa  [rsp+2C8h+var_108], xmm1
0x1800159e4  lea     rcx, [rsp+2C8h+var_F8]
0x1800159ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800159f1  nop
0x1800159f2  xor     eax, eax
0x1800159f4  mov     [rsp+2C8h+var_D8], rax
0x1800159fc  lea     rcx, [rsp+2C8h+var_258]
0x180015a01  call    ??0?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@QEAA@XZ; std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(void)
0x180015a06  nop
0x180015a07  xor     r8d, r8d
0x180015a0a  lea     rdx, aHttpsLoginMicr; "https://login.microsoftonline.us/"
0x180015a11  mov     rcx, r15
0x180015a14  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180015a19  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015a1d  jz      loc_180015C28
0x180015a23  lea     rcx, aHttpsGraphMicr; "https://graph.microsoft.us/v1.0"
0x180015a2a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180015a2f  mov     r8, rax
0x180015a32  mov     rdx, rcx
0x180015a35  mov     rcx, r14
0x180015a38  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180015a3d  nop
0x180015a3e  lea     rdx, aHttpsLoginMicr; "https://login.microsoftonline.us/"
0x180015a45  lea     rcx, [rsp+2C8h+var_210]
0x180015a4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015a52  nop
0x180015a53  lea     r8, aWellKnownOpeni; "/.well-known/openid-configuration"
0x180015a5a  lea     rdx, [rsp+2C8h+var_1B0]
0x180015a62  lea     rcx, [rsp+2C8h+var_1F0]
0x180015a6a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180015a6f  nop
0x180015a70  mov     rdx, rax
0x180015a73  lea     rcx, [rsp+2C8h+var_210]
0x180015a7b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180015a80  nop
0x180015a81  lea     rcx, [rsp+2C8h+var_1F0]
0x180015a89  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015a8e  mov     rbx, [rsp+2C8h+var_260]
0x180015a93  lea     rcx, [rsp+2C8h+var_1D0]
0x180015a9b  call    ??0?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@QEAA@XZ; std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(void)
0x180015aa0  nop
0x180015aa1  lea     rcx, [rsp+2C8h+var_258]
0x180015aa6  mov     qword ptr [rsp+2C8h+var_2A8], rcx
0x180015aab  lea     r9, [rsp+2C8h+var_128]
0x180015ab3  mov     r8, rax
0x180015ab6  lea     rdx, [rsp+2C8h+var_210]
0x180015abe  mov     rcx, rbx
0x180015ac1  call    ?SendRequestAndReceiveReply@HttpRestChannel@PrintCore@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@AEAUHttpContext@2@AEAV54@_N@Z; PrintCore::HttpRestChannel::SendRequestAndReceiveReply(std::wstring const &,std::vector<uchar> const &,PrintCore::HttpContext &,std::vector<uchar> &,bool)
0x180015ac6  mov     edi, eax
0x180015ac8  lea     rcx, [rsp+2C8h+var_1D0]
0x180015ad0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180015ad5  test    edi, edi
0x180015ad7  js      loc_180015BE0
0x180015add  mov     r8, [rsp+2C8h+var_250]
0x180015ae2  mov     rdx, qword ptr [rsp+2C8h+var_258]
0x180015ae7  lea     rcx, [rsp+2C8h+var_150]
0x180015aef  call    ??$?0V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@0AEBV?$allocator@D@1@@Z; std::string::string(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::allocator<char> const &)
0x180015af4  nop
0x180015af5  lea     rdx, [rsp+2C8h+var_150]
0x180015afd  lea     rcx, [rsp+2C8h+var_1F0]
0x180015b05  call    ?AsciiToUnicode@Serialization@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; PrintCore::Serialization::AsciiToUnicode(std::string const &)
0x180015b0a  nop
0x180015b0b  lea     rcx, [rsp+2C8h+var_1D0]
0x180015b13  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015b18  nop
0x180015b19  lea     rdx, [rsp+2C8h+var_1D0]
0x180015b21  lea     rcx, [rsp+2C8h+var_1F0]
0x180015b29  call    ?ParseAadDiscoveryMetadataDocumentForMsGraphHost@AadParser@CloudPrint@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV34@@Z; CloudPrint::AadParser::ParseAadDiscoveryMetadataDocumentForMsGraphHost(std::wstring const &,std::wstring *)
0x180015b2e  mov     edi, eax
0x180015b30  test    eax, eax
0x180015b32  js      short loc_180015B90
0x180015b34  lea     r8, [rsp+2C8h+var_1D0]
0x180015b3c  lea     rdx, aHttps; "https://"
0x180015b43  lea     rcx, [rsp+2C8h+var_68]
0x180015b4b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x180015b50  nop
0x180015b51  lea     r8, aV10; "/v1.0"
0x180015b58  mov     rdx, rax
0x180015b5b  lea     rcx, [rsp+2C8h+var_88]
0x180015b63  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180015b68  mov     rdx, rax
0x180015b6b  mov     rcx, r14
0x180015b6e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180015b73  lea     rcx, [rsp+2C8h+var_88]
0x180015b7b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015b80  nop
0x180015b81  lea     rcx, [rsp+2C8h+var_68]
0x180015b89  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015b8e  jmp     short loc_180015BB5
0x180015b90  mov     r8d, edi
0x180015b93  lea     rdx, aFailedToParseA; "Failed to parse AAD OpenID Connect meta"...
0x180015b9a  lea     rcx, aCloudprintClou_25; "CloudPrint::CloudPrintHelper::GetMpsDis"...
0x180015ba1  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180015ba6  mov     edx, edi
0x180015ba8  lea     rcx, aFailedToParseA; "Failed to parse AAD OpenID Connect meta"...
0x180015baf  call    ?ReportErrorEvent@McpEvtSrc@PrintCore@@SAXPEBGZZ; PrintCore::McpEvtSrc::ReportErrorEvent(ushort const *,...)
0x180015bb4  nop
0x180015bb5  lea     rcx, [rsp+2C8h+var_1D0]
0x180015bbd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015bc2  nop
0x180015bc3  lea     rcx, [rsp+2C8h+var_1F0]
0x180015bcb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015bd0  nop
0x180015bd1  lea     rcx, [rsp+2C8h+var_150]
0x180015bd9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180015bde  jmp     short loc_180015C08
0x180015be0  movzx   edi, di
0x180015be3  mov     r8d, edi
0x180015be6  lea     rdx, aFailureRespons; "Failure response trying to get AAD Open"...
0x180015bed  lea     rcx, aCloudprintClou_25; "CloudPrint::CloudPrintHelper::GetMpsDis"...
0x180015bf4  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180015bf9  mov     edx, edi
0x180015bfb  lea     rcx, aFailureRespons; "Failure response trying to get AAD Open"...
0x180015c02  call    ?ReportErrorEvent@McpEvtSrc@PrintCore@@SAXPEBGZZ; PrintCore::McpEvtSrc::ReportErrorEvent(ushort const *,...)
0x180015c07  nop
0x180015c08  lea     rcx, [rsp+2C8h+var_210]
0x180015c10  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015c15  nop
0x180015c16  jmp     short loc_180015C2D
0x180015c18  mov     rsi, [rsp+2C8h+var_240]
0x180015c20  mov     r14, [rsp+2C8h+var_238]
0x180015c28  mov     rbx, [rsp+2C8h+var_260]
0x180015c2d  mov     rcx, r14
0x180015c30  call    ?RemoveTrailingForwardSlash@CloudPrintHelper@CloudPrint@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudPrint::CloudPrintHelper::RemoveTrailingForwardSlash(std::wstring &)
0x180015c35  mov     rdx, r14
0x180015c38  lea     rcx, [rsp+2C8h+var_170]
0x180015c40  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180015c45  nop
0x180015c46  lea     rdx, aPrintServicesF; "/print/services/f4cfee8b-4117-4773-a2f0"...
0x180015c4d  lea     rcx, [rsp+2C8h+var_170]
0x180015c55  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180015c5a  lea     rdx, aAuthorization; "Authorization"
0x180015c61  lea     rcx, [rsp+2C8h+var_1F0]
0x180015c69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015c6e  nop
0x180015c6f  lea     r8, [rsp+2C8h+var_190]
0x180015c77  lea     rdx, [rsp+2C8h+var_1F0]
0x180015c7f  mov     rcx, rbx
0x180015c82  call    ?AddRequestHeader@HttpRestChannel@PrintCore@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PrintCore::HttpRestChannel::AddRequestHeader(std::wstring const &,std::wstring const &)
0x180015c87  nop
0x180015c88  lea     rcx, [rsp+2C8h+var_1F0]
0x180015c90  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015c95  mov     rdx, rbx; struct PrintCore::HttpRestChannel *
0x180015c98  mov     rcx, rsi; this
0x180015c9b  call    ?IncrementAndAddCorrelationVectorHeader@CloudPrintHelper@CloudPrint@@IEAAXPEAVHttpRestChannel@PrintCore@@@Z; CloudPrint::CloudPrintHelper::IncrementAndAddCorrelationVectorHeader(PrintCore::HttpRestChannel *)
0x180015ca0  mov     rax, qword ptr [rsp+2C8h+var_258]
0x180015ca5  cmp     rax, [rsp+2C8h+var_250]
0x180015caa  jz      short loc_180015CB1
0x180015cac  mov     [rsp+2C8h+var_250], rax
0x180015cb1  lea     rcx, [rsp+2C8h+var_1D0]
0x180015cb9  call    ??0?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@QEAA@XZ; std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(void)
0x180015cbe  nop
0x180015cbf  lea     rcx, [rsp+2C8h+var_258]
0x180015cc4  mov     qword ptr [rsp+2C8h+var_2A8], rcx; int
0x180015cc9  lea     r9, [rsp+2C8h+var_128]
0x180015cd1  mov     r8, rax
0x180015cd4  lea     rdx, [rsp+2C8h+var_170]
0x180015cdc  mov     rcx, rbx
0x180015cdf  call    ?SendRequestAndReceiveReply@HttpRestChannel@PrintCore@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@AEAUHttpContext@2@AEAV54@_N@Z; PrintCore::HttpRestChannel::SendRequestAndReceiveReply(std::wstring const &,std::vector<uchar> const &,PrintCore::HttpContext &,std::vector<uchar> &,bool)
0x180015ce4  mov     ebx, eax
0x180015ce6  lea     rcx, [rsp+2C8h+var_1D0]
0x180015cee  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180015cf3  test    ebx, ebx
0x180015cf5  jns     loc_180015E56
0x180015cfb  cmp     ebx, 80190193h
0x180015d01  jnz     short loc_180015D7A
0x180015d03  lea     rdx, aUpIsNotEnabled; "UP is not enabled in the user's tenant."
0x180015d0a  lea     rcx, aCloudprintClou_25; "CloudPrint::CloudPrintHelper::GetMpsDis"...
0x180015d11  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180015d16  lea     rcx, aUniversalPrint_0; "Universal Print is not enabled in the u"...
0x180015d1d  call    ?ReportInfoEvent@McpEvtSrc@PrintCore@@SAXPEBGZZ; PrintCore::McpEvtSrc::ReportInfoEvent(ushort const *,...)
0x180015d22  nop
0x180015d23  lea     rcx, [rsp+2C8h+var_170]
0x180015d2b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015d30  nop
0x180015d31  lea     rcx, [rsp+2C8h+var_258]
0x180015d36  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180015d3b  nop
0x180015d3c  lea     rcx, [rsp+2C8h+var_128]; this
0x180015d44  call    ??1HttpContext@PrintCore@@QEAA@XZ; PrintCore::HttpContext::~HttpContext(void)
0x180015d49  nop
0x180015d4a  lea     rcx, [rsp+2C8h+var_260]
0x180015d4f  call    ??1?$unique_ptr@VHttpRestChannel@PrintCore@@U?$default_delete@VHttpRestChannel@PrintCore@@@std@@@std@@QEAA@XZ; std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(void)
0x180015d54  nop
0x180015d55  lea     rcx, [rsp+2C8h+var_1B0]
0x180015d5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015d62  nop
0x180015d63  lea     rcx, [rsp+2C8h+var_190]
0x180015d6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015d70  mov     eax, 1
0x180015d75  jmp     loc_180015F31
0x180015d7a  movzx   edi, bx
0x180015d7d  lea     r8, [rsp+2C8h+var_128]
0x180015d85  lea     rdx, [rsp+2C8h+var_210]
0x180015d8d  call    ?GetResponseTraceId@CloudPrintHelper@CloudPrint@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUHttpContext@PrintCore@@PEAVHttpRestChannel@6@@Z; CloudPrint::CloudPrintHelper::GetResponseTraceId(PrintCore::HttpContext const &,PrintCore::HttpRestChannel *)
  ... truncated ...
```
