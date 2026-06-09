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
  int v33; // ecx
  unsigned int v34; // edx
  __int64 v35; // rax
  __int64 v36; // r15
  int *v37; // rdx
  HANDLE v38; // rax
  int v39; // eax
  DWORD FileAttributesW; // eax
  BOOL v41; // esi
  int FileSize; // eax
  __int64 v43; // rcx
  signed int LastError; // eax
  int v45; // eax
  unsigned int v46; // esi
  const wchar_t **v47; // rbx
  int v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rcx
  int v51; // eax
  struct CDeploymentFileRequest *v52; // rcx
  int v53; // eax
  __int64 v54; // rcx
  __int64 v55; // rcx
  int v56; // eax
  struct CDeploymentFileRequest *v57; // rdx
  struct CDeploymentFileRequest *v58; // rsi
  int v59; // eax
  int OffsetInOuterContainer; // eax
  int v61; // eax
  struct CDeploymentFileRange *v62; // rax
  int appended; // eax
  __int64 v64; // rcx
  int v65; // esi
  struct CDeploymentFileRequest *v66; // rcx
  int v67; // eax
  int v68; // eax
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  const wchar_t *v73; // r9
  int v74; // eax
  __int64 v75; // r14
  char *v76; // rbx
  WCHAR *v77; // rbx
  HANDLE v78; // rax
  int v79; // eax
  DWORD v80; // eax
  BOOL v81; // ebx
  HANDLE v82; // rax
  int v83; // eax
  int v84; // eax
  __int64 v85; // rsi
  char *v86; // r12
  WCHAR *v87; // rbx
  HANDLE v88; // rax
  int v89; // eax
  DWORD v90; // eax
  BOOL v91; // ebx
  int v92; // eax
  unsigned __int64 v93; // r14
  __int64 v94; // rcx
  unsigned int i; // r15d
  __int64 v96; // rbx
  __int64 v97; // rsi
  __int64 v98; // r14
  __int64 v99; // rcx
  _WORD *v100; // rdx
  unsigned __int64 v101; // r8
  __int64 v102; // rax
  int PackageExpanderProgress; // eax
  __int64 v104; // r9
  __int64 v105; // rcx
  __int64 v106; // rdx
  __int64 v107; // rcx
  __int64 v108; // rcx
  const wchar_t *v109; // r9
  __int64 v110; // rcx
  int v111; // esi
  __int64 v112; // rcx
  int v113; // eax
  int *v114; // rdx
  __int64 v115; // rax
  const WCHAR *v116; // rbx
  const WCHAR *v117; // rdx
  unsigned __int64 v118; // r12
  unsigned __int64 v119; // r8
  const WCHAR *v120; // rdx
  unsigned __int64 v121; // r8
  unsigned __int64 v122; // r8
  unsigned __int64 v123; // r8
  int *v124; // rdx
  int v125; // eax
  LPVOID v126; // rdx
  unsigned int v127; // eax
  int v128; // ecx
  __int64 v129; // rdx
  utl::_RefCountBase *v130; // r15
  int v131; // eax
  int *v132; // rdx
  int v133; // eax
  int *v134; // rdx
  __int64 v135; // rcx
  unsigned __int64 v136; // r14
  __int64 v137; // rcx
  unsigned int v138; // r14d
  int v139; // eax
  __int64 v140; // r12
  __int64 v141; // r15
  int v142; // eax
  const WCHAR *v143; // r14
  int v144; // eax
  int *v145; // rdx
  __int64 v146; // rcx
  signed int v147; // eax
  const wchar_t *v148; // r14
  int v149; // eax
  const wchar_t *v150; // r13
  wchar_t *v151; // rbx
  __int64 v152; // rax
  int v153; // eax
  int v154; // eax
  unsigned int j; // ebx
  int v156; // eax
  int v157; // eax
  int v158; // eax
  __int64 v159; // rcx
  struct CDeploymentFileRequest *v160; // rbx
  __int64 v161; // rcx
  int v162; // eax
  __int64 v163; // rcx
  int v164; // eax
  __int64 v165; // rcx
  int v166; // ebx
  unsigned int k; // r15d
  int v168; // eax
  __int64 v169; // r14
  __int64 v170; // r12
  int v171; // eax
  __int64 v172; // rax
  int v173; // eax
  __int64 v174; // rax
  int v175; // eax
  __int64 v176; // rcx
  __int64 v177; // rcx
  const wchar_t *v178; // r9
  __int64 v179; // rcx
  __int64 v180; // rcx
  unsigned int v181; // r14d
  __int64 v182; // rcx
  __int64 v183; // rcx
  unsigned __int64 v184; // rsi
  __int64 v185; // rcx
  unsigned __int64 v186; // r15
  const char *v187; // r9
  __int64 result; // rax
  wchar_t *v189; // [rsp+20h] [rbp-288h]
  int v190; // [rsp+20h] [rbp-288h]
  wchar_t *v191; // [rsp+20h] [rbp-288h]
  unsigned __int64 *v192; // [rsp+28h] [rbp-280h]
  const WCHAR *v193; // [rsp+50h] [rbp-258h] BYREF
  unsigned int v194; // [rsp+58h] [rbp-250h]
  int v195; // [rsp+5Ch] [rbp-24Ch]
  BOOL v196; // [rsp+60h] [rbp-248h] BYREF
  int v197; // [rsp+64h] [rbp-244h]
  wchar_t *Src; // [rsp+68h] [rbp-240h]
  unsigned __int64 v199; // [rsp+70h] [rbp-238h] BYREF
  unsigned __int64 v200; // [rsp+78h] [rbp-230h]
  int v201; // [rsp+80h] [rbp-228h]
  int v202; // [rsp+84h] [rbp-224h]
  struct CDeploymentFileRequest *v203; // [rsp+88h] [rbp-220h] BYREF
  struct IPackageExpanderProgress *v204; // [rsp+90h] [rbp-218h] BYREF
  struct CDeploymentFileRange *v205; // [rsp+98h] [rbp-210h] BYREF
  __int64 v206; // [rsp+A0h] [rbp-208h] BYREF
  unsigned __int64 v207; // [rsp+A8h] [rbp-200h]
  __int64 v208; // [rsp+B0h] [rbp-1F8h]
  struct ActionList::Package *v209; // [rsp+B8h] [rbp-1F0h]
  char v210[8]; // [rsp+C0h] [rbp-1E8h] BYREF
  char *v211; // [rsp+C8h] [rbp-1E0h] BYREF
  unsigned __int64 v212; // [rsp+D0h] [rbp-1D8h]
  __int64 v213; // [rsp+D8h] [rbp-1D0h] BYREF
  __int64 v214; // [rsp+E0h] [rbp-1C8h]
  utl::_RefCountBase *v215[2]; // [rsp+E8h] [rbp-1C0h] BYREF
  __int64 v216; // [rsp+F8h] [rbp-1B0h] BYREF
  __int64 v217; // [rsp+100h] [rbp-1A8h]
  __int128 v218; // [rsp+108h] [rbp-1A0h] BYREF
  __int128 v219; // [rsp+118h] [rbp-190h]
  _OWORD v220[2]; // [rsp+128h] [rbp-180h] BYREF
  unsigned __int64 *v221; // [rsp+148h] [rbp-160h]
  unsigned __int64 *v222; // [rsp+150h] [rbp-158h]
  int *v223; // [rsp+158h] [rbp-150h]
  __int64 v224; // [rsp+160h] [rbp-148h] BYREF
  unsigned __int64 *v225; // [rsp+168h] [rbp-140h]
  _OWORD v226[2]; // [rsp+170h] [rbp-138h] BYREF
  _OWORD v227[2]; // [rsp+190h] [rbp-118h] BYREF
  _OWORD v228[2]; // [rsp+1B0h] [rbp-F8h] BYREF
  __int64 v229; // [rsp+1D0h] [rbp-D8h]
  struct CDeploymentFileRange *v230; // [rsp+1D8h] [rbp-D0h] BYREF
  struct CDeploymentFileRequest *v231; // [rsp+1E0h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+1E8h] [rbp-C0h] BYREF
  struct CDeploymentFileRequest *v233; // [rsp+1F0h] [rbp-B8h] BYREF
  unsigned int v234; // [rsp+1F8h] [rbp-B0h] BYREF
  LPVOID v235; // [rsp+200h] [rbp-A8h] BYREF
  char *v236; // [rsp+208h] [rbp-A0h] BYREF
  int v237; // [rsp+210h] [rbp-98h] BYREF
  LPCWSTR lpFileName; // [rsp+218h] [rbp-90h] BYREF
  LPCWSTR v239; // [rsp+220h] [rbp-88h] BYREF
  __int64 v240; // [rsp+228h] [rbp-80h] BYREF
  LPCWSTR v241; // [rsp+230h] [rbp-78h] BYREF
  wchar_t *v242; // [rsp+238h] [rbp-70h] BYREF
  __int64 v243; // [rsp+240h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+248h] [rbp-60h] BYREF
  _WORD *v245; // [rsp+250h] [rbp-58h] BYREF
  __int64 v246; // [rsp+258h] [rbp-50h] BYREF
  __int64 v247; // [rsp+260h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v229 = -2;
  try
  {
    v201 = a4;
    v195 = a3;
    v11 = (struct ActionList::Package *)a2;
    v209 = (struct ActionList::Package *)a2;
    v13 = (int)a6;
    Src = a6;
    v208 = a7;
    v225 = a8;
    v221 = a9;
    v222 = a10;
    v223 = a11;
    v243 = 0;
    v14 = 0;
    v230 = 0;
    v231 = 0;
    v211 = 0;
    v216 = 0;
    v217 = 0;
    v239 = 0;
    v224 = 0;
    *(_OWORD *)v215 = 0;
    v213 = 0;
    v214 = 0;
    v15 = 0;
    v240 = 0;
    v204 = 0;
    bstrString = 0;
    v247 = 0;
    v246 = 0;
    v206 = 0;
    v199 = 0;
    v245 = 0;
    v16 = 0;
    lpFileName = 0;
    v241 = 0;
    v242 = 0;
    v196 = 0;
    LODWORD(v203) = 0;
    v237 = 0;
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
      v190 = 1459;
      goto LABEL_12;
    }
    if ( !a8 )
    {
      v20 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      v190 = 1460;
      goto LABEL_12;
    }
    if ( !a9 )
    {
      v20 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      v190 = 1461;
      goto LABEL_12;
    }
    if ( !a10 )
    {
      v20 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      v190 = 1462;
      goto LABEL_12;
    }
    if ( !a11 )
    {
      v20 = *((_QWORD *)this + 75);
      v16 = 0;
      ShouldDownloadRangelessFile = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      v190 = 1463;
LABEL_12:
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v20,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GenerateExpressDownloadList",
                                v190,
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
        v11 = v209;
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
    v236 = v27;
    v28 = 0;
    if ( !v27 )
    {
      v16 = 0;
      v211 = 0;
      v29 = *((_QWORD *)this + 75);
      ShouldDownloadRangelessFile = -2147024882;
      if ( v29 )
      {
        LODWORD(v192) = -2147024882;
        LODWORD(v189) = 1472;
        goto LABEL_40;
      }
      goto LABEL_32;
    }
    v211 = v27;
    memset_0(v27, 0, v25);
    if ( !a5 )
    {
      PackageFileListPath = CDeploymentSession::GetPackageFileListPath(this, v11, &v242);
      ShouldDownloadRangelessFile = PackageFileListPath;
      if ( PackageFileListPath < 0 )
      {
        v29 = *((_QWORD *)this + 75);
        v16 = 0;
        if ( v29 )
        {
          LODWORD(v192) = PackageFileListPath;
          LODWORD(v189) = 1480;
          goto LABEL_40;
        }
        goto LABEL_32;
      }
    }
    v31 = *((_QWORD *)this + 75);
    if ( v31 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v31, 2, L"Package: [%s]", *((_QWORD *)v11 + 7));
    v32 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v208 + 40LL))(v208, &v243);
    ShouldDownloadRangelessFile = v32;
    if ( v32 < 0 )
    {
      v29 = *((_QWORD *)this + 75);
      v16 = 0;
      if ( v29 )
      {
        LODWORD(v192) = v32;
        LODWORD(v189) = 1490;
        goto LABEL_40;
      }
      goto LABEL_32;
    }
    v202 = 0;
    v212 = 0;
    v33 = 0;
    v197 = 0;
    v234 = 0;
    v200 = 0;
    v207 = 0;
    v34 = 0;
    v194 = 0;
    v35 = 0;
    while ( 1 )
    {
      LODWORD(v193) = v35;
      if ( (unsigned int)v35 >= *((_DWORD *)v11 + 30) )
        break;
      v36 = *((_QWORD *)v209 + 14) + 184 * v35;
      if ( *(_BYTE *)(v36 + 153) )
      {
        if ( !a5 )
        {
          ShouldDownloadRangelessFile = CDeploymentSession::ShouldDownloadRangelessFile(
                                          (_DWORD)this,
                                          (_DWORD)v242,
                                          v36,
                                          v13,
                                          (__int64)&v203,
                                          (__int64)&v206);
          if ( ShouldDownloadRangelessFile < 0 )
          {
            v29 = *((_QWORD *)this + 75);
            v16 = 0;
            if ( v29 )
            {
              LODWORD(v192) = ShouldDownloadRangelessFile;
              LODWORD(v189) = 1505;
              goto LABEL_40;
            }
            goto LABEL_32;
          }
          if ( (_DWORD)v203 )
          {
            if ( v16 )
            {
              v38 = GetProcessHeap();
              HeapFree(v38, 0, v16 - 2);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              v16 = 0;
              lpFileName = 0;
            }
            v39 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)(v36 + 80), 0);
            ShouldDownloadRangelessFile = v39;
            if ( v39 < 0 )
            {
              v29 = *((_QWORD *)this + 75);
              if ( v29 )
              {
                LODWORD(v192) = v39;
                LODWORD(v189) = 1512;
                goto LABEL_40;
              }
              goto LABEL_32;
            }
            v16 = (WCHAR *)lpFileName;
            FileAttributesW = GetFileAttributesW(lpFileName);
            v41 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
            v196 = v41;
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            if ( !v41 )
              goto LABEL_83;
            FileSize = CMoUpdateHelpersT<CEmptyType>::GetFileSize(v16, &v246);
            ShouldDownloadRangelessFile = FileSize;
            if ( FileSize < 0 )
            {
              v29 = *((_QWORD *)this + 75);
              v16 = 0;
              if ( v29 )
              {
                LODWORD(v192) = FileSize;
                LODWORD(v189) = 1517;
                goto LABEL_40;
              }
              goto LABEL_32;
            }
            ShouldDownloadRangelessFile = 0;
            if ( !v246 )
            {
              v43 = *((_QWORD *)this + 75);
              if ( v43 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v43,
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
                  LODWORD(v192) = ShouldDownloadRangelessFile;
                  LODWORD(v189) = 1521;
                  v29 = *((_QWORD *)this + 75);
                  goto LABEL_40;
                }
                goto LABEL_36;
              }
              v202 = 1;
              v41 = 0;
              v196 = 0;
            }
            if ( !v41 )
            {
LABEL_83:
              LODWORD(v235) = 0;
              if ( v231 )
              {
                (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v231 + 16LL))(v231);
                v231 = 0;
              }
              if ( *(_QWORD *)(v36 + 48) )
              {
                v45 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v243 + 24LL))(v243, &v235);
                ShouldDownloadRangelessFile = v45;
                if ( v45 < 0 )
                {
                  v29 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( v29 )
                  {
                    LODWORD(v192) = v45;
                    LODWORD(v189) = 1538;
                    goto LABEL_40;
                  }
                  goto LABEL_32;
                }
                v46 = 0;
                v47 = (const wchar_t **)(v36 + 64);
                while ( 1 )
                {
                  if ( v46 >= (unsigned int)v235 )
                    goto LABEL_115;
                  v233 = 0;
                  pv = 0;
                  v48 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct CDeploymentFileRequest **))(*(_QWORD *)v243 + 32LL))(
                          v243,
                          v46,
                          &v233);
                  ShouldDownloadRangelessFile = v48;
                  if ( v48 < 0 )
                  {
                    v49 = *((_QWORD *)this + 75);
                    v16 = 0;
                    if ( v49 )
                    {
                      LODWORD(v192) = v48;
                      LODWORD(v189) = 1545;
                      v51 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v49,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::GenerateExpressDownloadList",
                              v189,
                              v192);
                      v50 = (unsigned int)v51;
                      if ( v51 < 0 )
                        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v51);
                    }
                    else
                    {
                      v50 = 0;
                    }
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v50);
                    if ( pv )
                    {
                      CoTaskMemFree(pv);
                      pv = 0;
                    }
                    v52 = v233;
                    if ( !v233 )
                      goto LABEL_438;
                    goto LABEL_99;
                  }
                  v53 = (*(__int64 (__fastcall **)(struct CDeploymentFileRequest *, LPVOID *))(*(_QWORD *)v233 + 24LL))(
                          v233,
                          &pv);
                  ShouldDownloadRangelessFile = v53;
                  if ( v53 < 0 )
                  {
                    v54 = *((_QWORD *)this + 75);
                    v16 = 0;
                    if ( v54 )
                    {
                      LODWORD(v192) = v53;
                      LODWORD(v189) = 1546;
                      v56 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v54,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::GenerateExpressDownloadList",
                              v189,
                              v192);
                      v55 = (unsigned int)v56;
                      if ( v56 < 0 )
                        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v56);
                    }
                    else
                    {
                      v55 = 0;
                    }
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v55);
                    if ( pv )
                    {
                      CoTaskMemFree(pv);
                      pv = 0;
                    }
                    v52 = v233;
                    if ( !v233 )
                      goto LABEL_438;
LABEL_99:
                    (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v233 + 16LL))(v52);
                    goto LABEL_438;
                  }
                  v47 = (const wchar_t **)(v36 + 64);
                  if ( !(unsigned int)_o__wcsicmp(pv, *(_QWORD *)(v36 + 64)) )
                    break;
                  if ( pv )
                  {
                    CoTaskMemFree(pv);
                    pv = 0;
                  }
                  if ( v233 )
                  {
                    (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v233 + 16LL))(v233);
                    v233 = 0;
                  }
                  ++v46;
                }
                v57 = v233;
                v58 = v233;
                if ( pv )
                {
                  CoTaskMemFree(pv);
                  pv = 0;
                  v57 = v233;
                }
                if ( v57 )
                {
                  (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v57 + 16LL))(v57);
                  v233 = 0;
                }
                if ( !v58 )
                {
LABEL_115:
                  v59 = CDeploymentFileRequest::Create(
                          *v47,
                          *(const wchar_t **)(v36 + 48),
                          *(const wchar_t **)(v36 + 48),
                          *(const wchar_t **)(v36 + 88),
                          L"Canonical",
                          v195,
                          &v231);
                  ShouldDownloadRangelessFile = v59;
                  if ( v59 < 0 )
                  {
                    v29 = *((_QWORD *)this + 75);
                    v16 = 0;
                    if ( v29 )
                    {
                      LODWORD(v192) = v59;
                      LODWORD(v189) = 1563;
                      goto LABEL_40;
                    }
LABEL_32:
                    v24 = (unsigned int)v16;
LABEL_36:
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v24);
LABEL_438:
                    v14 = v230;
LABEL_439:
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v242);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v241);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v245);
                    if ( bstrString )
                    {
                      SysFreeString(bstrString);
                      bstrString = v16;
                    }
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v240);
                    CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::~CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>(&v213);
                    if ( v215[1] )
                      utl::_RefCountBase::_DecStrong(v215[1]);
                    SP_ARBITER<SessionData>::~SP_ARBITER<SessionData>(&v224);
                    DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v239);
                    CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::~CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>(&v216);
                    SP_MEM<wchar_t>::~SP_MEM<wchar_t>(&v211);
                    if ( v231 )
                      (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v231 + 16LL))(v231);
                    if ( v14 )
                      (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v14 + 16LL))(v14);
                    SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v243);
                    return (unsigned int)ShouldDownloadRangelessFile;
                  }
                  v58 = v231;
                }
                if ( v230 )
                {
                  (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v230 + 16LL))(v230);
                  v230 = 0;
                }
                OffsetInOuterContainer = CDeploymentSession::GetOffsetInOuterContainer(
                                           this,
                                           *(const wchar_t **)(v36 + 48),
                                           *(const wchar_t **)(v36 + 56),
                                           *(const wchar_t **)(v36 + 72),
                                           *(const wchar_t **)(v36 + 112),
                                           &v199,
                                           0);
                ShouldDownloadRangelessFile = OffsetInOuterContainer;
                if ( OffsetInOuterContainer < 0 )
                {
                  v29 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( !v29 )
                    goto LABEL_32;
                  LODWORD(v192) = OffsetInOuterContainer;
                  LODWORD(v189) = 1572;
                  goto LABEL_40;
                }
                v61 = CDeploymentFileRange::Create(v199, *(_QWORD *)(v36 + 160), &v230);
                ShouldDownloadRangelessFile = v61;
                if ( v61 < 0 )
                {
                  v29 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( !v29 )
                    goto LABEL_32;
                  LODWORD(v192) = v61;
                  LODWORD(v189) = 1573;
                  goto LABEL_40;
                }
                v62 = v230;
                v230 = 0;
                v205 = v62;
                appended = CDeploymentFileRequest::AppendFileRange(v58, &v205);
                ShouldDownloadRangelessFile = appended;
                v29 = *((_QWORD *)this + 75);
                if ( appended < 0 )
                {
                  v16 = 0;
                  if ( !v29 )
                    goto LABEL_32;
                  LODWORD(v192) = appended;
                  LODWORD(v189) = 1574;
                  goto LABEL_40;
                }
                if ( v29 )
                  CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v29,
                    2,
                    L"        Rangeless file container: [%ws]",
                    *(_QWORD *)(v36 + 48));
                v64 = *((_QWORD *)this + 75);
                if ( v64 )
                  CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v64,
                    2,
                    L"        Rangeless file container offset: [%llu]",
                    v199);
                v65 = v195;
                v13 = (int)Src;
              }
              else
              {
                v65 = v195;
                v68 = CDeploymentFileRequest::Create(
                        *(const wchar_t **)(v36 + 112),
                        *(const wchar_t **)(v36 + 80),
                        *(const wchar_t **)(v36 + 72),
                        *(const wchar_t **)(v36 + 88),
                        L"Canonical",
                        v195,
                        &v231);
                ShouldDownloadRangelessFile = v68;
                if ( v68 < 0 )
                {
                  v29 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( !v29 )
                    goto LABEL_32;
                  LODWORD(v192) = v68;
                  LODWORD(v189) = 1587;
                  goto LABEL_40;
                }
              }
              v66 = v231;
              if ( v231 )
              {
                v231 = 0;
                v205 = v66;
                v67 = CDeploymentDownloadRequest::AppendFileRequest(v208, &v205);
                ShouldDownloadRangelessFile = v67;
                if ( v67 < 0 )
                {
                  v29 = *((_QWORD *)this + 75);
                  v16 = 0;
                  if ( !v29 )
                    goto LABEL_32;
                  LODWORD(v192) = v67;
                  LODWORD(v189) = 1592;
                  goto LABEL_40;
                }
              }
              v69 = *((_QWORD *)this + 75);
              if ( v69 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v69, 2, L"        Rangeless file name: [%s]", v16);
              v70 = *((_QWORD *)this + 75);
              if ( v70 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v70,
                  2,
                  L"        Rangeless file size: [%llu]",
                  *(_QWORD *)(v36 + 160));
              v71 = *((_QWORD *)this + 75);
              if ( v71 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v71, 2, L"        Extraction file size: [%lu]", v206);
              v72 = *((_QWORD *)this + 75);
              if ( v72 )
              {
                v73 = L"TRUE";
                if ( !v65 )
                  v73 = L"FALSE";
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v72, 2, L"        Optional: [%s]", v73);
              }
              if ( v200 + *(_QWORD *)(v36 + 160) < v200 )
              {
                ShouldDownloadRangelessFile = -2147024362;
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
              }
              else
              {
                v200 += *(_QWORD *)(v36 + 160);
                ShouldDownloadRangelessFile = 0;
              }
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
              if ( ShouldDownloadRangelessFile < 0 )
              {
                v29 = *((_QWORD *)this + 75);
                v16 = 0;
                if ( !v29 )
                  goto LABEL_32;
                LODWORD(v192) = ShouldDownloadRangelessFile;
                LODWORD(v189) = 1599;
                goto LABEL_40;
              }
              ShouldDownloadRangelessFile = 0;
            }
            if ( v207 + *(_QWORD *)(v36 + 160) < v207 )
            {
              ShouldDownloadRangelessFile = -2147024362;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            }
            else
            {
              v207 += *(_QWORD *)(v36 + 160);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
            if ( ShouldDownloadRangelessFile < 0 )
            {
              v29 = *((_QWORD *)this + 75);
              v16 = 0;
              if ( !v29 )
                goto LABEL_32;
              LODWORD(v192) = ShouldDownloadRangelessFile;
              LODWORD(v189) = 1602;
              goto LABEL_40;
            }
            if ( v212 + v206 < v212 )
            {
              ShouldDownloadRangelessFile = -2147024362;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            }
            else
            {
              v212 += v206;
              ShouldDownloadRangelessFile = 0;
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
            if ( ShouldDownloadRangelessFile < 0 )
            {
              v29 = *((_QWORD *)this + 75);
              v16 = 0;
              if ( !v29 )
                goto LABEL_32;
              LODWORD(v192) = ShouldDownloadRangelessFile;
              LODWORD(v189) = 1603;
              goto LABEL_40;
            }
          }
          v74 = CDeploymentSession::CheckCancelRequested(this, v37);
          ShouldDownloadRangelessFile = v74;
          if ( v74 < 0 )
          {
            v29 = *((_QWORD *)this + 75);
            v16 = 0;
            if ( !v29 )
              goto LABEL_32;
            LODWORD(v192) = v74;
            LODWORD(v189) = 1606;
            goto LABEL_40;
          }
          v34 = v194;
          v33 = v197;
        }
      }
      else
      {
        v75 = 88LL * v34;
        v76 = v236;
        *(_QWORD *)&v236[v75] = *(_QWORD *)(v36 + 72);
        *(_QWORD *)&v76[v75 + 8] = *(_QWORD *)(v36 + 80);
        *(_QWORD *)&v76[v75 + 16] = *(_QWORD *)(v36 + 88);
        *(_QWORD *)&v76[v75 + 24] = *(_QWORD *)(v36 + 112);
        *(_QWORD *)&v76[v75 + 48] = *(_QWORD *)(v36 + 48);
        *(_QWORD *)&v76[v75 + 56] = *(_QWORD *)(v36 + 64);
        if ( v241 )
        {
          v77 = (WCHAR *)(v241 - 2);
          v78 = GetProcessHeap();
          HeapFree(v78, 0, v77);
          v76 = v236;
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v241 = 0;
        }
        v79 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)&v76[v75 + 8], 0);
        ShouldDownloadRangelessFile = v79;
        if ( v79 < 0 )
        {
          v29 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( !v29 )
            goto LABEL_32;
          LODWORD(v192) = v79;
          LODWORD(v189) = 1620;
          goto LABEL_40;
        }
        v80 = GetFileAttributesW(v241);
        v81 = v80 != -1 && (v80 & 0x10) == 0;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( v81 )
          v28 = 1;
        v234 = v28;
        if ( v15 )
        {
          v82 = GetProcessHeap();
          HeapFree(v82, 0, (LPVOID)(v15 - 4));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v240 = 0;
        }
        v83 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 62), *(_QWORD *)(v36 + 120), 0);
        ShouldDownloadRangelessFile = v83;
        if ( v83 < 0 )
        {
          v29 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( !v29 )
            goto LABEL_32;
          LODWORD(v192) = v83;
          LODWORD(v189) = 1628;
          goto LABEL_40;
        }
        v84 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(&v213, &v240);
        ShouldDownloadRangelessFile = v84;
        if ( v84 < 0 )
        {
          v29 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( !v29 )
            goto LABEL_32;
          LODWORD(v192) = v84;
          LODWORD(v189) = 1629;
          goto LABEL_40;
        }
        v85 = (int)v194;
        v86 = v236;
        *(_QWORD *)&v236[v75 + 32] = *(_QWORD *)(v214 + 8LL * (int)v194);
        if ( v239 )
        {
          v87 = (WCHAR *)(v239 - 2);
          v88 = GetProcessHeap();
          HeapFree(v88, 0, v87);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v239 = 0;
        }
        v89 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)(v36 + 72), 0);
        ShouldDownloadRangelessFile = v89;
        if ( v89 < 0 )
        {
          v29 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( !v29 )
            goto LABEL_32;
          LODWORD(v192) = v89;
          LODWORD(v189) = 1635;
          goto LABEL_40;
        }
        v90 = GetFileAttributesW(v239);
        v91 = v90 != -1 && (v90 & 0x10) == 0;
        v196 = v91;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( v91 )
        {
          v92 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(&v216, &v239);
          ShouldDownloadRangelessFile = v92;
          if ( v92 < 0 )
          {
            v29 = *((_QWORD *)this + 75);
            v16 = 0;
            if ( !v29 )
              goto LABEL_32;
            LODWORD(v192) = v92;
            LODWORD(v189) = 1639;
            goto LABEL_40;
          }
          *(_QWORD *)&v86[v75 + 40] = *(_QWORD *)(v217 + 8 * v85);
          v33 = 1;
          v197 = 1;
        }
        else
        {
          v33 = v197;
        }
        v34 = ++v194;
        v15 = v240;
        v13 = (int)Src;
      }
      v35 = (unsigned int)((_DWORD)v193 + 1);
      v28 = v234;
      v11 = v209;
    }
    v16 = 0;
    v93 = 0;
    v199 = 0;
    if ( !v34 )
    {
      v94 = *((_QWORD *)this + 75);
      if ( v94 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v94, 2, L"    All Express content is rangeless.", 1);
      goto LABEL_428;
    }
    if ( a5 )
    {
      if ( !v33 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= *((_DWORD *)v209 + 30) )
            goto LABEL_427;
          v96 = 184LL * i;
          v97 = *((_QWORD *)v209 + 14);
          if ( *(_QWORD *)(v96 + v97 + 64) && (v98 = v96 + v97, *(_QWORD *)(v96 + v97 + 48)) )
          {
            if ( !std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::contains<wchar_t *>(
                    (__int64)this + 768,
                    (__int64 *)(v98 + 48)) )
            {
              v99 = *((_QWORD *)this + 75);
              if ( v99 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v99,
                  2,
                  L"    Adding container file: [%s]",
                  *(_QWORD *)(v98 + 48));
              ShouldDownloadRangelessFile = CDeploymentFileRequest::Create(
                                              *(const wchar_t **)(v96 + v97 + 64),
                                              *(const wchar_t **)(v98 + 48),
                                              *(const wchar_t **)(v98 + 48),
                                              0,
                                              L"Canonical",
                                              v195,
                                              &v231);
              if ( ShouldDownloadRangelessFile < 0 )
              {
                v29 = *((_QWORD *)this + 75);
                v16 = 0;
                if ( !v29 )
                  goto LABEL_32;
                LODWORD(v192) = ShouldDownloadRangelessFile;
                LODWORD(v189) = 1676;
LABEL_40:
                v24 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                      v29,
                                      4,
                                      L"%s(%d): Result = 0x%X",
                                      L"CDeploymentSession::GenerateExpressDownloadList",
                                      v189,
                                      v192);
LABEL_34:
                if ( (int)v24 < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v24);
                goto LABEL_36;
              }
              v100 = *(_WORD **)(v98 + 48);
              v218 = 0;
              v219 = 0;
              v101 = -1;
              do
                ++v101;
              while ( v100[v101] );
              std::wstring::_Construct<1,wchar_t const *>((__int64)&v218, v100, v101);
              std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
                (__int64 *)this + 96,
                (__int64)v220,
                (__int64)&v218);
              std::wstring::~wstring(&v218);
            }
            v16 = 0;
          }
          else
          {
            v105 = *((_QWORD *)this + 75);
            if ( v105 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v105,
                2,
                L"    Adding PSF file: [%s]",
                *(_QWORD *)(v96 + v97 + 72));
            PackageExpanderProgress = CDeploymentFileRequest::Create(
                                        *(const wchar_t **)(v96 + v97 + 112),
                                        *(const wchar_t **)(v96 + v97 + 72),
                                        *(const wchar_t **)(v96 + v97 + 72),
                                        *(const wchar_t **)(v96 + v97 + 88),
                                        L"Canonical",
                                        v195,
                                        &v231);
            ShouldDownloadRangelessFile = PackageExpanderProgress;
            if ( PackageExpanderProgress < 0 )
            {
              v104 = 1693;
              goto LABEL_239;
            }
          }
          v102 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(&v204, &v231);
          PackageExpanderProgress = CDeploymentDownloadRequest::AppendFileRequest(v208, v102);
          ShouldDownloadRangelessFile = PackageExpanderProgress;
          if ( PackageExpanderProgress < 0 )
          {
            v104 = 1696;
            goto LABEL_239;
          }
        }
      }
LABEL_428:
      v183 = *((_QWORD *)this + 75);
      v184 = v200;
      if ( v183 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v183, 2, L"    Required Download size : [%llu]", v200);
      v185 = *((_QWORD *)this + 75);
      v186 = v207;
      if ( v185 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v185, 2, L"    Total Download size : [%llu]", v207);
      if ( v93 + v212 < v93 )
      {
        ShouldDownloadRangelessFile = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
      }
      else
      {
        v93 += v212;
        ShouldDownloadRangelessFile = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)ShouldDownloadRangelessFile);
      if ( ShouldDownloadRangelessFile >= 0 )
      {
        *v225 = v184;
        *v221 = v186;
        *v222 = v93;
        *v223 = v202;
        goto LABEL_438;
      }
      v104 = 1945;
      v106 = (unsigned int)ShouldDownloadRangelessFile;
      goto LABEL_240;
    }
    v108 = *((_QWORD *)this + 75);
    if ( v108 )
    {
      v109 = L"TRUE";
      if ( !v28 )
        v109 = L"FALSE";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v108, 2, L"Range file Exists: [%s]", v109);
    }
    if ( !*((_DWORD *)this + 66) || v28 )
    {
      v111 = 1;
      v112 = *((_QWORD *)this + 75);
      if ( v112 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v112, 2, L"    Calculating ranges", 1);
    }
    else
    {
      v110 = *((_QWORD *)this + 75);
      if ( v110 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v110, 2, L"    Calculating ranges (new job)", 1);
      v111 = 5;
    }
    PackageExpanderProgress = CProgressHandler::GetPackageExpanderProgress(
                                *((CProgressHandler **)this + 60),
                                *((const wchar_t **)v11 + 7),
                                &v204);
    ShouldDownloadRangelessFile = PackageExpanderProgress;
    if ( PackageExpanderProgress < 0 )
    {
      v104 = 1721;
LABEL_239:
      v106 = (unsigned int)PackageExpanderProgress;
LABEL_240:
      v107 = *((_QWORD *)this + 75);
LABEL_241:
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(v107, v106, L"CDeploymentSession::GenerateExpressDownloadList", v104);
      goto LABEL_438;
    }
    v113 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *((_QWORD *)v11 + 7), 0);
    ShouldDownloadRangelessFile = v113;
    v107 = *((_QWORD *)this + 75);
    if ( v113 < 0 )
    {
      v104 = 1722;
      v106 = (unsigned int)v113;
      goto LABEL_241;
    }
    PackageExpanderProgress = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v107 + 88LL))(v107, &bstrString);
    ShouldDownloadRangelessFile = PackageExpanderProgress;
    if ( PackageExpanderProgress < 0 )
    {
      v104 = 1723;
      goto LABEL_239;
    }
    PackageExpanderProgress = CDeploymentSession::CheckCancelRequested(this, v114);
    ShouldDownloadRangelessFile = PackageExpanderProgress;
    if ( PackageExpanderProgress < 0 )
    {
      v104 = 1725;
      goto LABEL_239;
    }
    v115 = *((_QWORD *)this + 80);
    if ( v115 && *(_DWORD *)(v115 + 8) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    UpdateAgentMisc::ConvertWinDirToDefaultBootDir(&v193, *((_QWORD *)this + 70));
    pv = 0;
    v116 = &String2;
    v117 = &String2;
    if ( *((_QWORD *)this + 70) )
      v117 = (const WCHAR *)*((_QWORD *)this + 70);
    memset(v228, 0, sizeof(v228));
    v118 = -1;
    v119 = -1;
    do
      ++v119;
    while ( v117[v119] );
    std::wstring::_Construct<1,wchar_t const *>((__int64)v228, v117, v119);
    v120 = &String2;
    if ( v193 )
      v120 = v193;
    memset(v227, 0, sizeof(v227));
    v121 = -1;
    do
      ++v121;
    while ( v120[v121] );
    std::wstring::_Construct<1,wchar_t const *>((__int64)v227, v120, v121);
    if ( *((_QWORD *)this + 67) )
    {
      v116 = (const WCHAR *)*((_QWORD *)this + 67);
    }
    else if ( *((_QWORD *)this + 62) )
    {
      v116 = (const WCHAR *)*((_QWORD *)this + 62);
    }
    memset(v226, 0, sizeof(v226));
    v122 = -1;
    do
      ++v122;
    while ( v116[v122] );
    std::wstring::_Construct<1,wchar_t const *>((__int64)v226, v116, v122);
    memset(v220, 0, sizeof(v220));
    v123 = -1;
    do
      ++v123;
    while ( bstrString[v123] );
    std::wstring::_Construct<1,wchar_t const *>((__int64)v220, bstrString, v123);
    v218 = 0;
    v219 = 0;
    do
      ++v118;
    while ( v245[v118] );
    std::wstring::_Construct<1,wchar_t const *>((__int64)&v218, v245, v118);
    ShouldDownloadRangelessFile = GetPackageExpanderEx(
                                    v111,
                                    (*((_DWORD *)this + 150) + 24) & (unsigned int)-(*((_QWORD *)this + 75) != 0),
                                    (_DWORD)v204,
                                    (unsigned int)&v218,
                                    (__int64)v220,
                                    (__int64)v226,
                                    (__int64)v227,
                                    (__int64)v228,
                                    (__int64)&pv,
                                    (__int64)&v237);
    std::wstring::~wstring(&v218);
    std::wstring::~wstring(v220);
    std::wstring::~wstring(v226);
    std::wstring::~wstring(v227);
    std::wstring::~wstring(v228);
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
    v125 = CDeploymentSession::CheckCancelRequested(this, v124);
    ShouldDownloadRangelessFile = v125;
    if ( v125 < 0 )
    {
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        *((_QWORD *)this + 75),
        (unsigned int)v125,
        L"CDeploymentSession::GenerateExpressDownloadList",
        1741);
      if ( pv )
        (**(void (__fastcall ***)(LPVOID))pv)(pv);
      goto LABEL_287;
    }
    v126 = pv;
    pv = 0;
    if ( !(unsigned __int8)___reset_VIPackageExpander__V_lambda_1___0__GenerateExpressDownloadList_CDeploymentSession__QEAAJQEBUPackage_ActionList__HHHPEAV__set_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UWstringCaseInsensitiveCompare__V__allocator_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__std__PEAVCDeploymentDownloadRequest__PEA_K33PEAH_Z__0A____shared_ptr_VIPackageExpander___utl__QEAA_NPEAVIPackageExpander__V_lambda_1___0__GenerateExpressDownloadList_CDeploymentSession__QEAAJQEBUPackage_ActionList__HHHPEAV__set_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UWstringCaseInsensitiveCompare__V__allocator_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__std__PEAVCDeploymentDownloadRequest__PEA_K44PEAH_Z__Z(
                             v215,
                             v126) )
    {
      ShouldDownloadRangelessFile = -2147467261;
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        *((_QWORD *)this + 75),
        2147500035LL,
        L"CDeploymentSession::GenerateExpressDownloadList",
        1743);
LABEL_287:
      __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v193);
      goto LABEL_438;
    }
    utl::weak_ptr<IPackageExpander>::operator=<IPackageExpander,0>((char *)this + 632, v215);
    v127 = *((_DWORD *)this + 114);
    if ( v127 <= 0x16 && (v128 = 4195888, _bittest(&v128, v127)) || (v129 = 0, v127 == 6) )
    {
      v129 = 1;
      if ( v127 == 9 )
        v129 = 3;
    }
    v130 = v215[0];
    v191 = v242;
    v131 = (*(__int64 (__fastcall **)(utl::_RefCountBase *, __int64, char *, _QWORD))(*(_QWORD *)v215[0] + 8LL))(
             v215[0],
             v129,
             v236,
             v194);
    ShouldDownloadRangelessFile = v131;
    if ( v131 < 0 )
    {
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        *((_QWORD *)this + 75),
        (unsigned int)v131,
        L"CDeploymentSession::GenerateExpressDownloadList",
        1764);
      goto LABEL_287;
    }
    v133 = CDeploymentSession::CheckCancelRequested(this, v132);
    ShouldDownloadRangelessFile = v133;
    v135 = *((_QWORD *)this + 75);
    if ( v133 < 0 )
    {
      CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
        v135,
        (unsigned int)v133,
        L"CDeploymentSession::GenerateExpressDownloadList",
        1766);
      goto LABEL_287;
    }
    if ( *((_DWORD *)v130 + 4) )
    {
      v136 = *((_QWORD *)v130 + 3);
      v199 = v136;
      if ( v135 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v135, 2, L"    Expand size: [%llu]", v136, v191);
      v137 = *((_QWORD *)this + 75);
      if ( v137 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v137,
          2,
          L"    Required RNG files count:[%lu]",
          *((unsigned int *)v130 + 4));
    }
    else
    {
      v199 = 0;
      if ( v135 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v135, 2, L"    Already expanded");
    }
    v138 = 0;
    while ( 1 )
    {
      v194 = v138;
      if ( v138 >= *((_DWORD *)v130 + 4) )
      {
        Windows::AutoReleasePtr<IPackageExpander>::~AutoReleasePtr<IPackageExpander>(&pv);
        __1__unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAA_XZ(&v193);
LABEL_427:
        v93 = v199;
        goto LABEL_428;
      }
      v139 = CDeploymentSession::CheckCancelRequested(this, v134);
      ShouldDownloadRangelessFile = v139;
      if ( v139 < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v139,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1786);
        goto LABEL_287;
      }
      v140 = 88LL * v138;
      *(_QWORD *)&v220[0] = v140;
      v141 = *((_QWORD *)v130 + 1);
      v206 = v141;
      v204 = 0;
      SH_SSTRING::operator=(&lpFileName);
      v142 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)(v141 + v140 + 8), 0);
      ShouldDownloadRangelessFile = v142;
      if ( v142 < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v142,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1795);
        goto LABEL_287;
      }
      v143 = lpFileName;
      v144 = CMiscHelpersT<CEmptyType>::FileExists(lpFileName, &v196);
      ShouldDownloadRangelessFile = v144;
      if ( v144 < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v144,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1796);
        goto LABEL_287;
      }
      LODWORD(v16) = v196;
      if ( v196 )
      {
        ShouldDownloadRangelessFile = CMoUpdateHelpersT<CEmptyType>::GetFileSize(v143, &v247);
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
        if ( !v247 )
        {
          v146 = *((_QWORD *)this + 75);
          v16 = 0;
          if ( v146 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v146, 2, L"    Deleting zero byte RNG file: [%s]", v143);
          if ( !DeleteFileW(v143) )
          {
            v147 = GetLastError();
            ShouldDownloadRangelessFile = v147;
            if ( v147 )
            {
              if ( v147 > 0 )
                ShouldDownloadRangelessFile = (unsigned __int16)v147 | 0x80070000;
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
          v202 = 1;
          v196 = 0;
        }
      }
      v203 = 0;
      if ( (_DWORD)v16 )
        break;
      v148 = *(const wchar_t **)(v141 + v140 + 48);
      v16 = 0;
      if ( v148 )
      {
        Src = *(wchar_t **)(v141 + v140 + 56);
        v149 = CDeploymentSession::GetOffsetInOuterContainer(
                 this,
                 v148,
                 0,
                 *(const wchar_t **)(v141 + v140),
                 *(const wchar_t **)(v141 + v140 + 24),
                 (unsigned __int64 *)&v204,
                 0);
        ShouldDownloadRangelessFile = v149;
        if ( v149 < 0 )
        {
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)v149,
            L"CDeploymentSession::GenerateExpressDownloadList",
            1821);
          goto LABEL_287;
        }
        v150 = v148;
        v151 = Src;
      }
      else
      {
        v151 = *(wchar_t **)(v141 + v140 + 24);
        Src = v151;
        v148 = *(const wchar_t **)(v141 + v140);
        v150 = *(const wchar_t **)(v141 + v140 + 8);
      }
      v145 = 0;
      if ( v231 )
      {
        (*(void (__fastcall **)(struct CDeploymentFileRequest *, _QWORD))(*(_QWORD *)v231 + 16LL))(v231, 0);
        v145 = 0;
        v231 = 0;
      }
      if ( !v201 )
      {
        v16 = 0;
        if ( !v197 )
        {
          v163 = *((_QWORD *)this + 75);
          if ( v163 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v163, 2, L"    Adding PSF file: [%s]", v148);
          v164 = CDeploymentFileRequest::Create(
                   v151,
                   v148,
                   v148,
                   *(const wchar_t **)(v141 + v140 + 16),
                   L"Canonical",
                   v195,
                   &v231);
          ShouldDownloadRangelessFile = v164;
          if ( v164 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v164,
              L"CDeploymentSession::GenerateExpressDownloadList",
              1888);
            goto LABEL_287;
          }
        }
LABEL_376:
        v166 = v201;
        if ( !v201 )
          goto LABEL_394;
        goto LABEL_377;
      }
      if ( *(_QWORD *)(v141 + v140 + 56) )
      {
        v234 = 0;
        v152 = *(_QWORD *)v208;
        v236 = 0;
        v153 = (*(__int64 (__fastcall **)(__int64, char **))(v152 + 40))(v208, &v236);
        if ( v153 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x732,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v153,
            (int)v191);
        v154 = (*(__int64 (__fastcall **)(char *, unsigned int *))(*(_QWORD *)v236 + 24LL))(v236, &v234);
        v145 = 0;
        if ( v154 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x733,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v154,
            (int)v191);
        for ( j = 0; ; ++j )
        {
          if ( j >= v234 )
          {
            v160 = v203;
            goto LABEL_360;
          }
          v233 = 0;
          v235 = 0;
          v156 = (*(__int64 (__fastcall **)(char *, _QWORD, struct CDeploymentFileRequest **))(*(_QWORD *)v236 + 32LL))(
                   v236,
                   j,
                   &v233);
          if ( v156 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x73A,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v156,
              (int)v191);
          v157 = (*(__int64 (__fastcall **)(struct CDeploymentFileRequest *, LPVOID *))(*(_QWORD *)v233 + 24LL))(
                   v233,
                   &v235);
          if ( v157 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x73B,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v157,
              (int)v191);
          v158 = _o__wcsicmp(v235, *(_QWORD *)(v141 + v140 + 56));
          v145 = 0;
          if ( !v158 )
            break;
          if ( v235 )
          {
            CoTaskMemFree(v235);
            v145 = 0;
            v235 = 0;
          }
          if ( v233 )
          {
            (*(void (__fastcall **)(struct CDeploymentFileRequest *, _QWORD))(*(_QWORD *)v233 + 16LL))(v233, 0);
            v145 = 0;
            v233 = 0;
          }
        }
        v159 = *((_QWORD *)this + 75);
        if ( v159 )
        {
          v191 = *(wchar_t **)(v141 + v140 + 56);
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v159,
            2,
            L"    Found existing RNG file: [%s] with AltSourceHash [%s]",
            *(_QWORD *)(v141 + v140 + 8));
        }
        v145 = (int *)v233;
        v160 = v233;
        v203 = v233;
        if ( v235 )
        {
          CoTaskMemFree(v235);
          v235 = 0;
          v145 = (int *)v233;
        }
        if ( v145 )
        {
          (*(void (__fastcall **)(int *))(*(_QWORD *)v145 + 16LL))(v145);
          v145 = 0;
          v233 = 0;
        }
LABEL_360:
        if ( v236 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v236 + 16LL))(v236);
        if ( v160 )
        {
          v16 = 0;
          goto LABEL_376;
        }
      }
      v161 = *((_QWORD *)this + 75);
      if ( v161 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v161,
          2,
          L"    Adding RNG file: [%s] with AltSourceHash [%s]",
          *(_QWORD *)(v141 + v140 + 8),
          *(_QWORD *)(v141 + v140 + 56));
      v162 = CDeploymentFileRequest::Create(
               Src,
               v150,
               v148,
               *(const wchar_t **)(v141 + v140 + 16),
               L"Express",
               v195,
               &v231);
      ShouldDownloadRangelessFile = v162;
      v16 = 0;
      if ( v162 < 0 )
      {
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v162,
          L"CDeploymentSession::GenerateExpressDownloadList",
          1872);
        goto LABEL_287;
      }
      v203 = v231;
LABEL_377:
      for ( k = 0; k < *(_DWORD *)(v206 + v140 + 80); ++k )
      {
        v168 = CDeploymentSession::CheckCancelRequested(this, v145);
        ShouldDownloadRangelessFile = v168;
        if ( v168 < 0 )
        {
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            *((_QWORD *)this + 75),
            (unsigned int)v168,
            L"CDeploymentSession::GenerateExpressDownloadList",
            1901);
          v16 = 0;
          goto LABEL_287;
        }
        v169 = 16LL * k;
        v170 = *(_QWORD *)(v206 + v140 + 72);
        if ( (WCHAR *)((char *)v16 + *(_QWORD *)(v169 + v170 + 8)) < v16 )
        {
          ShouldDownloadRangelessFile = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v16 = (WCHAR *)((char *)v16 + *(_QWORD *)(v169 + v170 + 8));
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
        if ( !v196 )
        {
          if ( v230 )
          {
            (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v230 + 16LL))(v230);
            v230 = 0;
          }
          v171 = CDeploymentFileRange::Create(
                   (unsigned __int64)v204 + *(_QWORD *)(v169 + v170),
                   *(_QWORD *)(v169 + v170 + 8),
                   &v230);
          ShouldDownloadRangelessFile = v171;
          if ( v171 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v171,
              L"CDeploymentSession::GenerateExpressDownloadList",
              1909);
            v16 = 0;
            goto LABEL_287;
          }
          v172 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(&v205, &v230);
          v173 = CDeploymentFileRequest::AppendExpressFileRange(v203, v172);
          if ( v173 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x776,
              (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
              (const char *)(unsigned int)v173,
              (int)v191);
        }
        v140 = *(_QWORD *)&v220[0];
      }
      v141 = v206;
      v166 = v201;
LABEL_394:
      if ( v196 )
        goto LABEL_419;
      if ( v231 )
      {
        v174 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v210, &v231);
        v175 = CDeploymentDownloadRequest::AppendFileRequest(v208, v174);
        if ( v175 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x77F,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v175,
            (int)v191);
      }
      if ( v166 )
      {
        v176 = *((_QWORD *)this + 75);
        if ( v176 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v176, 2, L"        RNG file size: [%llu]", v16);
        v177 = *((_QWORD *)this + 75);
        if ( v177 )
        {
          v178 = L"TRUE";
          if ( !v195 )
            v178 = L"FALSE";
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v177, 2, L"        Optional: [%s]", v178, v191);
        }
        v179 = *((_QWORD *)this + 75);
        if ( v179 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v179, 2, L"        IsRangeRequestSupported: [%s]", L"TRUE");
        v180 = *((_QWORD *)this + 75);
        if ( v180 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v180,
            2,
            L"        Range count in RNG file: [%lu]",
            *(unsigned int *)(v141 + v140 + 80));
        if ( (unsigned __int64)v16 + v200 < v200 )
        {
          ShouldDownloadRangelessFile = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v200 += (unsigned __int64)v16;
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
        v181 = v194;
        goto LABEL_420;
      }
      if ( v197 )
        goto LABEL_419;
      v181 = v194;
      v182 = 184LL * v194;
      if ( v200 + *(_QWORD *)(v182 + *((_QWORD *)v209 + 14)) < v200 )
      {
        ShouldDownloadRangelessFile = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
      }
      else
      {
        v200 += *(_QWORD *)(v182 + *((_QWORD *)v209 + 14));
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
      if ( (unsigned __int64)v16 + v207 < v207 )
      {
        ShouldDownloadRangelessFile = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        v16 = 0;
      }
      else
      {
        v207 += (unsigned __int64)v16;
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
      v138 = v181 + 1;
      v130 = v215[0];
    }
    v165 = *((_QWORD *)this + 75);
    v16 = 0;
    if ( v165 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v165, 2, L"    RNG File exists: [%s]", *(_QWORD *)(v141 + v140 + 8));
    goto LABEL_376;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7A4,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v187);
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
