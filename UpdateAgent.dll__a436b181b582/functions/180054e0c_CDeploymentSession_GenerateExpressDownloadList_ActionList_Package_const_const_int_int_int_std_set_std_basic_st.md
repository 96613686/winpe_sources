# CDeploymentSession::GenerateExpressDownloadList(ActionList::Package const * const,int,int,int,std::set<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,WstringCaseInsensitiveCompare,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> *,CDeploymentDownloadRequest *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,int *)

- ea: `0x180054e0c`
- end: `0x1800573f4`
- name: `?GenerateExpressDownloadList@CDeploymentSession@@QEAAJQEBUPackage@ActionList@@HHHPEAV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@PEAVCDeploymentDownloadRequest@@PEA_K33PEAH@Z`
- size: `9704`
- prototype: `__int64 __usercall@<rax>(CDeploymentSession *this@<rcx>, int, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004f0b0`

## callees

- `0x1800059d0`
- `0x180006a18`
- `0x180007d54`
- `0x180012d94`
- `0x180012fe4`
- `0x18001efc8`
- `0x18001fc58`
- `0x1800201cc`
- `0x180022ab8`
- `0x180022c30`
- `0x180022e2c`
- `0x180022f6c`
- `0x180022fa8`
- `0x180023b20`
- `0x180024930`
- `0x180026af8`
- `0x1800281d4`
- `0x18003557c`
- `0x180035a80`
- `0x180035b4c`
- `0x180035bf0`
- `0x180038ecc`
- `0x180039f90`
- `0x18003c418`
- `0x18003d3b8`
- `0x18003e4a4`
- `0x18003e600`
- `0x18004d8d0`
- `0x180054e0c`
- `0x18005e9e8`
- `0x1800613b4`
- `0x180062d24`
- `0x180062e60`
- `0x180077664`
- `0x180078b4c`
- `0x180078b9c`
- `0x1800918a8`
- `0x180094d0c`
- `0x18009a9e0`
- `0x1801e9f20`
- `0x180220c78`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180055744`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180056b30`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180055744`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180056b30`
- `OLEAUT32!__imp_SysFreeString` at `0x180057292`
- `OLEAUT32!__imp_SysFreeString` at `0x180057292`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800554af`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180056903`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800554af`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180056903`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180055407`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180055d4d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180055ef9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180055407`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180055d4d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180055ef9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055165`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055387`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055cc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055d92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055e76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055165`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055387`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055cc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055d92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055e76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005539c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055cd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055da8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055e8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005539c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055cd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055da8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055e8a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055179`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800554bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800554bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056913`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005564b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800556fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055770`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005581d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056b92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056bde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005564b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800556fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055770`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005581d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056b92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056bde`

## string_xrefs

- `0x18005737b`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18005738f`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800573a4`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800573b8`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800573cd`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x1800573e1`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x180056783`: `    Already expanded`

## pseudocode

```c
// Hidden C++ exception states: #wind=54
__int64 __fastcall CDeploymentSession::GenerateExpressDownloadList(
        CDeploymentSession *this,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        wchar_t *a6,
        __int64 a7,
        unsigned __int64 *a8,
        unsigned __int64 *a9,
        unsigned __int64 *a10,
        int *a11)
{
  struct ActionList::Package *v11; // r15
  int v13; // r14d
  struct CDeploymentFileRange *v14; // rsi
  __int64 v15; // r12
  WCHAR *v16; // r13
  __int64 v17; // rcx
  signed int ShouldDownloadRangelessFile; // ebx
  __int64 updated; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // ecx
  unsigned int v23; // esi
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  size_t v28; // rbx
  HANDLE ProcessHeap; // rax
  char *v30; // rax
  int v31; // esi
  __int64 v32; // rcx
  int PackageFileListPath; // eax
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // r8
  int v37; // ecx
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // r9
  __int64 v41; // r15
  int *v42; // rdx
  HANDLE v43; // rax
  int v44; // eax
  DWORD FileAttributesW; // eax
  BOOL v46; // esi
  int FileSize; // eax
  __int64 v48; // rdx
  __int64 v49; // rcx
  signed int LastError; // eax
  int v51; // eax
  unsigned int v52; // esi
  const wchar_t **v53; // rbx
  int v54; // eax
  __int64 v55; // rcx
  __int64 v56; // rcx
  int v57; // eax
  __int64 v58; // rdx
  struct CDeploymentFileRequest *v59; // rcx
  int v60; // eax
  __int64 v61; // rcx
  __int64 v62; // rcx
  int v63; // eax
  __int64 v64; // rdx
  struct CDeploymentFileRequest *v65; // rdx
  struct CDeploymentFileRequest *v66; // rsi
  int v67; // eax
  int OffsetInOuterContainer; // eax
  int v69; // eax
  struct CDeploymentFileRange *v70; // rax
  int appended; // eax
  __int64 v72; // rcx
  int v73; // esi
  struct CDeploymentFileRequest *v74; // rcx
  int v75; // eax
  int v76; // eax
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  const wchar_t *v81; // r9
  int v82; // eax
  __int64 v83; // r14
  char *v84; // rbx
  WCHAR *v85; // rbx
  HANDLE v86; // rax
  int v87; // eax
  DWORD v88; // eax
  BOOL v89; // ebx
  HANDLE v90; // rax
  int v91; // eax
  int v92; // eax
  __int64 v93; // rsi
  char *v94; // r12
  WCHAR *v95; // rbx
  HANDLE v96; // rax
  int v97; // eax
  DWORD v98; // eax
  BOOL v99; // ebx
  int v100; // eax
  unsigned __int64 v101; // r14
  __int64 v102; // rcx
  unsigned int i; // r15d
  __int64 v104; // rbx
  __int64 v105; // rsi
  __int64 v106; // r14
  __int64 v107; // rcx
  __int64 v108; // rdx
  __int64 v109; // r8
  __int64 v110; // rax
  int PackageExpanderProgress; // eax
  __int64 v112; // r9
  __int64 v113; // rcx
  __int64 v114; // rdx
  __int64 v115; // rcx
  __int64 v116; // rcx
  const wchar_t *v117; // r9
  __int64 v118; // rcx
  int v119; // esi
  __int64 v120; // rcx
  int v121; // eax
  int *v122; // rdx
  __int64 v123; // rax
  const WCHAR *v124; // rbx
  const WCHAR *v125; // rdx
  __int64 v126; // r12
  __int64 v127; // r8
  const WCHAR *v128; // rdx
  __int64 v129; // r8
  __int64 v130; // r8
  __int64 v131; // r8
  int *v132; // rdx
  int v133; // eax
  LPVOID v134; // rdx
  unsigned int v135; // eax
  int v136; // ecx
  __int64 v137; // rdx
  utl::_RefCountBase *v138; // r15
  int v139; // eax
  int *v140; // rdx
  int v141; // eax
  int *v142; // rdx
  __int64 v143; // rcx
  unsigned __int64 v144; // r14
  __int64 v145; // rcx
  unsigned int v146; // r14d
  int v147; // eax
  __int64 v148; // r12
  __int64 v149; // r15
  int v150; // eax
  const WCHAR *v151; // r14
  int v152; // eax
  int *v153; // rdx
  __int64 v154; // rcx
  signed int v155; // eax
  const wchar_t *v156; // r14
  int v157; // eax
  const wchar_t *v158; // r13
  wchar_t *v159; // rbx
  __int64 v160; // rax
  int v161; // eax
  int v162; // eax
  unsigned int j; // ebx
  int v164; // eax
  int v165; // eax
  int v166; // eax
  __int64 v167; // rcx
  struct CDeploymentFileRequest *v168; // rbx
  __int64 v169; // rcx
  int v170; // eax
  __int64 v171; // rcx
  int v172; // eax
  __int64 v173; // rcx
  int v174; // ebx
  unsigned int k; // r15d
  int v176; // eax
  __int64 v177; // rdx
  __int64 v178; // r14
  __int64 v179; // r12
  int v180; // eax
  __int64 v181; // rax
  int v182; // eax
  __int64 v183; // rax
  int v184; // eax
  __int64 v185; // rcx
  __int64 v186; // rcx
  const wchar_t *v187; // r9
  __int64 v188; // rcx
  __int64 v189; // rcx
  unsigned int v190; // r14d
  __int64 v191; // rcx
  __int64 v192; // rcx
  unsigned __int64 v193; // rsi
  __int64 v194; // rcx
  unsigned __int64 v195; // r15
  const char *v196; // r9
  __int64 result; // rax
  wchar_t *v198; // [rsp+20h] [rbp-288h]
  int v199; // [rsp+20h] [rbp-288h]
  wchar_t *v200; // [rsp+20h] [rbp-288h]
  unsigned __int64 *v201; // [rsp+28h] [rbp-280h]
  const WCHAR *v202; // [rsp+50h] [rbp-258h] BYREF
  unsigned int v203; // [rsp+58h] [rbp-250h]
  int v204; // [rsp+5Ch] [rbp-24Ch]
  BOOL v205; // [rsp+60h] [rbp-248h] BYREF
  int v206; // [rsp+64h] [rbp-244h]
  wchar_t *Src; // [rsp+68h] [rbp-240h]
  unsigned __int64 v208; // [rsp+70h] [rbp-238h] BYREF
  unsigned __int64 v209; // [rsp+78h] [rbp-230h]
  int v210; // [rsp+80h] [rbp-228h]
  int v211; // [rsp+84h] [rbp-224h]
  struct CDeploymentFileRequest *v212; // [rsp+88h] [rbp-220h] BYREF
  struct IPackageExpanderProgress *v213; // [rsp+90h] [rbp-218h] BYREF
  struct CDeploymentFileRange *v214; // [rsp+98h] [rbp-210h] BYREF
  __int64 v215; // [rsp+A0h] [rbp-208h] BYREF
  unsigned __int64 v216; // [rsp+A8h] [rbp-200h]
  __int64 v217; // [rsp+B0h] [rbp-1F8h]
  struct ActionList::Package *v218; // [rsp+B8h] [rbp-1F0h]
  char v219[8]; // [rsp+C0h] [rbp-1E8h] BYREF
  char *v220; // [rsp+C8h] [rbp-1E0h] BYREF
  unsigned __int64 v221; // [rsp+D0h] [rbp-1D8h]
  __int64 v222; // [rsp+D8h] [rbp-1D0h] BYREF
  __int64 v223; // [rsp+E0h] [rbp-1C8h]
  utl::_RefCountBase *v224[2]; // [rsp+E8h] [rbp-1C0h] BYREF
  __int64 v225; // [rsp+F8h] [rbp-1B0h] BYREF
  __int64 v226; // [rsp+100h] [rbp-1A8h]
  __int128 v227; // [rsp+108h] [rbp-1A0h] BYREF
  __int128 v228; // [rsp+118h] [rbp-190h]
  _OWORD v229[2]; // [rsp+128h] [rbp-180h] BYREF
  unsigned __int64 *v230; // [rsp+148h] [rbp-160h]
  unsigned __int64 *v231; // [rsp+150h] [rbp-158h]
  int *v232; // [rsp+158h] [rbp-150h]
  __int64 v233; // [rsp+160h] [rbp-148h] BYREF
  unsigned __int64 *v234; // [rsp+168h] [rbp-140h]
  _OWORD v235[2]; // [rsp+170h] [rbp-138h] BYREF
  _OWORD v236[2]; // [rsp+190h] [rbp-118h] BYREF
  _OWORD v237[2]; // [rsp+1B0h] [rbp-F8h] BYREF
  __int64 v238; // [rsp+1D0h] [rbp-D8h]
  struct CDeploymentFileRange *v239; // [rsp+1D8h] [rbp-D0h] BYREF
  struct CDeploymentFileRequest *v240; // [rsp+1E0h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+1E8h] [rbp-C0h] BYREF
  struct CDeploymentFileRequest *v242; // [rsp+1F0h] [rbp-B8h] BYREF
  unsigned int v243; // [rsp+1F8h] [rbp-B0h] BYREF
  LPVOID v244; // [rsp+200h] [rbp-A8h] BYREF
  char *v245; // [rsp+208h] [rbp-A0h] BYREF
  int v246; // [rsp+210h] [rbp-98h] BYREF
  LPCWSTR lpFileName; // [rsp+218h] [rbp-90h] BYREF
  LPCWSTR v248; // [rsp+220h] [rbp-88h] BYREF
  __int64 v249; // [rsp+228h] [rbp-80h] BYREF
  LPCWSTR v250; // [rsp+230h] [rbp-78h] BYREF
  wchar_t *v251; // [rsp+238h] [rbp-70h] BYREF
  __int64 v252; // [rsp+240h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+248h] [rbp-60h] BYREF
  __int64 v254; // [rsp+250h] [rbp-58h] BYREF
  __int64 v255; // [rsp+258h] [rbp-50h] BYREF
  __int64 v256; // [rsp+260h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v238 = -2;
  try
  {
    v210 = a4;
    v204 = a3;
    v11 = (struct ActionList::Package *)a2;
    v218 = (struct ActionList::Package *)a2;
    v13 = (int)a6;
    Src = a6;
    v217 = a7;
    v234 = a8;
    v230 = a9;
    v231 = a10;
    v232 = a11;
    v252 = 0;
    v14 = 0;
    v239 = 0;
    v240 = 0;
    v220 = 0;
    v225 = 0;
    v226 = 0;
    v248 = 0;
    v233 = 0;
    *(_OWORD *)v224 = 0;
    v222 = 0;
    v223 = 0;
    v15 = 0;
    v249 = 0;
    v213 = 0;
    bstrString = 0;
    v256 = 0;
    v255 = 0;
    v215 = 0;
    v208 = 0;
    v254 = 0;
    v16 = 0;
    lpFileName = 0;
    v250 = 0;
    v251 = 0;
    v205 = 0;
    LODWORD(v212) = 0;
    v246 = 0;
    if ( !a2 )
    {
      v17 = *((_QWORD *)this + 75);
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v17 )
      {
LABEL_4:
        updated = 0;
LABEL_8:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
        goto LABEL_439;
      }
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v17,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GenerateExpressDownloadList",
                                1458,
                                -2147024809);
LABEL_6:
      if ( (int)updated < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated, v20);
      goto LABEL_8;
    }
    if ( !a7 )
    {
      v21 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v21 )
        goto LABEL_4;
      v199 = 1459;
      goto LABEL_12;
    }
    if ( !a8 )
    {
      v21 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v21 )
        goto LABEL_4;
      v199 = 1460;
      goto LABEL_12;
    }
    if ( !a9 )
    {
      v21 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v21 )
        goto LABEL_4;
      v199 = 1461;
      goto LABEL_12;
    }
    if ( !a10 )
    {
      v21 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v21 )
        goto LABEL_4;
      v199 = 1462;
      goto LABEL_12;
    }
    if ( !a11 )
    {
      v21 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v21 )
        goto LABEL_4;
      v199 = 1463;
LABEL_12:
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v21,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GenerateExpressDownloadList",
                                v199,
                                -2147024809);
      goto LABEL_6;
    }
    v22 = *(_DWORD *)(a2 + 120);
    if ( v22 )
    {
      v23 = 88 * v22;
      v24 = 88 * v22 / 0x58u;
      if ( (_DWORD)v24 != v22 )
      {
        v23 = 0;
        ShouldDownloadRangelessFile = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v24);
        v11 = v218;
        goto LABEL_30;
      }
    }
    else
    {
      v23 = 0;
    }
    ShouldDownloadRangelessFile = 0;
LABEL_30:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
    if ( ShouldDownloadRangelessFile < 0 )
    {
      v25 = *((_QWORD *)this + 75);
      v16 = 0;
      if ( !v25 )
        goto LABEL_32;
      v26 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                            v25,
                            4,
                            L"%s(%d): Result = 0x%X",
                            L"CDeploymentSession::GenerateExpressDownloadList",
                            1470,
                            ShouldDownloadRangelessFile);
      goto LABEL_34;
    }
    v28 = v23;
    ProcessHeap = GetProcessHeap();
    v30 = (char *)HeapAlloc(ProcessHeap, 0, v23);
    v245 = v30;
    v31 = 0;
    if ( !v30 )
    {
      v16 = 0;
      v220 = 0;
      v32 = *((_QWORD *)this + 75);
      ShouldDownloadRangelessFile = -2147024882;
      if ( v32 )
      {
        LODWORD(v201) = -2147024882;
        LODWORD(v198) = 1472;
        goto LABEL_40;
      }
      goto LABEL_32;
    }
    v220 = v30;
    memset_0(v30, 0, v28);
    if ( !a5 )
    {
      PackageFileListPath = CDeploymentSession::GetPackageFileListPath(this, v11, &v251);
      ShouldDownloadRangelessFile = PackageFileListPath;
      if ( PackageFileListPath < 0 )
      {
        v32 = *((_QWORD *)this + 75);
        v16 = 0;
        if ( v32 )
        {
          LODWORD(v201) = PackageFileListPath;
          LODWORD(v198) = 1480;
          goto LABEL_40;
        }
        goto LABEL_32;
      }
    }
    v34 = *((_QWORD *)this + 75);
    if ( v34 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v34, 2, L"Package: [%s]", *((_QWORD *)v11 + 7));
    v35 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v217 + 40LL))(v217, &v252);
    ShouldDownloadRangelessFile = v35;
    v36 = 0;
    if ( v35 < 0 )
    {
      v32 = *((_QWORD *)this + 75);
      v16 = 0;
      if ( v32 )
      {
        LODWORD(v201) = v35;
        LODWORD(v198) = 1490;
        goto LABEL_40;
      }
      goto LABEL_32;
    }
    v211 = 0;
    v221 = 0;
    v37 = 0;
    v206 = 0;
    v243 = 0;
    v209 = 0;
    v216 = 0;
    v38 = 0;
    v203 = 0;
    v39 = 0;
    v40 = 1;
    while ( 1 )
    {
      LODWORD(v202) = v39;
      if ( (unsigned int)v39 >= *((_DWORD *)v11 + 30) )
        break;
      v41 = *((_QWORD *)v218 + 14) + 184 * v39;
      if ( *(_BYTE *)(v41 + 153) )
      {
        if ( !a5 )
        {
          ShouldDownloadRangelessFile = CDeploymentSession::ShouldDownloadRangelessFile(
                                          (_DWORD)this,
                                          (_DWORD)v251,
                                          v41,
                                          v13,
                                          (__int64)&v212,
                                          (__int64)&v215);
          if ( ShouldDownloadRangelessFile < 0 )
          {
            v32 = *((_QWORD *)this + 75);
            v16 = 0;
            if ( v32 )
            {
              LODWORD(v201) = ShouldDownloadRangelessFile;
              LODWORD(v198) = 1505;
              goto LABEL_40;
            }
            goto LABEL_32;
          }
          if ( (_DWORD)v212 )
          {
            if ( v16 )
            {
              v43 = GetProcessHeap();
              HeapFree(v43, 0, v16 - 2);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              v16 = 0;
              lpFileName = 0;
            }
            v44 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)(v41 + 80), 0, &lpFileName);
            ShouldDownloadRangelessFile = v44;
            if ( v44 < 0 )
            {
              v32 = *((_QWORD *)this + 75);
              if ( v32 )
              {
                LODWORD(v201) = v44;
                LODWORD(v198) = 1512;
                goto LABEL_40;
              }
              goto LABEL_32;
            }
            v16 = (WCHAR *)lpFileName;
            FileAttributesW = GetFileAttributesW(lpFileName);
            v46 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
            v205 = v46;
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            if ( !v46 )
              goto LABEL_83;
            FileSize = CMoUpdateHelpersT<CEmptyType>::GetFileSize(v16, &v255);
            ShouldDownloadRangelessFile = FileSize;
            if ( FileSize < 0 )
            {
              v32 = *((_QWORD *)this + 75);
              v16 = 0;
              if ( v32 )
              {
                LODWORD(v201) = FileSize;
                LODWORD(v198) = 1517;
                goto LABEL_40;
              }
              goto LABEL_32;
            }
            ShouldDownloadRangelessFile = 0;
            if ( !v255 )
            {
              v49 = *((_QWORD *)this + 75);
              if ( v49 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v49,
                  2,
                  L"    Deleting zero byte rangeless file: [%s]",
                  v16);
              if ( !DeleteFileW(v16) )
              {
                LastError = GetLastError();
                ShouldDownloadRangelessFile = LastError;
                v16 = 0;
                if ( LastError )
                {
                  if ( LastError > 0 )
                    ShouldDownloadRangelessFile = (unsigned __int16)LastError | 0x80070000;
                }
                else
                {
                  ShouldDownloadRangelessFile = -2147467259;
                }
                v26 = 0;
                if ( ShouldDownloadRangelessFile < 0 && *((_QWORD *)this + 75) )
                {
                  LODWORD(v201) = ShouldDownloadRangelessFile;
                  LODWORD(v198) = 1521;
                  v32 = *((_QWORD *)this + 75);
                  goto LABEL_40;
                }
                goto LABEL_36;
              }
              v211 = 1;
              v46 = 0;
              v205 = 0;
            }
            if ( !v46 )
            {
LABEL_83:
              LODWORD(v244) = 0;
              if ( v240 )
              {
                (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v240 + 16LL))(v240);
                v240 = 0;
              }
              if ( *(_QWORD *)(v41 + 48) )
              {
                v51 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v252 + 24LL))(v252, &v244);
                ShouldDownloadRangelessFile = v51;
                if ( v51 < 0 )
                {
                  v32 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( v32 )
                  {
                    LODWORD(v201) = v51;
                    LODWORD(v198) = 1538;
                    goto LABEL_40;
                  }
                  goto LABEL_32;
                }
                v52 = 0;
                v53 = (const wchar_t **)(v41 + 64);
                while ( 1 )
                {
                  if ( v52 >= (unsigned int)v244 )
                    goto LABEL_115;
                  v242 = 0;
                  pv = 0;
                  v54 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct CDeploymentFileRequest **))(*(_QWORD *)v252 + 32LL))(
                          v252,
                          v52,
                          &v242);
                  ShouldDownloadRangelessFile = v54;
                  if ( v54 < 0 )
                  {
                    v55 = *((_QWORD *)this + 75);
                    v16 = 0;
                    if ( v55 )
                    {
                      LODWORD(v201) = v54;
                      LODWORD(v198) = 1545;
                      v57 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v55,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::GenerateExpressDownloadList",
                              v198,
                              v201);
                      v56 = (unsigned int)v57;
                      if ( v57 < 0 )
                        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v57, v58);
                    }
                    else
                    {
                      v56 = 0;
                    }
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v56);
                    if ( pv )
                    {
                      CoTaskMemFree(pv);
                      pv = 0;
                    }
                    v59 = v242;
                    if ( !v242 )
                      goto LABEL_438;
                    goto LABEL_99;
                  }
                  v60 = (*(__int64 (__fastcall **)(struct CDeploymentFileRequest *, LPVOID *))(*(_QWORD *)v242 + 24LL))(
                          v242,
                          &pv);
                  ShouldDownloadRangelessFile = v60;
                  if ( v60 < 0 )
                  {
                    v61 = *((_QWORD *)this + 75);
                    v16 = 0;
                    if ( v61 )
                    {
                      LODWORD(v201) = v60;
                      LODWORD(v198) = 1546;
                      v63 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v61,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::GenerateExpressDownloadList",
                              v198,
                              v201);
                      v62 = (unsigned int)v63;
                      if ( v63 < 0 )
                        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v63, v64);
                    }
                    else
                    {
                      v62 = 0;
                    }
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v62);
                    if ( pv )
                    {
                      CoTaskMemFree(pv);
                      pv = 0;
                    }
                    v59 = v242;
                    if ( !v242 )
                      goto LABEL_438;
LABEL_99:
                    (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v242 + 16LL))(v59);
                    goto LABEL_438;
                  }
                  v53 = (const wchar_t **)(v41 + 64);
                  if ( !(unsigned int)_o__wcsicmp(pv, *(_QWORD *)(v41 + 64)) )
                    break;
                  if ( pv )
                  {
                    CoTaskMemFree(pv);
                    pv = 0;
                  }
                  if ( v242 )
                  {
                    (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v242 + 16LL))(v242);
                    v242 = 0;
                  }
                  ++v52;
                }
                v65 = v242;
                v66 = v242;
                if ( pv )
                {
                  CoTaskMemFree(pv);
                  pv = 0;
                  v65 = v242;
                }
                if ( v65 )
                {
                  (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v65 + 16LL))(v65);
                  v242 = 0;
                }
                if ( !v66 )
                {
LABEL_115:
                  v67 = CDeploymentFileRequest::Create(
                          *v53,
                          *(const wchar_t **)(v41 + 48),
                          *(const wchar_t **)(v41 + 48),
                          *(const wchar_t **)(v41 + 88),
                          L"Canonical",
                          v204,
                          &v240);
                  ShouldDownloadRangelessFile = v67;
                  if ( v67 < 0 )
                  {
                    v32 = *((_QWORD *)this + 75);
                    v16 = 0;
                    if ( v32 )
                    {
                      LODWORD(v201) = v67;
                      LODWORD(v198) = 1563;
                      goto LABEL_40;
                    }
LABEL_32:
                    v26 = (unsigned int)v16;
LABEL_36:
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v26);
LABEL_438:
                    v14 = v239;
LABEL_439:
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v251);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v250);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v254);
                    if ( bstrString )
                    {
                      SysFreeString(bstrString);
                      bstrString = v16;
                    }
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v249);
                    CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::~CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>(&v222);
                    if ( v224[1] )
                      utl::_RefCountBase::_DecStrong(v224[1]);
                    SP_ARBITER<SessionData>::~SP_ARBITER<SessionData>(&v233);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v248);
                    CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::~CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>(&v225);
                    SP_MEM<wchar_t>::~SP_MEM<wchar_t>(&v220);
                    if ( v240 )
                      (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v240 + 16LL))(v240);
                    if ( v14 )
                      (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v14 + 16LL))(v14);
                    SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v252);
                    return (unsigned int)ShouldDownloadRangelessFile;
                  }
                  v66 = v240;
                }
                if ( v239 )
                {
                  (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v239 + 16LL))(v239);
                  v239 = 0;
                }
                OffsetInOuterContainer = CDeploymentSession::GetOffsetInOuterContainer(
                                           this,
                                           *(const wchar_t **)(v41 + 48),
                                           *(const wchar_t **)(v41 + 56),
                                           *(const wchar_t **)(v41 + 72),
                                           *(const wchar_t **)(v41 + 112),
                                           &v208,
                                           0);
                ShouldDownloadRangelessFile = OffsetInOuterContainer;
                if ( OffsetInOuterContainer < 0 )
                {
                  v32 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( !v32 )
                    goto LABEL_32;
                  LODWORD(v201) = OffsetInOuterContainer;
                  LODWORD(v198) = 1572;
                  goto LABEL_40;
                }
                v69 = CDeploymentFileRange::Create(v208, *(_QWORD *)(v41 + 160), &v239);
                ShouldDownloadRangelessFile = v69;
                if ( v69 < 0 )
                {
                  v32 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( !v32 )
                    goto LABEL_32;
                  LODWORD(v201) = v69;
                  LODWORD(v198) = 1573;
                  goto LABEL_40;
                }
                v70 = v239;
                v239 = 0;
                v214 = v70;
                appended = CDeploymentFileRequest::AppendFileRange(v66, &v214);
                ShouldDownloadRangelessFile = appended;
                v32 = *((_QWORD *)this + 75);
                if ( appended < 0 )
                {
                  v16 = 0;
                  if ( !v32 )
                    goto LABEL_32;
                  LODWORD(v201) = appended;
                  LODWORD(v198) = 1574;
                  goto LABEL_40;
                }
                if ( v32 )
                  CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v32,
                    2,
                    L"        Rangeless file container: [%ws]",
                    *(_QWORD *)(v41 + 48));
                v72 = *((_QWORD *)this + 75);
                if ( v72 )
                  CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v72,
                    2,
                    L"        Rangeless file container offset: [%llu]",
                    v208);
                v73 = v204;
                v13 = (int)Src;
              }
              else
              {
                v73 = v204;
                v76 = CDeploymentFileRequest::Create(
                        *(const wchar_t **)(v41 + 112),
                        *(const wchar_t **)(v41 + 80),
                        *(const wchar_t **)(v41 + 72),
                        *(const wchar_t **)(v41 + 88),
                        L"Canonical",
                        v204,
                        &v240);
                ShouldDownloadRangelessFile = v76;
                if ( v76 < 0 )
                {
                  v32 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( !v32 )
                    goto LABEL_32;
                  LODWORD(v201) = v76;
                  LODWORD(v198) = 1587;
                  goto LABEL_40;
                }
              }
              v74 = v240;
              if ( v240 )
              {
                v240 = 0;
                v214 = v74;
                v75 = CDeploymentDownloadRequest::AppendFileRequest(v217, &v214);
                ShouldDownloadRangelessFile = v75;
                if ( v75 < 0 )
                {
                  v32 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( !v32 )
                    goto LABEL_32;
                  LODWORD(v201) = v75;
                  LODWORD(v198) = 1592;
                  goto LABEL_40;
                }
              }
              v77 = *((_QWORD *)this + 75);
              if ( v77 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v77, 2, L"        Rangeless file name: [%s]", v16);
              v78 = *((_QWORD *)this + 75);
              if ( v78 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v78,
                  2,
                  L"        Rangeless file size: [%llu]",
                  *(_QWORD *)(v41 + 160));
              v79 = *((_QWORD *)this + 75);
              if ( v79 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v79, 2, L"        Extraction file size: [%lu]", v215);
              v80 = *((_QWORD *)this + 75);
              if ( v80 )
              {
                v81 = L"TRUE";
                if ( !v73 )
                  v81 = L"FALSE";
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v80, 2, L"        Optional: [%s]", v81);
              }
              if ( v209 + *(_QWORD *)(v41 + 160) < v209 )
              {
                ShouldDownloadRangelessFile = -2147024362;
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, 0);
              }
              else
              {
                v209 += *(_QWORD *)(v41 + 160);
                ShouldDownloadRangelessFile = 0;
              }
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
              if ( ShouldDownloadRangelessFile < 0 )
              {
                v32 = *((_QWORD *)this + 75);
                v16 = 0;
                if ( !v32 )
                  goto LABEL_32;
                LODWORD(v201) = ShouldDownloadRangelessFile;
                LODWORD(v198) = 1599;
                goto LABEL_40;
              }
              ShouldDownloadRangelessFile = 0;
            }
            if ( v216 + *(_QWORD *)(v41 + 160) < v216 )
            {
              ShouldDownloadRangelessFile = -2147024362;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v48);
            }
            else
            {
              v216 += *(_QWORD *)(v41 + 160);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
            if ( ShouldDownloadRangelessFile < 0 )
            {
              v32 = *((_QWORD *)this + 75);
              v16 = 0;
              if ( !v32 )
                goto LABEL_32;
              LODWORD(v201) = ShouldDownloadRangelessFile;
              LODWORD(v198) = 1602;
              goto LABEL_40;
            }
            if ( v221 + v215 < v221 )
            {
              ShouldDownloadRangelessFile = -2147024362;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, 0);
            }
            else
            {
              v221 += v215;
              ShouldDownloadRangelessFile = 0;
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
            if ( ShouldDownloadRangelessFile < 0 )
            {
              v32 = *((_QWORD *)this + 75);
              v16 = 0;
              if ( !v32 )
                goto LABEL_32;
              LODWORD(v201) = ShouldDownloadRangelessFile;
              LODWORD(v198) = 1603;
              goto LABEL_40;
            }
          }
          v82 = CDeploymentSession::CheckCancelRequested(this, v42);
          ShouldDownloadRangelessFile = v82;
          v36 = 0;
          if ( v82 < 0 )
          {
            v32 = *((_QWORD *)this + 75);
            v16 = 0;
            if ( !v32 )
              goto LABEL_32;
            LODWORD(v201) = v82;
            LODWORD(v198) = 1606;
            goto LABEL_40;
          }
          v38 = v203;
          v37 = v206;
          v40 = 1;
        }
      }
      else
      {
        v83 = 88LL * (unsigned int)v38;
        v84 = v245;
        *(_QWORD *)&v245[v83] = *(_QWORD *)(v41 + 72);
        *(_QWORD *)&v84[v83 + 8] = *(_QWORD *)(v41 + 80);
        *(_QWORD *)&v84[v83 + 16] = *(_QWORD *)(v41 + 88);
        *(_QWORD *)&v84[v83 + 24] = *(_QWORD *)(v41 + 112);
        *(_QWORD *)&v84[v83 + 48] = *(_QWORD *)(v41 + 48);
        *(_QWORD *)&v84[v83 + 56] = *(_QWORD *)(v41 + 64);
        if ( v250 )
        {
          v85 = (WCHAR *)(v250 - 2);
          v86 = GetProcessHeap();
          HeapFree(v86, 0, v85);
          v84 = v245;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v250 = 0;
        }
        v87 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)&v84[v83 + 8], 0, &v250);
        ShouldDownloadRangelessFile = v87;
        if ( v87 < 0 )
        {
          v32 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( !v32 )
            goto LABEL_32;
          LODWORD(v201) = v87;
          LODWORD(v198) = 1620;
          goto LABEL_40;
        }
        v88 = GetFileAttributesW(v250);
        v89 = v88 != -1 && (v88 & 0x10) == 0;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( v89 )
          v31 = 1;
        v243 = v31;
        if ( v15 )
        {
          v90 = GetProcessHeap();
          HeapFree(v90, 0, (LPVOID)(v15 - 4));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v249 = 0;
        }
        v91 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 62), *(_QWORD *)(v41 + 120), 0, &v249);
        ShouldDownloadRangelessFile = v91;
        if ( v91 < 0 )
        {
          v32 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( !v32 )
            goto LABEL_32;
          LODWORD(v201) = v91;
          LODWORD(v198) = 1628;
          goto LABEL_40;
        }
        v92 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(&v222, &v249);
        ShouldDownloadRangelessFile = v92;
        if ( v92 < 0 )
        {
          v32 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( !v32 )
            goto LABEL_32;
          LODWORD(v201) = v92;
          LODWORD(v198) = 1629;
          goto LABEL_40;
        }
        v93 = (int)v203;
        v94 = v245;
        *(_QWORD *)&v245[v83 + 32] = *(_QWORD *)(v223 + 8LL * (int)v203);
        if ( v248 )
        {
          v95 = (WCHAR *)(v248 - 2);
          v96 = GetProcessHeap();
          HeapFree(v96, 0, v95);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v248 = 0;
        }
        v97 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)(v41 + 72), 0, &v248);
        ShouldDownloadRangelessFile = v97;
        if ( v97 < 0 )
        {
          v32 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( !v32 )
            goto LABEL_32;
          LODWORD(v201) = v97;
          LODWORD(v198) = 1635;
          goto LABEL_40;
        }
        v98 = GetFileAttributesW(v248);
        v99 = v98 != -1 && (v98 & 0x10) == 0;
        v205 = v99;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v36 = 0;
        if ( v99 )
        {
          v100 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(&v225, &v248);
          ShouldDownloadRangelessFile = v100;
          v36 = 0;
          if ( v100 < 0 )
          {
            v32 = *((_QWORD *)this + 75);
            v16 = 0;
            if ( !v32 )
              goto LABEL_32;
            LODWORD(v201) = v100;
            LODWORD(v198) = 1639;
            goto LABEL_40;
          }
          *(_QWORD *)&v94[v83 + 40] = *(_QWORD *)(v226 + 8 * v93);
          v40 = 1;
          v37 = 1;
          v206 = 1;
        }
        else
        {
          v37 = v206;
          v40 = 1;
        }
        v38 = ++v203;
        v15 = v249;
        v13 = (int)Src;
      }
      v39 = (unsigned int)((_DWORD)v202 + 1);
      v31 = v243;
      v11 = v218;
    }
    v16 = 0;
    v101 = 0;
    v208 = 0;
    if ( !(_DWORD)v38 )
    {
      v102 = *((_QWORD *)this + 75);
      if ( v102 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v102, 2, L"    All Express content is rangeless.", 1);
      goto LABEL_428;
    }
    if ( a5 )
    {
      if ( !v37 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= *((_DWORD *)v218 + 30) )
            goto LABEL_427;
          v104 = 184LL * i;
          v105 = *((_QWORD *)v218 + 14);
          if ( *(_QWORD *)(v104 + v105 + 64) && (v106 = v104 + v105, *(_QWORD *)(v104 + v105 + 48)) )
          {
            if ( !(unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::contains<wchar_t *>(
                                     (char *)this + 768,
                                     v106 + 48,
                                     v36,
                                     v40) )
            {
              v107 = *((_QWORD *)this + 75);
              if ( v107 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v107,
                  2,
                  L"    Adding container file: [%s]",
                  *(_QWORD *)(v106 + 48));
              ShouldDownloadRangelessFile = CDeploymentFileRequest::Create(
                                              *(const wchar_t **)(v104 + v105 + 64),
                                              *(const wchar_t **)(v106 + 48),
                                              *(const wchar_t **)(v106 + 48),
                                              0,
                                              L"Canonical",
                                              v204,
                                              &v240);
              if ( ShouldDownloadRangelessFile < 0 )
              {
                v32 = *((_QWORD *)this + 75);
                v16 = 0;
                if ( !v32 )
                  goto LABEL_32;
                LODWORD(v201) = ShouldDownloadRangelessFile;
                LODWORD(v198) = 1676;
LABEL_40:
                v26 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                      v32,
                                      4,
                                      L"%s(%d): Result = 0x%X",
                                      L"CDeploymentSession::GenerateExpressDownloadList",
                                      v198,
                                      v201);
LABEL_34:
                if ( (int)v26 < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v26, v27);
                goto LABEL_36;
              }
              v108 = *(_QWORD *)(v106 + 48);
              v227 = 0;
              v228 = 0;
              v109 = -1;
              do
                ++v109;
              while ( *(_WORD *)(v108 + 2 * v109) );
              std::wstring::_Construct<1,wchar_t const *>(&v227, v108, v109);
              std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
                (char *)this + 768,
                v229,
                &v227);
              std::wstring::~wstring(&v227);
            }
            v16 = 0;
          }
          else
          {
            v113 = *((_QWORD *)this + 75);
            if ( v113 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v113,
                2,
                L"    Adding PSF file: [%s]",
                *(_QWORD *)(v104 + v105 + 72));
            PackageExpanderProgress = CDeploymentFileRequest::Create(
                                        *(const wchar_t **)(v104 + v105 + 112),
                                        *(const wchar_t **)(v104 + v105 + 72),
                                        *(const wchar_t **)(v104 + v105 + 72),
                                        *(const wchar_t **)(v104 + v105 + 88),
                                        L"Canonical",
                                        v204,
                                        &v240);
            ShouldDownloadRangelessFile = PackageExpanderProgress;
            if ( PackageExpanderProgress < 0 )
            {
              v112 = 1693;
              goto LABEL_239;
            }
          }
          v110 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(&v213, &v240);
          PackageExpanderProgress = CDeploymentDownloadRequest::AppendFileRequest(v217, v110);
          ShouldDownloadRangelessFile = PackageExpanderProgress;
          if ( PackageExpanderProgress < 0 )
          {
            v112 = 1696;
            goto LABEL_239;
          }
        }
      }
LABEL_428:
      v192 = *((_QWORD *)this + 75);
      v193 = v209;
      if ( v192 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v192, 2, L"    Required Download size : [%llu]", v209);
      v194 = *((_QWORD *)this + 75);
      v195 = v216;
      if ( v194 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v194, 2, L"    Total Download size : [%llu]", v216);
      if ( v101 + v221 < v101 )
      {
        ShouldDownloadRangelessFile = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v38);
      }
      else
      {
        v101 += v221;
        ShouldDownloadRangelessFile = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
      if ( ShouldDownloadRangelessFile >= 0 )
      {
        *v234 = v193;
        *v230 = v195;
        *v231 = v101;
        *v232 = v211;
        goto LABEL_438;
      }
      v112 = 1945;
      v114 = (unsigned int)ShouldDownloadRangelessFile;
      goto LABEL_240;
    }
    v116 = *((_QWORD *)this + 75);
    if ( v116 )
    {
      v117 = L"TRUE";
      if ( !v31 )
        v117 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v116, 2, L"Range file Exists: [%s]", v117);
    }
    if ( !*((_DWORD *)this + 66) || v31 )
    {
      v119 = 1;
      v120 = *((_QWORD *)this + 75);
      if ( v120 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v120, 2, L"    Calculating ranges", 1);
    }
    else
    {
      v118 = *((_QWORD *)this + 75);
      if ( v118 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v118, 2, L"    Calculating ranges (new job)", 1);
      v119 = 5;
    }
    PackageExpanderProgress = CProgressHandler::GetPackageExpanderProgress(
                                *((CProgressHandler **)this + 60),
                                *((const wchar_t **)v11 + 7),
                                &v213);
    ShouldDownloadRangelessFile = PackageExpanderProgress;
    if ( PackageExpanderProgress < 0 )
    {
      v112 = 1721;
LABEL_239:
      v114 = (unsigned int)PackageExpanderProgress;
LABEL_240:
      v115 = *((_QWORD *)this + 75);
LABEL_241:
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(v115, v114, L"CDeploymentSession::GenerateExpressDownloadList", v112);
      goto LABEL_438;
    }
    v121 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *((_QWORD *)v11 + 7), 0, &v254);
    ShouldDownloadRangelessFile = v121;
    v115 = *((_QWORD *)this + 75);
    if ( v121 < 0 )
    {
      v112 = 1722;
      v114 = (unsigned int)v121;
      goto LABEL_241;
    }
    PackageExpanderProgress = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v115 + 88LL))(v115, &bstrString);
    ShouldDownloadRangelessFile = PackageExpanderProgress;
    if ( PackageExpanderProgress < 0 )
    {
      v112 = 1723;
      goto LABEL_239;
    }
    PackageExpanderProgress = CDeploymentSession::CheckCancelRequested(this, v122);
    ShouldDownloadRangelessFile = PackageExpanderProgress;
    if ( PackageExpanderProgress < 0 )
    {
      v112 = 1725;
      goto LABEL_239;
    }
    v123 = *((_QWORD *)this + 80);
    if ( v123 && *(_DWORD *)(v123 + 8) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    UpdateAgentMisc::ConvertWinDirToDefaultBootDir(&v202, *((_QWORD *)this + 70));
    pv = 0;
    v124 = &String2;
    v125 = &String2;
    if ( *((_QWORD *)this + 70) )
      v125 = (const WCHAR *)*((_QWORD *)this + 70);
    memset(v237, 0, sizeof(v237));
    v126 = -1;
    v127 = -1;
    do
      ++v127;
    while ( v125[v127] );
    std::wstring::_Construct<1,wchar_t const *>(v237, v125, v127);
    v128 = &String2;
    if ( v202 )
      v128 = v202;
    memset(v236, 0, sizeof(v236));
    v129 = -1;
    do
      ++v129;
    while ( v128[v129] );
    std::wstring::_Construct<1,wchar_t const *>(v236, v128, v129);
    if ( *((_QWORD *)this + 67) )
    {
      v124 = (const WCHAR *)*((_QWORD *)this + 67);
    }
    else if ( *((_QWORD *)this + 62) )
    {
      v124 = (const WCHAR *)*((_QWORD *)this + 62);
    }
    memset(v235, 0, sizeof(v235));
    v130 = -1;
    do
      ++v130;
    while ( v124[v130] );
    std::wstring::_Construct<1,wchar_t const *>(v235, v124, v130);
    memset(v229, 0, sizeof(v229));
    v131 = -1;
    do
      ++v131;
    while ( bstrString[v131] );
    std::wstring::_Construct<1,wchar_t const *>(v229, bstrString, v131);
    v227 = 0;
    v228 = 0;
    do
      ++v126;
    while ( *(_WORD *)(v254 + 2 * v126) );
    std::wstring::_Construct<1,wchar_t const *>(&v227, v254, v126);
    ShouldDownloadRangelessFile = GetPackageExpanderEx(
                                    v119,
                                    (*((_DWORD *)this + 150) + 24) & (unsigned int)-(*((_QWORD *)this + 75) != 0),
                                    (_DWORD)v213,
                                    (unsigned int)&v227,
                                    (__int64)v229,
                                    (__int64)v235,
                                    (__int64)v236,
                                    (__int64)v237,
                                    (__int64)&pv,
                                    (__int64)&v246);
    std::wstring::~wstring(&v227);
    std::wstring::~wstring(v229);
    std::wstring::~wstring(v235);
    std::wstring::~wstring(v236);
    std::wstring::~wstring(v237);
    if ( ShouldDownloadRangelessFile < 0 )
    {
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        *((_QWORD *)this + 75),
        (unsigned int)ShouldDownloadRangelessFile,
        L"CDeploymentSession::GenerateExpressDownloadList",
        1740);
      if ( pv )
        (**(void (__fastcall ***)(LPVOID))pv)(pv);
      goto LABEL_287;
    }
    v133 = CDeploymentSession::CheckCancelRequested(this, v132);
    ShouldDownloadRangelessFile = v133;
    if ( v133 < 0 )
    {
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        *((_QWORD *)this + 75),
        (unsigned int)v133,
        L"CDeploymentSession::GenerateExpressDownloadList",
        1741);
      if ( pv )
        (**(void (__fastcall ***)(LPVOID))pv)(pv);
      goto LABEL_287;
    }
    v134 = pv;
    pv = 0;
    if ( !(unsigned __int8)___reset_VIPackageExpander__V_lambda_1___0__GenerateExpressDownloadList_CDeploymentSession__QEAAJQEBUPackage_ActionList__HHHPEAV__set_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UWstringCaseInsensitiveCompare__V__allocator_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__std__PEAVCDeploymentDownloadRequest__PEA_K33PEAH_Z__0A____shared_ptr_VIPackageExpander___utl__QEAA_NPEAVIPackageExpander__V_lambda_1___0__GenerateExpressDownloadList_CDeploymentSession__QEAAJQEBUPackage_ActionList__HHHPEAV__set_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UWstringCaseInsensitiveCompare__V__allocator_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__std__PEAVCDeploymentDownloadRequest__PEA_K44PEAH_Z__Z(
                             v224,
                             v134) )
    {
      ShouldDownloadRangelessFile = -2147467261;
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        *((_QWORD *)this + 75),
        2147500035LL,
        L"CDeploymentSession::GenerateExpressDownloadList",
        1743);
LABEL_287:
      __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v202);
      goto LABEL_438;
    }
    utl::weak_ptr<IPackageExpander>::operator=<IPackageExpander,0>((char *)this + 632, v224);
    v135 = *((_DWORD *)this + 114);
    if ( v135 <= 0x16 && (v136 = 4195888, _bittest(&v136, v135)) || (v137 = 0, v135 == 6) )
    {
      v137 = 1;
      if ( v135 == 9 )
        v137 = 3;
    }
    v138 = v224[0];
    v200 = v251;
    v139 = (*(__int64 (__fastcall **)(utl::_RefCountBase *, __int64, char *, _QWORD))(*(_QWORD *)v224[0] + 8LL))(
             v224[0],
             v137,
             v245,
             v203);
    ShouldDownloadRangelessFile = v139;
    if ( v139 < 0 )
    {
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        *((_QWORD *)this + 75),
        (unsigned int)v139,
        L"CDeploymentSession::GenerateExpressDownloadList",
        1764);
      goto LABEL_287;
    }
    v141 = CDeploymentSession::CheckCancelRequested(this, v140);
    ShouldDownloadRangelessFile = v141;
    v143 = *((_QWORD *)this + 75);
    if ( v141 < 0 )
    {
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        v143,
        (unsigned int)v141,
        L"CDeploymentSession::GenerateExpressDownloadList",
        1766);
      goto LABEL_287;
    }
    if ( *((_DWORD *)v138 + 4) )
    {
      v144 = *((_QWORD *)v138 + 3);
      v208 = v144;
      if ( v143 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v143, 2, L"    Expand size: [%llu]", v144, v200);
      v145 = *((_QWORD *)this + 75);
      if ( v145 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v145,
          2,
          L"    Required RNG files count:[%lu]",
          *((unsigned int *)v138 + 4));
    }
    else
    {
      v208 = 0;
      if ( v143 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v143, 2, L"    Already expanded");
    }
    v146 = 0;
    while ( 1 )
    {
      v203 = v146;
      if ( v146 >= *((_DWORD *)v138 + 4) )
      {
        Windows::AutoReleasePtr<IPackageExpander>::~AutoReleasePtr<IPackageExpander>(&pv);
        __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v202);
LABEL_427:
        v101 = v208;
        goto LABEL_428;
      }
      v147 = CDeploymentSession::CheckCancelRequested(this, v142);
      ShouldDownloadRangelessFile = v147;
      if ( v147 < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v147,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1786);
        goto LABEL_287;
      }
      v148 = 88LL * v146;
      *(_QWORD *)&v229[0] = v148;
      v149 = *((_QWORD *)v138 + 1);
      v215 = v149;
      v213 = 0;
      SH_SSTRING::operator=(&lpFileName);
      v150 = CMiscHelpersT<CEmptyType>::CombinePath(
               *((_QWORD *)this + 61),
               *(_QWORD *)(v149 + v148 + 8),
               0,
               &lpFileName);
      ShouldDownloadRangelessFile = v150;
      if ( v150 < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v150,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1795);
        goto LABEL_287;
      }
      v151 = lpFileName;
      v152 = CMiscHelpersT<CEmptyType>::FileExists(lpFileName, &v205);
      ShouldDownloadRangelessFile = v152;
      if ( v152 < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v152,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1796);
        goto LABEL_287;
      }
      LODWORD(v16) = v205;
      if ( v205 )
      {
        ShouldDownloadRangelessFile = CMoUpdateHelpersT<CEmptyType>::GetFileSize(v151, &v256);
        if ( ShouldDownloadRangelessFile < 0 )
        {
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)ShouldDownloadRangelessFile,
            L"CDeploymentSession::GenerateExpressDownloadList",
            1800);
          v16 = 0;
          goto LABEL_287;
        }
        if ( !v256 )
        {
          v154 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( v154 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v154, 2, L"    Deleting zero byte RNG file: [%s]", v151);
          if ( !DeleteFileW(v151) )
          {
            v155 = GetLastError();
            ShouldDownloadRangelessFile = v155;
            if ( v155 )
            {
              if ( v155 > 0 )
                ShouldDownloadRangelessFile = (unsigned __int16)v155 | 0x80070000;
            }
            else
            {
              ShouldDownloadRangelessFile = -2147467259;
            }
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)ShouldDownloadRangelessFile,
              L"CDeploymentSession::GenerateExpressDownloadList",
              1804);
            goto LABEL_287;
          }
          v211 = 1;
          v205 = 0;
        }
      }
      v212 = 0;
      if ( (_DWORD)v16 )
        break;
      v156 = *(const wchar_t **)(v149 + v148 + 48);
      v16 = 0;
      if ( v156 )
      {
        Src = *(wchar_t **)(v149 + v148 + 56);
        v157 = CDeploymentSession::GetOffsetInOuterContainer(
                 this,
                 v156,
                 0,
                 *(const wchar_t **)(v149 + v148),
                 *(const wchar_t **)(v149 + v148 + 24),
                 (unsigned __int64 *)&v213,
                 0);
        ShouldDownloadRangelessFile = v157;
        if ( v157 < 0 )
        {
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)v157,
            L"CDeploymentSession::GenerateExpressDownloadList",
            1821);
          goto LABEL_287;
        }
        v158 = v156;
        v159 = Src;
      }
      else
      {
        v159 = *(wchar_t **)(v149 + v148 + 24);
        Src = v159;
        v156 = *(const wchar_t **)(v149 + v148);
        v158 = *(const wchar_t **)(v149 + v148 + 8);
      }
      v153 = 0;
      if ( v240 )
      {
        (*(void (__fastcall **)(struct CDeploymentFileRequest *, _QWORD))(*(_QWORD *)v240 + 16LL))(v240, 0);
        v153 = 0;
        v240 = 0;
      }
      if ( !v210 )
      {
        v16 = 0;
        if ( !v206 )
        {
          v171 = *((_QWORD *)this + 75);
          if ( v171 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v171, 2, L"    Adding PSF file: [%s]", v156);
          v172 = CDeploymentFileRequest::Create(
                   v159,
                   v156,
                   v156,
                   *(const wchar_t **)(v149 + v148 + 16),
                   L"Canonical",
                   v204,
                   &v240);
          ShouldDownloadRangelessFile = v172;
          if ( v172 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v172,
              L"CDeploymentSession::GenerateExpressDownloadList",
              1888);
            goto LABEL_287;
          }
        }
LABEL_376:
        v174 = v210;
        if ( !v210 )
          goto LABEL_394;
        goto LABEL_377;
      }
      if ( *(_QWORD *)(v149 + v148 + 56) )
      {
        v243 = 0;
        v160 = *(_QWORD *)v217;
        v245 = 0;
        v161 = (*(__int64 (__fastcall **)(__int64, char **))(v160 + 40))(v217, &v245);
        if ( v161 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x732,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v161,
            (int)v200);
        v162 = (*(__int64 (__fastcall **)(char *, unsigned int *))(*(_QWORD *)v245 + 24LL))(v245, &v243);
        v153 = 0;
        if ( v162 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x733,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v162,
            (int)v200);
        for ( j = 0; ; ++j )
        {
          if ( j >= v243 )
          {
            v168 = v212;
            goto LABEL_360;
          }
          v242 = 0;
          v244 = 0;
          v164 = (*(__int64 (__fastcall **)(char *, _QWORD, struct CDeploymentFileRequest **))(*(_QWORD *)v245 + 32LL))(
                   v245,
                   j,
                   &v242);
          if ( v164 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x73A,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v164,
              (int)v200);
          v165 = (*(__int64 (__fastcall **)(struct CDeploymentFileRequest *, LPVOID *))(*(_QWORD *)v242 + 24LL))(
                   v242,
                   &v244);
          if ( v165 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x73B,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v165,
              (int)v200);
          v166 = _o__wcsicmp(v244, *(_QWORD *)(v149 + v148 + 56));
          v153 = 0;
          if ( !v166 )
            break;
          if ( v244 )
          {
            CoTaskMemFree(v244);
            v153 = 0;
            v244 = 0;
          }
          if ( v242 )
          {
            (*(void (__fastcall **)(struct CDeploymentFileRequest *, _QWORD))(*(_QWORD *)v242 + 16LL))(v242, 0);
            v153 = 0;
            v242 = 0;
          }
        }
        v167 = *((_QWORD *)this + 75);
        if ( v167 )
        {
          v200 = *(wchar_t **)(v149 + v148 + 56);
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v167,
            2,
            L"    Found existing RNG file: [%s] with AltSourceHash [%s]",
            *(_QWORD *)(v149 + v148 + 8));
        }
        v153 = (int *)v242;
        v168 = v242;
        v212 = v242;
        if ( v244 )
        {
          CoTaskMemFree(v244);
          v244 = 0;
          v153 = (int *)v242;
        }
        if ( v153 )
        {
          (*(void (__fastcall **)(int *))(*(_QWORD *)v153 + 16LL))(v153);
          v153 = 0;
          v242 = 0;
        }
LABEL_360:
        if ( v245 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v245 + 16LL))(v245);
        if ( v168 )
        {
          v16 = 0;
          goto LABEL_376;
        }
      }
      v169 = *((_QWORD *)this + 75);
      if ( v169 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v169,
          2,
          L"    Adding RNG file: [%s] with AltSourceHash [%s]",
          *(_QWORD *)(v149 + v148 + 8),
          *(_QWORD *)(v149 + v148 + 56));
      v170 = CDeploymentFileRequest::Create(
               Src,
               v158,
               v156,
               *(const wchar_t **)(v149 + v148 + 16),
               L"Express",
               v204,
               &v240);
      ShouldDownloadRangelessFile = v170;
      v16 = 0;
      if ( v170 < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v170,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1872);
        goto LABEL_287;
      }
      v212 = v240;
LABEL_377:
      for ( k = 0; k < *(_DWORD *)(v215 + v148 + 80); ++k )
      {
        v176 = CDeploymentSession::CheckCancelRequested(this, v153);
        ShouldDownloadRangelessFile = v176;
        if ( v176 < 0 )
        {
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)v176,
            L"CDeploymentSession::GenerateExpressDownloadList",
            1901);
          v16 = 0;
          goto LABEL_287;
        }
        v178 = 16LL * k;
        v179 = *(_QWORD *)(v215 + v148 + 72);
        if ( (WCHAR *)((char *)v16 + *(_QWORD *)(v178 + v179 + 8)) < v16 )
        {
          ShouldDownloadRangelessFile = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v177);
        }
        else
        {
          v16 = (WCHAR *)((char *)v16 + *(_QWORD *)(v178 + v179 + 8));
          ShouldDownloadRangelessFile = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
        if ( ShouldDownloadRangelessFile < 0 )
        {
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)ShouldDownloadRangelessFile,
            L"CDeploymentSession::GenerateExpressDownloadList",
            1904);
          v16 = 0;
          goto LABEL_287;
        }
        if ( !v205 )
        {
          if ( v239 )
          {
            (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v239 + 16LL))(v239);
            v239 = 0;
          }
          v180 = CDeploymentFileRange::Create(
                   (unsigned __int64)v213 + *(_QWORD *)(v178 + v179),
                   *(_QWORD *)(v178 + v179 + 8),
                   &v239);
          ShouldDownloadRangelessFile = v180;
          if ( v180 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v180,
              L"CDeploymentSession::GenerateExpressDownloadList",
              1909);
            v16 = 0;
            goto LABEL_287;
          }
          v181 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(&v214, &v239);
          v182 = CDeploymentFileRequest::AppendExpressFileRange(v212, v181);
          if ( v182 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x776,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v182,
              (int)v200);
        }
        v148 = *(_QWORD *)&v229[0];
      }
      v149 = v215;
      v174 = v210;
LABEL_394:
      if ( v205 )
        goto LABEL_419;
      if ( v240 )
      {
        v183 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v219, &v240);
        v184 = CDeploymentDownloadRequest::AppendFileRequest(v217, v183);
        if ( v184 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x77F,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v184,
            (int)v200);
      }
      if ( v174 )
      {
        v185 = *((_QWORD *)this + 75);
        if ( v185 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v185, 2, L"        RNG file size: [%llu]", v16);
        v186 = *((_QWORD *)this + 75);
        if ( v186 )
        {
          v187 = L"TRUE";
          if ( !v204 )
            v187 = L"FALSE";
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v186, 2, L"        Optional: [%s]", v187, v200);
        }
        v188 = *((_QWORD *)this + 75);
        if ( v188 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v188, 2, L"        IsRangeRequestSupported: [%s]", L"TRUE");
        v189 = *((_QWORD *)this + 75);
        if ( v189 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v189,
            2,
            L"        Range count in RNG file: [%lu]",
            *(unsigned int *)(v149 + v148 + 80));
        if ( (unsigned __int64)v16 + v209 < v209 )
        {
          ShouldDownloadRangelessFile = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v153);
        }
        else
        {
          v209 += (unsigned __int64)v16;
          ShouldDownloadRangelessFile = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
        if ( ShouldDownloadRangelessFile < 0 )
        {
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)ShouldDownloadRangelessFile,
            L"CDeploymentSession::GenerateExpressDownloadList",
            1929);
          v16 = 0;
          goto LABEL_287;
        }
LABEL_419:
        v190 = v203;
        goto LABEL_420;
      }
      if ( v206 )
        goto LABEL_419;
      v190 = v203;
      v191 = 184LL * v203;
      if ( v209 + *(_QWORD *)(v191 + *((_QWORD *)v218 + 14)) < v209 )
      {
        ShouldDownloadRangelessFile = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v153);
      }
      else
      {
        v209 += *(_QWORD *)(v191 + *((_QWORD *)v218 + 14));
        ShouldDownloadRangelessFile = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
      if ( ShouldDownloadRangelessFile < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)ShouldDownloadRangelessFile,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1933);
        v16 = 0;
        goto LABEL_287;
      }
LABEL_420:
      if ( (unsigned __int64)v16 + v216 < v216 )
      {
        ShouldDownloadRangelessFile = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v153);
        v16 = 0;
      }
      else
      {
        v216 += (unsigned __int64)v16;
        v16 = 0;
        ShouldDownloadRangelessFile = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
      if ( ShouldDownloadRangelessFile < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)ShouldDownloadRangelessFile,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1937);
        Windows::AutoReleasePtr<IPackageExpander>::~AutoReleasePtr<IPackageExpander>(&pv);
        goto LABEL_287;
      }
      v146 = v190 + 1;
      v138 = v224[0];
    }
    v173 = *((_QWORD *)this + 75);
    v16 = 0;
    if ( v173 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v173, 2, L"    RNG File exists: [%s]", *(_QWORD *)(v149 + v148 + 8));
    goto LABEL_376;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7A4,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v196);
  }
  return result;
}

```

## disassembly

```asm
0x180054e0c  push    rbx
0x180054e0e  push    rsi
0x180054e0f  push    rdi
0x180054e10  push    r12
0x180054e12  push    r13
0x180054e14  push    r14
0x180054e16  push    r15
0x180054e18  sub     rsp, 270h
0x180054e1f  mov     [rsp+2A8h+var_D8], 0FFFFFFFFFFFFFFFEh
0x180054e2b  mov     rax, cs:__security_cookie
0x180054e32  xor     rax, rsp
0x180054e35  mov     [rsp+2A8h+var_40], rax
0x180054e3d  mov     [rsp+2A8h+var_228], r9d
0x180054e45  mov     [rsp+2A8h+var_24C], r8d
0x180054e4a  mov     r15, rdx
0x180054e4d  mov     [rsp+2A8h+var_1F0], rdx
0x180054e55  mov     rdi, rcx
0x180054e58  mov     r14, [rsp+2A8h+arg_28]
0x180054e60  mov     [rsp+2A8h+Src], r14
0x180054e65  mov     rax, [rsp+2A8h+arg_30]
0x180054e6d  mov     [rsp+2A8h+var_1F8], rax
0x180054e75  mov     rdx, [rsp+2A8h+arg_38]
0x180054e7d  mov     [rsp+2A8h+var_140], rdx
0x180054e85  mov     r8, [rsp+2A8h+arg_40]
0x180054e8d  mov     [rsp+2A8h+var_160], r8
0x180054e95  mov     r9, [rsp+2A8h+arg_48]
0x180054e9d  mov     [rsp+2A8h+var_158], r9
0x180054ea5  mov     r10, [rsp+2A8h+arg_50]
0x180054ead  mov     [rsp+2A8h+var_150], r10
0x180054eb5  xor     r11d, r11d
0x180054eb8  mov     [rsp+2A8h+var_68], r11
0x180054ec0  mov     esi, r11d
0x180054ec3  mov     [rsp+2A8h+var_D0], r11
0x180054ecb  mov     [rsp+2A8h+var_C8], r11
0x180054ed3  mov     [rsp+2A8h+var_1E0], r11
0x180054edb  mov     [rsp+2A8h+var_1B0], r11
0x180054ee3  mov     [rsp+2A8h+var_1A8], r11
0x180054eeb  mov     [rsp+2A8h+var_88], r11
0x180054ef3  mov     [rsp+2A8h+var_148], r11
0x180054efb  xorps   xmm0, xmm0
0x180054efe  movdqu  xmmword ptr [rsp+2A8h+var_1C0], xmm0
0x180054f07  mov     [rsp+2A8h+var_1D0], r11
0x180054f0f  mov     [rsp+2A8h+var_1C8], r11
0x180054f17  mov     r12d, r11d
0x180054f1a  mov     [rsp+2A8h+var_80], r11
0x180054f22  mov     [rsp+2A8h+var_218], r11
0x180054f2a  mov     [rsp+2A8h+bstrString], r11
0x180054f32  mov     [rsp+2A8h+var_48], r11
0x180054f3a  mov     [rsp+2A8h+var_50], r11
0x180054f42  mov     [rsp+2A8h+var_208], r11
0x180054f4a  mov     [rsp+2A8h+var_238], r11
0x180054f4f  mov     [rsp+2A8h+var_58], r11
0x180054f57  mov     r13d, r11d
0x180054f5a  mov     [rsp+2A8h+lpFileName], r11
0x180054f62  mov     [rsp+2A8h+var_78], r11
0x180054f6a  mov     [rsp+2A8h+var_70], r11
0x180054f72  mov     [rsp+2A8h+var_248], r11d
0x180054f77  mov     dword ptr [rsp+2A8h+var_220], r11d
0x180054f7f  mov     [rsp+2A8h+var_98], r11d
0x180054f87  test    r15, r15
0x180054f8a  jnz     short loc_180054FDB
0x180054f8c  mov     rcx, [rcx+258h]
0x180054f93  mov     ebx, 80070057h
0x180054f98  test    rcx, rcx
0x180054f9b  jnz     short loc_180054FA2
0x180054f9d  mov     ecx, r13d
0x180054fa0  jmp     short loc_180054FD1
0x180054fa2  mov     dword ptr [rsp+2A8h+var_280], ebx
0x180054fa6  mov     dword ptr [rsp+2A8h+var_288], 5B2h
0x180054fae  lea     r9, aCdeploymentses_32; "CDeploymentSession::GenerateExpressDown"...
0x180054fb5  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180054fbc  mov     edx, 4
0x180054fc1  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180054fc6  mov     ecx, eax
0x180054fc8  test    ecx, ecx
0x180054fca  jns     short loc_180054FD1
0x180054fcc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180054fd1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180054fd6  jmp     loc_180057245
0x180054fdb  test    rax, rax
0x180054fde  jnz     short loc_18005501C
0x180054fe0  mov     rcx, [rcx+258h]
0x180054fe7  xor     r13d, r13d
0x180054fea  mov     ebx, 80070057h
0x180054fef  test    rcx, rcx
0x180054ff2  jz      short loc_180054F9D
0x180054ff4  mov     dword ptr [rsp+2A8h+var_280], ebx
0x180054ff8  mov     dword ptr [rsp+2A8h+var_288], 5B3h
0x180055000  lea     r9, aCdeploymentses_32; "CDeploymentSession::GenerateExpressDown"...
0x180055007  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18005500e  mov     edx, 4
0x180055013  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180055018  mov     ecx, eax
0x18005501a  jmp     short loc_180054FC8
0x18005501c  test    rdx, rdx
0x18005501f  jnz     short loc_180055047
0x180055021  mov     rcx, [rcx+258h]
0x180055028  xor     r13d, r13d
0x18005502b  mov     ebx, 80070057h
0x180055030  test    rcx, rcx
0x180055033  jz      loc_180054F9D
0x180055039  mov     dword ptr [rsp+2A8h+var_280], ebx
0x18005503d  mov     dword ptr [rsp+2A8h+var_288], 5B4h
0x180055045  jmp     short loc_180055000
0x180055047  test    r8, r8
0x18005504a  jnz     short loc_180055072
0x18005504c  mov     rcx, [rcx+258h]
0x180055053  xor     r13d, r13d
0x180055056  mov     ebx, 80070057h
0x18005505b  test    rcx, rcx
0x18005505e  jz      loc_180054F9D
0x180055064  mov     dword ptr [rsp+2A8h+var_280], ebx
0x180055068  mov     dword ptr [rsp+2A8h+var_288], 5B5h
0x180055070  jmp     short loc_180055000
0x180055072  test    r9, r9
0x180055075  jnz     short loc_1800550A0
0x180055077  mov     rcx, [rcx+258h]
0x18005507e  xor     r13d, r13d
0x180055081  mov     ebx, 80070057h
0x180055086  test    rcx, rcx
0x180055089  jz      loc_180054F9D
0x18005508f  mov     dword ptr [rsp+2A8h+var_280], ebx
0x180055093  mov     dword ptr [rsp+2A8h+var_288], 5B6h
0x18005509b  jmp     loc_180055000
0x1800550a0  test    r10, r10
0x1800550a3  jnz     short loc_1800550CE
0x1800550a5  mov     rcx, [rcx+258h]
0x1800550ac  xor     r13d, r13d
0x1800550af  mov     ebx, 80070057h
0x1800550b4  test    rcx, rcx
0x1800550b7  jz      loc_180054F9D
0x1800550bd  mov     dword ptr [rsp+2A8h+var_280], ebx
0x1800550c1  mov     dword ptr [rsp+2A8h+var_288], 5B7h
0x1800550c9  jmp     loc_180055000
0x1800550ce  mov     ecx, [r15+78h]
0x1800550d2  test    ecx, ecx
0x1800550d4  jz      short loc_180055105
0x1800550d6  imul    esi, ecx, 58h ; 'X'
0x1800550d9  mov     eax, 0BA2E8BA3h
0x1800550de  mul     esi
0x1800550e0  shr     edx, 6
0x1800550e3  cmp     edx, ecx
0x1800550e5  jz      short loc_180055108
0x1800550e7  mov     esi, r11d
0x1800550ea  mov     r15d, 80070216h
0x1800550f0  mov     ebx, r15d
0x1800550f3  mov     ecx, r15d
0x1800550f6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800550fb  mov     r15, [rsp+2A8h+var_1F0]
0x180055103  jmp     short loc_18005510B
0x180055105  mov     esi, r11d
0x180055108  mov     ebx, r11d
0x18005510b  mov     ecx, ebx
0x18005510d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180055112  test    ebx, ebx
0x180055114  jns     short loc_180055163
0x180055116  mov     rcx, [rdi+258h]
0x18005511d  xor     r13d, r13d
0x180055120  test    rcx, rcx
0x180055123  jnz     short loc_18005512A
0x180055125  mov     ecx, r13d
0x180055128  jmp     short loc_180055159
0x18005512a  mov     dword ptr [rsp+2A8h+var_280], ebx
0x18005512e  mov     dword ptr [rsp+2A8h+var_288], 5BEh
0x180055136  lea     r9, aCdeploymentses_32; "CDeploymentSession::GenerateExpressDown"...
0x18005513d  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180055144  mov     edx, 4
0x180055149  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18005514e  mov     ecx, eax
0x180055150  test    ecx, ecx
0x180055152  jns     short loc_180055159
0x180055154  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180055159  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18005515e  jmp     loc_18005723D
0x180055163  mov     ebx, esi
0x180055165  call    cs:__imp_GetProcessHeap
0x18005516c  nop     dword ptr [rax+rax+00h]
0x180055171  mov     rcx, rax; hHeap
0x180055174  mov     r8d, esi; dwBytes
0x180055177  xor     edx, edx; dwFlags
0x180055179  call    cs:__imp_HeapAlloc
0x180055180  nop     dword ptr [rax+rax+00h]
0x180055185  mov     [rsp+2A8h+var_A0], rax
0x18005518d  xor     esi, esi
0x18005518f  test    rax, rax
0x180055192  jnz     short loc_1800551DF
0x180055194  xor     r13d, r13d
0x180055197  mov     [rsp+2A8h+var_1E0], r13
0x18005519f  mov     rcx, [rdi+258h]
0x1800551a6  mov     ebx, 8007000Eh
0x1800551ab  test    rcx, rcx
0x1800551ae  jz      loc_180055125
0x1800551b4  mov     dword ptr [rsp+2A8h+var_280], ebx
0x1800551b8  mov     dword ptr [rsp+2A8h+var_288], 5C0h
0x1800551c0  mov     edx, 4
0x1800551c5  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800551cc  lea     r9, aCdeploymentses_32; "CDeploymentSession::GenerateExpressDown"...
0x1800551d3  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800551d8  mov     ecx, eax
0x1800551da  jmp     loc_180055150
0x1800551df  mov     [rsp+2A8h+var_1E0], rax
0x1800551e7  mov     rcx, rax; void *
0x1800551ea  mov     r8, rbx; Size
0x1800551ed  xor     edx, edx; Val
0x1800551ef  call    memset_0
0x1800551f4  cmp     [rsp+2A8h+arg_20], esi
0x1800551fb  jnz     short loc_180055237
0x1800551fd  lea     r8, [rsp+2A8h+var_70]; wchar_t **
0x180055205  mov     rdx, r15; struct ActionList::Package *
0x180055208  mov     rcx, rdi; this
0x18005520b  call    ?GetPackageFileListPath@CDeploymentSession@@QEAAJQEBUPackage@ActionList@@PEAPEA_W@Z; CDeploymentSession::GetPackageFileListPath(ActionList::Package const * const,wchar_t * *)
0x180055210  mov     ebx, eax
0x180055212  test    eax, eax
0x180055214  jns     short loc_180055237
0x180055216  mov     rcx, [rdi+258h]
0x18005521d  xor     r13d, r13d
0x180055220  test    rcx, rcx
0x180055223  jz      loc_180055125
0x180055229  mov     dword ptr [rsp+2A8h+var_280], eax
0x18005522d  mov     dword ptr [rsp+2A8h+var_288], 5C8h
0x180055235  jmp     short loc_1800551C0
0x180055237  mov     rcx, [rdi+258h]
0x18005523e  test    rcx, rcx
0x180055241  jz      short loc_180055258
0x180055243  mov     r9, [r15+38h]
0x180055247  lea     r8, aPackageS; "Package: [%s]"
0x18005524e  mov     edx, 2
0x180055253  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180055258  mov     rcx, [rsp+2A8h+var_1F8]
0x180055260  mov     rax, [rcx]
0x180055263  lea     rdx, [rsp+2A8h+var_68]
0x18005526b  mov     rax, [rax+28h]
0x18005526f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055274  mov     ebx, eax
0x180055276  xor     r8d, r8d
0x180055279  test    eax, eax
0x18005527b  jns     short loc_1800552A1
0x18005527d  mov     rcx, [rdi+258h]
0x180055284  xor     r13d, r13d
0x180055287  test    rcx, rcx
0x18005528a  jz      loc_180055125
0x180055290  mov     dword ptr [rsp+2A8h+var_280], eax
0x180055294  mov     dword ptr [rsp+2A8h+var_288], 5D2h
0x18005529c  jmp     loc_1800551C0
0x1800552a1  mov     [rsp+2A8h+var_224], r8d
0x1800552a9  mov     [rsp+2A8h+var_1D8], r8
0x1800552b1  mov     ecx, r8d
0x1800552b4  mov     [rsp+2A8h+var_244], ecx
0x1800552b8  mov     [rsp+2A8h+var_B0], r8d
0x1800552c0  mov     [rsp+2A8h+var_230], r8
0x1800552c5  mov     [rsp+2A8h+var_200], r8
0x1800552cd  mov     edx, r8d
0x1800552d0  mov     [rsp+2A8h+var_250], edx
0x1800552d4  mov     eax, r8d
0x1800552d7  mov     r9d, 1
0x1800552dd  mov     dword ptr [rsp+2A8h+var_258], eax
0x1800552e1  cmp     eax, [r15+78h]
0x1800552e5  jnb     loc_180055FE1
0x1800552eb  imul    r15, rax, 0B8h
0x1800552f2  mov     rax, [rsp+2A8h+var_1F0]
0x1800552fa  add     r15, [rax+70h]
0x1800552fe  cmp     [r15+99h], r8b
0x180055305  jz      loc_180055C70
0x18005530b  cmp     [rsp+2A8h+arg_20], r8d
0x180055313  jnz     loc_180055FC6
0x180055319  lea     rax, [rsp+2A8h+var_208]
0x180055321  mov     [rsp+2A8h+var_280], rax
0x180055326  lea     rax, [rsp+2A8h+var_220]
0x18005532e  mov     [rsp+2A8h+var_288], rax
0x180055333  mov     r9, r14
0x180055336  mov     r8, r15
0x180055339  mov     rdx, [rsp+2A8h+var_70]
0x180055341  mov     rcx, rdi
0x180055344  call    ?ShouldDownloadRangelessFile@CDeploymentSession@@QEAAJPEB_WQEBUPayload@ActionList@@PEAV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UWstringCaseInsensitiveCompare@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@PEAHPEA_K@Z; CDeploymentSession::ShouldDownloadRangelessFile(wchar_t const *,ActionList::Payload const * const,std::set<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>> *,int *,unsigned __int64 *)
0x180055349  mov     ebx, eax
0x18005534b  xor     eax, eax
0x18005534d  test    ebx, ebx
0x18005534f  jns     short loc_180055375
0x180055351  mov     rcx, [rdi+258h]
0x180055358  xor     r13d, r13d
0x18005535b  test    rcx, rcx
0x18005535e  jz      loc_180055125
0x180055364  mov     dword ptr [rsp+2A8h+var_280], ebx
0x180055368  mov     dword ptr [rsp+2A8h+var_288], 5E1h
0x180055370  jmp     loc_1800551C0
0x180055375  cmp     dword ptr [rsp+2A8h+var_220], eax
0x18005537c  jz      loc_180055C37
0x180055382  test    r13, r13
0x180055385  jz      short loc_1800553BA
0x180055387  call    cs:__imp_GetProcessHeap
0x18005538e  nop     dword ptr [rax+rax+00h]
0x180055393  mov     rcx, rax; hHeap
0x180055396  lea     r8, [r13-4]; lpMem
0x18005539a  xor     edx, edx; dwFlags
0x18005539c  call    cs:__imp_HeapFree
0x1800553a3  nop     dword ptr [rax+rax+00h]
0x1800553a8  xor     ecx, ecx
0x1800553aa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800553af  xor     r13d, r13d
0x1800553b2  mov     [rsp+2A8h+lpFileName], r13
  ... truncated ...
```
