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
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  struct _GUID *v17; // r15
  __int64 v18; // r12
  LPVOID v19; // rax
  __int64 (*v20)(void); // rbx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // esi
  __int128 v27; // kr00_16
  const wchar_t *v28; // rsi
  int ParentPackage; // eax
  int v30; // esi
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rdx
  LPVOID v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  int v40; // esi
  __int128 v41; // kr10_16
  __int64 v42; // rsi
  int v43; // r14d
  const struct std::nothrow_t *v44; // rdx
  const struct std::nothrow_t *v45; // rdx
  __int64 v46; // rdx
  const struct std::nothrow_t *v47; // rdx
  __int64 v48; // rdx
  const struct std::nothrow_t *v49; // rdx
  unsigned int v50; // edi
  const struct std::nothrow_t *v51; // rdx
  const struct std::nothrow_t *v52; // rdx
  const struct std::nothrow_t *v53; // rdx
  int v55; // [rsp+28h] [rbp-E0h]
  int v56; // [rsp+28h] [rbp-E0h]
  int *v57; // [rsp+28h] [rbp-E0h]
  __int64 (*v58)(void); // [rsp+48h] [rbp-C0h] BYREF
  int *v59; // [rsp+50h] [rbp-B8h] BYREF
  struct _GUID v60; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v61; // [rsp+68h] [rbp-A0h] BYREF
  const wchar_t *v62; // [rsp+78h] [rbp-90h]
  wchar_t *v63[2]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v64; // [rsp+90h] [rbp-78h]
  __int64 v65; // [rsp+98h] [rbp-70h] BYREF
  __int64 v66; // [rsp+A0h] [rbp-68h]
  __int64 v67; // [rsp+A8h] [rbp-60h]
  __int64 v68; // [rsp+B0h] [rbp-58h]
  __int64 v69; // [rsp+B8h] [rbp-50h]
  const wchar_t *v70; // [rsp+C0h] [rbp-48h]
  __int64 v71; // [rsp+C8h] [rbp-40h]
  __int64 v72; // [rsp+D0h] [rbp-38h]
  LPVOID v73; // [rsp+D8h] [rbp-30h]
  __int64 v74; // [rsp+E8h] [rbp-20h]
  __int64 v75; // [rsp+F0h] [rbp-18h]
  __int64 v76; // [rsp+F8h] [rbp-10h]
  int v77; // [rsp+100h] [rbp-8h] BYREF
  __int64 v78; // [rsp+108h] [rbp+0h] BYREF
  LPVOID pv; // [rsp+110h] [rbp+8h]
  __int64 v80; // [rsp+118h] [rbp+10h] BYREF
  __int64 (*v81)(void); // [rsp+120h] [rbp+18h] BYREF
  __int64 v82; // [rsp+128h] [rbp+20h] BYREF
  int v83[2]; // [rsp+130h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+180h] [rbp+78h]

  v74 = -2;
  v6 = a4;
  v81 = a4;
  v59 = a6;
  v75 = 0;
  v76 = 0;
  v58 = 0;
  FunctionPointer = LoadHelper::GetFunctionPointer(a2, "GetIServicingStore", &v58);
  v11 = FunctionPointer;
  if ( FunctionPointer < 0 )
  {
    v77 = FunctionPointer;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get address of function GetIServicingStore.");
      v58 = (__int64 (*)(void))&v77;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v58);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53C,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v11,
      v55);
    return v11;
  }
  v80 = 0;
  v12 = ((__int64 (__fastcall *)(__int64 *))v58)(&v80);
  v11 = v12;
  if ( v12 < 0 )
  {
    v77 = v12;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get IServicingStore.");
      v58 = (__int64 (*)(void))&v77;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v58);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53F,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v11,
      v55);
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    return v11;
  }
  v56 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v80 + 24LL))(v80, 4, 0);
  v11 = v13;
  if ( v13 < 0 )
  {
    v77 = v13;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to initialize IServicingStore.");
      v58 = (__int64 (*)(void))&v77;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v58);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x546,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v11,
      v56);
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    return v11;
  }
  v58 = 0;
  v14 = LoadHelper::GetFunctionPointer(a2, "GetIServicingQuerier", &v58);
  v11 = v14;
  if ( v14 < 0 )
  {
    v77 = v14;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get address of function GetIServicingQuerier.");
      v58 = (__int64 (*)(void))&v77;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v58);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54A,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v11,
      v56);
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    return v11;
  }
  v78 = 0;
  v15 = ((__int64 (__fastcall *)(__int64 *))v58)(&v78);
  v11 = v15;
  if ( v15 < 0 )
  {
    v77 = v15;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get IServicingQuerier.");
      v58 = (__int64 (*)(void))&v77;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v58);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54E,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v11,
      v56);
    if ( v78 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      v78 = 0;
    }
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    return v11;
  }
  LODWORD(v57) = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, const OLECHAR *, __int64))(*(_QWORD *)v78 + 24LL))(
          v78,
          0,
          L"UpdateAgent",
          v80);
  v11 = v16;
  if ( v16 < 0 )
  {
    v77 = v16;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to initialize IServicingQuerier.");
      v59 = &v77;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)&v59);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x551,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v11,
      (int)v57);
    if ( v78 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      v78 = 0;
    }
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    return v11;
  }
  v17 = *a1;
  v18 = (__int64)&(*a1)[(_QWORD)a1[1]];
  if ( *a1 == (struct _GUID *)v18 )
  {
LABEL_162:
    if ( v78 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      v78 = 0;
    }
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    return 0;
  }
  while ( 1 )
  {
    *(_QWORD *)v83 = 0;
    v19 = 0;
    pv = 0;
    v20 = 0;
    v58 = 0;
    if ( a5 )
      goto LABEL_58;
    v61 = 0;
    v62 = 0;
    if ( a3 )
    {
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)(a3 + 2 * v21) );
      v22 = 2 * v21;
      v23 = a3;
      v24 = v22 + 2;
    }
    else
    {
      v23 = 0;
      v22 = 0;
      v24 = 0;
    }
    v65 = v22;
    v66 = v24;
    v67 = v23;
    v68 = 36;
    v69 = 38;
    v70 = L"Servicing\\Packages";
    v26 = RtlCombineNtPathSegments(2, &v65, &v61);
    if ( v26 < 0 )
      goto LABEL_89;
    v27 = v61;
    if ( *((_QWORD *)&v61 + 1) - (_QWORD)v61 < 2u )
      break;
LABEL_51:
    v28 = v62;
    *(const wchar_t *)((char *)v62 + (v27 & 0xFFFFFFFFFFFFFFFEuLL)) = 0;
    if ( v28 && (*((_QWORD *)&v27 + 1) - (_QWORD)v27 < 2u || v28[(unsigned __int64)v27 >> 1]) )
      goto LABEL_168;
    v60 = *v17;
    ParentPackage = GetParentPackage(&v60, v28, (struct AutoScz *)&v58);
    v11 = ParentPackage;
    if ( ParentPackage < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x566,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)(unsigned int)ParentPackage,
        (int)v57);
      if ( v28 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v28);
      if ( v58 )
        operator delete((char *)v58 - 8, v47);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v78 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
      }
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      return v11;
    }
    v20 = v58;
    v6 = v58;
    if ( v28 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v28);
    v19 = pv;
LABEL_58:
    if ( *(_QWORD *)&v17->Data1 != CMS_CLIENT_PROFESSIONAL_LAYER_ID || *(_QWORD *)v17->Data4 != 0xBC13D37997636694uLL )
    {
      v43 = -2147418113;
      LODWORD(v82) = -2147418113;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unsupported layer");
        *(_QWORD *)&v60.Data1 = &v82;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&v60);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x577,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)0x8000FFFFLL,
        (int)v57);
      if ( v20 )
        operator delete((char *)v20 - 8, v53);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v78 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
      }
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      return (unsigned int)v43;
    }
    if ( v19 )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
LABEL_168:
      INTERNAL_ERROR_ACTION(-1073741595);
LABEL_169:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18027515CLL);
    }
    v57 = v83;
    v30 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (*)(void), const wchar_t *))(*(_QWORD *)v78 + 56LL))(
            v78,
            1,
            v6,
            L"Microsoft-Windows-Professional-Config,language=neutral,publicKeyToken=31bf3856ad364e35,versionScope=nonSxS,p"
             "rocessorArchitecture=amd64");
    if ( v30 < 0 )
    {
      LODWORD(v81) = v30;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get component version for professional");
        *(_QWORD *)&v60.Data1 = &v81;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&v60);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x573,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)(unsigned int)v30,
        (int)v57);
      if ( v20 )
        operator delete((char *)v20 - 8, v52);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v78 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
      }
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      return (unsigned int)v30;
    }
    *(_OWORD *)v63 = 0;
    v64 = 0;
    if ( a3 )
    {
      v31 = -1;
      do
        ++v31;
      while ( *(_WORD *)(a3 + 2 * v31) );
      v32 = 2 * v31;
      v33 = a3;
      v34 = v32 + 2;
    }
    else
    {
      v33 = 0;
      v32 = 0;
      v34 = 0;
    }
    v65 = v32;
    v66 = v34;
    v67 = v33;
    v68 = 12;
    v69 = 14;
    v70 = L"Winsxs";
    v35 = pv;
    if ( pv )
    {
      v36 = -1;
      do
        ++v36;
      while ( *((_WORD *)pv + v36) );
      v37 = 2 * v36;
      v38 = v37 + 2;
    }
    else
    {
      v35 = 0;
      v37 = 0;
      v38 = 0;
    }
    v71 = v37;
    v72 = v38;
    v73 = v35;
    v40 = RtlCombineNtPathSegments(3, &v65, v63);
    if ( v40 < 0 )
      goto LABEL_112;
    v41 = *(_OWORD *)v63;
    if ( (wchar_t *)((char *)v63[1] - (char *)v63[0]) < (wchar_t *)2 )
    {
      if ( v63[0] + 1 < v63[0] )
      {
        v40 = -1073741675;
LABEL_112:
        LODWORD(v81) = v40;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create path for config directory");
          *(_QWORD *)&v60.Data1 = &v81;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            v48,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
            (__int64)&v60);
        }
        v50 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x57D,
                (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
                (const char *)(unsigned int)v40,
                (int)v57);
        if ( v64 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v64);
        if ( v20 )
          operator delete((char *)v20 - 8, v49);
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v78 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
          v78 = 0;
        }
        if ( v80 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
        return v50;
      }
      v40 = RtlReallocateLUnicodeString(v39, v63[0] + 1, v63);
      if ( v40 < 0 )
        goto LABEL_112;
      v41 = *(_OWORD *)v63;
    }
    v42 = v64;
    *(_WORD *)((v41 & 0xFFFFFFFFFFFFFFFEuLL) + v64) = 0;
    if ( !v42 )
    {
      v43 = -2147024809;
      goto LABEL_128;
    }
    if ( *((_QWORD *)&v41 + 1) - (_QWORD)v41 < 2u || *(_WORD *)(v42 + 2 * ((unsigned __int64)v41 >> 1)) )
      goto LABEL_169;
    v82 = 0;
    v43 = SczAllocFromSz(&v82, v42);
    if ( v43 < 0 )
      goto LABEL_128;
    v43 = CCbsArrayBase<wchar_t *,CCbsStringArray>::Add(v59, &v82);
    if ( v43 < 0 )
    {
      if ( v82 )
        operator delete((void *)(v82 - 8), v44);
LABEL_128:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57F,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)(unsigned int)v43,
        (int)v83);
      if ( v42 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v42);
      if ( v20 )
        operator delete((char *)v20 - 8, v51);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v78 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
        v78 = 0;
      }
      if ( v80 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      return (unsigned int)v43;
    }
    anonymous_namespace_::OurRtlFreeStringRoutine(v42);
    if ( v20 )
      operator delete((char *)v20 - 8, v45);
    if ( pv )
      CoTaskMemFree(pv);
    if ( ++v17 == (struct _GUID *)v18 )
      goto LABEL_162;
    v6 = v81;
  }
  if ( (__int64)v61 + 2 >= (unsigned __int64)v61 )
  {
    v26 = RtlReallocateLUnicodeString(v25, v61 + 2, &v61);
    if ( v26 < 0 )
      goto LABEL_89;
    v27 = v61;
    goto LABEL_51;
  }
  v26 = -1073741675;
LABEL_89:
  v77 = v26;
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      *(__int64 *)&LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create path for host servicing packages dir.");
    v59 = &v77;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
      *(__int64 *)&LogAdapter::g_Logger,
      v46,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
      (__int64)&v59);
  }
  v11 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x564,
          (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
          (const char *)(unsigned int)v26,
          (int)v57);
  if ( v62 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v62);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v78 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
    v78 = 0;
  }
  if ( v80 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
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
