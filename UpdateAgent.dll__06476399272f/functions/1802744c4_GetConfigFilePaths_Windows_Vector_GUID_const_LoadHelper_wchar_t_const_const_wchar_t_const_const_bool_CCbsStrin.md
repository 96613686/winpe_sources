# GetConfigFilePaths(Windows::Vector<_GUID> const &,LoadHelper &,wchar_t const * const,wchar_t const * const,bool,CCbsStringArray *)

- ea: `0x1802744c4`
- end: `0x18027515d`
- name: `?GetConfigFilePaths@@YAJAEBU?$Vector@U_GUID@@@Windows@@AEAVLoadHelper@@QEB_W2_NPEAVCCbsStringArray@@@Z`
- size: `3225`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18027a59c`
- `0x18027b984`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18000a0e8`
- `0x18000c4c4`
- `0x1800692fc`
- `0x18008b38c`
- `0x18008b3bc`
- `0x1800bd064`
- `0x1800cf56c`
- `0x18014b0c8`
- `0x1801ee64c`
- `0x1801f01e4`
- `0x1801f250c`
- `0x1802744c4`
- `0x180275608`
- `0x180275678`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274c73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274d16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274d9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274f14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274fd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18027509d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274c73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274d16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274d9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274f14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180274fd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18027509d`

## string_xrefs

- `0x180274866`: `UpdateAgent`
- `0x180274df6`: `Failed to create path for config directory`
- `0x180274ad1`: `Microsoft-Windows-Professional-Config,language=neutral,publicKeyToken=31bf3856ad364e35,versionScope=nonSxS,processorArchitecture=amd64`
- `0x180274ca9`: `Failed to create path for host servicing packages dir.`
- `0x180274f67`: `Failed to get component version for professional`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall GetConfigFilePaths(
        struct _GUID **a1,
        LoadHelper *a2,
        __int64 a3,
        __int64 (*a4)(void),
        char a5,
        int *a6)
{
  __int64 (*v6)(void); // r14
  int FunctionPointer; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  struct _GUID *v23; // r15
  __int64 v24; // r12
  LPVOID v25; // rax
  __int64 (*v26)(void); // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  int v32; // esi
  __int128 v33; // kr00_16
  const wchar_t *v34; // rsi
  int ParentPackage; // eax
  int v36; // esi
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rdx
  LPVOID v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rcx
  int v46; // esi
  __int128 v47; // kr10_16
  __int64 v48; // rsi
  int v49; // r14d
  const struct std::nothrow_t *v50; // rdx
  const struct std::nothrow_t *v51; // rdx
  __int64 v52; // rdx
  const struct std::nothrow_t *v53; // rdx
  __int64 v54; // rdx
  const struct std::nothrow_t *v55; // rdx
  unsigned int v56; // edi
  const struct std::nothrow_t *v57; // rdx
  __int64 v58; // rdx
  const struct std::nothrow_t *v59; // rdx
  __int64 v60; // rdx
  const struct std::nothrow_t *v61; // rdx
  __int64 (**v63)(void); // [rsp+28h] [rbp-E0h]
  __int64 (**v64)(void); // [rsp+28h] [rbp-E0h]
  int *v65; // [rsp+28h] [rbp-E0h]
  __int64 (*v66)(void); // [rsp+48h] [rbp-C0h] BYREF
  int *v67; // [rsp+50h] [rbp-B8h] BYREF
  struct _GUID v68; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v69; // [rsp+68h] [rbp-A0h] BYREF
  const wchar_t *v70; // [rsp+78h] [rbp-90h]
  wchar_t *v71[2]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v72; // [rsp+90h] [rbp-78h]
  __int64 v73; // [rsp+98h] [rbp-70h] BYREF
  __int64 v74; // [rsp+A0h] [rbp-68h]
  __int64 v75; // [rsp+A8h] [rbp-60h]
  __int64 v76; // [rsp+B0h] [rbp-58h]
  __int64 v77; // [rsp+B8h] [rbp-50h]
  const wchar_t *v78; // [rsp+C0h] [rbp-48h]
  __int64 v79; // [rsp+C8h] [rbp-40h]
  __int64 v80; // [rsp+D0h] [rbp-38h]
  LPVOID v81; // [rsp+D8h] [rbp-30h]
  __int64 v82; // [rsp+E8h] [rbp-20h]
  __int64 v83; // [rsp+F0h] [rbp-18h]
  __int64 v84; // [rsp+F8h] [rbp-10h]
  int v85; // [rsp+100h] [rbp-8h] BYREF
  __int64 v86; // [rsp+108h] [rbp+0h] BYREF
  LPVOID pv; // [rsp+110h] [rbp+8h]
  __int64 v88; // [rsp+118h] [rbp+10h] BYREF
  __int64 (*v89)(void); // [rsp+120h] [rbp+18h] BYREF
  __int64 v90; // [rsp+128h] [rbp+20h] BYREF
  int v91[2]; // [rsp+130h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+180h] [rbp+78h]

  v82 = -2;
  v6 = a4;
  v89 = a4;
  v67 = a6;
  v83 = 0;
  v84 = 0;
  v66 = 0;
  FunctionPointer = LoadHelper::GetFunctionPointer(a2, "GetIServicingStore", &v66);
  v11 = FunctionPointer;
  if ( FunctionPointer < 0 )
  {
    v85 = FunctionPointer;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to get address of function GetIServicingStore.");
      v66 = (__int64 (*)(void))&v85;
      v63 = &v66;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v12,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53C,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v11,
      (int)v63);
    return v11;
  }
  v88 = 0;
  v13 = ((__int64 (__fastcall *)(__int64 *))v66)(&v88);
  v11 = v13;
  if ( v13 < 0 )
  {
    v85 = v13;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get IServicingStore.");
      v66 = (__int64 (*)(void))&v85;
      v63 = &v66;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v14,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53F,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v11,
      (int)v63);
    if ( v88 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    return v11;
  }
  LODWORD(v64) = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v88 + 24LL))(v88, 4, 0);
  v11 = v15;
  if ( v15 < 0 )
  {
    v85 = v15;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to initialize IServicingStore.");
      v66 = (__int64 (*)(void))&v85;
      v64 = &v66;
      LOBYTE(v16) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v16,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x546,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v11,
      (int)v64);
    if ( v88 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    return v11;
  }
  v66 = 0;
  v17 = LoadHelper::GetFunctionPointer(a2, "GetIServicingQuerier", &v66);
  v11 = v17;
  if ( v17 < 0 )
  {
    v85 = v17;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to get address of function GetIServicingQuerier.");
      v66 = (__int64 (*)(void))&v85;
      v64 = &v66;
      LOBYTE(v18) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v18,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54A,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v11,
      (int)v64);
    if ( v88 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    return v11;
  }
  v86 = 0;
  v19 = ((__int64 (__fastcall *)(__int64 *))v66)(&v86);
  v11 = v19;
  if ( v19 < 0 )
  {
    v85 = v19;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get IServicingQuerier.");
      v66 = (__int64 (*)(void))&v85;
      v64 = &v66;
      LOBYTE(v20) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v20,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54E,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v11,
      (int)v64);
    if ( v86 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
      v86 = 0;
    }
    if ( v88 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    return v11;
  }
  LODWORD(v65) = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, const OLECHAR *, __int64))(*(_QWORD *)v86 + 24LL))(
          v86,
          0,
          L"UpdateAgent",
          v88);
  v11 = v21;
  if ( v21 < 0 )
  {
    v85 = v21;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to initialize IServicingQuerier.");
      v67 = &v85;
      v65 = (int *)&v67;
      LOBYTE(v22) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v22,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x551,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v11,
      (int)v65);
    if ( v86 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
      v86 = 0;
    }
    if ( v88 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    return v11;
  }
  v23 = *a1;
  v24 = (__int64)&(*a1)[(_QWORD)a1[1]];
  if ( *a1 == (struct _GUID *)v24 )
  {
LABEL_162:
    if ( v86 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
      v86 = 0;
    }
    if ( v88 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    return 0;
  }
  while ( 1 )
  {
    *(_QWORD *)v91 = 0;
    v25 = 0;
    pv = 0;
    v26 = 0;
    v66 = 0;
    if ( a5 )
      goto LABEL_58;
    v69 = 0;
    v70 = 0;
    if ( a3 )
    {
      v27 = -1;
      do
        ++v27;
      while ( *(_WORD *)(a3 + 2 * v27) );
      v28 = 2 * v27;
      v29 = a3;
      v30 = v28 + 2;
    }
    else
    {
      v29 = 0;
      v28 = 0;
      v30 = 0;
    }
    v73 = v28;
    v74 = v30;
    v75 = v29;
    v76 = 36;
    v77 = 38;
    v78 = L"Servicing\\Packages";
    v32 = RtlCombineNtPathSegments(2, &v73, &v69);
    if ( v32 < 0 )
      goto LABEL_89;
    v33 = v69;
    if ( *((_QWORD *)&v69 + 1) - (_QWORD)v69 < 2u )
      break;
LABEL_51:
    v34 = v70;
    *(const wchar_t *)((char *)v70 + (v33 & 0xFFFFFFFFFFFFFFFEuLL)) = 0;
    if ( v34 && (*((_QWORD *)&v33 + 1) - (_QWORD)v33 < 2u || v34[(unsigned __int64)v33 >> 1]) )
      goto LABEL_168;
    v68 = *v23;
    ParentPackage = GetParentPackage(&v68, v34, (struct AutoScz *)&v66);
    v11 = ParentPackage;
    if ( ParentPackage < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x566,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)(unsigned int)ParentPackage,
        (int)v65);
      if ( v34 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v34);
      if ( v66 )
        operator delete((char *)v66 - 8, v53);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v86 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
        v86 = 0;
      }
      if ( v88 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      return v11;
    }
    v26 = v66;
    v6 = v66;
    if ( v34 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v34);
    v25 = pv;
LABEL_58:
    if ( *(_QWORD *)&v23->Data1 != CMS_CLIENT_PROFESSIONAL_LAYER_ID || *(_QWORD *)v23->Data4 != 0xBC13D37997636694uLL )
    {
      v49 = -2147418113;
      LODWORD(v90) = -2147418113;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Unsupported layer");
        *(_QWORD *)&v68.Data1 = &v90;
        v65 = (int *)&v68;
        LOBYTE(v60) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v60,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x577,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)0x8000FFFFLL,
        (int)v65);
      if ( v26 )
        operator delete((char *)v26 - 8, v61);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v86 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
        v86 = 0;
      }
      if ( v88 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      return (unsigned int)v49;
    }
    if ( v25 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
LABEL_168:
      INTERNAL_ERROR_ACTION(-1073741595);
LABEL_169:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18027515CLL);
    }
    v65 = v91;
    v36 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (*)(void), const wchar_t *))(*(_QWORD *)v86 + 56LL))(
            v86,
            1,
            v6,
            L"Microsoft-Windows-Professional-Config,language=neutral,publicKeyToken=31bf3856ad364e35,versionScope=nonSxS,p"
             "rocessorArchitecture=amd64");
    if ( v36 < 0 )
    {
      LODWORD(v89) = v36;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to get component version for professional");
        *(_QWORD *)&v68.Data1 = &v89;
        v65 = (int *)&v68;
        LOBYTE(v58) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v58,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x573,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)(unsigned int)v36,
        (int)v65);
      if ( v26 )
        operator delete((char *)v26 - 8, v59);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v86 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
        v86 = 0;
      }
      if ( v88 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      return (unsigned int)v36;
    }
    *(_OWORD *)v71 = 0;
    v72 = 0;
    if ( a3 )
    {
      v37 = -1;
      do
        ++v37;
      while ( *(_WORD *)(a3 + 2 * v37) );
      v38 = 2 * v37;
      v39 = a3;
      v40 = v38 + 2;
    }
    else
    {
      v39 = 0;
      v38 = 0;
      v40 = 0;
    }
    v73 = v38;
    v74 = v40;
    v75 = v39;
    v76 = 12;
    v77 = 14;
    v78 = L"Winsxs";
    v41 = pv;
    if ( pv )
    {
      v42 = -1;
      do
        ++v42;
      while ( *((_WORD *)pv + v42) );
      v43 = 2 * v42;
      v44 = v43 + 2;
    }
    else
    {
      v41 = 0;
      v43 = 0;
      v44 = 0;
    }
    v79 = v43;
    v80 = v44;
    v81 = v41;
    v46 = RtlCombineNtPathSegments(3, &v73, v71);
    if ( v46 < 0 )
      goto LABEL_112;
    v47 = *(_OWORD *)v71;
    if ( (wchar_t *)((char *)v71[1] - (char *)v71[0]) < (wchar_t *)2 )
    {
      if ( v71[0] + 1 < v71[0] )
      {
        v46 = -1073741675;
LABEL_112:
        LODWORD(v89) = v46;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to create path for config directory");
          *(_QWORD *)&v68.Data1 = &v89;
          v65 = (int *)&v68;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v54,
            3,
            ": {}");
        }
        v56 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x57D,
                (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                (const char *)(unsigned int)v46,
                (int)v65);
        if ( v72 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v72);
        if ( v26 )
          operator delete((char *)v26 - 8, v55);
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v86 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
          v86 = 0;
        }
        if ( v88 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
        return v56;
      }
      v46 = RtlReallocateLUnicodeString(v45, v71[0] + 1, v71);
      if ( v46 < 0 )
        goto LABEL_112;
      v47 = *(_OWORD *)v71;
    }
    v48 = v72;
    *(_WORD *)((v47 & 0xFFFFFFFFFFFFFFFEuLL) + v72) = 0;
    if ( !v48 )
    {
      v49 = -2147024809;
      goto LABEL_128;
    }
    if ( *((_QWORD *)&v47 + 1) - (_QWORD)v47 < 2u || *(_WORD *)(v48 + 2 * ((unsigned __int64)v47 >> 1)) )
      goto LABEL_169;
    v90 = 0;
    v49 = SczAllocFromSz(&v90, v48);
    if ( v49 < 0 )
      goto LABEL_128;
    v49 = CCbsArrayBase<wchar_t *,CCbsStringArray>::Add(v67, &v90);
    if ( v49 < 0 )
    {
      if ( v90 )
        operator delete((void *)(v90 - 8), v50);
LABEL_128:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57F,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)(unsigned int)v49,
        (int)v91);
      if ( v48 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v48);
      if ( v26 )
        operator delete((char *)v26 - 8, v57);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v86 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
        v86 = 0;
      }
      if ( v88 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
      return (unsigned int)v49;
    }
    anonymous_namespace_::OurRtlFreeStringRoutine(v48);
    if ( v26 )
      operator delete((char *)v26 - 8, v51);
    if ( pv )
      CoTaskMemFree(pv);
    if ( ++v23 == (struct _GUID *)v24 )
      goto LABEL_162;
    v6 = v89;
  }
  if ( (__int64)v69 + 2 >= (unsigned __int64)v69 )
  {
    v32 = RtlReallocateLUnicodeString(v31, v69 + 2, &v69);
    if ( v32 < 0 )
      goto LABEL_89;
    v33 = v69;
    goto LABEL_51;
  }
  v32 = -1073741675;
LABEL_89:
  v85 = v32;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "Failed to create path for host servicing packages dir.");
    v67 = &v85;
    v65 = (int *)&v67;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v52,
      3,
      ": {}");
  }
  v11 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x564,
          (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
          (const char *)(unsigned int)v32,
          (int)v65);
  if ( v70 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v70);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v86 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
    v86 = 0;
  }
  if ( v88 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
  return v11;
}

```

## disassembly

```asm
0x1802744c4  mov     rax, rsp
0x1802744c7  push    rbp
0x1802744c8  push    rsi
0x1802744c9  push    rdi
0x1802744ca  push    r12
0x1802744cc  push    r13
0x1802744ce  push    r14
0x1802744d0  push    r15
0x1802744d2  lea     rbp, [rax-78h]
0x1802744d6  sub     rsp, 140h
0x1802744dd  mov     [rbp+70h+var_90], 0FFFFFFFFFFFFFFFEh
0x1802744e5  mov     [rax+18h], rbx
0x1802744e9  mov     rax, cs:__security_cookie
0x1802744f0  xor     rax, rsp
0x1802744f3  mov     [rbp+70h+var_40], rax
0x1802744f7  mov     r14, r9
0x1802744fa  mov     [rbp+70h+var_58], r9
0x1802744fe  mov     r13, r8
0x180274501  mov     rsi, rdx
0x180274504  mov     rdi, rcx
0x180274507  mov     rax, [rbp+70h+arg_28]
0x18027450e  mov     qword ptr [rsp+170h+var_128.Data1], rax
0x180274513  xor     r15d, r15d
0x180274516  mov     [rbp+70h+var_88], r15
0x18027451a  mov     [rbp+70h+var_80], r15
0x18027451e  mov     [rsp+170h+var_130], r15
0x180274523  lea     r8, [rsp+170h+var_130]; __int64 (**)(void)
0x180274528  lea     rdx, aGetiservicings; "GetIServicingStore"
0x18027452f  mov     rcx, rsi; this
0x180274532  call    ?GetFunctionPointer@LoadHelper@@QEAAJQEBDPEAP6A_JXZ@Z; LoadHelper::GetFunctionPointer(char const * const,__int64 (**)(void))
0x180274537  mov     ebx, eax
0x180274539  test    eax, eax
0x18027453b  jns     short loc_1802745A9
0x18027453d  mov     [rbp+70h+var_78], eax
0x180274540  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180274547  test    rcx, rcx
0x18027454a  jz      short loc_18027458C
0x18027454c  lea     r9, aFailedToGetAdd_0; "Failed to get address of function GetIS"...
0x180274553  lea     edi, [r15+3]
0x180274557  mov     r8d, edi
0x18027455a  xor     edx, edx
0x18027455c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180274561  lea     rax, [rbp+70h+var_78]
0x180274565  mov     [rsp+170h+var_130], rax
0x18027456a  lea     rax, [rsp+170h+var_130]
0x18027456f  mov     qword ptr [rsp+170h+var_150], rax; int
0x180274574  lea     r9, asc_1802C6678; ": {}"
0x18027457b  mov     r8d, edi
0x18027457e  mov     dl, 1
0x180274580  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180274587  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18027458c  mov     rcx, [rbp+78h]; this
0x180274590  mov     r9d, ebx; char *
0x180274593  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x18027459a  mov     edx, 53Ch; void *
0x18027459f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802745a4  jmp     loc_1802750DF
0x1802745a9  mov     [rbp+70h+var_60], r15
0x1802745ad  lea     rcx, [rbp+70h+var_60]
0x1802745b1  mov     rax, [rsp+170h+var_130]
0x1802745b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802745bb  mov     ebx, eax
0x1802745bd  test    eax, eax
0x1802745bf  jns     loc_180274649
0x1802745c5  mov     [rbp+70h+var_78], eax
0x1802745c8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802745cf  test    rcx, rcx
0x1802745d2  jz      short loc_180274615
0x1802745d4  lea     r9, aFailedToGetIse; "Failed to get IServicingStore."
0x1802745db  mov     edi, 3
0x1802745e0  mov     r8d, edi
0x1802745e3  xor     edx, edx
0x1802745e5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802745ea  lea     rax, [rbp+70h+var_78]
0x1802745ee  mov     [rsp+170h+var_130], rax
0x1802745f3  lea     rax, [rsp+170h+var_130]
0x1802745f8  mov     qword ptr [rsp+170h+var_150], rax; int
0x1802745fd  lea     r9, asc_1802C6678; ": {}"
0x180274604  mov     r8d, edi
0x180274607  mov     dl, 1
0x180274609  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180274610  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180274615  mov     rcx, [rbp+78h]; this
0x180274619  mov     r9d, ebx; char *
0x18027461c  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x180274623  mov     edx, 53Fh; void *
0x180274628  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027462d  nop
0x18027462e  mov     rcx, [rbp+70h+var_60]
0x180274632  test    rcx, rcx
0x180274635  jz      short loc_180274644
0x180274637  mov     rax, [rcx]
0x18027463a  mov     rax, [rax+10h]
0x18027463e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274643  nop
0x180274644  jmp     loc_1802750DF
0x180274649  mov     rcx, [rbp+70h+var_60]
0x18027464d  mov     rax, [rcx]
0x180274650  mov     qword ptr [rsp+170h+var_150], r15
0x180274655  xor     r9d, r9d
0x180274658  xor     r8d, r8d
0x18027465b  lea     edx, [r9+4]
0x18027465f  mov     rax, [rax+18h]
0x180274663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274668  mov     ebx, eax
0x18027466a  test    eax, eax
0x18027466c  jns     loc_1802746F6
0x180274672  mov     [rbp+70h+var_78], eax
0x180274675  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027467c  test    rcx, rcx
0x18027467f  jz      short loc_1802746C2
0x180274681  lea     r9, aFailedToInitia_0; "Failed to initialize IServicingStore."
0x180274688  mov     edi, 3
0x18027468d  mov     r8d, edi
0x180274690  xor     edx, edx
0x180274692  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180274697  lea     rax, [rbp+70h+var_78]
0x18027469b  mov     [rsp+170h+var_130], rax
0x1802746a0  lea     rax, [rsp+170h+var_130]
0x1802746a5  mov     qword ptr [rsp+170h+var_150], rax; int
0x1802746aa  lea     r9, asc_1802C6678; ": {}"
0x1802746b1  mov     r8d, edi
0x1802746b4  mov     dl, 1
0x1802746b6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802746bd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802746c2  mov     rcx, [rbp+78h]; this
0x1802746c6  mov     r9d, ebx; char *
0x1802746c9  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x1802746d0  mov     edx, 546h; void *
0x1802746d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802746da  nop
0x1802746db  mov     rcx, [rbp+70h+var_60]
0x1802746df  test    rcx, rcx
0x1802746e2  jz      short loc_1802746F1
0x1802746e4  mov     rax, [rcx]
0x1802746e7  mov     rax, [rax+10h]
0x1802746eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802746f0  nop
0x1802746f1  jmp     loc_1802750DF
0x1802746f6  mov     [rsp+170h+var_130], r15
0x1802746fb  lea     r8, [rsp+170h+var_130]; __int64 (**)(void)
0x180274700  lea     rdx, aGetiservicingq; "GetIServicingQuerier"
0x180274707  mov     rcx, rsi; this
0x18027470a  call    ?GetFunctionPointer@LoadHelper@@QEAAJQEBDPEAP6A_JXZ@Z; LoadHelper::GetFunctionPointer(char const * const,__int64 (**)(void))
0x18027470f  mov     ebx, eax
0x180274711  xor     esi, esi
0x180274713  test    eax, eax
0x180274715  jns     loc_18027479D
0x18027471b  mov     [rbp+70h+var_78], eax
0x18027471e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180274725  test    rcx, rcx
0x180274728  jz      short loc_180274769
0x18027472a  lea     r9, aFailedToGetAdd_25; "Failed to get address of function GetIS"...
0x180274731  lea     edi, [rsi+3]
0x180274734  mov     r8d, edi
0x180274737  xor     edx, edx
0x180274739  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18027473e  lea     rax, [rbp+70h+var_78]
0x180274742  mov     [rsp+170h+var_130], rax
0x180274747  lea     rax, [rsp+170h+var_130]
0x18027474c  mov     qword ptr [rsp+170h+var_150], rax; int
0x180274751  lea     r9, asc_1802C6678; ": {}"
0x180274758  mov     r8d, edi
0x18027475b  mov     dl, 1
0x18027475d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180274764  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180274769  mov     rcx, [rbp+78h]; this
0x18027476d  mov     r9d, ebx; char *
0x180274770  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x180274777  mov     edx, 54Ah; void *
0x18027477c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180274781  nop
0x180274782  mov     rcx, [rbp+70h+var_60]
0x180274786  test    rcx, rcx
0x180274789  jz      short loc_180274798
0x18027478b  mov     rax, [rcx]
0x18027478e  mov     rax, [rax+10h]
0x180274792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274797  nop
0x180274798  jmp     loc_1802750DF
0x18027479d  mov     [rbp+70h+var_70], rsi
0x1802747a1  lea     rcx, [rbp+70h+var_70]
0x1802747a5  mov     rax, [rsp+170h+var_130]
0x1802747aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802747af  mov     ebx, eax
0x1802747b1  test    eax, eax
0x1802747b3  jns     loc_180274856
0x1802747b9  mov     [rbp+70h+var_78], eax
0x1802747bc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802747c3  test    rcx, rcx
0x1802747c6  jz      short loc_180274809
0x1802747c8  lea     r9, aFailedToGetIse_0; "Failed to get IServicingQuerier."
0x1802747cf  mov     edi, 3
0x1802747d4  mov     r8d, edi
0x1802747d7  xor     edx, edx
0x1802747d9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802747de  lea     rax, [rbp+70h+var_78]
0x1802747e2  mov     [rsp+170h+var_130], rax
0x1802747e7  lea     rax, [rsp+170h+var_130]
0x1802747ec  mov     qword ptr [rsp+170h+var_150], rax; int
0x1802747f1  lea     r9, asc_1802C6678; ": {}"
0x1802747f8  mov     r8d, edi
0x1802747fb  mov     dl, 1
0x1802747fd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180274804  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180274809  mov     rcx, [rbp+78h]; this
0x18027480d  mov     r9d, ebx; char *
0x180274810  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x180274817  mov     edx, 54Eh; void *
0x18027481c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180274821  nop
0x180274822  mov     rcx, [rbp+70h+var_70]
0x180274826  test    rcx, rcx
0x180274829  jz      short loc_18027483B
0x18027482b  mov     rax, [rcx]
0x18027482e  mov     rax, [rax+10h]
0x180274832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274837  mov     [rbp+70h+var_70], rsi
0x18027483b  mov     rcx, [rbp+70h+var_60]
0x18027483f  test    rcx, rcx
0x180274842  jz      short loc_180274851
0x180274844  mov     rax, [rcx]
0x180274847  mov     rax, [rax+10h]
0x18027484b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274850  nop
0x180274851  jmp     loc_1802750DF
0x180274856  mov     rcx, [rbp+70h+var_70]
0x18027485a  mov     rax, [rcx]
0x18027485d  mov     qword ptr [rsp+170h+var_150], rsi; int
0x180274862  mov     r9, [rbp+70h+var_60]
0x180274866  lea     r8, aUpdateagent; "UpdateAgent"
0x18027486d  xor     edx, edx
0x18027486f  mov     rax, [rax+18h]
0x180274873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274878  mov     ebx, eax
0x18027487a  test    eax, eax
0x18027487c  jns     loc_18027491F
0x180274882  mov     [rbp+70h+var_78], eax
0x180274885  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027488c  test    rcx, rcx
0x18027488f  jz      short loc_1802748D2
0x180274891  lea     r9, aFailedToInitia; "Failed to initialize IServicingQuerier."
0x180274898  mov     edi, 3
0x18027489d  mov     r8d, edi
0x1802748a0  xor     edx, edx
0x1802748a2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802748a7  lea     rax, [rbp+70h+var_78]
0x1802748ab  mov     qword ptr [rsp+170h+var_128.Data1], rax
0x1802748b0  lea     rax, [rsp+170h+var_128]
0x1802748b5  mov     qword ptr [rsp+170h+var_150], rax; int
0x1802748ba  lea     r9, asc_1802C6678; ": {}"
0x1802748c1  mov     r8d, edi
0x1802748c4  mov     dl, 1
0x1802748c6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802748cd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802748d2  mov     rcx, [rbp+78h]; this
0x1802748d6  mov     r9d, ebx; char *
0x1802748d9  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x1802748e0  mov     edx, 551h; void *
0x1802748e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802748ea  nop
0x1802748eb  mov     rcx, [rbp+70h+var_70]
0x1802748ef  test    rcx, rcx
0x1802748f2  jz      short loc_180274904
0x1802748f4  mov     rax, [rcx]
0x1802748f7  mov     rax, [rax+10h]
0x1802748fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274900  mov     [rbp+70h+var_70], rsi
0x180274904  mov     rcx, [rbp+70h+var_60]
0x180274908  test    rcx, rcx
0x18027490b  jz      short loc_18027491A
0x18027490d  mov     rax, [rcx]
0x180274910  mov     rax, [rax+10h]
0x180274914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180274919  nop
0x18027491a  jmp     loc_1802750DF
0x18027491f  mov     r15, [rdi]
0x180274922  mov     r12, [rdi+8]
0x180274926  shl     r12, 4
0x18027492a  add     r12, r15
0x18027492d  cmp     r15, r12
0x180274930  jz      loc_1802750E3
0x180274936  mov     edi, 3
0x18027493b  mov     qword ptr [rbp+70h+var_48], rsi
0x18027493f  mov     rax, rsi
0x180274942  mov     [rbp+70h+pv], rax
0x180274946  mov     rbx, rsi
0x180274949  mov     [rsp+170h+var_130], rbx
0x18027494e  cmp     [rbp+70h+arg_20], sil
0x180274955  jnz     loc_180274A8E
0x18027495b  xorps   xmm0, xmm0
0x18027495e  xor     eax, eax
0x180274960  movups  [rsp+170h+var_118+8], xmm0
0x180274965  mov     [rsp+170h+var_100], rax
0x18027496a  test    r13, r13
0x18027496d  jz      short loc_18027498A
0x18027496f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180274973  inc     rax
0x180274976  cmp     [r13+rax*2+0], si
0x18027497c  jnz     short loc_180274973
  ... truncated ...
```
