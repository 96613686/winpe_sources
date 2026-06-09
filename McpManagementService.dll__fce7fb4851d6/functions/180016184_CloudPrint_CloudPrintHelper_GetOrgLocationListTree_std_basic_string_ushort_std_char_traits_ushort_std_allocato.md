# CloudPrint::CloudPrintHelper::GetOrgLocationListTree(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180016184`
- end: `0x18001691a`
- name: `?GetOrgLocationListTree@CloudPrintHelper@CloudPrint@@QEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1942`
- prototype: `__int64 __fastcall(CloudPrint::CloudPrintHelper *this, __int64)`
- caller_count: `1`
- callee_count: `43`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180026330`

## callees

- `0x180003a60`
- `0x180003aa0`
- `0x1800067a4`
- `0x180006b38`
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
- `0x180011030`
- `0x1800115c0`
- `0x180011d98`
- `0x180011de0`
- `0x180011f68`
- `0x1800120a0`
- `0x18001227c`
- `0x180012668`
- `0x1800129c4`
- `0x180012a44`
- `0x180012bfc`
- `0x180012e90`
- `0x180012f08`
- `0x1800138ec`
- `0x1800146b8`
- `0x180016184`
- `0x180016920`
- `0x180018668`
- `0x180018e60`
- `0x18001aaf4`
- `0x18001b8c4`
- `0x18001bfb0`
- `0x18001c0a8`
- `0x18001c298`
- `0x18001db04`
- `0x18001db44`
- `0x18001ddb4`
- `0x18001e4c4`
- `0x18001ef30`

## string_xrefs

- `0x18001648e`: `application/json`
- `0x1800166de`: `Discovery Service returned no locations.`

## pseudocode

```c
__int64 __fastcall CloudPrint::CloudPrintHelper::GetOrgLocationListTree(CloudPrint::CloudPrintHelper *this, __int64 a2)
{
  __int64 v5; // rcx
  int DeviceAndLocationSearchEndpoints; // eax
  unsigned int v7; // ebx
  void *v8; // r10
  __int64 v9; // rax
  __int64 v10; // rdx
  int AuthorizationHeaderByEndpointSilent; // ebx
  void *v12; // rbx
  struct PrintCore::HttpRestChannel *v13; // rbx
  __int64 v14; // rax
  int v15; // eax
  int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  int v20; // r8d
  __int64 v21; // rax
  int v22; // [rsp+20h] [rbp-208h]
  int v23; // [rsp+20h] [rbp-208h]
  int v24; // [rsp+28h] [rbp-200h]
  __int64 v25; // [rsp+40h] [rbp-1E8h] BYREF
  struct PrintCore::HttpRestChannel *v26; // [rsp+48h] [rbp-1E0h] BYREF
  _QWORD v27[4]; // [rsp+50h] [rbp-1D8h] BYREF
  __int64 v28; // [rsp+70h] [rbp-1B8h] BYREF
  int v29; // [rsp+78h] [rbp-1B0h]
  void *v30; // [rsp+80h] [rbp-1A8h]
  _BYTE v31[32]; // [rsp+88h] [rbp-1A0h] BYREF
  _BYTE v32[16]; // [rsp+A8h] [rbp-180h] BYREF
  __int64 v33; // [rsp+B8h] [rbp-170h]
  _BYTE v34[32]; // [rsp+C8h] [rbp-160h] BYREF
  _BYTE v35[32]; // [rsp+E8h] [rbp-140h] BYREF
  _BYTE v36[32]; // [rsp+108h] [rbp-120h] BYREF
  _BYTE v37[40]; // [rsp+128h] [rbp-100h] BYREF
  _OWORD v38[3]; // [rsp+150h] [rbp-D8h] BYREF
  _BYTE v39[32]; // [rsp+180h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+1A0h] [rbp-88h]
  _BYTE v41[32]; // [rsp+1B0h] [rbp-78h] BYREF
  _BYTE v42[32]; // [rsp+1D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  LODWORD(v25) = 0;
  if ( *((_BYTE *)this + 10) )
  {
    if ( a2 )
    {
      std::_WChar_traits<unsigned short>::length(L"MockOrgLocationListTree");
      std::wstring::_Assign<unsigned short>(a2, v5);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AB,
        (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
        (const char *)0x80004003LL,
        v22);
      return 2147500035LL;
    }
  }
  else if ( *((_BYTE *)this + 8) )
  {
    if ( CloudPrint::CloudPrintHelper::IsCloudPrintEnabled(this) )
    {
      if ( a2 )
      {
        *(_QWORD *)(a2 + 16) = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2) = 0;
        _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
          (char *)this + 136,
          &v26);
        if ( *((_QWORD *)this + 15)
          || (DeviceAndLocationSearchEndpoints = CloudPrint::CloudPrintHelper::GetDeviceAndLocationSearchEndpoints(this),
              v7 = DeviceAndLocationSearchEndpoints,
              DeviceAndLocationSearchEndpoints >= 0) )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v26);
          std::wstring::wstring(v31, (char *)this + 104);
          if ( (unsigned __int8)CloudPrint::CloudPrintHelper::UrlContainsQueryParameters(v31) )
            std::wstring::append(v31, L"&");
          else
            std::wstring::append(v31, L"?");
          std::to_wstring(v36, 0x7FFFFFFF);
          std::_WChar_traits<unsigned short>::length(L"scope=sub&location_tree_type=Org&limit=");
          v9 = std::wstring::_Insert<unsigned short>(v8);
          std::wstring::wstring(v34, v9);
          std::wstring::append(v31, v34);
          std::wstring::_Tidy_deallocate(v34);
          std::wstring::_Tidy_deallocate(v36);
          std::wstring::wstring(v37);
          AuthorizationHeaderByEndpointSilent = CloudPrint::CloudPrintHelper::GetAuthorizationHeaderByEndpointSilent(
                                                  this,
                                                  v10,
                                                  v37);
          if ( AuthorizationHeaderByEndpointSilent >= 0 )
          {
            v26 = 0;
            CloudPrint::ImpersonateClientRAII::ImpersonateClientRAII(
              (CloudPrint::ImpersonateClientRAII *)v32,
              *((int (**)(void *))this + 2),
              *((int (**)(void *))this + 3),
              *((void **)this + 4));
            v12 = operator new(0xC8u);
            v30 = v12;
            std::wstring::wstring(v36, L"Cloud Print Helper");
            std::wstring::wstring(v42, L"application/json");
            std::wstring::wstring(v34, L"GET");
            v28 = 7730941132860000LL;
            v29 = 1800000;
            v25 = PrintCore::HttpRestChannel::HttpRestChannel(
                    (__int64)v12,
                    (__int64)v34,
                    (__int64)v42,
                    (__int64)v36,
                    v22,
                    v24,
                    (__int64)&v28);
            std::unique_ptr<PrintCore::HttpRestChannel>::operator=<std::default_delete<PrintCore::HttpRestChannel>,0>(
              &v26,
              &v25);
            std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v25);
            std::wstring::_Tidy_deallocate(v34);
            std::wstring::_Tidy_deallocate(v42);
            std::wstring::_Tidy_deallocate(v36);
            CloudPrint::ImpersonateClientRAII::~ImpersonateClientRAII((CloudPrint::ImpersonateClientRAII *)v32);
            v13 = v26;
            std::wstring::wstring(v36, L"Authorization");
            PrintCore::HttpRestChannel::AddRequestHeader(v13, v36, v37);
            std::wstring::_Tidy_deallocate(v36);
            CloudPrint::CloudPrintHelper::IncrementAndAddCorrelationVectorHeader(this, v13);
            v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
            CloudPrintHelperTelemetry::WriteDbgTraceInfo(
              "CloudPrint::CloudPrintHelper::GetOrgLocationListTree",
              L"Getting Location List Tree. RequestUrl: %s",
              v14);
            memset(v38, 0, sizeof(v38));
            std::wstring::wstring(v39);
            v40 = 0;
            std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(v27);
            v15 = std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(v32);
            v16 = PrintCore::HttpRestChannel::SendRequestAndReceiveReply(
                    (_DWORD)v13,
                    (unsigned int)v31,
                    v15,
                    (unsigned int)v38,
                    (__int64)v27);
            std::vector<unsigned char>::_Tidy(v32);
            std::string::string(v41, v27[0], v27[1]);
            PrintCore::Serialization::AsciiToUnicode(v35, v41);
            if ( v16 >= 0 )
            {
              std::wstring::operator=(a2, v35);
              std::wstring::_Tidy_deallocate(v35);
              std::string::_Tidy_deallocate(v41);
              std::vector<unsigned char>::_Tidy(v27);
              PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v38);
              std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v26);
              std::wstring::_Tidy_deallocate(v37);
              std::wstring::_Tidy_deallocate(v31);
              return 0;
            }
            else
            {
              std::wstring::wstring(v32);
              CloudPrint::MopriaJsonParser::ExtractErrorCodeFromErrorResponse(v35, v32);
              if ( v33
                && (std::_WChar_traits<unsigned short>::length(L"err_no_match"),
                    v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32),
                    (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v18)) )
              {
                CloudPrintHelperTelemetry::WriteDbgTraceInfo(
                  "CloudPrint::CloudPrintHelper::GetOrgLocationListTree",
                  L"Discovery Service returned no locations.");
                std::wstring::_Tidy_deallocate(v32);
                std::wstring::_Tidy_deallocate(v35);
                std::string::_Tidy_deallocate(v41);
                std::vector<unsigned char>::_Tidy(v27);
                PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v38);
                std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v26);
                std::wstring::_Tidy_deallocate(v37);
                std::wstring::_Tidy_deallocate(v31);
                return 0;
              }
              else
              {
                CloudPrint::CloudPrintHelper::GetResponseTraceId(v17, v34, v38);
                std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
                v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
                v23 = v20;
                CloudPrintHelperTelemetry::WriteDbgTraceWarning(
                  "CloudPrint::CloudPrintHelper::GetOrgLocationListTree",
                  L"Failure response trying to get Org location list tree. HttpStatus=%u, ErrorResponse: %s, TraceId: %s",
                  (unsigned __int16)v16,
                  v19);
                std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
                v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
                PrintCore::McpEvtSrc::ReportErrorEvent(
                  L"Failure response trying to get Org location list tree. HttpStatus=%u, ErrorResponse: %s, TraceId: %s",
                  (unsigned __int16)v16,
                  v21);
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x204,
                  (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
                  (const char *)(unsigned int)v16,
                  v23);
                std::wstring::_Tidy_deallocate(v34);
                std::wstring::_Tidy_deallocate(v32);
                std::wstring::_Tidy_deallocate(v35);
                std::string::_Tidy_deallocate(v41);
                std::vector<unsigned char>::_Tidy(v27);
                PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v38);
                std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(&v26);
                std::wstring::_Tidy_deallocate(v37);
                std::wstring::_Tidy_deallocate(v31);
                return (unsigned int)v16;
              }
            }
          }
          else
          {
            std::wstring::_Tidy_deallocate(v37);
            std::wstring::_Tidy_deallocate(v31);
            return (unsigned int)AuthorizationHeaderByEndpointSilent;
          }
        }
        else
        {
          CloudPrintHelperTelemetry::WriteDbgTraceWarning(
            "CloudPrint::CloudPrintHelper::GetOrgLocationListTree",
            L"Failed to get device and location search endpoints. hr: %#x",
            (unsigned int)DeviceAndLocationSearchEndpoints);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v26);
          return v7;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1BC,
          (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
          (const char *)0x80004003LL,
          v22);
        return 2147500035LL;
      }
    }
    else
    {
      CloudPrintHelperTelemetry::WriteDbgTraceWarning(
        "CloudPrint::CloudPrintHelper::GetOrgLocationListTree",
        L"Cloud Print is not enabled.");
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B9,
        (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
        (const char *)0x8007139FLL,
        v22);
      return 2147947423LL;
    }
  }
  else
  {
    CloudPrintHelperTelemetry::WriteDbgTraceWarning(
      "CloudPrint::CloudPrintHelper::GetOrgLocationListTree",
      L"Cloud Print Helper is not initialized.");
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
      (const char *)0x80040007LL,
      v22);
    return 2147745799LL;
  }
}

```

## disassembly

```asm
0x180016184  mov     rax, rsp
0x180016187  mov     [rax+18h], rbx
0x18001618b  push    rsi
0x18001618c  push    rdi
0x18001618d  push    r14
0x18001618f  sub     rsp, 210h
0x180016196  movaps  xmmword ptr [rax-28h], xmm6
0x18001619a  mov     rax, cs:__security_cookie
0x1800161a1  xor     rax, rsp
0x1800161a4  mov     [rsp+228h+var_38], rax
0x1800161ac  mov     rsi, rdx
0x1800161af  mov     rdi, rcx
0x1800161b2  mov     dword ptr [rsp+228h+var_1E8], 0
0x1800161ba  cmp     byte ptr [rcx+0Ah], 0
0x1800161be  jz      short loc_18001620E
0x1800161c0  test    rdx, rdx
0x1800161c3  jnz     short loc_1800161ED
0x1800161c5  mov     rcx, [rsp+228h]; this
0x1800161cd  mov     ebx, 80004003h
0x1800161d2  mov     r9d, ebx; char *
0x1800161d5  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x1800161dc  mov     edx, 1ABh; void *
0x1800161e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800161e6  mov     eax, ebx
0x1800161e8  jmp     loc_1800168F0
0x1800161ed  lea     rcx, aMockorglocatio; "MockOrgLocationListTree"
0x1800161f4  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800161f9  mov     r8, rax
0x1800161fc  mov     rdx, rcx
0x1800161ff  mov     rcx, rsi
0x180016202  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180016207  xor     eax, eax
0x180016209  jmp     loc_1800168F0
0x18001620e  cmp     byte ptr [rcx+8], 0
0x180016212  jnz     short loc_18001624F
0x180016214  lea     rdx, aCloudPrintHelp_0; "Cloud Print Helper is not initialized."
0x18001621b  lea     rcx, aCloudprintClou_4; "CloudPrint::CloudPrintHelper::GetOrgLoc"...
0x180016222  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180016227  mov     rcx, [rsp+228h]; this
0x18001622f  mov     ebx, 80040007h
0x180016234  mov     r9d, ebx; char *
0x180016237  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x18001623e  mov     edx, 1B3h; void *
0x180016243  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016248  mov     eax, ebx
0x18001624a  jmp     loc_1800168F0
0x18001624f  call    ?IsCloudPrintEnabled@CloudPrintHelper@CloudPrint@@QEBA_NXZ; CloudPrint::CloudPrintHelper::IsCloudPrintEnabled(void)
0x180016254  test    al, al
0x180016256  jnz     short loc_180016293
0x180016258  lea     rdx, aCloudPrintIsNo; "Cloud Print is not enabled."
0x18001625f  lea     rcx, aCloudprintClou_4; "CloudPrint::CloudPrintHelper::GetOrgLoc"...
0x180016266  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001626b  mov     rcx, [rsp+228h]; this
0x180016273  mov     ebx, 8007139Fh
0x180016278  mov     r9d, ebx; char *
0x18001627b  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180016282  mov     edx, 1B9h; void *
0x180016287  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001628c  mov     eax, ebx
0x18001628e  jmp     loc_1800168F0
0x180016293  test    rsi, rsi
0x180016296  jnz     short loc_1800162C0
0x180016298  mov     rcx, [rsp+228h]; this
0x1800162a0  mov     ebx, 80004003h
0x1800162a5  mov     r9d, ebx; char *
0x1800162a8  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x1800162af  mov     edx, 1BCh; void *
0x1800162b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800162b9  mov     eax, ebx
0x1800162bb  jmp     loc_1800168F0
0x1800162c0  mov     qword ptr [rsi+10h], 0
0x1800162c8  mov     rcx, rsi
0x1800162cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800162d0  xor     ecx, ecx
0x1800162d2  mov     [rax], cx
0x1800162d5  lea     rcx, [rdi+88h]
0x1800162dc  lea     rdx, [rsp+228h+var_1E0]
0x1800162e1  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800162e6  cmp     qword ptr [rdi+78h], 0
0x1800162eb  jnz     short loc_180016322
0x1800162ed  mov     rcx, rdi; this
0x1800162f0  call    ?GetDeviceAndLocationSearchEndpoints@CloudPrintHelper@CloudPrint@@IEAAJXZ; CloudPrint::CloudPrintHelper::GetDeviceAndLocationSearchEndpoints(void)
0x1800162f5  mov     ebx, eax
0x1800162f7  test    eax, eax
0x1800162f9  jns     short loc_180016322
0x1800162fb  mov     r8d, eax
0x1800162fe  lea     rdx, aFailedToGetDev; "Failed to get device and location searc"...
0x180016305  lea     rcx, aCloudprintClou_4; "CloudPrint::CloudPrintHelper::GetOrgLoc"...
0x18001630c  call    ?WriteDbgTraceWarning@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180016311  lea     rcx, [rsp+228h+var_1E0]
0x180016316  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001631b  mov     eax, ebx
0x18001631d  jmp     loc_1800168F0
0x180016322  lea     rcx, [rsp+228h+var_1E0]
0x180016327  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001632c  lea     rdx, [rdi+68h]
0x180016330  lea     rcx, [rsp+228h+var_1A0]
0x180016338  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001633d  nop
0x18001633e  lea     rcx, [rsp+228h+var_1A0]
0x180016346  call    ?UrlContainsQueryParameters@CloudPrintHelper@CloudPrint@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudPrint::CloudPrintHelper::UrlContainsQueryParameters(std::wstring const &)
0x18001634b  lea     rcx, [rsp+228h+var_1A0]
0x180016353  test    al, al
0x180016355  jz      short loc_180016365
0x180016357  lea     rdx, asc_180030D38; "&"
0x18001635e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180016363  jmp     short loc_180016371
0x180016365  lea     rdx, asc_180030D3C; "?"
0x18001636c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180016371  mov     edx, 7FFFFFFFh
0x180016376  lea     rcx, [rsp+228h+var_120]
0x18001637e  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x180016383  mov     r10, rax
0x180016386  lea     rcx, aScopeSubLocati; "scope=sub&location_tree_type=Org&limit="
0x18001638d  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180016392  mov     r9, rax
0x180016395  mov     r8, rcx
0x180016398  xor     edx, edx
0x18001639a  mov     rcx, r10; Src
0x18001639d  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x1800163a2  mov     rdx, rax
0x1800163a5  lea     rcx, [rsp+228h+var_160]
0x1800163ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800163b2  nop
0x1800163b3  lea     rdx, [rsp+228h+var_160]
0x1800163bb  lea     rcx, [rsp+228h+var_1A0]
0x1800163c3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800163c8  nop
0x1800163c9  lea     rcx, [rsp+228h+var_160]
0x1800163d1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800163d6  nop
0x1800163d7  lea     rcx, [rsp+228h+var_120]
0x1800163df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800163e4  lea     rcx, [rsp+228h+var_100]
0x1800163ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800163f1  nop
0x1800163f2  lea     r8, [rsp+228h+var_100]
0x1800163fa  mov     rcx, rdi
0x1800163fd  call    ?GetAuthorizationHeaderByEndpointSilent@CloudPrintHelper@CloudPrint@@QEBAJW4CloudPrintEndpoint@2@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; CloudPrint::CloudPrintHelper::GetAuthorizationHeaderByEndpointSilent(CloudPrint::CloudPrintEndpoint,std::wstring *,std::wstring *,std::wstring *,std::wstring *)
0x180016402  mov     ebx, eax
0x180016404  test    eax, eax
0x180016406  jns     short loc_18001642A
0x180016408  lea     rcx, [rsp+228h+var_100]
0x180016410  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016415  nop
0x180016416  lea     rcx, [rsp+228h+var_1A0]
0x18001641e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016423  mov     eax, ebx
0x180016425  jmp     loc_1800168F0
0x18001642a  mov     [rsp+228h+var_1E0], 0
0x180016433  mov     r9, [rdi+20h]; void *
0x180016437  mov     r8, [rdi+18h]; int (*)(void *)
0x18001643b  mov     rdx, [rdi+10h]; int (*)(void *)
0x18001643f  lea     rcx, [rsp+228h+var_180]; this
0x180016447  call    ??0ImpersonateClientRAII@CloudPrint@@QEAA@P6AJPEAX@Z10@Z; CloudPrint::ImpersonateClientRAII::ImpersonateClientRAII(long (*)(void *),long (*)(void *),void *)
0x18001644c  nop
0x18001644d  mov     ecx, 0C8h; Size
0x180016452  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016457  mov     rbx, rax
0x18001645a  mov     [rsp+228h+var_1A8], rax
0x180016462  movsd   xmm6, cs:qword_18002F010
0x18001646a  mov     r14d, cs:dword_18002F018
0x180016471  lea     rdx, aCloudPrintHelp; "Cloud Print Helper"
0x180016478  lea     rcx, [rsp+228h+var_120]
0x180016480  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016485  nop
0x180016486  mov     dword ptr [rsp+228h+var_1E8], 9
0x18001648e  lea     rdx, aApplicationJso; "application/json"
0x180016495  lea     rcx, [rsp+228h+var_58]
0x18001649d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800164a2  nop
0x1800164a3  mov     dword ptr [rsp+228h+var_1E8], 0Bh
0x1800164ab  lea     rdx, aGet; "GET"
0x1800164b2  lea     rcx, [rsp+228h+var_160]
0x1800164ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800164bf  nop
0x1800164c0  mov     dword ptr [rsp+228h+var_1E8], 0Fh
0x1800164c8  movsd   [rsp+228h+var_1B8], xmm6
0x1800164ce  mov     [rsp+228h+var_1B0], r14d
0x1800164d3  lea     rax, [rsp+228h+var_1B8]
0x1800164d8  mov     [rsp+228h+var_1F8], rax
0x1800164dd  lea     r9, [rsp+228h+var_120]
0x1800164e5  lea     r8, [rsp+228h+var_58]
0x1800164ed  lea     rdx, [rsp+228h+var_160]
0x1800164f5  mov     rcx, rbx
0x1800164f8  call    ??0HttpRestChannel@PrintCore@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00_NKUHttpTimeouts@1@@Z; PrintCore::HttpRestChannel::HttpRestChannel(std::wstring const &,std::wstring const &,std::wstring const &,bool,ulong,PrintCore::HttpTimeouts)
0x1800164fd  nop
0x1800164fe  mov     [rsp+228h+var_1E8], rax
0x180016503  lea     rdx, [rsp+228h+var_1E8]
0x180016508  lea     rcx, [rsp+228h+var_1E0]
0x18001650d  call    ??$?4U?$default_delete@VHttpRestChannel@PrintCore@@@std@@$0A@@?$unique_ptr@VHttpRestChannel@PrintCore@@U?$default_delete@VHttpRestChannel@PrintCore@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<PrintCore::HttpRestChannel>::operator=<std::default_delete<PrintCore::HttpRestChannel>,0>(std::unique_ptr<PrintCore::HttpRestChannel> &&)
0x180016512  lea     rcx, [rsp+228h+var_1E8]
0x180016517  call    ??1?$unique_ptr@VHttpRestChannel@PrintCore@@U?$default_delete@VHttpRestChannel@PrintCore@@@std@@@std@@QEAA@XZ; std::unique_ptr<PrintCore::HttpRestChannel>::~unique_ptr<PrintCore::HttpRestChannel>(void)
0x18001651c  nop
0x18001651d  lea     rcx, [rsp+228h+var_160]
0x180016525  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001652a  nop
0x18001652b  lea     rcx, [rsp+228h+var_58]
0x180016533  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016538  nop
0x180016539  lea     rcx, [rsp+228h+var_120]
0x180016541  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016546  nop
0x180016547  lea     rcx, [rsp+228h+var_180]; this
0x18001654f  call    ??1ImpersonateClientRAII@CloudPrint@@QEAA@XZ; CloudPrint::ImpersonateClientRAII::~ImpersonateClientRAII(void)
0x180016554  mov     rbx, [rsp+228h+var_1E0]
0x180016559  lea     rdx, aAuthorization; "Authorization"
0x180016560  lea     rcx, [rsp+228h+var_120]
0x180016568  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001656d  nop
0x18001656e  lea     r8, [rsp+228h+var_100]
0x180016576  lea     rdx, [rsp+228h+var_120]
0x18001657e  mov     rcx, rbx
0x180016581  call    ?AddRequestHeader@HttpRestChannel@PrintCore@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PrintCore::HttpRestChannel::AddRequestHeader(std::wstring const &,std::wstring const &)
0x180016586  nop
0x180016587  lea     rcx, [rsp+228h+var_120]
0x18001658f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016594  mov     rdx, rbx; struct PrintCore::HttpRestChannel *
0x180016597  mov     rcx, rdi; this
0x18001659a  call    ?IncrementAndAddCorrelationVectorHeader@CloudPrintHelper@CloudPrint@@IEAAXPEAVHttpRestChannel@PrintCore@@@Z; CloudPrint::CloudPrintHelper::IncrementAndAddCorrelationVectorHeader(PrintCore::HttpRestChannel *)
0x18001659f  lea     rcx, [rsp+228h+var_1A0]
0x1800165a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800165ac  mov     r8, rax
0x1800165af  lea     rdx, aGettingLocatio; "Getting Location List Tree. RequestUrl:"...
0x1800165b6  lea     rcx, aCloudprintClou_4; "CloudPrint::CloudPrintHelper::GetOrgLoc"...
0x1800165bd  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800165c2  xorps   xmm1, xmm1
0x1800165c5  movdqa  [rsp+228h+var_D8], xmm1
0x1800165ce  movdqa  [rsp+228h+var_C8], xmm1
0x1800165d7  movdqa  [rsp+228h+var_B8], xmm1
0x1800165e0  lea     rcx, [rsp+228h+var_A8]
0x1800165e8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800165ed  nop
0x1800165ee  xor     eax, eax
0x1800165f0  mov     [rsp+228h+var_88], rax
0x1800165f8  lea     rcx, [rsp+228h+var_1D8]
0x1800165fd  call    ??0?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@QEAA@XZ; std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(void)
0x180016602  nop
0x180016603  lea     rcx, [rsp+228h+var_180]
0x18001660b  call    ??0?$vector@UCloudPrinter@CloudPrint@@V?$allocator@UCloudPrinter@CloudPrint@@@std@@@std@@QEAA@XZ; std::vector<CloudPrint::CloudPrinter>::vector<CloudPrint::CloudPrinter>(void)
0x180016610  nop
0x180016611  lea     rcx, [rsp+228h+var_1D8]
0x180016616  mov     qword ptr [rsp+228h+var_208], rcx
0x18001661b  lea     r9, [rsp+228h+var_D8]
0x180016623  mov     r8, rax
0x180016626  lea     rdx, [rsp+228h+var_1A0]
0x18001662e  mov     rcx, rbx
0x180016631  call    ?SendRequestAndReceiveReply@HttpRestChannel@PrintCore@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@AEAUHttpContext@2@AEAV54@_N@Z; PrintCore::HttpRestChannel::SendRequestAndReceiveReply(std::wstring const &,std::vector<uchar> const &,PrintCore::HttpContext &,std::vector<uchar> &,bool)
0x180016636  mov     ebx, eax
0x180016638  lea     rcx, [rsp+228h+var_180]
0x180016640  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180016645  mov     r8, [rsp+228h+var_1D0]
0x18001664a  mov     rdx, [rsp+228h+var_1D8]
0x18001664f  lea     rcx, [rsp+228h+var_78]
0x180016657  call    ??$?0V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@0AEBV?$allocator@D@1@@Z; std::string::string(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::allocator<char> const &)
0x18001665c  nop
0x18001665d  lea     rdx, [rsp+228h+var_78]
0x180016665  lea     rcx, [rsp+228h+var_140]
0x18001666d  call    ?AsciiToUnicode@Serialization@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; PrintCore::Serialization::AsciiToUnicode(std::string const &)
0x180016672  nop
0x180016673  test    ebx, ebx
0x180016675  jns     loc_18001687C
0x18001667b  lea     rcx, [rsp+228h+var_180]
0x180016683  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016688  nop
0x180016689  lea     rdx, [rsp+228h+var_180]
0x180016691  lea     rcx, [rsp+228h+var_140]
0x180016699  call    ?ExtractErrorCodeFromErrorResponse@MopriaJsonParser@CloudPrint@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV34@@Z; CloudPrint::MopriaJsonParser::ExtractErrorCodeFromErrorResponse(std::wstring const &,std::wstring *)
0x18001669e  mov     rdx, [rsp+228h+var_170]
0x1800166a6  test    rdx, rdx
0x1800166a9  jz      loc_180016762
0x1800166af  lea     r8, aErrNoMatch; "err_no_match"
0x1800166b6  mov     rcx, r8
0x1800166b9  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800166be  mov     r9, rax
0x1800166c1  lea     rcx, [rsp+228h+var_180]
0x1800166c9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800166ce  mov     rcx, rax
0x1800166d1  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800166d6  test    al, al
0x1800166d8  jz      loc_180016762
0x1800166de  lea     rdx, aDiscoveryServi; "Discovery Service returned no locations"...
0x1800166e5  lea     rcx, aCloudprintClou_4; "CloudPrint::CloudPrintHelper::GetOrgLoc"...
0x1800166ec  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800166f1  nop
0x1800166f2  lea     rcx, [rsp+228h+var_180]
0x1800166fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800166ff  nop
0x180016700  lea     rcx, [rsp+228h+var_140]
0x180016708  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001670d  nop
0x18001670e  lea     rcx, [rsp+228h+var_78]
0x180016716  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001671b  nop
0x18001671c  lea     rcx, [rsp+228h+var_1D8]
0x180016721  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180016726  nop
0x180016727  lea     rcx, [rsp+228h+var_D8]; this
0x18001672f  call    ??1HttpContext@PrintCore@@QEAA@XZ; PrintCore::HttpContext::~HttpContext(void)
0x180016734  nop
  ... truncated ...
```
