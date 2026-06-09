# CDeploymentSession::CreateUaLiteDownloadRequest(bool,std::set<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,WstringCaseInsensitiveCompare,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> *)

- ea: `0x18004478c`
- end: `0x180045cb8`
- name: `?CreateUaLiteDownloadRequest@CDeploymentSession@@QEAA?AV?$com_ptr_t@UIDeploymentDownloadRequest@@Uerr_exception_policy@wil@@@wil@@_NPEAV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z`
- size: `5420`
- prototype: `_QWORD *__fastcall(CDeploymentSession *this, struct CDeploymentDownloadRequest *, char, __int64)`
- caller_count: `1`
- callee_count: `45`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180095f2c`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x180005cf0`
- `0x18000bf9c`
- `0x18000c4c4`
- `0x18000e768`
- `0x18000ea04`
- `0x1800123fc`
- `0x180012770`
- `0x1800127a4`
- `0x180012d94`
- `0x180012fe4`
- `0x180016014`
- `0x1800201cc`
- `0x180020254`
- `0x1800235cc`
- `0x18002374c`
- `0x180023b20`
- `0x1800274a8`
- `0x1800316b0`
- `0x180035b4c`
- `0x180035bf0`
- `0x180039f90`
- `0x18003c418`
- `0x18003e304`
- `0x18003e4a4`
- `0x18003e600`
- `0x18004478c`
- `0x18005284c`
- `0x1800613b4`
- `0x18006ecbc`
- `0x180074c18`
- `0x180077664`
- `0x18007c740`
- `0x180094d0c`
- `0x18009af9c`
- `0x18009b1cc`
- `0x18009b848`
- `0x18009ba64`
- `0x18009f0b0`
- `0x1800a6698`
- `0x1800acd88`
- `0x1801dec50`
- `0x1801e3fc0`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180045226`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800455c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800456bc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180045226`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800455c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800456bc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180044c72`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180044c72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044e11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044e46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044f31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044f66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800452d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045305`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044e11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044e46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044f31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044f66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800452d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045305`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044e26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044e5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044f46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044f7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800452e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004531a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044e26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044e5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044f46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044f7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800452e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004531a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044b2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044b90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044b2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044b90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044b1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044b82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044e78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044e8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044fae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045337`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004534d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044b1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044b82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044e78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044e8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044f98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044fae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045337`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004534d`

## string_xrefs

- `0x180044915`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180045ab1`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180044858`: `CDeploymentSession::CreateUaLiteDownloadRequest`
- `0x180044db7`: `Failed to create hardlink for file from {0}`
- `0x180044f18`: `UaLiteDownload: File already seen, Container Name: [{}], Filename: [{}]`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall CDeploymentSession::CreateUaLiteDownloadRequest(
        CDeploymentSession *this,
        struct CDeploymentDownloadRequest *a2,
        char a3,
        __int64 a4)
{
  _QWORD *v5; // r12
  struct CDeploymentDownloadRequest *v7; // r15
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  int ActionList; // eax
  struct ActionList *v13; // r14
  __int64 v14; // rcx
  __int64 DownloadRequest; // rbx
  int IsRangeRequestSupported; // eax
  int v17; // eax
  const wchar_t *v18; // rcx
  const wchar_t *v19; // rbx
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, __int64 **); // rdi
  __int64 *v22; // rcx
  int v23; // eax
  int v24; // eax
  unsigned int v25; // r12d
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // r14
  __int64 (__fastcall *v29)(__int64, LPVOID *); // r15
  void *v30; // rdi
  DWORD LastError; // ebx
  int v32; // eax
  __int64 v33; // r14
  __int64 (__fastcall *v34)(__int64, wchar_t **); // r15
  wchar_t *v35; // rdi
  DWORD v36; // ebx
  int v37; // eax
  __int64 v38; // rbx
  __int64 (__fastcall *v39)(__int64, __int64 **); // rdi
  __int64 *v40; // rcx
  int v41; // eax
  int v42; // eax
  __int64 v43; // rax
  int v44; // eax
  DWORD FileAttributesW; // eax
  BOOL v46; // ebx
  __int64 v47; // rax
  _QWORD *v48; // rcx
  int v49; // eax
  int v50; // edx
  int v51; // r8d
  int v52; // r9d
  __int64 v53; // rbx
  __int64 v54; // r8
  __int64 v55; // rax
  __int64 v56; // rax
  int HardLinkWithFallback; // eax
  int v58; // ebx
  __int64 v59; // rdx
  __int64 v60; // rbx
  HANDLE ProcessHeap; // rax
  LPCWSTR v62; // rbx
  HANDLE v63; // rax
  __int64 v64; // r8
  wchar_t **v65; // rax
  __int64 v66; // rbx
  HANDLE v67; // rax
  LPCWSTR v68; // rbx
  HANDLE v69; // rax
  int v70; // eax
  unsigned int v71; // edi
  struct CDeploymentFileRequest *i; // rbx
  __int64 v73; // rax
  int v74; // eax
  int v75; // eax
  int v76; // eax
  int v77; // eax
  struct CDeploymentFileRange *v78; // rax
  int appended; // eax
  wchar_t *v80; // r15
  _QWORD *v81; // r12
  char *v82; // r14
  char **v83; // rdi
  __int64 v84; // r8
  __int64 v85; // rax
  __int128 v86; // xmm6
  __int64 v87; // rax
  __int64 v88; // rdx
  unsigned __int64 v89; // r15
  char *v90; // rcx
  unsigned __int64 v91; // r12
  unsigned __int64 v92; // r8
  int v93; // eax
  __int64 v94; // rcx
  __int64 v95; // rbx
  HANDLE v96; // rax
  LPCWSTR v97; // rbx
  HANDLE v98; // rax
  int v99; // eax
  wil::details::in1diag3 *m; // rcx
  wil::details::in1diag3 *v101; // rbx
  struct CDeploymentDownloadRequest *v102; // rdi
  __int64 v103; // rax
  int v104; // eax
  __int64 k; // rax
  const wchar_t *v106; // rdx
  int OffsetInOuterContainer; // eax
  int v108; // edx
  int v109; // r8d
  int v110; // r9d
  wchar_t **v111; // rax
  __int64 v112; // rax
  __int64 v113; // rdx
  unsigned __int64 v114; // rdi
  wchar_t **v115; // rcx
  unsigned __int64 v116; // rbx
  unsigned __int64 v117; // r8
  int v118; // eax
  const wchar_t *v119; // r8
  const wchar_t *v120; // rdx
  const wchar_t *v121; // rcx
  int v122; // eax
  __int64 v123; // rax
  __int128 v124; // xmm6
  __int64 v125; // rax
  struct CDeploymentFileRequest *v126; // rbx
  __int64 v127; // rdx
  unsigned __int64 v128; // r14
  wchar_t **v129; // rcx
  unsigned __int64 v130; // rdi
  unsigned __int64 v131; // r8
  int v132; // eax
  _QWORD *v133; // r15
  _QWORD *v134; // r14
  __int64 v135; // rbx
  __int64 v136; // r8
  __int64 v137; // rcx
  wchar_t **v138; // rdx
  struct ActionList *v139; // rbx
  unsigned int j; // r15d
  __int64 v141; // rax
  int v142; // eax
  int v143; // eax
  int v144; // eax
  char *v145; // r14
  int v146; // edi
  int v147; // eax
  struct CDeploymentFileRange *v148; // rax
  int v149; // eax
  int v150; // eax
  struct CDeploymentFileRange *v151; // rax
  int v152; // eax
  struct CDeploymentFileRequest **v154; // [rsp+28h] [rbp-E0h]
  struct CDeploymentFileRange *v155; // [rsp+48h] [rbp-C0h] BYREF
  struct CDeploymentDownloadRequest *v156; // [rsp+50h] [rbp-B8h] BYREF
  struct CDeploymentDownloadRequest *v157; // [rsp+58h] [rbp-B0h] BYREF
  struct ActionList *v158[3]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v159; // [rsp+78h] [rbp-90h]
  _QWORD **v160; // [rsp+90h] [rbp-78h]
  _QWORD *v161; // [rsp+98h] [rbp-70h]
  _QWORD **v162; // [rsp+A0h] [rbp-68h]
  char *v163; // [rsp+A8h] [rbp-60h]
  __int64 v164; // [rsp+B0h] [rbp-58h]
  _QWORD v165[2]; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v166[2]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v167[2]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD v168[4]; // [rsp+E8h] [rbp-20h] BYREF
  char v169; // [rsp+108h] [rbp+0h]
  _BYTE v170[16]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v171[24]; // [rsp+120h] [rbp+18h] BYREF
  const char *v172; // [rsp+138h] [rbp+30h] BYREF
  struct CDeploymentFileRequest *v173; // [rsp+140h] [rbp+38h] BYREF
  wchar_t *v174; // [rsp+148h] [rbp+40h] BYREF
  int v175; // [rsp+150h] [rbp+48h] BYREF
  unsigned __int64 v176; // [rsp+158h] [rbp+50h] BYREF
  unsigned int v177; // [rsp+160h] [rbp+58h] BYREF
  __int64 v178; // [rsp+168h] [rbp+60h] BYREF
  __int64 *v179; // [rsp+170h] [rbp+68h] BYREF
  LPVOID pv; // [rsp+178h] [rbp+70h] BYREF
  unsigned __int64 v181; // [rsp+180h] [rbp+78h] BYREF
  __int64 v182; // [rsp+188h] [rbp+80h] BYREF
  LPCWSTR lpFileName; // [rsp+190h] [rbp+88h] BYREF
  _QWORD *v184; // [rsp+198h] [rbp+90h] BYREF
  __int64 v185; // [rsp+1A0h] [rbp+98h]
  struct CDeploymentFileRequest *v186; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v187; // [rsp+1B0h] [rbp+A8h] BYREF
  unsigned __int64 v188; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 *v189; // [rsp+1C0h] [rbp+B8h] BYREF
  wchar_t *v190[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  __int64 v191; // [rsp+1D8h] [rbp+D0h]
  wchar_t *v192[2]; // [rsp+1E8h] [rbp+E0h] BYREF
  unsigned __int64 v193; // [rsp+1F8h] [rbp+F0h]
  unsigned __int64 v194; // [rsp+200h] [rbp+F8h]
  wchar_t *Src[4]; // [rsp+208h] [rbp+100h] BYREF
  _QWORD v196[4]; // [rsp+228h] [rbp+120h] BYREF
  __int64 v197; // [rsp+248h] [rbp+140h]
  _QWORD v198[2]; // [rsp+258h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C0h] [rbp+1B8h]

  v168[2] = -2;
  v164 = a4;
  v5 = a2;
  v157 = a2;
  v156 = a2;
  v7 = 0;
  *(_OWORD *)v190 = 0;
  v191 = 0;
  v184 = 0;
  v185 = 0;
  v8 = operator new(0x48u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  v184 = v8;
  v198[0] = 0;
  v198[1] = 0;
  v9 = operator new(0x40u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  v198[0] = v9;
  v158[0] = 0;
  v172 = "CDeploymentSession::CreateUaLiteDownloadRequest";
  LogAdapter::TraceAtLevel<char const *>(v10, "{}: Enter", &v172);
  v168[3] = &v172;
  v169 = 1;
  ActionList = LoadActionList(0, *((_QWORD *)this + 63), v11, v158);
  if ( ActionList < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x203E,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)ActionList,
      (int)v154);
  v13 = v158[0];
  CDeploymentSession::InitializeUaLite(this, v158[0]);
  v14 = *((_QWORD *)this + 82);
  if ( v14 )
  {
    DownloadRequest = UaLiteManager::GenerateDownloadRequest(v14, v171);
    if ( v190 != (wchar_t **)DownloadRequest )
    {
      std::vector<UaLiteManagerDownloadRequest>::_Tidy(v190);
      v190[0] = *(wchar_t **)DownloadRequest;
      v190[1] = *(wchar_t **)(DownloadRequest + 8);
      v191 = *(_QWORD *)(DownloadRequest + 16);
      *(_QWORD *)DownloadRequest = 0;
      *(_QWORD *)(DownloadRequest + 8) = 0;
      *(_QWORD *)(DownloadRequest + 16) = 0;
    }
    std::vector<UaLiteManagerDownloadRequest>::_Tidy(v171);
  }
  if ( a3 )
  {
    v175 = 0;
    LODWORD(v176) = 0;
    IsRangeRequestSupported = CDeploymentSession::IsRangeRequestSupported(
                                this,
                                &v175,
                                (enum MoUpdateRangeRequestState *)&v176);
    if ( IsRangeRequestSupported < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x204B,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)IsRangeRequestSupported,
        (int)v154);
    v17 = CDeploymentSession::ProcessSandboxContainerPayload(this, (__int64)v190);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x204C,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v17,
        (int)v154);
  }
  v156 = 0;
  v18 = v190[0];
  if ( 0x4EC4EC4EC4EC4EC5LL * (((char *)v190[1] - (char *)v190[0]) >> 3) )
  {
    do
    {
      v189 = 0;
      v175 = 0;
      v19 = &v18[52 * (_QWORD)v7];
      v173 = (struct CDeploymentFileRequest *)v192;
      std::wstring::wstring(v192, v19);
      std::wstring::wstring(Src, v19 + 16);
      std::wstring::wstring(v196, v19 + 32);
      v20 = *((_QWORD *)v19 + 12);
      v197 = v20;
      if ( v20 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
        v20 = v197;
      }
      v21 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v20 + 40LL);
      v22 = v189;
      v189 = 0;
      if ( v22 )
        (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
      v23 = v21(v20, &v189);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2055,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v23,
          (int)v154);
      v24 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v189 + 24))(v189, &v175);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2056,
          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
          (const char *)(unsigned int)v24,
          (int)v154);
      v25 = 0;
      LODWORD(v176) = 0;
      if ( v175 )
      {
        while ( 1 )
        {
          v182 = 0;
          v179 = 0;
          pv = 0;
          v174 = 0;
          v177 = 0;
          v26 = *v189;
          v182 = 0;
          v27 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v26 + 32))(v189, v25, &v182);
          if ( v27 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2060,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v27,
              (int)v154);
          v28 = v182;
          v29 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v182 + 24LL);
          v30 = pv;
          if ( pv )
          {
            LastError = GetLastError();
            CoTaskMemFree(v30);
            SetLastError(LastError);
          }
          pv = 0;
          v32 = v29(v28, &pv);
          if ( v32 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2061,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v32,
              (int)v154);
          v33 = v182;
          v34 = *(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v182 + 40LL);
          v35 = v174;
          if ( v174 )
          {
            v36 = GetLastError();
            CoTaskMemFree(v35);
            SetLastError(v36);
          }
          v174 = 0;
          v37 = v34(v33, &v174);
          if ( v37 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2062,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v37,
              (int)v154);
          v38 = v182;
          v39 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v182 + 48LL);
          v40 = v179;
          v179 = 0;
          if ( v40 )
            (*(void (__fastcall **)(__int64 *))(*v40 + 16))(v40);
          v41 = v39(v38, &v179);
          if ( v41 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2063,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v41,
              (int)v154);
          v42 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v179 + 24))(v179, &v177);
          if ( v42 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2064,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v42,
              (int)v154);
          lpFileName = 0;
          v187 = 0;
          v43 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&lpFileName);
          v44 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v174, 0, v43);
          if ( v44 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x206A,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v44,
              (int)v154);
          FileAttributesW = GetFileAttributesW(lpFileName);
          v46 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v47 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&v187);
          v48 = v196;
          if ( v196[3] > 7u )
            v48 = (_QWORD *)v196[0];
          v49 = CMiscHelpersT<CEmptyType>::CombinePath(v48, v174, 0, v47);
          if ( v49 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x206C,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v49,
              (int)v154);
          if ( v46 )
          {
            v53 = v164;
            if ( v164 )
            {
              v54 = to_wstring(&v158[1], lpFileName);
              std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
                v53,
                v171,
                v54);
              std::wstring::~wstring(&v158[1]);
            }
            if ( *(_QWORD *)&LogAdapter::g_Logger )
              ___LogNumObjects_V__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__V12__Logger_LogAdapter__AEAAJ_NW4LogLevel_1_QEBDAEBV__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__3_Z(
                LogAdapter::g_Logger,
                v50,
                v51,
                v52,
                (__int64)&lpFileName,
                (__int64)&v187);
            v166[0] = v187;
            v55 = -1;
            do
              ++v55;
            while ( *(_WORD *)(v187 + 2 * v55) );
            v166[1] = v55;
            v165[0] = lpFileName;
            v56 = -1;
            do
              ++v56;
            while ( lpFileName[v56] );
            v165[1] = v56;
            HardLinkWithFallback = CreateHardLinkWithFallback(v165, v166, 1);
            v58 = HardLinkWithFallback;
            if ( HardLinkWithFallback < 0 )
            {
              LODWORD(v176) = HardLinkWithFallback;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                ___LogNumObjects_V__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil___Logger_LogAdapter__AEAAJ_NW4LogLevel_1_QEBDAEBV__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil___Z(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to create hardlink for file from {0}",
                  &v187);
                v173 = (struct CDeploymentFileRequest *)&v176;
                v154 = &v173;
                LOBYTE(v59) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v59,
                  3,
                  ": {}");
              }
            }
            if ( v58 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x2080,
                (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                (const char *)(unsigned int)v58,
                (int)v154);
            v60 = v187;
            if ( v187 )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, (LPVOID)(v60 - 4));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            }
            v62 = lpFileName;
            if ( lpFileName )
            {
              v63 = GetProcessHeap();
              HeapFree(v63, 0, (LPVOID)(v62 - 2));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            }
            if ( v174 )
              CoTaskMemFree(v174);
            if ( pv )
              CoTaskMemFree(pv);
            if ( v179 )
              (*(void (__fastcall **)(__int64 *))(*v179 + 16))(v179);
          }
          else
          {
            v64 = to_wstring(&v158[1], pv);
            std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
              v198,
              v170,
              v64);
            std::wstring::~wstring(&v158[1]);
            if ( v170[8] )
            {
              v186 = 0;
              if ( !v193 )
              {
                v173 = (struct CDeploymentFileRequest *)v174;
                LogAdapter::TraceInfo<wchar_t const *>(
                  "UaLiteDownload: Non-container download requested, Filename: [{}]",
                  &v173);
                v186 = 0;
                v70 = CDeploymentFileRequest::Create((const wchar_t *)pv, v174, v174, 0, L"Canonical", 0, &v186);
                if ( v70 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x209A,
                    (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                    (const char *)(unsigned int)v70,
                    (int)v154);
                v71 = 0;
                for ( i = v186; v71 < v177; ++v71 )
                {
                  v178 = 0;
                  v155 = 0;
                  v181 = 0;
                  v188 = 0;
                  v73 = *v179;
                  v178 = 0;
                  v74 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v73 + 32))(v179, v71, &v178);
                  if ( v74 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x20A2,
                      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                      (const char *)(unsigned int)v74,
                      (int)v154);
                  v75 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v178 + 24LL))(v178, &v181);
                  if ( v75 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x20A3,
                      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                      (const char *)(unsigned int)v75,
                      (int)v154);
                  v76 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v178 + 32LL))(v178, &v188);
                  if ( v76 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x20A4,
                      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                      (const char *)(unsigned int)v76,
                      (int)v154);
                  v77 = CDeploymentFileRange::Create(v181, v188, &v155);
                  if ( v77 < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x20A5,
                      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                      (const char *)(unsigned int)v77,
                      (int)v154);
                  v78 = v155;
                  v155 = 0;
                  v173 = v78;
                  appended = CDeploymentFileRequest::AppendFileRange(i, &v173);
                  if ( appended < 0 )
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x20A6,
                      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                      (const char *)(unsigned int)appended,
                      (int)v154);
                  if ( v178 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v178 + 16LL))(v178);
                }
                v80 = v174;
                v81 = v184;
                v162 = &v184;
                v163 = 0;
                v82 = (char *)operator new(0x48u);
                v163 = v82;
                v83 = (char **)(v82 + 32);
                *((_OWORD *)v82 + 2) = 0;
                *((_QWORD *)v82 + 6) = 0;
                *((_QWORD *)v82 + 7) = 0;
                v84 = -1;
                do
                  ++v84;
                while ( v80[v84] );
                std::wstring::_Construct<1,wchar_t const *>(v83, v80);
                *((_QWORD *)v82 + 8) = i;
                if ( i )
                  (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)i + 8LL))(i);
                *(_QWORD *)v82 = v81;
                *((_QWORD *)v82 + 1) = v81;
                *((_QWORD *)v82 + 2) = v81;
                *((_WORD *)v82 + 12) = 0;
                v85 = std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
                        &v184,
                        &v158[1],
                        v83);
                v86 = *(_OWORD *)v85;
                v87 = *(_QWORD *)(v85 + 16);
                if ( !*(_BYTE *)(v87 + 25) )
                {
                  if ( *(_QWORD *)(v87 + 56) <= 7u )
                    v88 = v87 + 32;
                  else
                    v88 = *(_QWORD *)(v87 + 32);
                  v89 = *(_QWORD *)(v87 + 48);
                  if ( *((_QWORD *)v82 + 7) <= 7u )
                    v90 = v82 + 32;
                  else
                    v90 = *v83;
                  v91 = *((_QWORD *)v82 + 6);
                  v92 = v91;
                  if ( v91 > v89 )
                    v92 = *(_QWORD *)(v87 + 48);
                  v93 = _o__wcsnicmp(v90, v88, v92);
                  if ( v93 )
                  {
                    if ( v93 >= 0 )
                    {
LABEL_102:
                      v94 = *((_QWORD *)v82 + 8);
                      if ( v94 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
                      std::wstring::~wstring(v83);
                      operator delete(v82, (const struct std::nothrow_t *)0x48);
                      goto LABEL_107;
                    }
                  }
                  else if ( v91 >= v89 )
                  {
                    goto LABEL_102;
                  }
                }
                if ( v185 == 0x38E38E38E38E38ELL )
                  std::_Throw_tree_length_error();
                v163 = 0;
                *(_OWORD *)&v158[1] = v86;
                std::_Tree_val<std::_Tree_simple_types<std::wstring_view>>::_Insert_node(&v184, &v158[1], v82);
LABEL_107:
                if ( i )
                  (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)i + 16LL))(i);
                v25 = v176;
LABEL_110:
                v95 = v187;
                if ( v187 )
                {
                  v96 = GetProcessHeap();
                  HeapFree(v96, 0, (LPVOID)(v95 - 4));
                  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                }
                v97 = lpFileName;
                if ( lpFileName )
                {
                  v98 = GetProcessHeap();
                  HeapFree(v98, 0, (LPVOID)(v97 - 2));
                  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                }
                if ( v174 )
                  CoTaskMemFree(v174);
                if ( pv )
                  CoTaskMemFree(pv);
                if ( v179 )
                  (*(void (__fastcall **)(__int64 *))(*v179 + 16))(v179);
                goto LABEL_120;
              }
              v176 = 0;
              v106 = (const wchar_t *)v192;
              if ( v194 > 7 )
                v106 = v192[0];
              OffsetInOuterContainer = CDeploymentSession::GetOffsetInOuterContainer(
                                         this,
                                         v106,
                                         0,
                                         v174,
                                         (const wchar_t *)pv,
                                         &v176,
                                         (unsigned __int64 *)&v186);
              if ( OffsetInOuterContainer < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x20B5,
                  (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                  (const char *)(unsigned int)OffsetInOuterContainer,
                  (int)v154);
              v173 = (struct CDeploymentFileRequest *)v174;
              v111 = v192;
              if ( v194 > 7 )
                v111 = (wchar_t **)v192[0];
              v181 = (unsigned __int64)v111;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
                LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *,unsigned __int64,unsigned __int64>(
                  LogAdapter::g_Logger,
                  v108,
                  v109,
                  v110,
                  (__int64)&v181,
                  (__int64)&v173,
                  (__int64)&v176,
                  (__int64)&v186);
              v112 = *(_QWORD *)(std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
                                   &v184,
                                   &v158[1],
                                   v192)
                               + 16);
              if ( !*(_BYTE *)(v112 + 25) )
              {
                if ( *(_QWORD *)(v112 + 56) <= 7u )
                  v113 = v112 + 32;
                else
                  v113 = *(_QWORD *)(v112 + 32);
                v114 = *(_QWORD *)(v112 + 48);
                v115 = v192;
                if ( v194 > 7 )
                  v115 = (wchar_t **)v192[0];
                v116 = v193;
                v117 = v193;
                if ( v193 > v114 )
                  v117 = *(_QWORD *)(v112 + 48);
                v118 = _o__wcsnicmp(v115, v113, v117);
                if ( v118 )
                {
                  if ( v118 >= 0 )
                  {
LABEL_180:
                    std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
                      &v184,
                      &v158[1],
                      v192);
                    v135 = v159;
                    if ( *(_BYTE *)(v159 + 25) )
                      goto LABEL_238;
                    if ( *(_QWORD *)(v159 + 56) <= 7u )
                      v136 = v159 + 32;
                    else
                      v136 = *(_QWORD *)(v159 + 32);
                    v137 = *(_QWORD *)(v159 + 48);
                    v138 = v192;
                    if ( v194 > 7 )
                      v138 = (wchar_t **)v192[0];
                    v167[0] = v136;
                    v167[1] = v137;
                    v168[0] = v138;
                    v168[1] = v193;
                    if ( (unsigned __int8)WstringCaseInsensitiveCompare::operator()(v137, v168, v167) )
LABEL_238:
                      std::_Xout_of_range("invalid map<K, T> key");
                    v139 = *(struct ActionList **)(v135 + 64);
                    v158[1] = v139;
                    if ( v139 )
                      (*(void (__fastcall **)(struct ActionList *))(*(_QWORD *)v139 + 8LL))(v139);
                    if ( v177 )
                    {
                      for ( j = 0; j < v177; ++j )
                      {
                        v178 = 0;
                        v155 = 0;
                        v173 = 0;
                        v181 = 0;
                        v141 = *v179;
                        v178 = 0;
                        v142 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v141 + 32))(v179, j, &v178);
                        if ( v142 < 0 )
                          wil::details::in1diag3::Throw_Hr(
                            retaddr,
                            (void *)0x20D4,
                            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                            (const char *)(unsigned int)v142,
                            (int)v154);
                        v143 = (*(__int64 (__fastcall **)(__int64, struct CDeploymentFileRequest **))(*(_QWORD *)v178 + 24LL))(
                                 v178,
                                 &v173);
                        if ( v143 < 0 )
                          wil::details::in1diag3::Throw_Hr(
                            retaddr,
                            (void *)0x20D5,
                            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                            (const char *)(unsigned int)v143,
                            (int)v154);
                        v144 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v178 + 32LL))(
                                 v178,
                                 &v181);
                        if ( v144 < 0 )
                          wil::details::in1diag3::Throw_Hr(
                            retaddr,
                            (void *)0x20D6,
                            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                            (const char *)(unsigned int)v144,
                            (int)v154);
                        v145 = (char *)v173 + v176;
                        if ( (unsigned __int64)v173 + v176 < v176 )
                        {
                          v145 = 0;
                          v146 = -2147024362;
                          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
                        }
                        else
                        {
                          v146 = 0;
                        }
                        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v146);
                        if ( v146 < 0 )
                          wil::details::in1diag3::Throw_Hr(
                            retaddr,
                            (void *)0x20D7,
                            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                            (const char *)(unsigned int)v146,
                            (int)v154);
                        v147 = CDeploymentFileRange::Create((unsigned __int64)v145, v181, &v155);
                        if ( v147 < 0 )
                          wil::details::in1diag3::Throw_Hr(
                            retaddr,
                            (void *)0x20D8,
                            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                            (const char *)(unsigned int)v147,
                            (int)v154);
                        v148 = v155;
                        v155 = 0;
                        v188 = (unsigned __int64)v148;
                        v149 = CDeploymentFileRequest::AppendFileRange(v139, &v188);
                        if ( v149 < 0 )
                          wil::details::in1diag3::Throw_Hr(
                            retaddr,
                            (void *)0x20D9,
                            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                            (const char *)(unsigned int)v149,
                            (int)v154);
                        if ( v178 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v178 + 16LL))(v178);
                      }
                    }
                    else
                    {
                      v155 = 0;
                      v150 = CDeploymentFileRange::Create(v176, (unsigned __int64)v186, &v155);
                      if ( v150 < 0 )
                        wil::details::in1diag3::Throw_Hr(
                          retaddr,
                          (void *)0x20DF,
                          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                          (const char *)(unsigned int)v150,
                          (int)v154);
                      v151 = v155;
                      v155 = 0;
                      v173 = v151;
                      v152 = CDeploymentFileRequest::AppendFileRange(v139, &v173);
                      if ( v152 < 0 )
                        wil::details::in1diag3::Throw_Hr(
                          retaddr,
                          (void *)0x20E0,
                          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                          (const char *)(unsigned int)v152,
                          (int)v154);
                    }
                    if ( v139 )
                      (*(void (__fastcall **)(struct ActionList *))(*(_QWORD *)v139 + 16LL))(v139);
                    goto LABEL_110;
                  }
                }
                else if ( v116 >= v114 )
                {
                  goto LABEL_180;
                }
              }
              v173 = 0;
              v119 = (const wchar_t *)v192;
              if ( v194 > 7 )
                v119 = v192[0];
              v120 = (const wchar_t *)v192;
              if ( v194 > 7 )
                v120 = v192[0];
              v121 = (const wchar_t *)Src;
              if ( Src[3] > (wchar_t *)7 )
                v121 = Src[0];
              v122 = CDeploymentFileRequest::Create(v121, v120, v119, 0, L"Canonical", 0, &v173);
              if ( v122 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x20C6,
                  (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                  (const char *)(unsigned int)v122,
                  (int)v154);
              v123 = std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
                       &v184,
                       &v158[1],
                       v192);
              v124 = *(_OWORD *)v123;
              v125 = *(_QWORD *)(v123 + 16);
              v126 = v173;
              if ( !*(_BYTE *)(v125 + 25) )
              {
                if ( *(_QWORD *)(v125 + 56) <= 7u )
                  v127 = v125 + 32;
                else
                  v127 = *(_QWORD *)(v125 + 32);
                v128 = *(_QWORD *)(v125 + 48);
                v129 = v192;
                if ( v194 > 7 )
                  v129 = (wchar_t **)v192[0];
                v130 = v193;
                v131 = v193;
                if ( v193 > v128 )
                  v131 = *(_QWORD *)(v125 + 48);
                v132 = _o__wcsnicmp(v129, v127, v131);
                if ( v132 )
                {
                  if ( v132 >= 0 )
                  {
LABEL_178:
                    if ( v126 )
                      (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v126 + 16LL))(v126);
                    goto LABEL_180;
                  }
                }
                else if ( v130 >= v128 )
                {
                  goto LABEL_178;
                }
              }
              if ( v185 == 0x38E38E38E38E38ELL )
                std::_Throw_tree_length_error();
              v133 = v184;
              v160 = &v184;
              v161 = 0;
              v134 = operator new(0x48u);
              v161 = v134;
              std::wstring::wstring(v134 + 4, v192);
              v134[8] = v126;
              if ( v126 )
                (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v126 + 8LL))(v126);
              *v134 = v133;
              v134[1] = v133;
              v134[2] = v133;
              *((_WORD *)v134 + 12) = 0;
              v161 = 0;
              *(_OWORD *)&v158[1] = v124;
              std::_Tree_val<std::_Tree_simple_types<std::wstring_view>>::_Insert_node(&v184, &v158[1], v134);
              goto LABEL_178;
            }
            v173 = (struct CDeploymentFileRequest *)v174;
            v65 = v192;
            if ( v194 > 7 )
              v65 = (wchar_t **)v192[0];
            v181 = (unsigned __int64)v65;
            LogAdapter::TraceInfo<wchar_t const *,wchar_t *>(
              "UaLiteDownload: File already seen, Container Name: [{}], Filename: [{}]",
              &v181,
              &v173);
            v66 = v187;
            if ( v187 )
            {
              v67 = GetProcessHeap();
              HeapFree(v67, 0, (LPVOID)(v66 - 4));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            }
            v68 = lpFileName;
            if ( lpFileName )
            {
              v69 = GetProcessHeap();
              HeapFree(v69, 0, (LPVOID)(v68 - 2));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            }
            if ( v174 )
              CoTaskMemFree(v174);
            if ( pv )
              CoTaskMemFree(pv);
            if ( v179 )
              (*(void (__fastcall **)(__int64 *))(*v179 + 16))(v179);
          }
LABEL_120:
          if ( v182 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v182 + 16LL))(v182);
          LODWORD(v176) = ++v25;
          if ( v25 >= v175 )
          {
            v7 = v156;
            break;
          }
        }
      }
      UaLiteManagerDownloadRequest::~UaLiteManagerDownloadRequest((UaLiteManagerDownloadRequest *)v192);
      if ( v189 )
        (*(void (__fastcall **)(__int64 *))(*v189 + 16))(v189);
      v7 = (struct CDeploymentDownloadRequest *)((char *)v7 + 1);
      v156 = v7;
      v18 = v190[0];
    }
    while ( (unsigned __int64)v7 < 0x4EC4EC4EC4EC4EC5LL * (((char *)v190[1] - (char *)v190[0]) >> 3) );
    v13 = v158[0];
    v5 = v157;
  }
  v156 = 0;
  v99 = CDeploymentDownloadRequest::Create(v18, *((const wchar_t **)this + 68), 0, &v156);
  m = retaddr;
  if ( v99 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20E7,
      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
      (const char *)(unsigned int)v99,
      (int)v154);
  v101 = (wil::details::in1diag3 *)*v184;
  v102 = v156;
  while ( !*((_BYTE *)v101 + 25) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v101 + 8) + 8LL))(*((_QWORD *)v101 + 8));
    v173 = (struct CDeploymentFileRequest *)*((_QWORD *)v101 + 8);
    v103 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(&v157, &v173);
    v104 = CDeploymentDownloadRequest::AppendFileRequest(v102, v103);
    if ( v104 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x20ED,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v104,
        (int)v154);
    if ( v173 )
      (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v173 + 16LL))(v173);
    m = (wil::details::in1diag3 *)*((_QWORD *)v101 + 2);
    if ( *((_BYTE *)m + 25) )
    {
      for ( k = *((_QWORD *)v101 + 1);
            !*(_BYTE *)(k + 25) && v101 == *(wil::details::in1diag3 **)(k + 16);
            k = *(_QWORD *)(k + 8) )
      {
        v101 = (wil::details::in1diag3 *)k;
      }
      v101 = (wil::details::in1diag3 *)k;
    }
    else
    {
      v101 = (wil::details::in1diag3 *)*((_QWORD *)v101 + 2);
      for ( m = *(wil::details::in1diag3 **)m; !*((_BYTE *)m + 25); m = *(wil::details::in1diag3 **)m )
        v101 = m;
    }
  }
  *v5 = v102;
  LogAdapter::TraceAtLevel<char const *>(m, "{}: Exit", &v172);
  if ( v13 )
    (**(void (__fastcall ***)(struct ActionList *))v13)(v13);
  std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v198);
  std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<CDeploymentFileRequest,wil::err_exception_policy>,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CDeploymentFileRequest,wil::err_exception_policy>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<CDeploymentFileRequest,wil::err_exception_policy>,WstringCaseInsensitiveCompare,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<CDeploymentFileRequest,wil::err_exception_policy>>>,0>>(&v184);
  std::vector<UaLiteManagerDownloadRequest>::_Tidy(v190);
  return v5;
}

```

## disassembly

```asm
0x18004478c  mov     rax, rsp
0x18004478f  push    rbp
0x180044790  push    rsi
0x180044791  push    rdi
0x180044792  push    r12
0x180044794  push    r13
0x180044796  push    r14
0x180044798  push    r15
0x18004479a  lea     rbp, [rax-1B8h]
0x1800447a1  sub     rsp, 280h
0x1800447a8  mov     [rbp+1B0h+var_1C0], 0FFFFFFFFFFFFFFFEh
0x1800447b0  mov     [rax+18h], rbx
0x1800447b4  movaps  xmmword ptr [rax-48h], xmm6
0x1800447b8  mov     rax, cs:__security_cookie
0x1800447bf  xor     rax, rsp
0x1800447c2  mov     [rbp+1B0h+var_50], rax
0x1800447c9  mov     [rbp+1B0h+var_208], r9
0x1800447cd  mov     dil, r8b
0x1800447d0  mov     r12, rdx
0x1800447d3  mov     [rsp+2B0h+var_260], rdx
0x1800447d8  mov     r13, rcx
0x1800447db  mov     [rsp+2B0h+var_268], rdx
0x1800447e0  xor     r15d, r15d
0x1800447e3  xorps   xmm0, xmm0
0x1800447e6  movdqu  xmmword ptr [rbp+1B0h+var_F0], xmm0
0x1800447ee  mov     [rbp+1B0h+var_E0], r15
0x1800447f5  mov     [rbp+1B0h+var_120], r15
0x1800447fc  mov     [rbp+1B0h+var_118], r15
0x180044803  lea     ecx, [r15+48h]; Size
0x180044807  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004480c  mov     [rax], rax
0x18004480f  mov     [rax+8], rax
0x180044813  mov     [rax+10h], rax
0x180044817  mov     word ptr [rax+18h], 101h
0x18004481d  mov     [rbp+1B0h+var_120], rax
0x180044824  mov     [rbp+1B0h+var_60], r15
0x18004482b  mov     [rbp+1B0h+var_58], r15
0x180044832  lea     ecx, [r15+40h]; Size
0x180044836  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004483b  mov     [rax], rax
0x18004483e  mov     [rax+8], rax
0x180044842  mov     [rax+10h], rax
0x180044846  mov     word ptr [rax+18h], 101h
0x18004484c  mov     [rbp+1B0h+var_60], rax
0x180044853  mov     qword ptr [rsp+2B0h+var_258], r15
0x180044858  lea     rax, aCdeploymentses_130; "CDeploymentSession::CreateUaLiteDownloa"...
0x18004485f  mov     [rbp+1B0h+var_180], rax
0x180044863  lea     r8, [rbp+1B0h+var_180]
0x180044867  lea     rdx, aEnter; "{}: Enter"
0x18004486e  call    ??$TraceAtLevel@PEBD@LogAdapter@@YAXW4LogLevel@0@QEBDAEBQEBD@Z; LogAdapter::TraceAtLevel<char const *>(LogAdapter::LogLevel,char const * const,char const * const &)
0x180044873  lea     rax, [rbp+1B0h+var_180]
0x180044877  mov     [rbp+1B0h+var_1B8], rax
0x18004487b  mov     [rbp+1B0h+var_1B0], 1
0x18004487f  lea     r9, [rsp+2B0h+var_258]
0x180044884  mov     rdx, [r13+1F8h]
0x18004488b  xor     ecx, ecx
0x18004488d  call    LoadActionList
0x180044892  mov     rcx, [rbp+1B8h]; this
0x180044899  test    eax, eax
0x18004489b  js      loc_180045AAE
0x1800448a1  mov     r14, qword ptr [rsp+2B0h+var_258]
0x1800448a6  mov     rdx, r14; struct ActionList *
0x1800448a9  mov     rcx, r13; this
0x1800448ac  call    ?InitializeUaLite@CDeploymentSession@@QEAAXPEAUActionList@@@Z; CDeploymentSession::InitializeUaLite(ActionList *)
0x1800448b1  mov     rcx, [r13+290h]
0x1800448b8  test    rcx, rcx
0x1800448bb  jz      short loc_180044915
0x1800448bd  lea     rdx, [rbp+1B0h+var_198]
0x1800448c1  call    ?GenerateDownloadRequest@UaLiteManager@@QEAA?AV?$vector@UUaLiteManagerDownloadRequest@@V?$allocator@UUaLiteManagerDownloadRequest@@@std@@@std@@XZ; UaLiteManager::GenerateDownloadRequest(void)
0x1800448c6  mov     rbx, rax
0x1800448c9  lea     rax, [rbp+1B0h+var_F0]
0x1800448d0  cmp     rax, rbx
0x1800448d3  jz      short loc_18004490C
0x1800448d5  lea     rcx, [rbp+1B0h+var_F0]
0x1800448dc  call    ?_Tidy@?$vector@UUaLiteManagerDownloadRequest@@V?$allocator@UUaLiteManagerDownloadRequest@@@std@@@std@@AEAAXXZ; std::vector<UaLiteManagerDownloadRequest>::_Tidy(void)
0x1800448e1  mov     rax, [rbx]
0x1800448e4  mov     [rbp+1B0h+var_F0], rax
0x1800448eb  mov     rax, [rbx+8]
0x1800448ef  mov     [rbp+1B0h+var_F0+8], rax
0x1800448f6  mov     rax, [rbx+10h]
0x1800448fa  mov     [rbp+1B0h+var_E0], rax
0x180044901  mov     [rbx], r15
0x180044904  mov     [rbx+8], r15
0x180044908  mov     [rbx+10h], r15
0x18004490c  lea     rcx, [rbp+1B0h+var_198]
0x180044910  call    ?_Tidy@?$vector@UUaLiteManagerDownloadRequest@@V?$allocator@UUaLiteManagerDownloadRequest@@@std@@@std@@AEAAXXZ; std::vector<UaLiteManagerDownloadRequest>::_Tidy(void)
0x180044915  lea     rsi, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18004491c  test    dil, dil
0x18004491f  jz      short loc_180044981
0x180044921  mov     [rbp+1B0h+var_168], r15d
0x180044925  mov     dword ptr [rbp+1B0h+var_160], r15d
0x180044929  lea     r8, [rbp+1B0h+var_160]; enum MoUpdateRangeRequestState *
0x18004492d  lea     rdx, [rbp+1B0h+var_168]; int *
0x180044931  mov     rcx, r13; this
0x180044934  call    ?IsRangeRequestSupported@CDeploymentSession@@QEAAJPEAHPEAW4MoUpdateRangeRequestState@@@Z; CDeploymentSession::IsRangeRequestSupported(int *,MoUpdateRangeRequestState *)
0x180044939  mov     rcx, [rbp+1B8h]; this
0x180044940  test    eax, eax
0x180044942  jns     short loc_180044954
0x180044944  mov     r9d, eax; char *
0x180044947  mov     r8, rsi; unsigned int
0x18004494a  mov     edx, 204Bh; void *
0x18004494f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180044954  lea     rax, [rbp+1B0h+var_F0]
0x18004495b  mov     [rsp+2B0h+var_290], rax; int
0x180044960  mov     r9d, [rbp+1B0h+var_168]
0x180044964  xor     r8d, r8d
0x180044967  mov     rdx, r14
0x18004496a  mov     rcx, r13; this
0x18004496d  call    ?ProcessSandboxContainerPayload@CDeploymentSession@@QEAAJPEAUActionList@@HHPEAV?$vector@UUaLiteManagerDownloadRequest@@V?$allocator@UUaLiteManagerDownloadRequest@@@std@@@std@@@Z; CDeploymentSession::ProcessSandboxContainerPayload(ActionList *,int,int,std::vector<UaLiteManagerDownloadRequest> *)
0x180044972  mov     rcx, [rbp+1B8h]; this
0x180044979  test    eax, eax
0x18004497b  js      loc_180045AC3
0x180044981  mov     [rsp+2B0h+var_268], r15
0x180044986  mov     rax, [rbp+1B0h+var_F0+8]
0x18004498d  mov     rcx, [rbp+1B0h+var_F0]
0x180044994  sub     rax, rcx
0x180044997  sar     rax, 3
0x18004499b  mov     rdx, 4EC4EC4EC4EC4EC5h
0x1800449a5  imul    rax, rdx
0x1800449a9  test    rax, rax
0x1800449ac  jz      loc_180045403
0x1800449b2  xor     r14d, r14d
0x1800449b5  mov     [rbp+1B0h+var_F8], r14
0x1800449bc  mov     [rbp+1B0h+var_168], r14d
0x1800449c0  imul    rbx, r15, 68h ; 'h'
0x1800449c4  add     rbx, rcx
0x1800449c7  lea     rax, [rbp+1B0h+var_D0]
0x1800449ce  mov     [rbp+1B0h+var_178], rax
0x1800449d2  mov     rdx, rbx
0x1800449d5  lea     rcx, [rbp+1B0h+var_D0]
0x1800449dc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800449e1  nop
0x1800449e2  lea     rdx, [rbx+20h]
0x1800449e6  lea     rcx, [rbp+1B0h+Src]
0x1800449ed  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800449f2  nop
0x1800449f3  lea     rdx, [rbx+40h]
0x1800449f7  lea     rcx, [rbp+1B0h+var_90]
0x1800449fe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180044a03  mov     rbx, [rbx+60h]
0x180044a07  mov     [rbp+1B0h+var_70], rbx
0x180044a0e  test    rbx, rbx
0x180044a11  jz      short loc_180044A29
0x180044a13  mov     rax, [rbx]
0x180044a16  mov     rcx, rbx
0x180044a19  mov     rax, [rax+8]
0x180044a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a22  mov     rbx, [rbp+1B0h+var_70]
0x180044a29  mov     rax, [rbx]
0x180044a2c  mov     rdi, [rax+28h]
0x180044a30  mov     rcx, [rbp+1B0h+var_F8]
0x180044a37  mov     [rbp+1B0h+var_F8], r14
0x180044a3e  test    rcx, rcx
0x180044a41  jz      short loc_180044A50
0x180044a43  mov     rax, [rcx]
0x180044a46  mov     rax, [rax+10h]
0x180044a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a4f  nop
0x180044a50  lea     rdx, [rbp+1B0h+var_F8]
0x180044a57  mov     rcx, rbx
0x180044a5a  mov     rax, rdi
0x180044a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a62  mov     rcx, [rbp+1B8h]; this
0x180044a69  test    eax, eax
0x180044a6b  js      loc_180045CA7
0x180044a71  mov     rcx, [rbp+1B0h+var_F8]
0x180044a78  mov     rax, [rcx]
0x180044a7b  lea     rdx, [rbp+1B0h+var_168]
0x180044a7f  mov     rax, [rax+18h]
0x180044a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a88  mov     rcx, [rbp+1B8h]; this
0x180044a8f  test    eax, eax
0x180044a91  js      loc_180045C96
0x180044a97  mov     r12d, r14d
0x180044a9a  mov     dword ptr [rbp+1B0h+var_160], r14d
0x180044a9e  cmp     [rbp+1B0h+var_168], r14d
0x180044aa2  jbe     loc_18004539F
0x180044aa8  mov     [rbp+1B0h+var_130], r14
0x180044aaf  mov     [rbp+1B0h+var_148], r14
0x180044ab3  mov     [rbp+1B0h+pv], r14
0x180044ab7  mov     [rbp+1B0h+var_170], r14
0x180044abb  mov     [rbp+1B0h+var_158], r14d
0x180044abf  mov     rcx, [rbp+1B0h+var_F8]
0x180044ac6  mov     rax, [rcx]
0x180044ac9  mov     [rbp+1B0h+var_130], r14
0x180044ad0  lea     r8, [rbp+1B0h+var_130]
0x180044ad7  mov     edx, r12d
0x180044ada  mov     rax, [rax+20h]
0x180044ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ae3  mov     rcx, [rbp+1B8h]; this
0x180044aea  test    eax, eax
0x180044aec  js      loc_180045C85
0x180044af2  mov     r14, [rbp+1B0h+var_130]
0x180044af9  mov     rax, [r14]
0x180044afc  mov     r15, [rax+18h]
0x180044b00  mov     rdi, [rbp+1B0h+pv]
0x180044b04  xor     ebx, ebx
0x180044b06  test    rdi, rdi
0x180044b09  jz      short loc_180044B38
0x180044b0b  call    cs:__imp_GetLastError
0x180044b12  nop     dword ptr [rax+rax+00h]
0x180044b17  mov     ebx, eax
0x180044b19  mov     rcx, rdi; pv
0x180044b1c  call    cs:__imp_CoTaskMemFree
0x180044b23  nop     dword ptr [rax+rax+00h]
0x180044b28  mov     ecx, ebx; dwErrCode
0x180044b2a  call    cs:__imp_SetLastError
0x180044b31  nop     dword ptr [rax+rax+00h]
0x180044b36  xor     ebx, ebx
0x180044b38  mov     [rbp+1B0h+pv], rbx
0x180044b3c  lea     rdx, [rbp+1B0h+pv]
0x180044b40  mov     rcx, r14
0x180044b43  mov     rax, r15
0x180044b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044b4b  mov     rcx, [rbp+1B8h]; this
0x180044b52  test    eax, eax
0x180044b54  js      loc_180045C74
0x180044b5a  mov     r14, [rbp+1B0h+var_130]
0x180044b61  mov     rax, [r14]
0x180044b64  mov     r15, [rax+28h]
0x180044b68  mov     rdi, [rbp+1B0h+var_170]
0x180044b6c  test    rdi, rdi
0x180044b6f  jz      short loc_180044B9E
0x180044b71  call    cs:__imp_GetLastError
0x180044b78  nop     dword ptr [rax+rax+00h]
0x180044b7d  mov     ebx, eax
0x180044b7f  mov     rcx, rdi; pv
0x180044b82  call    cs:__imp_CoTaskMemFree
0x180044b89  nop     dword ptr [rax+rax+00h]
0x180044b8e  mov     ecx, ebx; dwErrCode
0x180044b90  call    cs:__imp_SetLastError
0x180044b97  nop     dword ptr [rax+rax+00h]
0x180044b9c  xor     ebx, ebx
0x180044b9e  mov     [rbp+1B0h+var_170], rbx
0x180044ba2  lea     rdx, [rbp+1B0h+var_170]
0x180044ba6  mov     rcx, r14
0x180044ba9  mov     rax, r15
0x180044bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bb1  mov     rcx, [rbp+1B8h]; this
0x180044bb8  xor     r14d, r14d
0x180044bbb  test    eax, eax
0x180044bbd  js      loc_180045C63
0x180044bc3  mov     rbx, [rbp+1B0h+var_130]
0x180044bca  mov     rax, [rbx]
0x180044bcd  mov     rdi, [rax+30h]
0x180044bd1  mov     rcx, [rbp+1B0h+var_148]
0x180044bd5  mov     [rbp+1B0h+var_148], r14
0x180044bd9  test    rcx, rcx
0x180044bdc  jz      short loc_180044BEB
0x180044bde  mov     rax, [rcx]
0x180044be1  mov     rax, [rax+10h]
0x180044be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bea  nop
0x180044beb  lea     rdx, [rbp+1B0h+var_148]
0x180044bef  mov     rcx, rbx
0x180044bf2  mov     rax, rdi
0x180044bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bfa  mov     rcx, [rbp+1B8h]; this
0x180044c01  test    eax, eax
0x180044c03  js      loc_180045C52
0x180044c09  mov     rcx, [rbp+1B0h+var_148]
0x180044c0d  mov     rax, [rcx]
0x180044c10  lea     rdx, [rbp+1B0h+var_158]
0x180044c14  mov     rax, [rax+18h]
0x180044c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c1d  mov     rcx, [rbp+1B8h]; this
0x180044c24  test    eax, eax
0x180044c26  js      loc_180045C41
0x180044c2c  mov     [rbp+1B0h+lpFileName], r14
0x180044c33  mov     [rbp+1B0h+var_108], r14
0x180044c3a  lea     rcx, [rbp+1B0h+lpFileName]
0x180044c41  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ
0x180044c46  mov     r9, rax
0x180044c49  xor     r8d, r8d
0x180044c4c  mov     rdx, [rbp+1B0h+var_170]
0x180044c50  mov     rcx, [r13+1E8h]
0x180044c57  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x180044c5c  mov     rcx, [rbp+1B8h]; this
0x180044c63  test    eax, eax
0x180044c65  js      loc_180045C30
0x180044c6b  mov     rcx, [rbp+1B0h+lpFileName]; lpFileName
0x180044c72  call    cs:__imp_GetFileAttributesW
0x180044c79  nop     dword ptr [rax+rax+00h]
0x180044c7e  mov     ebx, eax
0x180044c80  cmp     eax, 0FFFFFFFFh
0x180044c83  jz      short loc_180044C8F
0x180044c85  shr     ebx, 4
0x180044c88  not     ebx
0x180044c8a  and     ebx, 1
0x180044c8d  jmp     short loc_180044C92
0x180044c8f  mov     ebx, r14d
0x180044c92  xor     ecx, ecx
0x180044c94  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180044c99  xor     ecx, ecx
0x180044c9b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180044ca0  lea     rcx, [rbp+1B0h+var_108]
0x180044ca7  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ
0x180044cac  lea     rcx, [rbp+1B0h+var_90]
0x180044cb3  cmp     [rbp+1B0h+var_78], 7
0x180044cbb  cmova   rcx, [rbp+1B0h+var_90]
  ... truncated ...
```
