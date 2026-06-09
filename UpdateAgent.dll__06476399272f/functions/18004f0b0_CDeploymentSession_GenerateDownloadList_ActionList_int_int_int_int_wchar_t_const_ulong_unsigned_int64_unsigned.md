# CDeploymentSession::GenerateDownloadList(ActionList *,int,int,int,int,wchar_t const *,ulong,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,_DUPackageInfo *,_ReportEventDownloadRequestParams *,IDeploymentDownloadRequest * *)

- ea: `0x18004f0b0`
- end: `0x18005220a`
- name: `?GenerateDownloadList@CDeploymentSession@@QEAAJPEAUActionList@@HHHHPEB_WKPEA_K222PEAU_DUPackageInfo@@PEAU_ReportEventDownloadRequestParams@@PEAPEAUIDeploymentDownloadRequest@@@Z`
- size: `12634`
- prototype: `__int64 __usercall@<rax>(CDeploymentSession *__hidden this@<rcx>, struct ActionList *@<rdx>, int@<r8d>, int@<r9d>, int, int, const wchar_t *, unsigned int, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, struct _DUPackageInfo *, struct _ReportEventDownloadRequestParams *, struct IDeploymentDownloadRequest **)`
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
// Hidden C++ exception states: #wind=20
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
  __int64 v42; // rax
  int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rcx
  int v46; // eax
  __int64 v47; // rbx
  HANDLE v48; // rax
  __int64 v49; // rax
  _OWORD *v50; // rcx
  __int64 v51; // rbx
  HANDLE v52; // rax
  __int64 v53; // rcx
  int *v54; // rdx
  unsigned int v55; // eax
  __int64 v56; // rcx
  unsigned __int64 v57; // r15
  int v58; // ecx
  __int64 v59; // r14
  char v60; // bl
  int v61; // eax
  __int64 v62; // rcx
  int *v63; // r8
  int *v64; // r9
  const wchar_t **v65; // r12
  const wchar_t **v66; // rax
  int v67; // eax
  __int64 v68; // rcx
  __int64 v69; // rcx
  LPCWSTR v70; // rbx
  HANDLE v71; // rax
  __int64 v72; // rcx
  LPCWSTR v73; // rbx
  HANDLE v74; // rax
  int v75; // eax
  __int64 v76; // rcx
  __int64 v77; // rcx
  DWORD FileAttributesW; // eax
  BOOL v79; // r14d
  int FileSize; // eax
  __int64 v81; // rcx
  __int64 v82; // rcx
  signed int LastError; // eax
  const WCHAR *v84; // rbx
  __int64 v85; // rcx
  int v86; // eax
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // r9
  __int64 v90; // rdx
  const WCHAR *v91; // rax
  __int64 v92; // rcx
  __int64 v93; // rcx
  signed int v94; // eax
  __int64 v95; // rbx
  int v96; // ecx
  int v97; // ecx
  int v98; // ecx
  int v99; // ecx
  int v100; // ecx
  const wchar_t *v101; // r15
  __int64 v102; // rcx
  __int64 v103; // r8
  __int64 v104; // r9
  __int64 v105; // r9
  __int64 v106; // rdx
  int v107; // ecx
  int v108; // ecx
  int v109; // ecx
  int v110; // ecx
  int v111; // ecx
  __int64 v112; // r9
  __int64 v113; // rdx
  int OuterContainerDownloadList; // eax
  __int64 v115; // rcx
  const wchar_t *v116; // r9
  const wchar_t *v117; // r9
  __int64 v118; // rax
  int v119; // eax
  char v120; // r14
  bool v121; // zf
  const wchar_t **v122; // rbx
  int v123; // eax
  __int64 v124; // r9
  const wchar_t *v125; // rdx
  __int64 v126; // r8
  __int64 v127; // rax
  CDeploymentDownloadRequest *v128; // r15
  unsigned int v129; // eax
  int v130; // ecx
  __int64 v131; // rax
  __int64 v132; // rdx
  unsigned __int64 v133; // rbx
  const wchar_t *v134; // rdx
  __int64 v135; // r8
  __int64 v136; // r9
  __int64 v137; // rdx
  const wchar_t *v138; // r13
  const wchar_t *p_Src; // r15
  unsigned __int64 v140; // r12
  const wchar_t *v141; // rbx
  const wchar_t *v142; // r14
  int OffsetInOuterContainer; // eax
  __int64 v144; // rcx
  __int64 v145; // rcx
  __int64 v146; // rcx
  int v147; // eax
  __int64 v148; // rax
  int v149; // eax
  __int64 v150; // r9
  __int64 v151; // rax
  struct CDeploymentFileRequest *v152; // rbx
  int appended; // eax
  __int64 v154; // rax
  unsigned int v155; // r11d
  int v156; // eax
  char v157; // cl
  __int64 v158; // rbx
  __int64 v159; // rdi
  int v160; // ebx
  __int64 v161; // rcx
  unsigned __int8 v162; // r14
  __int64 v163; // r13
  int ExpressDownloadList; // eax
  __int64 v165; // r9
  __int64 v166; // rdx
  int v167; // eax
  unsigned __int64 v168; // r15
  int v169; // ecx
  int v170; // ecx
  int v171; // ecx
  int v172; // ecx
  unsigned __int64 v173; // r15
  unsigned __int64 v174; // rbx
  unsigned __int64 v175; // r15
  unsigned __int64 v176; // rbx
  int v177; // ecx
  int v178; // ecx
  int v179; // ecx
  unsigned __int64 v180; // r15
  unsigned __int64 v181; // rbx
  unsigned __int64 v182; // r15
  unsigned __int64 v183; // rbx
  unsigned __int64 v184; // r15
  unsigned __int64 v185; // rbx
  unsigned __int64 v186; // r15
  unsigned __int64 v187; // rbx
  int v188; // ecx
  int v189; // ecx
  int v190; // ecx
  int v191; // ecx
  unsigned __int64 v192; // r14
  unsigned __int64 v193; // rbx
  int v194; // eax
  __int64 v195; // r9
  __int64 v196; // rcx
  unsigned int i; // r14d
  int v198; // eax
  int v199; // eax
  __int64 v200; // r9
  __int64 v201; // rcx
  __int64 v202; // rdx
  unsigned int j; // ebx
  int v204; // eax
  __int64 v205; // r9
  __int64 v206; // rcx
  __int64 v207; // rcx
  unsigned __int64 v208; // rbx
  __int64 v209; // rcx
  __int64 v210; // rcx
  __int64 v211; // rcx
  __int64 v212; // rcx
  CDeploymentDownloadRequest *v213; // r13
  int v214; // r15d
  struct ActionList *v215; // r12
  unsigned int v216; // eax
  char v217; // cl
  int v218; // r14d
  __int64 v219; // rbx
  const WCHAR *v220; // rax
  __int64 v221; // rcx
  unsigned int v222; // eax
  int *v223; // rax
  struct _DUPackageInfo *v224; // rax
  struct _ReportEventDownloadRequestParams *v225; // rcx
  const char *v226; // r9
  __int64 result; // rax
  const char *v228; // r9
  PCNZWCH lpString2; // [rsp+20h] [rbp-418h]
  int lpString2a; // [rsp+20h] [rbp-418h]
  int cchCount2[2]; // [rsp+28h] [rbp-410h]
  int cchCount2a; // [rsp+28h] [rbp-410h]
  int cchCount2b; // [rsp+28h] [rbp-410h]
  struct CDeploymentFileRequest **v234; // [rsp+30h] [rbp-408h]
  __int64 v235; // [rsp+38h] [rbp-400h]
  __int64 v236; // [rsp+40h] [rbp-3F8h]
  __int64 v237; // [rsp+48h] [rbp-3F0h]
  unsigned __int8 v238; // [rsp+60h] [rbp-3D8h]
  LPCWSTR lpFileName; // [rsp+68h] [rbp-3D0h] BYREF
  char v240; // [rsp+70h] [rbp-3C8h]
  __int64 v241; // [rsp+78h] [rbp-3C0h]
  char v242; // [rsp+80h] [rbp-3B8h]
  struct CDeploymentFileRequest *v243; // [rsp+88h] [rbp-3B0h] BYREF
  CDeploymentDownloadRequest *v244; // [rsp+90h] [rbp-3A8h]
  struct CDeploymentFileRequest *v245; // [rsp+98h] [rbp-3A0h] BYREF
  unsigned int v246; // [rsp+A0h] [rbp-398h]
  int v247; // [rsp+A4h] [rbp-394h]
  unsigned __int64 v248; // [rsp+A8h] [rbp-390h] BYREF
  struct CDeploymentFileRequest *v249; // [rsp+B0h] [rbp-388h] BYREF
  struct CDeploymentFileRange *v250; // [rsp+B8h] [rbp-380h] BYREF
  unsigned __int64 v251; // [rsp+C0h] [rbp-378h]
  unsigned __int64 v252; // [rsp+C8h] [rbp-370h]
  int v253; // [rsp+D0h] [rbp-368h]
  struct CDeploymentDownloadRequest *v254; // [rsp+D8h] [rbp-360h] BYREF
  unsigned __int64 v255; // [rsp+E0h] [rbp-358h]
  struct ActionList *v256; // [rsp+E8h] [rbp-350h]
  unsigned __int64 v257; // [rsp+F0h] [rbp-348h]
  unsigned __int64 v258; // [rsp+F8h] [rbp-340h]
  unsigned int v259; // [rsp+100h] [rbp-338h]
  unsigned int v260; // [rsp+104h] [rbp-334h]
  unsigned int v261; // [rsp+108h] [rbp-330h]
  unsigned int v262; // [rsp+10Ch] [rbp-32Ch]
  unsigned int v263; // [rsp+110h] [rbp-328h]
  unsigned int v264; // [rsp+114h] [rbp-324h]
  unsigned int v265; // [rsp+118h] [rbp-320h]
  unsigned int v266; // [rsp+11Ch] [rbp-31Ch]
  unsigned __int64 v267; // [rsp+120h] [rbp-318h]
  int *v268; // [rsp+128h] [rbp-310h]
  unsigned __int64 v269; // [rsp+130h] [rbp-308h]
  int v270; // [rsp+138h] [rbp-300h] BYREF
  DWORD v271; // [rsp+13Ch] [rbp-2FCh]
  int v272; // [rsp+140h] [rbp-2F8h] BYREF
  char v273; // [rsp+144h] [rbp-2F4h] BYREF
  __int64 v274; // [rsp+148h] [rbp-2F0h] BYREF
  unsigned __int64 v275; // [rsp+150h] [rbp-2E8h] BYREF
  unsigned __int64 v276; // [rsp+158h] [rbp-2E0h]
  __int64 v277; // [rsp+160h] [rbp-2D8h] BYREF
  unsigned __int64 v278; // [rsp+168h] [rbp-2D0h]
  unsigned __int64 v279; // [rsp+170h] [rbp-2C8h]
  unsigned __int64 v280; // [rsp+178h] [rbp-2C0h]
  unsigned __int64 v281; // [rsp+180h] [rbp-2B8h]
  const wchar_t **v282; // [rsp+188h] [rbp-2B0h]
  __int128 v283; // [rsp+190h] [rbp-2A8h] BYREF
  __int128 v284; // [rsp+1A0h] [rbp-298h]
  __int128 v285; // [rsp+1B0h] [rbp-288h]
  __int128 v286; // [rsp+1C0h] [rbp-278h]
  __int64 v287; // [rsp+1D0h] [rbp-268h]
  struct IDeploymentDownloadRequest **v288; // [rsp+1E0h] [rbp-258h]
  unsigned __int64 *v289; // [rsp+1E8h] [rbp-250h]
  unsigned __int64 *v290; // [rsp+1F0h] [rbp-248h]
  unsigned __int64 v291; // [rsp+1F8h] [rbp-240h] BYREF
  const wchar_t **v292; // [rsp+200h] [rbp-238h]
  unsigned __int64 *v293; // [rsp+208h] [rbp-230h]
  unsigned __int64 *v294; // [rsp+210h] [rbp-228h]
  LPCWSTR v295; // [rsp+220h] [rbp-218h] BYREF
  __int64 v296; // [rsp+228h] [rbp-210h]
  struct _DUPackageInfo *v297; // [rsp+230h] [rbp-208h]
  struct _ReportEventDownloadRequestParams *v298; // [rsp+238h] [rbp-200h]
  const wchar_t *v299; // [rsp+240h] [rbp-1F8h] BYREF
  char v300[8]; // [rsp+248h] [rbp-1F0h] BYREF
  char v301[8]; // [rsp+250h] [rbp-1E8h] BYREF
  char v302[8]; // [rsp+258h] [rbp-1E0h] BYREF
  char v303[16]; // [rsp+260h] [rbp-1D8h] BYREF
  _QWORD v304[2]; // [rsp+270h] [rbp-1C8h] BYREF
  __int128 v305; // [rsp+280h] [rbp-1B8h] BYREF
  __int64 v306; // [rsp+290h] [rbp-1A8h]
  __int64 v307; // [rsp+298h] [rbp-1A0h]
  __int128 v308; // [rsp+2A0h] [rbp-198h] BYREF
  __int64 v309; // [rsp+2B0h] [rbp-188h]
  __int64 v310; // [rsp+2B8h] [rbp-180h]
  __int128 v311; // [rsp+2C0h] [rbp-178h] BYREF
  __int64 v312; // [rsp+2D0h] [rbp-168h]
  __int64 v313; // [rsp+2D8h] [rbp-160h]
  _QWORD v314[2]; // [rsp+2E0h] [rbp-158h] BYREF
  char v315; // [rsp+2F0h] [rbp-148h]
  __int64 v316; // [rsp+2F8h] [rbp-140h]
  char v317[16]; // [rsp+300h] [rbp-138h] BYREF
  _BYTE v318[32]; // [rsp+310h] [rbp-128h] BYREF
  LPVOID v319; // [rsp+330h] [rbp-108h] BYREF
  LPVOID pv; // [rsp+338h] [rbp-100h] BYREF
  __int64 v321; // [rsp+340h] [rbp-F8h] BYREF
  __int64 v322; // [rsp+348h] [rbp-F0h] BYREF
  __int64 v323; // [rsp+350h] [rbp-E8h] BYREF
  __int64 v324; // [rsp+358h] [rbp-E0h] BYREF
  unsigned int v325; // [rsp+360h] [rbp-D8h] BYREF
  unsigned int v326; // [rsp+364h] [rbp-D4h] BYREF
  int v327; // [rsp+368h] [rbp-D0h] BYREF
  int v328; // [rsp+36Ch] [rbp-CCh] BYREF
  __int64 v329; // [rsp+370h] [rbp-C8h] BYREF
  __int64 v330; // [rsp+378h] [rbp-C0h] BYREF
  __int64 v331; // [rsp+380h] [rbp-B8h] BYREF
  __int128 Src; // [rsp+388h] [rbp-B0h] BYREF
  __int64 v333; // [rsp+398h] [rbp-A0h]
  unsigned __int64 v334; // [rsp+3A0h] [rbp-98h]
  __int64 v335; // [rsp+3A8h] [rbp-90h] BYREF
  __int64 v336; // [rsp+3B0h] [rbp-88h] BYREF
  __int64 v337; // [rsp+3B8h] [rbp-80h] BYREF
  __int64 v338; // [rsp+3C0h] [rbp-78h] BYREF
  __int64 v339[2]; // [rsp+3C8h] [rbp-70h] BYREF
  _OWORD v340[2]; // [rsp+3D8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+0h]

  v316 = -2;
  v271 = a4;
  v253 = a3;
  v17 = a2;
  v256 = a2;
  v294 = a9;
  v293 = a10;
  v289 = a11;
  v290 = a12;
  v297 = a13;
  v298 = a14;
  v288 = a15;
  v244 = 0;
  v254 = 0;
  v327 = 0;
  v270 = 0;
  memset_0(&v283, 0, 0x48u);
  LODWORD(v330) = 0;
  v339[0] = 0;
  v339[1] = 0;
  try
  {
    v19 = operator new(0x40u);
    *v19 = v19;
    v19[1] = v19;
    v19[2] = v19;
    *((_WORD *)v19 + 12) = 257;
    v339[0] = (__int64)v19;
    v314[0] = this;
    v314[1] = &v327;
    v315 = 1;
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
    if ( !v294 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2063;
      goto LABEL_12;
    }
    if ( !v293 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2064;
      goto LABEL_12;
    }
    if ( !v289 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2065;
      goto LABEL_12;
    }
    if ( !v290 )
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
    if ( !v288 )
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
    v23 = CDeploymentDownloadRequest::Create(v20, a7, a8, &v254);
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
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_GetVariant(&`wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl'::`2'::impl) == 1 )
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
        v29 = CDeploymentSession::AdjustPriority(this, v28, &v327);
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
          CDeploymentSession::GetUserSessionId((char *)this + 24, &v275);
          v32 = L"TRUE";
          v33 = BYTE4(v275);
          if ( !BYTE4(v275) )
            v32 = L"FALSE";
          v299 = v32;
          LogAdapter::TraceInfo<wchar_t const *>("GenerateDownloadList: User session found = [{}].", &v299);
          if ( !v33 )
          {
            LogAdapter::TraceInfo<>("GenerateDownloadList: Adjusting thread priority...");
            v34 = CDeploymentSession::AdjustPriority(this, *((unsigned int *)this + 92), &v327);
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
          v17 = v256;
        }
      }
    }
    v21 = CMoUpdateHelpersT<CEmptyType>::IsSkipDeleteCorruptFile(&v270);
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
      v277 = 0;
      v42 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&v277);
      v43 = CMiscHelpersT<CEmptyType>::CombinePath(
              *((_QWORD *)this + 61),
              *(_QWORD *)(*(_QWORD *)(v40 + 112) + 24LL),
              0,
              v42);
      v21 = v43;
      if ( v43 < 0 )
      {
        v44 = *((_QWORD *)this + 75);
        if ( v44 )
        {
          LODWORD(lpString2) = 2133;
          v46 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v44,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDeploymentSession::GenerateDownloadList",
                  lpString2,
                  v43);
          v45 = (unsigned int)v46;
          if ( v46 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v46);
        }
        else
        {
          v45 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v45);
        v47 = v277;
        if ( v277 )
        {
          v48 = GetProcessHeap();
          HeapFree(v48, 0, (LPVOID)(v47 - 4));
          v25 = 0;
          goto LABEL_48;
        }
LABEL_49:
        v244 = v254;
        goto LABEL_705;
      }
      v49 = to_wstring(v318, v277);
      v50 = (_OWORD *)((char *)this + 96);
      if ( *((_BYTE *)this + 128) )
      {
        std::wstring::operator=(v50, v49);
      }
      else
      {
        *v50 = 0;
        *((_QWORD *)this + 14) = 0;
        *((_QWORD *)this + 15) = 0;
        *v50 = *(_OWORD *)v49;
        *((_OWORD *)this + 7) = *(_OWORD *)(v49 + 16);
        *(_QWORD *)(v49 + 16) = 0;
        *(_QWORD *)(v49 + 24) = 7;
        *(_WORD *)v49 = 0;
        *((_BYTE *)this + 128) = 1;
      }
      std::wstring::~wstring(v318);
      v51 = v277;
      if ( v277 )
      {
        v52 = GetProcessHeap();
        HeapFree(v52, 0, (LPVOID)(v51 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
    }
LABEL_104:
    v267 = 0;
    v276 = 0;
    v251 = 0;
    v275 = 0;
    v252 = 0;
    v247 = 0;
    v259 = 0;
    v260 = 0;
    v269 = 0;
    v280 = 0;
    v279 = 0;
    v278 = 0;
    v261 = 0;
    v262 = 0;
    v263 = 0;
    v264 = 0;
    v265 = 0;
    v266 = 0;
    v53 = *((_QWORD *)v17 + 8);
    v54 = (int *)(v53 + 168LL * *((unsigned int *)v17 + 18));
    v268 = v54;
    v244 = v254;
    while ( 1 )
    {
      v241 = v53;
      if ( (int *)v53 == v54 )
      {
        if ( *((_DWORD *)this + 66) && *((_DWORD *)this + 67) )
          *((_DWORD *)this + 66) = 0;
        v321 = 0;
        v326 = 0;
        v194 = (*(__int64 (__fastcall **)(CDeploymentDownloadRequest *, __int64 *))(*(_QWORD *)v244 + 40LL))(
                 v244,
                 &v321);
        v21 = v194;
        if ( v194 < 0 )
        {
          v195 = 2660;
          v196 = *((_QWORD *)this + 75);
LABEL_605:
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            v196,
            (unsigned int)v194,
            L"CDeploymentSession::GenerateDownloadList",
            v195);
          goto LABEL_606;
        }
        v194 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v321 + 24LL))(v321, &v326);
        v21 = v194;
        v196 = *((_QWORD *)this + 75);
        if ( v194 < 0 )
        {
          v195 = 2661;
          goto LABEL_605;
        }
        if ( v196 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v196, 1, L"Total file requests: [%lu]", v326);
        for ( i = 0; i < v326; ++i )
        {
          v322 = 0;
          v323 = 0;
          v319 = 0;
          pv = 0;
          v325 = 0;
          v198 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v321 + 32LL))(v321, i, &v322);
          v21 = v198;
          if ( v198 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v198,
              L"CDeploymentSession::GenerateDownloadList",
              2673);
            goto LABEL_615;
          }
          v199 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v322 + 24LL))(v322, &v319);
          v21 = v199;
          if ( v199 < 0 )
          {
            v200 = 2674;
            goto LABEL_622;
          }
          v21 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v322 + 40LL))(v322, &pv);
          if ( v21 < 0 )
          {
            v200 = 2675;
            v202 = (unsigned int)v21;
            v201 = *((_QWORD *)this + 75);
            goto LABEL_624;
          }
          if ( *((_QWORD *)this + 75) )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(*((_QWORD *)this + 75), 1, L"Requested file: %ws, hash: %ws");
          v199 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v322 + 48LL))(v322, &v323);
          v21 = v199;
          if ( v199 < 0 )
          {
            v200 = 2680;
LABEL_622:
            v201 = *((_QWORD *)this + 75);
            goto LABEL_623;
          }
          v199 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v323 + 24LL))(v323, &v325);
          v21 = v199;
          v201 = *((_QWORD *)this + 75);
          if ( v199 < 0 )
          {
            v200 = 2681;
LABEL_623:
            v202 = (unsigned int)v199;
LABEL_624:
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(v201, v202, L"CDeploymentSession::GenerateDownloadList", v200);
            goto LABEL_615;
          }
          if ( v201 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v201, 1, L"  Total range requests for file: [%lu]", v325);
          for ( j = 0; j < v325; ++j )
          {
            v324 = 0;
            v336 = 0;
            v335 = 0;
            v204 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v323 + 32LL))(v323, j, &v324);
            v21 = v204;
            if ( v204 < 0 )
            {
              v205 = 2691;
LABEL_639:
              v206 = *((_QWORD *)this + 75);
              goto LABEL_640;
            }
            v204 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v324 + 24LL))(v324, &v336);
            v21 = v204;
            if ( v204 < 0 )
            {
              v205 = 2692;
              goto LABEL_639;
            }
            v204 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v324 + 32LL))(v324, &v335);
            v21 = v204;
            v206 = *((_QWORD *)this + 75);
            if ( v204 < 0 )
            {
              v205 = 2693;
LABEL_640:
              CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                v206,
                (unsigned int)v204,
                L"CDeploymentSession::GenerateDownloadList",
                v205);
              SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v324);
LABEL_615:
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              if ( v319 )
              {
                CoTaskMemFree(v319);
                v319 = 0;
              }
              SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v323);
              SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v322);
LABEL_606:
              SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v321);
              goto LABEL_705;
            }
            if ( v206 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v206,
                1,
                L"  Requested range #%llu offset: %llu, length: %llu",
                j,
                v336,
                v335);
            SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v324);
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( v319 )
          {
            CoTaskMemFree(v319);
            v319 = 0;
          }
          SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v323);
          SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v322);
        }
        SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v321);
        v207 = *((_QWORD *)this + 75);
        v208 = v267;
        if ( v207 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v207, 2, L"Required size of the Download: [%llu]", v267);
        v209 = *((_QWORD *)this + 75);
        if ( v209 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v209, 2, L"Total Expanded size : [%llu]", v276);
        v210 = *((_QWORD *)this + 75);
        if ( v210 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v210, 2, L"Required size of the required Download: [%llu]", v251);
        v211 = *((_QWORD *)this + 75);
        if ( v211 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v211, 2, L"Required Expanded size : [%llu]", v252);
        v212 = *((_QWORD *)this + 75);
        if ( v212 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v212, 2, L"Setting total size of the Request: [%llu]", v208);
        v213 = v244;
        ExpressDownloadList = CDeploymentDownloadRequest::SetTotalRequestSize(v244, v208, v253 == 0);
        v21 = ExpressDownloadList;
        if ( ExpressDownloadList < 0 )
        {
          v165 = 2705;
          goto LABEL_415;
        }
        v214 = 0;
        if ( v208 )
        {
          *((_QWORD *)this + 47) = v208;
          goto LABEL_667;
        }
        v216 = *((_DWORD *)this + 114);
        if ( v216 == 25 || v216 == 4 || (v217 = 0, v216 == 22) )
          v217 = 1;
        if ( (*((_BYTE *)this + 372) & 0x20) != 0 && v216 <= 0x18 )
        {
          v218 = 20971544;
          if ( !_bittest(&v218, v216) )
            goto LABEL_677;
          goto LABEL_679;
        }
        v218 = 20971544;
LABEL_677:
        if ( *((int *)this + 83) < 2 && *((_BYTE *)this + 128) )
LABEL_679:
          v217 = 0;
        if ( *((_BYTE *)this + 336) || !v217 )
        {
LABEL_667:
          v215 = v256;
        }
        else
        {
          v219 = *((_QWORD *)this + 58);
          if ( *((_DWORD *)this + 83) == 2 && *((_BYTE *)this + 128) )
          {
            v220 = (const WCHAR *)((char *)this + 96);
            v221 = *((_QWORD *)this + 14);
            if ( *((_QWORD *)this + 15) > 7u )
              v220 = *(const WCHAR **)v220;
            v295 = v220;
            v296 = v221;
            std::optional<std::wstring>::operator=<wil::basic_zstring_view<wchar_t> &,0>(v219 + 136, &v295);
          }
          v215 = v256;
          if ( !*((_DWORD *)this + 57) )
          {
            ExpressDownloadList = CDeploymentSession::Expand(this, v256);
            v21 = ExpressDownloadList;
            if ( ExpressDownloadList < 0 )
            {
              v165 = 2750;
              goto LABEL_415;
            }
          }
          if ( *((_DWORD *)v215 + 60) && (v222 = *((_DWORD *)this + 114), v222 <= 0x18) && _bittest(&v218, v222) )
          {
            ExpressDownloadList = CDeploymentSession::ComposePayloads(this, v215);
            v21 = ExpressDownloadList;
            v214 = 1;
            if ( ExpressDownloadList < 0 )
            {
              v165 = 2758;
              goto LABEL_415;
            }
          }
          else
          {
            v214 = 0;
          }
          v328 = 0;
          v272 = -2145116147;
          v21 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v219 + 200LL))(
                  v219,
                  4096,
                  *((_QWORD *)this + 63),
                  &v328);
          v223 = &v272;
          do
          {
            if ( v21 == *v223 )
            {
              v21 = 0;
              goto LABEL_702;
            }
            ++v223;
          }
          while ( v223 != (int *)&v273 );
          if ( v21 >= 0 )
LABEL_702:
            *((_BYTE *)this + 336) = 1;
          v208 = v267;
        }
        v224 = v297;
        *(_OWORD *)v297 = v283;
        *((_OWORD *)v224 + 1) = v284;
        *((_OWORD *)v224 + 2) = v285;
        *((_OWORD *)v224 + 3) = v286;
        *((_QWORD *)v224 + 8) = v287;
        *v294 = v208;
        *v293 = v276;
        *v289 = v251;
        *v290 = v252;
        v225 = v298;
        *((_DWORD *)v298 + 33) = v214;
        *((_DWORD *)v225 + 6) = v247;
        *((_DWORD *)v225 + 28) = *((_DWORD *)this + 87);
        *((_DWORD *)v225 + 12) = *((_DWORD *)v215 + 18);
        *((_DWORD *)v225 + 13) = v259;
        *((_DWORD *)v225 + 14) = v260;
        *((_QWORD *)v225 + 8) = v269;
        *((_QWORD *)v225 + 9) = v280;
        *((_QWORD *)v225 + 10) = v279;
        *((_QWORD *)v225 + 11) = v278;
        *((_DWORD *)v225 + 24) = v261;
        *((_DWORD *)v225 + 25) = v262;
        *((_DWORD *)v225 + 26) = v263;
        *((_DWORD *)v225 + 27) = v264;
        *((_DWORD *)v225 + 32) = v265;
        *((_DWORD *)v225 + 34) = v266;
        v244 = 0;
        *v288 = v213;
        goto LABEL_705;
      }
      v331 = 0;
      v55 = *(_DWORD *)(v53 + 88);
      if ( v55 == 24 )
      {
        v56 = *((_QWORD *)this + 75);
        if ( !v56 )
          goto LABEL_110;
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v56,
          2,
          L"Skipping UUP Product package download from ActionList [%ws]",
          *(_QWORD *)(v241 + 56));
        goto LABEL_109;
      }
      v255 = 0;
      v57 = 0;
      v258 = 0;
      v257 = 0;
      v281 = 0;
      v246 = 0;
      v240 = 0;
      if ( v55 <= 0xF )
      {
        v58 = 36992;
        if ( _bittest(&v58, v55) )
          break;
      }
      v59 = v241;
      if ( *(_DWORD *)(v241 + 104) == 2 || *((_DWORD *)this + 114) == 8 )
        goto LABEL_117;
      v21 = 0;
      v60 = 0;
LABEL_118:
      v242 = v60;
      v61 = *((_DWORD *)this + 114);
      if ( (v61 == 3 || v61 == 24)
        && ((v62 = *((_QWORD *)this + 49)) != 0
          ? (v63 = (int *)*((_QWORD *)this + 49), v54 = v63)
          : (v62 = 0, v63 = 0, v54 = 0),
            v64 = (int *)(v62 + 4LL * *((int *)this + 97)),
            v63 != v64) )
      {
        while ( *(_DWORD *)(v59 + 88) != *v54 )
        {
          if ( ++v54 == v64 )
            goto LABEL_126;
        }
        v238 = 1;
      }
      else
      {
LABEL_126:
        v238 = 0;
      }
      v65 = *(const wchar_t ***)(v59 + 112);
      v66 = &v65[23 * *(unsigned int *)(v59 + 120)];
      v292 = v66;
      while ( 1 )
      {
        v282 = v65;
        if ( v65 == v66 )
        {
          v128 = v244;
          goto LABEL_397;
        }
        lpFileName = 0;
        v329 = 0;
        v67 = CDeploymentSession::CheckCancelRequested(this, v54);
        v21 = v67;
        if ( v67 < 0 )
        {
          v68 = *((_QWORD *)this + 75);
          if ( !v68 )
            goto LABEL_131;
          cchCount2[0] = v67;
          LODWORD(lpString2) = 2177;
          v69 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v68,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GenerateDownloadList",
                                lpString2,
                                *(_QWORD *)cchCount2);
LABEL_134:
          if ( (int)v69 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v69);
          goto LABEL_136;
        }
        if ( (unsigned int)(*(_DWORD *)(v59 + 88) - 5) <= 1 )
        {
          if ( v266 + 1 < v266 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            ++v266;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v72 = *((_QWORD *)this + 75);
            if ( v72 )
            {
              cchCount2[0] = v21;
              LODWORD(lpString2) = 2181;
              goto LABEL_145;
            }
LABEL_131:
            v69 = 0;
LABEL_136:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v69);
            v70 = lpFileName;
            if ( lpFileName )
            {
              v71 = GetProcessHeap();
              HeapFree(v71, 0, (LPVOID)(v70 - 2));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              lpFileName = 0;
            }
LABEL_705:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
            __1__lambda_call_V_lambda_1___2__GenerateDownloadList_CDeploymentSession__QEAAJPEAUActionList__HHHHPEB_WKPEA_K222PEAU_DUPackageInfo__PEAU_ReportEventDownloadRequestParams__PEAPEAUIDeploymentDownloadRequest___Z__details_wil__QEAA_XZ(v314);
            std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v339);
            if ( v244 )
              (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v244 + 16LL))(v244);
            return (unsigned int)v21;
          }
        }
        if ( (unsigned __int64)*v65 + v57 < v57 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v258 = (unsigned __int64)*v65 + v57;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v72 = *((_QWORD *)this + 75);
          if ( !v72 )
            goto LABEL_131;
          cchCount2[0] = v21;
          LODWORD(lpString2) = 2184;
LABEL_145:
          v69 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v72,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GenerateDownloadList",
                                lpString2,
                                *(_QWORD *)cchCount2,
                                v234,
                                v235,
                                v236,
                                v237);
          goto LABEL_134;
        }
        if ( v253 && !v60 )
        {
          v73 = lpFileName;
          if ( lpFileName )
          {
            v74 = GetProcessHeap();
            HeapFree(v74, 0, (LPVOID)(v73 - 2));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            lpFileName = 0;
          }
          goto LABEL_395;
        }
        v75 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v65[3], 0, &lpFileName);
        v21 = v75;
        if ( v75 < 0 )
        {
          v76 = *((_QWORD *)this + 75);
          if ( v76 )
          {
            cchCount2[0] = v75;
            LODWORD(lpString2) = 2196;
            v77 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                  v76,
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
        v79 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
        LODWORD(v245) = v79;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( v79 )
        {
          FileSize = CMoUpdateHelpersT<CEmptyType>::GetFileSize(lpFileName, &v329);
          v21 = FileSize;
          if ( FileSize < 0 )
          {
            v81 = *((_QWORD *)this + 75);
            if ( v81 )
            {
              cchCount2[0] = FileSize;
              LODWORD(lpString2) = 2201;
              goto LABEL_171;
            }
LABEL_158:
            v77 = 0;
            goto LABEL_162;
          }
          if ( !v329 )
          {
            v82 = *((_QWORD *)this + 75);
            if ( v82 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v82, 2, L"Deleting zero byte file: [%ws]", lpFileName);
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
              v77 = 0;
              if ( v21 < 0 && *((_QWORD *)this + 75) )
              {
                cchCount2[0] = v21;
                LODWORD(lpString2) = 2205;
                v81 = *((_QWORD *)this + 75);
LABEL_171:
                v77 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                      v81,
                                      4,
                                      L"%s(%d): Result = 0x%X",
                                      L"CDeploymentSession::GenerateDownloadList",
                                      lpString2,
                                      *(_QWORD *)cchCount2,
                                      v234,
                                      v235,
                                      v236,
                                      v237);
LABEL_160:
                if ( (int)v77 < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v77);
              }
LABEL_162:
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v77);
LABEL_163:
              DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
              goto LABEL_705;
            }
            v247 = 1;
            v79 = 0;
            LODWORD(v245) = 0;
          }
          if ( v79 && a5 && !v60 )
          {
            memset(v340, 0, sizeof(v340));
            v84 = 0;
            v248 = 0;
            v85 = *((_QWORD *)this + 75);
            if ( v85 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v85, 2, L"Validating payload file [%ws]", v65[3]);
            if ( v65[5] )
            {
              v86 = CDlpHelpersT<CEmptyType>::CalculateHash(lpFileName);
              v21 = v86;
              if ( v86 < 0 )
              {
                v89 = 2222;
LABEL_192:
                v90 = (unsigned int)v86;
LABEL_193:
                CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                  *((_QWORD *)this + 75),
                  v90,
                  L"CDeploymentSession::GenerateDownloadList",
                  v89);
                DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v248);
                goto LABEL_163;
              }
              v86 = CStringConvertT<unsigned long>::Base64Encode(v340, v87, v88, &v248);
              v21 = v86;
              if ( v86 < 0 )
              {
                v89 = 2223;
                goto LABEL_192;
              }
              v84 = (const WCHAR *)v248;
            }
            v91 = v65[5];
            if ( v91 )
            {
              if ( CompareStringW(0x409u, 1u, v84, -1, v91, -1) != 2 )
              {
                v93 = *((_QWORD *)this + 75);
                if ( v270 )
                {
                  if ( v93 )
                    CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v93,
                      3,
                      L"File hash doesn't match but file was not deleted in Test Mode.");
                }
                else
                {
                  if ( v93 )
                  {
                    lpString2 = v65[5];
                    CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v93,
                      2,
                      L"Deleting corrupt payload file. Actual hash: [%ws], Expected Hash: [%ws]",
                      v84);
                  }
                  if ( !DeleteFileW(lpFileName) )
                  {
                    v94 = GetLastError();
                    v21 = v94;
                    if ( v94 )
                    {
                      if ( v94 > 0 )
                        v21 = (unsigned __int16)v94 | 0x80070000;
                    }
                    else
                    {
                      v21 = -2147467259;
                    }
                    v89 = 2240;
                    v90 = (unsigned int)v21;
                    goto LABEL_193;
                  }
                  v247 = 1;
                  v79 = 0;
                  LODWORD(v245) = 0;
                }
              }
            }
            else
            {
              v92 = *((_QWORD *)this + 75);
              if ( v92 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v92,
                  3,
                  L"Expected hash not available; assuming hashless CompDB and skipping validation.");
            }
            DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v248);
          }
        }
        v95 = v241;
        v96 = *(_DWORD *)(v241 + 104);
        if ( v96 )
        {
          v97 = v96 - 1;
          if ( v97 )
          {
            v98 = v97 - 1;
            if ( v98 )
            {
              v99 = v98 - 2;
              if ( v99 )
              {
                v100 = v99 - 1;
                if ( v100 )
                {
                  if ( v100 != 1 )
                  {
                    v228 = (const char *)(unsigned int)EnsureNTSTATUS<long>(2147549183LL);
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x7B9,
                      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                      v228,
                      (int)lpString2);
                  }
                  v101 = L"Bundle";
                }
                else
                {
                  v101 = L"ReverseDiff";
                }
              }
              else
              {
                v101 = L"PSFX";
              }
            }
            else
            {
              v101 = L"Express";
            }
          }
          else
          {
            v101 = L"Diff";
          }
        }
        else
        {
          v101 = L"Canonical";
        }
        if ( v79 )
        {
          v102 = *((_QWORD *)this + 75);
          if ( v102 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v102, 2, L"File exists: [%ws]", v65[3]);
          if ( v257 + v329 < v257 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v257 += v329;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v105 = 2258;
            goto LABEL_234;
          }
        }
        else
        {
          v243 = 0;
          v107 = *(_DWORD *)(v241 + 104);
          if ( v107 )
          {
            v108 = v107 - 1;
            if ( v108 )
            {
              v109 = v108 - 1;
              if ( v109 )
              {
                v110 = v109 - 2;
                if ( v110 )
                {
                  v111 = v110 - 1;
                  if ( v111 )
                  {
                    if ( v111 != 1 )
                    {
                      v112 = 2310;
                      v21 = -2147418113;
LABEL_243:
                      v113 = (unsigned int)v21;
                      goto LABEL_254;
                    }
                  }
                  else
                  {
                    ++v246;
                    if ( !*((_QWORD *)this + 69) )
                    {
                      OuterContainerDownloadList = STRAPI_Create(v65[17], (wchar_t **)this + 69);
                      v21 = OuterContainerDownloadList;
                      if ( OuterContainerDownloadList < 0 )
                      {
                        v112 = 2290;
                        goto LABEL_253;
                      }
                    }
                  }
                }
              }
              else if ( !*((_QWORD *)this + 69) )
              {
                OuterContainerDownloadList = STRAPI_Create(v65[17], (wchar_t **)this + 69);
                v21 = OuterContainerDownloadList;
                if ( OuterContainerDownloadList < 0 )
                {
                  v112 = 2298;
                  goto LABEL_253;
                }
              }
            }
            else
            {
              ++v246;
              if ( !*((_QWORD *)this + 69) )
              {
                OuterContainerDownloadList = STRAPI_Create(v65[17], (wchar_t **)this + 69);
                v21 = OuterContainerDownloadList;
                if ( OuterContainerDownloadList < 0 )
                {
                  v112 = 2279;
                  goto LABEL_253;
                }
              }
            }
          }
          if ( (unsigned __int64)*v65 + v255 < v255 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v255 += (unsigned __int64)*v65;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v112 = 2314;
            goto LABEL_243;
          }
          v115 = *((_QWORD *)this + 75);
          if ( v65[6] )
          {
            if ( v115 )
            {
              v116 = L"TRUE";
              if ( !v238 )
                v116 = L"FALSE";
              v237 = (__int64)v65[2];
              v236 = (__int64)v65[7];
              v235 = (__int64)v65[8];
              v234 = (struct CDeploymentFileRequest **)v65[6];
              *(_QWORD *)cchCount2 = v65[3];
              LODWORD(lpString2) = *(_DWORD *)(v241 + 88);
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v115,
                2,
                L"Adding file: Optional = [%ws], Category = [%u], FileName = [%ws], Container = [%ws], Hash = [%ws], Cix ="
                 " [%ws], payloadName = [%ws]",
                v116);
            }
            OuterContainerDownloadList = CDeploymentSession::GenerateOuterContainerDownloadList(
                                           this,
                                           (const struct ActionList::Payload *const)v65,
                                           v101,
                                           v244);
            v21 = OuterContainerDownloadList;
            if ( OuterContainerDownloadList < 0 )
            {
              v112 = 2329;
              goto LABEL_253;
            }
          }
          else
          {
            if ( v115 )
            {
              v117 = L"TRUE";
              if ( !v238 )
                v117 = L"FALSE";
              LODWORD(lpString2) = *(_DWORD *)(v241 + 88);
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v115,
                2,
                L"Adding file: Optional = [%ws], Category = [%u], FileName = [%ws]",
                v117,
                lpString2,
                v65[3],
                v234,
                v235,
                v236,
                v237);
            }
            OuterContainerDownloadList = CDeploymentFileRequest::Create(
                                           v65[5],
                                           v65[3],
                                           v65[2],
                                           v65[4],
                                           v101,
                                           v238,
                                           &v243);
            v21 = OuterContainerDownloadList;
            if ( OuterContainerDownloadList < 0 )
            {
              v112 = 2344;
              goto LABEL_253;
            }
            v118 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v300, &v243);
            OuterContainerDownloadList = CDeploymentDownloadRequest::AppendFileRequest(v244, v118);
            v21 = OuterContainerDownloadList;
            if ( OuterContainerDownloadList < 0 )
            {
              v112 = 2345;
LABEL_253:
              v113 = (unsigned int)OuterContainerDownloadList;
LABEL_254:
              CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                *((_QWORD *)this + 75),
                v113,
                L"CDeploymentSession::GenerateDownloadList",
                v112);
              if ( v243 )
              {
                (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v243 + 16LL))(v243);
                v243 = 0;
              }
              goto LABEL_163;
            }
          }
          if ( v243 )
          {
            (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v243 + 16LL))(v243);
            v243 = 0;
          }
          v95 = v241;
        }
        if ( !v65[10] || !a5 || *(_DWORD *)(v95 + 104) != 2 )
          goto LABEL_301;
        SH_SSTRING::operator=(&lpFileName);
        v119 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v65[10], 0, &lpFileName);
        v21 = v119;
        if ( v119 < 0 )
        {
          v105 = 2356;
LABEL_284:
          v106 = (unsigned int)v119;
          goto LABEL_235;
        }
        v119 = CMiscHelpersT<CEmptyType>::FileExists(lpFileName, &v245);
        v21 = v119;
        if ( v119 < 0 )
        {
          v105 = 2357;
          goto LABEL_284;
        }
        if ( (_DWORD)v245 )
        {
          v119 = CMoUpdateHelpersT<CEmptyType>::GetFileSize(lpFileName, &v329);
          v21 = v119;
          if ( v119 < 0 )
          {
            v105 = 2361;
            goto LABEL_284;
          }
          if ( v257 + v329 < v257 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v257 += v329;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v105 = 2362;
            goto LABEL_234;
          }
          v120 = 1;
          v240 = 1;
          if ( *((_BYTE *)v65 + 153) )
          {
            if ( v281 + v329 < v281 )
            {
              v21 = -2147024362;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            }
            else
            {
              v281 += v329;
              v21 = 0;
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
            if ( v21 < 0 )
            {
              v105 = 2367;
LABEL_234:
              v106 = (unsigned int)v21;
LABEL_235:
              CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                *((_QWORD *)this + 75),
                v106,
                L"CDeploymentSession::GenerateDownloadList",
                v105);
              goto LABEL_163;
            }
          }
        }
        else
        {
LABEL_301:
          v120 = v240;
        }
        if ( v253 && v65[14] && v65[9] && !v271 )
          break;
        v59 = v241;
LABEL_328:
        v274 = 0;
        v248 = 0;
        v245 = 0;
        if ( v253 )
          goto LABEL_394;
        v129 = *((_DWORD *)this + 114);
        if ( v129 > 0x16 )
          goto LABEL_394;
        v130 = 4195440;
        if ( !_bittest(&v130, v129) || *(_DWORD *)(v59 + 104) != 2 )
          goto LABEL_394;
        SH_SSTRING::operator=(&lpFileName);
        v119 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v65[2], 0, &lpFileName);
        v21 = v119;
        if ( v119 < 0 )
        {
          v105 = 2433;
          goto LABEL_284;
        }
        v131 = -1;
        v132 = -1;
        do
          ++v132;
        while ( *(_WORD *)(*((_QWORD *)this + 61) + 2 * v132) );
        do
          ++v131;
        while ( lpFileName[v131] );
        v304[0] = *((_QWORD *)this + 61);
        v304[1] = v132;
        v295 = lpFileName;
        v296 = v131;
        v119 = CheckIfHistoryCixIsPresent(
                 (unsigned int)&v295,
                 (unsigned int)v304,
                 (unsigned int)&v274,
                 (unsigned int)&v248,
                 (__int64)&v245);
        v21 = v119;
        if ( v119 < 0 )
        {
          v105 = 2435;
          goto LABEL_284;
        }
        v133 = v248;
        if ( v248 )
        {
          v134 = v65[9];
          Src = 0;
          v333 = 0;
          v334 = 0;
          v135 = -1;
          do
            ++v135;
          while ( v134[v135] );
          std::wstring::_Construct<1,wchar_t const *>(&Src);
          v311 = 0;
          v312 = 0;
          v313 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v311);
          v308 = 0;
          v309 = 0;
          v310 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v308);
          ReplaceAll<std::wstring>(&Src);
          std::wstring::~wstring(&v308);
          std::wstring::~wstring(&v311);
          if ( v133 + v255 < v255 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v255 += v133;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v136 = 2445;
            goto LABEL_347;
          }
          if ( v133 + v258 < v258 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v258 += v133;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v136 = 2446;
            goto LABEL_347;
          }
          if ( (unsigned __int64)v245 + v331 < v331 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v331 += (__int64)v245;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v136 = 2447;
LABEL_347:
            v137 = (unsigned int)v21;
LABEL_348:
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              v137,
              L"CDeploymentSession::GenerateDownloadList",
              v136);
            goto LABEL_349;
          }
          v138 = v65[11];
          p_Src = (const wchar_t *)&Src;
          if ( v334 > 7 )
            p_Src = (const wchar_t *)Src;
          v140 = 0;
          v291 = 0;
          v141 = v282[6];
          if ( v141 )
          {
            v142 = v282[8];
            OffsetInOuterContainer = CDeploymentSession::GetOffsetInOuterContainer(
                                       this,
                                       v141,
                                       0,
                                       v282[9],
                                       v282[14],
                                       &v291,
                                       0);
            v21 = OffsetInOuterContainer;
            if ( OffsetInOuterContainer < 0 )
            {
              v136 = 2464;
              v137 = (unsigned int)OffsetInOuterContainer;
              goto LABEL_348;
            }
            v140 = v291;
          }
          else
          {
            v142 = v282[5];
            v141 = v282[2];
          }
          v144 = *((_QWORD *)this + 75);
          if ( v144 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v144,
              2,
              L"    Adding HistoryCIX file: [%s] with Hash [%s]",
              p_Src,
              v142);
          v145 = *((_QWORD *)this + 75);
          if ( v145 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v145, 2, L"    Download size : [%llu]", v248);
          v146 = *((_QWORD *)this + 75);
          if ( v146 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v146, 2, L"    Expand size : [%llu]", v245);
          v245 = 0;
          v147 = CDeploymentFileRequest::Create(v142, p_Src, v141, v138, L"Express", v238, &v245);
          v21 = v147;
          if ( v147 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v147,
              L"CDeploymentSession::GenerateDownloadList",
              2483);
            goto LABEL_375;
          }
          v250 = 0;
          v149 = CDeploymentFileRange::Create(v140 + v274, v248, &v250);
          v21 = v149;
          if ( v149 < 0 )
          {
            v150 = 2486;
            goto LABEL_380;
          }
          v151 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v302, &v250);
          v152 = v245;
          appended = CDeploymentFileRequest::AppendExpressFileRange(v245, v151);
          v21 = appended;
          if ( appended < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)appended,
              L"CDeploymentSession::GenerateDownloadList",
              2487);
            if ( v250 )
            {
              (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v250 + 16LL))(v250);
              v250 = 0;
            }
            if ( v152 )
            {
              v148 = *(_QWORD *)v152;
LABEL_377:
              (*(void (**)(void))(v148 + 16))();
            }
            goto LABEL_349;
          }
          v154 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v303, &v245);
          v149 = CDeploymentDownloadRequest::AppendFileRequest(v244, v154);
          v21 = v149;
          if ( v149 < 0 )
          {
            v150 = 2489;
LABEL_380:
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v149,
              L"CDeploymentSession::GenerateDownloadList",
              v150);
            if ( v250 )
            {
              (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v250 + 16LL))(v250);
              v250 = 0;
            }
LABEL_375:
            if ( v245 )
            {
              v148 = *(_QWORD *)v245;
              goto LABEL_377;
            }
LABEL_349:
            std::wstring::~wstring(&Src);
            goto LABEL_163;
          }
          v38 = 1;
          if ( v250 )
          {
            (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v250 + 16LL))(v250);
            v250 = 0;
          }
          if ( v245 )
            (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v245 + 16LL))(v245);
          std::wstring::~wstring(&Src);
          DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
          v65 = v282;
          v59 = v241;
        }
        else
        {
LABEL_394:
          DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
        }
LABEL_395:
        v65 += 23;
        v66 = v292;
        v60 = v242;
        v57 = v258;
        v21 = 0;
      }
      v121 = v120 == 0;
      v59 = v241;
      if ( !v121 || *((_BYTE *)v65 + 153) || *(_DWORD *)(v241 + 104) != 2 )
        goto LABEL_328;
      v249 = 0;
      if ( !v65[8] || (v122 = v65 + 6, !v65[6]) )
      {
        v123 = CDeploymentFileRequest::Create(v65[14], v65[9], v65[9], v65[11], L"Canonical", v238, &v249);
        v21 = v123;
        if ( v123 >= 0 )
          goto LABEL_320;
        v124 = 2412;
LABEL_314:
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v123,
          L"CDeploymentSession::GenerateDownloadList",
          v124);
        if ( v249 )
        {
          (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v249 + 16LL))(v249);
          v249 = 0;
        }
        goto LABEL_163;
      }
      if ( !(unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::contains<wchar_t *>(
                               (char *)this + 768,
                               v65 + 6,
                               v103,
                               v104) )
      {
        v123 = CDeploymentFileRequest::Create(v65[8], *v122, *v122, 0, L"Canonical", v238, &v249);
        v21 = v123;
        if ( v123 < 0 )
        {
          v124 = 2397;
          goto LABEL_314;
        }
        v125 = *v122;
        v305 = 0;
        v306 = 0;
        v307 = 0;
        v126 = -1;
        do
          ++v126;
        while ( v125[v126] );
        std::wstring::_Construct<1,wchar_t const *>(&v305);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
          (char *)this + 768,
          v317,
          &v305);
        std::wstring::~wstring(&v305);
      }
      v59 = v241;
LABEL_320:
      v127 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v301, &v249);
      v128 = v244;
      v123 = CDeploymentDownloadRequest::AppendFileRequest(v244, v127);
      v21 = v123;
      if ( v123 < 0 )
      {
        v124 = 2415;
        goto LABEL_314;
      }
      v21 = 0;
      if ( v249 )
      {
        (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v249 + 16LL))(v249);
        v249 = 0;
      }
      DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
LABEL_397:
      v155 = v265;
      if ( v265 <= v246 )
        v155 = v246;
      v265 = v155;
      if ( v253 || a5 || *(_DWORD *)(v59 + 104) != 2 || v38 )
      {
        v168 = v255;
        v162 = v238;
        v163 = v241;
      }
      else
      {
        v338 = 0;
        v337 = 0;
        v156 = *((_DWORD *)this + 114);
        if ( (v156 == 4 || (v157 = 1, v156 == 22))
          && (v157 = 0, v158 = *((_QWORD *)v256 + 11), v159 = v158 + 168LL * *((unsigned int *)v256 + 24), v158 != v159) )
        {
          while ( (unsigned int)_o__wcsicmp(*(_QWORD *)(v59 + 56), *(_QWORD *)(v158 + 56)) )
          {
            v158 += 168;
            if ( v158 == v159 )
              goto LABEL_410;
          }
LABEL_412:
          v160 = a6;
        }
        else
        {
          if ( v157 )
            goto LABEL_412;
LABEL_410:
          v160 = 1;
          v161 = *((_QWORD *)this + 75);
          if ( v161 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v161,
              2,
              L"Skipping ICbsServicingProcessor->WritePackageFileList PackageFilePath: [%ws]; must be repair content",
              *(_QWORD *)(v59 + 56));
        }
        v162 = v238;
        v163 = v241;
        ExpressDownloadList = CDeploymentSession::GenerateExpressDownloadList(
                                this,
                                v241,
                                v238,
                                v271,
                                v160,
                                (wchar_t *)v339,
                                (__int64)v128,
                                (unsigned __int64 *)&v338,
                                (unsigned __int64 *)&v337,
                                (unsigned __int64 *)&v331,
                                (int *)&v330);
        v21 = ExpressDownloadList;
        if ( ExpressDownloadList < 0 )
        {
          v165 = 2546;
LABEL_415:
          v166 = (unsigned int)ExpressDownloadList;
          goto LABEL_416;
        }
        v167 = v247;
        if ( (_DWORD)v330 )
          v167 = 1;
        v247 = v167;
        v168 = v255;
        if ( v255 + v338 < v255 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v168 = v255 + v338;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v165 = 2552;
          goto LABEL_424;
        }
        if ( v258 + v337 < v258 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v258 += v337;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v165 = 2553;
          goto LABEL_424;
        }
        v21 = 0;
      }
      if ( v168 + v267 < v267 )
      {
        v21 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
      }
      else
      {
        v267 += v168;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
      if ( v21 < 0 )
      {
        v165 = 2558;
        goto LABEL_424;
      }
      if ( v276 + v331 < v276 )
      {
        v21 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
      }
      else
      {
        v276 += v331;
        v21 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
      if ( v21 < 0 )
      {
        v165 = 2559;
        goto LABEL_424;
      }
      if ( v168 )
      {
        if ( v162 )
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
          if ( v21 < 0 )
          {
            v165 = 2565;
            goto LABEL_424;
          }
        }
        else
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
          if ( v21 < 0 )
          {
            v165 = 2569;
            goto LABEL_424;
          }
          if ( v168 + v251 < v251 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v251 += v168;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v165 = 2571;
            goto LABEL_424;
          }
          if ( v275 + v258 < v275 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v275 += v258;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v165 = 2572;
            goto LABEL_424;
          }
          if ( v252 + v331 < v252 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v252 += v331;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v165 = 2573;
            goto LABEL_424;
          }
        }
      }
      v169 = *(_DWORD *)(v163 + 88);
      if ( v169 > 7 )
      {
        v177 = v169 - 13;
        if ( !v177 )
        {
          v186 = *((_QWORD *)&v284 + 1);
          v187 = *((_QWORD *)&v284 + 1) + v251;
          if ( *((_QWORD *)&v284 + 1) + v251 < *((_QWORD *)&v284 + 1) )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            v187 = v186;
          }
          else
          {
            *((_QWORD *)&v284 + 1) += v251;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v165 = 2602;
            goto LABEL_424;
          }
          if ( v187 + v252 < v187 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            *((_QWORD *)&v284 + 1) = v187 + v252;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v165 = 2603;
            goto LABEL_424;
          }
          HIDWORD(v286) = v162;
          goto LABEL_545;
        }
        v178 = v177 - 1;
        if ( !v178 )
        {
          v184 = v285;
          v185 = v285 + v251;
          if ( (unsigned __int64)v285 + v251 < (unsigned __int64)v285 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            v185 = v184;
          }
          else
          {
            *(_QWORD *)&v285 = v285 + v251;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v165 = 2608;
            goto LABEL_424;
          }
          if ( v185 + v252 < v185 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            *(_QWORD *)&v285 = v185 + v252;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v165 = 2609;
            goto LABEL_424;
          }
          LODWORD(v287) = v162;
          goto LABEL_545;
        }
        v179 = v178 - 1;
        if ( !v179 )
        {
          v182 = *((_QWORD *)&v285 + 1);
          v183 = *((_QWORD *)&v285 + 1) + v251;
          if ( *((_QWORD *)&v285 + 1) + v251 < *((_QWORD *)&v285 + 1) )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            v183 = v182;
          }
          else
          {
            *((_QWORD *)&v285 + 1) += v251;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v165 = 2614;
            goto LABEL_424;
          }
          if ( v183 + v252 < v183 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            *((_QWORD *)&v285 + 1) = v183 + v252;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v165 = 2615;
            goto LABEL_424;
          }
          HIDWORD(v287) = v162;
          goto LABEL_545;
        }
        if ( v179 != 2 )
          goto LABEL_545;
LABEL_501:
        v180 = v284;
        v181 = v284 + v251;
        if ( (unsigned __int64)v284 + v251 < (unsigned __int64)v284 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          v181 = v180;
        }
        else
        {
          *(_QWORD *)&v284 = v284 + v251;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v165 = 2589;
          goto LABEL_424;
        }
        if ( v181 + v252 < v181 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          *(_QWORD *)&v284 = v181 + v252;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v165 = 2590;
          goto LABEL_424;
        }
        DWORD2(v286) = v162;
        goto LABEL_545;
      }
      if ( v169 == 7 )
        goto LABEL_475;
      v170 = v169 - 2;
      if ( !v170 || (v171 = v170 - 1) == 0 )
      {
        v175 = *((_QWORD *)&v283 + 1);
        v176 = *((_QWORD *)&v283 + 1) + v251;
        if ( *((_QWORD *)&v283 + 1) + v251 < *((_QWORD *)&v283 + 1) )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          v176 = v175;
        }
        else
        {
          *((_QWORD *)&v283 + 1) += v251;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v165 = 2596;
          goto LABEL_424;
        }
        if ( v176 + v252 < v176 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          *((_QWORD *)&v283 + 1) = v176 + v252;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v165 = 2597;
          goto LABEL_424;
        }
        DWORD1(v286) = v162;
        goto LABEL_545;
      }
      v172 = v171 - 1;
      if ( !v172 )
        goto LABEL_501;
      if ( (unsigned int)(v172 - 1) <= 1 )
      {
LABEL_475:
        v173 = v283;
        v174 = v283 + v251;
        if ( (unsigned __int64)v283 + v251 < (unsigned __int64)v283 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          v174 = v173;
        }
        else
        {
          *(_QWORD *)&v283 = v283 + v251;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v165 = 2582;
          goto LABEL_424;
        }
        if ( v174 + v252 < v174 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          *(_QWORD *)&v283 = v174 + v252;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v165 = 2583;
          goto LABEL_424;
        }
        LODWORD(v286) = v162;
      }
LABEL_545:
      v188 = *(_DWORD *)(v163 + 104);
      v38 = 0;
      if ( !v188 )
      {
        if ( v269 + v257 < v269 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v269 += v257;
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
          v165 = 2624;
        }
        else
        {
          v165 = 2623;
        }
        goto LABEL_424;
      }
      v189 = v188 - 1;
      if ( !v189 )
        goto LABEL_550;
      v190 = v189 - 1;
      if ( !v190 )
      {
        v192 = v281;
        if ( v281 + v269 < v269 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v269 += v281;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 >= 0 )
        {
          v193 = v257;
          if ( v257 - v192 > v257 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            v193 = v257 - v192;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 >= 0 )
          {
            if ( v193 + v278 < v278 )
            {
              v21 = -2147024362;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
            }
            else
            {
              v278 += v193;
              v21 = 0;
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
            if ( v21 >= 0 )
            {
              if ( v264 + 1 < v264 )
              {
                v21 = -2147024362;
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
              }
              else
              {
                ++v264;
                v21 = 0;
              }
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
              if ( v21 >= 0 )
                goto LABEL_109;
              v165 = 2643;
            }
            else
            {
              v165 = 2642;
            }
          }
          else
          {
            v165 = 2640;
          }
        }
        else
        {
          v165 = 2639;
        }
        goto LABEL_424;
      }
      v191 = v190 - 2;
      if ( !v191 )
      {
        if ( v280 + v257 < v280 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v280 += v257;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 >= 0 )
        {
          if ( v262 + 1 < v262 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
          }
          else
          {
            ++v262;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 >= 0 )
            goto LABEL_109;
          v165 = 2629;
        }
        else
        {
          v165 = 2628;
        }
        goto LABEL_424;
      }
      if ( v191 == 1 )
      {
LABEL_550:
        if ( v279 + v257 < v279 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v279 += v257;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 >= 0 )
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
          if ( v21 >= 0 )
            goto LABEL_109;
          v165 = 2635;
        }
        else
        {
          v165 = 2634;
        }
LABEL_424:
        v166 = (unsigned int)v21;
LABEL_416:
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          v166,
          L"CDeploymentSession::GenerateDownloadList",
          v165);
        goto LABEL_705;
      }
LABEL_109:
      v54 = v268;
LABEL_110:
      v53 = v241 + 168;
    }
    v59 = v241;
LABEL_117:
    *((_DWORD *)this + 71) = 1;
    v60 = 1;
    v21 = 0;
    goto LABEL_118;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAFE,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v226);
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
