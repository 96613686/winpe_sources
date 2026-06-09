# Microsoft::Diagnostics::Utils::Os::GetServiceProcessIdsRegex(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,int,std::unordered_multimap<ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::hash<ulong>,std::equal_to<ulong>,std::allocator<std::pair<ulong const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>> &,Microsoft::Diagnostics::EscalationWorkItemState *)

- ea: `0x18031f0a4`
- end: `0x18031f9e9`
- name: `?GetServiceProcessIdsRegex@Os@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@HAEAV?$unordered_multimap@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@6@PEAVEscalationWorkItemState@34@@Z`
- size: `2373`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18031ccb0`
- `0x18032a8e0`

## callees

- `0x18001b510`
- `0x180027c28`
- `0x18002967c`
- `0x18006b958`
- `0x18008abf4`
- `0x1800f7b34`
- `0x1800f7f64`
- `0x18019b4b0`
- `0x1801ecf60`
- `0x18031b144`
- `0x18031b284`
- `0x18031f0a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f14d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f3a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f3f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f57d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f7bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f8c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f14d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f3a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f3f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f57d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f7bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031f8c6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18031f35d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18031f35d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18031f0d4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18031f0d4`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18031f394`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18031f3df`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18031f394`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18031f3df`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18031f13f`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18031f1b6`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18031f13f`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18031f1b6`

## string_xrefs

- `0x18031f1dc`: `Failed to query services (2): 0x`
- `0x18031f8de`: `Failed to open SC Manager: 0x`
- `0x18031f7d7`: `Failed to query services (1): 0x`
- `0x18031f405`: `Failed to query PID for service (2), `
- `0x18031f58c`: `Failed to query PID for service (1), `
- `0x18031f697`: `Failed to open service, `
- `0x18031f53e`: `Found PID matching regex, service '`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::GetServiceProcessIdsRegex(
        _QWORD *a1,
        DWORD a2,
        __int64 a3,
        __int64 a4)
{
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rdi
  DWORD v9; // r13d
  const struct std::nothrow_t *v10; // rdx
  DWORD LastError; // ebx
  __int64 v12; // rax
  void *v13; // rax
  __int64 v14; // rax
  void *v15; // rax
  unsigned int v16; // ebx
  const struct std::nothrow_t *v17; // rdx
  const char *v18; // r9
  __int64 result; // rax
  LPBYTE v20; // r12
  LPCWSTR *v21; // r12
  SC_HANDLE v22; // rbx
  const struct std::nothrow_t *v23; // rdx
  void *v24; // rax
  void *v25; // rax
  __int64 v26; // rax
  void *v27; // rax
  __int64 v28; // rax
  void *v29; // rax
  void *v30; // rax
  void *v31; // rax
  void *v32; // rax
  void *v33; // rax
  void *v34; // rax
  __int64 v35; // rax
  void *v36; // rax
  __int64 v37; // rax
  void *v38; // rax
  void *v39; // rax
  void *v40; // rax
  __int64 v41; // rax
  void *v42; // rax
  __int64 v43; // rax
  void *v44; // rax
  const struct std::nothrow_t *v45; // rdx
  DWORD v46; // ebx
  __int64 v47; // rax
  void *v48; // rax
  __int64 v49; // rax
  void *v50; // rax
  unsigned int v51; // ebx
  DWORD v52; // ebx
  __int64 v53; // rax
  void *v54; // rax
  __int64 v55; // rax
  void *v56; // rax
  unsigned int v57; // ebx
  unsigned int lpServices; // [rsp+20h] [rbp-198h]
  unsigned int lpServicesa; // [rsp+20h] [rbp-198h]
  unsigned int lpServicesb; // [rsp+20h] [rbp-198h]
  char v61; // [rsp+50h] [rbp-168h] BYREF
  _BYTE v62[3]; // [rsp+51h] [rbp-167h]
  int v63; // [rsp+54h] [rbp-164h]
  __int64 v64; // [rsp+58h] [rbp-160h]
  DWORD pcbBytesNeeded; // [rsp+60h] [rbp-158h] BYREF
  DWORD ServicesReturned; // [rsp+64h] [rbp-154h] BYREF
  int v67; // [rsp+68h] [rbp-150h] BYREF
  _QWORD v68[2]; // [rsp+70h] [rbp-148h] BYREF
  char v69; // [rsp+80h] [rbp-138h] BYREF
  __int16 v70; // [rsp+81h] [rbp-137h]
  char v71; // [rsp+83h] [rbp-135h]
  int v72; // [rsp+84h] [rbp-134h]
  __int64 v73; // [rsp+88h] [rbp-130h]
  unsigned __int8 v74; // [rsp+91h] [rbp-127h]
  __int16 v75; // [rsp+92h] [rbp-126h]
  DWORD ResumeHandle; // [rsp+A0h] [rbp-118h] BYREF
  LPBYTE v77; // [rsp+A8h] [rbp-110h] BYREF
  LPBYTE lpBuffer; // [rsp+B0h] [rbp-108h] BYREF
  SC_HANDLE v79; // [rsp+B8h] [rbp-100h] BYREF
  char v80; // [rsp+C0h] [rbp-F8h] BYREF
  __int16 v81; // [rsp+C1h] [rbp-F7h]
  char v82; // [rsp+C3h] [rbp-F5h]
  int v83; // [rsp+C4h] [rbp-F4h]
  __int64 v84; // [rsp+C8h] [rbp-F0h]
  char v85; // [rsp+D0h] [rbp-E8h] BYREF
  __int16 v86; // [rsp+D1h] [rbp-E7h]
  char v87; // [rsp+D3h] [rbp-E5h]
  int v88; // [rsp+D4h] [rbp-E4h]
  __int64 v89; // [rsp+D8h] [rbp-E0h]
  char v90; // [rsp+E0h] [rbp-D8h] BYREF
  __int16 v91; // [rsp+E1h] [rbp-D7h]
  char v92; // [rsp+E3h] [rbp-D5h]
  int v93; // [rsp+E4h] [rbp-D4h]
  __int64 v94; // [rsp+E8h] [rbp-D0h]
  char v95; // [rsp+F0h] [rbp-C8h] BYREF
  __int16 v96; // [rsp+F1h] [rbp-C7h]
  char v97; // [rsp+F3h] [rbp-C5h]
  int v98; // [rsp+F4h] [rbp-C4h]
  __int64 v99; // [rsp+F8h] [rbp-C0h]
  char v100; // [rsp+100h] [rbp-B8h] BYREF
  __int16 v101; // [rsp+101h] [rbp-B7h]
  char v102; // [rsp+103h] [rbp-B5h]
  int v103; // [rsp+104h] [rbp-B4h]
  __int64 v104; // [rsp+108h] [rbp-B0h]
  LPBYTE v105; // [rsp+110h] [rbp-A8h]
  unsigned __int8 v106; // [rsp+119h] [rbp-9Fh]
  __int16 v107; // [rsp+11Ah] [rbp-9Eh]
  unsigned __int8 v108; // [rsp+129h] [rbp-8Fh]
  __int16 v109; // [rsp+12Ah] [rbp-8Eh]
  unsigned __int8 v110; // [rsp+139h] [rbp-7Fh]
  __int16 v111; // [rsp+13Ah] [rbp-7Eh]
  unsigned __int8 v112; // [rsp+149h] [rbp-6Fh]
  __int16 v113; // [rsp+14Ah] [rbp-6Eh]
  unsigned __int8 v114; // [rsp+159h] [rbp-5Fh]
  __int16 v115; // [rsp+15Ah] [rbp-5Eh]
  _BYTE v116[40]; // [rsp+168h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v7 = OpenSCManagerW(0, 0, 4u);
  try
  {
    v8 = v7;
    v68[0] = v7;
    v9 = 0;
    if ( v7 )
    {
      pcbBytesNeeded = 0;
      ServicesReturned = 0;
      ResumeHandle = 0;
      if ( !EnumServicesStatusExW(
              v7,
              SC_ENUM_PROCESS_INFO,
              0x30u,
              a2,
              0,
              0,
              &pcbBytesNeeded,
              &ServicesReturned,
              &ResumeHandle,
              0)
        && GetLastError() == 234 )
      {
        std::make_unique<unsigned char [0],0>(&v77, pcbBytesNeeded);
        if ( !EnumServicesStatusExW(
                v8,
                SC_ENUM_PROCESS_INFO,
                0x30u,
                a2,
                v77,
                pcbBytesNeeded,
                &pcbBytesNeeded,
                &ServicesReturned,
                &ResumeHandle,
                0) )
        {
          LastError = GetLastError();
          if ( a4 )
          {
            v12 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
            v69 = 1;
            v70 = v62[0];
            v71 = 0;
            v72 = 2097153;
            v73 = 0;
            v13 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v12, &v69);
            v14 = Microsoft::Diagnostics::WideStringStream::operator<<(v13);
            *(_WORD *)&v62[1] = 0;
            v69 = 1;
            v70 = v62[0];
            v71 = 0;
            v72 = 0x200000;
            v73 = 0;
            v15 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v14, &v69);
            Microsoft::Diagnostics::WideStringStream::operator<<(v15);
          }
          if ( LastError )
          {
            v16 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x5A4,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                    (const char *)LastError,
                    lpServicesb);
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&v77, v17);
            wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v68);
            return v16;
          }
          else
          {
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&v77, v10);
            wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v68);
            return 0;
          }
        }
        v20 = v77;
        v105 = v77;
        std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(
          v116,
          *a1,
          a1[1]);
        while ( 1 )
        {
          if ( v9 >= ServicesReturned )
          {
            std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(v116);
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&v77, v45);
            wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v68);
            return 0;
          }
          v21 = (LPCWSTR *)&v20[56 * v9];
          if ( (unsigned __int8)std::regex_search<wchar_t,std::regex_traits<wchar_t>>(*v21, v116) )
            break;
LABEL_29:
          ++v9;
          v20 = v105;
        }
        v22 = OpenServiceW(v8, *v21, 4u);
        v79 = v22;
        if ( !v22 )
        {
          if ( a4 )
          {
            GetLastError();
            v39 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
            v40 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v39);
            v41 = Microsoft::Diagnostics::WideStringStream::operator<<(v40);
            v115 = 0;
            v100 = 1;
            v101 = v114;
            v102 = 0;
            v103 = 2097153;
            v104 = 0;
            v42 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v41, &v100);
            v43 = Microsoft::Diagnostics::WideStringStream::operator<<(v42);
            v75 = 0;
            v61 = 1;
            *(_WORD *)v62 = v74;
            v62[2] = 0;
            v63 = 0x200000;
            v64 = 0;
            v44 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v43, &v61);
            Microsoft::Diagnostics::WideStringStream::operator<<(v44);
          }
          goto LABEL_28;
        }
        pcbBytesNeeded = 0;
        if ( QueryServiceStatusEx(v22, SC_STATUS_PROCESS_INFO, 0, 0, &pcbBytesNeeded) || GetLastError() != 122 )
        {
          if ( a4 )
          {
            GetLastError();
            v33 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
            v34 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v33);
            v35 = Microsoft::Diagnostics::WideStringStream::operator<<(v34);
            v111 = 0;
            v90 = 1;
            v91 = v110;
            v92 = 0;
            v93 = 2097153;
            v94 = 0;
            v36 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v35, &v90);
            v37 = Microsoft::Diagnostics::WideStringStream::operator<<(v36);
            v113 = 0;
            v95 = 1;
            v96 = v112;
            v97 = 0;
            v98 = 0x200000;
            v99 = 0;
            v38 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v37, &v95);
            Microsoft::Diagnostics::WideStringStream::operator<<(v38);
          }
          goto LABEL_28;
        }
        std::make_unique<unsigned char [0],0>(&lpBuffer, pcbBytesNeeded);
        if ( QueryServiceStatusEx(v22, SC_STATUS_PROCESS_INFO, lpBuffer, pcbBytesNeeded, &pcbBytesNeeded) )
        {
          v67 = *((_DWORD *)lpBuffer + 7);
          std::_Hash<std::_Umap_traits<unsigned long,std::wstring,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::wstring>>,1>>::emplace<unsigned long &,wchar_t * &>(
            a3,
            &v69,
            &v67,
            v21);
          if ( !a4 )
            goto LABEL_21;
          v30 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
          v31 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v30);
          v32 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v31);
          v29 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v32);
        }
        else
        {
          if ( !a4 )
          {
LABEL_21:
            std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>((void **)&lpBuffer, v23);
LABEL_28:
            wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v79);
            goto LABEL_29;
          }
          GetLastError();
          v24 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
          v25 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v24);
          v26 = Microsoft::Diagnostics::WideStringStream::operator<<(v25);
          v107 = 0;
          v80 = 1;
          v81 = v106;
          v82 = 0;
          v83 = 2097153;
          v84 = 0;
          v27 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v26, &v80);
          v28 = Microsoft::Diagnostics::WideStringStream::operator<<(v27);
          v109 = 0;
          v85 = 1;
          v86 = v108;
          v87 = 0;
          v88 = 0x200000;
          v89 = 0;
          v29 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v28, &v85);
        }
        Microsoft::Diagnostics::WideStringStream::operator<<(v29);
        goto LABEL_21;
      }
      v46 = GetLastError();
      if ( a4 )
      {
        v47 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
        v75 = 0;
        v61 = 1;
        *(_WORD *)v62 = v74;
        v62[2] = 0;
        v63 = 2097153;
        v64 = 0;
        v48 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v47, &v61);
        v49 = Microsoft::Diagnostics::WideStringStream::operator<<(v48);
        v75 = 0;
        v61 = 1;
        *(_WORD *)v62 = v74;
        v62[2] = 0;
        v63 = 0x200000;
        v64 = 0;
        v50 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v49, &v61);
        Microsoft::Diagnostics::WideStringStream::operator<<(v50);
      }
      if ( v46 )
      {
        v51 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x590,
                (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                (const char *)v46,
                lpServicesa);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v68);
        return v51;
      }
    }
    else
    {
      v52 = GetLastError();
      if ( a4 )
      {
        v53 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a4 + 168));
        v75 = 0;
        v61 = 1;
        *(_WORD *)v62 = v74;
        v62[2] = 0;
        v63 = 2097153;
        v64 = 0;
        v54 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v53, &v61);
        v55 = Microsoft::Diagnostics::WideStringStream::operator<<(v54);
        v75 = 0;
        v61 = 1;
        *(_WORD *)v62 = v74;
        v62[2] = 0;
        v63 = 0x200000;
        v64 = 0;
        v56 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v55, &v61);
        Microsoft::Diagnostics::WideStringStream::operator<<(v56);
      }
      if ( v52 )
      {
        v57 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x579,
                (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                (const char *)v52,
                lpServices);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v68);
        return v57;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v68);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5DF,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x18031f0a4  mov     [rsp+arg_0], rbx
0x18031f0a9  mov     [rsp+arg_8], rsi
0x18031f0ae  mov     [rsp+arg_10], r8
0x18031f0b3  push    rdi
0x18031f0b4  push    r12
0x18031f0b6  push    r13
0x18031f0b8  push    r14
0x18031f0ba  push    r15
0x18031f0bc  sub     rsp, 190h
0x18031f0c3  mov     rsi, r9
0x18031f0c6  mov     r14d, edx
0x18031f0c9  mov     rbx, rcx
0x18031f0cc  xor     edx, edx; lpDatabaseName
0x18031f0ce  xor     ecx, ecx; lpMachineName
0x18031f0d0  lea     r8d, [rdx+4]; dwDesiredAccess
0x18031f0d4  call    cs:__imp_OpenSCManagerW
0x18031f0da  mov     rdi, rax
0x18031f0dd  mov     [rsp+1B8h+var_148], rax
0x18031f0e2  xor     r13d, r13d
0x18031f0e5  test    rax, rax
0x18031f0e8  jz      loc_18031F8C6
0x18031f0ee  mov     [rsp+1B8h+var_158], r13d
0x18031f0f3  mov     [rsp+1B8h+ServicesReturned], r13d
0x18031f0f8  mov     [rsp+1B8h+ResumeHandle], r13d
0x18031f100  mov     [rsp+1B8h+pszGroupName], r13; pszGroupName
0x18031f105  lea     rax, [rsp+1B8h+ResumeHandle]
0x18031f10d  mov     [rsp+1B8h+lpResumeHandle], rax; lpResumeHandle
0x18031f112  lea     rax, [rsp+1B8h+ServicesReturned]
0x18031f117  mov     [rsp+1B8h+lpServicesReturned], rax; lpServicesReturned
0x18031f11c  lea     rax, [rsp+1B8h+var_158]
0x18031f121  mov     [rsp+1B8h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18031f126  mov     [rsp+1B8h+cbBufSize], r13d; cbBufSize
0x18031f12b  mov     [rsp+1B8h+lpServices], r13; unsigned int
0x18031f130  mov     r9d, r14d; dwServiceState
0x18031f133  lea     r15d, [r13+30h]
0x18031f137  mov     r8d, r15d; dwServiceType
0x18031f13a  xor     edx, edx; InfoLevel
0x18031f13c  mov     rcx, rdi; hSCManager
0x18031f13f  call    cs:__imp_EnumServicesStatusExW
0x18031f145  test    eax, eax
0x18031f147  jnz     loc_18031F7BF
0x18031f14d  call    cs:__imp_GetLastError
0x18031f153  cmp     eax, 0EAh
0x18031f158  jnz     loc_18031F7BF
0x18031f15e  mov     edx, [rsp+1B8h+var_158]
0x18031f162  lea     rcx, [rsp+1B8h+var_110]
0x18031f16a  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x18031f16f  nop
0x18031f170  mov     eax, [rsp+1B8h+var_158]
0x18031f174  mov     rcx, [rsp+1B8h+var_110]
0x18031f17c  mov     [rsp+1B8h+pszGroupName], r13; pszGroupName
0x18031f181  lea     rdx, [rsp+1B8h+ResumeHandle]
0x18031f189  mov     [rsp+1B8h+lpResumeHandle], rdx; lpResumeHandle
0x18031f18e  lea     rdx, [rsp+1B8h+ServicesReturned]
0x18031f193  mov     [rsp+1B8h+lpServicesReturned], rdx; lpServicesReturned
0x18031f198  lea     rdx, [rsp+1B8h+var_158]
0x18031f19d  mov     [rsp+1B8h+pcbBytesNeeded], rdx; pcbBytesNeeded
0x18031f1a2  mov     [rsp+1B8h+cbBufSize], eax; cbBufSize
0x18031f1a6  mov     [rsp+1B8h+lpServices], rcx; unsigned int
0x18031f1ab  mov     r9d, r14d; dwServiceState
0x18031f1ae  mov     r8d, r15d; dwServiceType
0x18031f1b1  xor     edx, edx; InfoLevel
0x18031f1b3  mov     rcx, rdi; hSCManager
0x18031f1b6  call    cs:__imp_EnumServicesStatusExW
0x18031f1bc  test    eax, eax
0x18031f1be  jnz     loc_18031F2F7
0x18031f1c4  call    cs:__imp_GetLastError
0x18031f1ca  mov     ebx, eax
0x18031f1cc  test    rsi, rsi
0x18031f1cf  jz      loc_18031F297
0x18031f1d5  lea     rcx, [rsi+0A8h]; Src
0x18031f1dc  lea     rdx, aFailedToQueryS_0; "Failed to query services (2): 0x"
0x18031f1e3  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f1e8  mov     [rsp+1B8h+var_166], r13w
0x18031f1ee  lea     r14d, [r13+1]
0x18031f1f2  mov     [rsp+1B8h+var_138], r14b
0x18031f1fa  movzx   ecx, word ptr [rsp+51h]
0x18031f1ff  mov     [rsp+1B8h+var_137], cx
0x18031f207  mov     cl, byte ptr [rsp+1B8h+var_166+1]
0x18031f20b  mov     [rsp+1B8h+var_135], cl
0x18031f212  mov     [rsp+1B8h+var_134], 200001h
0x18031f21d  mov     [rsp+1B8h+var_130], r13
0x18031f225  lea     rdx, [rsp+1B8h+var_138]
0x18031f22d  mov     rcx, rax
0x18031f230  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18031f235  mov     edx, ebx
0x18031f237  mov     rcx, rax; Src
0x18031f23a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x18031f23f  mov     [rsp+1B8h+var_166], r13w
0x18031f245  mov     [rsp+1B8h+var_138], r14b
0x18031f24d  movzx   ecx, word ptr [rsp+51h]
0x18031f252  mov     [rsp+1B8h+var_137], cx
0x18031f25a  mov     cl, byte ptr [rsp+1B8h+var_166+1]
0x18031f25e  mov     [rsp+1B8h+var_135], cl
0x18031f265  mov     [rsp+1B8h+var_134], 200000h
0x18031f270  mov     [rsp+1B8h+var_130], r13
0x18031f278  lea     rdx, [rsp+1B8h+var_138]
0x18031f280  mov     rcx, rax
0x18031f283  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18031f288  lea     rdx, asc_1803A0C7C; "\r\n"
0x18031f28f  mov     rcx, rax; Src
0x18031f292  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f297  test    ebx, ebx
0x18031f299  jz      short loc_18031F2D8
0x18031f29b  mov     rcx, [rsp+1B8h]; this
0x18031f2a3  mov     r9d, ebx; char *
0x18031f2a6  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x18031f2ad  mov     edx, 5A4h; void *
0x18031f2b2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18031f2b7  mov     ebx, eax
0x18031f2b9  lea     rcx, [rsp+1B8h+var_110]
0x18031f2c1  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x18031f2c6  nop
0x18031f2c7  lea     rcx, [rsp+1B8h+var_148]
0x18031f2cc  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18031f2d1  mov     eax, ebx
0x18031f2d3  jmp     loc_18031F9CB
0x18031f2d8  lea     rcx, [rsp+1B8h+var_110]
0x18031f2e0  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x18031f2e5  nop
0x18031f2e6  lea     rcx, [rsp+1B8h+var_148]
0x18031f2eb  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18031f2f0  xor     eax, eax
0x18031f2f2  jmp     loc_18031F9CB
0x18031f2f7  mov     r12, [rsp+1B8h+var_110]
0x18031f2ff  mov     [rsp+1B8h+var_A8], r12
0x18031f307  mov     r8, [rbx+8]
0x18031f30b  mov     rdx, [rbx]
0x18031f30e  lea     rcx, [rsp+1B8h+var_50]
0x18031f316  call    ??0?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@PEB_W_KW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(wchar_t const *,unsigned __int64,std::regex_constants::syntax_option_type)
0x18031f31b  nop
0x18031f31c  mov     r14d, 1
0x18031f322  cmp     r13d, [rsp+1B8h+ServicesReturned]
0x18031f327  jnb     loc_18031F791
0x18031f32d  mov     eax, r13d
0x18031f330  imul    rcx, rax, 38h ; '8'
0x18031f334  add     r12, rcx
0x18031f337  lea     rdx, [rsp+1B8h+var_50]
0x18031f33f  mov     rcx, [r12]
0x18031f343  call    ??$regex_search@_WV?$regex_traits@_W@std@@@std@@YA_NPEB_WAEBV?$basic_regex@_WV?$regex_traits@_W@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_search<wchar_t,std::regex_traits<wchar_t>>(wchar_t const *,std::basic_regex<wchar_t,std::regex_traits<wchar_t>> const &,std::regex_constants::match_flag_type)
0x18031f348  test    al, al
0x18031f34a  jz      loc_18031F781
0x18031f350  mov     r8d, 4; dwDesiredAccess
0x18031f356  mov     rdx, [r12]; lpServiceName
0x18031f35a  mov     rcx, rdi; hSCManager
0x18031f35d  call    cs:__imp_OpenServiceW
0x18031f363  mov     rbx, rax
0x18031f366  mov     [rsp+1B8h+var_100], rax
0x18031f36e  test    rax, rax
0x18031f371  jz      loc_18031F67F
0x18031f377  mov     [rsp+1B8h+var_158], 0
0x18031f37f  lea     rax, [rsp+1B8h+var_158]
0x18031f384  mov     [rsp+1B8h+lpServices], rax; pcbBytesNeeded
0x18031f389  xor     r9d, r9d; cbBufSize
0x18031f38c  xor     r8d, r8d; lpBuffer
0x18031f38f  xor     edx, edx; InfoLevel
0x18031f391  mov     rcx, rbx; hService
0x18031f394  call    cs:__imp_QueryServiceStatusEx
0x18031f39a  test    eax, eax
0x18031f39c  jnz     loc_18031F574
0x18031f3a2  call    cs:__imp_GetLastError
0x18031f3a8  cmp     eax, 7Ah ; 'z'
0x18031f3ab  jnz     loc_18031F574
0x18031f3b1  mov     edx, [rsp+1B8h+var_158]
0x18031f3b5  lea     rcx, [rsp+1B8h+lpBuffer]
0x18031f3bd  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x18031f3c2  nop
0x18031f3c3  lea     rax, [rsp+1B8h+var_158]
0x18031f3c8  mov     [rsp+1B8h+lpServices], rax; pcbBytesNeeded
0x18031f3cd  mov     r9d, [rsp+1B8h+var_158]; cbBufSize
0x18031f3d2  mov     r8, [rsp+1B8h+lpBuffer]; lpBuffer
0x18031f3da  xor     edx, edx; InfoLevel
0x18031f3dc  mov     rcx, rbx; hService
0x18031f3df  call    cs:__imp_QueryServiceStatusEx
0x18031f3e5  test    eax, eax
0x18031f3e7  jnz     loc_18031F506
0x18031f3ed  test    rsi, rsi
0x18031f3f0  jz      loc_18031F4F4
0x18031f3f6  call    cs:__imp_GetLastError
0x18031f3fc  mov     ebx, eax
0x18031f3fe  lea     rcx, [rsi+0A8h]; Src
0x18031f405  lea     rdx, aFailedToQueryP_0; "Failed to query PID for service (2), "
0x18031f40c  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f411  mov     rdx, [r12]
0x18031f415  mov     rcx, rax; Src
0x18031f418  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f41d  lea     rdx, a0x; ": 0x"
0x18031f424  mov     rcx, rax; Src
0x18031f427  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f42c  xor     ecx, ecx
0x18031f42e  mov     [rsp+1B8h+var_9E], cx
0x18031f436  mov     [rsp+1B8h+var_F8], r14b
0x18031f43e  movzx   ecx, word ptr [rsp+119h]
0x18031f446  mov     [rsp+1B8h+var_F7], cx
0x18031f44e  mov     cl, byte ptr [rsp+1B8h+var_9E+1]
0x18031f455  mov     [rsp+1B8h+var_F5], cl
0x18031f45c  mov     [rsp+1B8h+var_F4], 200001h
0x18031f467  mov     [rsp+1B8h+var_F0], 0
0x18031f473  lea     rdx, [rsp+1B8h+var_F8]
0x18031f47b  mov     rcx, rax
0x18031f47e  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18031f483  mov     edx, ebx
0x18031f485  mov     rcx, rax; Src
0x18031f488  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x18031f48d  xor     ecx, ecx
0x18031f48f  mov     [rsp+1B8h+var_8E], cx
0x18031f497  mov     [rsp+1B8h+var_E8], r14b
0x18031f49f  movzx   ecx, word ptr [rsp+129h]
0x18031f4a7  mov     [rsp+1B8h+var_E7], cx
0x18031f4af  mov     cl, byte ptr [rsp+1B8h+var_8E+1]
0x18031f4b6  mov     [rsp+1B8h+var_E5], cl
0x18031f4bd  mov     [rsp+1B8h+var_E4], 200000h
0x18031f4c8  mov     [rsp+1B8h+var_E0], 0
0x18031f4d4  lea     rdx, [rsp+1B8h+var_E8]
0x18031f4dc  mov     rcx, rax
0x18031f4df  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18031f4e4  lea     rdx, asc_1803A0C7C; "\r\n"
0x18031f4eb  mov     rcx, rax; Src
0x18031f4ee  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f4f3  nop
0x18031f4f4  lea     rcx, [rsp+1B8h+lpBuffer]
0x18031f4fc  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x18031f501  jmp     loc_18031F774
0x18031f506  mov     rax, [rsp+1B8h+lpBuffer]
0x18031f50e  mov     ebx, [rax+1Ch]
0x18031f511  mov     [rsp+1B8h+var_150], ebx
0x18031f515  mov     r9, r12
0x18031f518  lea     r8, [rsp+1B8h+var_150]
0x18031f51d  lea     rdx, [rsp+1B8h+var_138]
0x18031f525  mov     rcx, [rsp+1B8h+arg_10]
0x18031f52d  call    ??$emplace@AEAKAEAPEA_W@?$_Hash@V?$_Umap_traits@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@$00@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@@1@AEAKAEAPEA_W@Z; std::_Hash<std::_Umap_traits<ulong,std::wstring,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::wstring>>,1>>::emplace<ulong &,wchar_t * &>(ulong &,wchar_t * &)
0x18031f532  test    rsi, rsi
0x18031f535  jz      short loc_18031F4F4
0x18031f537  lea     rcx, [rsi+0A8h]; Src
0x18031f53e  lea     rdx, aFoundPidMatchi; "Found PID matching regex, service '"
0x18031f545  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f54a  mov     rdx, [r12]
0x18031f54e  mov     rcx, rax; Src
0x18031f551  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f556  lea     rdx, asc_1803D8368; "': "
0x18031f55d  mov     rcx, rax; Src
0x18031f560  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f565  mov     edx, ebx
0x18031f567  mov     rcx, rax; Src
0x18031f56a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x18031f56f  jmp     loc_18031F4E4
0x18031f574  test    rsi, rsi
0x18031f577  jz      loc_18031F774
0x18031f57d  call    cs:__imp_GetLastError
0x18031f583  mov     ebx, eax
0x18031f585  lea     rcx, [rsi+0A8h]; Src
0x18031f58c  lea     rdx, aFailedToQueryP; "Failed to query PID for service (1), "
0x18031f593  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f598  mov     rdx, [r12]
0x18031f59c  mov     rcx, rax; Src
0x18031f59f  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f5a4  lea     rdx, a0x; ": 0x"
0x18031f5ab  mov     rcx, rax; Src
0x18031f5ae  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f5b3  xor     ecx, ecx
0x18031f5b5  mov     [rsp+1B8h+var_7E], cx
0x18031f5bd  mov     [rsp+1B8h+var_D8], r14b
0x18031f5c5  movzx   ecx, word ptr [rsp+139h]
0x18031f5cd  mov     [rsp+1B8h+var_D7], cx
0x18031f5d5  mov     cl, byte ptr [rsp+1B8h+var_7E+1]
0x18031f5dc  mov     [rsp+1B8h+var_D5], cl
0x18031f5e3  mov     [rsp+1B8h+var_D4], 200001h
0x18031f5ee  mov     [rsp+1B8h+var_D0], 0
0x18031f5fa  lea     rdx, [rsp+1B8h+var_D8]
0x18031f602  mov     rcx, rax
0x18031f605  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18031f60a  mov     edx, ebx
0x18031f60c  mov     rcx, rax; Src
0x18031f60f  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x18031f614  xor     ecx, ecx
0x18031f616  mov     [rsp+1B8h+var_6E], cx
0x18031f61e  mov     [rsp+1B8h+var_C8], r14b
0x18031f626  movzx   ecx, word ptr [rsp+149h]
0x18031f62e  mov     [rsp+1B8h+var_C7], cx
0x18031f636  mov     cl, byte ptr [rsp+1B8h+var_6E+1]
0x18031f63d  mov     [rsp+1B8h+var_C5], cl
0x18031f644  mov     [rsp+1B8h+var_C4], 200000h
0x18031f64f  mov     [rsp+1B8h+var_C0], 0
0x18031f65b  lea     rdx, [rsp+1B8h+var_C8]
0x18031f663  mov     rcx, rax
0x18031f666  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x18031f66b  lea     rdx, asc_1803A0C7C; "\r\n"
0x18031f672  mov     rcx, rax; Src
0x18031f675  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f67a  jmp     loc_18031F774
0x18031f67f  test    rsi, rsi
0x18031f682  jz      loc_18031F774
0x18031f688  call    cs:__imp_GetLastError
0x18031f68e  mov     ebx, eax
0x18031f690  lea     rcx, [rsi+0A8h]; Src
0x18031f697  lea     rdx, aFailedToOpenSe; "Failed to open service, "
0x18031f69e  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18031f6a3  mov     rdx, [r12]
0x18031f6a7  mov     rcx, rax; Src
0x18031f6aa  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
  ... truncated ...
```
