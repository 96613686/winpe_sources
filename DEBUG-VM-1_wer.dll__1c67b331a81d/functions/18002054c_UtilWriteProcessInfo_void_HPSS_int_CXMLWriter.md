# UtilWriteProcessInfo(void *,HPSS__ *,int,CXMLWriter *)

- ea: `0x18002054c`
- end: `0x18002162c`
- name: `?UtilWriteProcessInfo@@YAJPEAXPEAUHPSS__@@HPEAVCXMLWriter@@@Z`
- size: `4320`
- prototype: `__int64 __fastcall(void *, struct HPSS__ *, int, struct CXMLWriter *)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002054c`
- `0x180090dac`

## callees

- `0x180007e10`
- `0x18000bc10`
- `0x18000c390`
- `0x18000cc74`
- `0x18001fe24`
- `0x18002054c`
- `0x180021634`
- `0x18002de18`
- `0x180039874`
- `0x18003bf14`
- `0x180040f08`
- `0x18004144c`
- `0x180041588`
- `0x180041830`
- `0x180049458`
- `0x180049ee4`
- `0x18004c520`
- `0x180050db0`
- `0x1800517cc`
- `0x180077f8c`
- `0x18007f408`
- `0x180097e84`
- `0x1800a5aa8`
- `0x1800a5cb4`
- `0x1800a5e04`
- `0x1800a5ffc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021494`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021511`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021534`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021551`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021574`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021591`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800215b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800215d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800215fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021494`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021511`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021534`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021551`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021574`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021591`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800215b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800215d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800215fa`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x180020bb0`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x180020bb0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020eee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bbe`
- `ntdll!NtQueryInformationProcess` at `0x180020737`
- `ntdll!NtQueryInformationProcess` at `0x1800212a9`
- `ntdll!NtQueryInformationProcess` at `0x180020737`
- `ntdll!NtQueryInformationProcess` at `0x1800212a9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800213c9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800213c9`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180020798`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x1800207e7`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180020f5d`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180020798`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x1800207e7`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180020f5d`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180020a07`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180020a07`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180020978`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180020978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800209ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800209ec`

## string_xrefs

- `0x1800211d3`: `ComponentId`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall UtilWriteProcessInfo(void *a1, struct HPSS__ *a2, int a3, struct CXMLWriter *a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  _BOOL8 v9; // rcx
  unsigned int *v10; // rax
  _OWORD *v11; // rcx
  __int64 v12; // rdx
  NTSTATUS v13; // ebx
  unsigned int v14; // ebx
  wchar_t *v15; // rcx
  __int64 v16; // rdx
  void *v17; // r14
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // eax
  wchar_t *v24; // rcx
  int ProcessPathFromHandle; // eax
  const wchar_t *v26; // rax
  int ProcessCommandLine; // ebx
  unsigned int v28; // ebx
  PWSTR *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r8
  _WORD *v32; // rax
  __int64 v33; // rcx
  void *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rax
  unsigned int v38; // ebx
  int ProcessPackageFullName; // eax
  int ProcessApplicationId; // eax
  wchar_t *v41; // rcx
  __int64 v42; // rdx
  int ProcessHostComponentIds; // eax
  signed int LastError; // eax
  int v45; // r9d
  int v46; // r9d
  int v47; // r9d
  int v48; // r9d
  int v49; // r9d
  char v50; // dl
  const wchar_t *v51; // rcx
  __int64 v52; // rax
  int v53; // r9d
  int v54; // r9d
  int v55; // r9d
  int v56; // r9d
  int v57; // r9d
  int v58; // r9d
  NTSTATUS v59; // eax
  char *v60; // rbx
  __int128 v62; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v63; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v65[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v66; // [rsp+64h] [rbp-9Ch] BYREF
  struct _FILETIME CreationTime; // [rsp+68h] [rbp-98h] BYREF
  char *v68; // [rsp+70h] [rbp-90h] BYREF
  void *v69; // [rsp+78h] [rbp-88h] BYREF
  struct _FILETIME ExitTime; // [rsp+80h] [rbp-80h] BYREF
  struct _FILETIME KernelTime; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME UserTime; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v73; // [rsp+98h] [rbp-68h] BYREF
  __int128 ProcessInformation; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v75; // [rsp+B0h] [rbp-50h]
  DWORD dwProcessId[4]; // [rsp+C0h] [rbp-40h]
  LPVOID lpMem; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v78; // [rsp+D8h] [rbp-28h]
  char v79; // [rsp+E0h] [rbp-20h] BYREF
  LPVOID v80; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE *v81; // [rsp+F8h] [rbp-8h]
  char v82; // [rsp+100h] [rbp+0h] BYREF
  LPVOID v83; // [rsp+110h] [rbp+10h] BYREF
  __int64 v84; // [rsp+118h] [rbp+18h]
  char v85; // [rsp+120h] [rbp+20h] BYREF
  LPVOID v86[2]; // [rsp+130h] [rbp+30h] BYREF
  char v87; // [rsp+140h] [rbp+40h] BYREF
  LPVOID v88[2]; // [rsp+150h] [rbp+50h] BYREF
  char v89; // [rsp+160h] [rbp+60h] BYREF
  LPVOID v90[2]; // [rsp+170h] [rbp+70h] BYREF
  char v91; // [rsp+180h] [rbp+80h] BYREF
  LPVOID v92[2]; // [rsp+190h] [rbp+90h] BYREF
  char v93; // [rsp+1A0h] [rbp+A0h] BYREF
  LPVOID v94[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v95; // [rsp+1C0h] [rbp+C0h] BYREF
  LPVOID v96[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v97; // [rsp+1E0h] [rbp+E0h] BYREF
  LPVOID v98[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v99; // [rsp+200h] [rbp+100h] BYREF
  LPVOID v100[2]; // [rsp+210h] [rbp+110h] BYREF
  char v101; // [rsp+220h] [rbp+120h] BYREF
  wchar_t *v102; // [rsp+230h] [rbp+130h] BYREF
  char v103; // [rsp+240h] [rbp+140h] BYREF
  _QWORD v104[6]; // [rsp+250h] [rbp+150h] BYREF
  _VM_COUNTERS_EX v105; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v106[704]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned int v107; // [rsp+5A0h] [rbp+4A0h] BYREF
  __int64 v108; // [rsp+5A8h] [rbp+4A8h]
  __int64 v109; // [rsp+5B0h] [rbp+4B0h]
  unsigned int v110; // [rsp+5B8h] [rbp+4B8h]
  unsigned int v111; // [rsp+5BCh] [rbp+4BCh]
  unsigned int v112; // [rsp+5C0h] [rbp+4C0h]
  struct _FILETIME v113; // [rsp+5C8h] [rbp+4C8h]
  struct _FILETIME v114; // [rsp+5D0h] [rbp+4D0h]
  struct _FILETIME v115; // [rsp+5D8h] [rbp+4D8h]
  struct _FILETIME v116; // [rsp+5E0h] [rbp+4E0h]
  SIZE_T v117; // [rsp+5F0h] [rbp+4F0h]
  SIZE_T v118; // [rsp+5F8h] [rbp+4F8h]
  ULONG v119; // [rsp+600h] [rbp+500h]
  SIZE_T v120; // [rsp+608h] [rbp+508h]
  SIZE_T v121; // [rsp+610h] [rbp+510h]
  SIZE_T v122; // [rsp+618h] [rbp+518h]
  SIZE_T v123; // [rsp+620h] [rbp+520h]
  SIZE_T v124; // [rsp+628h] [rbp+528h]
  SIZE_T v125; // [rsp+630h] [rbp+530h]
  SIZE_T v126; // [rsp+638h] [rbp+538h]
  SIZE_T v127; // [rsp+640h] [rbp+540h]
  SIZE_T v128; // [rsp+648h] [rbp+548h]
  char v129; // [rsp+654h] [rbp+554h] BYREF
  _VM_COUNTERS_EX v130; // [rsp+860h] [rbp+760h] BYREF
  struct _GUID v131; // [rsp+8C0h] [rbp+7C0h] BYREF
  _WORD v132[264]; // [rsp+8D0h] [rbp+7D0h] BYREF

  LODWORD(v68) = a3;
  memset_0(&v107, 0, 0x2C0u);
  v69 = 0;
  ProcessInformation = 0;
  v75 = 0;
  *(_OWORD *)dwProcessId = 0;
  CreationTime = 0;
  ExitTime = 0;
  KernelTime = 0;
  UserTime = 0;
  memset_0(&v130, 0, sizeof(v130));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v98);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v102);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v96);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v83);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v94);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v86);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v92);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v80);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v100);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v90);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v88);
  v73 = 0;
  v131 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpMem);
  v9 = a2 != 0;
  if ( v9 == (a1 != 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v7, v8);
  memset_0(v106, 0, sizeof(v106));
  v10 = &v107;
  v11 = v106;
  v12 = 5;
  do
  {
    *(_OWORD *)v10 = *v11;
    *((_OWORD *)v10 + 1) = v11[1];
    *((_OWORD *)v10 + 2) = v11[2];
    *((_OWORD *)v10 + 3) = v11[3];
    *((_OWORD *)v10 + 4) = v11[4];
    *((_OWORD *)v10 + 5) = v11[5];
    *((_OWORD *)v10 + 6) = v11[6];
    *((_OWORD *)v10 + 7) = v11[7];
    v10 += 32;
    v11 += 8;
    --v12;
  }
  while ( v12 );
  *(_OWORD *)v10 = *v11;
  *((_OWORD *)v10 + 1) = v11[1];
  *((_OWORD *)v10 + 2) = v11[2];
  *((_OWORD *)v10 + 3) = v11[3];
  CreationTime = 0;
  if ( a1 )
  {
    v13 = NtQueryInformationProcess(a1, ProcessBasicInformation, &ProcessInformation, 0x30u, 0);
    if ( v13 < 0 )
    {
      v14 = v13 | 0x10000000;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v16 = 14;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_683aa959ceed38e99a300365342989fb_Traceguids, v14);
        goto LABEL_114;
      }
      goto LABEL_114;
    }
    v17 = a1;
LABEL_26:
    v23 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v98, L"%d", dwProcessId[0]);
    if ( v23 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_683aa959ceed38e99a300365342989fb_Traceguids,
        (unsigned int)v23);
    if ( a2 )
    {
      v24 = (wchar_t *)&v129;
    }
    else
    {
      ProcessPathFromHandle = UtilGetProcessPathFromHandle(v17);
      if ( ProcessPathFromHandle < 0 )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_683aa959ceed38e99a300365342989fb_Traceguids,
            (unsigned int)ProcessPathFromHandle);
        v26 = L"(unable to retrieve)";
LABEL_39:
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v96, v26);
        ProcessCommandLine = UtilGetProcessCommandLine(v17);
        if ( ProcessCommandLine < 0 )
        {
          v28 = ProcessCommandLine | 0x80000000;
        }
        else
        {
          v28 = 0;
          pv[0] = 0;
          v29 = (PWSTR *)___replace___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__YAPEAPEA_WAEAV__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___0__Z(pv);
          if ( SHGetKnownFolderPath(&FOLDERID_InternetCache, 0x4000u, 0, v29) >= 0 )
          {
            v32 = pv[0];
            if ( !pv[0] )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(v30, 0, v31);
              v32 = pv[0];
            }
            v33 = -1;
            do
              ++v33;
            while ( v32[v33] );
            *(_QWORD *)&v63 = v32;
            *((_QWORD *)&v63 + 1) = v33;
            *(_QWORD *)&v62 = v83;
            *((_QWORD *)&v62 + 1) = (v84 - (__int64)v83) >> 1;
            v28 = (unsigned __int8)StringContainsOrdinalIgnoreCase(&v62, &v63);
            v34 = pv[0];
            pv[0] = 0;
            if ( v34 )
              CoTaskMemFree(v34);
          }
          v132[0] = 0;
          if ( (unsigned int)GetTempPath2W(260, v132) - 1 <= 0x102 )
          {
            if ( !v132[0] )
              MicrosoftTelemetryAssertTriggeredNoArgs(0, v35, v36);
            v37 = -1;
            do
              ++v37;
            while ( v132[v37] );
            *(_QWORD *)&v62 = v132;
            *((_QWORD *)&v62 + 1) = v37;
            *(_QWORD *)&v63 = v83;
            *((_QWORD *)&v63 + 1) = (v84 - (__int64)v83) >> 1;
            if ( (unsigned __int8)StringContainsOrdinalIgnoreCase(&v63, &v62) )
              v28 |= 2u;
          }
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(pv);
        }
        tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v94, L"%08X", v28);
        v38 = 0;
        if ( !(unsigned int)PackageUtility::IsPackagedApplication(v17) )
        {
LABEL_74:
          if ( a1 )
          {
            if ( !GetProcessTimes(a1, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
            {
LABEL_76:
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                v86,
                L"Error %08X",
                (unsigned int)LastError);
LABEL_79:
              v63 = 0;
              *(_OWORD *)pv = 0;
              *(_QWORD *)&v62 = L"ProcessInformation";
              *((_QWORD *)&v62 + 1) = 18;
              CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)&v62, (unsigned int)pv, 0, (__int64)&v63);
              *(_OWORD *)pv = 0;
              *(LPVOID *)&v62 = v98[0];
              *((_QWORD *)&v62 + 1) = ((char *)v98[1] - (char *)v98[0]) >> 1;
              *(_QWORD *)&v63 = L"Pid";
              *((_QWORD *)&v63 + 1) = 3;
              LOBYTE(v45) = 1;
              CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)&v63, (unsigned int)&v62, v45, (__int64)pv);
              *(_OWORD *)pv = 0;
              *(LPVOID *)&v62 = v96[0];
              *((_QWORD *)&v62 + 1) = ((char *)v96[1] - (char *)v96[0]) >> 1;
              *(_QWORD *)&v63 = L"ImageName";
              *((_QWORD *)&v63 + 1) = 9;
              LOBYTE(v46) = 1;
              CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)&v63, (unsigned int)&v62, v46, (__int64)pv);
              *(_OWORD *)pv = 0;
              *(LPVOID *)&v62 = v94[0];
              *((_QWORD *)&v62 + 1) = ((char *)v94[1] - (char *)v94[0]) >> 1;
              *(_QWORD *)&v63 = L"CmdLineSignature";
              *((_QWORD *)&v63 + 1) = 16;
              LOBYTE(v47) = 1;
              CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)&v63, (unsigned int)&v62, v47, (__int64)pv);
              *(_OWORD *)pv = 0;
              *(LPVOID *)&v62 = v86[0];
              *((_QWORD *)&v62 + 1) = ((char *)v86[1] - (char *)v86[0]) >> 1;
              *(_QWORD *)&v63 = L"Uptime";
              *((_QWORD *)&v63 + 1) = 6;
              LOBYTE(v48) = 1;
              CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)&v63, (unsigned int)&v62, v48, (__int64)pv);
              v65[0] = 0;
              v66 = 0;
              UtilGetProcessArchitecture(v17, v65, &v66);
              if ( v65[0] == v66 || !v65[0] || (v50 = 1, !v66) )
                v50 = 0;
              v104[0] = L"guest";
              v104[1] = 0;
              v104[2] = v65[0];
              v104[3] = L"host";
              v104[4] = 0;
              v104[5] = v66;
              v51 = L"1";
              if ( !v50 )
                v51 = L"0";
              v52 = -1;
              do
                ++v52;
              while ( v51[v52] );
              *(_QWORD *)&v62 = v104;
              *((_QWORD *)&v62 + 1) = 2;
              *(_QWORD *)&v63 = v51;
              *((_QWORD *)&v63 + 1) = v52;
              pv[0] = L"Wow64";
              pv[1] = (LPVOID)5;
              LOBYTE(v49) = 1;
              CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)pv, (unsigned int)&v63, v49, (__int64)&v62);
              if ( a1 )
              {
                LODWORD(pv[0]) = 0;
                if ( (int)GetProcessIptTraceSize(a1, pv) >= 0 && LODWORD(pv[0]) )
                  v38 = 1;
              }
              else if ( a2 )
              {
                v62 = 0;
                if ( !(unsigned int)PssQuerySnapshot(a2, 10, &v62) )
                {
                  if ( DWORD2(v62) )
                    v38 = 1;
                }
              }
              tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v92, L"%u", v38);
              *(_OWORD *)pv = 0;
              *(LPVOID *)&v62 = v92[0];
              *((_QWORD *)&v62 + 1) = ((char *)v92[1] - (char *)v92[0]) >> 1;
              *(_QWORD *)&v63 = L"IptEnabled";
              *((_QWORD *)&v63 + 1) = 10;
              LOBYTE(v53) = 1;
              CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)&v63, (unsigned int)&v62, v53, (__int64)pv);
              if ( v80 != v81 )
              {
                v63 = 0;
                *(_OWORD *)pv = 0;
                *(_QWORD *)&v62 = L"Package";
                *((_QWORD *)&v62 + 1) = 7;
                CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)&v62, (unsigned int)pv, 0, (__int64)&v63);
                *(_OWORD *)pv = 0;
                *(_QWORD *)&v62 = v80;
                *((_QWORD *)&v62 + 1) = (v81 - (_BYTE *)v80) >> 1;
                *(_QWORD *)&v63 = L"FullName";
                *((_QWORD *)&v63 + 1) = 8;
                LOBYTE(v54) = 1;
                CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)&v63, (unsigned int)&v62, v54, (__int64)pv);
                *(_OWORD *)pv = 0;
                *(LPVOID *)&v62 = v90[0];
                *((_QWORD *)&v62 + 1) = ((char *)v90[1] - (char *)v90[0]) >> 1;
                *(_QWORD *)&v63 = L"FamilyName";
                *((_QWORD *)&v63 + 1) = 10;
                LOBYTE(v55) = 1;
                CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)&v63, (unsigned int)&v62, v55, (__int64)pv);
                *(_OWORD *)pv = 0;
                *(LPVOID *)&v62 = v88[0];
                *((_QWORD *)&v62 + 1) = ((char *)v88[1] - (char *)v88[0]) >> 1;
                *(_QWORD *)&v63 = L"PackageRelativeApplicationId";
                *((_QWORD *)&v63 + 1) = 28;
                LOBYTE(v56) = 1;
                CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)&v63, (unsigned int)&v62, v56, (__int64)pv);
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpMem, L"%I64u", v73);
                *(_OWORD *)pv = 0;
                *(_QWORD *)&v62 = lpMem;
                *((_QWORD *)&v62 + 1) = (v78 - (__int64)lpMem) >> 1;
                *(_QWORD *)&v63 = L"HostId";
                *((_QWORD *)&v63 + 1) = 6;
                LOBYTE(v57) = 1;
                CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)&v63, (unsigned int)&v62, v57, (__int64)pv);
                UtilGetStringFromGUID(&v131, &lpMem);
                *(_OWORD *)pv = 0;
                *(_QWORD *)&v62 = lpMem;
                *((_QWORD *)&v62 + 1) = (v78 - (__int64)lpMem) >> 1;
                *(_QWORD *)&v63 = L"ComponentId";
                *((_QWORD *)&v63 + 1) = 11;
                LOBYTE(v58) = 1;
                CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)&v63, (unsigned int)&v62, v58, (__int64)pv);
                *(_QWORD *)&v62 = L"Package";
                *((_QWORD *)&v62 + 1) = 7;
                CXMLWriter::EndElement(a4, &v62);
              }
              if ( a1 )
              {
                memset_0(&v105, 0, sizeof(v105));
                v130 = v105;
                v59 = NtQueryInformationProcess(a1, ProcessVmCounters, &v130, 0x60u, 0);
                if ( v59 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      23,
                      WPP_683aa959ceed38e99a300365342989fb_Traceguids,
                      v59 | 0x10000000u);
                  goto LABEL_108;
                }
              }
              else
              {
                if ( !a2 )
                  goto LABEL_108;
                v130.PeakVirtualSize = v117;
                v130.VirtualSize = v118;
                v130.PageFaultCount = v119;
                v130.PeakWorkingSetSize = v120;
                v130.WorkingSetSize = v121;
                v130.QuotaPeakPagedPoolUsage = v122;
                v130.QuotaPagedPoolUsage = v123;
                v130.QuotaPeakNonPagedPoolUsage = v124;
                v130.QuotaNonPagedPoolUsage = v125;
                v130.PagefileUsage = v126;
                v130.PeakPagefileUsage = v127;
                v130.PrivateUsage = v128;
              }
              UtilWriteProcessVmInfo(&v130, a4);
LABEL_108:
              if ( (_DWORD)v68 && a1 )
              {
                v60 = (char *)OpenProcess(0x410u, 0, dwProcessId[2]);
                v68 = v60;
                if ( v60 != (char *)-1LL && v60 + 1 != (char *)1 )
                {
                  v63 = 0;
                  *(_OWORD *)pv = 0;
                  *(_QWORD *)&v62 = L"ParentProcess";
                  *((_QWORD *)&v62 + 1) = 13;
                  CXMLWriter::BeginElement((_DWORD)a4, (unsigned int)&v62, (unsigned int)pv, 0, (__int64)&v63);
                  UtilWriteProcessInfo(v60, 0, 0, a4);
                  *(_QWORD *)&v62 = L"ParentProcess";
                  *((_QWORD *)&v62 + 1) = 13;
                  CXMLWriter::EndElement(a4, &v62);
                }
                tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v68);
              }
              *(_QWORD *)&v62 = L"ProcessInformation";
              *((_QWORD *)&v62 + 1) = 18;
              CXMLWriter::EndElement(a4, &v62);
              v14 = 0;
              goto LABEL_114;
            }
          }
          else
          {
            if ( !a2 )
              goto LABEL_76;
            CreationTime = v113;
            ExitTime = v114;
            KernelTime = v115;
            UserTime = v116;
          }
          pv[0] = 0;
          GetSystemTimeAsFileTime((LPFILETIME)pv);
          tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v86,
            L"%I64u",
            ((unsigned __int64)pv[0] - *(_QWORD *)&CreationTime) / 0x2710);
          goto LABEL_79;
        }
        ProcessPackageFullName = PackageUtility::GetProcessPackageFullName(v17);
        if ( ProcessPackageFullName < 0
          && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_683aa959ceed38e99a300365342989fb_Traceguids,
            (unsigned int)ProcessPackageFullName);
        }
        ProcessApplicationId = PackageUtility::GetProcessApplicationId(v17);
        if ( ProcessApplicationId < 0 )
        {
          v41 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          {
            v42 = 21;
            goto LABEL_69;
          }
        }
        else
        {
          ProcessApplicationId = PackageUtility::ParseApplicationId(v100[0], v90, v88);
          if ( ProcessApplicationId < 0 )
          {
            v41 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
            {
              v42 = 20;
LABEL_69:
              WPP_SF_d(
                *((_QWORD *)v41 + 2),
                v42,
                WPP_683aa959ceed38e99a300365342989fb_Traceguids,
                (unsigned int)ProcessApplicationId);
            }
          }
        }
        ProcessHostComponentIds = PackageUtility::GetProcessHostComponentIds(v17, &v73, &v131);
        if ( ProcessHostComponentIds < 0
          && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_683aa959ceed38e99a300365342989fb_Traceguids,
            (unsigned int)ProcessHostComponentIds);
        }
        goto LABEL_74;
      }
      v24 = v102;
    }
    v26 = UtilPathTail(v24);
    goto LABEL_39;
  }
  v18 = PssQuerySnapshot(a2, 0, &v107);
  v14 = v18;
  if ( !v18 )
  {
    v19 = PssQuerySnapshot(a2, 1, &v69);
    v14 = v19;
    if ( v19 )
    {
      if ( v19 > 0 )
        v14 = (unsigned __int16)v19 | 0x80070000;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v16 = 16;
        goto LABEL_10;
      }
      goto LABEL_114;
    }
    *(_QWORD *)&ProcessInformation = v107;
    *((_QWORD *)&ProcessInformation + 1) = v108;
    *(_QWORD *)&v75 = v109;
    *((_QWORD *)&v75 + 1) = v110;
    *(_QWORD *)dwProcessId = v111;
    *(_QWORD *)&dwProcessId[2] = v112;
    v17 = v69;
    if ( !v69 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v21, v20, v22);
    goto LABEL_26;
  }
  if ( v18 > 0 )
    v14 = (unsigned __int16)v18 | 0x80070000;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v16 = 15;
    goto LABEL_10;
  }
LABEL_114:
  if ( lpMem != &v79 )
    HeapFree(g_hWerheap, 0, lpMem);
  if ( v88[0] != &v89 )
    HeapFree(g_hWerheap, 0, v88[0]);
  if ( v90[0] != &v91 )
    HeapFree(g_hWerheap, 0, v90[0]);
  if ( v100[0] != &v101 )
    HeapFree(g_hWerheap, 0, v100[0]);
  if ( v80 != &v82 )
    HeapFree(g_hWerheap, 0, v80);
  if ( v92[0] != &v93 )
    HeapFree(g_hWerheap, 0, v92[0]);
  if ( v86[0] != &v87 )
    HeapFree(g_hWerheap, 0, v86[0]);
  if ( v94[0] != &v95 )
    HeapFree(g_hWerheap, 0, v94[0]);
  if ( v83 != &v85 )
    HeapFree(g_hWerheap, 0, v83);
  if ( v96[0] != &v97 )
    HeapFree(g_hWerheap, 0, v96[0]);
  if ( v102 != (wchar_t *)&v103 )
    HeapFree(g_hWerheap, 0, v102);
  if ( v98[0] != &v99 )
    HeapFree(g_hWerheap, 0, v98[0]);
  return v14;
}

```

## disassembly

```asm
0x18002054c  mov     [rsp-8+arg_10], rbx
0x180020551  push    rbp
0x180020552  push    rsi
0x180020553  push    rdi
0x180020554  push    r12
0x180020556  push    r13
0x180020558  push    r14
0x18002055a  push    r15
0x18002055c  lea     rbp, [rsp-9F0h]
0x180020564  sub     rsp, 0AF0h
0x18002056b  mov     rax, cs:__security_cookie
0x180020572  xor     rax, rsp
0x180020575  mov     [rbp+0A20h+var_40], rax
0x18002057c  mov     r12, r9
0x18002057f  mov     dword ptr [rsp+0B20h+var_AB0], r8d
0x180020584  mov     r13, rdx
0x180020587  mov     r15, rcx
0x18002058a  mov     ebx, 2C0h
0x18002058f  mov     r8d, ebx; Size
0x180020592  xor     edx, edx; Val
0x180020594  lea     rcx, [rbp+0A20h+var_580]; void *
0x18002059b  call    memset_0
0x1800205a0  xor     edi, edi
0x1800205a2  mov     [rsp+0B20h+var_AA8], rdi
0x1800205a7  xorps   xmm0, xmm0
0x1800205aa  movups  [rbp+0A20h+ProcessInformation], xmm0
0x1800205ae  movups  [rbp+0A20h+var_A70], xmm0
0x1800205b2  movups  xmmword ptr [rbp+0A20h+dwProcessId], xmm0
0x1800205b6  mov     qword ptr [rsp+0B20h+CreationTime.dwLowDateTime], rdi
0x1800205bb  mov     qword ptr [rbp+0A20h+ExitTime.dwLowDateTime], rdi
0x1800205bf  mov     qword ptr [rbp+0A20h+KernelTime.dwLowDateTime], rdi
0x1800205c3  mov     qword ptr [rbp+0A20h+UserTime.dwLowDateTime], rdi
0x1800205c7  xor     edx, edx; Val
0x1800205c9  lea     r8d, [rdi+60h]; Size
0x1800205cd  lea     rcx, [rbp+0A20h+var_2C0]; void *
0x1800205d4  call    memset_0
0x1800205d9  lea     rcx, [rbp+0A20h+var_930]; void *
0x1800205e0  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800205e5  nop
0x1800205e6  lea     rcx, [rbp+0A20h+var_8F0]; void *
0x1800205ed  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800205f2  nop
0x1800205f3  lea     rcx, [rbp+0A20h+var_950]; void *
0x1800205fa  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800205ff  nop
0x180020600  lea     rcx, [rbp+0A20h+var_A10]; void *
0x180020604  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020609  nop
0x18002060a  lea     rcx, [rbp+0A20h+var_970]; void *
0x180020611  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020616  nop
0x180020617  lea     rcx, [rbp+0A20h+var_9F0]; void *
0x18002061b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020620  nop
0x180020621  lea     rcx, [rbp+0A20h+var_990]; void *
0x180020628  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18002062d  nop
0x18002062e  lea     rcx, [rbp+0A20h+var_A30]; void *
0x180020632  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020637  nop
0x180020638  lea     rcx, [rbp+0A20h+var_910]; void *
0x18002063f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020644  nop
0x180020645  lea     rcx, [rbp+0A20h+var_9B0]; void *
0x180020649  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18002064e  nop
0x18002064f  lea     rcx, [rbp+0A20h+var_9D0]; void *
0x180020653  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020658  nop
0x180020659  mov     [rbp+0A20h+var_A88], rdi
0x18002065d  xorps   xmm0, xmm0
0x180020660  movups  xmmword ptr [rbp+0A20h+var_260.Data1], xmm0
0x180020667  lea     rcx, [rbp+0A20h+lpMem]; void *
0x18002066b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180020670  nop
0x180020671  mov     ecx, edi
0x180020673  test    r13, r13
0x180020676  setnz   cl
0x180020679  mov     eax, edi
0x18002067b  test    r15, r15
0x18002067e  setnz   al
0x180020681  cmp     ecx, eax
0x180020683  jnz     short loc_18002068A
0x180020685  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002068a  mov     r8, rbx; Size
0x18002068d  xor     edx, edx; Val
0x18002068f  lea     rcx, [rbp+0A20h+var_840]; void *
0x180020696  call    memset_0
0x18002069b  lea     rax, [rbp+0A20h+var_580]
0x1800206a2  lea     rcx, [rbp+0A20h+var_840]
0x1800206a9  mov     edx, 5
0x1800206ae  lea     r8d, [rdx+7Bh]
0x1800206b2  movups  xmm0, xmmword ptr [rcx]
0x1800206b5  movups  xmmword ptr [rax], xmm0
0x1800206b8  movups  xmm1, xmmword ptr [rcx+10h]
0x1800206bc  movups  xmmword ptr [rax+10h], xmm1
0x1800206c0  movups  xmm0, xmmword ptr [rcx+20h]
0x1800206c4  movups  xmmword ptr [rax+20h], xmm0
0x1800206c8  movups  xmm1, xmmword ptr [rcx+30h]
0x1800206cc  movups  xmmword ptr [rax+30h], xmm1
0x1800206d0  movups  xmm0, xmmword ptr [rcx+40h]
0x1800206d4  movups  xmmword ptr [rax+40h], xmm0
0x1800206d8  movups  xmm1, xmmword ptr [rcx+50h]
0x1800206dc  movups  xmmword ptr [rax+50h], xmm1
0x1800206e0  movups  xmm0, xmmword ptr [rcx+60h]
0x1800206e4  movups  xmmword ptr [rax+60h], xmm0
0x1800206e8  movups  xmm1, xmmword ptr [rcx+70h]
0x1800206ec  movups  xmmword ptr [rax+70h], xmm1
0x1800206f0  add     rax, r8
0x1800206f3  add     rcx, r8
0x1800206f6  sub     rdx, 1; ProcessInformationClass
0x1800206fa  jnz     short loc_1800206B2
0x1800206fc  movups  xmm0, xmmword ptr [rcx]
0x1800206ff  movups  xmmword ptr [rax], xmm0
0x180020702  movups  xmm1, xmmword ptr [rcx+10h]
0x180020706  movups  xmmword ptr [rax+10h], xmm1
0x18002070a  movups  xmm0, xmmword ptr [rcx+20h]
0x18002070e  movups  xmmword ptr [rax+20h], xmm0
0x180020712  movups  xmm1, xmmword ptr [rcx+30h]
0x180020716  movups  xmmword ptr [rax+30h], xmm1
0x18002071a  mov     qword ptr [rsp+0B20h+CreationTime.dwLowDateTime], rdi
0x18002071f  lea     esi, [rdx+1]
0x180020722  test    r15, r15
0x180020725  jz      short loc_18002078B
0x180020727  mov     [rsp+0B20h+ReturnLength], rdi; ReturnLength
0x18002072c  lea     r9d, [rdx+30h]; ProcessInformationLength
0x180020730  lea     r8, [rbp+0A20h+ProcessInformation]; ProcessInformation
0x180020734  mov     rcx, r15; ProcessHandle
0x180020737  call    cs:__imp_NtQueryInformationProcess
0x18002073d  mov     ebx, eax
0x18002073f  test    eax, eax
0x180020741  jns     short loc_180020783
0x180020743  bts     ebx, 1Ch
0x180020747  lea     rdi, WPP_GLOBAL_Control
0x18002074e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020755  cmp     rcx, rdi
0x180020758  jz      loc_18002147E
0x18002075e  test    [rcx+1Ch], sil
0x180020762  jz      loc_18002147E
0x180020768  lea     edx, [rsi+0Dh]
0x18002076b  mov     r9d, ebx
0x18002076e  lea     r8, WPP_683aa959ceed38e99a300365342989fb_Traceguids
0x180020775  mov     rcx, [rcx+10h]
0x180020779  call    WPP_SF_d
0x18002077e  jmp     loc_18002147E
0x180020783  mov     r14, r15
0x180020786  jmp     loc_180020883
0x18002078b  mov     r9d, ebx
0x18002078e  lea     r8, [rbp+0A20h+var_580]
0x180020795  mov     rcx, r13
0x180020798  call    cs:__imp_PssQuerySnapshot
0x18002079e  mov     ebx, eax
0x1800207a0  test    eax, eax
0x1800207a2  jz      short loc_1800207D7
0x1800207a4  jle     short loc_1800207AF
0x1800207a6  movzx   ebx, ax
0x1800207a9  or      ebx, 80070000h
0x1800207af  lea     rdi, WPP_GLOBAL_Control
0x1800207b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207bd  cmp     rcx, rdi
0x1800207c0  jz      loc_18002147E
0x1800207c6  test    [rcx+1Ch], sil
0x1800207ca  jz      loc_18002147E
0x1800207d0  mov     edx, 0Fh
0x1800207d5  jmp     short loc_18002076B
0x1800207d7  mov     r9d, 8
0x1800207dd  lea     r8, [rsp+0B20h+var_AA8]
0x1800207e2  mov     edx, esi
0x1800207e4  mov     rcx, r13
0x1800207e7  call    cs:__imp_PssQuerySnapshot
0x1800207ed  mov     ebx, eax
0x1800207ef  test    eax, eax
0x1800207f1  jz      short loc_180020829
0x1800207f3  jle     short loc_1800207FE
0x1800207f5  movzx   ebx, ax
0x1800207f8  or      ebx, 80070000h
0x1800207fe  lea     rdi, WPP_GLOBAL_Control
0x180020805  mov     rcx, cs:WPP_GLOBAL_Control
0x18002080c  cmp     rcx, rdi
0x18002080f  jz      loc_18002147E
0x180020815  test    [rcx+1Ch], sil
0x180020819  jz      loc_18002147E
0x18002081f  mov     edx, 10h
0x180020824  jmp     loc_18002076B
0x180020829  xorps   xmm0, xmm0
0x18002082c  movups  [rbp+0A20h+ProcessInformation], xmm0
0x180020830  movups  [rbp+0A20h+var_A70], xmm0
0x180020834  movups  xmmword ptr [rbp+0A20h+dwProcessId], xmm0
0x180020838  mov     eax, [rbp+0A20h+var_580]
0x18002083e  mov     dword ptr [rbp+0A20h+ProcessInformation], eax
0x180020841  mov     rax, [rbp+0A20h+var_578]
0x180020848  mov     qword ptr [rbp+0A20h+ProcessInformation+8], rax
0x18002084c  mov     rax, [rbp+0A20h+var_570]
0x180020853  mov     qword ptr [rbp+0A20h+var_A70], rax
0x180020857  mov     eax, [rbp+0A20h+var_568]
0x18002085d  mov     dword ptr [rbp+0A20h+var_A70+8], eax
0x180020860  mov     eax, [rbp+0A20h+var_564]
0x180020866  mov     qword ptr [rbp+0A20h+dwProcessId], rax
0x18002086a  mov     eax, [rbp+0A20h+var_560]
0x180020870  mov     qword ptr [rbp+0A20h+dwProcessId+8], rax
0x180020874  mov     r14, [rsp+0B20h+var_AA8]
0x180020879  test    r14, r14
0x18002087c  jnz     short loc_180020883
0x18002087e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180020883  mov     r8d, [rbp+0A20h+dwProcessId]
0x180020887  lea     rdx, aD; "%d"
0x18002088e  lea     rcx, [rbp+0A20h+var_930]
0x180020895  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18002089a  lea     rsi, WPP_683aa959ceed38e99a300365342989fb_Traceguids
0x1800208a1  lea     rdi, WPP_GLOBAL_Control
0x1800208a8  test    eax, eax
0x1800208aa  jns     short loc_1800208D2
0x1800208ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208b3  cmp     rcx, rdi
0x1800208b6  jz      short loc_1800208D2
0x1800208b8  test    byte ptr [rcx+1Ch], 2
0x1800208bc  jz      short loc_1800208D2
0x1800208be  mov     edx, 11h
0x1800208c3  mov     r9d, eax
0x1800208c6  mov     r8, rsi
0x1800208c9  mov     rcx, [rcx+10h]
0x1800208cd  call    WPP_SF_d
0x1800208d2  test    r13, r13
0x1800208d5  jz      short loc_1800208E0
0x1800208d7  lea     rcx, [rbp+0A20h+var_4CC]
0x1800208de  jmp     short loc_180020929
0x1800208e0  lea     rdx, [rbp+0A20h+var_8F0]
0x1800208e7  mov     rcx, r14; hProcess
0x1800208ea  call    ?UtilGetProcessPathFromHandle@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetProcessPathFromHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800208ef  test    eax, eax
0x1800208f1  jns     short loc_180020922
0x1800208f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208fa  cmp     rcx, rdi
0x1800208fd  jz      short loc_180020919
0x1800208ff  test    byte ptr [rcx+1Ch], 2
0x180020903  jz      short loc_180020919
0x180020905  mov     edx, 12h
0x18002090a  mov     r9d, eax
0x18002090d  mov     r8, rsi
0x180020910  mov     rcx, [rcx+10h]
0x180020914  call    WPP_SF_d
0x180020919  lea     rax, aUnableToRetrie; "(unable to retrieve)"
0x180020920  jmp     short loc_18002092E
0x180020922  mov     rcx, [rbp+0A20h+var_8F0]; wchar_t *
0x180020929  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x18002092e  mov     rdx, rax
0x180020931  lea     rcx, [rbp+0A20h+var_950]
0x180020938  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18002093d  lea     rdx, [rbp+0A20h+var_A10]
0x180020941  mov     rcx, r14; hProcess
0x180020944  call    ?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180020949  mov     ebx, eax
0x18002094b  xor     eax, eax
0x18002094d  test    ebx, ebx
0x18002094f  js      loc_180020A87
0x180020955  mov     ebx, eax
0x180020957  mov     [rsp+0B20h+pv], rax
0x18002095c  lea     rcx, [rsp+0B20h+pv]
0x180020961  call    ??$replace@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEA_WAEAV?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x180020966  mov     r9, rax; ppszPath
0x180020969  xor     r8d, r8d; hToken
0x18002096c  mov     edx, 4000h; dwFlags
0x180020971  lea     rcx, FOLDERID_InternetCache; rfid
0x180020978  call    cs:__imp_SHGetKnownFolderPath
0x18002097e  xor     edx, edx
0x180020980  test    eax, eax
0x180020982  js      short loc_1800209F4
0x180020984  mov     rax, [rsp+0B20h+pv]
0x180020989  test    rax, rax
0x18002098c  jnz     short loc_18002099A
0x18002098e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180020993  mov     rax, [rsp+0B20h+pv]
0x180020998  xor     edx, edx
0x18002099a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002099e  inc     rcx
0x1800209a1  cmp     [rax+rcx*2], dx
0x1800209a5  jnz     short loc_18002099E
0x1800209a7  mov     qword ptr [rsp+0B20h+var_AE0], rax
0x1800209ac  mov     qword ptr [rsp+0B20h+var_AE0+8], rcx
0x1800209b1  mov     rax, [rbp+0A20h+var_A10]
0x1800209b5  mov     qword ptr [rsp+0B20h+var_AF0], rax
0x1800209ba  mov     rcx, [rbp+0A20h+var_A08]
0x1800209be  sub     rcx, rax
0x1800209c1  sar     rcx, 1
0x1800209c4  mov     qword ptr [rsp+0B20h+var_AF0+8], rcx
0x1800209c9  lea     rdx, [rsp+0B20h+var_AE0]
0x1800209ce  lea     rcx, [rsp+0B20h+var_AF0]
0x1800209d3  call    ?StringContainsOrdinalIgnoreCase@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0@Z; StringContainsOrdinalIgnoreCase(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800209d8  movzx   ebx, al
0x1800209db  mov     rcx, [rsp+0B20h+pv]; pv
0x1800209e0  xor     edx, edx
0x1800209e2  mov     [rsp+0B20h+pv], rdx
0x1800209e7  test    rcx, rcx
0x1800209ea  jz      short loc_1800209F4
0x1800209ec  call    cs:__imp_CoTaskMemFree
0x1800209f2  xor     edx, edx
0x1800209f4  mov     [rbp+0A20h+var_250], dx
0x1800209fb  lea     rdx, [rbp+0A20h+var_250]
0x180020a02  mov     ecx, 104h
0x180020a07  call    cs:__imp_GetTempPath2W
  ... truncated ...
```
