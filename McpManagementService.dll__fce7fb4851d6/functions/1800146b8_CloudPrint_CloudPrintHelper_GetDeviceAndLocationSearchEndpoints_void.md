# CloudPrint::CloudPrintHelper::GetDeviceAndLocationSearchEndpoints(void)

- ea: `0x1800146b8`
- end: `0x180014c4b`
- name: `?GetDeviceAndLocationSearchEndpoints@CloudPrintHelper@CloudPrint@@IEAAJXZ`
- size: `1427`
- prototype: `__int64 __fastcall(CloudPrint::CloudPrintHelper *__hidden this)`
- caller_count: `2`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180016184`
- `0x18001b128`

## callees

- `0x180003a60`
- `0x180003aa0`
- `0x180006b70`
- `0x18000c4cc`
- `0x18000e164`
- `0x18000e208`
- `0x18000e2dc`
- `0x18000f804`
- `0x18000f848`
- `0x180011d98`
- `0x180011de0`
- `0x180011f68`
- `0x1800120a0`
- `0x18001227c`
- `0x180012668`
- `0x1800129c4`
- `0x180012a44`
- `0x180012e90`
- `0x180012f08`
- `0x1800138ec`
- `0x1800146b8`
- `0x180016920`
- `0x180018668`
- `0x1800195fc`
- `0x18001aaf4`
- `0x18001b8c4`
- `0x18001c0a8`
- `0x18001c298`
- `0x18001db04`
- `0x18001db44`
- `0x1800203b0`

## string_xrefs

- `0x180014783`: `application/json`
- `0x1800148a5`: `/services`
- `0x180014b04`: `Failed to parse Mopria Cloud Discovery /Services response with %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CloudPrint::CloudPrintHelper::GetDeviceAndLocationSearchEndpoints(
        CloudPrint::CloudPrintHelper *this)
{
  __int64 v2; // rdx
  int AuthorizationHeaderByEndpointSilent; // ebx
  struct PrintCore::HttpRestChannel *v5; // rbx
  __int64 v6; // rax
  int v7; // eax
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // r8d
  __int64 v12; // r8
  __int64 v13; // rdx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rax
  int v17; // [rsp+20h] [rbp-218h]
  int v18; // [rsp+20h] [rbp-218h]
  int v19; // [rsp+20h] [rbp-218h]
  int v20; // [rsp+28h] [rbp-210h]
  __int64 v21; // [rsp+40h] [rbp-1F8h] BYREF
  struct PrintCore::HttpRestChannel *v22; // [rsp+48h] [rbp-1F0h] BYREF
  int v23[2]; // [rsp+50h] [rbp-1E8h] BYREF
  __int64 v24; // [rsp+58h] [rbp-1E0h]
  __int64 v25; // [rsp+70h] [rbp-1C8h] BYREF
  int v26; // [rsp+78h] [rbp-1C0h]
  void *v27; // [rsp+80h] [rbp-1B8h]
  _BYTE v28[32]; // [rsp+88h] [rbp-1B0h] BYREF
  _BYTE v29[32]; // [rsp+A8h] [rbp-190h] BYREF
  _BYTE v30[32]; // [rsp+C8h] [rbp-170h] BYREF
  _BYTE v31[32]; // [rsp+E8h] [rbp-150h] BYREF
  _BYTE v32[40]; // [rsp+108h] [rbp-130h] BYREF
  _OWORD v33[3]; // [rsp+130h] [rbp-108h] BYREF
  _BYTE v34[32]; // [rsp+160h] [rbp-D8h] BYREF
  __int64 v35; // [rsp+180h] [rbp-B8h]
  _BYTE v36[32]; // [rsp+190h] [rbp-A8h] BYREF
  _BYTE v37[32]; // [rsp+1B0h] [rbp-88h] BYREF
  _BYTE v38[32]; // [rsp+1D0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  LODWORD(v21) = 0;
  std::wstring::wstring(v31);
  AuthorizationHeaderByEndpointSilent = CloudPrint::CloudPrintHelper::GetAuthorizationHeaderByEndpointSilent(
                                          this,
                                          v2,
                                          v31);
  if ( AuthorizationHeaderByEndpointSilent >= 0 )
  {
    v22 = 0;
    CloudPrint::ImpersonateClientRAII::ImpersonateClientRAII(
      (CloudPrint::ImpersonateClientRAII *)v29,
      *((int (**)(void *))this + 2),
      *((int (**)(void *))this + 3),
      *((void **)this + 4));
    v27 = operator new(0xC8u);
    std::wstring::wstring(v32, L"Cloud Print Helper");
    std::wstring::wstring(v38, L"application/json");
    std::wstring::wstring(v37, L"GET");
    v25 = 7730941132860000LL;
    v26 = 1800000;
    v21 = PrintCore::HttpRestChannel::HttpRestChannel(
            (__int64)v27,
            (__int64)v37,
            (__int64)v38,
            (__int64)v32,
            v17,
            v20,
            (__int64)&v25);
    std::unique_ptr<PrintCore::HttpRestChannel>::operator=<std::default_delete<PrintCore::HttpRestChannel>,0>(
      &v22,
      &v21);
    std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v21);
    std::wstring::_Tidy_deallocate(v37);
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v32);
    CloudPrint::ImpersonateClientRAII::~ImpersonateClientRAII((CloudPrint::ImpersonateClientRAII *)v29);
    v5 = v22;
    std::wstring::wstring(v32, L"Authorization");
    PrintCore::HttpRestChannel::AddRequestHeader(v5, v32, v31);
    std::wstring::_Tidy_deallocate(v32);
    CloudPrint::CloudPrintHelper::IncrementAndAddCorrelationVectorHeader(this, v5);
    std::wstring::wstring(v28, (char *)this + 40);
    std::wstring::append(v28, L"/services");
    if ( CloudPrint::CloudPrintHelper::IsMps(this) )
    {
      std::wstring::append(v28, L"?max_ver_supported=");
      std::wstring::append(v28, L"mod1.0");
    }
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    CloudPrintHelperTelemetry::WriteDbgTraceInfo(
      "CloudPrint::CloudPrintHelper::GetDeviceAndLocationSearchEndpoints",
      L"Getting Device And Location Search Endpoints. RequestUrl: %s",
      v6);
    memset(v33, 0, sizeof(v33));
    std::wstring::wstring(v34);
    v35 = 0;
    std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(v23);
    v7 = std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(v29);
    v8 = PrintCore::HttpRestChannel::SendRequestAndReceiveReply(
           (_DWORD)v5,
           (unsigned int)v28,
           v7,
           (unsigned int)v33,
           (__int64)v23);
    std::vector<unsigned char>::_Tidy(v29);
    std::string::string(v36, *(_QWORD *)v23, v24);
    PrintCore::Serialization::AsciiToUnicode(v30, v36);
    if ( v8 >= 0 )
    {
      LOBYTE(v13) = CloudPrint::CloudPrintHelper::IsMps(this);
      v14 = CloudPrint::MopriaJsonParser::ParseHttpResponseForLocationAndDeviceEndPoints(
              v30,
              v13,
              (char *)this + 104,
              (char *)this + 72);
      v15 = v14;
      if ( v14 >= 0 )
      {
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 104);
        v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 72);
        CloudPrintHelperTelemetry::WriteDbgTraceInfo(
          "CloudPrint::CloudPrintHelper::GetDeviceAndLocationSearchEndpoints",
          L"DiscoveryDevicesSearchEndpoint: %s, DiscoveryLocationsSearchEndpoint: %s",
          v16);
        std::wstring::_Tidy_deallocate(v30);
        std::string::_Tidy_deallocate(v36);
        std::vector<unsigned char>::_Tidy(v23);
        PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v33);
        std::wstring::_Tidy_deallocate(v28);
        std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v22);
        std::wstring::_Tidy_deallocate(v31);
        return 0;
      }
      else
      {
        CloudPrintHelperTelemetry::WriteDbgTraceWarning(
          "CloudPrint::CloudPrintHelper::GetDeviceAndLocationSearchEndpoints",
          L"Failed to parse Mopria Cloud Discovery /Services response with %#x",
          (unsigned int)v14);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x64A,
          (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
          (const char *)v15,
          v18);
        std::wstring::_Tidy_deallocate(v30);
        std::string::_Tidy_deallocate(v36);
        std::vector<unsigned char>::_Tidy(v23);
        PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v33);
        std::wstring::_Tidy_deallocate(v28);
        std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v22);
        std::wstring::_Tidy_deallocate(v31);
        return v15;
      }
    }
    else
    {
      CloudPrint::CloudPrintHelper::GetResponseTraceId(v9, v29, v33);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
      v19 = v11;
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::GetDeviceAndLocationSearchEndpoints",
        L"Failure response trying to get Device and Location Search Endpoints. HttpStatus=%u, Response: %s, TraceId: %s",
        (unsigned __int16)v8,
        v10);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
      PrintCore::McpEvtSrc::ReportErrorEvent(
        L"Failure response trying to get Device and Location Search Endpoints. HttpStatus=%u, Response: %s, TraceId: %s",
        (unsigned __int16)v8,
        v12);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x643,
        (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
        (const char *)(unsigned int)v8,
        v19);
      std::wstring::_Tidy_deallocate(v29);
      std::wstring::_Tidy_deallocate(v30);
      std::string::_Tidy_deallocate(v36);
      std::vector<unsigned char>::_Tidy(v23);
      PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v33);
      std::wstring::_Tidy_deallocate(v28);
      std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v22);
      std::wstring::_Tidy_deallocate(v31);
      return (unsigned int)v8;
    }
  }
  else
  {
    std::wstring::_Tidy_deallocate(v31);
    return (unsigned int)AuthorizationHeaderByEndpointSilent;
  }
}

```

## disassembly

```asm
0x1800146b8  mov     rax, rsp
0x1800146bb  push    rbx
0x1800146bc  push    rsi
0x1800146bd  push    rdi
0x1800146be  push    r14
0x1800146c0  sub     rsp, 218h
0x1800146c7  movaps  xmmword ptr [rax-38h], xmm6
0x1800146cb  mov     rax, cs:__security_cookie
0x1800146d2  xor     rax, rsp
0x1800146d5  mov     [rsp+238h+var_48], rax
0x1800146dd  mov     rdi, rcx
0x1800146e0  mov     dword ptr [rsp+238h+var_1F8], 0
0x1800146e8  lea     rcx, [rsp+238h+var_150]
0x1800146f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800146f5  nop
0x1800146f6  lea     r8, [rsp+238h+var_150]
0x1800146fe  mov     rcx, rdi
0x180014701  call    ?GetAuthorizationHeaderByEndpointSilent@CloudPrintHelper@CloudPrint@@QEBAJW4CloudPrintEndpoint@2@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; CloudPrint::CloudPrintHelper::GetAuthorizationHeaderByEndpointSilent(CloudPrint::CloudPrintEndpoint,std::wstring *,std::wstring *,std::wstring *,std::wstring *)
0x180014706  mov     ebx, eax
0x180014708  test    eax, eax
0x18001470a  jns     short loc_180014720
0x18001470c  lea     rcx, [rsp+238h+var_150]
0x180014714  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014719  mov     eax, ebx
0x18001471b  jmp     loc_180014C25
0x180014720  mov     [rsp+238h+var_1F0], 0
0x180014729  mov     r9, [rdi+20h]; void *
0x18001472d  mov     r8, [rdi+18h]; int (*)(void *)
0x180014731  mov     rdx, [rdi+10h]; int (*)(void *)
0x180014735  lea     rcx, [rsp+238h+var_190]; this
0x18001473d  call    ??0ImpersonateClientRAII@CloudPrint@@QEAA@P6AJPEAX@Z10@Z; CloudPrint::ImpersonateClientRAII::ImpersonateClientRAII(long (*)(void *),long (*)(void *),void *)
0x180014742  nop
0x180014743  mov     ecx, 0C8h; Size
0x180014748  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001474d  mov     rbx, rax
0x180014750  mov     [rsp+238h+var_1B8], rax
0x180014758  movsd   xmm6, cs:qword_18002F010
0x180014760  mov     esi, cs:dword_18002F018
0x180014766  lea     rdx, aCloudPrintHelp; "Cloud Print Helper"
0x18001476d  lea     rcx, [rsp+238h+var_130]
0x180014775  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001477a  nop
0x18001477b  mov     dword ptr [rsp+238h+var_1F8], 1
0x180014783  lea     rdx, aApplicationJso; "application/json"
0x18001478a  lea     rcx, [rsp+238h+var_68]
0x180014792  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180014797  nop
0x180014798  mov     dword ptr [rsp+238h+var_1F8], 3
0x1800147a0  lea     rdx, aGet; "GET"
0x1800147a7  lea     rcx, [rsp+238h+var_88]
0x1800147af  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800147b4  nop
0x1800147b5  mov     dword ptr [rsp+238h+var_1F8], 7
0x1800147bd  movsd   [rsp+238h+var_1C8], xmm6
0x1800147c3  mov     [rsp+238h+var_1C0], esi
0x1800147c7  lea     rax, [rsp+238h+var_1C8]
0x1800147cc  mov     [rsp+238h+var_208], rax
0x1800147d1  lea     r9, [rsp+238h+var_130]
0x1800147d9  lea     r8, [rsp+238h+var_68]
0x1800147e1  lea     rdx, [rsp+238h+var_88]
0x1800147e9  mov     rcx, rbx
0x1800147ec  call    ??0HttpRestChannel@PrintCore@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00_NKUHttpTimeouts@1@@Z; PrintCore::HttpRestChannel::HttpRestChannel(std::wstring const &,std::wstring const &,std::wstring const &,bool,ulong,PrintCore::HttpTimeouts)
0x1800147f1  nop
0x1800147f2  mov     [rsp+238h+var_1F8], rax
0x1800147f7  lea     rdx, [rsp+238h+var_1F8]
0x1800147fc  lea     rcx, [rsp+238h+var_1F0]
0x180014801  call    ??$?4U?$default_delete@VHttpRestChannel@PrintCore@@@std@@$0A@@?$unique_ptr@VHttpRestChannel@PrintCore@@U?$default_delete@VHttpRestChannel@PrintCore@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<PrintCore::HttpRestChannel>::operator=<std::default_delete<PrintCore::HttpRestChannel>,0>(std::unique_ptr<PrintCore::HttpRestChannel> &&)
0x180014806  lea     rcx, [rsp+238h+var_1F8]
0x18001480b  call    ??1?$unique_ptr@VHttpRestChannel@PrintCore@@U?$default_delete@VHttpRestChannel@PrintCore@@@std@@@std@@QEAA@XZ; std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(void)
0x180014810  nop
0x180014811  lea     rcx, [rsp+238h+var_88]
0x180014819  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001481e  nop
0x18001481f  lea     rcx, [rsp+238h+var_68]
0x180014827  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001482c  nop
0x18001482d  lea     rcx, [rsp+238h+var_130]
0x180014835  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001483a  nop
0x18001483b  lea     rcx, [rsp+238h+var_190]; this
0x180014843  call    ??1ImpersonateClientRAII@CloudPrint@@QEAA@XZ; CloudPrint::ImpersonateClientRAII::~ImpersonateClientRAII(void)
0x180014848  mov     rbx, [rsp+238h+var_1F0]
0x18001484d  lea     rdx, aAuthorization; "Authorization"
0x180014854  lea     rcx, [rsp+238h+var_130]
0x18001485c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180014861  nop
0x180014862  lea     r8, [rsp+238h+var_150]
0x18001486a  lea     rdx, [rsp+238h+var_130]
0x180014872  mov     rcx, rbx
0x180014875  call    ?AddRequestHeader@HttpRestChannel@PrintCore@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PrintCore::HttpRestChannel::AddRequestHeader(std::wstring const &,std::wstring const &)
0x18001487a  nop
0x18001487b  lea     rcx, [rsp+238h+var_130]
0x180014883  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014888  mov     rdx, rbx; struct PrintCore::HttpRestChannel *
0x18001488b  mov     rcx, rdi; this
0x18001488e  call    ?IncrementAndAddCorrelationVectorHeader@CloudPrintHelper@CloudPrint@@IEAAXPEAVHttpRestChannel@PrintCore@@@Z; CloudPrint::CloudPrintHelper::IncrementAndAddCorrelationVectorHeader(PrintCore::HttpRestChannel *)
0x180014893  lea     rdx, [rdi+28h]
0x180014897  lea     rcx, [rsp+238h+var_1B0]
0x18001489f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800148a4  nop
0x1800148a5  lea     rdx, aServices; "/services"
0x1800148ac  lea     rcx, [rsp+238h+var_1B0]
0x1800148b4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800148b9  mov     rcx, rdi; this
0x1800148bc  call    ?IsMps@CloudPrintHelper@CloudPrint@@QEBA_NXZ; CloudPrint::CloudPrintHelper::IsMps(void)
0x1800148c1  test    al, al
0x1800148c3  jz      short loc_1800148ED
0x1800148c5  lea     rdx, aMaxVerSupporte; "?max_ver_supported="
0x1800148cc  lea     rcx, [rsp+238h+var_1B0]
0x1800148d4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800148d9  lea     rdx, aMod10; "mod1.0"
0x1800148e0  lea     rcx, [rsp+238h+var_1B0]
0x1800148e8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800148ed  lea     rcx, [rsp+238h+var_1B0]
0x1800148f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800148fa  mov     r8, rax
0x1800148fd  lea     rdx, aGettingDeviceA; "Getting Device And Location Search Endp"...
0x180014904  lea     rcx, aCloudprintClou_1; "CloudPrint::CloudPrintHelper::GetDevice"...
0x18001490b  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014910  xorps   xmm1, xmm1
0x180014913  movdqa  [rsp+238h+var_108], xmm1
0x18001491c  movdqa  [rsp+238h+var_F8], xmm1
0x180014925  movdqa  [rsp+238h+var_E8], xmm1
0x18001492e  lea     rcx, [rsp+238h+var_D8]
0x180014936  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001493b  nop
0x18001493c  xor     eax, eax
0x18001493e  mov     [rsp+238h+var_B8], rax
0x180014946  lea     rcx, [rsp+238h+var_1E8]
0x18001494b  call    ??0?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@QEAA@XZ; std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(void)
0x180014950  nop
0x180014951  lea     rcx, [rsp+238h+var_190]
0x180014959  call    ??0?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@QEAA@XZ; std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(void)
0x18001495e  nop
0x18001495f  lea     rcx, [rsp+238h+var_1E8]
0x180014964  mov     qword ptr [rsp+238h+var_218], rcx; int
0x180014969  lea     r9, [rsp+238h+var_108]
0x180014971  mov     r8, rax
0x180014974  lea     rdx, [rsp+238h+var_1B0]
0x18001497c  mov     rcx, rbx
0x18001497f  call    ?SendRequestAndReceiveReply@HttpRestChannel@PrintCore@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@AEAUHttpContext@2@AEAV54@_N@Z; PrintCore::HttpRestChannel::SendRequestAndReceiveReply(std::wstring const &,std::vector<uchar> const &,PrintCore::HttpContext &,std::vector<uchar> &,bool)
0x180014984  mov     ebx, eax
0x180014986  lea     rcx, [rsp+238h+var_190]
0x18001498e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180014993  mov     r8, [rsp+238h+var_1E0]
0x180014998  mov     rdx, qword ptr [rsp+238h+var_1E8]
0x18001499d  lea     rcx, [rsp+238h+var_A8]
0x1800149a5  call    ??$?0V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@0AEBV?$allocator@D@1@@Z; std::string::string(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::allocator<char> const &)
0x1800149aa  nop
0x1800149ab  lea     rdx, [rsp+238h+var_A8]
0x1800149b3  lea     rcx, [rsp+238h+var_170]
0x1800149bb  call    ?AsciiToUnicode@Serialization@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; PrintCore::Serialization::AsciiToUnicode(std::string const &)
0x1800149c0  nop
0x1800149c1  test    ebx, ebx
0x1800149c3  jns     loc_180014AD8
0x1800149c9  movzx   edi, bx
0x1800149cc  lea     r8, [rsp+238h+var_108]
0x1800149d4  lea     rdx, [rsp+238h+var_190]
0x1800149dc  call    ?GetResponseTraceId@CloudPrintHelper@CloudPrint@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUHttpContext@PrintCore@@PEAVHttpRestChannel@6@@Z; CloudPrint::CloudPrintHelper::GetResponseTraceId(PrintCore::HttpContext const &,PrintCore::HttpRestChannel *)
0x1800149e1  nop
0x1800149e2  lea     rcx, [rsp+238h+var_190]
0x1800149ea  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800149ef  mov     r8, rax
0x1800149f2  lea     rcx, [rsp+238h+var_170]
0x1800149fa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800149ff  mov     r9, rax
0x180014a02  mov     qword ptr [rsp+238h+var_218], r8; int
0x180014a07  mov     r8d, edi
0x180014a0a  lea     rdx, aFailureRespons_2; "Failure response trying to get Device a"...
0x180014a11  lea     rcx, aCloudprintClou_1; "CloudPrint::CloudPrintHelper::GetDevice"...
0x180014a18  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180014a1d  lea     rcx, [rsp+238h+var_190]
0x180014a25  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014a2a  mov     r9, rax
0x180014a2d  lea     rcx, [rsp+238h+var_170]
0x180014a35  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014a3a  mov     r8, rax
0x180014a3d  mov     edx, edi
0x180014a3f  lea     rcx, aFailureRespons_2; "Failure response trying to get Device a"...
0x180014a46  call    ?ReportErrorEvent@McpEvtSrc@PrintCore@@SAXPEBGZZ; PrintCore::McpEvtSrc::ReportErrorEvent(ushort const *,...)
0x180014a4b  mov     rcx, [rsp+238h]; this
0x180014a53  mov     r9d, ebx; char *
0x180014a56  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180014a5d  mov     edx, 643h; void *
0x180014a62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a67  nop
0x180014a68  lea     rcx, [rsp+238h+var_190]
0x180014a70  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014a75  nop
0x180014a76  lea     rcx, [rsp+238h+var_170]
0x180014a7e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014a83  nop
0x180014a84  lea     rcx, [rsp+238h+var_A8]
0x180014a8c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014a91  nop
0x180014a92  lea     rcx, [rsp+238h+var_1E8]
0x180014a97  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180014a9c  nop
0x180014a9d  lea     rcx, [rsp+238h+var_108]; this
0x180014aa5  call    ??1HttpContext@PrintCore@@QEAA@XZ; PrintCore::HttpContext::~HttpContext(void)
0x180014aaa  nop
0x180014aab  lea     rcx, [rsp+238h+var_1B0]
0x180014ab3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014ab8  nop
0x180014ab9  lea     rcx, [rsp+238h+var_1F0]
0x180014abe  call    ??1?$unique_ptr@VHttpRestChannel@PrintCore@@U?$default_delete@VHttpRestChannel@PrintCore@@@std@@@std@@QEAA@XZ; std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(void)
0x180014ac3  nop
0x180014ac4  lea     rcx, [rsp+238h+var_150]
0x180014acc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014ad1  mov     eax, ebx
0x180014ad3  jmp     loc_180014C25
0x180014ad8  mov     rcx, rdi; this
0x180014adb  call    ?IsMps@CloudPrintHelper@CloudPrint@@QEBA_NXZ; CloudPrint::CloudPrintHelper::IsMps(void)
0x180014ae0  mov     dl, al
0x180014ae2  lea     r9, [rdi+48h]
0x180014ae6  lea     r8, [rdi+68h]
0x180014aea  lea     rcx, [rsp+238h+var_170]
0x180014af2  call    ?ParseHttpResponseForLocationAndDeviceEndPoints@MopriaJsonParser@CloudPrint@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NPEAV34@2@Z; CloudPrint::MopriaJsonParser::ParseHttpResponseForLocationAndDeviceEndPoints(std::wstring const &,bool,std::wstring *,std::wstring *)
0x180014af7  mov     ebx, eax
0x180014af9  test    eax, eax
0x180014afb  jns     loc_180014B96
0x180014b01  mov     r8d, eax
0x180014b04  lea     rdx, aFailedToParseM_1; "Failed to parse Mopria Cloud Discovery "...
0x180014b0b  lea     rcx, aCloudprintClou_1; "CloudPrint::CloudPrintHelper::GetDevice"...
0x180014b12  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180014b17  mov     rcx, [rsp+238h]; this
0x180014b1f  mov     r9d, ebx; char *
0x180014b22  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180014b29  mov     edx, 64Ah; void *
0x180014b2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014b33  nop
0x180014b34  lea     rcx, [rsp+238h+var_170]
0x180014b3c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014b41  nop
0x180014b42  lea     rcx, [rsp+238h+var_A8]
0x180014b4a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014b4f  nop
0x180014b50  lea     rcx, [rsp+238h+var_1E8]
0x180014b55  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180014b5a  nop
0x180014b5b  lea     rcx, [rsp+238h+var_108]; this
0x180014b63  call    ??1HttpContext@PrintCore@@QEAA@XZ; PrintCore::HttpContext::~HttpContext(void)
0x180014b68  nop
0x180014b69  lea     rcx, [rsp+238h+var_1B0]
0x180014b71  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014b76  nop
0x180014b77  lea     rcx, [rsp+238h+var_1F0]
0x180014b7c  call    ??1?$unique_ptr@VHttpRestChannel@PrintCore@@U?$default_delete@VHttpRestChannel@PrintCore@@@std@@@std@@QEAA@XZ; std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(void)
0x180014b81  nop
0x180014b82  lea     rcx, [rsp+238h+var_150]
0x180014b8a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014b8f  mov     eax, ebx
0x180014b91  jmp     loc_180014C25
0x180014b96  lea     rcx, [rdi+68h]
0x180014b9a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014b9f  mov     r9, rax
0x180014ba2  lea     rcx, [rdi+48h]
0x180014ba6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180014bab  mov     r8, rax
0x180014bae  lea     rdx, aDiscoverydevic; "DiscoveryDevicesSearchEndpoint: %s, Dis"...
0x180014bb5  lea     rcx, aCloudprintClou_1; "CloudPrint::CloudPrintHelper::GetDevice"...
0x180014bbc  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014bc1  nop
0x180014bc2  lea     rcx, [rsp+238h+var_170]
0x180014bca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014bcf  nop
0x180014bd0  lea     rcx, [rsp+238h+var_A8]
0x180014bd8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180014bdd  nop
0x180014bde  lea     rcx, [rsp+238h+var_1E8]
0x180014be3  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180014be8  nop
0x180014be9  lea     rcx, [rsp+238h+var_108]; this
0x180014bf1  call    ??1HttpContext@PrintCore@@QEAA@XZ; PrintCore::HttpContext::~HttpContext(void)
0x180014bf6  nop
0x180014bf7  lea     rcx, [rsp+238h+var_1B0]
0x180014bff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014c04  nop
0x180014c05  lea     rcx, [rsp+238h+var_1F0]
0x180014c0a  call    ??1?$unique_ptr@VHttpRestChannel@PrintCore@@U?$default_delete@VHttpRestChannel@PrintCore@@@std@@@std@@QEAA@XZ; std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(void)
0x180014c0f  nop
0x180014c10  lea     rcx, [rsp+238h+var_150]
0x180014c18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014c1d  xor     eax, eax
0x180014c1f  jmp     short loc_180014C25
0x180014c21  mov     eax, dword ptr [rsp+238h+var_1F8]
0x180014c25  mov     rcx, [rsp+238h+var_48]
0x180014c2d  xor     rcx, rsp; StackCookie
0x180014c30  call    __security_check_cookie
0x180014c35  movaps  xmm6, [rsp+238h+var_38]
0x180014c3d  add     rsp, 218h
0x180014c44  pop     r14
0x180014c46  pop     rdi
0x180014c47  pop     rsi
0x180014c48  pop     rbx
0x180014c49  retn
```
