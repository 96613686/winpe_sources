# Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult(ulong,void *,RtlStringArray &,RtlArray<ushort const *> &,Windows::Compat::Appraiser::IPropertyAppender *,ushort const *,void *,bool,Windows::Compat::Appraiser::SdbDataSourcePropertyCounter &,Windows::Compat::Appraiser::IPropertyAppender *)

- ea: `0x1801f6934`
- end: `0x1801f8b52`
- name: `?CheckAppQueryResult@SdbUtils@Appraiser@Compat@Windows@@SAJKPEAXAEAVRtlStringArray@@AEAV?$RtlArray@PEBG@@PEAVIPropertyAppender@234@PEBG0_NAEAUSdbDataSourcePropertyCounter@234@3@Z`
- size: `8734`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801e5490`
- `0x1801e83d4`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x180013f90`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18003b2a0`
- `0x180083278`
- `0x180083390`
- `0x180088940`
- `0x18008a254`
- `0x18008b374`
- `0x18008b5f8`
- `0x18008badc`
- `0x1800a5d88`
- `0x1801b3564`
- `0x1801baf00`
- `0x1801bbb00`
- `0x1801bc984`
- `0x1801f6934`
- `0x1801f9834`
- `0x1801f9ef8`
- `0x1801fadc8`
- `0x1801fbe7c`
- `0x1801fbf8c`
- `0x1801fcaf8`
- `0x1801fdb28`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x1801f6c36`
- `KERNEL32!InitOnceExecuteOnce` at `0x1801f6c36`
- `KERNEL32!GetProcessHeap` at `0x1801f69d0`
- `KERNEL32!GetProcessHeap` at `0x1801f69e1`
- `KERNEL32!GetProcessHeap` at `0x1801f6a13`
- `KERNEL32!GetProcessHeap` at `0x1801f6a4b`
- `KERNEL32!GetProcessHeap` at `0x1801f6f20`
- `KERNEL32!GetProcessHeap` at `0x1801f6f4a`
- `KERNEL32!GetProcessHeap` at `0x1801f6fa8`
- `KERNEL32!GetProcessHeap` at `0x1801f6fc8`
- `KERNEL32!GetProcessHeap` at `0x1801f8a52`
- `KERNEL32!GetProcessHeap` at `0x1801f8a6f`
- `KERNEL32!GetProcessHeap` at `0x1801f8a8c`
- `KERNEL32!GetProcessHeap` at `0x1801f8aa5`
- `KERNEL32!GetProcessHeap` at `0x1801f8ac2`
- `KERNEL32!GetProcessHeap` at `0x1801f69d0`
- `KERNEL32!GetProcessHeap` at `0x1801f69e1`
- `KERNEL32!GetProcessHeap` at `0x1801f6a13`
- `KERNEL32!GetProcessHeap` at `0x1801f6a4b`
- `KERNEL32!GetProcessHeap` at `0x1801f6f20`
- `KERNEL32!GetProcessHeap` at `0x1801f6f4a`
- `KERNEL32!GetProcessHeap` at `0x1801f6fa8`
- `KERNEL32!GetProcessHeap` at `0x1801f6fc8`
- `KERNEL32!GetProcessHeap` at `0x1801f8a52`
- `KERNEL32!GetProcessHeap` at `0x1801f8a6f`
- `KERNEL32!GetProcessHeap` at `0x1801f8a8c`
- `KERNEL32!GetProcessHeap` at `0x1801f8aa5`
- `KERNEL32!GetProcessHeap` at `0x1801f8ac2`
- `KERNEL32!HeapFree` at `0x1801f6f2e`
- `KERNEL32!HeapFree` at `0x1801f6f58`
- `KERNEL32!HeapFree` at `0x1801f6fb6`
- `KERNEL32!HeapFree` at `0x1801f6fd6`
- `KERNEL32!HeapFree` at `0x1801f8a60`
- `KERNEL32!HeapFree` at `0x1801f8a7d`
- `KERNEL32!HeapFree` at `0x1801f8a9a`
- `KERNEL32!HeapFree` at `0x1801f8ab3`
- `KERNEL32!HeapFree` at `0x1801f8ad0`
- `KERNEL32!HeapFree` at `0x1801f8aec`
- `KERNEL32!HeapFree` at `0x1801f8b08`
- `KERNEL32!HeapFree` at `0x1801f8b27`
- `KERNEL32!HeapFree` at `0x1801f6f2e`
- `KERNEL32!HeapFree` at `0x1801f6f58`
- `KERNEL32!HeapFree` at `0x1801f6fb6`
- `KERNEL32!HeapFree` at `0x1801f6fd6`
- `KERNEL32!HeapFree` at `0x1801f8a60`
- `KERNEL32!HeapFree` at `0x1801f8a7d`
- `KERNEL32!HeapFree` at `0x1801f8a9a`
- `KERNEL32!HeapFree` at `0x1801f8ab3`
- `KERNEL32!HeapFree` at `0x1801f8ad0`
- `KERNEL32!HeapFree` at `0x1801f8aec`
- `KERNEL32!HeapFree` at `0x1801f8b08`
- `KERNEL32!HeapFree` at `0x1801f8b27`

## string_xrefs

- `0x1801f8123`: `ReinstallUpgradeMessage`
- `0x1801f814f`: `ReinstallUpgradeMessage`
- `0x1801f8171`: `ReinstallUpgradeMessage`
- `0x1801f81a9`: `ReinstallUpgradeMessageRedirectionInstruction`
- `0x1801f81d1`: `ReinstallUpgradeMessageRedirectionInstruction`
- `0x1801f81f3`: `ReinstallUpgradeMessageRedirectionInstruction`
- `0x1801f8321`: `ReinstallUpgradeTitleRedirectionInstruction`
- `0x1801f8349`: `ReinstallUpgradeTitleRedirectionInstruction`
- `0x1801f836b`: `ReinstallUpgradeTitleRedirectionInstruction`
- `0x1801f829b`: `ReinstallUpgradeTitle`
- `0x1801f82c7`: `ReinstallUpgradeTitle`
- `0x1801f82e9`: `ReinstallUpgradeTitle`
- `0x1801f8941`: `SdbHyperlinkTarget`
- `0x1801f89c9`: `SdbHyperlinkText`
- `0x1801f89ee`: `SdbHyperlinkText`
- `0x1801f89ff`: `SdbHyperlinkText`
- `0x1801f847d`: `MigShimCommand`
- `0x1801f84a2`: `MigShimCommand`
- `0x1801f84b3`: `MigShimCommand`
- `0x1801f80b1`: `MigXmlType`
- `0x1801f80de`: `MigXmlType`
- `0x1801f80ef`: `MigXmlType`
- `0x1801f7fd6`: `MigXmlName`
- `0x1801f7ffb`: `MigXmlName`
- `0x1801f800c`: `MigXmlName`
- `0x1801f8040`: `MigXmlValue`
- `0x1801f8065`: `MigXmlValue`
- `0x1801f8076`: `MigXmlValue`
- `0x1801f7f66`: `ReinstallAfterUpgrade`
- `0x1801f7f91`: `ReinstallAfterUpgrade`
- `0x1801f7fa2`: `ReinstallAfterUpgrade`
- `0x1801f78df`: `SdbFwLink`
- `0x1801f790b`: `SdbFwLink`
- `0x1801f822e`: `ReinstallUpgradeMessageStringPresent`
- `0x1801f8256`: `ReinstallUpgradeMessageStringPresent`
- `0x1801f8267`: `ReinstallUpgradeMessageStringPresent`
- `0x1801f6c60`: `Failed to read exe GUID from os upgrade entry: [0x%x].`
- `0x1801f6c81`: `Failed to read exe GUID from os upgrade entry: [0x%x].`
- `0x1801f7303`: `Failed to read exe GUID from os upgrade entry: [0x%x].`
- `0x1801f7324`: `Failed to read exe GUID from os upgrade entry: [0x%x].`
- `0x1801f73c7`: `Failed to read app name from os upgrade entry: [0x%x].`
- `0x1801f73ed`: `Failed to read app name from os upgrade entry: [0x%x].`
- `0x1801f7357`: `Failed to read app GUID from os upgrade entry: [0x%x].`
- `0x1801f737d`: `Failed to read app GUID from os upgrade entry: [0x%x].`
- `0x1801f7439`: `Failed to read app vendor from os upgrade entry: [0x%x].`
- `0x1801f745f`: `Failed to read app vendor from os upgrade entry: [0x%x].`
- `0x1801f83a6`: `ReinstallUpgradeTitleStringPresent`
- `0x1801f83ce`: `ReinstallUpgradeTitleStringPresent`
- `0x1801f83df`: `ReinstallUpgradeTitleStringPresent`
- `0x1801f7ef6`: `ReinstallAfterUpgradeWarn`
- `0x1801f7f21`: `ReinstallAfterUpgradeWarn`
- `0x1801f7f32`: `ReinstallAfterUpgradeWarn`
- `0x1801f6b59`: `onecore\base\appcompat\appraiser\datasource\sdbutils.cpp`
- `0x1801f6b8d`: `onecore\base\appcompat\appraiser\datasource\sdbutils.cpp`
- `0x1801f76c5`: `onecore\base\appcompat\appraiser\datasource\sdbutils.cpp`
- `0x1801f6b52`: `Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult`
- `0x1801f6b86`: `Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult`
- `0x1801f76be`: `Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult`
- `0x1801f6f7b`: `BLOCK_UPGRADE GENERIC_MESSAGE attributes SUMMARY_MSG_RC_ID and TITLE_MSG_RC_ID must come as a pair.`
- `0x1801f7a22`: `BlockUpgradeCanReinstall`
- `0x1801f7a54`: `BlockUpgradeCanReinstall`
- `0x1801f7a97`: `BlockUpgradeCanReinstall`
- `0x1801f7e86`: `ReinstallAfterUpgradeInfo`
- `0x1801f7eb1`: `ReinstallAfterUpgradeInfo`
- `0x1801f7ec2`: `ReinstallAfterUpgradeInfo`
- `0x1801f7acb`: `BlockUpgradeUntilUpdate`
- `0x1801f7af6`: `BlockUpgradeUntilUpdate`
- `0x1801f7b07`: `BlockUpgradeUntilUpdate`
- `0x1801f7214`: `Retrieving MigXml info failed: [0x%x].`
- `0x1801f786d`: `Custom Sdb entry does not include Appraiser CustomMigXml tag`
- `0x1801f7680`: `CustomMigXML`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult(
        unsigned int a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        struct Windows::Compat::Appraiser::IPropertyAppender *a5,
        char *a6,
        void *a7,
        char a8,
        struct Windows::Compat::Appraiser::SdbDataSourcePropertyCounter *a9,
        __int64 *a10)
{
  int v12; // eax
  int SdbEntryTargets; // ebx
  char v14; // dl
  const char *v15; // r9
  HANDLE *v16; // rdx
  __int64 v17; // rax
  unsigned int v18; // ebx
  unsigned int FirstTagRef; // eax
  unsigned __int64 v20; // r9
  unsigned int v21; // eax
  char v22; // r13
  int DWORDTagRef; // eax
  char v24; // cl
  char *v25; // rbx
  int v26; // eax
  int v27; // r15d
  unsigned __int16 *v28; // r15
  int v29; // eax
  unsigned __int16 *v30; // rdi
  void *v31; // rbx
  unsigned __int16 *v32; // r15
  HANDLE ProcessHeap; // rax
  HANDLE v34; // rax
  HANDLE v35; // rax
  HANDLE v36; // rax
  char *v37; // r13
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // r15d
  char v41; // bl
  char v42; // r15
  unsigned __int64 v43; // r9
  char v44; // dl
  const char *v45; // rax
  unsigned int v46; // r15d
  signed int MigrationData; // eax
  unsigned __int16 *v48; // r13
  bool v49; // sf
  int v50; // eax
  int AppGuid; // eax
  bool v52; // r13
  int AppraiserDataTagsInternal; // eax
  char v54; // r15
  unsigned __int64 v55; // rbx
  unsigned __int64 v56; // rcx
  char *v57; // rsi
  unsigned __int64 v58; // r14
  char *v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rax
  unsigned __int64 v62; // r9
  unsigned __int64 v63; // rax
  unsigned int v64; // eax
  __int64 v65; // rax
  unsigned int v66; // r13d
  bool v67; // r15
  const char *v68; // rax
  char v69; // dl
  bool v70; // zf
  struct Windows::Compat::Appraiser::IPropertyAppender *v71; // r15
  int appended; // eax
  int v73; // eax
  struct Windows::Compat::Appraiser::IPropertyAppender *v74; // r13
  const unsigned __int16 *v75; // rax
  const char *v76; // rax
  char v77; // dl
  int v78; // eax
  unsigned __int16 *v79; // r12
  int v80; // eax
  unsigned int v81; // r12d
  unsigned __int16 *v82; // r15
  int v83; // eax
  int v84; // eax
  unsigned __int16 *v85; // r15
  int v86; // eax
  int v87; // eax
  unsigned __int64 v88; // rdx
  __int64 *v89; // rax
  __int64 v90; // rcx
  __int64 v91; // rax
  __int64 v92; // r10
  const unsigned __int16 **v93; // rcx
  unsigned __int64 v94; // rax
  const wchar_t **v95; // rax
  int v96; // eax
  const unsigned __int16 **v97; // rax
  unsigned __int64 v98; // r15
  unsigned __int64 *v99; // r8
  unsigned __int64 *v100; // r12
  unsigned __int64 v101; // rax
  const unsigned __int16 **v102; // rdx
  unsigned __int64 v103; // rax
  unsigned __int64 v104; // rcx
  __int64 v105; // rax
  int v106; // eax
  unsigned __int16 *v107; // rdi
  HANDLE v108; // rax
  unsigned __int16 *v109; // rdi
  HANDLE v110; // rax
  HANDLE v111; // rax
  HANDLE v112; // rax
  unsigned __int16 *v113; // rdi
  HANDLE v114; // rax
  char *v116; // [rsp+20h] [rbp-E0h]
  char *v117; // [rsp+20h] [rbp-E0h]
  char *v118; // [rsp+20h] [rbp-E0h]
  char *v119; // [rsp+20h] [rbp-E0h]
  char *v120; // [rsp+20h] [rbp-E0h]
  const char *v121; // [rsp+28h] [rbp-D8h]
  const char *v122; // [rsp+28h] [rbp-D8h]
  char *v123; // [rsp+30h] [rbp-D0h]
  char *v124; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v125; // [rsp+30h] [rbp-D0h]
  int v126; // [rsp+38h] [rbp-C8h]
  __int64 v127; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v128; // [rsp+48h] [rbp-B8h]
  bool v129; // [rsp+50h] [rbp-B0h] BYREF
  bool v130; // [rsp+51h] [rbp-AFh] BYREF
  bool v131; // [rsp+52h] [rbp-AEh] BYREF
  bool v132; // [rsp+53h] [rbp-ADh] BYREF
  unsigned int v133; // [rsp+54h] [rbp-ACh]
  _BYTE v134[39]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v135; // [rsp+80h] [rbp-80h] BYREF
  int v136; // [rsp+84h] [rbp-7Ch]
  unsigned int v137; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v138; // [rsp+90h] [rbp-70h]
  LPVOID lpMem; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v140; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v141; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v142; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v143; // [rsp+B0h] [rbp-50h] BYREF
  void *v144; // [rsp+B8h] [rbp-48h]
  struct Windows::Compat::Appraiser::IPropertyAppender *v145; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v146; // [rsp+C8h] [rbp-38h] BYREF
  char *v147; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v148; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 *v149; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v150; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v151; // [rsp+F0h] [rbp-10h] BYREF
  int v152; // [rsp+F8h] [rbp-8h] BYREF
  int v153; // [rsp+FCh] [rbp-4h]
  HANDLE v154[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v155; // [rsp+110h] [rbp+10h]
  LPVOID v156[2]; // [rsp+120h] [rbp+20h]
  unsigned __int16 *v157; // [rsp+130h] [rbp+30h] BYREF
  __int64 v158; // [rsp+138h] [rbp+38h]
  unsigned __int16 *v159; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 *v160; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int16 *v161; // [rsp+150h] [rbp+50h]
  struct Windows::Compat::Appraiser::SdbDataSourcePropertyCounter *v162; // [rsp+158h] [rbp+58h]
  HANDLE hHeap[2]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v164; // [rsp+170h] [rbp+70h]
  LPVOID v165[2]; // [rsp+180h] [rbp+80h]
  HANDLE v166[2]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v167; // [rsp+1A0h] [rbp+A0h]
  LPVOID v168[4]; // [rsp+1B0h] [rbp+B0h]
  _BYTE v169[23]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v170[5]; // [rsp+1E8h] [rbp+E8h]
  wchar_t String2[40]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v172[40]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v173[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v174[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  unsigned __int16 v175[264]; // [rsp+6D0h] [rbp+5D0h] BYREF
  unsigned __int16 v176[264]; // [rsp+8E0h] [rbp+7E0h] BYREF

  v170[4] = -2;
  v158 = a4;
  v133 = a1;
  v145 = a5;
  v147 = a6;
  v144 = a7;
  v162 = a9;
  v137 = 0;
  v135 = 0;
  v141 = 0;
  v142 = 0;
  v150 = 0;
  v143 = 0;
  v149 = 0;
  v159 = 0;
  v160 = 0;
  v152 = 0;
  GetProcessHeap();
  *(_OWORD *)v154 = 0;
  *(_OWORD *)v156 = 0;
  v154[0] = GetProcessHeap();
  v156[0] = (LPVOID)16;
  v155 = 0;
  v156[1] = 0;
  v154[1] = (HANDLE)8;
  *(_OWORD *)v166 = 0;
  *(_OWORD *)v168 = 0;
  v166[0] = GetProcessHeap();
  v168[0] = (LPVOID)16;
  v167 = 0;
  v168[1] = 0;
  v166[1] = (HANDLE)8;
  *(_OWORD *)hHeap = 0;
  *(_OWORD *)v165 = 0;
  hHeap[0] = GetProcessHeap();
  v165[0] = (LPVOID)16;
  v164 = 0;
  v165[1] = 0;
  hHeap[1] = (HANDLE)8;
  v170[0] = &v137;
  v170[1] = &v135;
  v170[2] = &v141;
  v170[3] = &v142;
  memset_0(String2, 0, sizeof(String2));
  memset_0(v172, 0, sizeof(v172));
  memset(v134, 0, sizeof(v134));
  v148 = 0;
  v149 = 0;
  v151 = 0;
  v161 = 0;
  v157 = 0;
  v146 = 0;
  v138 = 0;
  v140 = 0;
  v128 = 0;
  lpMem = 0;
  v130 = 0;
  v129 = 0;
  v132 = 0;
  v131 = 0;
  v136 = 0;
  v142 = 0;
  v141 = 0;
  v135 = 0;
  v137 = 0;
  v176[0] = 0;
  v175[0] = 0;
  v12 = RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(v166);
  SdbEntryTargets = v12;
  if ( v12 < 0 )
  {
    LODWORD(v123) = v12;
    v121 = "Failed to initialize RtlArray: [0x%x].";
    v14 = -95;
LABEL_3:
    LODWORD(v116) = SdbEntryTargets;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v14,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      v116,
      (int)v121,
      v123);
    goto LABEL_448;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x3A1u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Failed to initialize RtlArray: [0x%x].",
      v12);
  SdbEntryTargets = Windows::Compat::Appraiser::Utilities::GetSdbEntryTargets(v166, a3, a2, v133);
  if ( SdbEntryTargets < 0 )
  {
    v15 = "Failed to get entry targets: [0x%x].";
    v14 = -92;
LABEL_8:
    LODWORD(v123) = SdbEntryTargets;
    LODWORD(v121) = (_DWORD)v15;
    goto LABEL_3;
  }
  LOBYTE(a3) = 0;
  v153 = a3;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x3A4u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Failed to get entry targets: [0x%x].",
      SdbEntryTargets);
  InitOnceExecuteOnce(
    &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
    Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
    0,
    0);
  if ( Windows::Compat::Appraiser::AppraiserTestHooks::TestHookForceGatedBlock )
  {
    SdbEntryTargets = Windows::Compat::Appraiser::Utilities::GetExeGuid(String2, a2, v133);
    if ( SdbEntryTargets < 0 )
    {
      v15 = "Failed to read exe GUID from os upgrade entry: [0x%x].";
      v14 = -82;
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x3AEu,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to read exe GUID from os upgrade entry: [0x%x].",
        SdbEntryTargets);
    LODWORD(a3) = wcscmp_0(L"{9d9219f4-eccd-4802-92ec-d2acb87281f7}", String2) == 0;
    v153 = a3;
  }
  v16 = v166;
  if ( (_BYTE)a3 )
    v16 = (HANDLE *)v158;
  SdbEntryTargets = Windows::Compat::Appraiser::Utilities::GetTargetListIntersection(hHeap, v16, v158);
  if ( SdbEntryTargets < 0 )
  {
    v15 = "Failed to get applicable targets: [0x%x].";
    v14 = -73;
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x3B7u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Failed to get applicable targets: [0x%x].",
      SdbEntryTargets);
  if ( !(_QWORD)v164 )
  {
    SdbEntryTargets = 1;
    goto LABEL_448;
  }
  if ( a10 )
    v17 = *a10;
  else
    v17 = *(_QWORD *)v145;
  LODWORD(v127) = (*(__int64 (**)(void))(v17 + 8))();
  v18 = v133;
  FirstTagRef = SdbFindFirstTagRef(a2, v133, 0x7029u);
  v137 = FirstTagRef;
  if ( !FirstTagRef )
  {
    v22 = v134[3];
    goto LABEL_59;
  }
  v21 = SdbFindFirstTagRef(a2, FirstTagRef, 0x4047u);
  v22 = 1;
  v134[3] = 1;
  if ( !v21 )
    goto LABEL_60;
  DWORDTagRef = SdbReadDWORDTagRef(a2, v21, 0);
  if ( DWORDTagRef == 1 )
  {
    v24 = 1;
    v134[4] = 1;
    goto LABEL_32;
  }
  v24 = 0;
  v134[4] = 0;
  if ( DWORDTagRef != 2 )
  {
LABEL_32:
    v134[5] = 0;
    if ( !v24 )
      goto LABEL_34;
    goto LABEL_33;
  }
  v134[5] = 1;
LABEL_33:
  v22 = 0;
  v134[3] = 0;
LABEL_34:
  if ( DWORDTagRef == 3 )
  {
    v25 = v147;
    v26 = Windows::Compat::Appraiser::SdbUtils::InflateSdbResourceStringAlloc(
            (unsigned __int16 **)&lpMem,
            &v132,
            0x4026u,
            0x402Cu,
            v137,
            a2,
            (const unsigned __int16 *)v147);
    v27 = v26;
    if ( v26 < 0 )
    {
      SdbEntryTargets = v26;
      LODWORD(v124) = v26;
      LODWORD(v117) = v26;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        230,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        v117,
        (int)"Failed InflateSdbResourceStringAlloc: [0x%x]",
        v124);
      v28 = (unsigned __int16 *)lpMem;
      goto LABEL_443;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x3E6u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed InflateSdbResourceStringAlloc: [0x%x]",
        v26);
    v29 = Windows::Compat::Appraiser::SdbUtils::InflateSdbResourceStringAlloc(
            &v140,
            &v131,
            0x4059u,
            0x402Bu,
            v137,
            a2,
            (const unsigned __int16 *)v25);
    SdbEntryTargets = v29;
    if ( v29 < 0 )
    {
      LODWORD(v123) = v29;
      LODWORD(v118) = v29;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        240,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        v118,
        (int)"Failed InflateSdbResourceStringAlloc: [0x%x]",
        v123);
      v28 = (unsigned __int16 *)lpMem;
      v30 = v140;
      goto LABEL_444;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x3F0u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed InflateSdbResourceStringAlloc: [0x%x]",
        v29);
    if ( v27 == 1 || SdbEntryTargets == 1 )
    {
      v31 = lpMem;
      v128 = (unsigned __int16 *)lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v31);
        v31 = 0;
        v128 = 0;
      }
      v32 = v140;
      v138 = v140;
      if ( v140 )
      {
        v34 = GetProcessHeap();
        HeapFree(v34, 0, v32);
        v32 = 0;
        v138 = 0;
      }
    }
    else
    {
      v31 = lpMem;
      v128 = (unsigned __int16 *)lpMem;
      v32 = v140;
      v138 = v140;
    }
    if ( (v31 == 0) != (v32 == 0) )
    {
      LODWORD(v118) = -2147024809;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        3,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        v118,
        (int)"BLOCK_UPGRADE GENERIC_MESSAGE attributes SUMMARY_MSG_RC_ID and TITLE_MSG_RC_ID must come as a pair.",
        v123);
      if ( v31 )
      {
        v35 = GetProcessHeap();
        HeapFree(v35, 0, v31);
        v128 = 0;
      }
      if ( v32 )
      {
        v36 = GetProcessHeap();
        HeapFree(v36, 0, v32);
        v138 = 0;
      }
    }
    v18 = v133;
  }
LABEL_59:
  if ( !v22 )
  {
    v37 = v147;
    goto LABEL_63;
  }
LABEL_60:
  v37 = v147;
  if ( !v134[38] )
    Windows::Compat::Appraiser::SdbUtils::GetHyperlinkInfo(
      &v134[38],
      &v148,
      v173,
      v20,
      a2,
      v137,
      (const unsigned __int16 *)v147);
LABEL_63:
  v38 = SdbFindFirstTagRef(a2, v18, 0x7027u);
  v135 = v38;
  if ( !v38 )
  {
LABEL_69:
    v42 = v134[30];
    v41 = v134[29];
    goto LABEL_70;
  }
  v134[28] = 1;
  v39 = SdbFindFirstTagRef(a2, v38, 0x4046u);
  v40 = v39;
  if ( !v39 )
  {
    v38 = v135;
    goto LABEL_69;
  }
  v41 = (unsigned int)SdbReadDWORDTagRef(a2, v39, 0) == 1;
  v134[29] = v41;
  v42 = (unsigned int)SdbReadDWORDTagRef(a2, v40, 0) == 2;
  v134[30] = v42;
  if ( v41 || v42 )
  {
    v134[28] = 0;
    v38 = v135;
LABEL_70:
    if ( v41 || v42 )
    {
      SdbEntryTargets = Windows::Compat::Appraiser::SdbUtils::InflateSdbResourceStringAlloc(
                          &v146,
                          &v129,
                          0x4026u,
                          0x402Cu,
                          v38,
                          a2,
                          (const unsigned __int16 *)v37);
      if ( SdbEntryTargets < 0 )
      {
        v44 = 51;
LABEL_74:
        v45 = "Failed InflateSdbResourceStringAlloc: [0x%x]";
LABEL_75:
        LODWORD(v123) = SdbEntryTargets;
        LODWORD(v122) = (_DWORD)v45;
LABEL_76:
        LODWORD(v119) = SdbEntryTargets;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          v44,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
          "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
          v119,
          (int)v122,
          v123);
LABEL_438:
        v28 = v128;
        goto LABEL_439;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x433u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
          "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
          "Failed InflateSdbResourceStringAlloc: [0x%x]",
          SdbEntryTargets);
      if ( v146 )
      {
        SdbEntryTargets = Windows::Compat::Appraiser::SdbUtils::InflateSdbResourceStringAlloc(
                            &v157,
                            &v130,
                            0x4059u,
                            0x402Bu,
                            v135,
                            a2,
                            (const unsigned __int16 *)v37);
        if ( SdbEntryTargets < 0 )
        {
          v44 = 62;
          goto LABEL_74;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x43Eu,
            "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
            "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
            "Failed InflateSdbResourceStringAlloc: [0x%x]",
            SdbEntryTargets);
      }
      if ( v42 && !v134[38] )
        Windows::Compat::Appraiser::SdbUtils::GetHyperlinkInfo(
          &v134[38],
          &v148,
          v173,
          v43,
          a2,
          v135,
          (const unsigned __int16 *)v37);
    }
  }
  v46 = v133;
  MigrationData = SdbGetMigrationData(a2, (__int64)&v151);
  v48 = 0;
  v49 = MigrationData < 0;
  if ( MigrationData > 0 )
  {
    MigrationData = (unsigned __int16)MigrationData | 0x80070000;
    v49 = MigrationData < 0;
  }
  if ( v49 )
  {
    LODWORD(v123) = MigrationData;
    LODWORD(v120) = MigrationData;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      104,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      v120,
      (int)"Retrieving MigXml info failed: [0x%x].",
      v123);
    v136 = 0;
    v140 = 0;
  }
  else
  {
    v48 = v161;
    v140 = (unsigned __int16 *)v151;
  }
  lpMem = v48;
  v50 = Windows::Compat::Appraiser::SdbUtils::CheckForMigShim(
          (const unsigned __int16 **)&v159,
          (const unsigned __int16 **)&v160,
          &v149,
          &v141,
          v144,
          a2,
          v46);
  SdbEntryTargets = v50;
  if ( v50 < 0 )
  {
    LODWORD(v123) = v50;
    v122 = "Error getting migshim info: [0x%x].";
    v44 = 111;
    goto LABEL_76;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x46Fu,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Error getting migshim info: [0x%x].",
      v50);
  if ( v149 && !v48 )
  {
    v136 = 2;
    v140 = 0;
    v48 = v149;
    lpMem = v149;
  }
  SdbEntryTargets = Windows::Compat::Appraiser::Utilities::GetExeGuid(String2, a2, v46);
  if ( SdbEntryTargets < 0 )
  {
    v45 = "Failed to read exe GUID from os upgrade entry: [0x%x].";
    v44 = -123;
    goto LABEL_75;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x485u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Failed to read exe GUID from os upgrade entry: [0x%x].",
      SdbEntryTargets);
  AppGuid = Windows::Compat::Appraiser::Utilities::GetAppGuid(v172, a2, v46);
  SdbEntryTargets = AppGuid;
  if ( AppGuid < 0 )
  {
    LODWORD(v123) = AppGuid;
    v122 = "Failed to read app GUID from os upgrade entry: [0x%x].";
    v44 = -120;
    goto LABEL_76;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x488u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Failed to read app GUID from os upgrade entry: [0x%x].",
      AppGuid);
  SdbEntryTargets = Windows::Compat::Appraiser::Utilities::GetSdbStringForTag(v175, 0x104u, a2, v46, 0x6006u);
  if ( SdbEntryTargets == 1 )
  {
    SdbEntryTargets = -2147467259;
LABEL_110:
    LODWORD(v123) = SdbEntryTargets;
    v122 = "Failed to read app name from os upgrade entry: [0x%x].";
    v44 = -117;
    goto LABEL_76;
  }
  if ( SdbEntryTargets < 0 )
    goto LABEL_110;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x48Bu,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Failed to read app name from os upgrade entry: [0x%x].",
      SdbEntryTargets);
  SdbEntryTargets = Windows::Compat::Appraiser::Utilities::GetSdbStringForTag(v176, 0x104u, a2, v46, 0x6005u);
  if ( SdbEntryTargets == 1 )
  {
    SdbEntryTargets = -2147467259;
LABEL_116:
    LODWORD(v123) = SdbEntryTargets;
    v122 = "Failed to read app vendor from os upgrade entry: [0x%x].";
    v44 = -114;
    goto LABEL_76;
  }
  if ( SdbEntryTargets < 0 )
    goto LABEL_116;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x48Eu,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Failed to read app vendor from os upgrade entry: [0x%x].",
      SdbEntryTargets);
  v134[22] = v140 != 0;
  v134[26] = v48 != 0;
  v134[25] = v136 != 0;
  if ( !v146 || (v134[31] = 1, v129) )
    v134[31] = 0;
  if ( !v146 || (v134[32] = 1, !v129) )
    v134[32] = 0;
  v134[33] = v146 != 0;
  if ( !v157 || (v134[34] = 1, v130) )
    v134[34] = 0;
  if ( !v157 || (v134[35] = 1, !v130) )
    v134[35] = 0;
  v134[36] = v157 != 0;
  if ( !v138 || (v134[10] = 1, v131) )
    v134[10] = 0;
  if ( !v138 || (v134[11] = 1, !v131) )
    v134[11] = 0;
  v134[12] = v138 != 0;
  if ( !v128 || (v134[13] = 1, v132) )
    v134[13] = 0;
  if ( !v128 || (v134[14] = 1, !v132) )
    v134[14] = 0;
  v134[15] = v128 != 0;
  v52 = v159 != 0;
  v134[23] = v159 != 0;
  v134[24] = v160 != 0;
  if ( !(unsigned int)SdbGetUxBlockOverrideForEntry(a2, v46, &v152) )
  {
    SdbEntryTargets = -2147467259;
    LODWORD(v119) = -2147467259;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      169,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      v119,
      (int)"SdbGetUxBlockOverrideForEntry failed.",
      v123);
    goto LABEL_438;
  }
  AppraiserDataTagsInternal = Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTagsInternal(
                                (RtlStringArray *)v154,
                                (__int64)v147);
  SdbEntryTargets = AppraiserDataTagsInternal;
  if ( AppraiserDataTagsInternal < 0 )
  {
    LODWORD(v123) = AppraiserDataTagsInternal;
    v122 = "Failed to get appraiser data tags: [0x%x].";
    v44 = -76;
    goto LABEL_76;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4B4u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Failed to get appraiser data tags: [0x%x].",
      AppraiserDataTagsInternal);
  if ( a8 )
  {
    v54 = 0;
    v55 = 0;
    v56 = v155;
    if ( !(_QWORD)v155 )
      goto LABEL_176;
    v57 = (char *)v156[1];
    v58 = (unsigned __int64)v154[1];
    do
    {
      v59 = 0;
      if ( v55 < v56 )
      {
        v144 = 0;
        if ( !is_mul_ok(v58, v55) || (v59 = &v57[v58 * v55], v59 < v57) )
          v59 = 0;
      }
      v60 = *(_QWORD *)v59;
      v61 = -1;
      do
        ++v61;
      while ( *(_WORD *)(v60 + 2 * v61) );
      if ( !wcscmp_0(L"CustomMigXML", (const wchar_t *)(v60 + 2 * (v61 + 1))) )
      {
        v54 = 1;
      }
      else
      {
        RtlNameValueArray::Delete((RtlNameValueArray *)v154, v55);
        v57 = (char *)v156[1];
        v58 = (unsigned __int64)v154[1];
      }
      ++v55;
      v56 = v155;
    }
    while ( v55 < (unsigned __int64)v155 );
    if ( !v54 )
    {
LABEL_176:
      SdbEntryTargets = 1;
      if ( Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors() )
      {
        LODWORD(v119) = 1;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          203,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
          "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
          v119,
          (int)"Custom Sdb entry does not include Appraiser CustomMigXml tag",
          v123);
      }
      else
      {
        Windows::Compat::Appraiser::WriteLog(
          0,
          203,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
          "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
          0,
          (int)"Custom Sdb entry does not include Appraiser CustomMigXml tag",
          v123);
      }
      goto LABEL_438;
    }
    memset(v169, 0, sizeof(v169));
    v169[6] = v134[22];
    *(_WORD *)&v169[8] = *(_WORD *)&v134[24];
    v169[7] = v52;
    v169[10] = v134[26];
    *(_OWORD *)v134 = 0;
    *(_OWORD *)&v134[16] = *(_OWORD *)v169;
    *(_QWORD *)&v134[31] = 0;
    v46 = v133;
  }
  v142 = SdbFindFirstTagRef(a2, v46, 0x7031u);
  v63 = 0;
  v151 = 0;
  do
  {
    v64 = *(_DWORD *)v170[v63];
    v133 = v64;
    if ( v64 )
    {
      SdbEntryTargets = Windows::Compat::Appraiser::SdbUtils::GetHelpResourcesFromMitigation(
                          &v150,
                          &v143,
                          v174,
                          v62,
                          a2,
                          v64);
      if ( SdbEntryTargets < 0 )
      {
        LODWORD(v123) = SdbEntryTargets;
        v122 = "Failed to get additional help resources: [0x%x].";
        v44 = -23;
        goto LABEL_76;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x4E9u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
          "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
          "Failed to get additional help resources: [0x%x].",
          SdbEntryTargets);
      v65 = -1;
      do
        ++v65;
      while ( v174[v65] );
      v134[37] = v65 != 0;
      v66 = v150;
      v67 = v150 != 0;
      v134[9] = v150 != 0;
      v134[21] = v143 != 0;
      if ( v65 )
      {
        SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                            L"SdbStoreUrl",
                            v174,
                            (unsigned int *)&v127,
                            v145);
        if ( SdbEntryTargets < 0 )
        {
          v68 = L"SdbStoreUrl";
          v69 = -12;
LABEL_174:
          v126 = SdbEntryTargets;
          v125 = (const unsigned __int16 *)v68;
          goto LABEL_175;
        }
      }
      else
      {
        SdbEntryTargets = 0;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x4F4u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
          "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
          "Failed to append %ls: [0x%x].",
          (const wchar_t *)L"SdbStoreUrl",
          SdbEntryTargets);
      v70 = !v67;
      v71 = v145;
      if ( v70 )
      {
        SdbEntryTargets = 0;
      }
      else
      {
        appended = Windows::Compat::Appraiser::Utilities::CreateAndAppendDwordProperty(
                     L"SdbFwLink",
                     v66,
                     (unsigned int *)&v127,
                     v145);
        SdbEntryTargets = appended;
        if ( appended < 0 )
        {
          v126 = appended;
          v125 = L"SdbFwLink";
          v69 = -5;
LABEL_175:
          LODWORD(v119) = SdbEntryTargets;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            v69,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
            "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
            v119,
            (int)"Failed to append %ls: [0x%x].",
            (const char *)v125,
            v126,
            v127);
          goto LABEL_438;
        }
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x4FBu,
          "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
          "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
          "Failed to append %ls: [0x%x].",
          L"SdbFwLink",
          SdbEntryTargets);
      if ( v134[21] )
      {
        v73 = Windows::Compat::Appraiser::Utilities::CreateAndAppendDwordProperty(
                L"SdbKbArticle",
                v143,
                (unsigned int *)&v127,
                v71);
        SdbEntryTargets = v73;
        if ( v73 < 0 )
        {
          LODWORD(v119) = v73;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            2,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
            "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
            v119,
            (int)"Failed to append %ls: [0x%x].",
            (const char *)L"SdbKbArticle",
            v73,
            v127);
          goto LABEL_438;
        }
      }
      else
      {
        SdbEntryTargets = 0;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x502u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
          "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
          "Failed to append %ls: [0x%x].",
          L"SdbKbArticle",
          SdbEntryTargets);
      if ( !v134[38] )
        Windows::Compat::Appraiser::SdbUtils::GetHyperlinkInfo(
          &v134[38],
          &v148,
          v173,
          v62,
          a2,
          v133,
          (const unsigned __int16 *)v147);
    }
    v63 = v151 + 1;
    v151 = v63;
  }
  while ( v63 < 4 );
  v74 = v145;
  if ( v134[4] )
  {
    SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                        L"SdbBlockType",
                        L"BlockUpgradeCanReinstall",
                        (unsigned int *)&v127,
                        v145);
    if ( SdbEntryTargets < 0 )
    {
      v75 = L"BlockUpgradeCanReinstall";
      v69 = 24;
      goto LABEL_200;
    }
  }
  else
  {
    SdbEntryTargets = 0;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x518u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Failed to append %ls: [0x%x].",
      (const wchar_t *)L"BlockUpgradeCanReinstall",
      SdbEntryTargets);
  if ( v134[5] )
  {
    SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                        L"SdbBlockType",
                        L"BlockUpgradeUntilUpdate",
                        (unsigned int *)&v127,
                        v74);
    if ( SdbEntryTargets < 0 )
    {
      v75 = L"BlockUpgradeUntilUpdate";
      v69 = 31;
      goto LABEL_200;
    }
  }
  else
  {
    SdbEntryTargets = 0;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x51Fu,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Failed to append %ls: [0x%x].",
      L"BlockUpgradeUntilUpdate",
      SdbEntryTargets);
  if ( v134[3] )
  {
    SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                        L"SdbBlockType",
                        L"BlockUpgrade",
                        (unsigned int *)&v127,
                        v74);
    if ( SdbEntryTargets < 0 )
    {
      v75 = L"BlockUpgrade";
      v69 = 38;
      goto LABEL_200;
    }
  }
  else
  {
    SdbEntryTargets = 0;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x526u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Failed to append %ls: [0x%x].",
      L"BlockUpgrade",
      SdbEntryTargets);
  if ( v134[15] )
  {
    SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                        L"SdbGenericMessageSummaryStringPresent",
                        L"TRUE",
                        (unsigned int *)&v127,
                        v74);
    if ( SdbEntryTargets < 0 )
    {
      v75 = L"SdbGenericMessageSummaryStringPresent";
      v69 = 45;
      goto LABEL_200;
    }
  }
  else
  {
    SdbEntryTargets = 0;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x52Du,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Failed to append %ls: [0x%x].",
      L"SdbGenericMessageSummaryStringPresent",
      SdbEntryTargets);
  v28 = v128;
  if ( v134[13] )
  {
    SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                        L"SdbGenericMessageSummary",
                        v128,
                        (unsigned int *)&v127,
                        v74);
    if ( SdbEntryTargets < 0 )
    {
      v76 = L"SdbGenericMessageSummary";
      v77 = 52;
      goto LABEL_230;
    }
  }
  else
  {
    SdbEntryTargets = 0;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x534u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
      "Failed to append %ls: [0x%x].",
      (const wchar_t *)L"SdbGenericMessageSummary",
      SdbEntryTargets);
  if ( !v134[14] )
  {
    SdbEntryTargets = 0;
    goto LABEL_240;
  }
  SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                      L"SdbGenericMessageSummaryRedirectionInstruction",
                      v28,
                      (unsigned int *)&v127,
                      v74);
  if ( SdbEntryTargets >= 0 )
  {
LABEL_240:
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x53Bu,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"SdbGenericMessageSummaryRedirectionInstruction",
        SdbEntryTargets);
    if ( v134[12] )
    {
      v78 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
              L"SdbGenericMessageTitleStringPresent",
              L"TRUE",
              (unsigned int *)&v127,
              v74);
      SdbEntryTargets = v78;
      if ( v78 < 0 )
      {
        v126 = v78;
        v125 = L"SdbGenericMessageTitle";
        v69 = 66;
        goto LABEL_175;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x542u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"SdbGenericMessageTitle",
        SdbEntryTargets);
    if ( v134[10] )
    {
      v79 = v138;
      v80 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
              L"SdbGenericMessageTitle",
              v138,
              (unsigned int *)&v127,
              v74);
      SdbEntryTargets = v80;
      if ( v80 < 0 )
      {
        v126 = v80;
        v125 = L"SdbGenericMessageTitle";
        v69 = 73;
        goto LABEL_175;
      }
    }
    else
    {
      SdbEntryTargets = 0;
      v79 = v138;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x549u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"SdbGenericMessageTitle",
        SdbEntryTargets);
    if ( v134[11] )
    {
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                          L"SdbGenericMessageTitleRedirectionInstruction",
                          v79,
                          (unsigned int *)&v127,
                          v74);
      v81 = 0;
      if ( SdbEntryTargets < 0 )
      {
        v75 = L"SdbGenericMessageTitleRedirectionInstruction";
        v69 = 80;
        goto LABEL_200;
      }
    }
    else
    {
      v81 = 0;
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x550u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"SdbGenericMessageTitleRedirectionInstruction",
        SdbEntryTargets);
    if ( v134[29] )
    {
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                          L"SdbBlockType",
                          L"ReinstallAfterUpgradeInfo",
                          (unsigned int *)&v127,
                          v74);
      if ( SdbEntryTargets < 0 )
      {
        v75 = L"ReinstallAfterUpgradeInfo";
        v69 = 87;
        goto LABEL_200;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x557u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"ReinstallAfterUpgradeInfo",
        SdbEntryTargets);
    if ( v134[30] )
    {
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                          L"SdbBlockType",
                          L"ReinstallAfterUpgradeWarn",
                          (unsigned int *)&v127,
                          v74);
      if ( SdbEntryTargets < 0 )
      {
        v75 = L"ReinstallAfterUpgradeWarn";
        v69 = 94;
        goto LABEL_200;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x55Eu,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"ReinstallAfterUpgradeWarn",
        SdbEntryTargets);
    if ( v134[28] )
    {
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                          L"SdbBlockType",
                          L"ReinstallAfterUpgrade",
                          (unsigned int *)&v127,
                          v74);
      if ( SdbEntryTargets < 0 )
      {
        v75 = L"ReinstallAfterUpgrade";
        v69 = 101;
        goto LABEL_200;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x565u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"ReinstallAfterUpgrade",
        SdbEntryTargets);
    if ( v134[22] )
    {
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                          L"MigXmlName",
                          v140,
                          (unsigned int *)&v127,
                          v74);
      if ( SdbEntryTargets < 0 )
      {
        v75 = L"MigXmlName";
        v69 = 108;
        goto LABEL_200;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x56Cu,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"MigXmlName",
        SdbEntryTargets);
    if ( v134[26] )
    {
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                          L"MigXmlValue",
                          (const unsigned __int16 *)lpMem,
                          (unsigned int *)&v127,
                          v74);
      if ( SdbEntryTargets < 0 )
      {
        v75 = L"MigXmlValue";
        v69 = 115;
        goto LABEL_200;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x573u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"MigXmlValue",
        SdbEntryTargets);
    if ( v134[25] )
    {
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                          L"MigXmlType",
                          (const unsigned __int16 *)(&Windows::Compat::Appraiser::Utilities::MigXmlTypeStrings)[v136],
                          (unsigned int *)&v127,
                          v74);
      if ( SdbEntryTargets < 0 )
      {
        v75 = L"MigXmlType";
        v69 = 122;
        goto LABEL_200;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x57Au,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"MigXmlType",
        SdbEntryTargets);
    v82 = v146;
    if ( v134[31] )
    {
      v83 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
              L"ReinstallUpgradeMessage",
              v146,
              (unsigned int *)&v127,
              v74);
      SdbEntryTargets = v83;
      if ( v83 < 0 )
      {
        v126 = v83;
        v125 = L"ReinstallUpgradeMessage";
        v69 = -127;
        goto LABEL_175;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x581u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"ReinstallUpgradeMessage",
        SdbEntryTargets);
    if ( v134[32] )
    {
      v84 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
              L"ReinstallUpgradeMessageRedirectionInstruction",
              v82,
              (unsigned int *)&v127,
              v74);
      SdbEntryTargets = v84;
      if ( v84 < 0 )
      {
        v126 = v84;
        v125 = L"ReinstallUpgradeMessageRedirectionInstruction";
        v69 = -120;
        goto LABEL_175;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x588u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"ReinstallUpgradeMessageRedirectionInstruction",
        SdbEntryTargets);
    if ( v134[33] )
    {
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                          L"ReinstallUpgradeMessageStringPresent",
                          L"TRUE",
                          (unsigned int *)&v127,
                          v74);
      if ( SdbEntryTargets < 0 )
      {
        v75 = L"ReinstallUpgradeMessageStringPresent";
        v69 = -113;
        goto LABEL_200;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x58Fu,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"ReinstallUpgradeMessageStringPresent",
        SdbEntryTargets);
    v85 = v157;
    if ( v134[34] )
    {
      v86 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
              L"ReinstallUpgradeTitle",
              v157,
              (unsigned int *)&v127,
              v74);
      SdbEntryTargets = v86;
      if ( v86 < 0 )
      {
        v126 = v86;
        v125 = L"ReinstallUpgradeTitle";
        v69 = -106;
        goto LABEL_175;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x596u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"ReinstallUpgradeTitle",
        SdbEntryTargets);
    if ( v134[35] )
    {
      v87 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
              L"ReinstallUpgradeTitleRedirectionInstruction",
              v85,
              (unsigned int *)&v127,
              v74);
      SdbEntryTargets = v87;
      if ( v87 < 0 )
      {
        v126 = v87;
        v125 = L"ReinstallUpgradeTitleRedirectionInstruction";
        v69 = -99;
        goto LABEL_175;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x59Du,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"ReinstallUpgradeTitleRedirectionInstruction",
        SdbEntryTargets);
    if ( v134[36] )
    {
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                          L"ReinstallUpgradeTitleStringPresent",
                          L"TRUE",
                          (unsigned int *)&v127,
                          v74);
      if ( SdbEntryTargets < 0 )
      {
        v75 = L"ReinstallUpgradeTitleStringPresent";
        v69 = -92;
        goto LABEL_200;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x5A4u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"ReinstallUpgradeTitleStringPresent",
        SdbEntryTargets);
    if ( v134[23] )
    {
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                          L"MigShimName",
                          v159,
                          (unsigned int *)&v127,
                          v74);
      if ( SdbEntryTargets < 0 )
      {
        v75 = L"MigShimName";
        v69 = -85;
        goto LABEL_200;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x5ABu,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"MigShimName",
        SdbEntryTargets);
    if ( v134[24] )
    {
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                          L"MigShimCommand",
                          v160,
                          (unsigned int *)&v127,
                          v74);
      if ( SdbEntryTargets < 0 )
      {
        v75 = L"MigShimCommand";
        v69 = -78;
        goto LABEL_200;
      }
    }
    else
    {
      SdbEntryTargets = 0;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x5B2u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
        "Failed to append %ls: [0x%x].",
        L"MigShimCommand",
        SdbEntryTargets);
    SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                        L"SdbBlockOverrideType",
                        (const unsigned __int16 *)(&Windows::Compat::Appraiser::Utilities::BlockOverrideTypeStrings)[v152],
                        (unsigned int *)&v127,
                        v74);
    if ( SdbEntryTargets >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x5B8u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
          "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
          "Failed to append %ls: [0x%x].",
          L"SdbBlockOverrideType",
          SdbEntryTargets);
      v88 = v155;
      if ( (_QWORD)v155 )
      {
        while ( 1 )
        {
          v89 = 0;
          if ( v81 < v88 )
          {
            v144 = 0;
            if ( !is_mul_ok((unsigned __int64)v154[1], v81)
              || (v89 = (__int64 *)((char *)v156[1] + (unsigned __int64)v154[1] * v81), v89 < v156[1]) )
            {
              v89 = 0;
            }
            v88 = v155;
          }
          v90 = *v89;
          v91 = -1;
          do
            ++v91;
          while ( *(_WORD *)(v90 + 2 * v91) );
          v92 = v90 + 2 * v91;
          v93 = 0;
          if ( v81 < v88 )
          {
            v144 = 0;
            v94 = (unsigned __int64)v154[1] * v81;
            if ( !is_mul_ok((unsigned __int64)v154[1], v81)
              || (v93 = (const unsigned __int16 **)((char *)v156[1] + v94), (char *)v156[1] + v94 < v156[1]) )
            {
              v93 = 0;
            }
          }
          SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                              *v93,
                              (const unsigned __int16 *)(v92 + 2),
                              (unsigned int *)&v127,
                              v74);
          if ( SdbEntryTargets < 0 )
            break;
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          {
            v95 = 0;
            if ( v81 < (unsigned __int64)v155 )
            {
              v144 = 0;
              if ( !is_mul_ok((unsigned __int64)v154[1], v81)
                || (v95 = (const wchar_t **)((char *)v156[1] + (unsigned __int64)v154[1] * v81), v95 < v156[1]) )
              {
                v95 = 0;
              }
            }
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x5C0u,
              "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
              "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
              "Failed to append %ls: [0x%x].",
              *v95,
              SdbEntryTargets);
          }
          ++v81;
          v88 = v155;
          if ( v81 >= (unsigned __int64)v155 )
            goto LABEL_383;
        }
        v97 = 0;
        if ( v81 < (unsigned __int64)v155 )
        {
          if ( !is_mul_ok((unsigned __int64)v154[1], v81)
            || (v97 = (const unsigned __int16 **)((char *)v156[1] + (unsigned __int64)v154[1] * v81), v97 < v156[1]) )
          {
            v97 = 0;
          }
        }
        v126 = SdbEntryTargets;
        v125 = *v97;
        v69 = -64;
        goto LABEL_175;
      }
LABEL_383:
      v96 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
              L"SdbAppGuid",
              v172,
              (unsigned int *)&v127,
              v74);
      SdbEntryTargets = v96;
      if ( v96 < 0 )
      {
        v126 = v96;
        v125 = L"SdbAppGuid";
        v69 = -53;
        goto LABEL_175;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x5CBu,
          "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
          "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
          "Failed to append %ls: [0x%x].",
          L"SdbAppGuid",
          v96);
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                          L"SdbEntryGuid",
                          String2,
                          (unsigned int *)&v127,
                          v74);
      if ( SdbEntryTargets >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x5D1u,
            "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
            "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
            "Failed to append %ls: [0x%x].",
            L"SdbEntryGuid",
            SdbEntryTargets);
        SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                            L"SdbAppName",
                            v175,
                            (unsigned int *)&v127,
                            v74);
        if ( SdbEntryTargets >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x5D7u,
              "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
              "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
              "Failed to append %ls: [0x%x].",
              L"SdbAppName",
              SdbEntryTargets);
          SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                              L"SdbAppVendor",
                              v176,
                              (unsigned int *)&v127,
                              v74);
          if ( SdbEntryTargets >= 0 )
          {
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x5DDu,
                "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
                "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
                "Failed to append %ls: [0x%x].",
                L"SdbAppVendor",
                SdbEntryTargets);
            v98 = 0;
            v99 = (unsigned __int64 *)v158;
            v100 = (unsigned __int64 *)(v158 + 16);
            while ( 1 )
            {
              if ( (_BYTE)v153 )
              {
                v100 = v99 + 2;
                v101 = v99[2];
              }
              else
              {
                v101 = v164;
              }
              if ( v98 >= v101 )
                break;
              v102 = 0;
              if ( (_BYTE)v153 )
              {
                if ( v98 < *v100 )
                {
                  v144 = 0;
                  v103 = v99[1] * v98;
                  if ( !is_mul_ok(v99[1], v98)
                    || (v104 = v99[5], v102 = (const unsigned __int16 **)(v104 + v103), v104 + v103 < v104) )
                  {
                    v102 = 0;
                  }
                }
              }
              else
              {
                if ( v98 < (unsigned __int64)v164 )
                {
                  v144 = 0;
                  v105 = (unsigned __int64)hHeap[1] * v98;
                  if ( !is_mul_ok((unsigned __int64)hHeap[1], v98)
                    || (v102 = (const unsigned __int16 **)((char *)v165[1] + v105), (char *)v165[1] + v105 < v165[1]) )
                  {
                    v102 = 0;
                  }
                }
                v100 = v99 + 2;
              }
              SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                                  L"ApplicableTargetVersion",
                                  *v102,
                                  (unsigned int *)&v127,
                                  v74);
              if ( SdbEntryTargets < 0 )
              {
                v68 = (const char *)L"ApplicableTargetVersion";
                v69 = -27;
                goto LABEL_174;
              }
              if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                  0x5E5u,
                  "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
                  "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
                  "Failed to append %ls: [0x%x].",
                  L"ApplicableTargetVersion",
                  SdbEntryTargets);
              ++v98;
              v99 = (unsigned __int64 *)v158;
            }
            if ( v134[38] )
            {
              v106 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                       L"SdbHyperlinkTarget",
                       v173,
                       (unsigned int *)&v127,
                       v74);
              SdbEntryTargets = v106;
              if ( v106 < 0 )
              {
                v126 = v106;
                v125 = L"SdbHyperlinkTarget";
                v69 = -19;
                goto LABEL_175;
              }
            }
            else
            {
              SdbEntryTargets = 0;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x5EDu,
                "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
                "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
                "Failed to append %ls: [0x%x].",
                (const wchar_t *)L"SdbHyperlinkTarget",
                SdbEntryTargets);
            if ( v134[38] )
            {
              SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                                  L"SdbHyperlinkText",
                                  v148,
                                  (unsigned int *)&v127,
                                  v74);
              if ( SdbEntryTargets < 0 )
              {
                v75 = L"SdbHyperlinkText";
                v69 = -12;
                goto LABEL_200;
              }
            }
            else
            {
              SdbEntryTargets = 0;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x5F4u,
                "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
                "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
                "Failed to append %ls: [0x%x].",
                (const wchar_t *)L"SdbHyperlinkText",
                SdbEntryTargets);
            Windows::Compat::Appraiser::SdbUtils::UpdateSdbTelemetryData(
              v162,
              (const struct Windows::Compat::Appraiser::SdbDataSourcePropertyBoolean *)v134);
            SdbEntryTargets = 0;
            goto LABEL_438;
          }
          v75 = L"SdbAppVendor";
          v69 = -35;
        }
        else
        {
          v75 = L"SdbAppName";
          v69 = -41;
        }
      }
      else
      {
        v75 = L"SdbEntryGuid";
        v69 = -47;
      }
    }
    else
    {
      v75 = L"SdbBlockOverrideType";
      v69 = -72;
    }
LABEL_200:
    v126 = SdbEntryTargets;
    v125 = v75;
    goto LABEL_175;
  }
  v76 = (const char *)L"SdbGenericMessageSummaryRedirectionInstruction";
  v77 = 59;
LABEL_230:
  LODWORD(v119) = SdbEntryTargets;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v77,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
    "Windows::Compat::Appraiser::SdbUtils::CheckAppQueryResult",
    v119,
    (int)"Failed to append %ls: [0x%x].",
    v76,
    SdbEntryTargets,
    v127);
LABEL_439:
  v107 = v148;
  if ( v148 )
  {
    v108 = GetProcessHeap();
    HeapFree(v108, 0, v107);
  }
  v109 = v146;
  if ( v146 )
  {
    v110 = GetProcessHeap();
    HeapFree(v110, 0, v109);
  }
LABEL_443:
  v30 = v138;
LABEL_444:
  if ( v28 )
  {
    v111 = GetProcessHeap();
    HeapFree(v111, 0, v28);
  }
  if ( v30 )
  {
    v112 = GetProcessHeap();
    HeapFree(v112, 0, v30);
  }
LABEL_448:
  v113 = v149;
  if ( v149 )
  {
    v114 = GetProcessHeap();
    HeapFree(v114, 0, v113);
    v149 = 0;
  }
  if ( v165[1] )
    HeapFree(hHeap[0], 0, v165[1]);
  if ( v168[1] )
    HeapFree(v166[0], 0, v168[1]);
  RtlStringArray::Clear((RtlStringArray *)v154);
  if ( v156[1] )
    HeapFree(v154[0], 0, v156[1]);
  return (unsigned int)SdbEntryTargets;
}

```

## disassembly

```asm
0x1801f6934  push    rbp
0x1801f6936  push    rbx
0x1801f6937  push    rsi
0x1801f6938  push    rdi
0x1801f6939  push    r12
0x1801f693b  push    r13
0x1801f693d  push    r14
0x1801f693f  push    r15
0x1801f6941  lea     rbp, [rsp-0A08h]
0x1801f6949  sub     rsp, 0B08h
0x1801f6950  mov     [rbp+0A40h+var_938], 0FFFFFFFFFFFFFFFEh
0x1801f695b  mov     rax, cs:__security_cookie
0x1801f6962  xor     rax, rsp
0x1801f6965  mov     [rbp+0A40h+var_50], rax
0x1801f696c  mov     [rbp+0A40h+var_A08], r9
0x1801f6970  mov     r13, r8
0x1801f6973  mov     r12, rdx
0x1801f6976  mov     dword ptr [rsp+0B40h+var_AEC], ecx
0x1801f697a  mov     rax, [rbp+0A40h+arg_20]
0x1801f6981  mov     [rbp+0A40h+var_A80], rax
0x1801f6985  mov     rax, [rbp+0A40h+arg_28]
0x1801f698c  mov     [rbp+0A40h+var_A70], rax
0x1801f6990  mov     rax, [rbp+0A40h+arg_30]
0x1801f6997  mov     [rbp+0A40h+var_A88], rax
0x1801f699b  mov     rax, [rbp+0A40h+arg_40]
0x1801f69a2  mov     [rbp+0A40h+var_9E8], rax
0x1801f69a6  mov     r15, [rbp+0A40h+arg_48]
0x1801f69ad  xor     esi, esi
0x1801f69af  mov     [rbp+0A40h+var_AB8], esi
0x1801f69b2  mov     [rbp+0A40h+var_AC0], esi
0x1801f69b5  mov     [rbp+0A40h+var_A98], esi
0x1801f69b8  mov     [rbp+0A40h+var_A94], esi
0x1801f69bb  mov     [rbp+0A40h+var_A58], esi
0x1801f69be  mov     [rbp+0A40h+var_A90], esi
0x1801f69c1  mov     [rbp+0A40h+var_A60], rsi
0x1801f69c5  mov     [rbp+0A40h+var_A00], rsi
0x1801f69c9  mov     [rbp+0A40h+var_9F8], rsi
0x1801f69cd  mov     [rbp+0A40h+var_A48], esi
0x1801f69d0  call    cs:__imp_GetProcessHeap
0x1801f69d6  xorps   xmm0, xmm0
0x1801f69d9  movups  xmmword ptr [rbp+0A40h+var_A40], xmm0
0x1801f69dd  movups  xmmword ptr [rbp+0A40h+var_A20], xmm0
0x1801f69e1  call    cs:__imp_GetProcessHeap
0x1801f69e7  mov     [rbp+0A40h+var_A40], rax
0x1801f69eb  lea     edi, [rsi+10h]
0x1801f69ee  mov     [rbp+0A40h+var_A20], rdi
0x1801f69f2  xorps   xmm0, xmm0
0x1801f69f5  movdqu  [rbp+0A40h+var_A30], xmm0
0x1801f69fa  mov     [rbp+0A40h+var_A20+8], rsi
0x1801f69fe  lea     ebx, [rsi+8]
0x1801f6a01  mov     [rbp+0A40h+var_A40+8], rbx
0x1801f6a05  movups  xmmword ptr [rbp+0A40h+var_9B0], xmm0
0x1801f6a0c  movups  xmmword ptr [rbp+0A40h+var_990], xmm0
0x1801f6a13  call    cs:__imp_GetProcessHeap
0x1801f6a19  mov     [rbp+0A40h+var_9B0], rax
0x1801f6a20  mov     [rbp+0A40h+var_990], rdi
0x1801f6a27  xorps   xmm0, xmm0
0x1801f6a2a  movdqu  [rbp+0A40h+var_9A0], xmm0
0x1801f6a32  mov     [rbp+0A40h+var_990+8], rsi
0x1801f6a39  mov     [rbp+0A40h+var_9B0+8], rbx
0x1801f6a40  movups  xmmword ptr [rbp+0A40h+hHeap], xmm0
0x1801f6a44  movups  xmmword ptr [rbp+0A40h+var_9C0], xmm0
0x1801f6a4b  call    cs:__imp_GetProcessHeap
0x1801f6a51  mov     [rbp+0A40h+hHeap], rax
0x1801f6a55  mov     [rbp+0A40h+var_9C0], rdi
0x1801f6a5c  xorps   xmm0, xmm0
0x1801f6a5f  movdqu  [rbp+0A40h+var_9D0], xmm0
0x1801f6a64  mov     [rbp+0A40h+var_9C0+8], rsi
0x1801f6a6b  mov     [rbp+0A40h+hHeap+8], rbx
0x1801f6a6f  lea     rax, [rbp+0A40h+var_AB8]
0x1801f6a73  mov     [rbp+0A40h+var_958], rax
0x1801f6a7a  lea     rax, [rbp+0A40h+var_AC0]
0x1801f6a7e  mov     [rbp+0A40h+var_950], rax
0x1801f6a85  lea     rax, [rbp+0A40h+var_A98]
0x1801f6a89  mov     [rbp+0A40h+var_948], rax
0x1801f6a90  lea     rax, [rbp+0A40h+var_A94]
0x1801f6a94  mov     [rbp+0A40h+var_940], rax
0x1801f6a9b  lea     ebx, [rsi+50h]
0x1801f6a9e  mov     r8d, ebx; Size
0x1801f6aa1  xor     edx, edx; Val
0x1801f6aa3  lea     rcx, [rbp+0A40h+String2]; void *
0x1801f6aaa  call    memset_0
0x1801f6aaf  mov     r8d, ebx; Size
0x1801f6ab2  xor     edx, edx; Val
0x1801f6ab4  lea     rcx, [rbp+0A40h+var_8E0]; void *
0x1801f6abb  call    memset_0
0x1801f6ac0  xorps   xmm0, xmm0
0x1801f6ac3  xor     eax, eax
0x1801f6ac5  movups  xmmword ptr [rsp+0B40h+var_AEC+4], xmm0
0x1801f6aca  movups  [rsp+0B40h+var_AD8], xmm0
0x1801f6acf  mov     qword ptr [rsp+0B40h+var_AD8+0Fh], rax
0x1801f6ad4  mov     [rbp+0A40h+var_A68], rsi
0x1801f6ad8  mov     [rbp+0A40h+var_A60], rsi
0x1801f6adc  mov     [rbp+0A40h+var_A50], rsi
0x1801f6ae0  mov     [rbp+0A40h+var_9F0], rsi
0x1801f6ae4  mov     [rbp+0A40h+var_A10], rsi
0x1801f6ae8  mov     [rbp+0A40h+var_A78], rsi
0x1801f6aec  mov     eax, esi
0x1801f6aee  mov     [rbp+0A40h+var_AB0], rax
0x1801f6af2  mov     [rbp+0A40h+var_AA0], rax
0x1801f6af6  mov     [rsp+0B40h+var_AF8], rax
0x1801f6afb  mov     [rbp+0A40h+lpMem], rax
0x1801f6aff  mov     [rsp+0B40h+var_AEF], sil
0x1801f6b04  mov     [rsp+0B40h+var_AF0], sil
0x1801f6b09  mov     [rsp+0B40h+var_AED], sil
0x1801f6b0e  mov     [rsp+0B40h+var_AEE], sil
0x1801f6b13  mov     [rbp+0A40h+var_ABC], esi
0x1801f6b16  mov     [rbp+0A40h+var_A94], esi
0x1801f6b19  mov     [rbp+0A40h+var_A98], esi
0x1801f6b1c  mov     [rbp+0A40h+var_AC0], esi
0x1801f6b1f  mov     [rbp+0A40h+var_AB8], esi
0x1801f6b22  mov     [rbp+0A40h+var_260], si
0x1801f6b29  mov     [rbp+0A40h+var_470], si
0x1801f6b30  lea     rcx, [rbp+0A40h+var_9B0]
0x1801f6b37  call    ?Initialize@?$RtlArray@PEAVIProperty@Appraiser@Compat@Windows@@@@QEAAJ_K@Z; RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(unsigned __int64)
0x1801f6b3c  mov     ebx, eax
0x1801f6b3e  test    eax, eax
0x1801f6b40  jns     short loc_1801F6B79
0x1801f6b42  mov     dword ptr [rsp+0B40h+var_B10], eax; char *
0x1801f6b46  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1801f6b4d  mov     [rsp+0B40h+var_B18], r9; int
0x1801f6b52  lea     r9, aWindowsCompatA_459; "Windows::Compat::Appraiser::SdbUtils::C"...
0x1801f6b59  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801f6b60  mov     edx, 3A1h; bool
0x1801f6b65  lea     ecx, [rsi+1]; this
0x1801f6b68  mov     dword ptr [rsp+0B40h+var_B20], ebx; char *
0x1801f6b6c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801f6b71  xor     r12d, r12d
0x1801f6b74  jmp     loc_1801F8AB9
0x1801f6b79  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801f6b7f  mov     edi, 1
0x1801f6b84  and     eax, edi
0x1801f6b86  lea     rsi, aWindowsCompatA_459; "Windows::Compat::Appraiser::SdbUtils::C"...
0x1801f6b8d  lea     r14, aOnecoreBaseApp_63; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801f6b94  test    al, al
0x1801f6b96  jz      short loc_1801F6BB3
0x1801f6b98  mov     dword ptr [rsp+0B40h+var_B20], ebx
0x1801f6b9c  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1801f6ba3  mov     r8, rsi; char *
0x1801f6ba6  mov     rdx, r14; char *
0x1801f6ba9  mov     ecx, 3A1h; unsigned int
0x1801f6bae  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801f6bb3  mov     r9d, dword ptr [rsp+0B40h+var_AEC]
0x1801f6bb8  mov     r8, r12
0x1801f6bbb  mov     rdx, r13
0x1801f6bbe  lea     rcx, [rbp+0A40h+var_9B0]
0x1801f6bc5  call    ?GetSdbEntryTargets@Utilities@Appraiser@Compat@Windows@@SAJAEAV?$RtlArray@PEBG@@AEAVRtlStringArray@@PEAXK@Z; Windows::Compat::Appraiser::Utilities::GetSdbEntryTargets(RtlArray<ushort const *> &,RtlStringArray &,void *,ulong)
0x1801f6bca  mov     ebx, eax
0x1801f6bcc  xor     ecx, ecx
0x1801f6bce  test    eax, eax
0x1801f6bd0  jns     short loc_1801F6BF4
0x1801f6bd2  lea     r9, aFailedToGetEnt; "Failed to get entry targets: [0x%x]."
0x1801f6bd9  mov     edx, 3A4h
0x1801f6bde  mov     dword ptr [rsp+0B40h+var_B10], ebx
0x1801f6be2  mov     [rsp+0B40h+var_B18], r9
0x1801f6be7  mov     r9, rsi
0x1801f6bea  mov     r8, r14
0x1801f6bed  mov     ecx, edi
0x1801f6bef  jmp     loc_1801F6B68
0x1801f6bf4  mov     r13b, cl
0x1801f6bf7  mov     [rbp+0A40h+var_A44], r13d
0x1801f6bfb  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801f6c01  and     eax, edi
0x1801f6c03  test    al, al
0x1801f6c05  jz      short loc_1801F6C22
0x1801f6c07  mov     dword ptr [rsp+0B40h+var_B20], ebx
0x1801f6c0b  lea     r9, aFailedToGetEnt; "Failed to get entry targets: [0x%x]."
0x1801f6c12  mov     r8, rsi; char *
0x1801f6c15  mov     rdx, r14; char *
0x1801f6c18  mov     ecx, 3A4h; unsigned int
0x1801f6c1d  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801f6c22  xor     r9d, r9d; Context
0x1801f6c25  xor     r8d, r8d; Parameter
0x1801f6c28  lea     rdx, ?InitOnceCallback@AppraiserTestHooks@Appraiser@Compat@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1801f6c2f  lea     rcx, ?InitOnce@AppraiserTestHooks@Appraiser@Compat@Windows@@0T_RTL_RUN_ONCE@@A; InitOnce
0x1801f6c36  call    cs:__imp_InitOnceExecuteOnce
0x1801f6c3c  xor     ecx, ecx
0x1801f6c3e  cmp     cs:?TestHookForceGatedBlock@AppraiserTestHooks@Appraiser@Compat@Windows@@0_NA, cl; bool Windows::Compat::Appraiser::AppraiserTestHooks::TestHookForceGatedBlock
0x1801f6c44  jz      short loc_1801F6CB9
0x1801f6c46  mov     r8d, dword ptr [rsp+0B40h+var_AEC]; unsigned int
0x1801f6c4b  mov     rdx, r12; void *
0x1801f6c4e  lea     rcx, [rbp+0A40h+String2]; unsigned __int16 *
0x1801f6c55  call    ?GetExeGuid@Utilities@Appraiser@Compat@Windows@@SAJPEAGPEAXK@Z; Windows::Compat::Appraiser::Utilities::GetExeGuid(ushort *,void *,ulong)
0x1801f6c5a  mov     ebx, eax
0x1801f6c5c  test    eax, eax
0x1801f6c5e  jns     short loc_1801F6C71
0x1801f6c60  lea     r9, aFailedToReadEx; "Failed to read exe GUID from os upgrade"...
0x1801f6c67  mov     edx, 3AEh
0x1801f6c6c  jmp     loc_1801F6BDE
0x1801f6c71  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801f6c77  and     eax, edi
0x1801f6c79  test    al, al
0x1801f6c7b  jz      short loc_1801F6C98
0x1801f6c7d  mov     dword ptr [rsp+0B40h+var_B20], ebx
0x1801f6c81  lea     r9, aFailedToReadEx; "Failed to read exe GUID from os upgrade"...
0x1801f6c88  mov     r8, rsi; char *
0x1801f6c8b  mov     rdx, r14; char *
0x1801f6c8e  mov     ecx, 3AEh; unsigned int
0x1801f6c93  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801f6c98  lea     rdx, [rbp+0A40h+String2]; String2
0x1801f6c9f  lea     rcx, a9d9219f4Eccd48; "{9d9219f4-eccd-4802-92ec-d2acb87281f7}"
0x1801f6ca6  call    wcscmp_0
0x1801f6cab  movzx   r13d, r13b
0x1801f6caf  test    eax, eax
0x1801f6cb1  cmovz   r13d, edi
0x1801f6cb5  mov     [rbp+0A40h+var_A44], r13d
0x1801f6cb9  lea     rdx, [rbp+0A40h+var_9B0]
0x1801f6cc0  test    r13b, r13b
0x1801f6cc3  cmovnz  rdx, [rbp+0A40h+var_A08]
0x1801f6cc8  mov     r8, [rbp+0A40h+var_A08]
0x1801f6ccc  lea     rcx, [rbp+0A40h+hHeap]
0x1801f6cd0  call    ?GetTargetListIntersection@Utilities@Appraiser@Compat@Windows@@SAJAEAV?$RtlArray@PEBG@@00@Z; Windows::Compat::Appraiser::Utilities::GetTargetListIntersection(RtlArray<ushort const *> &,RtlArray<ushort const *> &,RtlArray<ushort const *> &)
0x1801f6cd5  mov     ebx, eax
0x1801f6cd7  xor     r13d, r13d
0x1801f6cda  test    eax, eax
0x1801f6cdc  jns     short loc_1801F6CEF
0x1801f6cde  lea     r9, aFailedToGetApp_1; "Failed to get applicable targets: [0x%x"...
0x1801f6ce5  mov     edx, 3B7h
0x1801f6cea  jmp     loc_1801F6BDE
0x1801f6cef  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801f6cf5  and     eax, edi
0x1801f6cf7  test    al, al
0x1801f6cf9  jz      short loc_1801F6D16
0x1801f6cfb  mov     dword ptr [rsp+0B40h+var_B20], ebx
0x1801f6cff  lea     r9, aFailedToGetApp_1; "Failed to get applicable targets: [0x%x"...
0x1801f6d06  mov     r8, rsi; char *
0x1801f6d09  mov     rdx, r14; char *
0x1801f6d0c  mov     ecx, 3B7h; unsigned int
0x1801f6d11  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801f6d16  cmp     qword ptr [rbp+0A40h+var_9D0], r13
0x1801f6d1a  jnz     short loc_1801F6D23
0x1801f6d1c  mov     ebx, edi
0x1801f6d1e  jmp     loc_1801F6B71
0x1801f6d23  test    r15, r15
0x1801f6d26  jnz     short loc_1801F6D31
0x1801f6d28  mov     rcx, [rbp+0A40h+var_A80]
0x1801f6d2c  mov     rax, [rcx]
0x1801f6d2f  jmp     short loc_1801F6D37
0x1801f6d31  mov     rax, [r15]
0x1801f6d34  mov     rcx, r15
0x1801f6d37  mov     rax, [rax+8]
0x1801f6d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f6d40  mov     dword ptr [rsp+0B40h+var_B00], eax
0x1801f6d44  mov     r8d, 7029h; unsigned __int16
0x1801f6d4a  mov     ebx, dword ptr [rsp+0B40h+var_AEC]
0x1801f6d4e  mov     edx, ebx; unsigned int
0x1801f6d50  mov     rcx, r12; void *
0x1801f6d53  call    SdbFindFirstTagRef
0x1801f6d58  mov     [rbp+0A40h+var_AB8], eax
0x1801f6d5b  xor     edx, edx
0x1801f6d5d  test    eax, eax
0x1801f6d5f  jz      loc_1801F6FE8
0x1801f6d65  mov     r8d, 4047h; unsigned __int16
0x1801f6d6b  mov     edx, eax; unsigned int
0x1801f6d6d  mov     rcx, r12; void *
0x1801f6d70  call    SdbFindFirstTagRef
0x1801f6d75  mov     r13b, dil
0x1801f6d78  mov     [rsp+0B40h+var_AEC+7], dil
0x1801f6d7d  xor     edx, edx
0x1801f6d7f  test    eax, eax
0x1801f6d81  jz      loc_1801F6FF2
0x1801f6d87  xor     r8d, r8d
0x1801f6d8a  mov     edx, eax
0x1801f6d8c  mov     rcx, r12
0x1801f6d8f  call    SdbReadDWORDTagRef
0x1801f6d94  xor     edx, edx
0x1801f6d96  cmp     eax, edi
0x1801f6d98  jnz     loc_1801F6E25
0x1801f6d9e  mov     cl, dil
0x1801f6da1  mov     [rsp+0B40h+var_AEC+8], cl
0x1801f6da5  mov     [rsp+0B40h+var_AEC+9], dl
0x1801f6da9  test    cl, cl
0x1801f6dab  jz      short loc_1801F6DB4
0x1801f6dad  mov     r13b, dl
0x1801f6db0  mov     [rsp+0B40h+var_AEC+7], dl
0x1801f6db4  cmp     eax, 3
0x1801f6db7  jnz     loc_1801F6FED
0x1801f6dbd  mov     r9d, 402Ch; unsigned __int16
0x1801f6dc3  lea     r8d, [r9-6]; unsigned __int16
0x1801f6dc7  mov     rbx, [rbp+0A40h+var_A70]
0x1801f6dcb  mov     [rsp+0B40h+var_B10], rbx; unsigned __int16 *
0x1801f6dd0  mov     [rsp+0B40h+var_B18], r12; void *
0x1801f6dd5  mov     eax, [rbp+0A40h+var_AB8]
0x1801f6dd8  mov     dword ptr [rsp+0B40h+var_B20], eax; unsigned int
0x1801f6ddc  lea     rdx, [rsp+0B40h+var_AED]; bool *
0x1801f6de1  lea     rcx, [rbp+0A40h+lpMem]; unsigned __int16 **
0x1801f6de5  call    ?InflateSdbResourceStringAlloc@SdbUtils@Appraiser@Compat@Windows@@SAJAEAPEAGAEA_NGGKPEAXPEBG@Z; Windows::Compat::Appraiser::SdbUtils::InflateSdbResourceStringAlloc(ushort * &,bool &,ushort,ushort,ulong,void *,ushort const *)
0x1801f6dea  mov     r15d, eax
0x1801f6ded  test    eax, eax
0x1801f6def  jns     short loc_1801F6E3E
0x1801f6df1  mov     ebx, eax
0x1801f6df3  mov     dword ptr [rsp+0B40h+var_B10], eax; char *
0x1801f6df7  lea     r9, aFailedInflates_0; "Failed InflateSdbResourceStringAlloc: ["...
0x1801f6dfe  mov     [rsp+0B40h+var_B18], r9; int
0x1801f6e03  mov     dword ptr [rsp+0B40h+var_B20], eax; char *
0x1801f6e07  mov     r9, rsi; char *
0x1801f6e0a  mov     r8, r14; unsigned int
0x1801f6e0d  mov     edx, 3E6h; bool
0x1801f6e12  mov     ecx, edi; this
0x1801f6e14  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
  ... truncated ...
```
