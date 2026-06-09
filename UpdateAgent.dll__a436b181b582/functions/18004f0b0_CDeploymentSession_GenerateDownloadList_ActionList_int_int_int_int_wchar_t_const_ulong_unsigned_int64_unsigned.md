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
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  bool v28; // dl
  int v29; // eax
  unsigned int v30; // ebx
  int v31; // eax
  __int64 v32; // rcx
  int v33; // eax
  const wchar_t *v34; // rax
  char v35; // bl
  int v36; // eax
  __int64 v37; // rbx
  HANDLE ProcessHeap; // rax
  int v39; // eax
  char v40; // r13
  __int64 v41; // rcx
  __int64 v42; // rbx
  __int64 v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rcx
  int v48; // eax
  __int64 v49; // rdx
  __int64 v50; // rbx
  HANDLE v51; // rax
  __int64 v52; // rax
  _OWORD *v53; // rcx
  __int64 v54; // rbx
  HANDLE v55; // rax
  __int64 v56; // rcx
  int *v57; // rdx
  unsigned int v58; // eax
  __int64 v59; // rcx
  unsigned __int64 v60; // r15
  int v61; // ecx
  __int64 v62; // r14
  char v63; // bl
  int v64; // eax
  __int64 v65; // rcx
  int *v66; // r8
  int *v67; // r9
  const wchar_t **v68; // r12
  const wchar_t **v69; // rax
  int v70; // eax
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rdx
  LPCWSTR v75; // rbx
  HANDLE v76; // rax
  __int64 v77; // rcx
  LPCWSTR v78; // rbx
  HANDLE v79; // rax
  int v80; // eax
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rdx
  DWORD FileAttributesW; // eax
  BOOL v85; // r14d
  wchar_t **v86; // rdx
  int FileSize; // eax
  __int64 v88; // rcx
  __int64 v89; // rcx
  signed int LastError; // eax
  const WCHAR *v91; // rbx
  __int64 v92; // rcx
  int v93; // eax
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // r9
  __int64 v97; // rdx
  const WCHAR *v98; // rax
  __int64 v99; // rcx
  __int64 v100; // rcx
  signed int v101; // eax
  __int64 v102; // rbx
  int v103; // ecx
  int v104; // ecx
  int v105; // ecx
  int v106; // ecx
  int v107; // ecx
  const wchar_t *v108; // r15
  __int64 v109; // rcx
  __int64 v110; // r8
  __int64 v111; // r9
  __int64 v112; // r9
  __int64 v113; // rdx
  int v114; // ecx
  int v115; // ecx
  int v116; // ecx
  int v117; // ecx
  int v118; // ecx
  __int64 v119; // r9
  __int64 v120; // rdx
  int OuterContainerDownloadList; // eax
  __int64 v122; // rcx
  const wchar_t *v123; // r9
  const wchar_t *v124; // r9
  __int64 v125; // rax
  int v126; // eax
  __int64 v127; // rdx
  __int64 v128; // rdx
  char v129; // r14
  bool v130; // zf
  const wchar_t **v131; // rbx
  int v132; // eax
  __int64 v133; // r9
  const wchar_t *v134; // rdx
  __int64 v135; // r8
  __int64 v136; // rax
  CDeploymentDownloadRequest *v137; // r15
  unsigned int v138; // eax
  int v139; // ecx
  __int64 v140; // rax
  __int64 v141; // rdx
  unsigned __int64 v142; // rbx
  const wchar_t *v143; // rdx
  __int64 v144; // r8
  __int64 v145; // rdx
  __int64 v146; // rdx
  __int64 v147; // r9
  __int64 v148; // rdx
  __int64 v149; // rdx
  const wchar_t *v150; // r13
  const wchar_t *p_Src; // r15
  unsigned __int64 v152; // r12
  const wchar_t *v153; // rbx
  const wchar_t *v154; // r14
  int OffsetInOuterContainer; // eax
  __int64 v156; // rcx
  __int64 v157; // rcx
  __int64 v158; // rcx
  int v159; // eax
  __int64 v160; // rax
  int v161; // eax
  __int64 v162; // r9
  __int64 v163; // rax
  struct CDeploymentFileRequest *v164; // rbx
  int appended; // eax
  __int64 v166; // rax
  unsigned int v167; // r11d
  int v168; // eax
  char v169; // cl
  __int64 v170; // rbx
  __int64 v171; // rdi
  int v172; // ebx
  __int64 v173; // rcx
  unsigned __int8 v174; // r14
  __int64 v175; // r13
  int ExpressDownloadList; // eax
  __int64 v177; // rdx
  __int64 v178; // r9
  __int64 v179; // rdx
  int v180; // eax
  unsigned __int64 v181; // r15
  __int64 v182; // rdx
  __int64 v183; // rdx
  __int64 v184; // rdx
  __int64 v185; // rdx
  __int64 v186; // rdx
  int v187; // ecx
  int v188; // ecx
  int v189; // ecx
  int v190; // ecx
  unsigned __int64 v191; // r15
  unsigned __int64 v192; // rbx
  unsigned __int64 v193; // r15
  unsigned __int64 v194; // rbx
  __int64 v195; // rdx
  __int64 v196; // rdx
  int v197; // ecx
  int v198; // ecx
  int v199; // ecx
  unsigned __int64 v200; // r15
  unsigned __int64 v201; // rbx
  __int64 v202; // rdx
  unsigned __int64 v203; // r15
  unsigned __int64 v204; // rbx
  __int64 v205; // rdx
  unsigned __int64 v206; // r15
  unsigned __int64 v207; // rbx
  __int64 v208; // rdx
  unsigned __int64 v209; // r15
  unsigned __int64 v210; // rbx
  __int64 v211; // rdx
  int v212; // ecx
  int v213; // ecx
  int v214; // ecx
  int v215; // ecx
  __int64 v216; // rdx
  unsigned __int64 v217; // r14
  __int64 v218; // rdx
  unsigned __int64 v219; // rbx
  __int64 v220; // rdx
  __int64 v221; // rdx
  __int64 v222; // rdx
  __int64 v223; // rdx
  int v224; // eax
  __int64 v225; // r9
  __int64 v226; // rcx
  unsigned int i; // r14d
  int v228; // eax
  int v229; // eax
  __int64 v230; // r9
  __int64 v231; // rcx
  __int64 v232; // rdx
  unsigned int j; // ebx
  int v234; // eax
  __int64 v235; // r9
  __int64 v236; // rcx
  __int64 v237; // rcx
  unsigned __int64 v238; // rbx
  __int64 v239; // rcx
  __int64 v240; // rcx
  __int64 v241; // rcx
  __int64 v242; // rcx
  CDeploymentDownloadRequest *v243; // r13
  int v244; // r15d
  struct ActionList *v245; // r12
  unsigned int v246; // eax
  char v247; // cl
  int v248; // r14d
  __int64 v249; // rbx
  const WCHAR *v250; // rax
  __int64 v251; // rcx
  unsigned int v252; // eax
  int *v253; // rax
  struct _DUPackageInfo *v254; // rax
  struct _ReportEventDownloadRequestParams *v255; // rcx
  const char *v256; // r9
  __int64 result; // rax
  const char *v258; // r9
  PCNZWCH lpString2; // [rsp+20h] [rbp-418h]
  int lpString2a; // [rsp+20h] [rbp-418h]
  int cchCount2[2]; // [rsp+28h] [rbp-410h]
  int cchCount2a; // [rsp+28h] [rbp-410h]
  int cchCount2b; // [rsp+28h] [rbp-410h]
  struct CDeploymentFileRequest **v264; // [rsp+30h] [rbp-408h]
  __int64 v265; // [rsp+38h] [rbp-400h]
  __int64 v266; // [rsp+40h] [rbp-3F8h]
  __int64 v267; // [rsp+48h] [rbp-3F0h]
  unsigned __int8 v268; // [rsp+60h] [rbp-3D8h]
  LPCWSTR lpFileName; // [rsp+68h] [rbp-3D0h] BYREF
  char v270; // [rsp+70h] [rbp-3C8h]
  __int64 v271; // [rsp+78h] [rbp-3C0h]
  char v272; // [rsp+80h] [rbp-3B8h]
  struct CDeploymentFileRequest *v273; // [rsp+88h] [rbp-3B0h] BYREF
  CDeploymentDownloadRequest *v274; // [rsp+90h] [rbp-3A8h]
  struct CDeploymentFileRequest *v275; // [rsp+98h] [rbp-3A0h] BYREF
  unsigned int v276; // [rsp+A0h] [rbp-398h]
  int v277; // [rsp+A4h] [rbp-394h]
  unsigned __int64 v278; // [rsp+A8h] [rbp-390h] BYREF
  struct CDeploymentFileRequest *v279; // [rsp+B0h] [rbp-388h] BYREF
  struct CDeploymentFileRange *v280; // [rsp+B8h] [rbp-380h] BYREF
  unsigned __int64 v281; // [rsp+C0h] [rbp-378h]
  unsigned __int64 v282; // [rsp+C8h] [rbp-370h]
  int v283; // [rsp+D0h] [rbp-368h]
  struct CDeploymentDownloadRequest *v284; // [rsp+D8h] [rbp-360h] BYREF
  unsigned __int64 v285; // [rsp+E0h] [rbp-358h]
  struct ActionList *v286; // [rsp+E8h] [rbp-350h]
  unsigned __int64 v287; // [rsp+F0h] [rbp-348h]
  unsigned __int64 v288; // [rsp+F8h] [rbp-340h]
  unsigned int v289; // [rsp+100h] [rbp-338h]
  unsigned int v290; // [rsp+104h] [rbp-334h]
  unsigned int v291; // [rsp+108h] [rbp-330h]
  unsigned int v292; // [rsp+10Ch] [rbp-32Ch]
  unsigned int v293; // [rsp+110h] [rbp-328h]
  unsigned int v294; // [rsp+114h] [rbp-324h]
  unsigned int v295; // [rsp+118h] [rbp-320h]
  unsigned int v296; // [rsp+11Ch] [rbp-31Ch]
  unsigned __int64 v297; // [rsp+120h] [rbp-318h]
  int *v298; // [rsp+128h] [rbp-310h]
  unsigned __int64 v299; // [rsp+130h] [rbp-308h]
  int v300; // [rsp+138h] [rbp-300h] BYREF
  DWORD v301; // [rsp+13Ch] [rbp-2FCh]
  int v302; // [rsp+140h] [rbp-2F8h] BYREF
  char v303; // [rsp+144h] [rbp-2F4h] BYREF
  __int64 v304; // [rsp+148h] [rbp-2F0h] BYREF
  unsigned __int64 v305; // [rsp+150h] [rbp-2E8h] BYREF
  unsigned __int64 v306; // [rsp+158h] [rbp-2E0h]
  __int64 v307; // [rsp+160h] [rbp-2D8h] BYREF
  unsigned __int64 v308; // [rsp+168h] [rbp-2D0h]
  unsigned __int64 v309; // [rsp+170h] [rbp-2C8h]
  unsigned __int64 v310; // [rsp+178h] [rbp-2C0h]
  unsigned __int64 v311; // [rsp+180h] [rbp-2B8h]
  const wchar_t **v312; // [rsp+188h] [rbp-2B0h]
  __int128 v313; // [rsp+190h] [rbp-2A8h] BYREF
  __int128 v314; // [rsp+1A0h] [rbp-298h]
  __int128 v315; // [rsp+1B0h] [rbp-288h]
  __int128 v316; // [rsp+1C0h] [rbp-278h]
  __int64 v317; // [rsp+1D0h] [rbp-268h]
  struct IDeploymentDownloadRequest **v318; // [rsp+1E0h] [rbp-258h]
  unsigned __int64 *v319; // [rsp+1E8h] [rbp-250h]
  unsigned __int64 *v320; // [rsp+1F0h] [rbp-248h]
  unsigned __int64 v321; // [rsp+1F8h] [rbp-240h] BYREF
  const wchar_t **v322; // [rsp+200h] [rbp-238h]
  unsigned __int64 *v323; // [rsp+208h] [rbp-230h]
  unsigned __int64 *v324; // [rsp+210h] [rbp-228h]
  LPCWSTR v325; // [rsp+220h] [rbp-218h] BYREF
  __int64 v326; // [rsp+228h] [rbp-210h]
  struct _DUPackageInfo *v327; // [rsp+230h] [rbp-208h]
  struct _ReportEventDownloadRequestParams *v328; // [rsp+238h] [rbp-200h]
  const wchar_t *v329; // [rsp+240h] [rbp-1F8h] BYREF
  char v330[8]; // [rsp+248h] [rbp-1F0h] BYREF
  char v331[8]; // [rsp+250h] [rbp-1E8h] BYREF
  char v332[8]; // [rsp+258h] [rbp-1E0h] BYREF
  char v333[16]; // [rsp+260h] [rbp-1D8h] BYREF
  _QWORD v334[2]; // [rsp+270h] [rbp-1C8h] BYREF
  __int128 v335; // [rsp+280h] [rbp-1B8h] BYREF
  __int64 v336; // [rsp+290h] [rbp-1A8h]
  __int64 v337; // [rsp+298h] [rbp-1A0h]
  __int128 v338; // [rsp+2A0h] [rbp-198h] BYREF
  __int64 v339; // [rsp+2B0h] [rbp-188h]
  __int64 v340; // [rsp+2B8h] [rbp-180h]
  __int128 v341; // [rsp+2C0h] [rbp-178h] BYREF
  __int64 v342; // [rsp+2D0h] [rbp-168h]
  __int64 v343; // [rsp+2D8h] [rbp-160h]
  _QWORD v344[2]; // [rsp+2E0h] [rbp-158h] BYREF
  char v345; // [rsp+2F0h] [rbp-148h]
  __int64 v346; // [rsp+2F8h] [rbp-140h]
  char v347[16]; // [rsp+300h] [rbp-138h] BYREF
  _BYTE v348[32]; // [rsp+310h] [rbp-128h] BYREF
  LPVOID v349; // [rsp+330h] [rbp-108h] BYREF
  LPVOID pv; // [rsp+338h] [rbp-100h] BYREF
  __int64 v351; // [rsp+340h] [rbp-F8h] BYREF
  __int64 v352; // [rsp+348h] [rbp-F0h] BYREF
  __int64 v353; // [rsp+350h] [rbp-E8h] BYREF
  __int64 v354; // [rsp+358h] [rbp-E0h] BYREF
  unsigned int v355; // [rsp+360h] [rbp-D8h] BYREF
  unsigned int v356; // [rsp+364h] [rbp-D4h] BYREF
  int v357; // [rsp+368h] [rbp-D0h] BYREF
  int v358; // [rsp+36Ch] [rbp-CCh] BYREF
  __int64 v359; // [rsp+370h] [rbp-C8h] BYREF
  __int64 v360; // [rsp+378h] [rbp-C0h] BYREF
  __int64 v361; // [rsp+380h] [rbp-B8h] BYREF
  __int128 Src; // [rsp+388h] [rbp-B0h] BYREF
  __int64 v363; // [rsp+398h] [rbp-A0h]
  unsigned __int64 v364; // [rsp+3A0h] [rbp-98h]
  __int64 v365; // [rsp+3A8h] [rbp-90h] BYREF
  __int64 v366; // [rsp+3B0h] [rbp-88h] BYREF
  __int64 v367; // [rsp+3B8h] [rbp-80h] BYREF
  __int64 v368; // [rsp+3C0h] [rbp-78h] BYREF
  __int64 v369[2]; // [rsp+3C8h] [rbp-70h] BYREF
  _OWORD v370[2]; // [rsp+3D8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+0h]

  v346 = -2;
  v301 = a4;
  v283 = a3;
  v17 = a2;
  v286 = a2;
  v324 = a9;
  v323 = a10;
  v319 = a11;
  v320 = a12;
  v327 = a13;
  v328 = a14;
  v318 = a15;
  v274 = 0;
  v284 = 0;
  v357 = 0;
  v300 = 0;
  memset_0(&v313, 0, 0x48u);
  LODWORD(v360) = 0;
  v369[0] = 0;
  v369[1] = 0;
  try
  {
    v19 = operator new(0x40u);
    *v19 = v19;
    v19[1] = v19;
    v19[2] = v19;
    *((_WORD *)v19 + 12) = 257;
    v369[0] = (__int64)v19;
    v344[0] = this;
    v344[1] = &v357;
    v345 = 1;
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
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated, v23);
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
    if ( !v324 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2063;
      goto LABEL_12;
    }
    if ( !v323 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2064;
      goto LABEL_12;
    }
    if ( !v319 )
    {
      v21 = -2147024809;
      if ( !v20 )
        goto LABEL_4;
      cchCount2a = -2147024809;
      lpString2a = 2065;
      goto LABEL_12;
    }
    if ( !v320 )
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
    if ( !v318 )
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
    v24 = CDeploymentDownloadRequest::Create(v20, a7, a8, &v284);
    v21 = v24;
    if ( v24 < 0 )
    {
      v25 = *((_QWORD *)this + 75);
      if ( !v25 )
      {
LABEL_44:
        v26 = 0;
        goto LABEL_48;
      }
      v26 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                            v25,
                            4,
                            L"%s(%d): Result = 0x%X",
                            L"CDeploymentSession::GenerateDownloadList",
                            2074,
                            v24);
LABEL_46:
      if ( (int)v26 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v26, v27);
LABEL_48:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v26);
      goto LABEL_49;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_EcoQos>::__private_GetVariant(&`wil::Feature<__WilFeatureTraits_Feature_Update_EcoQos>::GetImpl'::`2'::impl) == 1 )
      {
        LogAdapter::TraceInfo<>("GenerateDownloadList: Enabling EcoQos for thread");
        v29 = CDeploymentSession::SetEcoQos(this, v28);
        if ( v29 < 0 )
          LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)v29, "GenerateDownloadList: Error requesting EcoQos");
      }
    }
    *((_DWORD *)this + 92) = 2;
    if ( *((_DWORD *)this + 186) == 1 )
    {
      v30 = 2;
    }
    else if ( *((_DWORD *)this + 186) == 2 )
    {
      v30 = 4;
    }
    else
    {
      v30 = 0;
    }
    if ( *((_QWORD *)this + 76) )
    {
      if ( v30 )
      {
        LogAdapter::TraceInfo<>("GenerateDownloadList: Adjusting thread priority...");
        v31 = CDeploymentSession::AdjustPriority(this, v30, &v357);
        v21 = v31;
        if ( v31 < 0 )
        {
          v32 = *((_QWORD *)this + 75);
          if ( !v32 )
            goto LABEL_44;
          cchCount2b = v31;
          LODWORD(lpString2) = 2092;
          goto LABEL_64;
        }
      }
      else
      {
        v33 = *((_DWORD *)this + 114);
        if ( v33 == 3 || v33 == 24 )
        {
          CDeploymentSession::GetUserSessionId((char *)this + 24, &v305);
          v34 = L"TRUE";
          v35 = BYTE4(v305);
          if ( !BYTE4(v305) )
            v34 = L"FALSE";
          v329 = v34;
          LogAdapter::TraceInfo<wchar_t const *>("GenerateDownloadList: User session found = [{}].", &v329);
          if ( !v35 )
          {
            LogAdapter::TraceInfo<>("GenerateDownloadList: Adjusting thread priority...");
            v36 = CDeploymentSession::AdjustPriority(this, *((unsigned int *)this + 92), &v357);
            v21 = v36;
            if ( v36 < 0 )
            {
              v32 = *((_QWORD *)this + 75);
              if ( !v32 )
                goto LABEL_44;
              cchCount2b = v36;
              LODWORD(lpString2) = 2105;
              goto LABEL_64;
            }
          }
          v17 = v286;
        }
      }
    }
    v21 = CMoUpdateHelpersT<CEmptyType>::IsSkipDeleteCorruptFile(&v300);
    if ( v21 < 0 )
    {
      v32 = *((_QWORD *)this + 75);
      if ( !v32 )
        goto LABEL_44;
      cchCount2b = v21;
      LODWORD(lpString2) = 2109;
      goto LABEL_64;
    }
    v37 = *((_QWORD *)this + 69);
    if ( v37 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v37 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      *((_QWORD *)this + 69) = 0;
    }
    v39 = CDeploymentSession::ProcessSandboxContainerPayload(this, (__int64)v17, a3, a4, 0);
    v21 = v39;
    v40 = 0;
    if ( v39 < 0 )
    {
      v41 = *((_QWORD *)this + 75);
      if ( v41 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v41,
          4,
          L"ProcessSandboxContainerPayload for GenerateDownloadList failed: [0x%X]",
          (unsigned int)v39);
      v32 = *((_QWORD *)this + 75);
      if ( !v32 )
        goto LABEL_44;
      cchCount2b = v21;
      LODWORD(lpString2) = 2121;
LABEL_64:
      v26 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                            v32,
                            4,
                            L"%s(%d): Result = 0x%X",
                            L"CDeploymentSession::GenerateDownloadList",
                            lpString2,
                            cchCount2b);
      goto LABEL_46;
    }
    if ( !*((_BYTE *)this + 128) || *((_DWORD *)this + 83) == 3 )
    {
      v42 = *((_QWORD *)v17 + 11);
      v43 = v42 + 168LL * *((unsigned int *)v17 + 24);
      while ( 1 )
      {
        if ( v42 == v43 )
        {
          if ( *((_DWORD *)this + 83) == 3 )
            *((_DWORD *)this + 83) = 4;
          goto LABEL_104;
        }
        if ( *(_DWORD *)(v42 + 88) == 7 )
          break;
        v42 += 168;
      }
      v307 = 0;
      v44 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&v307);
      v45 = CMiscHelpersT<CEmptyType>::CombinePath(
              *((_QWORD *)this + 61),
              *(_QWORD *)(*(_QWORD *)(v42 + 112) + 24LL),
              0,
              v44);
      v21 = v45;
      if ( v45 < 0 )
      {
        v46 = *((_QWORD *)this + 75);
        if ( v46 )
        {
          LODWORD(lpString2) = 2133;
          v48 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v46,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDeploymentSession::GenerateDownloadList",
                  lpString2,
                  v45);
          v47 = (unsigned int)v48;
          if ( v48 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v48, v49);
        }
        else
        {
          v47 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v47);
        v50 = v307;
        if ( v307 )
        {
          v51 = GetProcessHeap();
          HeapFree(v51, 0, (LPVOID)(v50 - 4));
          v26 = 0;
          goto LABEL_48;
        }
LABEL_49:
        v274 = v284;
        goto LABEL_705;
      }
      v52 = to_wstring(v348, v307);
      v53 = (_OWORD *)((char *)this + 96);
      if ( *((_BYTE *)this + 128) )
      {
        std::wstring::operator=(v53, v52);
      }
      else
      {
        *v53 = 0;
        *((_QWORD *)this + 14) = 0;
        *((_QWORD *)this + 15) = 0;
        *v53 = *(_OWORD *)v52;
        *((_OWORD *)this + 7) = *(_OWORD *)(v52 + 16);
        *(_QWORD *)(v52 + 16) = 0;
        *(_QWORD *)(v52 + 24) = 7;
        *(_WORD *)v52 = 0;
        *((_BYTE *)this + 128) = 1;
      }
      std::wstring::~wstring(v348);
      v54 = v307;
      if ( v307 )
      {
        v55 = GetProcessHeap();
        HeapFree(v55, 0, (LPVOID)(v54 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
    }
LABEL_104:
    v297 = 0;
    v306 = 0;
    v281 = 0;
    v305 = 0;
    v282 = 0;
    v277 = 0;
    v289 = 0;
    v290 = 0;
    v299 = 0;
    v310 = 0;
    v309 = 0;
    v308 = 0;
    v291 = 0;
    v292 = 0;
    v293 = 0;
    v294 = 0;
    v295 = 0;
    v296 = 0;
    v56 = *((_QWORD *)v17 + 8);
    v57 = (int *)(v56 + 168LL * *((unsigned int *)v17 + 18));
    v298 = v57;
    v274 = v284;
    while ( 1 )
    {
      v271 = v56;
      if ( (int *)v56 == v57 )
      {
        if ( *((_DWORD *)this + 66) && *((_DWORD *)this + 67) )
          *((_DWORD *)this + 66) = 0;
        v351 = 0;
        v356 = 0;
        v224 = (*(__int64 (__fastcall **)(CDeploymentDownloadRequest *, __int64 *))(*(_QWORD *)v274 + 40LL))(
                 v274,
                 &v351);
        v21 = v224;
        if ( v224 < 0 )
        {
          v225 = 2660;
          v226 = *((_QWORD *)this + 75);
LABEL_605:
          CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
            v226,
            (unsigned int)v224,
            L"CDeploymentSession::GenerateDownloadList",
            v225);
          goto LABEL_606;
        }
        v224 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v351 + 24LL))(v351, &v356);
        v21 = v224;
        v226 = *((_QWORD *)this + 75);
        if ( v224 < 0 )
        {
          v225 = 2661;
          goto LABEL_605;
        }
        if ( v226 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v226, 1, L"Total file requests: [%lu]", v356);
        for ( i = 0; i < v356; ++i )
        {
          v352 = 0;
          v353 = 0;
          v349 = 0;
          pv = 0;
          v355 = 0;
          v228 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v351 + 32LL))(v351, i, &v352);
          v21 = v228;
          if ( v228 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v228,
              L"CDeploymentSession::GenerateDownloadList",
              2673);
            goto LABEL_615;
          }
          v229 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v352 + 24LL))(v352, &v349);
          v21 = v229;
          if ( v229 < 0 )
          {
            v230 = 2674;
            goto LABEL_622;
          }
          v21 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v352 + 40LL))(v352, &pv);
          if ( v21 < 0 )
          {
            v230 = 2675;
            v232 = (unsigned int)v21;
            v231 = *((_QWORD *)this + 75);
            goto LABEL_624;
          }
          if ( *((_QWORD *)this + 75) )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(*((_QWORD *)this + 75), 1, L"Requested file: %ws, hash: %ws");
          v229 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v352 + 48LL))(v352, &v353);
          v21 = v229;
          if ( v229 < 0 )
          {
            v230 = 2680;
LABEL_622:
            v231 = *((_QWORD *)this + 75);
            goto LABEL_623;
          }
          v229 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v353 + 24LL))(v353, &v355);
          v21 = v229;
          v231 = *((_QWORD *)this + 75);
          if ( v229 < 0 )
          {
            v230 = 2681;
LABEL_623:
            v232 = (unsigned int)v229;
LABEL_624:
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(v231, v232, L"CDeploymentSession::GenerateDownloadList", v230);
            goto LABEL_615;
          }
          if ( v231 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v231, 1, L"  Total range requests for file: [%lu]", v355);
          for ( j = 0; j < v355; ++j )
          {
            v354 = 0;
            v366 = 0;
            v365 = 0;
            v234 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v353 + 32LL))(v353, j, &v354);
            v21 = v234;
            if ( v234 < 0 )
            {
              v235 = 2691;
LABEL_639:
              v236 = *((_QWORD *)this + 75);
              goto LABEL_640;
            }
            v234 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v354 + 24LL))(v354, &v366);
            v21 = v234;
            if ( v234 < 0 )
            {
              v235 = 2692;
              goto LABEL_639;
            }
            v234 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v354 + 32LL))(v354, &v365);
            v21 = v234;
            v236 = *((_QWORD *)this + 75);
            if ( v234 < 0 )
            {
              v235 = 2693;
LABEL_640:
              CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                v236,
                (unsigned int)v234,
                L"CDeploymentSession::GenerateDownloadList",
                v235);
              SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v354);
LABEL_615:
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              if ( v349 )
              {
                CoTaskMemFree(v349);
                v349 = 0;
              }
              SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v353);
              SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v352);
LABEL_606:
              SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v351);
              goto LABEL_705;
            }
            if ( v236 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v236,
                1,
                L"  Requested range #%llu offset: %llu, length: %llu",
                j,
                v366,
                v365);
            SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v354);
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( v349 )
          {
            CoTaskMemFree(v349);
            v349 = 0;
          }
          SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v353);
          SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v352);
        }
        SP_COM<IUpdateDiagnostics>::~SP_COM<IUpdateDiagnostics>(&v351);
        v237 = *((_QWORD *)this + 75);
        v238 = v297;
        if ( v237 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v237, 2, L"Required size of the Download: [%llu]", v297);
        v239 = *((_QWORD *)this + 75);
        if ( v239 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v239, 2, L"Total Expanded size : [%llu]", v306);
        v240 = *((_QWORD *)this + 75);
        if ( v240 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v240, 2, L"Required size of the required Download: [%llu]", v281);
        v241 = *((_QWORD *)this + 75);
        if ( v241 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v241, 2, L"Required Expanded size : [%llu]", v282);
        v242 = *((_QWORD *)this + 75);
        if ( v242 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v242, 2, L"Setting total size of the Request: [%llu]", v238);
        v243 = v274;
        ExpressDownloadList = CDeploymentDownloadRequest::SetTotalRequestSize(v274, v238, v283 == 0);
        v21 = ExpressDownloadList;
        if ( ExpressDownloadList < 0 )
        {
          v178 = 2705;
          goto LABEL_415;
        }
        v244 = 0;
        if ( v238 )
        {
          *((_QWORD *)this + 47) = v238;
          goto LABEL_667;
        }
        v246 = *((_DWORD *)this + 114);
        if ( v246 == 25 || v246 == 4 || (v247 = 0, v246 == 22) )
          v247 = 1;
        if ( (*((_BYTE *)this + 372) & 0x20) != 0 && v246 <= 0x18 )
        {
          v248 = 20971544;
          if ( !_bittest(&v248, v246) )
            goto LABEL_677;
          goto LABEL_679;
        }
        v248 = 20971544;
LABEL_677:
        if ( *((int *)this + 83) < 2 && *((_BYTE *)this + 128) )
LABEL_679:
          v247 = 0;
        if ( *((_BYTE *)this + 336) || !v247 )
        {
LABEL_667:
          v245 = v286;
        }
        else
        {
          v249 = *((_QWORD *)this + 58);
          if ( *((_DWORD *)this + 83) == 2 && *((_BYTE *)this + 128) )
          {
            v250 = (const WCHAR *)((char *)this + 96);
            v251 = *((_QWORD *)this + 14);
            if ( *((_QWORD *)this + 15) > 7u )
              v250 = *(const WCHAR **)v250;
            v325 = v250;
            v326 = v251;
            std::optional<std::wstring>::operator=<wil::basic_zstring_view<wchar_t> &,0>(v249 + 136, &v325);
          }
          v245 = v286;
          if ( !*((_DWORD *)this + 57) )
          {
            ExpressDownloadList = CDeploymentSession::Expand(this, v286);
            v21 = ExpressDownloadList;
            if ( ExpressDownloadList < 0 )
            {
              v178 = 2750;
              goto LABEL_415;
            }
          }
          if ( *((_DWORD *)v245 + 60) && (v252 = *((_DWORD *)this + 114), v252 <= 0x18) && _bittest(&v248, v252) )
          {
            ExpressDownloadList = CDeploymentSession::ComposePayloads(this, v245);
            v21 = ExpressDownloadList;
            v244 = 1;
            if ( ExpressDownloadList < 0 )
            {
              v178 = 2758;
              goto LABEL_415;
            }
          }
          else
          {
            v244 = 0;
          }
          v358 = 0;
          v302 = -2145116147;
          v21 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v249 + 200LL))(
                  v249,
                  4096,
                  *((_QWORD *)this + 63),
                  &v358);
          v253 = &v302;
          do
          {
            if ( v21 == *v253 )
            {
              v21 = 0;
              goto LABEL_702;
            }
            ++v253;
          }
          while ( v253 != (int *)&v303 );
          if ( v21 >= 0 )
LABEL_702:
            *((_BYTE *)this + 336) = 1;
          v238 = v297;
        }
        v254 = v327;
        *(_OWORD *)v327 = v313;
        *((_OWORD *)v254 + 1) = v314;
        *((_OWORD *)v254 + 2) = v315;
        *((_OWORD *)v254 + 3) = v316;
        *((_QWORD *)v254 + 8) = v317;
        *v324 = v238;
        *v323 = v306;
        *v319 = v281;
        *v320 = v282;
        v255 = v328;
        *((_DWORD *)v328 + 33) = v244;
        *((_DWORD *)v255 + 6) = v277;
        *((_DWORD *)v255 + 28) = *((_DWORD *)this + 87);
        *((_DWORD *)v255 + 12) = *((_DWORD *)v245 + 18);
        *((_DWORD *)v255 + 13) = v289;
        *((_DWORD *)v255 + 14) = v290;
        *((_QWORD *)v255 + 8) = v299;
        *((_QWORD *)v255 + 9) = v310;
        *((_QWORD *)v255 + 10) = v309;
        *((_QWORD *)v255 + 11) = v308;
        *((_DWORD *)v255 + 24) = v291;
        *((_DWORD *)v255 + 25) = v292;
        *((_DWORD *)v255 + 26) = v293;
        *((_DWORD *)v255 + 27) = v294;
        *((_DWORD *)v255 + 32) = v295;
        *((_DWORD *)v255 + 34) = v296;
        v274 = 0;
        *v318 = v243;
        goto LABEL_705;
      }
      v361 = 0;
      v58 = *(_DWORD *)(v56 + 88);
      if ( v58 == 24 )
      {
        v59 = *((_QWORD *)this + 75);
        if ( !v59 )
          goto LABEL_110;
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v59,
          2,
          L"Skipping UUP Product package download from ActionList [%ws]",
          *(_QWORD *)(v271 + 56));
        goto LABEL_109;
      }
      v285 = 0;
      v60 = 0;
      v288 = 0;
      v287 = 0;
      v311 = 0;
      v276 = 0;
      v270 = 0;
      if ( v58 <= 0xF )
      {
        v61 = 36992;
        if ( _bittest(&v61, v58) )
          break;
      }
      v62 = v271;
      if ( *(_DWORD *)(v271 + 104) == 2 || *((_DWORD *)this + 114) == 8 )
        goto LABEL_117;
      v21 = 0;
      v63 = 0;
LABEL_118:
      v272 = v63;
      v64 = *((_DWORD *)this + 114);
      if ( (v64 == 3 || v64 == 24)
        && ((v65 = *((_QWORD *)this + 49)) != 0
          ? (v66 = (int *)*((_QWORD *)this + 49), v57 = v66)
          : (v65 = 0, v66 = 0, v57 = 0),
            v67 = (int *)(v65 + 4LL * *((int *)this + 97)),
            v66 != v67) )
      {
        while ( *(_DWORD *)(v62 + 88) != *v57 )
        {
          if ( ++v57 == v67 )
            goto LABEL_126;
        }
        v268 = 1;
      }
      else
      {
LABEL_126:
        v268 = 0;
      }
      v68 = *(const wchar_t ***)(v62 + 112);
      v69 = &v68[23 * *(unsigned int *)(v62 + 120)];
      v322 = v69;
      while ( 1 )
      {
        v312 = v68;
        if ( v68 == v69 )
        {
          v137 = v274;
          goto LABEL_397;
        }
        lpFileName = 0;
        v359 = 0;
        v70 = CDeploymentSession::CheckCancelRequested(this, v57);
        v21 = v70;
        v71 = 0;
        if ( v70 < 0 )
        {
          v72 = *((_QWORD *)this + 75);
          if ( !v72 )
            goto LABEL_131;
          cchCount2[0] = v70;
          LODWORD(lpString2) = 2177;
          v73 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v72,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GenerateDownloadList",
                                lpString2,
                                *(_QWORD *)cchCount2);
LABEL_134:
          if ( (int)v73 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v73, v74);
          goto LABEL_136;
        }
        if ( (unsigned int)(*(_DWORD *)(v62 + 88) - 5) <= 1 )
        {
          if ( v296 + 1 < v296 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, 0);
          }
          else
          {
            ++v296;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v77 = *((_QWORD *)this + 75);
            if ( v77 )
            {
              cchCount2[0] = v21;
              LODWORD(lpString2) = 2181;
              goto LABEL_145;
            }
LABEL_131:
            v73 = 0;
LABEL_136:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v73);
            v75 = lpFileName;
            if ( lpFileName )
            {
              v76 = GetProcessHeap();
              HeapFree(v76, 0, (LPVOID)(v75 - 2));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
              lpFileName = 0;
            }
LABEL_705:
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
            __1__lambda_call_V_lambda_1___2__GenerateDownloadList_CDeploymentSession__QEAAJPEAUActionList__HHHHPEB_WKPEA_K222PEAU_DUPackageInfo__PEAU_ReportEventDownloadRequestParams__PEAPEAUIDeploymentDownloadRequest___Z__details_wil__QEAA_XZ(v344);
            std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>(v369);
            if ( v274 )
              (*(void (__fastcall **)(CDeploymentDownloadRequest *))(*(_QWORD *)v274 + 16LL))(v274);
            return (unsigned int)v21;
          }
        }
        if ( (unsigned __int64)*v68 + v60 < v60 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v71);
        }
        else
        {
          v288 = (unsigned __int64)*v68 + v60;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v77 = *((_QWORD *)this + 75);
          if ( !v77 )
            goto LABEL_131;
          cchCount2[0] = v21;
          LODWORD(lpString2) = 2184;
LABEL_145:
          v73 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v77,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::GenerateDownloadList",
                                lpString2,
                                *(_QWORD *)cchCount2,
                                v264,
                                v265,
                                v266,
                                v267);
          goto LABEL_134;
        }
        if ( v283 && !v63 )
        {
          v78 = lpFileName;
          if ( lpFileName )
          {
            v79 = GetProcessHeap();
            HeapFree(v79, 0, (LPVOID)(v78 - 2));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            lpFileName = 0;
          }
          goto LABEL_395;
        }
        v80 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v68[3], 0, &lpFileName);
        v21 = v80;
        if ( v80 < 0 )
        {
          v81 = *((_QWORD *)this + 75);
          if ( v81 )
          {
            cchCount2[0] = v80;
            LODWORD(lpString2) = 2196;
            v82 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                  v81,
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
        v85 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
        LODWORD(v275) = v85;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( v85 )
        {
          FileSize = CMoUpdateHelpersT<CEmptyType>::GetFileSize(lpFileName, &v359);
          v21 = FileSize;
          if ( FileSize < 0 )
          {
            v88 = *((_QWORD *)this + 75);
            if ( v88 )
            {
              cchCount2[0] = FileSize;
              LODWORD(lpString2) = 2201;
              goto LABEL_171;
            }
LABEL_158:
            v82 = 0;
            goto LABEL_162;
          }
          if ( !v359 )
          {
            v89 = *((_QWORD *)this + 75);
            if ( v89 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v89, 2, L"Deleting zero byte file: [%ws]", lpFileName);
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
              v82 = 0;
              if ( v21 < 0 && *((_QWORD *)this + 75) )
              {
                cchCount2[0] = v21;
                LODWORD(lpString2) = 2205;
                v88 = *((_QWORD *)this + 75);
LABEL_171:
                v82 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                      v88,
                                      4,
                                      L"%s(%d): Result = 0x%X",
                                      L"CDeploymentSession::GenerateDownloadList",
                                      lpString2,
                                      *(_QWORD *)cchCount2,
                                      v264,
                                      v265,
                                      v266,
                                      v267);
LABEL_160:
                if ( (int)v82 < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v82, v83);
              }
LABEL_162:
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v82);
LABEL_163:
              DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
              goto LABEL_705;
            }
            v277 = 1;
            v85 = 0;
            LODWORD(v275) = 0;
          }
          if ( v85 && a5 && !v63 )
          {
            memset(v370, 0, sizeof(v370));
            v91 = 0;
            v278 = 0;
            v92 = *((_QWORD *)this + 75);
            if ( v92 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v92, 2, L"Validating payload file [%ws]", v68[3]);
            if ( v68[5] )
            {
              v93 = CDlpHelpersT<CEmptyType>::CalculateHash(lpFileName);
              v21 = v93;
              if ( v93 < 0 )
              {
                v96 = 2222;
LABEL_192:
                v97 = (unsigned int)v93;
LABEL_193:
                CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                  *((_QWORD *)this + 75),
                  v97,
                  L"CDeploymentSession::GenerateDownloadList",
                  v96);
                DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v278);
                goto LABEL_163;
              }
              v93 = CStringConvertT<unsigned long>::Base64Encode(v370, v94, v95, &v278);
              v21 = v93;
              if ( v93 < 0 )
              {
                v96 = 2223;
                goto LABEL_192;
              }
              v91 = (const WCHAR *)v278;
            }
            v98 = v68[5];
            if ( v98 )
            {
              if ( CompareStringW(0x409u, 1u, v91, -1, v98, -1) != 2 )
              {
                v100 = *((_QWORD *)this + 75);
                if ( v300 )
                {
                  if ( v100 )
                    CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v100,
                      3,
                      L"File hash doesn't match but file was not deleted in Test Mode.");
                }
                else
                {
                  if ( v100 )
                  {
                    lpString2 = v68[5];
                    CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                      v100,
                      2,
                      L"Deleting corrupt payload file. Actual hash: [%ws], Expected Hash: [%ws]",
                      v91);
                  }
                  if ( !DeleteFileW(lpFileName) )
                  {
                    v101 = GetLastError();
                    v21 = v101;
                    if ( v101 )
                    {
                      if ( v101 > 0 )
                        v21 = (unsigned __int16)v101 | 0x80070000;
                    }
                    else
                    {
                      v21 = -2147467259;
                    }
                    v96 = 2240;
                    v97 = (unsigned int)v21;
                    goto LABEL_193;
                  }
                  v277 = 1;
                  v85 = 0;
                  LODWORD(v275) = 0;
                }
              }
            }
            else
            {
              v99 = *((_QWORD *)this + 75);
              if ( v99 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v99,
                  3,
                  L"Expected hash not available; assuming hashless CompDB and skipping validation.");
            }
            DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&v278);
          }
        }
        v102 = v271;
        v103 = *(_DWORD *)(v271 + 104);
        if ( v103 )
        {
          v104 = v103 - 1;
          if ( v104 )
          {
            v105 = v104 - 1;
            if ( v105 )
            {
              v106 = v105 - 2;
              if ( v106 )
              {
                v107 = v106 - 1;
                if ( v107 )
                {
                  if ( v107 != 1 )
                  {
                    v258 = (const char *)(unsigned int)EnsureNTSTATUS<long>(2147549183LL);
                    wil::details::in1diag3::Throw_Hr(
                      retaddr,
                      (void *)0x7B9,
                      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                      v258,
                      (int)lpString2);
                  }
                  v108 = L"Bundle";
                }
                else
                {
                  v108 = L"ReverseDiff";
                }
              }
              else
              {
                v108 = L"PSFX";
              }
            }
            else
            {
              v108 = L"Express";
            }
          }
          else
          {
            v108 = L"Diff";
          }
        }
        else
        {
          v108 = L"Canonical";
        }
        if ( v85 )
        {
          v109 = *((_QWORD *)this + 75);
          if ( v109 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v109, 2, L"File exists: [%ws]", v68[3]);
          if ( v287 + v359 < v287 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v86);
          }
          else
          {
            v287 += v359;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v112 = 2258;
            goto LABEL_234;
          }
        }
        else
        {
          v273 = 0;
          v114 = *(_DWORD *)(v271 + 104);
          if ( v114 )
          {
            v115 = v114 - 1;
            if ( v115 )
            {
              v116 = v115 - 1;
              if ( v116 )
              {
                v117 = v116 - 2;
                if ( v117 )
                {
                  v118 = v117 - 1;
                  if ( v118 )
                  {
                    if ( v118 != 1 )
                    {
                      v119 = 2310;
                      v21 = -2147418113;
LABEL_243:
                      v120 = (unsigned int)v21;
                      goto LABEL_254;
                    }
                  }
                  else
                  {
                    ++v276;
                    v86 = (wchar_t **)((char *)this + 552);
                    if ( !*((_QWORD *)this + 69) )
                    {
                      OuterContainerDownloadList = STRAPI_Create(v68[17], v86);
                      v21 = OuterContainerDownloadList;
                      if ( OuterContainerDownloadList < 0 )
                      {
                        v119 = 2290;
                        goto LABEL_253;
                      }
                    }
                  }
                }
              }
              else
              {
                v86 = (wchar_t **)((char *)this + 552);
                if ( !*((_QWORD *)this + 69) )
                {
                  OuterContainerDownloadList = STRAPI_Create(v68[17], v86);
                  v21 = OuterContainerDownloadList;
                  if ( OuterContainerDownloadList < 0 )
                  {
                    v119 = 2298;
                    goto LABEL_253;
                  }
                }
              }
            }
            else
            {
              ++v276;
              v86 = (wchar_t **)((char *)this + 552);
              if ( !*((_QWORD *)this + 69) )
              {
                OuterContainerDownloadList = STRAPI_Create(v68[17], v86);
                v21 = OuterContainerDownloadList;
                if ( OuterContainerDownloadList < 0 )
                {
                  v119 = 2279;
                  goto LABEL_253;
                }
              }
            }
          }
          if ( (unsigned __int64)*v68 + v285 < v285 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v86);
          }
          else
          {
            v285 += (unsigned __int64)*v68;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v119 = 2314;
            goto LABEL_243;
          }
          v122 = *((_QWORD *)this + 75);
          if ( v68[6] )
          {
            if ( v122 )
            {
              v123 = L"TRUE";
              if ( !v268 )
                v123 = L"FALSE";
              v267 = (__int64)v68[2];
              v266 = (__int64)v68[7];
              v265 = (__int64)v68[8];
              v264 = (struct CDeploymentFileRequest **)v68[6];
              *(_QWORD *)cchCount2 = v68[3];
              LODWORD(lpString2) = *(_DWORD *)(v271 + 88);
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v122,
                2,
                L"Adding file: Optional = [%ws], Category = [%u], FileName = [%ws], Container = [%ws], Hash = [%ws], Cix ="
                 " [%ws], payloadName = [%ws]",
                v123);
            }
            OuterContainerDownloadList = CDeploymentSession::GenerateOuterContainerDownloadList(
                                           this,
                                           (const struct ActionList::Payload *const)v68,
                                           v108,
                                           v274);
            v21 = OuterContainerDownloadList;
            if ( OuterContainerDownloadList < 0 )
            {
              v119 = 2329;
              goto LABEL_253;
            }
          }
          else
          {
            if ( v122 )
            {
              v124 = L"TRUE";
              if ( !v268 )
                v124 = L"FALSE";
              LODWORD(lpString2) = *(_DWORD *)(v271 + 88);
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v122,
                2,
                L"Adding file: Optional = [%ws], Category = [%u], FileName = [%ws]",
                v124,
                lpString2,
                v68[3],
                v264,
                v265,
                v266,
                v267);
            }
            OuterContainerDownloadList = CDeploymentFileRequest::Create(
                                           v68[5],
                                           v68[3],
                                           v68[2],
                                           v68[4],
                                           v108,
                                           v268,
                                           &v273);
            v21 = OuterContainerDownloadList;
            if ( OuterContainerDownloadList < 0 )
            {
              v119 = 2344;
              goto LABEL_253;
            }
            v125 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v330, &v273);
            OuterContainerDownloadList = CDeploymentDownloadRequest::AppendFileRequest(v274, v125);
            v21 = OuterContainerDownloadList;
            if ( OuterContainerDownloadList < 0 )
            {
              v119 = 2345;
LABEL_253:
              v120 = (unsigned int)OuterContainerDownloadList;
LABEL_254:
              CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                *((_QWORD *)this + 75),
                v120,
                L"CDeploymentSession::GenerateDownloadList",
                v119);
              if ( v273 )
              {
                (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v273 + 16LL))(v273);
                v273 = 0;
              }
              goto LABEL_163;
            }
          }
          if ( v273 )
          {
            (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v273 + 16LL))(v273);
            v273 = 0;
          }
          v102 = v271;
        }
        if ( !v68[10] || !a5 || *(_DWORD *)(v102 + 104) != 2 )
          goto LABEL_301;
        SH_SSTRING::operator=(&lpFileName);
        v126 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v68[10], 0, &lpFileName);
        v21 = v126;
        if ( v126 < 0 )
        {
          v112 = 2356;
LABEL_284:
          v113 = (unsigned int)v126;
          goto LABEL_235;
        }
        v126 = CMiscHelpersT<CEmptyType>::FileExists(lpFileName, &v275);
        v21 = v126;
        if ( v126 < 0 )
        {
          v112 = 2357;
          goto LABEL_284;
        }
        if ( (_DWORD)v275 )
        {
          v126 = CMoUpdateHelpersT<CEmptyType>::GetFileSize(lpFileName, &v359);
          v21 = v126;
          if ( v126 < 0 )
          {
            v112 = 2361;
            goto LABEL_284;
          }
          if ( v287 + v359 < v287 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v127);
          }
          else
          {
            v287 += v359;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v112 = 2362;
            goto LABEL_234;
          }
          v129 = 1;
          v270 = 1;
          if ( *((_BYTE *)v68 + 153) )
          {
            if ( v311 + v359 < v311 )
            {
              v21 = -2147024362;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v128);
            }
            else
            {
              v311 += v359;
              v21 = 0;
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
            if ( v21 < 0 )
            {
              v112 = 2367;
LABEL_234:
              v113 = (unsigned int)v21;
LABEL_235:
              CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
                *((_QWORD *)this + 75),
                v113,
                L"CDeploymentSession::GenerateDownloadList",
                v112);
              goto LABEL_163;
            }
          }
        }
        else
        {
LABEL_301:
          v129 = v270;
        }
        if ( v283 && v68[14] && v68[9] && !v301 )
          break;
        v62 = v271;
LABEL_328:
        v304 = 0;
        v278 = 0;
        v275 = 0;
        if ( v283 )
          goto LABEL_394;
        v138 = *((_DWORD *)this + 114);
        if ( v138 > 0x16 )
          goto LABEL_394;
        v139 = 4195440;
        if ( !_bittest(&v139, v138) || *(_DWORD *)(v62 + 104) != 2 )
          goto LABEL_394;
        SH_SSTRING::operator=(&lpFileName);
        v126 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), v68[2], 0, &lpFileName);
        v21 = v126;
        if ( v126 < 0 )
        {
          v112 = 2433;
          goto LABEL_284;
        }
        v140 = -1;
        v141 = -1;
        do
          ++v141;
        while ( *(_WORD *)(*((_QWORD *)this + 61) + 2 * v141) );
        do
          ++v140;
        while ( lpFileName[v140] );
        v334[0] = *((_QWORD *)this + 61);
        v334[1] = v141;
        v325 = lpFileName;
        v326 = v140;
        v126 = CheckIfHistoryCixIsPresent(
                 (unsigned int)&v325,
                 (unsigned int)v334,
                 (unsigned int)&v304,
                 (unsigned int)&v278,
                 (__int64)&v275);
        v21 = v126;
        if ( v126 < 0 )
        {
          v112 = 2435;
          goto LABEL_284;
        }
        v142 = v278;
        if ( v278 )
        {
          v143 = v68[9];
          Src = 0;
          v363 = 0;
          v364 = 0;
          v144 = -1;
          do
            ++v144;
          while ( v143[v144] );
          std::wstring::_Construct<1,wchar_t const *>(&Src, v143, v144);
          v341 = 0;
          v342 = 0;
          v343 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v341, L".historycix.cab", 15);
          v338 = 0;
          v339 = 0;
          v340 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v338, L".psf", 4);
          ReplaceAll<std::wstring>(&Src);
          std::wstring::~wstring(&v338);
          std::wstring::~wstring(&v341);
          if ( v142 + v285 < v285 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v145);
          }
          else
          {
            v285 += v142;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v147 = 2445;
            goto LABEL_347;
          }
          if ( v142 + v288 < v288 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v146);
          }
          else
          {
            v288 += v142;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v147 = 2446;
            goto LABEL_347;
          }
          if ( (unsigned __int64)v275 + v361 < v361 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v149);
          }
          else
          {
            v361 += (__int64)v275;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v147 = 2447;
LABEL_347:
            v148 = (unsigned int)v21;
LABEL_348:
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              v148,
              L"CDeploymentSession::GenerateDownloadList",
              v147);
            goto LABEL_349;
          }
          v150 = v68[11];
          p_Src = (const wchar_t *)&Src;
          if ( v364 > 7 )
            p_Src = (const wchar_t *)Src;
          v152 = 0;
          v321 = 0;
          v153 = v312[6];
          if ( v153 )
          {
            v154 = v312[8];
            OffsetInOuterContainer = CDeploymentSession::GetOffsetInOuterContainer(
                                       this,
                                       v153,
                                       0,
                                       v312[9],
                                       v312[14],
                                       &v321,
                                       0);
            v21 = OffsetInOuterContainer;
            if ( OffsetInOuterContainer < 0 )
            {
              v147 = 2464;
              v148 = (unsigned int)OffsetInOuterContainer;
              goto LABEL_348;
            }
            v152 = v321;
          }
          else
          {
            v154 = v312[5];
            v153 = v312[2];
          }
          v156 = *((_QWORD *)this + 75);
          if ( v156 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v156,
              2,
              L"    Adding HistoryCIX file: [%s] with Hash [%s]",
              p_Src,
              v154);
          v157 = *((_QWORD *)this + 75);
          if ( v157 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v157, 2, L"    Download size : [%llu]", v278);
          v158 = *((_QWORD *)this + 75);
          if ( v158 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v158, 2, L"    Expand size : [%llu]", v275);
          v275 = 0;
          v159 = CDeploymentFileRequest::Create(v154, p_Src, v153, v150, L"Express", v268, &v275);
          v21 = v159;
          if ( v159 < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v159,
              L"CDeploymentSession::GenerateDownloadList",
              2483);
            goto LABEL_375;
          }
          v280 = 0;
          v161 = CDeploymentFileRange::Create(v152 + v304, v278, &v280);
          v21 = v161;
          if ( v161 < 0 )
          {
            v162 = 2486;
            goto LABEL_380;
          }
          v163 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v332, &v280);
          v164 = v275;
          appended = CDeploymentFileRequest::AppendExpressFileRange(v275, v163);
          v21 = appended;
          if ( appended < 0 )
          {
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)appended,
              L"CDeploymentSession::GenerateDownloadList",
              2487);
            if ( v280 )
            {
              (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v280 + 16LL))(v280);
              v280 = 0;
            }
            if ( v164 )
            {
              v160 = *(_QWORD *)v164;
LABEL_377:
              (*(void (**)(void))(v160 + 16))();
            }
            goto LABEL_349;
          }
          v166 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v333, &v275);
          v161 = CDeploymentDownloadRequest::AppendFileRequest(v274, v166);
          v21 = v161;
          if ( v161 < 0 )
          {
            v162 = 2489;
LABEL_380:
            CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
              *((_QWORD *)this + 75),
              (unsigned int)v161,
              L"CDeploymentSession::GenerateDownloadList",
              v162);
            if ( v280 )
            {
              (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v280 + 16LL))(v280);
              v280 = 0;
            }
LABEL_375:
            if ( v275 )
            {
              v160 = *(_QWORD *)v275;
              goto LABEL_377;
            }
LABEL_349:
            std::wstring::~wstring(&Src);
            goto LABEL_163;
          }
          v40 = 1;
          if ( v280 )
          {
            (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v280 + 16LL))(v280);
            v280 = 0;
          }
          if ( v275 )
            (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v275 + 16LL))(v275);
          std::wstring::~wstring(&Src);
          DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
          v68 = v312;
          v62 = v271;
        }
        else
        {
LABEL_394:
          DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
        }
LABEL_395:
        v68 += 23;
        v69 = v322;
        v63 = v272;
        v60 = v288;
        v21 = 0;
      }
      v130 = v129 == 0;
      v62 = v271;
      if ( !v130 || *((_BYTE *)v68 + 153) || *(_DWORD *)(v271 + 104) != 2 )
        goto LABEL_328;
      v279 = 0;
      if ( !v68[8] || (v131 = v68 + 6, !v68[6]) )
      {
        v132 = CDeploymentFileRequest::Create(v68[14], v68[9], v68[9], v68[11], L"Canonical", v268, &v279);
        v21 = v132;
        if ( v132 >= 0 )
          goto LABEL_320;
        v133 = 2412;
LABEL_314:
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          (unsigned int)v132,
          L"CDeploymentSession::GenerateDownloadList",
          v133);
        if ( v279 )
        {
          (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v279 + 16LL))(v279);
          v279 = 0;
        }
        goto LABEL_163;
      }
      if ( !(unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::contains<wchar_t *>(
                               (char *)this + 768,
                               v68 + 6,
                               v110,
                               v111) )
      {
        v132 = CDeploymentFileRequest::Create(v68[8], *v131, *v131, 0, L"Canonical", v268, &v279);
        v21 = v132;
        if ( v132 < 0 )
        {
          v133 = 2397;
          goto LABEL_314;
        }
        v134 = *v131;
        v335 = 0;
        v336 = 0;
        v337 = 0;
        v135 = -1;
        do
          ++v135;
        while ( v134[v135] );
        std::wstring::_Construct<1,wchar_t const *>(&v335, v134, v135);
        std::_Tree<std::_Tset_traits<std::wstring,WstringCaseInsensitiveCompare,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
          (char *)this + 768,
          v347,
          &v335);
        std::wstring::~wstring(&v335);
      }
      v62 = v271;
LABEL_320:
      v136 = DP_COM<CDeploymentFileRequest>::DP_COM<CDeploymentFileRequest>(v331, &v279);
      v137 = v274;
      v132 = CDeploymentDownloadRequest::AppendFileRequest(v274, v136);
      v21 = v132;
      if ( v132 < 0 )
      {
        v133 = 2415;
        goto LABEL_314;
      }
      v21 = 0;
      if ( v279 )
      {
        (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v279 + 16LL))(v279);
        v279 = 0;
      }
      DH_SSTRING::~DH_SSTRING((DH_SSTRING *)&lpFileName);
LABEL_397:
      v167 = v295;
      if ( v295 <= v276 )
        v167 = v276;
      v295 = v167;
      if ( v283 || a5 || *(_DWORD *)(v62 + 104) != 2 || v40 )
      {
        v181 = v285;
        v174 = v268;
        v175 = v271;
      }
      else
      {
        v368 = 0;
        v367 = 0;
        v168 = *((_DWORD *)this + 114);
        if ( (v168 == 4 || (v169 = 1, v168 == 22))
          && (v169 = 0, v170 = *((_QWORD *)v286 + 11), v171 = v170 + 168LL * *((unsigned int *)v286 + 24), v170 != v171) )
        {
          while ( (unsigned int)_o__wcsicmp(*(_QWORD *)(v62 + 56), *(_QWORD *)(v170 + 56)) )
          {
            v170 += 168;
            if ( v170 == v171 )
              goto LABEL_410;
          }
LABEL_412:
          v172 = a6;
        }
        else
        {
          if ( v169 )
            goto LABEL_412;
LABEL_410:
          v172 = 1;
          v173 = *((_QWORD *)this + 75);
          if ( v173 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v173,
              2,
              L"Skipping ICbsServicingProcessor->WritePackageFileList PackageFilePath: [%ws]; must be repair content",
              *(_QWORD *)(v62 + 56));
        }
        v174 = v268;
        v175 = v271;
        ExpressDownloadList = CDeploymentSession::GenerateExpressDownloadList(
                                this,
                                v271,
                                v268,
                                v301,
                                v172,
                                (wchar_t *)v369,
                                (__int64)v137,
                                (unsigned __int64 *)&v368,
                                (unsigned __int64 *)&v367,
                                (unsigned __int64 *)&v361,
                                (int *)&v360);
        v21 = ExpressDownloadList;
        if ( ExpressDownloadList < 0 )
        {
          v178 = 2546;
LABEL_415:
          v179 = (unsigned int)ExpressDownloadList;
          goto LABEL_416;
        }
        v180 = v277;
        if ( (_DWORD)v360 )
          v180 = 1;
        v277 = v180;
        v181 = v285;
        if ( v285 + v368 < v285 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v177);
        }
        else
        {
          v181 = v285 + v368;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v178 = 2552;
          goto LABEL_424;
        }
        if ( v288 + v367 < v288 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v182);
        }
        else
        {
          v288 += v367;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v178 = 2553;
          goto LABEL_424;
        }
        v21 = 0;
      }
      if ( v181 + v297 < v297 )
      {
        v21 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v57);
      }
      else
      {
        v297 += v181;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
      if ( v21 < 0 )
      {
        v178 = 2558;
        goto LABEL_424;
      }
      if ( v306 + v361 < v306 )
      {
        v21 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, 0);
      }
      else
      {
        v306 += v361;
        v21 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
      v183 = 0;
      if ( v21 < 0 )
      {
        v178 = 2559;
        goto LABEL_424;
      }
      if ( v181 )
      {
        if ( v174 )
        {
          if ( v290 + 1 < v290 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, 0);
          }
          else
          {
            ++v290;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          v183 = 0;
          if ( v21 < 0 )
          {
            v178 = 2565;
            goto LABEL_424;
          }
        }
        else
        {
          if ( v289 + 1 < v289 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, 0);
          }
          else
          {
            ++v289;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v178 = 2569;
            goto LABEL_424;
          }
          if ( v181 + v281 < v281 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v184);
          }
          else
          {
            v281 += v181;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v178 = 2571;
            goto LABEL_424;
          }
          if ( v305 + v288 < v305 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v185);
          }
          else
          {
            v305 += v288;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v178 = 2572;
            goto LABEL_424;
          }
          if ( v282 + v361 < v282 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v186);
          }
          else
          {
            v282 += v361;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          v183 = 0;
          if ( v21 < 0 )
          {
            v178 = 2573;
            goto LABEL_424;
          }
        }
      }
      v187 = *(_DWORD *)(v175 + 88);
      if ( v187 > 7 )
      {
        v197 = v187 - 13;
        if ( !v197 )
        {
          v209 = *((_QWORD *)&v314 + 1);
          v210 = *((_QWORD *)&v314 + 1) + v281;
          if ( *((_QWORD *)&v314 + 1) + v281 < *((_QWORD *)&v314 + 1) )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, 0);
            v210 = v209;
          }
          else
          {
            *((_QWORD *)&v314 + 1) += v281;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v178 = 2602;
            goto LABEL_424;
          }
          if ( v210 + v282 < v210 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v211);
          }
          else
          {
            *((_QWORD *)&v314 + 1) = v210 + v282;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v178 = 2603;
            goto LABEL_424;
          }
          HIDWORD(v316) = v174;
          goto LABEL_545;
        }
        v198 = v197 - 1;
        if ( !v198 )
        {
          v206 = v315;
          v207 = v315 + v281;
          if ( (unsigned __int64)v315 + v281 < (unsigned __int64)v315 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, 0);
            v207 = v206;
          }
          else
          {
            *(_QWORD *)&v315 = v315 + v281;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v178 = 2608;
            goto LABEL_424;
          }
          if ( v207 + v282 < v207 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v208);
          }
          else
          {
            *(_QWORD *)&v315 = v207 + v282;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v178 = 2609;
            goto LABEL_424;
          }
          LODWORD(v317) = v174;
          goto LABEL_545;
        }
        v199 = v198 - 1;
        if ( !v199 )
        {
          v203 = *((_QWORD *)&v315 + 1);
          v204 = *((_QWORD *)&v315 + 1) + v281;
          if ( *((_QWORD *)&v315 + 1) + v281 < *((_QWORD *)&v315 + 1) )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, 0);
            v204 = v203;
          }
          else
          {
            *((_QWORD *)&v315 + 1) += v281;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v178 = 2614;
            goto LABEL_424;
          }
          if ( v204 + v282 < v204 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v205);
          }
          else
          {
            *((_QWORD *)&v315 + 1) = v204 + v282;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 < 0 )
          {
            v178 = 2615;
            goto LABEL_424;
          }
          HIDWORD(v317) = v174;
          goto LABEL_545;
        }
        if ( v199 != 2 )
          goto LABEL_545;
LABEL_501:
        v200 = v314;
        v201 = v314 + v281;
        if ( (unsigned __int64)v314 + v281 < (unsigned __int64)v314 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, 0);
          v201 = v200;
        }
        else
        {
          *(_QWORD *)&v314 = v314 + v281;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v178 = 2589;
          goto LABEL_424;
        }
        if ( v201 + v282 < v201 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v202);
        }
        else
        {
          *(_QWORD *)&v314 = v201 + v282;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v178 = 2590;
          goto LABEL_424;
        }
        DWORD2(v316) = v174;
        goto LABEL_545;
      }
      if ( v187 == 7 )
        goto LABEL_475;
      v188 = v187 - 2;
      if ( !v188 || (v189 = v188 - 1) == 0 )
      {
        v193 = *((_QWORD *)&v313 + 1);
        v194 = *((_QWORD *)&v313 + 1) + v281;
        if ( *((_QWORD *)&v313 + 1) + v281 < *((_QWORD *)&v313 + 1) )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, 0);
          v194 = v193;
        }
        else
        {
          *((_QWORD *)&v313 + 1) += v281;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v178 = 2596;
          goto LABEL_424;
        }
        if ( v194 + v282 < v194 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v195);
        }
        else
        {
          *((_QWORD *)&v313 + 1) = v194 + v282;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v178 = 2597;
          goto LABEL_424;
        }
        DWORD1(v316) = v174;
        goto LABEL_545;
      }
      v190 = v189 - 1;
      if ( !v190 )
        goto LABEL_501;
      if ( (unsigned int)(v190 - 1) <= 1 )
      {
LABEL_475:
        v191 = v313;
        v192 = v313 + v281;
        if ( (unsigned __int64)v313 + v281 < (unsigned __int64)v313 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, 0);
          v192 = v191;
        }
        else
        {
          *(_QWORD *)&v313 = v313 + v281;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v178 = 2582;
          goto LABEL_424;
        }
        if ( v192 + v282 < v192 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v196);
        }
        else
        {
          *(_QWORD *)&v313 = v192 + v282;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 < 0 )
        {
          v178 = 2583;
          goto LABEL_424;
        }
        LODWORD(v316) = v174;
      }
LABEL_545:
      v212 = *(_DWORD *)(v175 + 104);
      v40 = 0;
      if ( !v212 )
      {
        if ( v299 + v287 < v299 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v183);
        }
        else
        {
          v299 += v287;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 >= 0 )
        {
          if ( v291 + 1 < v291 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v223);
          }
          else
          {
            ++v291;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 >= 0 )
            goto LABEL_109;
          v178 = 2624;
        }
        else
        {
          v178 = 2623;
        }
        goto LABEL_424;
      }
      v213 = v212 - 1;
      if ( !v213 )
        goto LABEL_550;
      v214 = v213 - 1;
      if ( !v214 )
      {
        v217 = v311;
        if ( v311 + v299 < v299 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v183);
        }
        else
        {
          v299 += v311;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 >= 0 )
        {
          v219 = v287;
          if ( v287 - v217 > v287 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v218);
          }
          else
          {
            v219 = v287 - v217;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 >= 0 )
          {
            if ( v219 + v308 < v308 )
            {
              v21 = -2147024362;
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v220);
            }
            else
            {
              v308 += v219;
              v21 = 0;
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
            if ( v21 >= 0 )
            {
              if ( v294 + 1 < v294 )
              {
                v21 = -2147024362;
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v221);
              }
              else
              {
                ++v294;
                v21 = 0;
              }
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
              if ( v21 >= 0 )
                goto LABEL_109;
              v178 = 2643;
            }
            else
            {
              v178 = 2642;
            }
          }
          else
          {
            v178 = 2640;
          }
        }
        else
        {
          v178 = 2639;
        }
        goto LABEL_424;
      }
      v215 = v214 - 2;
      if ( !v215 )
      {
        if ( v310 + v287 < v310 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v183);
        }
        else
        {
          v310 += v287;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 >= 0 )
        {
          if ( v292 + 1 < v292 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v216);
          }
          else
          {
            ++v292;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 >= 0 )
            goto LABEL_109;
          v178 = 2629;
        }
        else
        {
          v178 = 2628;
        }
        goto LABEL_424;
      }
      if ( v215 == 1 )
      {
LABEL_550:
        if ( v309 + v287 < v309 )
        {
          v21 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v183);
        }
        else
        {
          v309 += v287;
          v21 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
        if ( v21 >= 0 )
        {
          if ( v293 + 1 < v293 )
          {
            v21 = -2147024362;
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL, v222);
          }
          else
          {
            ++v293;
            v21 = 0;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v21);
          if ( v21 >= 0 )
            goto LABEL_109;
          v178 = 2635;
        }
        else
        {
          v178 = 2634;
        }
LABEL_424:
        v179 = (unsigned int)v21;
LABEL_416:
        CMoUpdateLogT<CEmptyType>::MoUpdateLogError(
          *((_QWORD *)this + 75),
          v179,
          L"CDeploymentSession::GenerateDownloadList",
          v178);
        goto LABEL_705;
      }
LABEL_109:
      v57 = v298;
LABEL_110:
      v56 = v271 + 168;
    }
    v62 = v271;
LABEL_117:
    *((_DWORD *)this + 71) = 1;
    v63 = 1;
    v21 = 0;
    goto LABEL_118;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xAFE,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v256);
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
