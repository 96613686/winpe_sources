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
  __int64 v20; // rcx
  int v21; // ecx
  unsigned int v22; // esi
  __int64 v23; // rcx
  __int64 v24; // rcx
  size_t v25; // rbx
  HANDLE ProcessHeap; // rax
  char *v27; // rax
  int v28; // esi
  __int64 v29; // rcx
  int PackageFileListPath; // eax
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // r8
  int v34; // ecx
  unsigned int v35; // edx
  __int64 v36; // rax
  __int64 v37; // r9
  __int64 v38; // r15
  int *v39; // rdx
  HANDLE v40; // rax
  int v41; // eax
  DWORD FileAttributesW; // eax
  BOOL v43; // esi
  int FileSize; // eax
  __int64 v45; // rcx
  signed int LastError; // eax
  int v47; // eax
  unsigned int v48; // esi
  const wchar_t **v49; // rbx
  int v50; // eax
  __int64 v51; // rcx
  __int64 v52; // rcx
  int v53; // eax
  struct CDeploymentFileRequest *v54; // rcx
  int v55; // eax
  __int64 v56; // rcx
  __int64 v57; // rcx
  int v58; // eax
  struct CDeploymentFileRequest *v59; // rdx
  struct CDeploymentFileRequest *v60; // rsi
  int v61; // eax
  int OffsetInOuterContainer; // eax
  int v63; // eax
  struct CDeploymentFileRange *v64; // rax
  int appended; // eax
  __int64 v66; // rcx
  int v67; // esi
  struct CDeploymentFileRequest *v68; // rcx
  int v69; // eax
  int v70; // eax
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  const wchar_t *v75; // r9
  int v76; // eax
  __int64 v77; // r14
  char *v78; // rbx
  WCHAR *v79; // rbx
  HANDLE v80; // rax
  int v81; // eax
  DWORD v82; // eax
  BOOL v83; // ebx
  HANDLE v84; // rax
  int v85; // eax
  int v86; // eax
  __int64 v87; // rsi
  char *v88; // r12
  WCHAR *v89; // rbx
  HANDLE v90; // rax
  int v91; // eax
  DWORD v92; // eax
  BOOL v93; // ebx
  int v94; // eax
  unsigned __int64 v95; // r14
  __int64 v96; // rcx
  unsigned int i; // r15d
  __int64 v98; // rbx
  __int64 v99; // rsi
  __int64 v100; // r14
  __int64 v101; // rcx
  __int64 v102; // rdx
  __int64 v103; // r8
  __int64 v104; // rax
  int PackageExpanderProgress; // eax
  __int64 v106; // r9
  __int64 v107; // rcx
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // rcx
  const wchar_t *v111; // r9
  __int64 v112; // rcx
  int v113; // esi
  __int64 v114; // rcx
  int v115; // eax
  int *v116; // rdx
  __int64 v117; // rax
  const WCHAR *v118; // rbx
  const WCHAR *v119; // rdx
  __int64 v120; // r12
  __int64 v121; // r8
  const WCHAR *v122; // rdx
  __int64 v123; // r8
  __int64 v124; // r8
  __int64 v125; // r8
  int *v126; // rdx
  int v127; // eax
  LPVOID v128; // rdx
  unsigned int v129; // eax
  int v130; // ecx
  __int64 v131; // rdx
  utl::_RefCountBase *v132; // r15
  int v133; // eax
  int *v134; // rdx
  int v135; // eax
  int *v136; // rdx
  __int64 v137; // rcx
  unsigned __int64 v138; // r14
  __int64 v139; // rcx
  unsigned int v140; // r14d
  int v141; // eax
  __int64 v142; // r12
  __int64 v143; // r15
  int v144; // eax
  const WCHAR *v145; // r14
  int v146; // eax
  int *v147; // rdx
  __int64 v148; // rcx
  signed int v149; // eax
  const wchar_t *v150; // r14
  int v151; // eax
  const wchar_t *v152; // r13
  wchar_t *v153; // rbx
  __int64 v154; // rax
  int v155; // eax
  int v156; // eax
  unsigned int j; // ebx
  int v158; // eax
  int v159; // eax
  int v160; // eax
  __int64 v161; // rcx
  struct CDeploymentFileRequest *v162; // rbx
  __int64 v163; // rcx
  int v164; // eax
  __int64 v165; // rcx
  int v166; // eax
  __int64 v167; // rcx
  int v168; // ebx
  unsigned int k; // r15d
  int v170; // eax
  __int64 v171; // r14
  __int64 v172; // r12
  int v173; // eax
  __int64 v174; // rax
  int v175; // eax
  __int64 v176; // rax
  int v177; // eax
  __int64 v178; // rcx
  __int64 v179; // rcx
  const wchar_t *v180; // r9
  __int64 v181; // rcx
  __int64 v182; // rcx
  unsigned int v183; // r14d
  __int64 v184; // rcx
  __int64 v185; // rcx
  unsigned __int64 v186; // rsi
  __int64 v187; // rcx
  unsigned __int64 v188; // r15
  const char *v189; // r9
  __int64 result; // rax
  wchar_t *v191; // [rsp+20h] [rbp-288h]
  int v192; // [rsp+20h] [rbp-288h]
  wchar_t *v193; // [rsp+20h] [rbp-288h]
  unsigned __int64 *v194; // [rsp+28h] [rbp-280h]
  const WCHAR *v195; // [rsp+50h] [rbp-258h] BYREF
  unsigned int v196; // [rsp+58h] [rbp-250h]
  int v197; // [rsp+5Ch] [rbp-24Ch]
  BOOL v198; // [rsp+60h] [rbp-248h] BYREF
  int v199; // [rsp+64h] [rbp-244h]
  wchar_t *Src; // [rsp+68h] [rbp-240h]
  unsigned __int64 v201; // [rsp+70h] [rbp-238h] BYREF
  unsigned __int64 v202; // [rsp+78h] [rbp-230h]
  int v203; // [rsp+80h] [rbp-228h]
  int v204; // [rsp+84h] [rbp-224h]
  struct CDeploymentFileRequest *v205; // [rsp+88h] [rbp-220h] BYREF
  struct IPackageExpanderProgress *v206; // [rsp+90h] [rbp-218h] BYREF
  struct CDeploymentFileRange *v207; // [rsp+98h] [rbp-210h] BYREF
  __int64 v208; // [rsp+A0h] [rbp-208h] BYREF
  unsigned __int64 v209; // [rsp+A8h] [rbp-200h]
  __int64 v210; // [rsp+B0h] [rbp-1F8h]
  struct ActionList::Package *v211; // [rsp+B8h] [rbp-1F0h]
  char v212[8]; // [rsp+C0h] [rbp-1E8h] BYREF
  char *v213; // [rsp+C8h] [rbp-1E0h] BYREF
  unsigned __int64 v214; // [rsp+D0h] [rbp-1D8h]
  __int64 v215; // [rsp+D8h] [rbp-1D0h] BYREF
  __int64 v216; // [rsp+E0h] [rbp-1C8h]
  utl::_RefCountBase *v217[2]; // [rsp+E8h] [rbp-1C0h] BYREF
  __int64 v218; // [rsp+F8h] [rbp-1B0h] BYREF
  __int64 v219; // [rsp+100h] [rbp-1A8h]
  __int128 v220; // [rsp+108h] [rbp-1A0h] BYREF
  __int128 v221; // [rsp+118h] [rbp-190h]
  _OWORD v222[2]; // [rsp+128h] [rbp-180h] BYREF
  unsigned __int64 *v223; // [rsp+148h] [rbp-160h]
  unsigned __int64 *v224; // [rsp+150h] [rbp-158h]
  int *v225; // [rsp+158h] [rbp-150h]
  __int64 v226; // [rsp+160h] [rbp-148h] BYREF
  unsigned __int64 *v227; // [rsp+168h] [rbp-140h]
  _OWORD v228[2]; // [rsp+170h] [rbp-138h] BYREF
  _OWORD v229[2]; // [rsp+190h] [rbp-118h] BYREF
  _OWORD v230[2]; // [rsp+1B0h] [rbp-F8h] BYREF
  __int64 v231; // [rsp+1D0h] [rbp-D8h]
  struct CDeploymentFileRange *v232; // [rsp+1D8h] [rbp-D0h] BYREF
  struct CDeploymentFileRequest *v233; // [rsp+1E0h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+1E8h] [rbp-C0h] BYREF
  struct CDeploymentFileRequest *v235; // [rsp+1F0h] [rbp-B8h] BYREF
  unsigned int v236; // [rsp+1F8h] [rbp-B0h] BYREF
  LPVOID v237; // [rsp+200h] [rbp-A8h] BYREF
  char *v238; // [rsp+208h] [rbp-A0h] BYREF
  int v239; // [rsp+210h] [rbp-98h] BYREF
  LPCWSTR lpFileName; // [rsp+218h] [rbp-90h] BYREF
  LPCWSTR v241; // [rsp+220h] [rbp-88h] BYREF
  __int64 v242; // [rsp+228h] [rbp-80h] BYREF
  LPCWSTR v243; // [rsp+230h] [rbp-78h] BYREF
  wchar_t *v244; // [rsp+238h] [rbp-70h] BYREF
  __int64 v245; // [rsp+240h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+248h] [rbp-60h] BYREF
  __int64 v247; // [rsp+250h] [rbp-58h] BYREF
  __int64 v248; // [rsp+258h] [rbp-50h] BYREF
  __int64 v249; // [rsp+260h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v231 = -2;
  try
  {
    v203 = a4;
    v197 = a3;
    v11 = (struct ActionList::Package *)a2;
    v211 = (struct ActionList::Package *)a2;
    v13 = (int)a6;
    Src = a6;
    v210 = a7;
    v227 = a8;
    v223 = a9;
    v224 = a10;
    v225 = a11;
    v245 = 0;
    v14 = 0;
    v232 = 0;
    v233 = 0;
    v213 = 0;
    v218 = 0;
    v219 = 0;
    v241 = 0;
    v226 = 0;
    *(_OWORD *)v217 = 0;
    v215 = 0;
    v216 = 0;
    v15 = 0;
    v242 = 0;
    v206 = 0;
    bstrString = 0;
    v249 = 0;
    v248 = 0;
    v208 = 0;
    v201 = 0;
    v247 = 0;
    v16 = 0;
    lpFileName = 0;
    v243 = 0;
    v244 = 0;
    v198 = 0;
    LODWORD(v205) = 0;
    v239 = 0;
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
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated);
      goto LABEL_8;
    }
    if ( !a7 )
    {
      v20 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      v192 = 1459;
      goto LABEL_12;
    }
    if ( !a8 )
    {
      v20 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      v192 = 1460;
      goto LABEL_12;
    }
    if ( !a9 )
    {
      v20 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      v192 = 1461;
      goto LABEL_12;
    }
    if ( !a10 )
    {
      v20 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      v192 = 1462;
      goto LABEL_12;
    }
    if ( !a11 )
    {
      v20 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      v192 = 1463;
LABEL_12:
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v20,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GenerateExpressDownloadList",
                                v192,
                                -2147024809);
      goto LABEL_6;
    }
    v21 = *(_DWORD *)(a2 + 120);
    if ( v21 )
    {
      v22 = 88 * v21;
      if ( 88 * v21 / 0x58u != v21 )
      {
        v22 = 0;
        ShouldDownloadRangelessFile = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        v11 = v211;
        goto LABEL_30;
      }
    }
    else
    {
      v22 = 0;
    }
    ShouldDownloadRangelessFile = 0;
LABEL_30:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
    if ( ShouldDownloadRangelessFile < 0 )
    {
      v23 = *((_QWORD *)this + 75);
      v16 = 0;
      if ( !v23 )
        goto LABEL_32;
      v24 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                            v23,
                            4,
                            L"%s(%d): Result = 0x%X",
                            L"CDeploymentSession::GenerateExpressDownloadList",
                            1470,
                            ShouldDownloadRangelessFile);
      goto LABEL_34;
    }
    v25 = v22;
    ProcessHeap = GetProcessHeap();
    v27 = (char *)HeapAlloc(ProcessHeap, 0, v22);
    v238 = v27;
    v28 = 0;
    if ( !v27 )
    {
      v16 = 0;
      v213 = 0;
      v29 = *((_QWORD *)this + 75);
      ShouldDownloadRangelessFile = -2147024882;
      if ( v29 )
      {
        LODWORD(v194) = -2147024882;
        LODWORD(v191) = 1472;
        goto LABEL_40;
      }
      goto LABEL_32;
    }
    v213 = v27;
    memset_0(v27, 0, v25);
    if ( !a5 )
    {
      PackageFileListPath = CDeploymentSession::GetPackageFileListPath(this, v11, &v244);
      ShouldDownloadRangelessFile = PackageFileListPath;
      if ( PackageFileListPath < 0 )
      {
        v29 = *((_QWORD *)this + 75);
        v16 = 0;
        if ( v29 )
        {
          LODWORD(v194) = PackageFileListPath;
          LODWORD(v191) = 1480;
          goto LABEL_40;
        }
        goto LABEL_32;
      }
    }
    v31 = *((_QWORD *)this + 75);
    if ( v31 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v31, 2, L"Package: [%s]", *((_QWORD *)v11 + 7));
    v32 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v210 + 40LL))(v210, &v245);
    ShouldDownloadRangelessFile = v32;
    v33 = 0;
    if ( v32 < 0 )
    {
      v29 = *((_QWORD *)this + 75);
      v16 = 0;
      if ( v29 )
      {
        LODWORD(v194) = v32;
        LODWORD(v191) = 1490;
        goto LABEL_40;
      }
      goto LABEL_32;
    }
    v204 = 0;
    v214 = 0;
    v34 = 0;
    v199 = 0;
    v236 = 0;
    v202 = 0;
    v209 = 0;
    v35 = 0;
    v196 = 0;
    v36 = 0;
    v37 = 1;
    while ( 1 )
    {
      LODWORD(v195) = v36;
      if ( (unsigned int)v36 >= *((_DWORD *)v11 + 30) )
        break;
      v38 = *((_QWORD *)v211 + 14) + 184 * v36;
      if ( *(_BYTE *)(v38 + 153) )
      {
        if ( !a5 )
        {
          ShouldDownloadRangelessFile = CDeploymentSession::ShouldDownloadRangelessFile(
                                          (_DWORD)this,
                                          (_DWORD)v244,
                                          v38,
                                          v13,
                                          (__int64)&v205,
                                          (__int64)&v208);
          if ( ShouldDownloadRangelessFile < 0 )
          {
            v29 = *((_QWORD *)this + 75);
            v16 = 0;
            if ( v29 )
            {
              LODWORD(v194) = ShouldDownloadRangelessFile;
              LODWORD(v191) = 1505;
              goto LABEL_40;
            }
            goto LABEL_32;
          }
          if ( (_DWORD)v205 )
          {
            if ( v16 )
            {
              v40 = GetProcessHeap();
              HeapFree(v40, 0, v16 - 2);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              v16 = 0;
              lpFileName = 0;
            }
            v41 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)(v38 + 80), 0, &lpFileName);
            ShouldDownloadRangelessFile = v41;
            if ( v41 < 0 )
            {
              v29 = *((_QWORD *)this + 75);
              if ( v29 )
              {
                LODWORD(v194) = v41;
                LODWORD(v191) = 1512;
                goto LABEL_40;
              }
              goto LABEL_32;
            }
            v16 = (WCHAR *)lpFileName;
            FileAttributesW = GetFileAttributesW(lpFileName);
            v43 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
            v198 = v43;
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            if ( !v43 )
              goto LABEL_83;
            FileSize = CMoUpdateHelpersT<CEmptyType>::GetFileSize(v16, &v248);
            ShouldDownloadRangelessFile = FileSize;
            if ( FileSize < 0 )
            {
              v29 = *((_QWORD *)this + 75);
              v16 = 0;
              if ( v29 )
              {
                LODWORD(v194) = FileSize;
                LODWORD(v191) = 1517;
                goto LABEL_40;
              }
              goto LABEL_32;
            }
            ShouldDownloadRangelessFile = 0;
            if ( !v248 )
            {
              v45 = *((_QWORD *)this + 75);
              if ( v45 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v45,
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
                v24 = 0;
                if ( ShouldDownloadRangelessFile < 0 && *((_QWORD *)this + 75) )
                {
                  LODWORD(v194) = ShouldDownloadRangelessFile;
                  LODWORD(v191) = 1521;
                  v29 = *((_QWORD *)this + 75);
                  goto LABEL_40;
                }
                goto LABEL_36;
              }
              v204 = 1;
              v43 = 0;
              v198 = 0;
            }
            if ( !v43 )
            {
LABEL_83:
              LODWORD(v237) = 0;
              if ( v233 )
              {
                (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v233 + 16LL))(v233);
                v233 = 0;
              }
              if ( *(_QWORD *)(v38 + 48) )
              {
                v47 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v245 + 24LL))(v245, &v237);
                ShouldDownloadRangelessFile = v47;
                if ( v47 < 0 )
                {
                  v29 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( v29 )
                  {
                    LODWORD(v194) = v47;
                    LODWORD(v191) = 1538;
                    goto LABEL_40;
                  }
                  goto LABEL_32;
                }
                v48 = 0;
                v49 = (const wchar_t **)(v38 + 64);
                while ( 1 )
                {
                  if ( v48 >= (unsigned int)v237 )
                    goto LABEL_115;
                  v235 = 0;
                  pv = 0;
                  v50 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct CDeploymentFileRequest **))(*(_QWORD *)v245 + 32LL))(
                          v245,
                          v48,
                          &v235);
                  ShouldDownloadRangelessFile = v50;
                  if ( v50 < 0 )
                  {
                    v51 = *((_QWORD *)this + 75);
                    v16 = 0;
                    if ( v51 )
                    {
                      LODWORD(v194) = v50;
                      LODWORD(v191) = 1545;
                      v53 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v51,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::GenerateExpressDownloadList",
                              v191,
                              v194);
                      v52 = (unsigned int)v53;
                      if ( v53 < 0 )
                        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v53);
                    }
                    else
                    {
                      v52 = 0;
                    }
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v52);
                    if ( pv )
                    {
                      CoTaskMemFree(pv);
                      pv = 0;
                    }
                    v54 = v235;
                    if ( !v235 )
                      goto LABEL_438;
                    goto LABEL_99;
                  }
                  v55 = (*(__int64 (__fastcall **)(struct CDeploymentFileRequest *, LPVOID *))(*(_QWORD *)v235 + 24LL))(
                          v235,
                          &pv);
                  ShouldDownloadRangelessFile = v55;
                  if ( v55 < 0 )
                  {
                    v56 = *((_QWORD *)this + 75);
                    v16 = 0;
                    if ( v56 )
                    {
                      LODWORD(v194) = v55;
                      LODWORD(v191) = 1546;
                      v58 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v56,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::GenerateExpressDownloadList",
                              v191,
                              v194);
                      v57 = (unsigned int)v58;
                      if ( v58 < 0 )
                        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v58);
                    }
                    else
                    {
                      v57 = 0;
                    }
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v57);
                    if ( pv )
                    {
                      CoTaskMemFree(pv);
                      pv = 0;
                    }
                    v54 = v235;
                    if ( !v235 )
                      goto LABEL_438;
LABEL_99:
                    (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v235 + 16LL))(v54);
                    goto LABEL_438;
                  }
                  v49 = (const wchar_t **)(v38 + 64);
                  if ( !(unsigned int)_o__wcsicmp(pv, *(_QWORD *)(v38 + 64)) )
                    break;
                  if ( pv )
                  {
                    CoTaskMemFree(pv);
                    pv = 0;
                  }
                  if ( v235 )
                  {
                    (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v235 + 16LL))(v235);
                    v235 = 0;
                  }
                  ++v48;
                }
                v59 = v235;
                v60 = v235;
                if ( pv )
                {
                  CoTaskMemFree(pv);
                  pv = 0;
                  v59 = v235;
                }
                if ( v59 )
                {
                  (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v59 + 16LL))(v59);
                  v235 = 0;
                }
                if ( !v60 )
                {
LABEL_115:
                  v61 = CDeploymentFileRequest::Create(
                          *v49,
                          *(const wchar_t **)(v38 + 48),
                          *(const wchar_t **)(v38 + 48),
                          *(const wchar_t **)(v38 + 88),
                          L"Canonical",
                          v197,
                          &v233);
                  ShouldDownloadRangelessFile = v61;
                  if ( v61 < 0 )
                  {
                    v29 = *((_QWORD *)this + 75);
                    v16 = 0;
                    if ( v29 )
                    {
                      LODWORD(v194) = v61;
                      LODWORD(v191) = 1563;
                      goto LABEL_40;
                    }
LABEL_32:
                    v24 = (unsigned int)v16;
LABEL_36:
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v24);
LABEL_438:
                    v14 = v232;
LABEL_439:
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v244);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v243);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v247);
                    if ( bstrString )
                    {
                      SysFreeString(bstrString);
                      bstrString = v16;
                    }
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v242);
                    CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::~CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>(&v215);
                    if ( v217[1] )
                      utl::_RefCountBase::_DecStrong(v217[1]);
                    SP_ARBITER<SessionData>::~SP_ARBITER<SessionData>(&v226);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v241);
                    CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::~CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>(&v218);
                    SP_MEM<wchar_t>::~SP_MEM<wchar_t>(&v213);
                    if ( v233 )
                      (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v233 + 16LL))(v233);
                    if ( v14 )
                      (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v14 + 16LL))(v14);
                    SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v245);
                    return (unsigned int)ShouldDownloadRangelessFile;
                  }
                  v60 = v233;
                }
                if ( v232 )
                {
                  (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v232 + 16LL))(v232);
                  v232 = 0;
                }
                OffsetInOuterContainer = CDeploymentSession::GetOffsetInOuterContainer(
                                           this,
                                           *(const wchar_t **)(v38 + 48),
                                           *(const wchar_t **)(v38 + 56),
                                           *(const wchar_t **)(v38 + 72),
                                           *(const wchar_t **)(v38 + 112),
                                           &v201,
                                           0);
                ShouldDownloadRangelessFile = OffsetInOuterContainer;
                if ( OffsetInOuterContainer < 0 )
                {
                  v29 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( !v29 )
                    goto LABEL_32;
                  LODWORD(v194) = OffsetInOuterContainer;
                  LODWORD(v191) = 1572;
                  goto LABEL_40;
                }
                v63 = CDeploymentFileRange::Create(v201, *(_QWORD *)(v38 + 160), &v232);
                ShouldDownloadRangelessFile = v63;
                if ( v63 < 0 )
                {
                  v29 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( !v29 )
                    goto LABEL_32;
                  LODWORD(v194) = v63;
                  LODWORD(v191) = 1573;
                  goto LABEL_40;
                }
                v64 = v232;
                v232 = 0;
                v207 = v64;
                appended = CDeploymentFileRequest::AppendFileRange(v60, &v207);
                ShouldDownloadRangelessFile = appended;
                v29 = *((_QWORD *)this + 75);
                if ( appended < 0 )
                {
                  v16 = 0;
                  if ( !v29 )
                    goto LABEL_32;
                  LODWORD(v194) = appended;
                  LODWORD(v191) = 1574;
                  goto LABEL_40;
                }
                if ( v29 )
                  CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v29,
                    2,
                    L"        Rangeless file container: [%ws]",
                    *(_QWORD *)(v38 + 48));
                v66 = *((_QWORD *)this + 75);
                if ( v66 )
                  CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v66,
                    2,
                    L"        Rangeless file container offset: [%llu]",
                    v201);
                v67 = v197;
                v13 = (int)Src;
              }
              else
              {
                v67 = v197;
                v70 = CDeploymentFileRequest::Create(
                        *(const wchar_t **)(v38 + 112),
                        *(const wchar_t **)(v38 + 80),
                        *(const wchar_t **)(v38 + 72),
                        *(const wchar_t **)(v38 + 88),
                        L"Canonical",
                        v197,
                        &v233);
                ShouldDownloadRangelessFile = v70;
                if ( v70 < 0 )
                {
                  v29 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( !v29 )
                    goto LABEL_32;
                  LODWORD(v194) = v70;
                  LODWORD(v191) = 1587;
                  goto LABEL_40;
                }
              }
              v68 = v233;
              if ( v233 )
              {
                v233 = 0;
                v207 = v68;
                v69 = CDeploymentDownloadRequest::AppendFileRequest(v210, &v207);
                ShouldDownloadRangelessFile = v69;
                if ( v69 < 0 )
                {
                  v29 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( !v29 )
                    goto LABEL_32;
                  LODWORD(v194) = v69;
                  LODWORD(v191) = 1592;
                  goto LABEL_40;
                }
              }
              v71 = *((_QWORD *)this + 75);
              if ( v71 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v71, 2, L"        Rangeless file name: [%s]", v16);
              v72 = *((_QWORD *)this + 75);
              if ( v72 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v72,
                  2,
                  L"        Rangeless file size: [%llu]",
                  *(_QWORD *)(v38 + 160));
              v73 = *((_QWORD *)this + 75);
              if ( v73 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v73, 2, L"        Extraction file size: [%lu]", v208);
              v74 = *((_QWORD *)this + 75);
              if ( v74 )
              {
                v75 = L"TRUE";
                if ( !v67 )
                  v75 = L"FALSE";
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v74, 2, L"        Optional: [%s]", v75);
              }
              if ( v202 + *(_QWORD *)(v38 + 160) < v202 )
              {
                ShouldDownloadRangelessFile = -2147024362;
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
              }
              else
              {
                v202 += *(_QWORD *)(v38 + 160);
                ShouldDownloadRangelessFile = 0;
              }
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
              if ( ShouldDownloadRangelessFile < 0 )
              {
                v29 = *((_QWORD *)this + 75);
                v16 = 0;
                if ( !v29 )
                  goto LABEL_32;
                LODWORD(v194) = ShouldDownloadRangelessFile;
                LODWORD(v191) = 1599;
                goto LABEL_40;
              }
              ShouldDownloadRangelessFile = 0;
            }
            if ( v209 + *(_QWORD *)(v38 + 160) < v209 )
            {
              ShouldDownloadRangelessFile = -2147024362;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            }
            else
            {
              v209 += *(_QWORD *)(v38 + 160);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
            if ( ShouldDownloadRangelessFile < 0 )
            {
              v29 = *((_QWORD *)this + 75);
              v16 = 0;
              if ( !v29 )
                goto LABEL_32;
              LODWORD(v194) = ShouldDownloadRangelessFile;
              LODWORD(v191) = 1602;
              goto LABEL_40;
            }
            if ( v214 + v208 < v214 )
            {
              ShouldDownloadRangelessFile = -2147024362;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            }
            else
            {
              v214 += v208;
              ShouldDownloadRangelessFile = 0;
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
            if ( ShouldDownloadRangelessFile < 0 )
            {
              v29 = *((_QWORD *)this + 75);
              v16 = 0;
              if ( !v29 )
                goto LABEL_32;
              LODWORD(v194) = ShouldDownloadRangelessFile;
              LODWORD(v191) = 1603;
              goto LABEL_40;
            }
          }
          v76 = CDeploymentSession::CheckCancelRequested(this, v39);
          ShouldDownloadRangelessFile = v76;
          v33 = 0;
          if ( v76 < 0 )
          {
            v29 = *((_QWORD *)this + 75);
            v16 = 0;
            if ( !v29 )
              goto LABEL_32;
            LODWORD(v194) = v76;
            LODWORD(v191) = 1606;
            goto LABEL_40;
          }
          v35 = v196;
          v34 = v199;
          v37 = 1;
        }
      }
      else
      {
        v77 = 88LL * v35;
        v78 = v238;
        *(_QWORD *)&v238[v77] = *(_QWORD *)(v38 + 72);
        *(_QWORD *)&v78[v77 + 8] = *(_QWORD *)(v38 + 80);
        *(_QWORD *)&v78[v77 + 16] = *(_QWORD *)(v38 + 88);
        *(_QWORD *)&v78[v77 + 24] = *(_QWORD *)(v38 + 112);
        *(_QWORD *)&v78[v77 + 48] = *(_QWORD *)(v38 + 48);
        *(_QWORD *)&v78[v77 + 56] = *(_QWORD *)(v38 + 64);
        if ( v243 )
        {
          v79 = (WCHAR *)(v243 - 2);
          v80 = GetProcessHeap();
          HeapFree(v80, 0, v79);
          v78 = v238;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v243 = 0;
        }
        v81 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)&v78[v77 + 8], 0, &v243);
        ShouldDownloadRangelessFile = v81;
        if ( v81 < 0 )
        {
          v29 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( !v29 )
            goto LABEL_32;
          LODWORD(v194) = v81;
          LODWORD(v191) = 1620;
          goto LABEL_40;
        }
        v82 = GetFileAttributesW(v243);
        v83 = v82 != -1 && (v82 & 0x10) == 0;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( v83 )
          v28 = 1;
        v236 = v28;
        if ( v15 )
        {
          v84 = GetProcessHeap();
          HeapFree(v84, 0, (LPVOID)(v15 - 4));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v242 = 0;
        }
        v85 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 62), *(_QWORD *)(v38 + 120), 0, &v242);
        ShouldDownloadRangelessFile = v85;
        if ( v85 < 0 )
        {
          v29 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( !v29 )
            goto LABEL_32;
          LODWORD(v194) = v85;
          LODWORD(v191) = 1628;
          goto LABEL_40;
        }
        v86 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(&v215, &v242);
        ShouldDownloadRangelessFile = v86;
        if ( v86 < 0 )
        {
          v29 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( !v29 )
            goto LABEL_32;
          LODWORD(v194) = v86;
          LODWORD(v191) = 1629;
          goto LABEL_40;
        }
        v87 = (int)v196;
        v88 = v238;
        *(_QWORD *)&v238[v77 + 32] = *(_QWORD *)(v216 + 8LL * (int)v196);
        if ( v241 )
        {
          v89 = (WCHAR *)(v241 - 2);
          v90 = GetProcessHeap();
          HeapFree(v90, 0, v89);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v241 = 0;
        }
        v91 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)(v38 + 72), 0, &v241);
        ShouldDownloadRangelessFile = v91;
        if ( v91 < 0 )
        {
          v29 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( !v29 )
            goto LABEL_32;
          LODWORD(v194) = v91;
          LODWORD(v191) = 1635;
          goto LABEL_40;
        }
        v92 = GetFileAttributesW(v241);
        v93 = v92 != -1 && (v92 & 0x10) == 0;
        v198 = v93;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v33 = 0;
        if ( v93 )
        {
          v94 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(&v218, &v241);
          ShouldDownloadRangelessFile = v94;
          v33 = 0;
          if ( v94 < 0 )
          {
            v29 = *((_QWORD *)this + 75);
            v16 = 0;
            if ( !v29 )
              goto LABEL_32;
            LODWORD(v194) = v94;
            LODWORD(v191) = 1639;
            goto LABEL_40;
          }
          *(_QWORD *)&v88[v77 + 40] = *(_QWORD *)(v219 + 8 * v87);
          v37 = 1;
          v34 = 1;
          v199 = 1;
        }
        else
        {
          v34 = v199;
          v37 = 1;
        }
        v35 = ++v196;
        v15 = v242;
        v13 = (int)Src;
      }
      v36 = (unsigned int)((_DWORD)v195 + 1);
      v28 = v236;
      v11 = v211;
    }
    v16 = 0;
    v95 = 0;
    v201 = 0;
    if ( !v35 )
    {
      v96 = *((_QWORD *)this + 75);
      if ( v96 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v96, 2, L"    All Express content is rangeless.", 1);
      goto LABEL_428;
    }
    if ( a5 )
    {
      if ( !v34 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= *((_DWORD *)v211 + 30) )
            goto LABEL_427;
          v98 = 184LL * i;
          v99 = *((_QWORD *)v211 + 14);
          if ( *(_QWORD *)(v98 + v99 + 64) && (v100 = v98 + v99, *(_QWORD *)(v98 + v99 + 48)) )
          {
            if ( !(unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::contains<wchar_t *>(
                                     (char *)this + 768,
                                     v100 + 48,
                                     v33,
                                     v37) )
            {
              v101 = *((_QWORD *)this + 75);
              if ( v101 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v101,
                  2,
                  L"    Adding container file: [%s]",
                  *(_QWORD *)(v100 + 48));
              ShouldDownloadRangelessFile = CDeploymentFileRequest::Create(
                                              *(const wchar_t **)(v98 + v99 + 64),
                                              *(const wchar_t **)(v100 + 48),
                                              *(const wchar_t **)(v100 + 48),
                                              0,
                                              L"Canonical",
                                              v197,
                                              &v233);
              if ( ShouldDownloadRangelessFile < 0 )
              {
                v29 = *((_QWORD *)this + 75);
                v16 = 0;
                if ( !v29 )
                  goto LABEL_32;
                LODWORD(v194) = ShouldDownloadRangelessFile;
                LODWORD(v191) = 1676;
LABEL_40:
                v24 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                      v29,
                                      4,
                                      L"%s(%d): Result = 0x%X",
                                      L"CDeploymentSession::GenerateExpressDownloadList",
                                      v191,
                                      v194);
LABEL_34:
                if ( (int)v24 < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v24);
                goto LABEL_36;
              }
              v102 = *(_QWORD *)(v100 + 48);
              v220 = 0;
              v221 = 0;
              v103 = -1;
              do
                ++v103;
              while ( *(_WORD *)(v102 + 2 * v103) );
              std::wstring::_Construct<1,wchar_t const *>(&v220);
              std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
                (char *)this + 768,
                v222,
                &v220);
              std::wstring::~wstring(&v220);
            }
            v16 = 0;
          }
          else
          {
            v107 = *((_QWORD *)this + 75);
            if ( v107 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v107,
                2,
                L"    Adding PSF file: [%s]",
                *(_QWORD *)(v98 + v99 + 72));
            PackageExpanderProgress = CDeploymentFileRequest::Create(
                                        *(const wchar_t **)(v98 + v99 + 112),
                                        *(const wchar_t **)(v98 + v99 + 72),
                                        *(const wchar_t **)(v98 + v99 + 72),
                                        *(const wchar_t **)(v98 + v99 + 88),
                                        L"Canonical",
                                        v197,
                                        &v233);
            ShouldDownloadRangelessFile = PackageExpanderProgress;
            if ( PackageExpanderProgress < 0 )
            {
              v106 = 1693;
              goto LABEL_239;
            }
          }
          v104 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(&v206, &v233);
          PackageExpanderProgress = CDeploymentDownloadRequest::AppendFileRequest(v210, v104);
          ShouldDownloadRangelessFile = PackageExpanderProgress;
          if ( PackageExpanderProgress < 0 )
          {
            v106 = 1696;
            goto LABEL_239;
          }
        }
      }
LABEL_428:
      v185 = *((_QWORD *)this + 75);
      v186 = v202;
      if ( v185 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v185, 2, L"    Required Download size : [%llu]", v202);
      v187 = *((_QWORD *)this + 75);
      v188 = v209;
      if ( v187 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v187, 2, L"    Total Download size : [%llu]", v209);
      if ( v95 + v214 < v95 )
      {
        ShouldDownloadRangelessFile = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
      }
      else
      {
        v95 += v214;
        ShouldDownloadRangelessFile = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
      if ( ShouldDownloadRangelessFile >= 0 )
      {
        *v227 = v186;
        *v223 = v188;
        *v224 = v95;
        *v225 = v204;
        goto LABEL_438;
      }
      v106 = 1945;
      v108 = (unsigned int)ShouldDownloadRangelessFile;
      goto LABEL_240;
    }
    v110 = *((_QWORD *)this + 75);
    if ( v110 )
    {
      v111 = L"TRUE";
      if ( !v28 )
        v111 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v110, 2, L"Range file Exists: [%s]", v111);
    }
    if ( !*((_DWORD *)this + 66) || v28 )
    {
      v113 = 1;
      v114 = *((_QWORD *)this + 75);
      if ( v114 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v114, 2, L"    Calculating ranges", 1);
    }
    else
    {
      v112 = *((_QWORD *)this + 75);
      if ( v112 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v112, 2, L"    Calculating ranges (new job)", 1);
      v113 = 5;
    }
    PackageExpanderProgress = CProgressHandler::GetPackageExpanderProgress(
                                *((CProgressHandler **)this + 60),
                                *((const wchar_t **)v11 + 7),
                                &v206);
    ShouldDownloadRangelessFile = PackageExpanderProgress;
    if ( PackageExpanderProgress < 0 )
    {
      v106 = 1721;
LABEL_239:
      v108 = (unsigned int)PackageExpanderProgress;
LABEL_240:
      v109 = *((_QWORD *)this + 75);
LABEL_241:
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(v109, v108, L"CDeploymentSession::GenerateExpressDownloadList", v106);
      goto LABEL_438;
    }
    v115 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *((_QWORD *)v11 + 7), 0, &v247);
    ShouldDownloadRangelessFile = v115;
    v109 = *((_QWORD *)this + 75);
    if ( v115 < 0 )
    {
      v106 = 1722;
      v108 = (unsigned int)v115;
      goto LABEL_241;
    }
    PackageExpanderProgress = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v109 + 88LL))(v109, &bstrString);
    ShouldDownloadRangelessFile = PackageExpanderProgress;
    if ( PackageExpanderProgress < 0 )
    {
      v106 = 1723;
      goto LABEL_239;
    }
    PackageExpanderProgress = CDeploymentSession::CheckCancelRequested(this, v116);
    ShouldDownloadRangelessFile = PackageExpanderProgress;
    if ( PackageExpanderProgress < 0 )
    {
      v106 = 1725;
      goto LABEL_239;
    }
    v117 = *((_QWORD *)this + 80);
    if ( v117 && *(_DWORD *)(v117 + 8) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    UpdateAgentMisc::ConvertWinDirToDefaultBootDir(&v195, *((_QWORD *)this + 70));
    pv = 0;
    v118 = &String2;
    v119 = &String2;
    if ( *((_QWORD *)this + 70) )
      v119 = (const WCHAR *)*((_QWORD *)this + 70);
    memset(v230, 0, sizeof(v230));
    v120 = -1;
    v121 = -1;
    do
      ++v121;
    while ( v119[v121] );
    std::wstring::_Construct<1,wchar_t const *>(v230);
    v122 = &String2;
    if ( v195 )
      v122 = v195;
    memset(v229, 0, sizeof(v229));
    v123 = -1;
    do
      ++v123;
    while ( v122[v123] );
    std::wstring::_Construct<1,wchar_t const *>(v229);
    if ( *((_QWORD *)this + 67) )
    {
      v118 = (const WCHAR *)*((_QWORD *)this + 67);
    }
    else if ( *((_QWORD *)this + 62) )
    {
      v118 = (const WCHAR *)*((_QWORD *)this + 62);
    }
    memset(v228, 0, sizeof(v228));
    v124 = -1;
    do
      ++v124;
    while ( v118[v124] );
    std::wstring::_Construct<1,wchar_t const *>(v228);
    memset(v222, 0, sizeof(v222));
    v125 = -1;
    do
      ++v125;
    while ( bstrString[v125] );
    std::wstring::_Construct<1,wchar_t const *>(v222);
    v220 = 0;
    v221 = 0;
    do
      ++v120;
    while ( *(_WORD *)(v247 + 2 * v120) );
    std::wstring::_Construct<1,wchar_t const *>(&v220);
    ShouldDownloadRangelessFile = GetPackageExpanderEx(
                                    v113,
                                    (*((_DWORD *)this + 150) + 24) & (unsigned int)-(*((_QWORD *)this + 75) != 0),
                                    (_DWORD)v206,
                                    (unsigned int)&v220,
                                    (__int64)v222,
                                    (__int64)v228,
                                    (__int64)v229,
                                    (__int64)v230,
                                    (__int64)&pv,
                                    (__int64)&v239);
    std::wstring::~wstring(&v220);
    std::wstring::~wstring(v222);
    std::wstring::~wstring(v228);
    std::wstring::~wstring(v229);
    std::wstring::~wstring(v230);
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
    v127 = CDeploymentSession::CheckCancelRequested(this, v126);
    ShouldDownloadRangelessFile = v127;
    if ( v127 < 0 )
    {
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        *((_QWORD *)this + 75),
        (unsigned int)v127,
        L"CDeploymentSession::GenerateExpressDownloadList",
        1741);
      if ( pv )
        (**(void (__fastcall ***)(LPVOID))pv)(pv);
      goto LABEL_287;
    }
    v128 = pv;
    pv = 0;
    if ( !(unsigned __int8)___reset_VIPackageExpander__V_lambda_1___0__GenerateExpressDownloadList_CDeploymentSession__QEAAJQEBUPackage_ActionList__HHHPEAV__set_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UWstringCaseInsensitiveCompare__V__allocator_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__std__PEAVCDeploymentDownloadRequest__PEA_K33PEAH_Z__0A____shared_ptr_VIPackageExpander___utl__QEAA_NPEAVIPackageExpander__V_lambda_1___0__GenerateExpressDownloadList_CDeploymentSession__QEAAJQEBUPackage_ActionList__HHHPEAV__set_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UWstringCaseInsensitiveCompare__V__allocator_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__std__PEAVCDeploymentDownloadRequest__PEA_K44PEAH_Z__Z(
                             v217,
                             v128) )
    {
      ShouldDownloadRangelessFile = -2147467261;
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        *((_QWORD *)this + 75),
        2147500035LL,
        L"CDeploymentSession::GenerateExpressDownloadList",
        1743);
LABEL_287:
      __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v195);
      goto LABEL_438;
    }
    utl::weak_ptr<IPackageExpander>::operator=<IPackageExpander,0>((char *)this + 632, v217);
    v129 = *((_DWORD *)this + 114);
    if ( v129 <= 0x16 && (v130 = 4195888, _bittest(&v130, v129)) || (v131 = 0, v129 == 6) )
    {
      v131 = 1;
      if ( v129 == 9 )
        v131 = 3;
    }
    v132 = v217[0];
    v193 = v244;
    v133 = (*(__int64 (__fastcall **)(utl::_RefCountBase *, __int64, char *, _QWORD))(*(_QWORD *)v217[0] + 8LL))(
             v217[0],
             v131,
             v238,
             v196);
    ShouldDownloadRangelessFile = v133;
    if ( v133 < 0 )
    {
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        *((_QWORD *)this + 75),
        (unsigned int)v133,
        L"CDeploymentSession::GenerateExpressDownloadList",
        1764);
      goto LABEL_287;
    }
    v135 = CDeploymentSession::CheckCancelRequested(this, v134);
    ShouldDownloadRangelessFile = v135;
    v137 = *((_QWORD *)this + 75);
    if ( v135 < 0 )
    {
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        v137,
        (unsigned int)v135,
        L"CDeploymentSession::GenerateExpressDownloadList",
        1766);
      goto LABEL_287;
    }
    if ( *((_DWORD *)v132 + 4) )
    {
      v138 = *((_QWORD *)v132 + 3);
      v201 = v138;
      if ( v137 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v137, 2, L"    Expand size: [%llu]", v138, v193);
      v139 = *((_QWORD *)this + 75);
      if ( v139 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v139,
          2,
          L"    Required RNG files count:[%lu]",
          *((unsigned int *)v132 + 4));
    }
    else
    {
      v201 = 0;
      if ( v137 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v137, 2, L"    Already expanded");
    }
    v140 = 0;
    while ( 1 )
    {
      v196 = v140;
      if ( v140 >= *((_DWORD *)v132 + 4) )
      {
        Windows::AutoReleasePtr<IPackageExpander>::~AutoReleasePtr<IPackageExpander>(&pv);
        __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v195);
LABEL_427:
        v95 = v201;
        goto LABEL_428;
      }
      v141 = CDeploymentSession::CheckCancelRequested(this, v136);
      ShouldDownloadRangelessFile = v141;
      if ( v141 < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v141,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1786);
        goto LABEL_287;
      }
      v142 = 88LL * v140;
      *(_QWORD *)&v222[0] = v142;
      v143 = *((_QWORD *)v132 + 1);
      v208 = v143;
      v206 = 0;
      SH_SSTRING::operator=(&lpFileName);
      v144 = CMiscHelpersT<CEmptyType>::CombinePath(
               *((_QWORD *)this + 61),
               *(_QWORD *)(v143 + v142 + 8),
               0,
               &lpFileName);
      ShouldDownloadRangelessFile = v144;
      if ( v144 < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v144,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1795);
        goto LABEL_287;
      }
      v145 = lpFileName;
      v146 = CMiscHelpersT<CEmptyType>::FileExists(lpFileName, &v198);
      ShouldDownloadRangelessFile = v146;
      if ( v146 < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v146,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1796);
        goto LABEL_287;
      }
      LODWORD(v16) = v198;
      if ( v198 )
      {
        ShouldDownloadRangelessFile = CMoUpdateHelpersT<CEmptyType>::GetFileSize(v145, &v249);
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
        if ( !v249 )
        {
          v148 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( v148 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v148, 2, L"    Deleting zero byte RNG file: [%s]", v145);
          if ( !DeleteFileW(v145) )
          {
            v149 = GetLastError();
            ShouldDownloadRangelessFile = v149;
            if ( v149 )
            {
              if ( v149 > 0 )
                ShouldDownloadRangelessFile = (unsigned __int16)v149 | 0x80070000;
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
          v204 = 1;
          v198 = 0;
        }
      }
      v205 = 0;
      if ( (_DWORD)v16 )
        break;
      v150 = *(const wchar_t **)(v143 + v142 + 48);
      v16 = 0;
      if ( v150 )
      {
        Src = *(wchar_t **)(v143 + v142 + 56);
        v151 = CDeploymentSession::GetOffsetInOuterContainer(
                 this,
                 v150,
                 0,
                 *(const wchar_t **)(v143 + v142),
                 *(const wchar_t **)(v143 + v142 + 24),
                 (unsigned __int64 *)&v206,
                 0);
        ShouldDownloadRangelessFile = v151;
        if ( v151 < 0 )
        {
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)v151,
            L"CDeploymentSession::GenerateExpressDownloadList",
            1821);
          goto LABEL_287;
        }
        v152 = v150;
        v153 = Src;
      }
      else
      {
        v153 = *(wchar_t **)(v143 + v142 + 24);
        Src = v153;
        v150 = *(const wchar_t **)(v143 + v142);
        v152 = *(const wchar_t **)(v143 + v142 + 8);
      }
      v147 = 0;
      if ( v233 )
      {
        (*(void (__fastcall **)(struct CDeploymentFileRequest *, _QWORD))(*(_QWORD *)v233 + 16LL))(v233, 0);
        v147 = 0;
        v233 = 0;
      }
      if ( !v203 )
      {
        v16 = 0;
        if ( !v199 )
        {
          v165 = *((_QWORD *)this + 75);
          if ( v165 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v165, 2, L"    Adding PSF file: [%s]", v150);
          v166 = CDeploymentFileRequest::Create(
                   v153,
                   v150,
                   v150,
                   *(const wchar_t **)(v143 + v142 + 16),
                   L"Canonical",
                   v197,
                   &v233);
          ShouldDownloadRangelessFile = v166;
          if ( v166 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v166,
              L"CDeploymentSession::GenerateExpressDownloadList",
              1888);
            goto LABEL_287;
          }
        }
LABEL_376:
        v168 = v203;
        if ( !v203 )
          goto LABEL_394;
        goto LABEL_377;
      }
      if ( *(_QWORD *)(v143 + v142 + 56) )
      {
        v236 = 0;
        v154 = *(_QWORD *)v210;
        v238 = 0;
        v155 = (*(__int64 (__fastcall **)(__int64, char **))(v154 + 40))(v210, &v238);
        if ( v155 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x732,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v155,
            (int)v193);
        v156 = (*(__int64 (__fastcall **)(char *, unsigned int *))(*(_QWORD *)v238 + 24LL))(v238, &v236);
        v147 = 0;
        if ( v156 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x733,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v156,
            (int)v193);
        for ( j = 0; ; ++j )
        {
          if ( j >= v236 )
          {
            v162 = v205;
            goto LABEL_360;
          }
          v235 = 0;
          v237 = 0;
          v158 = (*(__int64 (__fastcall **)(char *, _QWORD, struct CDeploymentFileRequest **))(*(_QWORD *)v238 + 32LL))(
                   v238,
                   j,
                   &v235);
          if ( v158 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x73A,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v158,
              (int)v193);
          v159 = (*(__int64 (__fastcall **)(struct CDeploymentFileRequest *, LPVOID *))(*(_QWORD *)v235 + 24LL))(
                   v235,
                   &v237);
          if ( v159 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x73B,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v159,
              (int)v193);
          v160 = _o__wcsicmp(v237, *(_QWORD *)(v143 + v142 + 56));
          v147 = 0;
          if ( !v160 )
            break;
          if ( v237 )
          {
            CoTaskMemFree(v237);
            v147 = 0;
            v237 = 0;
          }
          if ( v235 )
          {
            (*(void (__fastcall **)(struct CDeploymentFileRequest *, _QWORD))(*(_QWORD *)v235 + 16LL))(v235, 0);
            v147 = 0;
            v235 = 0;
          }
        }
        v161 = *((_QWORD *)this + 75);
        if ( v161 )
        {
          v193 = *(wchar_t **)(v143 + v142 + 56);
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v161,
            2,
            L"    Found existing RNG file: [%s] with AltSourceHash [%s]",
            *(_QWORD *)(v143 + v142 + 8));
        }
        v147 = (int *)v235;
        v162 = v235;
        v205 = v235;
        if ( v237 )
        {
          CoTaskMemFree(v237);
          v237 = 0;
          v147 = (int *)v235;
        }
        if ( v147 )
        {
          (*(void (__fastcall **)(int *))(*(_QWORD *)v147 + 16LL))(v147);
          v147 = 0;
          v235 = 0;
        }
LABEL_360:
        if ( v238 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v238 + 16LL))(v238);
        if ( v162 )
        {
          v16 = 0;
          goto LABEL_376;
        }
      }
      v163 = *((_QWORD *)this + 75);
      if ( v163 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v163,
          2,
          L"    Adding RNG file: [%s] with AltSourceHash [%s]",
          *(_QWORD *)(v143 + v142 + 8),
          *(_QWORD *)(v143 + v142 + 56));
      v164 = CDeploymentFileRequest::Create(
               Src,
               v152,
               v150,
               *(const wchar_t **)(v143 + v142 + 16),
               L"Express",
               v197,
               &v233);
      ShouldDownloadRangelessFile = v164;
      v16 = 0;
      if ( v164 < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v164,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1872);
        goto LABEL_287;
      }
      v205 = v233;
LABEL_377:
      for ( k = 0; k < *(_DWORD *)(v208 + v142 + 80); ++k )
      {
        v170 = CDeploymentSession::CheckCancelRequested(this, v147);
        ShouldDownloadRangelessFile = v170;
        if ( v170 < 0 )
        {
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)v170,
            L"CDeploymentSession::GenerateExpressDownloadList",
            1901);
          v16 = 0;
          goto LABEL_287;
        }
        v171 = 16LL * k;
        v172 = *(_QWORD *)(v208 + v142 + 72);
        if ( (WCHAR *)((char *)v16 + *(_QWORD *)(v171 + v172 + 8)) < v16 )
        {
          ShouldDownloadRangelessFile = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v16 = (WCHAR *)((char *)v16 + *(_QWORD *)(v171 + v172 + 8));
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
        if ( !v198 )
        {
          if ( v232 )
          {
            (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v232 + 16LL))(v232);
            v232 = 0;
          }
          v173 = CDeploymentFileRange::Create(
                   (unsigned __int64)v206 + *(_QWORD *)(v171 + v172),
                   *(_QWORD *)(v171 + v172 + 8),
                   &v232);
          ShouldDownloadRangelessFile = v173;
          if ( v173 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v173,
              L"CDeploymentSession::GenerateExpressDownloadList",
              1909);
            v16 = 0;
            goto LABEL_287;
          }
          v174 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(&v207, &v232);
          v175 = CDeploymentFileRequest::AppendExpressFileRange(v205, v174);
          if ( v175 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x776,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v175,
              (int)v193);
        }
        v142 = *(_QWORD *)&v222[0];
      }
      v143 = v208;
      v168 = v203;
LABEL_394:
      if ( v198 )
        goto LABEL_419;
      if ( v233 )
      {
        v176 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v212, &v233);
        v177 = CDeploymentDownloadRequest::AppendFileRequest(v210, v176);
        if ( v177 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x77F,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v177,
            (int)v193);
      }
      if ( v168 )
      {
        v178 = *((_QWORD *)this + 75);
        if ( v178 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v178, 2, L"        RNG file size: [%llu]", v16);
        v179 = *((_QWORD *)this + 75);
        if ( v179 )
        {
          v180 = L"TRUE";
          if ( !v197 )
            v180 = L"FALSE";
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v179, 2, L"        Optional: [%s]", v180, v193);
        }
        v181 = *((_QWORD *)this + 75);
        if ( v181 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v181, 2, L"        IsRangeRequestSupported: [%s]", L"TRUE");
        v182 = *((_QWORD *)this + 75);
        if ( v182 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v182,
            2,
            L"        Range count in RNG file: [%lu]",
            *(unsigned int *)(v143 + v142 + 80));
        if ( (unsigned __int64)v16 + v202 < v202 )
        {
          ShouldDownloadRangelessFile = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v202 += (unsigned __int64)v16;
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
        v183 = v196;
        goto LABEL_420;
      }
      if ( v199 )
        goto LABEL_419;
      v183 = v196;
      v184 = 184LL * v196;
      if ( v202 + *(_QWORD *)(v184 + *((_QWORD *)v211 + 14)) < v202 )
      {
        ShouldDownloadRangelessFile = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
      }
      else
      {
        v202 += *(_QWORD *)(v184 + *((_QWORD *)v211 + 14));
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
      if ( (unsigned __int64)v16 + v209 < v209 )
      {
        ShouldDownloadRangelessFile = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        v16 = 0;
      }
      else
      {
        v209 += (unsigned __int64)v16;
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
      v140 = v183 + 1;
      v132 = v217[0];
    }
    v167 = *((_QWORD *)this + 75);
    v16 = 0;
    if ( v167 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v167, 2, L"    RNG File exists: [%s]", *(_QWORD *)(v143 + v142 + 8));
    goto LABEL_376;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7A4,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v189);
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
