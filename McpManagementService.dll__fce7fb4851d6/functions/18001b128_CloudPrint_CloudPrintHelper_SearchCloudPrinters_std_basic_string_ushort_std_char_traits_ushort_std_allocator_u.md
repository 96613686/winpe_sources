# CloudPrint::CloudPrintHelper::SearchCloudPrinters(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<CloudPrint::CloudPrinter,std::allocator<CloudPrint::CloudPrinter>> *)

- ea: `0x18001b128`
- end: `0x18001b8bd`
- name: `?SearchCloudPrinters@CloudPrintHelper@CloudPrint@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@4@@Z`
- size: `1941`
- prototype: `__int64 __fastcall(CloudPrint::CloudPrintHelper *this)`
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800268a0`

## callees

- `0x180003a60`
- `0x180003aa0`
- `0x180006b70`
- `0x18000753c`
- `0x18000c4cc`
- `0x18000e164`
- `0x18000e208`
- `0x18000e284`
- `0x18000e2dc`
- `0x18000e5e8`
- `0x18000f804`
- `0x18000f848`
- `0x1800115c0`
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
- `0x180018e60`
- `0x180019d74`
- `0x18001aaf4`
- `0x18001b128`
- `0x18001b8c4`
- `0x18001bfb0`
- `0x18001c0a8`
- `0x18001c298`
- `0x18001db04`
- `0x18001db44`
- `0x18001ddb4`
- `0x18001dde8`
- `0x18001ef30`
- `0x18001f9a4`

## string_xrefs

- `0x18001b38c`: `application/json`
- `0x18001b5dc`: `Discovery Service returned no devices.`

## pseudocode

```c
// Hidden C++ exception states: #wind=19 #try_helpers=1
__int64 __fastcall CloudPrint::CloudPrintHelper::SearchCloudPrinters(
        CloudPrint::CloudPrintHelper *this,
        __int64 a2,
        __int64 a3)
{
  int DeviceAndLocationSearchEndpoints; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int AuthorizationHeaderByEndpointSilent; // ebx
  void *v11; // rbx
  struct PrintCore::HttpRestChannel *v12; // rbx
  __int64 v13; // rax
  __int64 *v14; // rax
  int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // r8d
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // [rsp+20h] [rbp-208h]
  int v24; // [rsp+20h] [rbp-208h]
  int v25; // [rsp+20h] [rbp-208h]
  int v26; // [rsp+28h] [rbp-200h]
  struct PrintCore::HttpRestChannel *v27; // [rsp+40h] [rbp-1E8h] BYREF
  __int64 v28; // [rsp+48h] [rbp-1E0h] BYREF
  int v29[2]; // [rsp+50h] [rbp-1D8h] BYREF
  __int64 v30; // [rsp+58h] [rbp-1D0h]
  __int64 v31; // [rsp+70h] [rbp-1B8h] BYREF
  int v32; // [rsp+78h] [rbp-1B0h]
  void *v33; // [rsp+80h] [rbp-1A8h]
  _BYTE v34[32]; // [rsp+88h] [rbp-1A0h] BYREF
  _BYTE v35[16]; // [rsp+A8h] [rbp-180h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-170h]
  _BYTE v37[32]; // [rsp+C8h] [rbp-160h] BYREF
  _BYTE v38[32]; // [rsp+E8h] [rbp-140h] BYREF
  _BYTE v39[32]; // [rsp+108h] [rbp-120h] BYREF
  _BYTE v40[32]; // [rsp+128h] [rbp-100h] BYREF
  _BYTE v41[40]; // [rsp+148h] [rbp-E0h] BYREF
  _OWORD v42[3]; // [rsp+170h] [rbp-B8h] BYREF
  _BYTE v43[32]; // [rsp+1A0h] [rbp-88h] BYREF
  __int64 v44; // [rsp+1C0h] [rbp-68h]
  _BYTE v45[32]; // [rsp+1D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  LODWORD(v28) = 0;
  if ( *((_BYTE *)this + 10) || *((_BYTE *)this + 11) )
    return CloudPrint::CloudPrintHelper::MockedCloudPrinters((__int64)this, a2, a3);
  if ( *((_BYTE *)this + 8) )
  {
    if ( CloudPrint::CloudPrintHelper::IsCloudPrintEnabled(this) )
    {
      if ( a3 )
      {
        std::vector<CloudPrint::CloudPrinter>::clear(a3);
        _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
          (char *)this + 136,
          &v27);
        if ( *((_QWORD *)this + 11)
          || (DeviceAndLocationSearchEndpoints = CloudPrint::CloudPrintHelper::GetDeviceAndLocationSearchEndpoints(this),
              v8 = DeviceAndLocationSearchEndpoints,
              DeviceAndLocationSearchEndpoints >= 0) )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
          std::wstring::wstring((__int64)v34, (__int64)this + 72);
          if ( *(_QWORD *)(a2 + 16) )
          {
            if ( (unsigned __int8)CloudPrint::CloudPrintHelper::UrlContainsQueryParameters(v34) )
              std::wstring::append((__int64)v34, (__int64)L"&");
            else
              std::wstring::append((__int64)v34, (__int64)L"?");
            std::wstring::append(v34, a2);
          }
          std::wstring::wstring((__int64)v38);
          AuthorizationHeaderByEndpointSilent = CloudPrint::CloudPrintHelper::GetAuthorizationHeaderByEndpointSilent(
                                                  (int)this,
                                                  v9,
                                                  (__int64)v38);
          if ( AuthorizationHeaderByEndpointSilent >= 0 )
          {
            v27 = 0;
            CloudPrint::ImpersonateClientRAII::ImpersonateClientRAII(
              (CloudPrint::ImpersonateClientRAII *)v35,
              *((int (**)(void *))this + 2),
              *((int (**)(void *))this + 3),
              *((void **)this + 4));
            v11 = operator new(0xC8u);
            v33 = v11;
            std::wstring::wstring((__int64)v41, (__int64)L"Cloud Print Helper");
            LODWORD(v28) = 1;
            std::wstring::wstring((__int64)v45, (__int64)L"application/json");
            LODWORD(v28) = 3;
            std::wstring::wstring((__int64)v39, (__int64)L"GET");
            LODWORD(v28) = 7;
            v31 = 7730941132860000LL;
            v32 = 1800000;
            v28 = PrintCore::HttpRestChannel::HttpRestChannel(
                    (__int64)v11,
                    (__int64)v39,
                    (__int64)v45,
                    (__int64)v41,
                    v23,
                    v26,
                    (__int64)&v31);
            std::unique_ptr<PrintCore::HttpRestChannel>::operator=<std::default_delete<PrintCore::HttpRestChannel>,0>(
              (__int64 *)&v27,
              &v28);
            std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v28);
            std::wstring::_Tidy_deallocate((__int64)v39);
            std::wstring::_Tidy_deallocate((__int64)v45);
            std::wstring::_Tidy_deallocate((__int64)v41);
            CloudPrint::ImpersonateClientRAII::~ImpersonateClientRAII((CloudPrint::ImpersonateClientRAII *)v35);
            v12 = v27;
            std::wstring::wstring((__int64)v41, (__int64)L"Authorization");
            PrintCore::HttpRestChannel::AddRequestHeader(v12, v41, v38);
            std::wstring::_Tidy_deallocate((__int64)v41);
            CloudPrint::CloudPrintHelper::IncrementAndAddCorrelationVectorHeader(this, v12);
            v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
            CloudPrintHelperTelemetry::WriteDbgTraceInfo(
              "CloudPrint::CloudPrintHelper::SearchCloudPrinters",
              L"Searching for Cloud Printers. RequestUrl: %s",
              v13);
            memset(v42, 0, sizeof(v42));
            std::wstring::wstring((__int64)v43);
            v44 = 0;
            std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(v29);
            v14 = (__int64 *)std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(v35);
            v15 = PrintCore::HttpRestChannel::SendRequestAndReceiveReply(
                    v12,
                    (__int64)v34,
                    v14,
                    (__int64)v42,
                    (__int64)v29);
            std::vector<unsigned char>::_Tidy(v35);
            std::string::string(v40, *(_QWORD *)v29, v30);
            PrintCore::Serialization::AsciiToUnicode(v37, v40);
            if ( v15 >= 0 )
            {
              v21 = CloudPrint::MopriaJsonParser::ParseHttpResponseForCloudPrinters((__int64)v37, a3);
              v22 = v21;
              if ( v21 >= 0 )
              {
                std::wstring::_Tidy_deallocate((__int64)v37);
                std::string::_Tidy_deallocate(v40);
                std::vector<unsigned char>::_Tidy(v29);
                PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v42);
                std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v27);
                std::wstring::_Tidy_deallocate((__int64)v38);
                std::wstring::_Tidy_deallocate((__int64)v34);
                return 0;
              }
              else
              {
                CloudPrintHelperTelemetry::WriteDbgTraceWarning(
                  "CloudPrint::CloudPrintHelper::SearchCloudPrinters",
                  L"Failed to parse Mopria Cloud Discovery /Devices response with %#x",
                  (unsigned int)v21);
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x274,
                  (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
                  (const char *)v22,
                  v24);
                std::wstring::_Tidy_deallocate((__int64)v37);
                std::string::_Tidy_deallocate(v40);
                std::vector<unsigned char>::_Tidy(v29);
                PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v42);
                std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v27);
                std::wstring::_Tidy_deallocate((__int64)v38);
                std::wstring::_Tidy_deallocate((__int64)v34);
                return v22;
              }
            }
            else
            {
              std::wstring::wstring((__int64)v35);
              CloudPrint::MopriaJsonParser::ExtractErrorCodeFromErrorResponse((__int64)v37, (__int64)v35);
              if ( v36
                && (std::_WChar_traits<unsigned short>::length(L"err_no_match"),
                    v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(),
                    (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v17)) )
              {
                CloudPrintHelperTelemetry::WriteDbgTraceInfo(
                  "CloudPrint::CloudPrintHelper::SearchCloudPrinters",
                  L"Discovery Service returned no devices.");
                std::wstring::_Tidy_deallocate((__int64)v35);
                std::wstring::_Tidy_deallocate((__int64)v37);
                std::string::_Tidy_deallocate(v40);
                std::vector<unsigned char>::_Tidy(v29);
                PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v42);
                std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v27);
                std::wstring::_Tidy_deallocate((__int64)v38);
                std::wstring::_Tidy_deallocate((__int64)v34);
                return 0;
              }
              else
              {
                CloudPrint::CloudPrintHelper::GetResponseTraceId(v16, v39, v42);
                std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
                v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
                v25 = v19;
                CloudPrintHelperTelemetry::WriteDbgTraceWarning(
                  "CloudPrint::CloudPrintHelper::SearchCloudPrinters",
                  L"Failure Response trying to search for printers. HttpStatus=%u, ErrorResponse: %s, TraceId: %s",
                  (unsigned __int16)v15,
                  v18);
                std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
                v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
                PrintCore::McpEvtSrc::ReportErrorEvent(
                  L"Failure Response trying to search for printers. HttpStatus=%u, ErrorResponse: %s, TraceId: %s",
                  (unsigned __int16)v15,
                  v20);
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x26C,
                  (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
                  (const char *)(unsigned int)v15,
                  v25);
                std::wstring::_Tidy_deallocate((__int64)v39);
                std::wstring::_Tidy_deallocate((__int64)v35);
                std::wstring::_Tidy_deallocate((__int64)v37);
                std::string::_Tidy_deallocate(v40);
                std::vector<unsigned char>::_Tidy(v29);
                PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v42);
                std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v27);
                std::wstring::_Tidy_deallocate((__int64)v38);
                std::wstring::_Tidy_deallocate((__int64)v34);
                return (unsigned int)v15;
              }
            }
          }
          else
          {
            std::wstring::_Tidy_deallocate((__int64)v38);
            std::wstring::_Tidy_deallocate((__int64)v34);
            return (unsigned int)AuthorizationHeaderByEndpointSilent;
          }
        }
        else
        {
          CloudPrintHelperTelemetry::WriteDbgTraceWarning(
            "CloudPrint::CloudPrintHelper::SearchCloudPrinters",
            L"Failed to get device and location search endpoints. hr: %#x",
            (unsigned int)DeviceAndLocationSearchEndpoints);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
          return v8;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x222,
          (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
          (const char *)0x80004003LL,
          v23);
        return 2147500035LL;
      }
    }
    else
    {
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::SearchCloudPrinters",
        L"Cloud Print is not enabled.");
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21F,
        (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
        (const char *)0x8007139FLL,
        v23);
      return 2147947423LL;
    }
  }
  else
  {
    CloudPrintHelperTelemetry::WriteDbgTraceWarning(
      "CloudPrint::CloudPrintHelper::SearchCloudPrinters",
      L"Cloud Print Helper is not initialized.");
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x219,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
      (const char *)0x80040007LL,
      v23);
    return 2147745799LL;
  }
}

```

## disassembly

```asm
0x18001b128  mov     rax, rsp
0x18001b12b  mov     [rax+20h], rbx
0x18001b12f  push    rsi
0x18001b130  push    rdi
0x18001b131  push    r14
0x18001b133  sub     rsp, 210h
0x18001b13a  movaps  xmmword ptr [rax-28h], xmm6
0x18001b13e  mov     rax, cs:__security_cookie
0x18001b145  xor     rax, rsp
0x18001b148  mov     [rsp+228h+var_38], rax
0x18001b150  mov     rsi, r8
0x18001b153  mov     r14, rdx
0x18001b156  mov     rdi, rcx
0x18001b159  mov     dword ptr [rsp+228h+var_1E0], 0
0x18001b161  cmp     byte ptr [rcx+0Ah], 0
0x18001b165  jnz     loc_18001B888
0x18001b16b  cmp     byte ptr [rcx+0Bh], 0
0x18001b16f  jnz     loc_18001B888
0x18001b175  cmp     byte ptr [rcx+8], 0
0x18001b179  jnz     short loc_18001B1B6
0x18001b17b  lea     rdx, aCloudPrintHelp_0; "Cloud Print Helper is not initialized."
0x18001b182  lea     rcx, aCloudprintClou_5; "CloudPrint::CloudPrintHelper::SearchClo"...
0x18001b189  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001b18e  mov     rcx, [rsp+228h]; this
0x18001b196  mov     ebx, 80040007h
0x18001b19b  mov     r9d, ebx; char *
0x18001b19e  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001b1a5  mov     edx, 219h; void *
0x18001b1aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b1af  mov     eax, ebx
0x18001b1b1  jmp     loc_18001B893
0x18001b1b6  call    ?IsCloudPrintEnabled@CloudPrintHelper@CloudPrint@@QEBA_NXZ; CloudPrint::CloudPrintHelper::IsCloudPrintEnabled(void)
0x18001b1bb  test    al, al
0x18001b1bd  jnz     short loc_18001B1FA
0x18001b1bf  lea     rdx, aCloudPrintIsNo; "Cloud Print is not enabled."
0x18001b1c6  lea     rcx, aCloudprintClou_5; "CloudPrint::CloudPrintHelper::SearchClo"...
0x18001b1cd  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001b1d2  mov     rcx, [rsp+228h]; this
0x18001b1da  mov     ebx, 8007139Fh
0x18001b1df  mov     r9d, ebx; char *
0x18001b1e2  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001b1e9  mov     edx, 21Fh; void *
0x18001b1ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b1f3  mov     eax, ebx
0x18001b1f5  jmp     loc_18001B893
0x18001b1fa  test    rsi, rsi
0x18001b1fd  jnz     short loc_18001B227
0x18001b1ff  mov     rcx, [rsp+228h]; this
0x18001b207  mov     ebx, 80004003h
0x18001b20c  mov     r9d, ebx; char *
0x18001b20f  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001b216  mov     edx, 222h; void *
0x18001b21b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b220  mov     eax, ebx
0x18001b222  jmp     loc_18001B893
0x18001b227  mov     rcx, rsi
0x18001b22a  call    ?clear@?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@QEAAXXZ; std::vector<CloudPrint::CloudPrinter>::clear(void)
0x18001b22f  lea     rcx, [rdi+88h]
0x18001b236  lea     rdx, [rsp+228h+var_1E8]
0x18001b23b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001b240  cmp     qword ptr [rdi+58h], 0
0x18001b245  jnz     short loc_18001B27C
0x18001b247  mov     rcx, rdi; this
0x18001b24a  call    ?GetDeviceAndLocationSearchEndpoints@CloudPrintHelper@CloudPrint@@IEAAJXZ; CloudPrint::CloudPrintHelper::GetDeviceAndLocationSearchEndpoints(void)
0x18001b24f  mov     ebx, eax
0x18001b251  test    eax, eax
0x18001b253  jns     short loc_18001B27C
0x18001b255  mov     r8d, eax
0x18001b258  lea     rdx, aFailedToGetDev; "Failed to get device and location searc"...
0x18001b25f  lea     rcx, aCloudprintClou_5; "CloudPrint::CloudPrintHelper::SearchClo"...
0x18001b266  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001b26b  lea     rcx, [rsp+228h+var_1E8]
0x18001b270  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b275  mov     eax, ebx
0x18001b277  jmp     loc_18001B893
0x18001b27c  lea     rcx, [rsp+228h+var_1E8]
0x18001b281  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b286  lea     rdx, [rdi+48h]
0x18001b28a  lea     rcx, [rsp+228h+var_1A0]
0x18001b292  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001b297  nop
0x18001b298  cmp     qword ptr [r14+10h], 0
0x18001b29d  jz      short loc_18001B2E2
0x18001b29f  lea     rcx, [rsp+228h+var_1A0]
0x18001b2a7  call    ?UrlContainsQueryParameters@CloudPrintHelper@CloudPrint@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudPrint::CloudPrintHelper::UrlContainsQueryParameters(std::wstring const &)
0x18001b2ac  lea     rcx, [rsp+228h+var_1A0]
0x18001b2b4  test    al, al
0x18001b2b6  jz      short loc_18001B2C6
0x18001b2b8  lea     rdx, asc_180030D38; "&"
0x18001b2bf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001b2c4  jmp     short loc_18001B2D2
0x18001b2c6  lea     rdx, asc_180030D3C; "?"
0x18001b2cd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001b2d2  mov     rdx, r14
0x18001b2d5  lea     rcx, [rsp+228h+var_1A0]
0x18001b2dd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18001b2e2  lea     rcx, [rsp+228h+var_140]
0x18001b2ea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b2ef  nop
0x18001b2f0  lea     r8, [rsp+228h+var_140]
0x18001b2f8  mov     rcx, rdi
0x18001b2fb  call    ?GetAuthorizationHeaderByEndpointSilent@CloudPrintHelper@CloudPrint@@QEBAJW4CloudPrintEndpoint@2@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; CloudPrint::CloudPrintHelper::GetAuthorizationHeaderByEndpointSilent(CloudPrint::CloudPrintEndpoint,std::wstring *,std::wstring *,std::wstring *,std::wstring *)
0x18001b300  mov     ebx, eax
0x18001b302  test    eax, eax
0x18001b304  jns     short loc_18001B328
0x18001b306  lea     rcx, [rsp+228h+var_140]
0x18001b30e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b313  nop
0x18001b314  lea     rcx, [rsp+228h+var_1A0]
0x18001b31c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b321  mov     eax, ebx
0x18001b323  jmp     loc_18001B893
0x18001b328  mov     [rsp+228h+var_1E8], 0
0x18001b331  mov     r9, [rdi+20h]; void *
0x18001b335  mov     r8, [rdi+18h]; int (*)(void *)
0x18001b339  mov     rdx, [rdi+10h]; int (*)(void *)
0x18001b33d  lea     rcx, [rsp+228h+var_180]; this
0x18001b345  call    ??0ImpersonateClientRAII@CloudPrint@@QEAA@P6AJPEAX@Z10@Z; CloudPrint::ImpersonateClientRAII::ImpersonateClientRAII(long (*)(void *),long (*)(void *),void *)
0x18001b34a  nop
0x18001b34b  mov     ecx, 0C8h; Size
0x18001b350  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b355  mov     rbx, rax
0x18001b358  mov     [rsp+228h+var_1A8], rax
0x18001b360  movsd   xmm6, cs:qword_18002F010
0x18001b368  mov     r14d, cs:dword_18002F018
0x18001b36f  lea     rdx, aCloudPrintHelp; "Cloud Print Helper"
0x18001b376  lea     rcx, [rsp+228h+var_E0]
0x18001b37e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001b383  nop
0x18001b384  mov     dword ptr [rsp+228h+var_1E0], 1
0x18001b38c  lea     rdx, aApplicationJso; "application/json"
0x18001b393  lea     rcx, [rsp+228h+var_58]
0x18001b39b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001b3a0  nop
0x18001b3a1  mov     dword ptr [rsp+228h+var_1E0], 3
0x18001b3a9  lea     rdx, aGet; "GET"
0x18001b3b0  lea     rcx, [rsp+228h+var_120]
0x18001b3b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001b3bd  nop
0x18001b3be  mov     dword ptr [rsp+228h+var_1E0], 7
0x18001b3c6  movsd   [rsp+228h+var_1B8], xmm6
0x18001b3cc  mov     [rsp+228h+var_1B0], r14d
0x18001b3d1  lea     rax, [rsp+228h+var_1B8]
0x18001b3d6  mov     [rsp+228h+var_1F8], rax
0x18001b3db  lea     r9, [rsp+228h+var_E0]
0x18001b3e3  lea     r8, [rsp+228h+var_58]
0x18001b3eb  lea     rdx, [rsp+228h+var_120]
0x18001b3f3  mov     rcx, rbx
0x18001b3f6  call    ??0HttpRestChannel@PrintCore@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00_NKUHttpTimeouts@1@@Z; PrintCore::HttpRestChannel::HttpRestChannel(std::wstring const &,std::wstring const &,std::wstring const &,bool,ulong,PrintCore::HttpTimeouts)
0x18001b3fb  nop
0x18001b3fc  mov     [rsp+228h+var_1E0], rax
0x18001b401  lea     rdx, [rsp+228h+var_1E0]
0x18001b406  lea     rcx, [rsp+228h+var_1E8]
0x18001b40b  call    ??$?4U?$default_delete@VHttpRestChannel@PrintCore@@@std@@$0A@@?$unique_ptr@VHttpRestChannel@PrintCore@@U?$default_delete@VHttpRestChannel@PrintCore@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<PrintCore::HttpRestChannel>::operator=<std::default_delete<PrintCore::HttpRestChannel>,0>(std::unique_ptr<PrintCore::HttpRestChannel> &&)
0x18001b410  lea     rcx, [rsp+228h+var_1E0]
0x18001b415  call    ??1?$unique_ptr@VHttpRestChannel@PrintCore@@U?$default_delete@VHttpRestChannel@PrintCore@@@std@@@std@@QEAA@XZ; std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(void)
0x18001b41a  nop
0x18001b41b  lea     rcx, [rsp+228h+var_120]
0x18001b423  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b428  nop
0x18001b429  lea     rcx, [rsp+228h+var_58]
0x18001b431  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b436  nop
0x18001b437  lea     rcx, [rsp+228h+var_E0]
0x18001b43f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b444  nop
0x18001b445  lea     rcx, [rsp+228h+var_180]; this
0x18001b44d  call    ??1ImpersonateClientRAII@CloudPrint@@QEAA@XZ; CloudPrint::ImpersonateClientRAII::~ImpersonateClientRAII(void)
0x18001b452  mov     rbx, [rsp+228h+var_1E8]
0x18001b457  lea     rdx, aAuthorization; "Authorization"
0x18001b45e  lea     rcx, [rsp+228h+var_E0]
0x18001b466  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001b46b  nop
0x18001b46c  lea     r8, [rsp+228h+var_140]
0x18001b474  lea     rdx, [rsp+228h+var_E0]
0x18001b47c  mov     rcx, rbx
0x18001b47f  call    ?AddRequestHeader@HttpRestChannel@PrintCore@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PrintCore::HttpRestChannel::AddRequestHeader(std::wstring const &,std::wstring const &)
0x18001b484  nop
0x18001b485  lea     rcx, [rsp+228h+var_E0]
0x18001b48d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b492  mov     rdx, rbx; struct PrintCore::HttpRestChannel *
0x18001b495  mov     rcx, rdi; this
0x18001b498  call    ?IncrementAndAddCorrelationVectorHeader@CloudPrintHelper@CloudPrint@@IEAAXPEAVHttpRestChannel@PrintCore@@@Z; CloudPrint::CloudPrintHelper::IncrementAndAddCorrelationVectorHeader(PrintCore::HttpRestChannel *)
0x18001b49d  lea     rcx, [rsp+228h+var_1A0]
0x18001b4a5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b4aa  mov     r8, rax
0x18001b4ad  lea     rdx, aSearchingForCl; "Searching for Cloud Printers. RequestUr"...
0x18001b4b4  lea     rcx, aCloudprintClou_5; "CloudPrint::CloudPrintHelper::SearchClo"...
0x18001b4bb  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001b4c0  xorps   xmm1, xmm1
0x18001b4c3  movdqa  [rsp+228h+var_B8], xmm1
0x18001b4cc  movdqa  [rsp+228h+var_A8], xmm1
0x18001b4d5  movdqa  [rsp+228h+var_98], xmm1
0x18001b4de  lea     rcx, [rsp+228h+var_88]
0x18001b4e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b4eb  nop
0x18001b4ec  xor     eax, eax
0x18001b4ee  mov     [rsp+228h+var_68], rax
0x18001b4f6  lea     rcx, [rsp+228h+var_1D8]
0x18001b4fb  call    ??0?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@QEAA@XZ; std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(void)
0x18001b500  nop
0x18001b501  lea     rcx, [rsp+228h+var_180]
0x18001b509  call    ??0?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@QEAA@XZ; std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(void)
0x18001b50e  nop
0x18001b50f  lea     rcx, [rsp+228h+var_1D8]
0x18001b514  mov     qword ptr [rsp+228h+var_208], rcx; int
0x18001b519  lea     r9, [rsp+228h+var_B8]
0x18001b521  mov     r8, rax
0x18001b524  lea     rdx, [rsp+228h+var_1A0]
0x18001b52c  mov     rcx, rbx
0x18001b52f  call    ?SendRequestAndReceiveReply@HttpRestChannel@PrintCore@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@AEAUHttpContext@2@AEAV54@_N@Z; PrintCore::HttpRestChannel::SendRequestAndReceiveReply(std::wstring const &,std::vector<uchar> const &,PrintCore::HttpContext &,std::vector<uchar> &,bool)
0x18001b534  mov     ebx, eax
0x18001b536  lea     rcx, [rsp+228h+var_180]
0x18001b53e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001b543  mov     r8, [rsp+228h+var_1D0]
0x18001b548  mov     rdx, qword ptr [rsp+228h+var_1D8]
0x18001b54d  lea     rcx, [rsp+228h+var_100]
0x18001b555  call    ??$?0V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@0AEBV?$allocator@D@1@@Z; std::string::string(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::allocator<char> const &)
0x18001b55a  nop
0x18001b55b  lea     rdx, [rsp+228h+var_100]
0x18001b563  lea     rcx, [rsp+228h+var_160]
0x18001b56b  call    ?AsciiToUnicode@Serialization@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; PrintCore::Serialization::AsciiToUnicode(std::string const &)
0x18001b570  nop
0x18001b571  test    ebx, ebx
0x18001b573  jns     loc_18001B77D
0x18001b579  lea     rcx, [rsp+228h+var_180]
0x18001b581  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b586  nop
0x18001b587  lea     rdx, [rsp+228h+var_180]
0x18001b58f  lea     rcx, [rsp+228h+var_160]
0x18001b597  call    ?ExtractErrorCodeFromErrorResponse@MopriaJsonParser@CloudPrint@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV34@@Z; CloudPrint::MopriaJsonParser::ExtractErrorCodeFromErrorResponse(std::wstring const &,std::wstring *)
0x18001b59c  mov     rdx, [rsp+228h+var_170]
0x18001b5a4  test    rdx, rdx
0x18001b5a7  jz      loc_18001B660
0x18001b5ad  lea     r8, aErrNoMatch; "err_no_match"
0x18001b5b4  mov     rcx, r8
0x18001b5b7  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001b5bc  mov     r9, rax
0x18001b5bf  lea     rcx, [rsp+228h+var_180]
0x18001b5c7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b5cc  mov     rcx, rax
0x18001b5cf  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001b5d4  test    al, al
0x18001b5d6  jz      loc_18001B660
0x18001b5dc  lea     rdx, aDiscoveryServi_0; "Discovery Service returned no devices."
0x18001b5e3  lea     rcx, aCloudprintClou_5; "CloudPrint::CloudPrintHelper::SearchClo"...
0x18001b5ea  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001b5ef  nop
0x18001b5f0  lea     rcx, [rsp+228h+var_180]
0x18001b5f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b5fd  nop
0x18001b5fe  lea     rcx, [rsp+228h+var_160]
0x18001b606  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b60b  nop
0x18001b60c  lea     rcx, [rsp+228h+var_100]
0x18001b614  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001b619  nop
0x18001b61a  lea     rcx, [rsp+228h+var_1D8]
0x18001b61f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001b624  nop
0x18001b625  lea     rcx, [rsp+228h+var_B8]; this
0x18001b62d  call    ??1HttpContext@PrintCore@@QEAA@XZ; PrintCore::HttpContext::~HttpContext(void)
0x18001b632  nop
0x18001b633  lea     rcx, [rsp+228h+var_1E8]
0x18001b638  call    ??1?$unique_ptr@VHttpRestChannel@PrintCore@@U?$default_delete@VHttpRestChannel@PrintCore@@@std@@@std@@QEAA@XZ; std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(void)
0x18001b63d  nop
0x18001b63e  lea     rcx, [rsp+228h+var_140]
0x18001b646  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b64b  nop
0x18001b64c  lea     rcx, [rsp+228h+var_1A0]
0x18001b654  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b659  xor     eax, eax
0x18001b65b  jmp     loc_18001B893
0x18001b660  movzx   edi, bx
0x18001b663  lea     r8, [rsp+228h+var_B8]
0x18001b66b  lea     rdx, [rsp+228h+var_120]
0x18001b673  call    ?GetResponseTraceId@CloudPrintHelper@CloudPrint@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUHttpContext@PrintCore@@PEAVHttpRestChannel@6@@Z; CloudPrint::CloudPrintHelper::GetResponseTraceId(PrintCore::HttpContext const &,PrintCore::HttpRestChannel *)
0x18001b678  nop
0x18001b679  lea     rcx, [rsp+228h+var_120]
0x18001b681  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b686  mov     r8, rax
0x18001b689  lea     rcx, [rsp+228h+var_160]
0x18001b691  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b696  mov     r9, rax
0x18001b699  mov     qword ptr [rsp+228h+var_208], r8; int
0x18001b69e  mov     r8d, edi
0x18001b6a1  lea     rdx, aFailureRespons_1; "Failure Response trying to search for p"...
0x18001b6a8  lea     rcx, aCloudprintClou_5; "CloudPrint::CloudPrintHelper::SearchClo"...
0x18001b6af  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001b6b4  lea     rcx, [rsp+228h+var_120]
0x18001b6bc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b6c1  mov     r9, rax
0x18001b6c4  lea     rcx, [rsp+228h+var_160]
0x18001b6cc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b6d1  mov     r8, rax
0x18001b6d4  mov     edx, edi
0x18001b6d6  lea     rcx, aFailureRespons_1; "Failure Response trying to search for p"...
0x18001b6dd  call    ?ReportErrorEvent@McpEvtSrc@PrintCore@@SAXPEBGZZ; PrintCore::McpEvtSrc::ReportErrorEvent(ushort const *,...)
0x18001b6e2  mov     rcx, [rsp+228h]; this
0x18001b6ea  mov     r9d, ebx; char *
  ... truncated ...
```
