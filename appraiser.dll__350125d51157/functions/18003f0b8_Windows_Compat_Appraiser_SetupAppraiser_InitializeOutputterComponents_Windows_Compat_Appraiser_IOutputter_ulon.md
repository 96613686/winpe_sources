# Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents(Windows::Compat::Appraiser::IOutputter * * &,ulong &,Windows::Compat::Appraiser::RunOptions &,Windows::Compat::Appraiser::ValidOutputterComponents &,Windows::Compat::Appraiser::DataFile &)

- ea: `0x18003f0b8`
- end: `0x180041017`
- name: `?InitializeOutputterComponents@SetupAppraiser@Appraiser@Compat@Windows@@AEAAJAEAPEAPEAVIOutputter@234@AEAKAEAURunOptions@234@AEAUValidOutputterComponents@234@AEAVDataFile@234@@Z`
- size: `8031`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::SetupAppraiser *this, struct Windows::Compat::Appraiser::IOutputter ***, unsigned int *, struct Windows::Compat::Appraiser::RunOptions *, unsigned __int16 **, struct Windows::Compat::Appraiser::DataFile *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003b30c`

## callees

- `0x18000147c`
- `0x180008570`
- `0x1800085a0`
- `0x18000a5b8`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002a778`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180038f10`
- `0x18003b2a0`
- `0x18003f0b8`
- `0x180044bb4`
- `0x180044eb0`
- `0x180046c7c`
- `0x180082634`
- `0x180083094`
- `0x180096ef0`
- `0x1800dc444`
- `0x1800e2040`
- `0x1800e29a0`
- `0x1800e7fb8`
- `0x1800eee80`
- `0x1801ac054`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x180040055`
- `KERNEL32!GetSystemTime` at `0x180040223`
- `KERNEL32!GetSystemTime` at `0x1800409a8`
- `KERNEL32!GetSystemTime` at `0x180040d53`
- `KERNEL32!GetSystemTime` at `0x180040055`
- `KERNEL32!GetSystemTime` at `0x180040223`
- `KERNEL32!GetSystemTime` at `0x1800409a8`
- `KERNEL32!GetSystemTime` at `0x180040d53`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180040a52`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180040a52`
- `KERNEL32!GetProcessHeap` at `0x18003f12b`
- `KERNEL32!GetProcessHeap` at `0x18003f170`
- `KERNEL32!GetProcessHeap` at `0x18003f1ee`
- `KERNEL32!GetProcessHeap` at `0x18003f234`
- `KERNEL32!GetProcessHeap` at `0x18003f27a`
- `KERNEL32!GetProcessHeap` at `0x18003f569`
- `KERNEL32!GetProcessHeap` at `0x180040ed1`
- `KERNEL32!GetProcessHeap` at `0x18003f12b`
- `KERNEL32!GetProcessHeap` at `0x18003f170`
- `KERNEL32!GetProcessHeap` at `0x18003f1ee`
- `KERNEL32!GetProcessHeap` at `0x18003f234`
- `KERNEL32!GetProcessHeap` at `0x18003f27a`
- `KERNEL32!GetProcessHeap` at `0x18003f569`
- `KERNEL32!GetProcessHeap` at `0x180040ed1`
- `KERNEL32!HeapAlloc` at `0x18003f57a`
- `KERNEL32!HeapAlloc` at `0x18003f57a`
- `KERNEL32!HeapFree` at `0x180040edf`
- `KERNEL32!HeapFree` at `0x180040f2f`
- `KERNEL32!HeapFree` at `0x180040f62`
- `KERNEL32!HeapFree` at `0x180040f95`
- `KERNEL32!HeapFree` at `0x180040fc2`
- `KERNEL32!HeapFree` at `0x180040fec`
- `KERNEL32!HeapFree` at `0x180040edf`
- `KERNEL32!HeapFree` at `0x180040f2f`
- `KERNEL32!HeapFree` at `0x180040f62`
- `KERNEL32!HeapFree` at `0x180040f95`
- `KERNEL32!HeapFree` at `0x180040fc2`
- `KERNEL32!HeapFree` at `0x180040fec`

## string_xrefs

- `0x18003f4d3`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003f508`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18003f61a`: `Failed to copy path: [0x%x].`
- `0x18003f644`: `Failed to copy path: [0x%x].`
- `0x18003f2e1`: `%hs_APPRAISER_Migration.xml`
- `0x18003f2c1`: `%hs_APPRAISER_SetupOutput.xml`
- `0x18003f324`: `%hs_APPRAISER_UtcOutputVersioned.xml`
- `0x18003f301`: `%hs_APPRAISER_UtcOutput.xml`
- `0x18003f42a`: `%hs_APPRAISER_HumanReadable_Intermediate.xml`
- `0x18003f407`: `%hs_APPRAISER_HumanReadable.xml`
- `0x18003f46a`: `%hs_APPRAISER_SetupOutputDrv.xml`
- `0x18003f44a`: `%hs_APPRAISER_SetupOutputHw.xml`
- `0x18003f5d0`: `Error combining and printing: [0x%x].`
- `0x180040e9a`: `Error combining and printing: [0x%x].`
- `0x18003f4cc`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents`
- `0x18003f501`: `Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents`
- `0x18003fbcc`: `Error combining asset categories: [0x%x].`
- `0x18003fbf6`: `Error combining asset categories: [0x%x].`
- `0x180040b99`: `FT_ANY_CompatMarker_UexRatingRed`
- `0x18003f748`: `OutputFilePath`
- `0x180040e1d`: `Windows::Compat::Appraiser::SetupStatusOutputter::Initialize`
- `0x180040e24`: `onecore\base\appcompat\appraiser\outputters\setupstatus.cpp`
- `0x18003f76b`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x18003f7b4`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x18003f7e9`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x18003f848`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x18003f89a`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x18003f8ec`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x18003f93c`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x180040e60`: `onecore\base\appcompat\appraiser\outputters\setupxml.cpp`
- `0x18003f764`: `Windows::Compat::Appraiser::SetupXmlOutputter::Initialize`
- `0x18003f794`: `Windows::Compat::Appraiser::SetupXmlOutputter::Initialize`
- `0x18003f7d0`: `Windows::Compat::Appraiser::SetupXmlOutputter::Initialize`
- `0x18003f9b1`: `MT_HyperlinkTarget`
- `0x18003f7a4`: `Failed to copy file path: [0x%x].`
- `0x18003f7df`: `Failed to copy file path: [0x%x].`
- `0x18003f81a`: `Failed to copy file path: [0x%x].`
- `0x18003f83e`: `Failed to copy file path: [0x%x].`
- `0x18003f890`: `Failed to copy file path: [0x%x].`
- `0x18003f8e2`: `Failed to copy file path: [0x%x].`
- `0x18003f932`: `Failed to copy file path: [0x%x].`
- `0x18003f9c5`: `MT_HyperlinkText`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents(
        Windows::Compat::Appraiser::SetupAppraiser *this,
        struct Windows::Compat::Appraiser::IOutputter ***a2,
        unsigned int *a3,
        struct Windows::Compat::Appraiser::RunOptions *a4,
        unsigned __int16 **a5,
        struct Windows::Compat::Appraiser::DataFile *a6)
{
  unsigned __int16 *v9; // rax
  unsigned __int64 i; // rdx
  struct Windows::Compat::Appraiser::IOutputter **v11; // rax
  int appended; // edi
  const char *v13; // rbx
  char v14; // dl
  unsigned __int64 j; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v17; // rdx
  WCHAR *v18; // rcx
  HRESULT v19; // eax
  unsigned __int64 v20; // r9
  const unsigned __int16 *v21; // r8
  Windows::Compat::Appraiser::SetupAppraiser *v22; // rbx
  const unsigned __int16 *v23; // r8
  const unsigned __int16 *v24; // r8
  char v25; // dl
  int v26; // eax
  __int64 v27; // rdi
  __int64 v28; // rcx
  __int64 v29; // rcx
  struct Windows::Compat::Appraiser::IOutputter ***v30; // rdi
  __int64 v31; // rcx
  __int64 ListTableByName; // rax
  unsigned __int64 v33; // r9
  unsigned __int16 *v34; // rax
  char v35; // dl
  char v36; // cl
  char v37; // al
  int v38; // eax
  Windows::Compat::Appraiser::SetupAppraiser *v39; // rdi
  bool ShouldSendDiff; // cl
  int v41; // eax
  unsigned int v42; // ecx
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // r9d
  volatile signed __int64 *v50; // rcx
  void **v51; // rdx
  int v52; // edi
  int v53; // r8d
  int v54; // r9d
  int v55; // eax
  volatile signed __int64 *v56; // rcx
  void **v57; // rdx
  int v58; // r8d
  int v59; // r9d
  const unsigned __int16 *v60; // r8
  struct Windows::Compat::Appraiser::IOutputter *v61; // rdx
  const unsigned __int16 *v62; // r8
  const unsigned __int16 *v63; // r8
  Windows::Compat::Appraiser::SetupAppraiser *v64; // rdi
  const unsigned __int16 *v65; // r8
  const unsigned __int16 *v66; // r8
  const unsigned __int16 *v67; // r8
  Windows::Compat::Appraiser::SetupAppraiser *v68; // rdi
  const unsigned __int16 *v69; // r8
  const unsigned __int16 *v70; // r8
  int v71; // eax
  volatile signed __int64 *v72; // rcx
  void **v73; // rdx
  int v74; // ebx
  int v75; // r8d
  int v76; // r9d
  __int64 v77; // rbx
  int v78; // eax
  unsigned int v79; // ecx
  int v80; // eax
  int v81; // eax
  const char *v82; // rax
  int v83; // eax
  int v84; // edi
  volatile signed __int64 *v85; // rcx
  void **v86; // rdx
  int v87; // ebx
  int v88; // r8d
  int v89; // r9d
  unsigned __int64 k; // rbx
  void *v91; // r14
  HANDLE v92; // rax
  const char *dwFlags; // [rsp+20h] [rbp-110h]
  const char *dwFlagsa; // [rsp+20h] [rbp-110h]
  const char *dwFlagsb; // [rsp+20h] [rbp-110h]
  const char *v97; // [rsp+28h] [rbp-108h]
  char *v98; // [rsp+30h] [rbp-100h]
  char *v99; // [rsp+30h] [rbp-100h]
  char *v100; // [rsp+30h] [rbp-100h]
  char v101; // [rsp+B0h] [rbp-80h]
  char v102; // [rsp+B0h] [rbp-80h]
  unsigned __int16 *v104; // [rsp+C0h] [rbp-70h] BYREF
  unsigned __int16 *v105; // [rsp+C8h] [rbp-68h] BYREF
  struct Windows::Compat::Appraiser::IOutputter ***v106; // [rsp+D0h] [rbp-60h]
  __int64 v107; // [rsp+D8h] [rbp-58h]
  unsigned __int16 *v108; // [rsp+E0h] [rbp-50h] BYREF
  struct _SYSTEMTIME *v109; // [rsp+E8h] [rbp-48h] BYREF
  const char *v110; // [rsp+F0h] [rbp-40h] BYREF
  const char *v111; // [rsp+F8h] [rbp-38h] BYREF
  _QWORD v112[2]; // [rsp+100h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+110h] [rbp-20h] BYREF
  const unsigned __int16 *v114; // [rsp+120h] [rbp-10h] BYREF
  const unsigned __int16 *v115; // [rsp+128h] [rbp-8h] BYREF
  const unsigned __int16 *v116; // [rsp+130h] [rbp+0h] BYREF
  const unsigned __int16 *v117; // [rsp+138h] [rbp+8h] BYREF
  const unsigned __int16 *v118; // [rsp+140h] [rbp+10h] BYREF
  const unsigned __int16 *v119; // [rsp+148h] [rbp+18h] BYREF
  HANDLE v120[2]; // [rsp+150h] [rbp+20h] BYREF
  __int128 v121; // [rsp+160h] [rbp+30h]
  LPVOID v122[2]; // [rsp+170h] [rbp+40h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+180h] [rbp+50h] BYREF
  const unsigned __int16 *v124; // [rsp+188h] [rbp+58h] BYREF
  const unsigned __int16 *v125; // [rsp+190h] [rbp+60h] BYREF
  const unsigned __int16 *v126; // [rsp+198h] [rbp+68h] BYREF
  unsigned __int16 *v127; // [rsp+1A0h] [rbp+70h] BYREF
  int v128[2]; // [rsp+1A8h] [rbp+78h] BYREF
  int v129[2]; // [rsp+1B0h] [rbp+80h] BYREF
  __int64 v130; // [rsp+1B8h] [rbp+88h] BYREF
  HANDLE v131[2]; // [rsp+1C0h] [rbp+90h] BYREF
  __int128 v132; // [rsp+1D0h] [rbp+A0h]
  LPVOID v133[2]; // [rsp+1E0h] [rbp+B0h]
  HANDLE hHeap[2]; // [rsp+1F0h] [rbp+C0h] BYREF
  __int128 v135; // [rsp+200h] [rbp+D0h]
  LPVOID lpMem[2]; // [rsp+210h] [rbp+E0h]
  HANDLE v137[2]; // [rsp+220h] [rbp+F0h] BYREF
  __int128 v138; // [rsp+230h] [rbp+100h]
  LPVOID v139[2]; // [rsp+240h] [rbp+110h]
  HANDLE v140[2]; // [rsp+250h] [rbp+120h] BYREF
  __int128 v141; // [rsp+260h] [rbp+130h]
  LPVOID v142[2]; // [rsp+270h] [rbp+140h]
  _QWORD v143[2]; // [rsp+280h] [rbp+150h] BYREF
  struct _SYSTEMTIME v144; // [rsp+290h] [rbp+160h] BYREF
  struct _SYSTEMTIME v145; // [rsp+2A0h] [rbp+170h] BYREF
  _BYTE v146[144]; // [rsp+2B0h] [rbp+180h] BYREF
  unsigned __int16 **v147; // [rsp+340h] [rbp+210h] BYREF
  unsigned __int16 *v148; // [rsp+348h] [rbp+218h]
  unsigned __int16 *v149[40]; // [rsp+350h] [rbp+220h]
  char v150[144]; // [rsp+490h] [rbp+360h] BYREF
  WCHAR pszPathOut[264]; // [rsp+520h] [rbp+3F0h] BYREF

  v143[1] = -2;
  v106 = a2;
  v107 = (__int64)a6;
  *(_OWORD *)v140 = 0;
  v141 = 0;
  *(_OWORD *)v142 = 0;
  v140[0] = GetProcessHeap();
  v142[0] = (LPVOID)16;
  v141 = 0;
  v142[1] = 0;
  v140[1] = (HANDLE)8;
  *(_OWORD *)v120 = 0;
  v121 = 0;
  *(_OWORD *)v122 = 0;
  v120[0] = GetProcessHeap();
  v122[0] = (LPVOID)16;
  v121 = 0;
  v122[1] = 0;
  v120[1] = (HANDLE)8;
  v127 = 0;
  v126 = 0;
  *(_QWORD *)v128 = 0;
  *(_QWORD *)v129 = 0;
  v114 = 0;
  v117 = 0;
  v115 = 0;
  v118 = 0;
  v119 = 0;
  v116 = 0;
  v130 = 0;
  v143[0] = 0;
  v124 = 0;
  v125 = 0;
  SystemTimeAsFileTime = 0;
  *(_QWORD *)&SystemTime.wYear = 0;
  *(_OWORD *)v137 = 0;
  v138 = 0;
  *(_OWORD *)v139 = 0;
  v137[0] = GetProcessHeap();
  v139[0] = (LPVOID)16;
  v138 = 0;
  v139[1] = 0;
  v137[1] = (HANDLE)8;
  *(_OWORD *)v131 = 0;
  v132 = 0;
  *(_OWORD *)v133 = 0;
  v131[0] = GetProcessHeap();
  v133[0] = (LPVOID)16;
  v132 = 0;
  v133[1] = 0;
  v131[1] = (HANDLE)8;
  *(_OWORD *)hHeap = 0;
  v135 = 0;
  *(_OWORD *)lpMem = 0;
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v135 = 0;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)8;
  v9 = (unsigned __int16 *)*((_QWORD *)a4 + 6);
  v147 = &v127;
  v148 = v9;
  v149[0] = L"%hs_APPRAISER_SetupOutput.xml";
  v149[1] = (unsigned __int16 *)&v126;
  v149[2] = v9;
  v149[3] = L"%hs_APPRAISER_Migration.xml";
  v149[4] = (unsigned __int16 *)v128;
  v149[5] = v9;
  v149[6] = L"%hs_APPRAISER_UtcOutput.xml";
  v149[7] = (unsigned __int16 *)v129;
  v149[8] = v9;
  v149[9] = L"%hs_APPRAISER_UtcOutputVersioned.xml";
  v149[10] = (unsigned __int16 *)&v114;
  v149[11] = v9;
  v149[12] = L"%hs_APPRAISER_EverythingAppInteresting.bin";
  v149[13] = (unsigned __int16 *)&v117;
  v149[14] = v9;
  v149[15] = L"%hs_APPRAISER_EverythingAppUninteresting.bin";
  v149[16] = (unsigned __int16 *)&v115;
  v149[17] = v9;
  v149[18] = L"%hs_APPRAISER_EverythingDevInteresting.bin";
  v149[19] = (unsigned __int16 *)&v118;
  v149[20] = v9;
  v149[21] = L"%hs_APPRAISER_EverythingDevUninteresting.bin";
  v149[22] = (unsigned __int16 *)&v119;
  v149[23] = v9;
  v149[24] = L"%hs_APPRAISER_EverythingSys.bin";
  v149[25] = (unsigned __int16 *)&v116;
  v149[26] = v9;
  v149[27] = L"%hs_APPRAISER_EverythingGated.bin";
  v149[28] = (unsigned __int16 *)&v130;
  v149[29] = v9;
  v149[30] = L"%hs_APPRAISER_HumanReadable.xml";
  v149[31] = (unsigned __int16 *)v143;
  v149[32] = v9;
  v149[33] = L"%hs_APPRAISER_HumanReadable_Intermediate.xml";
  v149[34] = (unsigned __int16 *)&v124;
  v149[35] = v9;
  v149[36] = L"%hs_APPRAISER_SetupOutputHw.xml";
  v149[37] = (unsigned __int16 *)&v125;
  v149[38] = v9;
  v149[39] = L"%hs_APPRAISER_SetupOutputDrv.xml";
  for ( i = 0; i < 0xE; ++i )
    *(&v147)[3 * i] = 0;
  v11 = (struct Windows::Compat::Appraiser::IOutputter **)operator new[](
                                                            0xA8u,
                                                            (const struct std::nothrow_t *)&std::nothrow);
  *a2 = v11;
  if ( !v11 )
  {
LABEL_294:
    appended = -2147024882;
    goto LABEL_295;
  }
  appended = RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(v140);
  v13 = "Failed to initialize RtlArray: [0x%x].";
  if ( appended < 0 )
  {
    v14 = 116;
LABEL_6:
    LODWORD(v98) = appended;
    LODWORD(v97) = (_DWORD)v13;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xC74u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
      "Failed to initialize RtlArray: [0x%x].",
      appended);
  appended = RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(v120);
  if ( appended < 0 )
  {
    v14 = 117;
    goto LABEL_6;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xC75u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
      "Failed to initialize RtlArray: [0x%x].",
      appended);
  for ( j = 0; j < 0xE; ++j )
  {
    ProcessHeap = GetProcessHeap();
    *(&v147)[3 * j] = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
    v18 = *(&v147)[3 * j];
    if ( !v18 )
      goto LABEL_294;
    appended = Windows::Compat::Appraiser::SetupAppraiser::CombinePathAndAppendRunId(
                 v18,
                 v17,
                 v149[3 * j - 1],
                 v149[3 * j]);
    if ( appended < 0 )
    {
      LODWORD(v98) = appended;
      v97 = "Error combining and printing: [0x%x].";
      v14 = 0x80;
      goto LABEL_7;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xC80u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
        "Error combining and printing: [0x%x].",
        appended);
  }
  v19 = PathCchCombineEx(pszPathOut, 0x104u, *((PCWSTR *)a4 + 6), L"img", (ULONG)dwFlags);
  appended = v19;
  if ( v19 < 0 )
  {
    LODWORD(v98) = v19;
    v97 = "Failed to copy path: [0x%x].";
    v14 = -121;
    goto LABEL_7;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xC87u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
      "Failed to copy path: [0x%x].",
      v19);
  if ( !*((_BYTE *)a4 + 4) )
  {
    if ( *(_BYTE *)a4 )
    {
      v21 = v124;
      if ( !v124 || !*v124 )
        v21 = L"_NONE_";
      v22 = this;
      RtlStringArray::Set((Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 320), 0xDu, v21, v20);
    }
    else
    {
      v22 = this;
    }
    if ( *((_BYTE *)a4 + 2) )
    {
      v23 = v125;
      if ( !v125 || !*v125 )
        v23 = L"_NONE_";
      RtlStringArray::Set((Windows::Compat::Appraiser::SetupAppraiser *)((char *)v22 + 320), 0xCu, v23, v20);
    }
  }
  if ( *((_BYTE *)a4 + 1) )
  {
    v24 = v126;
    if ( !v126 || !*v126 )
      v24 = L"_NONE_";
    RtlStringArray::Set((Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 320), 8u, v24, v20);
  }
  v104 = (unsigned __int16 *)Windows::Compat::Appraiser::PersistedData::Get((char *)this + 152, 12);
  v108 = (unsigned __int16 *)Windows::Compat::Appraiser::PersistedData::Get((char *)this + 152, 13);
  v105 = (unsigned __int16 *)Windows::Compat::Appraiser::PersistedData::Get((char *)this + 152, 8);
  if ( !v127 )
  {
    appended = -2147024809;
    LODWORD(dwFlags) = -2147024809;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      104,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::Initialize",
      dwFlags,
      (int)"Required parameter [%s] missing: [0x%x].",
      "OutputFilePath",
      -2147024809);
    goto LABEL_292;
  }
  appended = Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc(a5 + 12, v127);
  if ( appended < 0 )
  {
    v25 = 108;
    goto LABEL_45;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x6Cu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::Initialize",
      "Failed to copy file path: [0x%x].",
      appended);
  if ( !v105 )
  {
LABEL_54:
    if ( v108 )
    {
      appended = Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc(a5 + 14, v108);
      if ( appended < 0 )
      {
        v25 = 119;
LABEL_45:
        LODWORD(v98) = appended;
        goto LABEL_46;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x77u,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::Initialize",
          "Failed to copy file path: [0x%x].",
          appended);
    }
    if ( v104 )
    {
      appended = Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc(a5 + 15, v104);
      if ( appended < 0 )
      {
        v25 = 125;
        goto LABEL_45;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x7Du,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::Initialize",
          "Failed to copy file path: [0x%x].",
          appended);
    }
    appended = Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc(a5 + 16, pszPathOut);
    if ( appended < 0 )
    {
      v25 = -127;
      goto LABEL_45;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x81u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::Initialize",
        "Failed to copy file path: [0x%x].",
        appended);
    a5[17] = (unsigned __int16 *)this;
    a5[22] = (unsigned __int16 *)Windows::Compat::Appraiser::SetupAppraiser::SetCurrentXmlText;
    a5[23] = (unsigned __int16 *)Windows::Compat::Appraiser::SetupAppraiser::AddUninstallInfo;
    v27 = v107;
    a5[18] = (unsigned __int16 *)Windows::Compat::Appraiser::DataFile::FindListTableByName(
                                   v107 + 144,
                                   L"FT_ALL_ShowGatedUnknownDefault");
    a5[19] = (unsigned __int16 *)Windows::Compat::Appraiser::DataFile::FindListTableByName(
                                   v28,
                                   L"FT_ANY_ShowGatedBlockDefault");
    a5[20] = (unsigned __int16 *)Windows::Compat::Appraiser::DataFile::FindListTableByName(
                                   v27 + 432,
                                   L"MT_HyperlinkTarget");
    a5[21] = (unsigned __int16 *)Windows::Compat::Appraiser::DataFile::FindListTableByName(v29, L"MT_HyperlinkText");
    if ( !a5[18] || !a5[19] )
    {
      appended = -2147024883;
      LODWORD(dwFlags) = -2147024883;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        143,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::Initialize",
        dwFlags,
        (int)"Missing required filter tables.",
        v98);
      goto LABEL_292;
    }
    v13 = "Failed to initialize: [0x%x].";
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xCA7u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
        "Failed to initialize: [0x%x].",
        0);
    (*v106)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 10);
    appended = Windows::Compat::Appraiser::IconOutputter::Initialize(
                 (Windows::Compat::Appraiser::IconOutputter *)(a5 + 24),
                 pszPathOut,
                 *(struct Windows::Compat::Appraiser::Table **)(v27 + 568));
    if ( appended < 0 )
    {
      v14 = -81;
      goto LABEL_6;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xCAFu,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
        "Failed to initialize: [0x%x].",
        appended);
    v30 = v106;
    (*v106)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 24);
    a5[98] = (unsigned __int16 *)Windows::Compat::Appraiser::SetupAppraiser::SetCurrentScanStatus;
    a5[95] = (unsigned __int16 *)this;
    a5[96] = (unsigned __int16 *)Windows::Compat::Appraiser::DataFile::FindListTableByName(
                                   v107 + 144,
                                   L"FT_ALL_ShowGatedUnknownDefault");
    ListTableByName = Windows::Compat::Appraiser::DataFile::FindListTableByName(v31, L"FT_ANY_ShowGatedBlockDefault");
    a5[97] = (unsigned __int16 *)ListTableByName;
    if ( !a5[96] || !ListTableByName )
    {
      appended = -2147024883;
      LODWORD(dwFlags) = -2147024883;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        69,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupstatus.cpp",
        "Windows::Compat::Appraiser::SetupStatusOutputter::Initialize",
        dwFlags,
        (int)"Missing required filter tables.",
        v98);
      v14 = -73;
      goto LABEL_6;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xCB7u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
        "Failed to initialize: [0x%x].",
        0);
    (*v30)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 93);
    if ( !*((_BYTE *)a4 + 5) )
    {
LABEL_160:
      if ( *((_BYTE *)a4 + 1) )
      {
        (*v30)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 2);
        if ( *((_BYTE *)a4 + 1) )
        {
          a5[498] = (unsigned __int16 *)*((_QWORD *)a4 + 12);
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xD2Du,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
              "Error initializing mig shim outputter: [0x%x].",
              0);
          (*v30)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 496);
          if ( *((_BYTE *)a4 + 1) )
            (*v30)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)a5;
        }
      }
      if ( *((_BYTE *)a4 + 2) )
        (*v30)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 4);
      if ( *((_BYTE *)a4 + 1) && !*((_BYTE *)a4 + 4) )
        (*v30)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 6);
      if ( *((_BYTE *)a4 + 3) )
      {
        if ( *((_BYTE *)a4 + 4) )
          goto LABEL_247;
        if ( *((_BYTE *)a4 + 5) )
        {
          v60 = v116;
          if ( !v116 || !*v116 )
            v60 = L"_NONE_";
          RtlStringArray::Set((Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 320), 3u, v60, v33);
        }
        LOBYTE(dwFlags) = 1;
        appended = Windows::Compat::Appraiser::BinaryEverything::Initialize(
                     a5 + 475,
                     v116,
                     *(_QWORD *)(v107 + 512),
                     0,
                     (_DWORD)dwFlags,
                     0);
        if ( appended < 0 )
        {
          v14 = 94;
          goto LABEL_6;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xD5Eu,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
            "Failed to initialize: [0x%x].",
            appended);
        v61 = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 475);
        goto LABEL_246;
      }
      if ( *((_BYTE *)a4 + 1) )
      {
        if ( !*((_BYTE *)a4 + 4) )
        {
          if ( *((_BYTE *)a4 + 5) )
          {
            v62 = v117;
            if ( !v117 || !*v117 )
              v62 = L"_NONE_";
            RtlStringArray::Set((Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 320), 0, v62, v33);
          }
          LOBYTE(dwFlags) = 1;
          appended = Windows::Compat::Appraiser::BinaryEverything::Initialize(
                       a5 + 451,
                       v117,
                       *(_QWORD *)(v107 + 544),
                       0,
                       (_DWORD)dwFlags,
                       0);
          if ( appended < 0 )
          {
            v14 = 109;
            goto LABEL_6;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xD6Du,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
              "Failed to initialize: [0x%x].",
              appended);
          (*v106)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 451);
        }
        if ( *((_BYTE *)a4 + 5) )
        {
          v63 = v114;
          if ( !v114 || !*v114 )
            v63 = L"_NONE_";
          v64 = this;
          RtlStringArray::Set((Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 320), 4u, v63, v33);
        }
        else
        {
          v64 = this;
        }
        v65 = v114;
        if ( !v114 || !*v114 )
          v65 = L"_NONE_";
        RtlStringArray::Set((Windows::Compat::Appraiser::SetupAppraiser *)((char *)v64 + 320), 5u, v65, v33);
        LOBYTE(dwFlags) = 1;
        appended = Windows::Compat::Appraiser::BinaryEverything::Initialize(
                     a5 + 443,
                     v114,
                     *(_QWORD *)(v107 + 536),
                     0,
                     (_DWORD)dwFlags,
                     0);
        if ( appended < 0 )
        {
          v14 = 127;
          goto LABEL_6;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xD7Fu,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
            "Failed to initialize: [0x%x].",
            appended);
        v30 = v106;
        (*v106)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 443);
      }
      if ( !*((_BYTE *)a4 + 2) )
      {
LABEL_234:
        if ( !*(_BYTE *)a4 || *((_BYTE *)a4 + 4) )
        {
LABEL_247:
          v71 = Windows::Compat::Appraiser::OutputEverything::Initialize(a5 + 491, v130, 0, 15);
          LODWORD(v105) = v71;
          if ( v71 >= 0 )
          {
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0xDADu,
                "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
                "Failed to initialize: [0x%x].",
                v71);
            (*v30)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 491);
          }
          else
          {
            LODWORD(v98) = v71;
            LODWORD(dwFlags) = v71;
            Windows::Compat::Appraiser::WriteLog(
              (Windows::Compat::Appraiser *)1,
              173,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
              dwFlags,
              (int)"Failed to initialize: [0x%x].",
              v98);
            TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v146);
            v72 = (volatile signed __int64 *)v146;
            if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
              v72 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
            TraceLoggingCorrelationVector::ToStringImpl(
              (TraceLoggingCorrelationVector *)v72,
              _InterlockedExchangeAdd64(v72 + 17, 0),
              v150);
            if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
              UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v73);
            v74 = qword_1802C9628;
            if ( *(_DWORD *)qword_1802C9628 > 5u
              && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
              && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
            {
              *(_QWORD *)&SystemTime.wYear = v150;
              v112[0] = "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents";
              v111 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
              LODWORD(v108) = 3501;
              v110 = (const char *)&szValueBuf;
              v144 = 0;
              GetSystemTime(&v144);
              v145 = v144;
              v109 = &v145;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v74,
                (unsigned int)byte_18029DE49,
                v75,
                v76,
                (__int64)&v109,
                (__int64)&v110,
                (__int64)&v108,
                (__int64)&v111,
                (__int64)v112,
                (__int64)&v105,
                (__int64)&SystemTime);
            }
          }
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          v77 = (__int64)SystemTimeAsFileTime;
          if ( *((_BYTE *)a4 + 3) )
          {
            *(_QWORD *)&SystemTime.wYear = L"LT_GatedSetupScanRequestedIndicators";
            v80 = RtlArray<JsonValue *>::Append(v131, &SystemTime);
            appended = v80;
            if ( v80 < 0 )
            {
              LODWORD(v98) = v80;
              v97 = "RtlArray Append failed: [0x%x].";
              v14 = -68;
              goto LABEL_7;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
              goto LABEL_271;
            v79 = 3516;
          }
          else
          {
            if ( !*(_BYTE *)a4 && !*((_BYTE *)a4 + 2) )
            {
LABEL_289:
              appended = 0;
              goto LABEL_295;
            }
            *(_QWORD *)&SystemTime.wYear = L"LT_RequestUpgExIndicators";
            v78 = RtlArray<JsonValue *>::Append(v131, &SystemTime);
            appended = v78;
            if ( v78 < 0 )
            {
              LODWORD(v98) = v78;
              v97 = "RtlArray Append failed: [0x%x].";
              v14 = -64;
              goto LABEL_7;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
            {
LABEL_271:
              *(_QWORD *)&SystemTime.wYear = L"LT_GatedSetupScanRequestedMarkers";
              v81 = RtlArray<JsonValue *>::Append(v131, &SystemTime);
              appended = v81;
              if ( v81 < 0 )
              {
                LODWORD(v98) = v81;
                v97 = "RtlArray Append failed: [0x%x].";
                v14 = -61;
                goto LABEL_7;
              }
              if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                  0xDC3u,
                  "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                  "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
                  "RtlArray Append failed: [0x%x].",
                  v81);
              v82 = 0;
              if ( !*((_BYTE *)a4 + 3) )
                v82 = L"FT_ANY_CompatMarker_UexRatingRed";
              v83 = Windows::Compat::Appraiser::RegistryMarkerOutputter::Initialize(
                      (Windows::Compat::Appraiser::RegistryMarkerOutputter *)(a5 + 499),
                      -1,
                      0,
                      0,
                      -1,
                      0,
                      1,
                      0,
                      (__int64)v137,
                      (__int64)hHeap,
                      (__int64)v131,
                      v77,
                      *((_BYTE *)a4 + 4) == 0,
                      *((_QWORD *)a4 + 4),
                      (__int64)L"Setup",
                      v107,
                      (int)L"LT_IndicatorsToIgnoreForUTC",
                      (__int64)v82,
                      1);
              v84 = v83;
              if ( v83 >= 0 )
              {
                if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                  Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                    0xDDAu,
                    "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                    "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
                    "Failed to initialize: [0x%x].",
                    v83);
                (*v106)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 499);
              }
              else
              {
                LODWORD(v100) = v83;
                LODWORD(dwFlagsb) = v83;
                Windows::Compat::Appraiser::WriteLog(
                  (Windows::Compat::Appraiser *)1,
                  218,
                  (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
                  "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
                  dwFlagsb,
                  (int)"Failed to initialize: [0x%x].",
                  v100);
                TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v146);
                v85 = (volatile signed __int64 *)v146;
                if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
                  v85 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
                TraceLoggingCorrelationVector::ToStringImpl(
                  (TraceLoggingCorrelationVector *)v85,
                  _InterlockedExchangeAdd64(v85 + 17, 0),
                  v150);
                if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
                  UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v86);
                v87 = qword_1802C9628;
                if ( *(_DWORD *)qword_1802C9628 > 5u
                  && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
                  && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
                {
                  *(_QWORD *)&SystemTime.wYear = v150;
                  LODWORD(v105) = v84;
                  v112[0] = "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents";
                  v111 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
                  LODWORD(v108) = 3546;
                  v110 = (const char *)&szValueBuf;
                  v144 = 0;
                  GetSystemTime(&v144);
                  v145 = v144;
                  v109 = &v145;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                    v87,
                    (unsigned int)&byte_18029DD97,
                    v88,
                    v89,
                    (__int64)&v109,
                    (__int64)&v110,
                    (__int64)&v108,
                    (__int64)&v111,
                    (__int64)v112,
                    (__int64)&v105,
                    (__int64)&SystemTime);
                }
              }
              goto LABEL_289;
            }
            v79 = 3520;
          }
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            v79,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
            "RtlArray Append failed: [0x%x].",
            appended);
          goto LABEL_271;
        }
        if ( *((_BYTE *)a4 + 5) )
        {
          v70 = v119;
          if ( !v119 || !*v119 )
            v70 = L"_NONE_";
          RtlStringArray::Set((Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 320), 2u, v70, v33);
        }
        LOBYTE(dwFlags) = 1;
        appended = Windows::Compat::Appraiser::BinaryEverything::Initialize(
                     a5 + 483,
                     v119,
                     *(_QWORD *)(v107 + 520),
                     0,
                     (_DWORD)dwFlags,
                     0);
        if ( appended < 0 )
        {
          v14 = -89;
          goto LABEL_6;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xDA7u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
            "Failed to initialize: [0x%x].",
            appended);
        v61 = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 483);
LABEL_246:
        v30 = v106;
        (*v106)[(*a3)++] = v61;
        goto LABEL_247;
      }
      if ( !*((_BYTE *)a4 + 4) )
      {
        if ( !*((_BYTE *)a4 + 5) )
          goto LABEL_225;
        v66 = v118;
        if ( !v118 || !*v118 )
          v66 = L"_NONE_";
        RtlStringArray::Set((Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 320), 1u, v66, v33);
        LOBYTE(dwFlags) = 1;
        appended = Windows::Compat::Appraiser::BinaryEverything::Initialize(
                     a5 + 467,
                     v118,
                     *(_QWORD *)(v107 + 560),
                     0,
                     (_DWORD)dwFlags,
                     0);
        if ( appended < 0 )
        {
          v14 = -118;
          goto LABEL_6;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xD8Au,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
            "Failed to initialize: [0x%x].",
            appended);
        (*v106)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 467);
      }
      if ( *((_BYTE *)a4 + 5) )
      {
        v67 = v115;
        if ( !v115 || !*v115 )
          v67 = L"_NONE_";
        v68 = this;
        RtlStringArray::Set((Windows::Compat::Appraiser::SetupAppraiser *)((char *)this + 320), 6u, v67, v33);
        goto LABEL_226;
      }
LABEL_225:
      v68 = this;
LABEL_226:
      v69 = v115;
      if ( !v115 || !*v115 )
        v69 = L"_NONE_";
      RtlStringArray::Set((Windows::Compat::Appraiser::SetupAppraiser *)((char *)v68 + 320), 7u, v69, v33);
      LOBYTE(dwFlags) = 1;
      appended = Windows::Compat::Appraiser::BinaryEverything::Initialize(
                   a5 + 459,
                   v115,
                   *(_QWORD *)(v107 + 552),
                   0,
                   (_DWORD)dwFlags,
                   0);
      if ( appended < 0 )
      {
        v14 = -100;
        goto LABEL_6;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xD9Cu,
          "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
          "Failed to initialize: [0x%x].",
          appended);
      v30 = v106;
      (*v106)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 459);
      goto LABEL_234;
    }
    v34 = (unsigned __int16 *)((char *)a4 + 3);
    v35 = *(_BYTE *)a4 || *(_BYTE *)v34;
    if ( *((_BYTE *)a4 + 2)
      || (v34 = (unsigned __int16 *)((char *)a4 + 3), v105 = (unsigned __int16 *)((char *)a4 + 3), *((_BYTE *)a4 + 3)) )
    {
      v36 = 1;
      v105 = v34;
    }
    else
    {
      v36 = 0;
    }
    v37 = *((_BYTE *)a4 + 1) || *(_BYTE *)v34;
    v38 = Windows::Compat::Appraiser::Utilities::AssetCategoriesToArray(
            (unsigned int)v140,
            *(_QWORD *)(v107 + 488),
            *(_QWORD *)(v107 + 496),
            *(_QWORD *)(v107 + 504),
            v37,
            v36,
            v35);
    appended = v38;
    if ( v38 < 0 )
    {
      LODWORD(v98) = v38;
      v97 = "Error combining asset categories: [0x%x].";
      v14 = -57;
      goto LABEL_7;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xCC7u,
        "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
        "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
        "Error combining asset categories: [0x%x].",
        v38);
    v39 = this;
    ShouldSendDiff = Windows::Compat::Appraiser::SetupAppraiser::ShouldSendDiff(this, a4);
    v101 = ShouldSendDiff;
    if ( !ShouldSendDiff )
    {
LABEL_134:
      v102 = !ShouldSendDiff;
      LOBYTE(v33) = 1;
      v48 = Windows::Compat::Appraiser::TelemetryOutputter::Initialize(
              (int)a5 + 792,
              (int)v140,
              v128[0],
              v33,
              v107,
              !ShouldSendDiff,
              1,
              (wchar_t *)L"ALL",
              0,
              (__int64)L"FT_ANY_IncludeInTelemetry",
              (__int64)v120,
              0);
      LODWORD(v108) = v48;
      if ( v48 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xD05u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
            "Failed to initialize: [0x%x].",
            v48);
        v30 = v106;
        (*v106)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 99);
      }
      else
      {
        LODWORD(v99) = v48;
        LODWORD(dwFlagsa) = v48;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          5,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
          dwFlagsa,
          (int)"Failed to initialize: [0x%x].",
          v99);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v146);
        v50 = (volatile signed __int64 *)v146;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v50 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v50,
          _InterlockedExchangeAdd64(v50 + 17, 0),
          v150);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v51);
        v52 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v104 = (unsigned __int16 *)v150;
          v109 = (struct _SYSTEMTIME *)"Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents";
          v110 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
          LODWORD(v105) = 3333;
          v111 = (const char *)&szValueBuf;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v144 = SystemTime;
          v112[0] = &v144;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v52,
            (unsigned int)&byte_18029DF0F,
            v53,
            v54,
            (__int64)v112,
            (__int64)&v111,
            (__int64)&v105,
            (__int64)&v110,
            (__int64)&v109,
            (__int64)&v108,
            (__int64)&v104);
        }
        v30 = v106;
      }
      LOBYTE(v49) = 1;
      v55 = Windows::Compat::Appraiser::TelemetryOutputter::Initialize(
              (int)a5 + 2168,
              (int)v140,
              v129[0],
              v49,
              v107,
              v102,
              1,
              *((wchar_t **)a4 + 4),
              (__int64)L"Setup",
              (__int64)L"FT_ANY_IncludeInTelemetry",
              (__int64)v120,
              0);
      LODWORD(v105) = v55;
      if ( v55 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xD15u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
            "Failed to initialize: [0x%x].",
            v55);
        (*v30)[(*a3)++] = (struct Windows::Compat::Appraiser::IOutputter *)(a5 + 271);
      }
      else
      {
        LODWORD(v98) = v55;
        LODWORD(dwFlags) = v55;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          21,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
          "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
          dwFlags,
          (int)"Failed to initialize: [0x%x].",
          v98);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v146);
        v56 = (volatile signed __int64 *)v146;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v56 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v56,
          _InterlockedExchangeAdd64(v56 + 17, 0),
          v150);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v57);
        *(_QWORD *)&SystemTime.wYear = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v112[0] = v150;
          v111 = "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents";
          v110 = "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp";
          LODWORD(v108) = 3349;
          v109 = (struct _SYSTEMTIME *)&szValueBuf;
          v144 = 0;
          GetSystemTime(&v144);
          v145 = v144;
          v104 = (unsigned __int16 *)&v145;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            *(_DWORD *)&SystemTime.wYear,
            (unsigned int)&dword_18029DEAC,
            v58,
            v59,
            (__int64)&v104,
            (__int64)&v109,
            (__int64)&v108,
            (__int64)&v110,
            (__int64)&v111,
            (__int64)&v105,
            (__int64)v112);
        }
      }
      goto LABEL_160;
    }
    if ( *(_BYTE *)v105 )
    {
      v104 = (unsigned __int16 *)Windows::Compat::Appraiser::PersistedData::Get((char *)this + 152, 3);
      v41 = RtlArray<JsonValue *>::Append(v120, &v104);
      appended = v41;
      if ( v41 < 0 )
      {
        LODWORD(v98) = v41;
        v97 = "RtlArray Append failed: [0x%x].";
        v14 = -47;
        goto LABEL_7;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
        goto LABEL_132;
      v42 = 3281;
    }
    else
    {
      if ( *((_BYTE *)a4 + 1) )
      {
        if ( !*((_BYTE *)a4 + 4) )
        {
          v104 = (unsigned __int16 *)Windows::Compat::Appraiser::PersistedData::Get((char *)this + 152, 0);
          v43 = RtlArray<JsonValue *>::Append(v120, &v104);
          appended = v43;
          if ( v43 < 0 )
          {
            LODWORD(v98) = v43;
            v97 = "RtlArray Append failed: [0x%x].";
            v14 = -37;
            goto LABEL_7;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xCDBu,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
              "RtlArray Append failed: [0x%x].",
              v43);
          v39 = this;
        }
        v104 = (unsigned __int16 *)Windows::Compat::Appraiser::PersistedData::Get((char *)v39 + 152, 4);
        v44 = RtlArray<JsonValue *>::Append(v120, &v104);
        appended = v44;
        if ( v44 < 0 )
        {
          LODWORD(v98) = v44;
          v97 = "RtlArray Append failed: [0x%x].";
          v14 = -32;
          goto LABEL_7;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xCE0u,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
            "RtlArray Append failed: [0x%x].",
            v44);
        v39 = this;
      }
      if ( *((_BYTE *)a4 + 2) )
      {
        if ( !*((_BYTE *)a4 + 4) )
        {
          v104 = (unsigned __int16 *)Windows::Compat::Appraiser::PersistedData::Get((char *)v39 + 152, 1);
          v45 = RtlArray<JsonValue *>::Append(v120, &v104);
          appended = v45;
          if ( v45 < 0 )
          {
            LODWORD(v98) = v45;
            v97 = "RtlArray Append failed: [0x%x].";
            v14 = -23;
            goto LABEL_7;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xCE9u,
              "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
              "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
              "RtlArray Append failed: [0x%x].",
              v45);
        }
        v104 = (unsigned __int16 *)Windows::Compat::Appraiser::PersistedData::Get((char *)this + 152, 6);
        v46 = RtlArray<JsonValue *>::Append(v120, &v104);
        appended = v46;
        if ( v46 < 0 )
        {
          LODWORD(v98) = v46;
          v97 = "RtlArray Append failed: [0x%x].";
          v14 = -18;
          goto LABEL_7;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xCEEu,
            "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
            "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
            "RtlArray Append failed: [0x%x].",
            v46);
      }
      if ( *((_BYTE *)a4 + 4) || !*(_BYTE *)a4 )
        goto LABEL_132;
      v104 = (unsigned __int16 *)Windows::Compat::Appraiser::PersistedData::Get((char *)this + 152, 2);
      v47 = RtlArray<JsonValue *>::Append(v120, &v104);
      appended = v47;
      if ( v47 < 0 )
      {
        LODWORD(v98) = v47;
        v97 = "RtlArray Append failed: [0x%x].";
        v14 = -11;
        goto LABEL_7;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
        goto LABEL_132;
      v42 = 3317;
    }
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      v42,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
      "RtlArray Append failed: [0x%x].",
      appended);
LABEL_132:
    if ( !(_QWORD)v121 )
    {
      v30 = v106;
      goto LABEL_160;
    }
    ShouldSendDiff = v101;
    goto LABEL_134;
  }
  v26 = Windows::Compat::Appraiser::Utilities::CopyStringNonConstAlloc(a5 + 13, v105);
  appended = v26;
  if ( v26 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x71u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::Initialize",
        "Failed to copy file path: [0x%x].",
        v26);
    goto LABEL_54;
  }
  LODWORD(v98) = v26;
  v25 = 113;
LABEL_46:
  LODWORD(dwFlags) = appended;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v25,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml.cpp",
    "Windows::Compat::Appraiser::SetupXmlOutputter::Initialize",
    dwFlags,
    (int)"Failed to copy file path: [0x%x].",
    v98);
LABEL_292:
  LODWORD(v98) = appended;
  v97 = "Failed to initialize: [0x%x].";
  v14 = -89;
LABEL_7:
  LODWORD(dwFlags) = appended;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v14,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::InitializeOutputterComponents",
    dwFlags,
    (int)v97,
    v98);
LABEL_295:
  for ( k = 0; k < 0xE; ++k )
  {
    v91 = *(&v147)[3 * k];
    if ( v91 )
    {
      v92 = GetProcessHeap();
      HeapFree(v92, 0, v91);
      *(&v147)[3 * k] = 0;
    }
  }
  `eh vector destructor iterator'(
    &v147,
    0x18u,
    0xEu,
    tip2::details::merged_data<_tip_MercuryRestoreExtendedAppsSuccess_attributes,tip2::test_data_basic>::on_result);
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  *(_OWORD *)hHeap = 0;
  v135 = 0;
  *(_OWORD *)lpMem = 0;
  if ( v133[1] )
    HeapFree(v131[0], 0, v133[1]);
  *(_OWORD *)v131 = 0;
  v132 = 0;
  *(_OWORD *)v133 = 0;
  if ( v139[1] )
    HeapFree(v137[0], 0, v139[1]);
  *(_OWORD *)v137 = 0;
  v138 = 0;
  *(_OWORD *)v139 = 0;
  if ( v122[1] )
    HeapFree(v120[0], 0, v122[1]);
  *(_OWORD *)v120 = 0;
  v121 = 0;
  *(_OWORD *)v122 = 0;
  if ( v142[1] )
    HeapFree(v140[0], 0, v142[1]);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18003f0b8  push    rbp
0x18003f0ba  push    rbx
0x18003f0bb  push    rsi
0x18003f0bc  push    rdi
0x18003f0bd  push    r12
0x18003f0bf  push    r13
0x18003f0c1  push    r14
0x18003f0c3  push    r15
0x18003f0c5  lea     rbp, [rsp-618h]
0x18003f0cd  sub     rsp, 748h
0x18003f0d4  mov     [rbp+650h+var_4F8], 0FFFFFFFFFFFFFFFEh
0x18003f0df  mov     rax, cs:__security_cookie
0x18003f0e6  xor     rax, rsp
0x18003f0e9  mov     [rbp+650h+var_50], rax
0x18003f0f0  mov     r13, r9
0x18003f0f3  mov     r15, r8
0x18003f0f6  mov     rbx, rdx
0x18003f0f9  mov     [rbp+650h+var_6B0], rdx
0x18003f0fd  mov     [rbp+650h+var_6C8], rcx
0x18003f101  mov     r12, [rbp+650h+arg_20]
0x18003f108  mov     rax, [rbp+650h+arg_28]
0x18003f10f  mov     [rbp+650h+var_6A8], rax
0x18003f113  xorps   xmm0, xmm0
0x18003f116  movups  xmmword ptr [rbp+650h+var_530], xmm0
0x18003f11d  movups  [rbp+650h+var_520], xmm0
0x18003f124  movups  xmmword ptr [rbp+650h+var_510], xmm0
0x18003f12b  call    cs:__imp_GetProcessHeap
0x18003f131  mov     [rbp+650h+var_530], rax
0x18003f138  mov     edi, 10h
0x18003f13d  mov     [rbp+650h+var_510], rdi
0x18003f144  xorps   xmm0, xmm0
0x18003f147  movdqu  [rbp+650h+var_520], xmm0
0x18003f14f  mov     [rbp+650h+var_510+8], 0
0x18003f15a  lea     esi, [rdi-8]
0x18003f15d  mov     [rbp+650h+var_530+8], rsi
0x18003f164  movups  xmmword ptr [rbp+650h+var_630], xmm0
0x18003f168  movups  [rbp+650h+var_620], xmm0
0x18003f16c  movups  xmmword ptr [rbp+650h+var_610], xmm0
0x18003f170  call    cs:__imp_GetProcessHeap
0x18003f176  mov     [rbp+650h+var_630], rax
0x18003f17a  mov     [rbp+650h+var_610], rdi
0x18003f17e  xorps   xmm0, xmm0
0x18003f181  movdqu  [rbp+650h+var_620], xmm0
0x18003f186  xor     eax, eax
0x18003f188  mov     [rbp+650h+var_610+8], rax
0x18003f18c  mov     [rbp+650h+var_630+8], rsi
0x18003f190  mov     [rbp+650h+var_5E0], rax
0x18003f194  mov     [rbp+650h+var_5E8], rax
0x18003f198  mov     qword ptr [rbp+650h+var_5D8], rax
0x18003f19c  mov     qword ptr [rbp+650h+var_5D0], rax
0x18003f1a3  mov     [rbp+650h+var_660], rax
0x18003f1a7  mov     [rbp+650h+var_648], rax
0x18003f1ab  mov     [rbp+650h+var_658], rax
0x18003f1af  mov     [rbp+650h+var_640], rax
0x18003f1b3  mov     [rbp+650h+var_638], rax
0x18003f1b7  mov     [rbp+650h+var_650], rax
0x18003f1bb  mov     [rbp+650h+var_5C8], rax
0x18003f1c2  mov     [rbp+650h+var_500], rax
0x18003f1c9  mov     [rbp+650h+var_5F8], rax
0x18003f1cd  mov     [rbp+650h+var_5F0], rax
0x18003f1d1  mov     qword ptr [rbp+650h+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003f1d5  mov     qword ptr [rbp+650h+SystemTime.wYear], rax
0x18003f1d9  movups  xmmword ptr [rbp+650h+var_560], xmm0
0x18003f1e0  movups  [rbp+650h+var_550], xmm0
0x18003f1e7  movups  xmmword ptr [rbp+650h+var_540], xmm0
0x18003f1ee  call    cs:__imp_GetProcessHeap
0x18003f1f4  mov     [rbp+650h+var_560], rax
0x18003f1fb  mov     [rbp+650h+var_540], rdi
0x18003f202  xorps   xmm0, xmm0
0x18003f205  movdqu  [rbp+650h+var_550], xmm0
0x18003f20d  mov     [rbp+650h+var_540+8], 0
0x18003f218  mov     [rbp+650h+var_560+8], rsi
0x18003f21f  movups  xmmword ptr [rbp+650h+var_5C0], xmm0
0x18003f226  movups  [rbp+650h+var_5B0], xmm0
0x18003f22d  movups  xmmword ptr [rbp+650h+var_5A0], xmm0
0x18003f234  call    cs:__imp_GetProcessHeap
0x18003f23a  mov     [rbp+650h+var_5C0], rax
0x18003f241  mov     [rbp+650h+var_5A0], rdi
0x18003f248  xorps   xmm0, xmm0
0x18003f24b  movdqu  [rbp+650h+var_5B0], xmm0
0x18003f253  mov     [rbp+650h+var_5A0+8], 0
0x18003f25e  mov     [rbp+650h+var_5C0+8], rsi
0x18003f265  movups  xmmword ptr [rbp+650h+hHeap], xmm0
0x18003f26c  movups  [rbp+650h+var_580], xmm0
0x18003f273  movups  xmmword ptr [rbp+650h+lpMem], xmm0
0x18003f27a  call    cs:__imp_GetProcessHeap
0x18003f280  mov     [rbp+650h+hHeap], rax
0x18003f287  mov     [rbp+650h+lpMem], rdi
0x18003f28e  xorps   xmm0, xmm0
0x18003f291  movdqu  [rbp+650h+var_580], xmm0
0x18003f299  mov     [rbp+650h+lpMem+8], 0
0x18003f2a4  mov     [rbp+650h+hHeap+8], rsi
0x18003f2ab  mov     rax, [r13+30h]
0x18003f2af  lea     rcx, [rbp+650h+var_5E0]
0x18003f2b3  mov     [rbp+650h+var_440], rcx
0x18003f2ba  mov     [rbp+650h+var_438], rax
0x18003f2c1  lea     rcx, aHsAppraiserSet_1; "%hs_APPRAISER_SetupOutput.xml"
0x18003f2c8  mov     [rbp+650h+var_430], rcx
0x18003f2cf  lea     rcx, [rbp+650h+var_5E8]
0x18003f2d3  mov     [rbp+650h+var_428], rcx
0x18003f2da  mov     [rbp+650h+var_420], rax
0x18003f2e1  lea     rcx, aHsAppraiserMig; "%hs_APPRAISER_Migration.xml"
0x18003f2e8  mov     [rbp+650h+var_418], rcx
0x18003f2ef  lea     rcx, [rbp+650h+var_5D8]
0x18003f2f3  mov     [rbp+650h+var_410], rcx
0x18003f2fa  mov     [rbp+650h+var_408], rax
0x18003f301  lea     rcx, aHsAppraiserUtc_0; "%hs_APPRAISER_UtcOutput.xml"
0x18003f308  mov     [rbp+650h+var_400], rcx
0x18003f30f  lea     rcx, [rbp+650h+var_5D0]
0x18003f316  mov     [rbp+650h+var_3F8], rcx
0x18003f31d  mov     [rbp+650h+var_3F0], rax
0x18003f324  lea     rcx, aHsAppraiserUtc; "%hs_APPRAISER_UtcOutputVersioned.xml"
0x18003f32b  mov     [rbp+650h+var_3E8], rcx
0x18003f332  lea     rcx, [rbp+650h+var_660]
0x18003f336  mov     [rbp+650h+var_3E0], rcx
0x18003f33d  mov     [rbp+650h+var_3D8], rax
0x18003f344  lea     rcx, aHsAppraiserEve_1; "%hs_APPRAISER_EverythingAppInteresting."...
0x18003f34b  mov     [rbp+650h+var_3D0], rcx
0x18003f352  lea     rcx, [rbp+650h+var_648]
0x18003f356  mov     [rbp+650h+var_3C8], rcx
0x18003f35d  mov     [rbp+650h+var_3C0], rax
0x18003f364  lea     rcx, aHsAppraiserEve_0; "%hs_APPRAISER_EverythingAppUninterestin"...
0x18003f36b  mov     [rbp+650h+var_3B8], rcx
0x18003f372  lea     rcx, [rbp+650h+var_658]
0x18003f376  mov     [rbp+650h+var_3B0], rcx
0x18003f37d  mov     [rbp+650h+var_3A8], rax
0x18003f384  lea     rcx, aHsAppraiserEve_2; "%hs_APPRAISER_EverythingDevInteresting."...
0x18003f38b  mov     [rbp+650h+var_3A0], rcx
0x18003f392  lea     rcx, [rbp+650h+var_640]
0x18003f396  mov     [rbp+650h+var_398], rcx
0x18003f39d  mov     [rbp+650h+var_390], rax
0x18003f3a4  lea     rcx, aHsAppraiserEve; "%hs_APPRAISER_EverythingDevUninterestin"...
0x18003f3ab  mov     [rbp+650h+var_388], rcx
0x18003f3b2  lea     rcx, [rbp+650h+var_638]
0x18003f3b6  mov     [rbp+650h+var_380], rcx
0x18003f3bd  mov     [rbp+650h+var_378], rax
0x18003f3c4  lea     rcx, aHsAppraiserEve_4; "%hs_APPRAISER_EverythingSys.bin"
0x18003f3cb  mov     [rbp+650h+var_370], rcx
0x18003f3d2  lea     rcx, [rbp+650h+var_650]
0x18003f3d6  mov     [rbp+650h+var_368], rcx
0x18003f3dd  mov     [rbp+650h+var_360], rax
0x18003f3e4  lea     rcx, aHsAppraiserEve_3; "%hs_APPRAISER_EverythingGated.bin"
0x18003f3eb  mov     [rbp+650h+var_358], rcx
0x18003f3f2  lea     rcx, [rbp+650h+var_5C8]
0x18003f3f9  mov     [rbp+650h+var_350], rcx
0x18003f400  mov     [rbp+650h+var_348], rax
0x18003f407  lea     rcx, aHsAppraiserHum_0; "%hs_APPRAISER_HumanReadable.xml"
0x18003f40e  mov     [rbp+650h+var_340], rcx
0x18003f415  lea     rcx, [rbp+650h+var_500]
0x18003f41c  mov     [rbp+650h+var_338], rcx
0x18003f423  mov     [rbp+650h+var_330], rax
0x18003f42a  lea     rcx, aHsAppraiserHum; "%hs_APPRAISER_HumanReadable_Intermediat"...
0x18003f431  mov     [rbp+650h+var_328], rcx
0x18003f438  lea     rcx, [rbp+650h+var_5F8]
0x18003f43c  mov     [rbp+650h+var_320], rcx
0x18003f443  mov     [rbp+650h+var_318], rax
0x18003f44a  lea     rcx, aHsAppraiserSet_0; "%hs_APPRAISER_SetupOutputHw.xml"
0x18003f451  mov     [rbp+650h+var_310], rcx
0x18003f458  lea     rcx, [rbp+650h+var_5F0]
0x18003f45c  mov     [rbp+650h+var_308], rcx
0x18003f463  mov     [rbp+650h+var_300], rax
0x18003f46a  lea     rax, aHsAppraiserSet; "%hs_APPRAISER_SetupOutputDrv.xml"
0x18003f471  mov     [rbp+650h+var_2F8], rax
0x18003f478  xor     edx, edx
0x18003f47a  lea     rax, [rdx+rdx*2]
0x18003f47e  mov     rcx, [rbp+rax*8+650h+var_440]
0x18003f486  mov     qword ptr [rcx], 0
0x18003f48d  inc     rdx
0x18003f490  cmp     rdx, 0Eh
0x18003f494  jb      short loc_18003F47A
0x18003f496  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003f49d  mov     ecx, 0A8h; unsigned __int64
0x18003f4a2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003f4a7  mov     [rbx], rax
0x18003f4aa  test    rax, rax
0x18003f4ad  jz      loc_180040EB6
0x18003f4b3  lea     rcx, [rbp+650h+var_530]
0x18003f4ba  call    ?Initialize@?$RtlArray@PEAVIProperty@Appraiser@Compat@Windows@@@@QEAAJ_K@Z; RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(unsigned __int64)
0x18003f4bf  mov     edi, eax
0x18003f4c1  lea     rbx, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x18003f4c8  test    eax, eax
0x18003f4ca  jns     short loc_18003F4FB
0x18003f4cc  lea     r9, aWindowsCompatA_460; "Windows::Compat::Appraiser::SetupApprai"...
0x18003f4d3  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18003f4da  mov     edx, 0C74h; bool
0x18003f4df  mov     dword ptr [rsp+780h+var_750], edi; char *
0x18003f4e3  mov     qword ptr [rsp+780h+var_758], rbx; int
0x18003f4e8  mov     [rsp+780h+dwFlags], edi; char *
0x18003f4ec  mov     ecx, 1; this
0x18003f4f1  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18003f4f6  jmp     loc_180040EBB
0x18003f4fb  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003f501  lea     rsi, aWindowsCompatA_460; "Windows::Compat::Appraiser::SetupApprai"...
0x18003f508  lea     r14, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18003f50f  test    al, 1
0x18003f511  jz      short loc_18003F52A
0x18003f513  mov     [rsp+780h+dwFlags], edi
0x18003f517  mov     r9, rbx; char *
0x18003f51a  mov     r8, rsi; char *
0x18003f51d  mov     rdx, r14; char *
0x18003f520  mov     ecx, 0C74h; unsigned int
0x18003f525  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003f52a  lea     rcx, [rbp+650h+var_630]
0x18003f52e  call    ?Initialize@?$RtlArray@PEAVIProperty@Appraiser@Compat@Windows@@@@QEAAJ_K@Z; RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(unsigned __int64)
0x18003f533  mov     edi, eax
0x18003f535  test    eax, eax
0x18003f537  jns     short loc_18003F546
0x18003f539  mov     r9, rsi
0x18003f53c  mov     r8, r14
0x18003f53f  mov     edx, 0C75h
0x18003f544  jmp     short loc_18003F4DF
0x18003f546  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003f54c  test    al, 1
0x18003f54e  jz      short loc_18003F567
0x18003f550  mov     [rsp+780h+dwFlags], edi
0x18003f554  mov     r9, rbx; char *
0x18003f557  mov     r8, rsi; char *
0x18003f55a  mov     rdx, r14; char *
0x18003f55d  mov     ecx, 0C75h; unsigned int
0x18003f562  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003f567  xor     ebx, ebx
0x18003f569  call    cs:__imp_GetProcessHeap
0x18003f56f  mov     rcx, rax; hHeap
0x18003f572  xor     edx, edx; dwFlags
0x18003f574  mov     r8d, 208h; dwBytes
0x18003f57a  call    cs:__imp_HeapAlloc
0x18003f580  lea     r8, [rbx+rbx*2]
0x18003f584  mov     rcx, [rbp+r8*8+650h+var_440]
0x18003f58c  mov     [rcx], rax
0x18003f58f  mov     rax, [rbp+r8*8+650h+var_440]
0x18003f597  mov     rcx, [rax]; pszPathOut
0x18003f59a  test    rcx, rcx
0x18003f59d  jz      loc_180040EB6
0x18003f5a3  mov     r9, [rbp+r8*8+650h+var_430]; unsigned __int16 *
0x18003f5ab  mov     r8, [rbp+r8*8+650h+var_438]; unsigned __int16 *
0x18003f5b3  call    ?CombinePathAndAppendRunId@SetupAppraiser@Appraiser@Compat@Windows@@CAJPEAG_KPEBG2@Z; Windows::Compat::Appraiser::SetupAppraiser::CombinePathAndAppendRunId(ushort *,unsigned __int64,ushort const *,ushort const *)
0x18003f5b8  mov     edi, eax
0x18003f5ba  test    eax, eax
0x18003f5bc  js      loc_180040E96
0x18003f5c2  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003f5c8  test    al, 1
0x18003f5ca  jz      short loc_18003F5E7
0x18003f5cc  mov     [rsp+780h+dwFlags], edi; dwFlags
0x18003f5d0  lea     r9, aErrorCombining_1; "Error combining and printing: [0x%x]."
0x18003f5d7  mov     r8, rsi; char *
0x18003f5da  mov     rdx, r14; char *
0x18003f5dd  mov     ecx, 0C80h; unsigned int
0x18003f5e2  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003f5e7  inc     rbx
0x18003f5ea  cmp     rbx, 0Eh
0x18003f5ee  jb      loc_18003F569
0x18003f5f4  lea     r9, aImg; "img"
0x18003f5fb  mov     r8, [r13+30h]; pszPathIn
0x18003f5ff  mov     edx, 104h; cchPathOut
0x18003f604  lea     rcx, [rbp+650h+pszPathOut]; pszPathOut
0x18003f60b  call    PathCchCombineEx
0x18003f610  mov     edi, eax
0x18003f612  test    eax, eax
0x18003f614  jns     short loc_18003F636
0x18003f616  mov     dword ptr [rsp+780h+var_750], eax
0x18003f61a  lea     r9, aFailedToCopyPa_0; "Failed to copy path: [0x%x]."
0x18003f621  mov     qword ptr [rsp+780h+var_758], r9
0x18003f626  mov     r9, rsi
0x18003f629  mov     r8, r14
0x18003f62c  mov     edx, 0C87h
0x18003f631  jmp     loc_18003F4E8
0x18003f636  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18003f63c  test    al, 1
0x18003f63e  jz      short loc_18003F65B
0x18003f640  mov     [rsp+780h+dwFlags], edi
0x18003f644  lea     r9, aFailedToCopyPa_0; "Failed to copy path: [0x%x]."
0x18003f64b  mov     r8, rsi; char *
0x18003f64e  mov     rdx, r14; char *
0x18003f651  mov     ecx, 0C87h; unsigned int
0x18003f656  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18003f65b  xor     edi, edi
0x18003f65d  cmp     [r13+4], dil
0x18003f661  jnz     short loc_18003F6C7
0x18003f663  cmp     [r13+0], dil
0x18003f667  jz      short loc_18003F696
0x18003f669  mov     r8, [rbp+650h+var_5F8]
0x18003f66d  test    r8, r8
0x18003f670  jz      short loc_18003F678
0x18003f672  cmp     di, [r8]
0x18003f676  jnz     short loc_18003F67F
0x18003f678  lea     r8, aNone_3; "_NONE_"
0x18003f67f  mov     rbx, [rbp+650h+var_6C8]
0x18003f683  lea     rcx, [rbx+140h]; this
0x18003f68a  mov     edx, 0Dh; unsigned __int64
0x18003f68f  call    ?Set@RtlStringArray@@QEAAJ_KPEBG0@Z; RtlStringArray::Set(unsigned __int64,ushort const *,unsigned __int64)
0x18003f694  jmp     short loc_18003F69A
0x18003f696  mov     rbx, [rbp+650h+var_6C8]
0x18003f69a  cmp     [r13+2], dil
0x18003f69e  jz      short loc_18003F6C7
0x18003f6a0  mov     r8, [rbp+650h+var_5F0]
0x18003f6a4  test    r8, r8
0x18003f6a7  jz      short loc_18003F6AF
0x18003f6a9  cmp     di, [r8]
0x18003f6ad  jnz     short loc_18003F6B6
0x18003f6af  lea     r8, aNone_3; "_NONE_"
  ... truncated ...
```
