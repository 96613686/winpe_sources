# CDeploymentSession::GenerateDownloadList(ActionList *,int,int,int,int,wchar_t const *,ulong,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,_DUPackageInfo *,_ReportEventDownloadRequestParams *,IDeploymentDownloadRequest * *)

- ea: `0x18004f0b0`
- end: `0x18005220a`
- name: `?GenerateDownloadList@CDeploymentSession@@QEAAJPEAUActionList@@HHHHPEB_WKPEA_K222PEAU_DUPackageInfo@@PEAU_ReportEventDownloadRequestParams@@PEAPEAUIDeploymentDownloadRequest@@@Z`
- size: `12634`
- prototype: `__int64 __fastcall(CDeploymentSession *this, struct ActionList *, int, DWORD, int, int, wchar_t *, unsigned int, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, struct _DUPackageInfo *, struct _ReportEventDownloadRequestParams *, struct IDeploymentDownloadRequest **)`
- caller_count: `1`
- callee_count: `56`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180052d40`

## callees

- `0x1800059d0`
- `0x180005cf0`
- `0x180006a18`
- `0x180007d08`
- `0x180008ed8`
- `0x180010af4`
- `0x180012460`
- `0x18001270c`
- `0x180012770`
- `0x180012d94`
- `0x180012fe4`
- `0x18001efc8`
- `0x1800201cc`
- `0x180022fa8`
- `0x18002374c`
- `0x180023b20`
- `0x180024170`
- `0x180026af8`
- `0x180027f3c`
- `0x1800281d4`
- `0x180034be4`
- `0x180035a80`
- `0x180035bf0`
- `0x180036d28`
- `0x18003734c`
- `0x180038ecc`
- `0x180039f90`
- `0x18003c418`
- `0x18003d07c`
- `0x18003e304`
- `0x18003e4a4`
- `0x18003e600`
- `0x18004a5fc`
- `0x18004d8d0`
- `0x18004f0b0`
- `0x180054e0c`
- `0x180057b60`
- `0x18005e9e8`
- `0x1800613b4`
- `0x1800671d0`
- `0x180075044`
- `0x180077664`
- `0x180078b4c`
- `0x180078b9c`
- `0x18007c740`
- `0x18008c3e0`
- `0x18008fa60`
- `0x1800914dc`
- `0x180094d0c`
- `0x18009b760`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180050e99`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180050e99`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004fdf4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004ffe0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004fdf4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004ffe0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004fd26`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004fd26`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ff94`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004ff94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f692`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f7e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fb55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fc78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f692`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f7e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fb55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004fc78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f6a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f7fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f896`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fb6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fc8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f6a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f7fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f896`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fb6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004fc8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fff0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051a7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051a9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051d26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051d47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051a7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051a9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051d26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051d47`

## string_xrefs

- `0x1800521f1`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18004f4d1`: `GenerateDownloadList: Enabling EcoQos for thread`
- `0x18004f530`: `GenerateDownloadList: Adjusting thread priority...`
- `0x18004f5f6`: `GenerateDownloadList: Adjusting thread priority...`
- `0x18004ff61`: `Expected hash not available; assuming hashless CompDB and skipping validation.`
- `0x18005003a`: `File hash doesn't match but file was not deleted in Test Mode.`
- `0x180050ed0`: `Skipping ICbsServicingProcessor->WritePackageFileList PackageFilePath: [%ws]; must be repair content`

## pseudocode

```c
__int64 __fastcall CDeploymentSession::GenerateDownloadList(
        CDeploymentSession *this,
        struct ActionList *a2,
        int a3,
        DWORD a4,
        int a5,
        int a6,
        wchar_t *a7,
        unsigned int a8,
        unsigned __int64 *a9,
        unsigned __int64 *a10,
        unsigned __int64 *a11,
        unsigned __int64 *a12,
        struct _DUPackageInfo *a13,
        struct _ReportEventDownloadRequestParams *a14,
        struct IDeploymentDownloadRequest **a15)
{
  struct ActionList *v17; // r14
  _QWORD *v19; // rax
  const wchar_t *v20; // rcx
  signed int v21; // edi
  __int64 updated; // rcx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  bool v26; // dl
  int v27; // eax
  unsigned int v28; // ebx
  int v29; // eax
  __int64 v30; // rcx
  int v31; // eax
  const wchar_t *v32; // rax
  char v33; // bl
  int v34; // eax
  __int64 v35; // rbx
  HANDLE ProcessHeap; // rax
  int v37; // eax
  char v38; // r13
  __int64 v39; // rcx
  __int64 v40; // rbx
  __int64 v41; // rcx
  int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rcx
  int v45; // eax
  __int64 v46; // rbx
  HANDLE v47; // rax
  __int64 v48; // rax
  _OWORD *v49; // rcx
  __int64 v50; // rbx
  HANDLE v51; // rax
  __int64 v52; // rcx
  int *v53; // rdx
  unsigned int v54; // eax
  __int64 v55; // rcx
  unsigned __int64 v56; // r15
  int v57; // ecx
  __int64 v58; // r14
  char v59; // bl
  int v60; // eax
  __int64 v61; // rcx
  int *v62; // r8
  int *v63; // r9
  const wchar_t **v64; // r12
  const wchar_t **v65; // rax
  int v66; // eax
  __int64 v67; // rcx
  __int64 v68; // rcx
  LPCWSTR v69; // rbx
  HANDLE v70; // rax
  __int64 v71; // rcx
  LPCWSTR v72; // rbx
  HANDLE v73; // rax
  int v74; // eax
  __int64 v75; // rcx
  __int64 v76; // rcx
  DWORD FileAttributesW; // eax
  BOOL v78; // r14d
  int FileSize; // eax
  __int64 v80; // rcx
  __int64 v81; // rcx
  signed int LastError; // eax
  const WCHAR *v83; // rbx
  __int64 v84; // rcx
  int v85; // eax
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // r9
  __int64 v89; // rdx
  const WCHAR *v90; // rax
  __int64 v91; // rcx
  __int64 v92; // rcx
  signed int v93; // eax
  __int64 v94; // rbx
  int v95; // ecx
  int v96; // ecx
  int v97; // ecx
  int v98; // ecx
  int v99; // ecx
  const wchar_t *v100; // r15
  __int64 v101; // rcx
  __int64 v102; // r9
  __int64 v103; // rdx
  int v104; // ecx
  int v105; // ecx
  int v106; // ecx
  int v107; // ecx
  int v108; // ecx
  __int64 v109; // r9
  __int64 v110; // rdx
  int OuterContainerDownloadList; // eax
  __int64 v112; // rcx
  const wchar_t *v113; // r9
  const wchar_t *v114; // r9
  __int64 v115; // rax
  int v116; // eax
  char v117; // r14
  bool v118; // zf
  const wchar_t **v119; // rbx
  int v120; // eax
  __int64 v121; // r9
  const wchar_t *v122; // rdx
  __int64 v123; // r8
  __int64 v124; // rax
  CDeploymentDownloadRequest *v125; // r15
  unsigned int v126; // eax
  int v127; // ecx
  __int64 v128; // rax
  __int64 v129; // rdx
  unsigned __int64 v130; // rbx
  const wchar_t *v131; // rdx
  __int64 v132; // r8
  __int64 v133; // r9
  __int64 v134; // rdx
  const wchar_t *v135; // r13
  const wchar_t *p_Src; // r15
  unsigned __int64 v137; // r12
  const wchar_t *v138; // rbx
  const wchar_t *v139; // r14
  int OffsetInOuterContainer; // eax
  __int64 v141; // rcx
  __int64 v142; // rcx
  __int64 v143; // rcx
  int v144; // eax
  __int64 v145; // rax
  int v146; // eax
  __int64 v147; // r9
  __int64 v148; // rax
  struct CDeploymentFileRequest *v149; // rbx
  int appended; // eax
  __int64 v151; // rax
  unsigned int v152; // r11d
  int v153; // eax
  char v154; // cl
  __int64 v155; // rbx
  __int64 v156; // rdi
  int v157; // ebx
  __int64 v158; // rcx
  unsigned __int8 v159; // r14
  __int64 v160; // r13
  int ExpressDownloadList; // eax
  __int64 v162; // r9
  __int64 v163; // rdx
  int v164; // eax
  unsigned __int64 v165; // r15
  int v166; // ecx
  int v167; // ecx
  int v168; // ecx
  int v169; // ecx
  unsigned __int64 v170; // r15
  unsigned __int64 v171; // rbx
  unsigned __int64 v172; // r15
  unsigned __int64 v173; // rbx
  int v174; // ecx
  int v175; // ecx
  int v176; // ecx
  unsigned __int64 v177; // r15
  unsigned __int64 v178; // rbx
  unsigned __int64 v179; // r15
  unsigned __int64 v180; // rbx
  unsigned __int64 v181; // r15
  unsigned __int64 v182; // rbx
  unsigned __int64 v183; // r15
  unsigned __int64 v184; // rbx
  int v185; // ecx
  int v186; // ecx
  int v187; // ecx
  int v188; // ecx
  unsigned __int64 v189; // r14
  unsigned __int64 v190; // rbx
  int v191; // eax
  __int64 v192; // r9
  __int64 v193; // rcx
  unsigned int i; // r14d
  int v195; // eax
  int v196; // eax
  __int64 v197; // r9
  __int64 v198; // rcx
  __int64 v199; // rdx
  unsigned int j; // ebx
  int v201; // eax
  __int64 v202; // r9
  __int64 v203; // rcx
  __int64 v204; // rcx
  unsigned __int64 v205; // rbx
  __int64 v206; // rcx
  __int64 v207; // rcx
  __int64 v208; // rcx
  __int64 v209; // rcx
  CDeploymentDownloadRequest *v210; // r13
  int v211; // r15d
  struct ActionList *v212; // r12
  unsigned int v213; // eax
  char v214; // cl
  int v215; // r14d
  __int64 v216; // rbx
  const WCHAR *v217; // rax
  __int64 v218; // rcx
  unsigned int v219; // eax
  int *v220; // rax
  struct _DUPackageInfo *v221; // rax
  struct _ReportEventDownloadRequestParams *v222; // rcx
  const char *v223; // r9
  __int64 result; // rax
  const char *v225; // r9
  PCNZWCH lpString2; // [rsp+20h] [rbp-418h]
  int lpString2a; // [rsp+20h] [rbp-418h]
  int cchCount2[2]; // [rsp+28h] [rbp-410h]
  int cchCount2a; // [rsp+28h] [rbp-410h]
  int cchCount2b; // [rsp+28h] [rbp-410h]
  struct CDeploymentFileRequest **v231; // [rsp+30h] [rbp-408h]
  __int64 v232; // [rsp+38h] [rbp-400h]
  __int64 v233; // [rsp+40h] [rbp-3F8h]
  __int64 v234; // [rsp+48h] [rbp-3F0h]
  unsigned __int8 v235; // [rsp+60h] [rbp-3D8h]
  LPCWSTR lpFileName; // [rsp+68h] [rbp-3D0h] BYREF
  char v237; // [rsp+70h] [rbp-3C8h]
  __int64 v238; // [rsp+78h] [rbp-3C0h]
  char v239; // [rsp+80h] [rbp-3B8h]
  struct CDeploymentFileRequest *v240; // [rsp+88h] [rbp-3B0h] BYREF
  CDeploymentDownloadRequest *v241; // [rsp+90h] [rbp-3A8h]
  struct CDeploymentFileRequest *v242; // [rsp+98h] [rbp-3A0h] BYREF
  unsigned int v243; // [rsp+A0h] [rbp-398h]
  int v244; // [rsp+A4h] [rbp-394h]
  unsigned __int64 v245; // [rsp+A8h] [rbp-390h] BYREF
  struct CDeploymentFileRequest *v246; // [rsp+B0h] [rbp-388h] BYREF
  struct CDeploymentFileRange *v247; // [rsp+B8h] [rbp-380h] BYREF
  unsigned __int64 v248; // [rsp+C0h] [rbp-378h]
  unsigned __int64 v249; // [rsp+C8h] [rbp-370h]
  int v250; // [rsp+D0h] [rbp-368h]
  struct CDeploymentDownloadRequest *v251; // [rsp+D8h] [rbp-360h] BYREF
  unsigned __int64 v252; // [rsp+E0h] [rbp-358h]
  struct ActionList *v253; // [rsp+E8h] [rbp-350h]
  unsigned __int64 v254; // [rsp+F0h] [rbp-348h]
  unsigned __int64 v255; // [rsp+F8h] [rbp-340h]
  unsigned int v256; // [rsp+100h] [rbp-338h]
  unsigned int v257; // [rsp+104h] [rbp-334h]
  unsigned int v258; // [rsp+108h] [rbp-330h]
  unsigned int v259; // [rsp+10Ch] [rbp-32Ch]
  unsigned int v260; // [rsp+110h] [rbp-328h]
  unsigned int v261; // [rsp+114h] [rbp-324h]
  unsigned int v262; // [rsp+118h] [rbp-320h]
  unsigned int v263; // [rsp+11Ch] [rbp-31Ch]
  unsigned __int64 v264; // [rsp+120h] [rbp-318h]
  int *v265; // [rsp+128h] [rbp-310h]
  unsigned __int64 v266; // [rsp+130h] [rbp-308h]
  int v267; // [rsp+138h] [rbp-300h] BYREF
  DWORD v268; // [rsp+13Ch] [rbp-2FCh]
  int v269; // [rsp+140h] [rbp-2F8h] BYREF
  char v270; // [rsp+144h] [rbp-2F4h] BYREF
  __int64 v271; // [rsp+148h] [rbp-2F0h] BYREF
  unsigned __int64 v272; // [rsp+150h] [rbp-2E8h] BYREF
  unsigned __int64 v273; // [rsp+158h] [rbp-2E0h]
  __int64 v274; // [rsp+160h] [rbp-2D8h] BYREF
  unsigned __int64 v275; // [rsp+168h] [rbp-2D0h]
  unsigned __int64 v276; // [rsp+170h] [rbp-2C8h]
  unsigned __int64 v277; // [rsp+178h] [rbp-2C0h]
  unsigned __int64 v278; // [rsp+180h] [rbp-2B8h]
  const wchar_t **v279; // [rsp+188h] [rbp-2B0h]
  __int128 v280; // [rsp+190h] [rbp-2A8h] BYREF
  __int128 v281; // [rsp+1A0h] [rbp-298h]
  __int128 v282; // [rsp+1B0h] [rbp-288h]
  __int128 v283; // [rsp+1C0h] [rbp-278h]
  __int64 v284; // [rsp+1D0h] [rbp-268h]
  struct IDeploymentDownloadRequest **v285; // [rsp+1E0h] [rbp-258h]
  unsigned __int64 *v286; // [rsp+1E8h] [rbp-250h]
  unsigned __int64 *v287; // [rsp+1F0h] [rbp-248h]
  unsigned __int64 v288; // [rsp+1F8h] [rbp-240h] BYREF
  const wchar_t **v289; // [rsp+200h] [rbp-238h]
  unsigned __int64 *v290; // [rsp+208h] [rbp-230h]
  unsigned __int64 *v291; // [rsp+210h] [rbp-228h]
  LPCWSTR v292; // [rsp+220h] [rbp-218h] BYREF
  __int64 v293; // [rsp+228h] [rbp-210h]
  struct _DUPackageInfo *v294; // [rsp+230h] [rbp-208h]
  struct _ReportEventDownloadRequestParams *v295; // [rsp+238h] [rbp-200h]
  const wchar_t *v296; // [rsp+240h] [rbp-1F8h] BYREF
  char v297[8]; // [rsp+248h] [rbp-1F0h] BYREF
  char v298[8]; // [rsp+250h] [rbp-1E8h] BYREF
  char v299[8]; // [rsp+258h] [rbp-1E0h] BYREF
  char v300[16]; // [rsp+260h] [rbp-1D8h] BYREF
  _QWORD v301[2]; // [rsp+270h] [rbp-1C8h] BYREF
  __int128 v302; // [rsp+280h] [rbp-1B8h] BYREF
  __int64 v303; // [rsp+290h] [rbp-1A8h]
  __int64 v304; // [rsp+298h] [rbp-1A0h]
  __int128 v305; // [rsp+2A0h] [rbp-198h] BYREF
  __int64 v306; // [rsp+2B0h] [rbp-188h]
  __int64 v307; // [rsp+2B8h] [rbp-180h]
  __int128 v308; // [rsp+2C0h] [rbp-178h] BYREF
  __int64 v309; // [rsp+2D0h] [rbp-168h]
  __int64 v310; // [rsp+2D8h] [rbp-160h]
  _QWORD v311[2]; // [rsp+2E0h] [rbp-158h] BYREF
  char v312; // [rsp+2F0h] [rbp-148h]
  __int64 v313; // [rsp+2F8h] [rbp-140h]
  char v314[16]; // [rsp+300h] [rbp-138h] BYREF
  _BYTE v315[32]; // [rsp+310h] [rbp-128h] BYREF
  LPVOID v316; // [rsp+330h] [rbp-108h] BYREF
  LPVOID pv; // [rsp+338h] [rbp-100h] BYREF
  __int64 v318; // [rsp+340h] [rbp-F8h] BYREF
  __int64 v319; // [rsp+348h] [rbp-F0h] BYREF
  __int64 v320; // [rsp+350h] [rbp-E8h] BYREF
  __int64 v321; // [rsp+358h] [rbp-E0h] BYREF
  unsigned int v322; // [rsp+360h] [rbp-D8h] BYREF
  unsigned int v323; // [rsp+364h] [rbp-D4h] BYREF
  int v324; // [rsp+368h] [rbp-D0h] BYREF
  int v325; // [rsp+36Ch] [rbp-CCh] BYREF
  __int64 v326; // [rsp+370h] [rbp-C8h] BYREF
  __int64 v327; // [rsp+378h] [rbp-C0h] BYREF
  __int64 v328; // [rsp+380h] [rbp-B8h] BYREF
  __int128 Src; // [rsp+388h] [rbp-B0h] BYREF
  __int64 v330; // [rsp+398h] [rbp-A0h]
  unsigned __int64 v331; // [rsp+3A0h] [rbp-98h]
  __int64 v332; // [rsp+3A8h] [rbp-90h] BYREF
  __int64 v333; // [rsp+3B0h] [rbp-88h] BYREF
  __int64 v334; // [rsp+3B8h] [rbp-80h] BYREF
  __int64 v335; // [rsp+3C0h] [rbp-78h] BYREF
  __int64 v336[2]; // [rsp+3C8h] [rbp-70h] BYREF
  _OWORD v337[2]; // [rsp+3D8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+0h]

  v313 = -2;
  v268 = a4;
  v250 = a3;
  v17 = a2;
  v253 = a2;
  v291 = a9;
  v290 = a10;
  v286 = a11;
  v287 = a12;
  v294 = a13;
  v295 = a14;
  v285 = a15;
  v241 = 0;
  v251 = 0;
  v324 = 0;
  v267 = 0;
  memset_0(&v280, 0, 0x48u);
  LODWORD(v327) = 0;
  v336[0] = 0;
  v336[1] = 0;
  try
  {
    v19 = operator new(0x40u);
    *v19 = v19;
    v19[1] = v19;
    v19[2] = v19;
    *((_WORD *)v19 + 12) = 257;
    v336[0] = (__int64)v19;
    v311[0] = this;
    v311[1] = &v324;
    v312 = 1;
    v20 = (const wchar_t *)*((_QWORD *)this + 75);
    if ( !v17 )
    {
      v21 = -2147024809;
      if ( !v20 )
      {
LABEL_4:
        updated = 0;
LABEL_8:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
        goto LABEL_705;
      }
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v20,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GenerateDownloadList",
                                2059,
                                -2147024809);
LABEL_6:
      if ( (int)updated < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated);
      goto LABEL_8;
    }
    if ( !*((_DWORD *)v17 + 18) )
    {
      v21 = -1047526399;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -1047526399;
      lpString2a = 2060;
      goto LABEL_12;
    }
    if ( !*((_QWORD *)v17 + 8) )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2061;
      goto LABEL_12;
    }
    if ( !a7 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2062;
      goto LABEL_12;
    }
    if ( !v291 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2063;
      goto LABEL_12;
    }
    if ( !v290 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2064;
      goto LABEL_12;
    }
    if ( !v286 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2065;
      goto LABEL_12;
    }
    if ( !v287 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2066;
      goto LABEL_12;
    }
    if ( !a14 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2067;
      goto LABEL_12;
    }
    if ( !v285 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2068;
      goto LABEL_12;
    }
    if ( !a13 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2069;
LABEL_12:
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v20,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GenerateDownloadList",
                                lpString2a,
                                cchCount2a);
      goto LABEL_6;
    }
    if ( v20 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v20, 2, L"Creating Download request MaxPercentage [%lu]", a8);
    v23 = CDeploymentDownloadRequest::Create(v20, a7, a8, &v251);
    v21 = v23;
    if ( v23 < 0 )
    {
      v24 = *((_QWORD *)this + 75);
      if ( !v24 )
      {
LABEL_44:
        v25 = 0;
        goto LABEL_48;
      }
      v25 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                            v24,
                            4,
                            L"%s(%d): Result = 0x%X",
                            L"CDeploymentSession::GenerateDownloadList",
                            2074,
                            v23);
LABEL_46:
      if ( (int)v25 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v25);
LABEL_48:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v25);
      goto LABEL_49;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl'::`2'::impl) == 1 )
      {
        LogAdapter::TraceInfo<>("GenerateDownloadList: Enabling EcoQos for thread");
        v27 = CDeploymentSession::SetEcoQos(this, v26);
        if ( v27 < 0 )
          LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v27, "GenerateDownloadList: Error requesting EcoQos");
      }
    }
    *((_DWORD *)this + 92) = 2;
    if ( *((_DWORD *)this + 186) == 1 )
    {
      v28 = 2;
    }
    else if ( *((_DWORD *)this + 186) == 2 )
    {
      v28 = 4;
    }
    else
    {
      v28 = 0;
    }
    if ( *((_QWORD *)this + 76) )
    {
      if ( v28 )
      {
        LogAdapter::TraceInfo<>("GenerateDownloadList: Adjusting thread priority...");
        v29 = CDeploymentSession::AdjustPriority(this, v28, &v324);
        v21 = v29;
        if ( v29 < 0 )
        {
          v30 = *((_QWORD *)this + 75);
          if ( !v30 )
            goto LABEL_44;
          cchCount2b = v29;
          LODWORD(lpString2) = 2092;
          goto LABEL_64;
        }
      }
      else
      {
        v31 = *((_DWORD *)this + 114);
        if ( v31 == 3 || v31 == 24 )
        {
          CDeploymentSession::GetUserSessionId((char *)this + 24, &v272);
          v32 = L"TRUE";
          v33 = BYTE4(v272);
          if ( !BYTE4(v272) )
            v32 = L"FALSE";
          v296 = v32;
          LogAdapter::TraceInfo<wchar_t const *>("GenerateDownloadList: User session found = [{}].", &v296);
          if ( !v33 )
          {
            LogAdapter::TraceInfo<>("GenerateDownloadList: Adjusting thread priority...");
            v34 = CDeploymentSession::AdjustPriority(this, *((unsigned int *)this + 92), &v324);
            v21 = v34;
            if ( v34 < 0 )
            {
              v30 = *((_QWORD *)this + 75);
              if ( !v30 )
                goto LABEL_44;
              cchCount2b = v34;
              LODWORD(lpString2) = 2105;
              goto LABEL_64;
            }
          }
          v17 = v253;
        }
      }
    }
    v21 = CMoUpdateHelpersT<CEmptyType>::IsSkipDeleteCorruptFile(&v267);
    if ( v21 < 0 )
    {
      v30 = *((_QWORD *)this + 75);
      if ( !v30 )
        goto LABEL_44;
      cchCount2b = v21;
      LODWORD(lpString2) = 2109;
      goto LABEL_64;
    }
    v35 = *((_QWORD *)this + 69);
    if ( v35 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v35 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      *((_QWORD *)this + 69) = 0;
    }
    v37 = CDeploymentSession::ProcessSandboxContainerPayload(this, (__int64)v17, a3, a4, 0);
    v21 = v37;
    v38 = 0;
    if ( v37 < 0 )
    {
      v39 = *((_QWORD *)this + 75);
      if ( v39 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v39,
          4,
          L"ProcessSandboxContainerPayload for GenerateDownloadList failed: [0x%X]",
          (unsigned int)v37);
      v30 = *((_QWORD *)this + 75);
      if ( !v30 )
        goto LABEL_44;
      cchCount2b = v21;
      LODWORD(lpString2) = 2121;
LABEL_64:
      v25 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                            v30,
                            4,
                            L"%s(%d): Result = 0x%X",
                            L"CDeploymentSession::GenerateDownloadList",
                            lpString2,
                            cchCount2b);
      goto LABEL_46;
    }
    if ( !*((_BYTE *)this + 128) || *((_DWORD *)this + 83) == 3 )
    {
      v40 = *((_QWORD *)v17 + 11);
      v41 = v40 + 168LL * *((unsigned int *)v17 + 24);
      while ( 1 )
      {
        if ( v40 == v41 )
        {
          if ( *((_DWORD *)this + 83) == 3 )
            *((_DWORD *)this + 83) = 4;
          goto LABEL_104;
        }
        if ( *(_DWORD *)(v40 + 88) == 7 )
          break;
        v40 += 168;
      }
      v274 = 0;
      _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&v274);
      v42 = CMiscHelpersT<CEmptyType>::CombinePath(
              *((_QWORD *)this + 61),
              *(_QWORD *)(*(_QWORD *)(v40 + 112) + 24LL),
              0);
      v21 = v42;
      if ( v42 < 0 )
      {
        v43 = *((_QWORD *)this + 75);
        if ( v43 )
        {
          LODWORD(lpString2) = 2133;
          v45 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v43,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDeploymentSession::GenerateDownloadList",
                  lpString2,
                  v42);
          v44 = (unsigned int)v45;
          if ( v45 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v45);
        }
        else
        {
          v44 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v44);
        v46 = v274;
        if ( v274 )
        {
          v47 = GetProcessHeap();
          HeapFree(v47, 0, (LPVOID)(v46 - 4));
          v25 = 0;
          goto LABEL_48;
        }
LABEL_49:
        v241 = v251;
        goto LABEL_705;
      }
      v48 = to_wstring(v315, v274);
      v49 = (_OWORD *)((char *)this + 96);
      if ( *((_BYTE *)this + 128) )
      {
        std::wstring::operator=(v49, v48);
      }
      else
      {
        *v49 = 0;
        *((_QWORD *)this + 14) = 0;
        *((_QWORD *)this + 15) = 0;
        *v49 = *(_OWORD *)v48;
        *((_OWORD *)this + 7) = *(_OWORD *)(v48 + 16);
        *(_QWORD *)(v48 + 16) = 0;
        *(_QWORD *)(v48 + 24) = 7;
        *(_WORD *)v48 = 0;
        *((_BYTE *)this + 128) = 1;
      }
      std::wstring::~wstring(v315);
      v50 = v274;
      if ( v274 )
      {
        v51 = GetProcessHeap();
        HeapFree(v51, 0, (LPVOID)(v50 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
    }
LABEL_104:
    v264 = 0;
    v273 = 0;
    v248 = 0;
    v272 = 0;
    v249 = 0;
    v244 = 0;
    v256 = 0;
    v257 = 0;
    v266 = 0;
    v277 = 0;
    v276 = 0;
    v275 = 0;
    v258 = 0;
    v259 = 0;
    v260 = 0;
    v261 = 0;
    v262 = 0;
    v263 = 0;
    v52 = *((_QWORD *)v17 + 8);
    v53 = (int *)(v52 + 168LL * *((unsigned int *)v17 + 18));
    v265 = v53;
    v241 = v251;
    while ( 1 )
    {
      v238 = v52;
      if ( (int *)v52 == v53 )
      {
        if ( *((_DWORD *)this + 66) && *((_DWORD *)this + 67) )
          *((_DWORD *)this + 66) = 0;
        v318 = 0;
        v323 = 0;
        v191 = (*(__int64 (__fastcall **)(CDeploymentDownloadRequest *, __int64 *))(*(_QWORD *)v241 + 40LL))(
                 v241,
                 &v318);
        v21 = v191;
        if ( v191 < 0 )
        {
          v192 = 2660;
          v193 = *((_QWORD *)this + 75);
LABEL_605:
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            v193,
            (unsigned int)v191,
            L"CDeploymentSession::GenerateDownloadList",
            v192);
          goto LABEL_606;
        }
        v191 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v318 + 24LL))(v318, &v323);
        v21 = v191;
        v193 = *((_QWORD *)this + 75);
        if ( v191 < 0 )
        {
          v192 = 2661;
          goto LABEL_605;
        }
        if ( v193 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v193, 1, L"Total file requests: [%lu]", v323);
        for ( i = 0; i < v323; ++i )
        {
          v319 = 0;
          v320 = 0;
          v316 = 0;
          pv = 0;
          v322 = 0;
          v195 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v318 + 32LL))(v318, i, &v319);
          v21 = v195;
          if ( v195 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v195,
              L"CDeploymentSession::GenerateDownloadList",
              2673);
            goto LABEL_615;
          }
          v196 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v319 + 24LL))(v319, &v316);
          v21 = v196;
          if ( v196 < 0 )
          {
            v197 = 2674;
            goto LABEL_622;
          }
          v21 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v319 + 40LL))(v319, &pv);
          if ( v21 < 0 )
          {
            v197 = 2675;
            v199 = (unsigned int)v21;
            v198 = *((_QWORD *)this + 75);
            goto LABEL_624;
          }
          if ( *((_QWORD *)this + 75) )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(*((_QWORD *)this + 75), 1, L"Requested file: %ws, hash: %ws");
          v196 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v319 + 48LL))(v319, &v320);
          v21 = v196;
          if ( v196 < 0 )
          {
            v197 = 2680;
LABEL_622:
            v198 = *((_QWORD *)this + 75);
            goto LABEL_623;
          }
          v196 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v320 + 24LL))(v320, &v322);
          v21 = v196;
          v198 = *((_QWORD *)this + 75);
          if ( v196 < 0 )
          {
            v197 = 2681;
LABEL_623:
            v199 = (unsigned int)v196;
LABEL_624:
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(v198, v199, L"CDeploymentSession::GenerateDownloadList", v197);
            goto LABEL_615;
          }
          if ( v198 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v198, 1, L"  Total range requests for file: [%lu]", v322);
          for ( j = 0; j < v322; ++j )
          {
            v321 = 0;
            v333 = 0;
            v332 = 0;
            v201 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v320 + 32LL))(v320, j, &v321);
            v21 = v201;
            if ( v201 < 0 )
            {
              v202 = 2691;
LABEL_639:
              v203 = *((_QWORD *)this + 75);
              goto LABEL_640;
            }
            v201 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v321 + 24LL))(v321, &v333);
            v21 = v201;
            if ( v201 < 0 )
            {
              v202 = 2692;
              goto LABEL_639;
            }
            v201 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v321 + 32LL))(v321, &v332);
            v21 = v201;
            v203 = *((_QWORD *)this + 75);
            if ( v201 < 0 )
            {
              v202 = 2693;
LABEL_640:
              CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                v203,
                (unsigned int)v201,
                L"CDeploymentSession::GenerateDownloadList",
                v202);
              SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v321);
LABEL_615:
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              if ( v316 )
              {
                CoTaskMemFree(v316);
                v316 = 0;
              }
              SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v320);
              SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v319);
LABEL_606:
              SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v318);
              goto LABEL_705;
            }
            if ( v203 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v203,
                1,
                L"  Requested range #%llu offset: %llu, length: %llu",
                j,
                v333,
                v332);
            SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v321);
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( v316 )
          {
            CoTaskMemFree(v316);
            v316 = 0;
          }
          SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v320);
          SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v319);
        }
        SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v318);
        v204 = *((_QWORD *)this + 75);
        v205 = v264;
        if ( v204 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v204, 2, L"Required size of the Download: [%llu]", v264);
        v206 = *((_QWORD *)this + 75);
        if ( v206 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v206, 2, L"Total Expanded size : [%llu]", v273);
        v207 = *((_QWORD *)this + 75);
        if ( v207 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v207, 2, L"Required size of the required Download: [%llu]", v248);
        v208 = *((_QWORD *)this + 75);
        if ( v208 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v208, 2, L"Required Expanded size : [%llu]", v249);
        v209 = *((_QWORD *)this + 75);
        if ( v209 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v209, 2, L"Setting total size of the Request: [%llu]", v205);
        v210 = v241;
        ExpressDownloadList = CDeploymentDownloadRequest::SetTotalRequestSize(v241, v205, v250 == 0);
        v21 = ExpressDownloadList;
        if ( ExpressDownloadList < 0 )
        {
          v162 = 2705;
          goto LABEL_415;
        }
        v211 = 0;
        if ( v205 )
        {
          *((_QWORD *)this + 47) = v205;
          goto LABEL_667;
        }
        v213 = *((_DWORD *)this + 114);
        if ( v213 == 25 || v213 == 4 || (v214 = 0, v213 == 22) )
          v214 = 1;
        if ( (*((_BYTE *)this + 372) & 0x20) != 0 && v213 <= 0x18 )
        {
          v215 = 20971544;
          if ( !_bittest(&v215, v213) )
            goto LABEL_677;
          goto LABEL_679;
        }
        v215 = 20971544;
LABEL_677:
        if ( *((int *)this + 83) < 2 && *((_BYTE *)this + 128) )
LABEL_679:
          v214 = 0;
        if ( *((_BYTE *)this + 336) || !v214 )
        {
LABEL_667:
          v212 = v253;
        }
        else
        {
          v216 = *((_QWORD *)this + 58);
          if ( *((_DWORD *)this + 83) == 2 && *((_BYTE *)this + 128) )
          {
            v217 = (const WCHAR *)((char *)this + 96);
            v218 = *((_QWORD *)this + 14);
            if ( *((_QWORD *)this + 15) > 7u )
              v217 = *(const WCHAR **)v217;
            v292 = v217;
            v293 = v218;
            std::optional<std::wstring>::operator=<wil::basic_zstring_view<wchar_t> &,0>(v216 + 136, &v292);
          }
          v212 = v253;
          if ( !*((_DWORD *)this + 57) )
          {
            ExpressDownloadList = CDeploymentSession::Expand(this, v253);
            v21 = ExpressDownloadList;
            if ( ExpressDownloadList < 0 )
            {
              v162 = 2750;
              goto LABEL_415;
            }
          }
          if ( *((_DWORD *)v212 + 60) && (v219 = *((_DWORD *)this + 114), v219 <= 0x18) && _bittest(&v215, v219) )
          {
            ExpressDownloadList = CDeploymentSession::ComposePayloads(this, v212);
            v21 = ExpressDownloadList;
            v211 = 1;
            if ( ExpressDownloadList < 0 )
            {
              v162 = 2758;
              goto LABEL_415;
            }
          }
          else
          {
            v211 = 0;
          }
          v325 = 0;
          v269 = -2145116147;
          v21 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v216 + 200LL))(
                  v216,
                  4096,
                  *((_QWORD *)this + 63),
                  &v325);
          v220 = &v269;
          do
          {
            if ( v21 == *v220 )
            {
              v21 = 0;
              goto LABEL_702;
            }
            ++v220;
          }
          while ( v220 != (int *)&v270 );
          if ( v21 >= 0 )
LABEL_702:
            *((_BYTE *)this + 336) = 1;
          v205 = v264;
        }
        v221 = v294;
        *(_OWORD *)v294 = v280;
        *((_OWORD *)v221 + 1) = v281;
        *((_OWORD *)v221 + 2) = v282;
        *((_OWORD *)v221 + 3) = v283;
        *((_QWORD *)v221 + 8) = v284;
        *v291 = v205;
        *v290 = v273;
        *v286 = v248;
        *v287 = v249;
        v222 = v295;
        *((_DWORD *)v295 + 33) = v211;
        *((_DWORD *)v222 + 6) = v244;
        *((_DWORD *)v222 + 28) = *((_DWORD *)this + 87);
        *((_DWORD *)v222 + 12) = *((_DWORD *)v212 + 18);
        *((_DWORD *)v222 + 13) = v256;
        *((_DWORD *)v222 + 14) = v257;
        *((_QWORD *)v222 + 8) = v266;
        *((_QWORD *)v222 + 9) = v277;
        *((_QWORD *)v222 + 10) = v276;
        *((_QWORD *)v222 + 11) = v275;
        *((_DWORD *)v222 + 24) = v258;
        *((_DWORD *)v222 + 25) = v259;
        *((_DWORD *)v222 + 26) = v260;
        *((_DWORD *)v222 + 27) = v261;
        *((_DWORD *)v222 + 32) = v262;
        *((_DWORD *)v222 + 34) = v263;
        v241 = 0;
        *v285 = v210;
        goto LABEL_705;
      }
      v328 = 0;
      v54 = *(_DWORD *)(v52 + 88);
      if ( v54 == 24 )
      {
        v55 = *((_QWORD *)this + 75);
        if ( !v55 )
          goto LABEL_110;
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v55,
          2,
          L"Skipping UUP Product package download from ActionList [%ws]",
          *(_QWORD *)(v238 + 56));
        goto LABEL_109;
      }
      v252 = 0;
      v56 = 0;
      v255 = 0;
      v254 = 0;
      v278 = 0;
      v243 = 0;
      v237 = 0;
      if ( v54 <= 0xF )
      {
        v57 = 36992;
        if ( _bittest(&v57, v54) )
          break;
      }
      v58 = v238;
      if ( *(_DWORD *)(v238 + 104) == 2 || *((_DWORD *)this + 114) == 8 )
        goto LABEL_117;
      v21 = 0;
      v59 = 0;
LABEL_118:
      v239 = v59;
      v60 = *((_DWORD *)this + 114);
      if ( (v60 == 3 || v60 == 24)
        && ((v61 = *((_QWORD *)this + 49)) != 0
          ? (v62 = (int *)*((_QWORD *)this + 49), v53 = v62)
          : (v61 = 0, v62 = 0, v53 = 0),
            v63 = (int *)(v61 + 4LL * *((int *)this + 97)),
            v62 != v63) )
      {
        while ( *(_DWORD *)(v58 + 88) != *v53 )
        {
          if ( ++v53 == v63 )
            goto LABEL_126;
        }
        v235 = 1;
      }
      else
      {
LABEL_126:
        v235 = 0;
      }
      v64 = *(const wchar_t ***)(v58 + 112);
      v65 = &v64[23 * *(unsigned int *)(v58 + 120)];
      v289 = v65;
      while ( 1 )
      {
        v279 = v64;
        if ( v64 == v65 )
        {
          v125 = v241;
          goto LABEL_397;
        }
        lpFileName = 0;
        v326 = 0;
        v66 = CDeploymentSession::CheckCancelRequested(this, v53);
        v21 = v66;
        if ( v66 < 0 )
        {
          v67 = *((_QWORD *)this + 75);
          if ( !v67 )
            goto LABEL_131;
          cchCount2[0] = v66;
          LODWORD(lpString2) = 2177;
          v68 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v67,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GenerateDownloadList",
                                lpString2,
                                *(_QWORD *)cchCount2);
LABEL_134:
          if ( (int)v68 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v68);
          goto LABEL_136;
        }
        if ( (unsigned int)(*(_DWORD *)(v58 + 88) - 5) <= 1 )
        {
          if ( v263 + 1 < v263 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            ++v263;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v71 = *((_QWORD *)this + 75);
            if ( v71 )
            {
              cchCount2[0] = v21;
              LODWORD(lpString2) = 2181;
              goto LABEL_145;
            }
LABEL_131:
            v68 = 0;
LABEL_136:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v68);
            v69 = lpFileName;
            if ( lpFileName )
            {
              v70 = GetProcessHeap();
              HeapFree(v70, 0, (LPVOID)(v69 - 2));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              lpFileName = 0;
            }
LABEL_705:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
            __1__lambda_call_V_lambda_1___2__GenerateDownloadList_CDeploymentSession__QEAAJPEAUActionList__HHHHPEB_WKPEA_K222PEAU_DUPackageInfo__PEAU_ReportEventDownloadRequestParams__PEAPEAUIDeploymentDownloadRequest___Z__details_wil__QEAA_XZ(v311);
            std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v336);
            if ( v241 )
              (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v241 + 16LL))(v241);
            return (unsigned int)v21;
          }
        }
        if ( (unsigned __int64)*v64 + v56 < v56 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v255 = (unsigned __int64)*v64 + v56;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v71 = *((_QWORD *)this + 75);
          if ( !v71 )
            goto LABEL_131;
          cchCount2[0] = v21;
          LODWORD(lpString2) = 2184;
LABEL_145:
          v68 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v71,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GenerateDownloadList",
                                lpString2,
                                *(_QWORD *)cchCount2,
                                v231,
                                v232,
                                v233,
                                v234);
          goto LABEL_134;
        }
        if ( v250 && !v59 )
        {
          v72 = lpFileName;
          if ( lpFileName )
          {
            v73 = GetProcessHeap();
            HeapFree(v73, 0, (LPVOID)(v72 - 2));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            lpFileName = 0;
          }
          goto LABEL_395;
        }
        v74 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), (__int64)v64[3], 0);
        v21 = v74;
        if ( v74 < 0 )
        {
          v75 = *((_QWORD *)this + 75);
          if ( v75 )
          {
            cchCount2[0] = v74;
            LODWORD(lpString2) = 2196;
            v76 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                  v75,
                                  4,
                                  L"%s(%d): Result = 0x%X",
                                  L"CDeploymentSession::GenerateDownloadList",
                                  lpString2,
                                  *(_QWORD *)cchCount2);
            goto LABEL_160;
          }
          goto LABEL_158;
        }
        FileAttributesW = GetFileAttributesW(lpFileName);
        v78 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
        LODWORD(v242) = v78;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( v78 )
        {
          FileSize = CMoUpdateHelpersT<CEmptyType>::GetFileSize(lpFileName, &v326);
          v21 = FileSize;
          if ( FileSize < 0 )
          {
            v80 = *((_QWORD *)this + 75);
            if ( v80 )
            {
              cchCount2[0] = FileSize;
              LODWORD(lpString2) = 2201;
              goto LABEL_171;
            }
LABEL_158:
            v76 = 0;
            goto LABEL_162;
          }
          if ( !v326 )
          {
            v81 = *((_QWORD *)this + 75);
            if ( v81 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v81, 2, L"Deleting zero byte file: [%ws]", lpFileName);
            if ( !DeleteFileW(lpFileName) )
            {
              LastError = GetLastError();
              v21 = LastError;
              if ( LastError )
              {
                if ( LastError > 0 )
                  v21 = (unsigned __int16)LastError | 0x80070000;
              }
              else
              {
                v21 = -2147467259;
              }
              v76 = 0;
              if ( v21 < 0 && *((_QWORD *)this + 75) )
              {
                cchCount2[0] = v21;
                LODWORD(lpString2) = 2205;
                v80 = *((_QWORD *)this + 75);
LABEL_171:
                v76 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                      v80,
                                      4,
                                      L"%s(%d): Result = 0x%X",
                                      L"CDeploymentSession::GenerateDownloadList",
                                      lpString2,
                                      *(_QWORD *)cchCount2,
                                      v231,
                                      v232,
                                      v233,
                                      v234);
LABEL_160:
                if ( (int)v76 < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v76);
              }
LABEL_162:
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v76);
LABEL_163:
              DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
              goto LABEL_705;
            }
            v244 = 1;
            v78 = 0;
            LODWORD(v242) = 0;
          }
          if ( v78 && a5 && !v59 )
          {
            memset(v337, 0, sizeof(v337));
            v83 = 0;
            v245 = 0;
            v84 = *((_QWORD *)this + 75);
            if ( v84 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v84, 2, L"Validating payload file [%ws]", v64[3]);
            if ( v64[5] )
            {
              v85 = CDlpHelpersT<CEmptyType>::CalculateHash(lpFileName);
              v21 = v85;
              if ( v85 < 0 )
              {
                v88 = 2222;
LABEL_192:
                v89 = (unsigned int)v85;
LABEL_193:
                CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                  *((_QWORD *)this + 75),
                  v89,
                  L"CDeploymentSession::GenerateDownloadList",
                  v88);
                DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v245);
                goto LABEL_163;
              }
              v85 = CStringConvertT<unsigned long>::Base64Encode(v337, v86, v87, &v245);
              v21 = v85;
              if ( v85 < 0 )
              {
                v88 = 2223;
                goto LABEL_192;
              }
              v83 = (const WCHAR *)v245;
            }
            v90 = v64[5];
            if ( v90 )
            {
              if ( CompareStringW(0x409u, 1u, v83, -1, v90, -1) != 2 )
              {
                v92 = *((_QWORD *)this + 75);
                if ( v267 )
                {
                  if ( v92 )
                    CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v92,
                      3,
                      L"File hash doesn't match but file was not deleted in Test Mode.");
                }
                else
                {
                  if ( v92 )
                  {
                    lpString2 = v64[5];
                    CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v92,
                      2,
                      L"Deleting corrupt payload file. Actual hash: [%ws], Expected Hash: [%ws]",
                      v83);
                  }
                  if ( !DeleteFileW(lpFileName) )
                  {
                    v93 = GetLastError();
                    v21 = v93;
                    if ( v93 )
                    {
                      if ( v93 > 0 )
                        v21 = (unsigned __int16)v93 | 0x80070000;
                    }
                    else
                    {
                      v21 = -2147467259;
                    }
                    v88 = 2240;
                    v89 = (unsigned int)v21;
                    goto LABEL_193;
                  }
                  v244 = 1;
                  v78 = 0;
                  LODWORD(v242) = 0;
                }
              }
            }
            else
            {
              v91 = *((_QWORD *)this + 75);
              if ( v91 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v91,
                  3,
                  L"Expected hash not available; assuming hashless CompDB and skipping validation.");
            }
            DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v245);
          }
        }
        v94 = v238;
        v95 = *(_DWORD *)(v238 + 104);
        if ( v95 )
        {
          v96 = v95 - 1;
          if ( v96 )
          {
            v97 = v96 - 1;
            if ( v97 )
            {
              v98 = v97 - 2;
              if ( v98 )
              {
                v99 = v98 - 1;
                if ( v99 )
                {
                  if ( v99 != 1 )
                  {
                    v225 = (const char *)(unsigned int)EnsureNTSTATUS<long>(2147549183LL);
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x7B9,
                      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                      v225,
                      (int)lpString2);
                  }
                  v100 = L"Bundle";
                }
                else
                {
                  v100 = L"ReverseDiff";
                }
              }
              else
              {
                v100 = L"PSFX";
              }
            }
            else
            {
              v100 = L"Express";
            }
          }
          else
          {
            v100 = L"Diff";
          }
        }
        else
        {
          v100 = L"Canonical";
        }
        if ( v78 )
        {
          v101 = *((_QWORD *)this + 75);
          if ( v101 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v101, 2, L"File exists: [%ws]", v64[3]);
          if ( v254 + v326 < v254 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v254 += v326;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v102 = 2258;
            goto LABEL_234;
          }
        }
        else
        {
          v240 = 0;
          v104 = *(_DWORD *)(v238 + 104);
          if ( v104 )
          {
            v105 = v104 - 1;
            if ( v105 )
            {
              v106 = v105 - 1;
              if ( v106 )
              {
                v107 = v106 - 2;
                if ( v107 )
                {
                  v108 = v107 - 1;
                  if ( v108 )
                  {
                    if ( v108 != 1 )
                    {
                      v109 = 2310;
                      v21 = -2147418113;
LABEL_243:
                      v110 = (unsigned int)v21;
                      goto LABEL_254;
                    }
                  }
                  else
                  {
                    ++v243;
                    if ( !*((_QWORD *)this + 69) )
                    {
                      OuterContainerDownloadList = STRAPI_Create(v64[17], (wchar_t **)this + 69);
                      v21 = OuterContainerDownloadList;
                      if ( OuterContainerDownloadList < 0 )
                      {
                        v109 = 2290;
                        goto LABEL_253;
                      }
                    }
                  }
                }
              }
              else if ( !*((_QWORD *)this + 69) )
              {
                OuterContainerDownloadList = STRAPI_Create(v64[17], (wchar_t **)this + 69);
                v21 = OuterContainerDownloadList;
                if ( OuterContainerDownloadList < 0 )
                {
                  v109 = 2298;
                  goto LABEL_253;
                }
              }
            }
            else
            {
              ++v243;
              if ( !*((_QWORD *)this + 69) )
              {
                OuterContainerDownloadList = STRAPI_Create(v64[17], (wchar_t **)this + 69);
                v21 = OuterContainerDownloadList;
                if ( OuterContainerDownloadList < 0 )
                {
                  v109 = 2279;
                  goto LABEL_253;
                }
              }
            }
          }
          if ( (unsigned __int64)*v64 + v252 < v252 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v252 += (unsigned __int64)*v64;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v109 = 2314;
            goto LABEL_243;
          }
          v112 = *((_QWORD *)this + 75);
          if ( v64[6] )
          {
            if ( v112 )
            {
              v113 = L"TRUE";
              if ( !v235 )
                v113 = L"FALSE";
              v234 = (__int64)v64[2];
              v233 = (__int64)v64[7];
              v232 = (__int64)v64[8];
              v231 = (struct CDeploymentFileRequest **)v64[6];
              *(_QWORD *)cchCount2 = v64[3];
              LODWORD(lpString2) = *(_DWORD *)(v238 + 88);
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v112,
                2,
                L"Adding file: Optional = [%ws], Category = [%u], FileName = [%ws], Container = [%ws], Hash = [%ws], Cix ="
                 " [%ws], payloadName = [%ws]",
                v113);
            }
            OuterContainerDownloadList = CDeploymentSession::GenerateOuterContainerDownloadList(
                                           this,
                                           (const struct ActionList::Payload *const)v64,
                                           v100,
                                           v241);
            v21 = OuterContainerDownloadList;
            if ( OuterContainerDownloadList < 0 )
            {
              v109 = 2329;
              goto LABEL_253;
            }
          }
          else
          {
            if ( v112 )
            {
              v114 = L"TRUE";
              if ( !v235 )
                v114 = L"FALSE";
              LODWORD(lpString2) = *(_DWORD *)(v238 + 88);
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v112,
                2,
                L"Adding file: Optional = [%ws], Category = [%u], FileName = [%ws]",
                v114,
                lpString2,
                v64[3],
                v231,
                v232,
                v233,
                v234);
            }
            OuterContainerDownloadList = CDeploymentFileRequest::Create(
                                           v64[5],
                                           v64[3],
                                           v64[2],
                                           v64[4],
                                           v100,
                                           v235,
                                           &v240);
            v21 = OuterContainerDownloadList;
            if ( OuterContainerDownloadList < 0 )
            {
              v109 = 2344;
              goto LABEL_253;
            }
            v115 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v297, &v240);
            OuterContainerDownloadList = CDeploymentDownloadRequest::AppendFileRequest(v241, v115);
            v21 = OuterContainerDownloadList;
            if ( OuterContainerDownloadList < 0 )
            {
              v109 = 2345;
LABEL_253:
              v110 = (unsigned int)OuterContainerDownloadList;
LABEL_254:
              CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                *((_QWORD *)this + 75),
                v110,
                L"CDeploymentSession::GenerateDownloadList",
                v109);
              if ( v240 )
              {
                (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v240 + 16LL))(v240);
                v240 = 0;
              }
              goto LABEL_163;
            }
          }
          if ( v240 )
          {
            (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v240 + 16LL))(v240);
            v240 = 0;
          }
          v94 = v238;
        }
        if ( !v64[10] || !a5 || *(_DWORD *)(v94 + 104) != 2 )
          goto LABEL_301;
        SH_SSTRING::operator=(&lpFileName);
        v116 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), (__int64)v64[10], 0);
        v21 = v116;
        if ( v116 < 0 )
        {
          v102 = 2356;
LABEL_284:
          v103 = (unsigned int)v116;
          goto LABEL_235;
        }
        v116 = CMiscHelpersT<CEmptyType>::FileExists(lpFileName, &v242);
        v21 = v116;
        if ( v116 < 0 )
        {
          v102 = 2357;
          goto LABEL_284;
        }
        if ( (_DWORD)v242 )
        {
          v116 = CMoUpdateHelpersT<CEmptyType>::GetFileSize(lpFileName, &v326);
          v21 = v116;
          if ( v116 < 0 )
          {
            v102 = 2361;
            goto LABEL_284;
          }
          if ( v254 + v326 < v254 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v254 += v326;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v102 = 2362;
            goto LABEL_234;
          }
          v117 = 1;
          v237 = 1;
          if ( *((_BYTE *)v64 + 153) )
          {
            if ( v278 + v326 < v278 )
            {
              v21 = -2147024362;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            }
            else
            {
              v278 += v326;
              v21 = 0;
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
            if ( v21 < 0 )
            {
              v102 = 2367;
LABEL_234:
              v103 = (unsigned int)v21;
LABEL_235:
              CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                *((_QWORD *)this + 75),
                v103,
                L"CDeploymentSession::GenerateDownloadList",
                v102);
              goto LABEL_163;
            }
          }
        }
        else
        {
LABEL_301:
          v117 = v237;
        }
        if ( v250 && v64[14] && v64[9] && !v268 )
          break;
        v58 = v238;
LABEL_328:
        v271 = 0;
        v245 = 0;
        v242 = 0;
        if ( v250 )
          goto LABEL_394;
        v126 = *((_DWORD *)this + 114);
        if ( v126 > 0x16 )
          goto LABEL_394;
        v127 = 4195440;
        if ( !_bittest(&v127, v126) || *(_DWORD *)(v58 + 104) != 2 )
          goto LABEL_394;
        SH_SSTRING::operator=(&lpFileName);
        v116 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), (__int64)v64[2], 0);
        v21 = v116;
        if ( v116 < 0 )
        {
          v102 = 2433;
          goto LABEL_284;
        }
        v128 = -1;
        v129 = -1;
        do
          ++v129;
        while ( *(_WORD *)(*((_QWORD *)this + 61) + 2 * v129) );
        do
          ++v128;
        while ( lpFileName[v128] );
        v301[0] = *((_QWORD *)this + 61);
        v301[1] = v129;
        v292 = lpFileName;
        v293 = v128;
        v116 = CheckIfHistoryCixIsPresent(
                 (unsigned int)&v292,
                 (unsigned int)v301,
                 (unsigned int)&v271,
                 (unsigned int)&v245,
                 (__int64)&v242);
        v21 = v116;
        if ( v116 < 0 )
        {
          v102 = 2435;
          goto LABEL_284;
        }
        v130 = v245;
        if ( v245 )
        {
          v131 = v64[9];
          Src = 0;
          v330 = 0;
          v331 = 0;
          v132 = -1;
          do
            ++v132;
          while ( v131[v132] );
          std::wstring::_Construct<1,wchar_t const *>(&Src, v131);
          v308 = 0;
          v309 = 0;
          v310 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v308, L".historycix.cab");
          v305 = 0;
          v306 = 0;
          v307 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v305, L".psf");
          ReplaceAll<std::wstring>(&Src);
          std::wstring::~wstring(&v305);
          std::wstring::~wstring(&v308);
          if ( v130 + v252 < v252 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v252 += v130;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v133 = 2445;
            goto LABEL_347;
          }
          if ( v130 + v255 < v255 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v255 += v130;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v133 = 2446;
            goto LABEL_347;
          }
          if ( (unsigned __int64)v242 + v328 < v328 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v328 += (__int64)v242;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v133 = 2447;
LABEL_347:
            v134 = (unsigned int)v21;
LABEL_348:
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              v134,
              L"CDeploymentSession::GenerateDownloadList",
              v133);
            goto LABEL_349;
          }
          v135 = v64[11];
          p_Src = (const wchar_t *)&Src;
          if ( v331 > 7 )
            p_Src = (const wchar_t *)Src;
          v137 = 0;
          v288 = 0;
          v138 = v279[6];
          if ( v138 )
          {
            v139 = v279[8];
            OffsetInOuterContainer = CDeploymentSession::GetOffsetInOuterContainer(
                                       this,
                                       v138,
                                       0,
                                       v279[9],
                                       v279[14],
                                       &v288,
                                       0);
            v21 = OffsetInOuterContainer;
            if ( OffsetInOuterContainer < 0 )
            {
              v133 = 2464;
              v134 = (unsigned int)OffsetInOuterContainer;
              goto LABEL_348;
            }
            v137 = v288;
          }
          else
          {
            v139 = v279[5];
            v138 = v279[2];
          }
          v141 = *((_QWORD *)this + 75);
          if ( v141 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v141,
              2,
              L"    Adding HistoryCIX file: [%s] with Hash [%s]",
              p_Src,
              v139);
          v142 = *((_QWORD *)this + 75);
          if ( v142 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v142, 2, L"    Download size : [%llu]", v245);
          v143 = *((_QWORD *)this + 75);
          if ( v143 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v143, 2, L"    Expand size : [%llu]", v242);
          v242 = 0;
          v144 = CDeploymentFileRequest::Create(v139, p_Src, v138, v135, L"Express", v235, &v242);
          v21 = v144;
          if ( v144 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v144,
              L"CDeploymentSession::GenerateDownloadList",
              2483);
            goto LABEL_375;
          }
          v247 = 0;
          v146 = CDeploymentFileRange::Create(v137 + v271, v245, &v247);
          v21 = v146;
          if ( v146 < 0 )
          {
            v147 = 2486;
            goto LABEL_380;
          }
          v148 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v299, &v247);
          v149 = v242;
          appended = CDeploymentFileRequest::AppendExpressFileRange(v242, v148);
          v21 = appended;
          if ( appended < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)appended,
              L"CDeploymentSession::GenerateDownloadList",
              2487);
            if ( v247 )
            {
              (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v247 + 16LL))(v247);
              v247 = 0;
            }
            if ( v149 )
            {
              v145 = *(_QWORD *)v149;
LABEL_377:
              (*(void (**)(void))(v145 + 16))();
            }
            goto LABEL_349;
          }
          v151 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v300, &v242);
          v146 = CDeploymentDownloadRequest::AppendFileRequest(v241, v151);
          v21 = v146;
          if ( v146 < 0 )
          {
            v147 = 2489;
LABEL_380:
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v146,
              L"CDeploymentSession::GenerateDownloadList",
              v147);
            if ( v247 )
            {
              (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v247 + 16LL))(v247);
              v247 = 0;
            }
LABEL_375:
            if ( v242 )
            {
              v145 = *(_QWORD *)v242;
              goto LABEL_377;
            }
LABEL_349:
            std::wstring::~wstring(&Src);
            goto LABEL_163;
          }
          v38 = 1;
          if ( v247 )
          {
            (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v247 + 16LL))(v247);
            v247 = 0;
          }
          if ( v242 )
            (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v242 + 16LL))(v242);
          std::wstring::~wstring(&Src);
          DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
          v64 = v279;
          v58 = v238;
        }
        else
        {
LABEL_394:
          DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
        }
LABEL_395:
        v64 += 23;
        v65 = v289;
        v59 = v239;
        v56 = v255;
        v21 = 0;
      }
      v118 = v117 == 0;
      v58 = v238;
      if ( !v118 || *((_BYTE *)v64 + 153) || *(_DWORD *)(v238 + 104) != 2 )
        goto LABEL_328;
      v246 = 0;
      if ( !v64[8] || (v119 = v64 + 6, !v64[6]) )
      {
        v120 = CDeploymentFileRequest::Create(v64[14], v64[9], v64[9], v64[11], L"Canonical", v235, &v246);
        v21 = v120;
        if ( v120 >= 0 )
          goto LABEL_320;
        v121 = 2412;
LABEL_314:
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v120,
          L"CDeploymentSession::GenerateDownloadList",
          v121);
        if ( v246 )
        {
          (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v246 + 16LL))(v246);
          v246 = 0;
        }
        goto LABEL_163;
      }
      if ( !(unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::contains<wchar_t *>(
                               (char *)this + 768,
                               v64 + 6) )
      {
        v120 = CDeploymentFileRequest::Create(v64[8], *v119, *v119, 0, L"Canonical", v235, &v246);
        v21 = v120;
        if ( v120 < 0 )
        {
          v121 = 2397;
          goto LABEL_314;
        }
        v122 = *v119;
        v302 = 0;
        v303 = 0;
        v304 = 0;
        v123 = -1;
        do
          ++v123;
        while ( v122[v123] );
        std::wstring::_Construct<1,wchar_t const *>(&v302, v122);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
          (char *)this + 768,
          v314,
          &v302);
        std::wstring::~wstring(&v302);
      }
      v58 = v238;
LABEL_320:
      v124 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v298, &v246);
      v125 = v241;
      v120 = CDeploymentDownloadRequest::AppendFileRequest(v241, v124);
      v21 = v120;
      if ( v120 < 0 )
      {
        v121 = 2415;
        goto LABEL_314;
      }
      v21 = 0;
      if ( v246 )
      {
        (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v246 + 16LL))(v246);
        v246 = 0;
      }
      DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
LABEL_397:
      v152 = v262;
      if ( v262 <= v243 )
        v152 = v243;
      v262 = v152;
      if ( v250 || a5 || *(_DWORD *)(v58 + 104) != 2 || v38 )
      {
        v165 = v252;
        v159 = v235;
        v160 = v238;
      }
      else
      {
        v335 = 0;
        v334 = 0;
        v153 = *((_DWORD *)this + 114);
        if ( (v153 == 4 || (v154 = 1, v153 == 22))
          && (v154 = 0, v155 = *((_QWORD *)v253 + 11), v156 = v155 + 168LL * *((unsigned int *)v253 + 24), v155 != v156) )
        {
          while ( (unsigned int)_o__wcsicmp(*(_QWORD *)(v58 + 56), *(_QWORD *)(v155 + 56)) )
          {
            v155 += 168;
            if ( v155 == v156 )
              goto LABEL_410;
          }
LABEL_412:
          v157 = a6;
        }
        else
        {
          if ( v154 )
            goto LABEL_412;
LABEL_410:
          v157 = 1;
          v158 = *((_QWORD *)this + 75);
          if ( v158 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v158,
              2,
              L"Skipping ICbsServicingProcessor->WritePackageFileList PackageFilePath: [%ws]; must be repair content",
              *(_QWORD *)(v58 + 56));
        }
        v159 = v235;
        v160 = v238;
        ExpressDownloadList = CDeploymentSession::GenerateExpressDownloadList(
                                this,
                                v157,
                                (__int64)v336,
                                (__int64)v125,
                                (__int64)&v335,
                                (__int64)&v334,
                                (__int64)&v328,
                                (__int64)&v327);
        v21 = ExpressDownloadList;
        if ( ExpressDownloadList < 0 )
        {
          v162 = 2546;
LABEL_415:
          v163 = (unsigned int)ExpressDownloadList;
          goto LABEL_416;
        }
        v164 = v244;
        if ( (_DWORD)v327 )
          v164 = 1;
        v244 = v164;
        v165 = v252;
        if ( v252 + v335 < v252 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v165 = v252 + v335;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v162 = 2552;
          goto LABEL_424;
        }
        if ( v255 + v334 < v255 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v255 += v334;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v162 = 2553;
          goto LABEL_424;
        }
        v21 = 0;
      }
      if ( v165 + v264 < v264 )
      {
        v21 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
      }
      else
      {
        v264 += v165;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
      if ( v21 < 0 )
      {
        v162 = 2558;
        goto LABEL_424;
      }
      if ( v273 + v328 < v273 )
      {
        v21 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
      }
      else
      {
        v273 += v328;
        v21 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
      if ( v21 < 0 )
      {
        v162 = 2559;
        goto LABEL_424;
      }
      if ( v165 )
      {
        if ( v159 )
        {
          if ( v257 + 1 < v257 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            ++v257;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v162 = 2565;
            goto LABEL_424;
          }
        }
        else
        {
          if ( v256 + 1 < v256 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            ++v256;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v162 = 2569;
            goto LABEL_424;
          }
          if ( v165 + v248 < v248 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v248 += v165;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v162 = 2571;
            goto LABEL_424;
          }
          if ( v272 + v255 < v272 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v272 += v255;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v162 = 2572;
            goto LABEL_424;
          }
          if ( v249 + v328 < v249 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v249 += v328;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v162 = 2573;
            goto LABEL_424;
          }
        }
      }
      v166 = *(_DWORD *)(v160 + 88);
      if ( v166 > 7 )
      {
        v174 = v166 - 13;
        if ( !v174 )
        {
          v183 = *((_QWORD *)&v281 + 1);
          v184 = *((_QWORD *)&v281 + 1) + v248;
          if ( *((_QWORD *)&v281 + 1) + v248 < *((_QWORD *)&v281 + 1) )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            v184 = v183;
          }
          else
          {
            *((_QWORD *)&v281 + 1) += v248;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v162 = 2602;
            goto LABEL_424;
          }
          if ( v184 + v249 < v184 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            *((_QWORD *)&v281 + 1) = v184 + v249;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v162 = 2603;
            goto LABEL_424;
          }
          HIDWORD(v283) = v159;
          goto LABEL_545;
        }
        v175 = v174 - 1;
        if ( !v175 )
        {
          v181 = v282;
          v182 = v282 + v248;
          if ( (unsigned __int64)v282 + v248 < (unsigned __int64)v282 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            v182 = v181;
          }
          else
          {
            *(_QWORD *)&v282 = v282 + v248;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v162 = 2608;
            goto LABEL_424;
          }
          if ( v182 + v249 < v182 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            *(_QWORD *)&v282 = v182 + v249;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v162 = 2609;
            goto LABEL_424;
          }
          LODWORD(v284) = v159;
          goto LABEL_545;
        }
        v176 = v175 - 1;
        if ( !v176 )
        {
          v179 = *((_QWORD *)&v282 + 1);
          v180 = *((_QWORD *)&v282 + 1) + v248;
          if ( *((_QWORD *)&v282 + 1) + v248 < *((_QWORD *)&v282 + 1) )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            v180 = v179;
          }
          else
          {
            *((_QWORD *)&v282 + 1) += v248;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v162 = 2614;
            goto LABEL_424;
          }
          if ( v180 + v249 < v180 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            *((_QWORD *)&v282 + 1) = v180 + v249;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v162 = 2615;
            goto LABEL_424;
          }
          HIDWORD(v284) = v159;
          goto LABEL_545;
        }
        if ( v176 != 2 )
          goto LABEL_545;
LABEL_501:
        v177 = v281;
        v178 = v281 + v248;
        if ( (unsigned __int64)v281 + v248 < (unsigned __int64)v281 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          v178 = v177;
        }
        else
        {
          *(_QWORD *)&v281 = v281 + v248;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v162 = 2589;
          goto LABEL_424;
        }
        if ( v178 + v249 < v178 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          *(_QWORD *)&v281 = v178 + v249;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v162 = 2590;
          goto LABEL_424;
        }
        DWORD2(v283) = v159;
        goto LABEL_545;
      }
      if ( v166 == 7 )
        goto LABEL_475;
      v167 = v166 - 2;
      if ( !v167 || (v168 = v167 - 1) == 0 )
      {
        v172 = *((_QWORD *)&v280 + 1);
        v173 = *((_QWORD *)&v280 + 1) + v248;
        if ( *((_QWORD *)&v280 + 1) + v248 < *((_QWORD *)&v280 + 1) )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          v173 = v172;
        }
        else
        {
          *((_QWORD *)&v280 + 1) += v248;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v162 = 2596;
          goto LABEL_424;
        }
        if ( v173 + v249 < v173 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          *((_QWORD *)&v280 + 1) = v173 + v249;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v162 = 2597;
          goto LABEL_424;
        }
        DWORD1(v283) = v159;
        goto LABEL_545;
      }
      v169 = v168 - 1;
      if ( !v169 )
        goto LABEL_501;
      if ( (unsigned int)(v169 - 1) <= 1 )
      {
LABEL_475:
        v170 = v280;
        v171 = v280 + v248;
        if ( (unsigned __int64)v280 + v248 < (unsigned __int64)v280 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          v171 = v170;
        }
        else
        {
          *(_QWORD *)&v280 = v280 + v248;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v162 = 2582;
          goto LABEL_424;
        }
        if ( v171 + v249 < v171 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          *(_QWORD *)&v280 = v171 + v249;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v162 = 2583;
          goto LABEL_424;
        }
        LODWORD(v283) = v159;
      }
LABEL_545:
      v185 = *(_DWORD *)(v160 + 104);
      v38 = 0;
      if ( !v185 )
      {
        if ( v266 + v254 < v266 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v266 += v254;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 >= 0 )
        {
          if ( v258 + 1 < v258 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            ++v258;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 >= 0 )
            goto LABEL_109;
          v162 = 2624;
        }
        else
        {
          v162 = 2623;
        }
        goto LABEL_424;
      }
      v186 = v185 - 1;
      if ( !v186 )
        goto LABEL_550;
      v187 = v186 - 1;
      if ( !v187 )
      {
        v189 = v278;
        if ( v278 + v266 < v266 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v266 += v278;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 >= 0 )
        {
          v190 = v254;
          if ( v254 - v189 > v254 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v190 = v254 - v189;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 >= 0 )
          {
            if ( v190 + v275 < v275 )
            {
              v21 = -2147024362;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            }
            else
            {
              v275 += v190;
              v21 = 0;
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
            if ( v21 >= 0 )
            {
              if ( v261 + 1 < v261 )
              {
                v21 = -2147024362;
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
              }
              else
              {
                ++v261;
                v21 = 0;
              }
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
              if ( v21 >= 0 )
                goto LABEL_109;
              v162 = 2643;
            }
            else
            {
              v162 = 2642;
            }
          }
          else
          {
            v162 = 2640;
          }
        }
        else
        {
          v162 = 2639;
        }
        goto LABEL_424;
      }
      v188 = v187 - 2;
      if ( !v188 )
      {
        if ( v277 + v254 < v277 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v277 += v254;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 >= 0 )
        {
          if ( v259 + 1 < v259 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            ++v259;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 >= 0 )
            goto LABEL_109;
          v162 = 2629;
        }
        else
        {
          v162 = 2628;
        }
        goto LABEL_424;
      }
      if ( v188 == 1 )
      {
LABEL_550:
        if ( v276 + v254 < v276 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v276 += v254;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 >= 0 )
        {
          if ( v260 + 1 < v260 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            ++v260;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 >= 0 )
            goto LABEL_109;
          v162 = 2635;
        }
        else
        {
          v162 = 2634;
        }
LABEL_424:
        v163 = (unsigned int)v21;
LABEL_416:
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          v163,
          L"CDeploymentSession::GenerateDownloadList",
          v162);
        goto LABEL_705;
      }
LABEL_109:
      v53 = v265;
LABEL_110:
      v52 = v238 + 168;
    }
    v58 = v238;
LABEL_117:
    *((_DWORD *)this + 71) = 1;
    v59 = 1;
    v21 = 0;
    goto LABEL_118;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAFE,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v223);
  }
  return result;
}

```

## disassembly

```asm
0x18004f0b0  push    rbx
0x18004f0b2  push    rsi
0x18004f0b3  push    rdi
0x18004f0b4  push    r12
0x18004f0b6  push    r13
0x18004f0b8  push    r14
0x18004f0ba  push    r15
0x18004f0bc  sub     rsp, 400h
0x18004f0c3  mov     [rsp+438h+var_140], 0FFFFFFFFFFFFFFFEh
0x18004f0cf  mov     rax, cs:__security_cookie
0x18004f0d6  xor     rax, rsp
0x18004f0d9  mov     [rsp+438h+var_40], rax
0x18004f0e1  mov     r15d, r9d
0x18004f0e4  mov     [rsp+438h+var_2FC], r9d
0x18004f0ec  mov     r13d, r8d
0x18004f0ef  mov     [rsp+438h+var_368], r8d
0x18004f0f7  mov     r14, rdx
0x18004f0fa  mov     [rsp+438h+var_350], rdx
0x18004f102  mov     rsi, rcx
0x18004f105  mov     rdi, [rsp+438h+arg_30]
0x18004f10d  mov     rax, [rsp+438h+arg_40]
0x18004f115  mov     [rsp+438h+var_228], rax
0x18004f11d  mov     rax, [rsp+438h+arg_48]
0x18004f125  mov     [rsp+438h+var_230], rax
0x18004f12d  mov     rax, [rsp+438h+arg_50]
0x18004f135  mov     [rsp+438h+var_250], rax
0x18004f13d  mov     rax, [rsp+438h+arg_58]
0x18004f145  mov     [rsp+438h+var_248], rax
0x18004f14d  mov     r12, [rsp+438h+arg_60]
0x18004f155  mov     [rsp+438h+var_208], r12
0x18004f15d  mov     rbx, [rsp+438h+arg_68]
0x18004f165  mov     [rsp+438h+var_200], rbx
0x18004f16d  mov     rax, [rsp+438h+arg_70]
0x18004f175  mov     [rsp+438h+var_258], rax
0x18004f17d  xor     ecx, ecx
0x18004f17f  mov     [rsp+438h+var_3A8], rcx
0x18004f187  mov     [rsp+438h+var_360], rcx
0x18004f18f  mov     [rsp+438h+var_D0], ecx
0x18004f196  mov     [rsp+438h+var_300], ecx
0x18004f19d  xor     edx, edx; Val
0x18004f19f  lea     r8d, [rcx+48h]; Size
0x18004f1a3  lea     rcx, [rsp+438h+var_2A8]; void *
0x18004f1ab  call    memset_0
0x18004f1b0  xor     eax, eax
0x18004f1b2  mov     dword ptr [rsp+438h+var_C0], eax
0x18004f1b9  mov     [rsp+438h+var_70], rax
0x18004f1c1  mov     [rsp+438h+var_68], rax
0x18004f1c9  lea     ecx, [rax+40h]; Size
0x18004f1cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f1d1  mov     [rax], rax
0x18004f1d4  mov     [rax+8], rax
0x18004f1d8  mov     [rax+10h], rax
0x18004f1dc  mov     ecx, 1
0x18004f1e1  mov     word ptr [rax+18h], 101h
0x18004f1e7  mov     [rsp+438h+var_70], rax
0x18004f1ef  mov     [rsp+438h+var_158], rsi
0x18004f1f7  lea     rax, [rsp+438h+var_D0]
0x18004f1ff  mov     [rsp+438h+var_150], rax
0x18004f207  mov     [rsp+438h+var_148], cl
0x18004f20e  xor     edx, edx
0x18004f210  mov     rcx, [rsi+258h]
0x18004f217  test    r14, r14
0x18004f21a  jnz     short loc_18004F267
0x18004f21c  xor     r13d, r13d
0x18004f21f  mov     edi, 80070057h
0x18004f224  test    rcx, rcx
0x18004f227  jnz     short loc_18004F22E
0x18004f229  mov     ecx, r13d
0x18004f22c  jmp     short loc_18004F25D
0x18004f22e  mov     [rsp+438h+cchCount2], edi
0x18004f232  mov     dword ptr [rsp+438h+lpString2], 80Bh
0x18004f23a  lea     r9, aCdeploymentses_126; "CDeploymentSession::GenerateDownloadLis"...
0x18004f241  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18004f248  mov     edx, 4
0x18004f24d  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18004f252  mov     ecx, eax
0x18004f254  test    ecx, ecx
0x18004f256  jns     short loc_18004F25D
0x18004f258  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004f25d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004f262  jmp     loc_180052170
0x18004f267  cmp     [r14+48h], edx
0x18004f26b  jnz     short loc_18004F2A2
0x18004f26d  xor     r13d, r13d
0x18004f270  mov     edi, 0C1900401h
0x18004f275  test    rcx, rcx
0x18004f278  jz      short loc_18004F229
0x18004f27a  mov     [rsp+438h+cchCount2], edi
0x18004f27e  mov     dword ptr [rsp+438h+lpString2], 80Ch
0x18004f286  lea     r9, aCdeploymentses_126; "CDeploymentSession::GenerateDownloadLis"...
0x18004f28d  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18004f294  mov     edx, 4
0x18004f299  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18004f29e  mov     ecx, eax
0x18004f2a0  jmp     short loc_18004F254
0x18004f2a2  cmp     [r14+40h], rdx
0x18004f2a6  jnz     short loc_18004F2C7
0x18004f2a8  xor     r13d, r13d
0x18004f2ab  mov     edi, 80070057h
0x18004f2b0  test    rcx, rcx
0x18004f2b3  jz      loc_18004F229
0x18004f2b9  mov     [rsp+438h+cchCount2], edi
0x18004f2bd  mov     dword ptr [rsp+438h+lpString2], 80Dh
0x18004f2c5  jmp     short loc_18004F286
0x18004f2c7  test    rdi, rdi
0x18004f2ca  jnz     short loc_18004F2EB
0x18004f2cc  xor     r13d, r13d
0x18004f2cf  mov     edi, 80070057h
0x18004f2d4  test    rcx, rcx
0x18004f2d7  jz      loc_18004F229
0x18004f2dd  mov     [rsp+438h+cchCount2], edi
0x18004f2e1  mov     dword ptr [rsp+438h+lpString2], 80Eh
0x18004f2e9  jmp     short loc_18004F286
0x18004f2eb  cmp     [rsp+438h+var_228], rdx
0x18004f2f3  jnz     short loc_18004F317
0x18004f2f5  xor     r13d, r13d
0x18004f2f8  mov     edi, 80070057h
0x18004f2fd  test    rcx, rcx
0x18004f300  jz      loc_18004F229
0x18004f306  mov     [rsp+438h+cchCount2], edi
0x18004f30a  mov     dword ptr [rsp+438h+lpString2], 80Fh
0x18004f312  jmp     loc_18004F286
0x18004f317  cmp     [rsp+438h+var_230], rdx
0x18004f31f  jnz     short loc_18004F343
0x18004f321  xor     r13d, r13d
0x18004f324  mov     edi, 80070057h
0x18004f329  test    rcx, rcx
0x18004f32c  jz      loc_18004F229
0x18004f332  mov     [rsp+438h+cchCount2], edi
0x18004f336  mov     dword ptr [rsp+438h+lpString2], 810h
0x18004f33e  jmp     loc_18004F286
0x18004f343  cmp     [rsp+438h+var_250], rdx
0x18004f34b  jnz     short loc_18004F36F
0x18004f34d  xor     r13d, r13d
0x18004f350  mov     edi, 80070057h
0x18004f355  test    rcx, rcx
0x18004f358  jz      loc_18004F229
0x18004f35e  mov     [rsp+438h+cchCount2], edi
0x18004f362  mov     dword ptr [rsp+438h+lpString2], 811h
0x18004f36a  jmp     loc_18004F286
0x18004f36f  cmp     [rsp+438h+var_248], rdx
0x18004f377  jnz     short loc_18004F39B
0x18004f379  xor     r13d, r13d
0x18004f37c  mov     edi, 80070057h
0x18004f381  test    rcx, rcx
0x18004f384  jz      loc_18004F229
0x18004f38a  mov     [rsp+438h+cchCount2], edi
0x18004f38e  mov     dword ptr [rsp+438h+lpString2], 812h
0x18004f396  jmp     loc_18004F286
0x18004f39b  test    rbx, rbx
0x18004f39e  jnz     short loc_18004F3C2
0x18004f3a0  xor     r13d, r13d
0x18004f3a3  mov     edi, 80070057h
0x18004f3a8  test    rcx, rcx
0x18004f3ab  jz      loc_18004F229
0x18004f3b1  mov     [rsp+438h+cchCount2], edi
0x18004f3b5  mov     dword ptr [rsp+438h+lpString2], 813h
0x18004f3bd  jmp     loc_18004F286
0x18004f3c2  cmp     [rsp+438h+var_258], rdx
0x18004f3ca  jnz     short loc_18004F3EE
0x18004f3cc  xor     r13d, r13d
0x18004f3cf  mov     edi, 80070057h
0x18004f3d4  test    rcx, rcx
0x18004f3d7  jz      loc_18004F229
0x18004f3dd  mov     [rsp+438h+cchCount2], edi
0x18004f3e1  mov     dword ptr [rsp+438h+lpString2], 814h
0x18004f3e9  jmp     loc_18004F286
0x18004f3ee  test    r12, r12
0x18004f3f1  jnz     short loc_18004F415
0x18004f3f3  xor     r13d, r13d
0x18004f3f6  mov     edi, 80070057h
0x18004f3fb  test    rcx, rcx
0x18004f3fe  jz      loc_18004F229
0x18004f404  mov     [rsp+438h+cchCount2], edi
0x18004f408  mov     dword ptr [rsp+438h+lpString2], 815h
0x18004f410  jmp     loc_18004F286
0x18004f415  mov     ebx, [rsp+438h+arg_38]
0x18004f41c  mov     r12d, 2
0x18004f422  test    rcx, rcx
0x18004f425  jz      short loc_18004F439
0x18004f427  mov     r9d, ebx
0x18004f42a  lea     r8, aCreatingDownlo; "Creating Download request MaxPercentage"...
0x18004f431  mov     edx, r12d
0x18004f434  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18004f439  lea     r9, [rsp+438h+var_360]; struct CDeploymentDownloadRequest **
0x18004f441  mov     r8d, ebx; unsigned int
0x18004f444  mov     rdx, rdi; wchar_t *
0x18004f447  call    ?Create@CDeploymentDownloadRequest@@SAJPEB_W0KPEAPEAV1@@Z; CDeploymentDownloadRequest::Create(wchar_t const *,wchar_t const *,ulong,CDeploymentDownloadRequest * *)
0x18004f44c  mov     edi, eax
0x18004f44e  test    eax, eax
0x18004f450  jns     short loc_18004F4AF
0x18004f452  mov     rcx, [rsi+258h]
0x18004f459  xor     r13d, r13d
0x18004f45c  test    rcx, rcx
0x18004f45f  jnz     short loc_18004F466
0x18004f461  mov     ecx, r13d
0x18004f464  jmp     short loc_18004F495
0x18004f466  mov     [rsp+438h+cchCount2], eax
0x18004f46a  mov     dword ptr [rsp+438h+lpString2], 81Ah
0x18004f472  lea     r9, aCdeploymentses_126; "CDeploymentSession::GenerateDownloadLis"...
0x18004f479  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18004f480  mov     edx, 4
0x18004f485  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18004f48a  mov     ecx, eax
0x18004f48c  test    ecx, ecx
0x18004f48e  jns     short loc_18004F495
0x18004f490  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004f495  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004f49a  mov     rax, [rsp+438h+var_360]
0x18004f4a2  mov     [rsp+438h+var_3A8], rax
0x18004f4aa  jmp     loc_180052170
0x18004f4af  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Update_EcoQos@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Update_EcoQos@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos> `wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl(void)'::`2'::impl
0x18004f4b6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Update_EcoQos@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_IsEnabled(void)
0x18004f4bb  xor     edi, edi
0x18004f4bd  test    al, al
0x18004f4bf  jz      short loc_18004F4FA
0x18004f4c1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Update_EcoQos@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Update_EcoQos@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos> `wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl(void)'::`2'::impl
0x18004f4c8  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_Update_EcoQos@@@details@wil@@QEAA?AW4Variant_Update_EcoQos@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_GetVariant(wil::VariantReportingKind,bool)
0x18004f4cd  cmp     al, 1
0x18004f4cf  jnz     short loc_18004F4FA
0x18004f4d1  lea     rcx, aGeneratedownlo_18; "GenerateDownloadList: Enabling EcoQos f"...
0x18004f4d8  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x18004f4dd  mov     rcx, rsi; this
0x18004f4e0  call    ?SetEcoQos@CDeploymentSession@@AEAAJ_N@Z; CDeploymentSession::SetEcoQos(bool)
0x18004f4e5  test    eax, eax
0x18004f4e7  jns     short loc_18004F4FA
0x18004f4e9  lea     r8, aGeneratedownlo_5; "GenerateDownloadList: Error requesting "...
0x18004f4f0  mov     edx, eax
0x18004f4f2  mov     ecx, r12d
0x18004f4f5  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x18004f4fa  mov     [rsi+170h], r12d
0x18004f501  mov     ecx, [rsi+2E8h]
0x18004f507  sub     ecx, 1
0x18004f50a  jz      short loc_18004F51C
0x18004f50c  cmp     ecx, 1
0x18004f50f  jz      short loc_18004F515
0x18004f511  mov     ebx, edi
0x18004f513  jmp     short loc_18004F51F
0x18004f515  mov     ebx, 4
0x18004f51a  jmp     short loc_18004F51F
0x18004f51c  mov     ebx, r12d
0x18004f51f  cmp     [rsi+260h], rdi
0x18004f526  jz      loc_18004F64A
0x18004f52c  test    ebx, ebx
0x18004f52e  jz      short loc_18004F596
0x18004f530  lea     rcx, aGeneratedownlo_2; "GenerateDownloadList: Adjusting thread "...
0x18004f537  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x18004f53c  lea     r8, [rsp+438h+var_D0]
0x18004f544  mov     edx, ebx
0x18004f546  mov     rcx, rsi
0x18004f549  call    ?AdjustPriority@CDeploymentSession@@AEAAJW4WINDLP_PRIORITY@@PEAW42@@Z; CDeploymentSession::AdjustPriority(WINDLP_PRIORITY,WINDLP_PRIORITY *)
0x18004f54e  mov     edi, eax
0x18004f550  test    eax, eax
0x18004f552  jns     loc_18004F64A
0x18004f558  mov     rcx, [rsi+258h]
0x18004f55f  xor     r13d, r13d
0x18004f562  test    rcx, rcx
0x18004f565  jz      loc_18004F461
0x18004f56b  mov     [rsp+438h+cchCount2], eax
0x18004f56f  mov     dword ptr [rsp+438h+lpString2], 82Ch
0x18004f577  lea     r9, aCdeploymentses_126; "CDeploymentSession::GenerateDownloadLis"...
0x18004f57e  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18004f585  mov     edx, 4
0x18004f58a  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18004f58f  mov     ecx, eax
0x18004f591  jmp     loc_18004F48C
0x18004f596  mov     eax, [rsi+1C8h]
0x18004f59c  cmp     eax, 3
0x18004f59f  jz      short loc_18004F5AA
0x18004f5a1  cmp     eax, 18h
0x18004f5a4  jnz     loc_18004F64A
0x18004f5aa  lea     rcx, [rsi+18h]
0x18004f5ae  lea     rdx, [rsp+438h+var_2E8]
0x18004f5b6  call    ?GetUserSessionId@CDeploymentSession@@UEAA?AV?$optional@K@std@@XZ; CDeploymentSession::GetUserSessionId(void)
0x18004f5bb  lea     rax, aTrue_3; "TRUE"
0x18004f5c2  lea     r14, aFalse_2; "FALSE"
0x18004f5c9  mov     bl, byte ptr [rsp+438h+var_2E8+4]
0x18004f5d0  test    bl, bl
0x18004f5d2  cmovz   rax, r14
0x18004f5d6  mov     [rsp+438h+var_1F8], rax
0x18004f5de  lea     rdx, [rsp+438h+var_1F8]
0x18004f5e6  lea     rcx, aGeneratedownlo_10; "GenerateDownloadList: User session foun"...
0x18004f5ed  call    ??$TraceInfo@PEB_W@LogAdapter@@YAXQEBDAEBQEB_W@Z; LogAdapter::TraceInfo<wchar_t const *>(char const * const,wchar_t const * const &)
0x18004f5f2  test    bl, bl
0x18004f5f4  jnz     short loc_18004F642
0x18004f5f6  lea     rcx, aGeneratedownlo_2; "GenerateDownloadList: Adjusting thread "...
0x18004f5fd  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x18004f602  lea     r8, [rsp+438h+var_D0]
0x18004f60a  mov     edx, [rsi+170h]
0x18004f610  mov     rcx, rsi
0x18004f613  call    ?AdjustPriority@CDeploymentSession@@AEAAJW4WINDLP_PRIORITY@@PEAW42@@Z; CDeploymentSession::AdjustPriority(WINDLP_PRIORITY,WINDLP_PRIORITY *)
0x18004f618  mov     edi, eax
0x18004f61a  test    eax, eax
0x18004f61c  jns     short loc_18004F642
0x18004f61e  mov     rcx, [rsi+258h]
0x18004f625  xor     r13d, r13d
0x18004f628  test    rcx, rcx
0x18004f62b  jz      loc_18004F461
0x18004f631  mov     [rsp+438h+cchCount2], eax
0x18004f635  mov     dword ptr [rsp+438h+lpString2], 839h
  ... truncated ...
```
