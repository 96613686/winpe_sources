# Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks(RtlArray<ulong> &,ushort const *,Windows::Compat::Appraiser::IPropertyAppender *)

- ea: `0x1801ec93c`
- end: `0x1801ed56a`
- name: `?LookupMachineBlocks@MachineSdbDataSource@Appraiser@Compat@Windows@@AEAAJAEAV?$RtlArray@K@@PEBGPEAVIPropertyAppender@234@@Z`
- size: `3118`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1801ebb60`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x180013f90`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18003b2a0`
- `0x180083390`
- `0x180088940`
- `0x18008a254`
- `0x18008b374`
- `0x18008b5f8`
- `0x18008badc`
- `0x18009606c`
- `0x1801b3078`
- `0x1801baf00`
- `0x1801ec93c`
- `0x1801fadc8`
- `0x1801fbf8c`
- `0x18021f010`

## import_xrefs

- `KERNEL32!RtlCompareMemory` at `0x1801ecb50`
- `KERNEL32!RtlCompareMemory` at `0x1801ecb50`
- `KERNEL32!GetProcessHeap` at `0x1801ec985`
- `KERNEL32!GetProcessHeap` at `0x1801ec996`
- `KERNEL32!GetProcessHeap` at `0x1801ec9c7`
- `KERNEL32!GetProcessHeap` at `0x1801ec9ee`
- `KERNEL32!GetProcessHeap` at `0x1801ed336`
- `KERNEL32!GetProcessHeap` at `0x1801ed383`
- `KERNEL32!GetProcessHeap` at `0x1801ec985`
- `KERNEL32!GetProcessHeap` at `0x1801ec996`
- `KERNEL32!GetProcessHeap` at `0x1801ec9c7`
- `KERNEL32!GetProcessHeap` at `0x1801ec9ee`
- `KERNEL32!GetProcessHeap` at `0x1801ed336`
- `KERNEL32!GetProcessHeap` at `0x1801ed383`
- `KERNEL32!HeapFree` at `0x1801ed344`
- `KERNEL32!HeapFree` at `0x1801ed391`
- `KERNEL32!HeapFree` at `0x1801ed3a8`
- `KERNEL32!HeapFree` at `0x1801ed3be`
- `KERNEL32!HeapFree` at `0x1801ed3dd`
- `KERNEL32!HeapFree` at `0x1801ed344`
- `KERNEL32!HeapFree` at `0x1801ed391`
- `KERNEL32!HeapFree` at `0x1801ed3a8`
- `KERNEL32!HeapFree` at `0x1801ed3be`
- `KERNEL32!HeapFree` at `0x1801ed3dd`

## string_xrefs

- `0x1801ed235`: `SdbHyperlinkTarget`
- `0x1801ed24e`: `SdbHyperlinkTarget`
- `0x1801ed277`: `SdbHyperlinkTarget`
- `0x1801ed2a0`: `SdbHyperlinkText`
- `0x1801eca5b`: `onecore\base\appcompat\appraiser\datasource\machinesdb.cpp`
- `0x1801eca8c`: `onecore\base\appcompat\appraiser\datasource\machinesdb.cpp`
- `0x1801eccb9`: `Failed to read GUID from device entry: [0x%x].`
- `0x1801ed52e`: `Failed to read GUID from device entry: [0x%x].`
- `0x1801ecd5b`: `Failed to read app name from os upgrade entry: [0x%x].`
- `0x1801ed504`: `Failed to read app name from os upgrade entry: [0x%x].`
- `0x1801eccfe`: `Failed to read app GUID from os upgrade entry: [0x%x].`
- `0x1801ed519`: `Failed to read app GUID from os upgrade entry: [0x%x].`
- `0x1801eca54`: `Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks`
- `0x1801eca85`: `Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks`
- `0x1801ecdb2`: `Failed to read app vendor from os upgrade entry: [0x%x].`
- `0x1801ed4ea`: `Failed to read app vendor from os upgrade entry: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks(
        __int64 a1,
        unsigned __int64 *a2,
        char *a3,
        struct Windows::Compat::Appraiser::IPropertyAppender *a4)
{
  unsigned __int64 v5; // r13
  int v6; // eax
  int SdbEntryTargets; // ebx
  char v8; // dl
  int MatchingMachineBlocks; // eax
  const char *v10; // rax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // r15
  unsigned int *v13; // r12
  unsigned __int64 v14; // rbx
  unsigned __int64 *v15; // r8
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rcx
  __int64 v18; // r13
  int SdbStringForTag; // eax
  int v20; // eax
  unsigned int FirstTagRef; // eax
  unsigned __int64 v22; // r9
  int v23; // ebx
  struct Windows::Compat::Appraiser::IPropertyAppender *v24; // r15
  int appended; // eax
  char v26; // dl
  unsigned int v27; // ecx
  unsigned __int64 v28; // r13
  const wchar_t **v29; // r12
  unsigned __int64 v30; // r15
  const wchar_t **v31; // rax
  const wchar_t *v32; // rcx
  __int64 v33; // rax
  const wchar_t *v34; // r10
  const unsigned __int16 **v35; // rcx
  __int64 v36; // rax
  const wchar_t **v37; // rax
  unsigned __int64 v38; // r15
  unsigned __int64 v39; // r12
  const unsigned __int16 **v40; // rdx
  unsigned __int64 v41; // rax
  char v42; // r12
  struct Windows::Compat::Appraiser::IPropertyAppender *v43; // r15
  int v44; // eax
  struct Windows::Compat::Appraiser::IPropertyAppender *v45; // r9
  unsigned __int16 *v46; // r15
  int v47; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v49; // rax
  const wchar_t **v51; // rax
  char *v52; // [rsp+20h] [rbp-E0h]
  const char *v53; // [rsp+28h] [rbp-D8h]
  char *v54; // [rsp+30h] [rbp-D0h]
  const wchar_t *v55; // [rsp+30h] [rbp-D0h]
  int v56; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *lpMem; // [rsp+40h] [rbp-C0h]
  unsigned int v58[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v59; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v60; // [rsp+58h] [rbp-A8h] BYREF
  struct Windows::Compat::Appraiser::IPropertyAppender *v61; // [rsp+60h] [rbp-A0h]
  unsigned __int64 *v62; // [rsp+70h] [rbp-90h]
  HANDLE hHeap[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v64; // [rsp+88h] [rbp-78h]
  void *v65[2]; // [rsp+98h] [rbp-68h]
  unsigned __int64 v66; // [rsp+A8h] [rbp-58h]
  HANDLE v67[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v68; // [rsp+C0h] [rbp-40h]
  LPVOID v69[2]; // [rsp+D0h] [rbp-30h]
  HANDLE v70[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v71; // [rsp+F0h] [rbp-10h]
  void *v72[2]; // [rsp+100h] [rbp+0h]
  __int64 v73; // [rsp+110h] [rbp+10h]
  __int128 v74; // [rsp+118h] [rbp+18h]
  _BYTE v75[23]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v76; // [rsp+140h] [rbp+40h]
  _DWORD v77[16]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v78[40]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v79[40]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v80[264]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v81[264]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int16 v82[264]; // [rsp+650h] [rbp+550h] BYREF

  v76 = -2;
  v61 = a4;
  v62 = a2;
  v73 = a1;
  GetProcessHeap();
  v67[0] = GetProcessHeap();
  v69[0] = (LPVOID)16;
  v68 = 0;
  v69[1] = 0;
  v5 = 8;
  v67[1] = (HANDLE)8;
  *(_OWORD *)v72 = 0;
  v70[0] = GetProcessHeap();
  v72[0] = (void *)16;
  v71 = 0;
  v72[1] = 0;
  v70[1] = (HANDLE)8;
  hHeap[0] = GetProcessHeap();
  v65[0] = (void *)16;
  v64 = 0;
  v65[1] = 0;
  hHeap[1] = (HANDLE)8;
  memset_0(v78, 0, sizeof(v78));
  v74 = 0;
  memset(v75, 0, sizeof(v75));
  lpMem = 0;
  v6 = RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(v70);
  SdbEntryTargets = v6;
  if ( v6 < 0 )
  {
    LODWORD(v54) = v6;
    v53 = "Failed to initialize RtlArray: [0x%x].";
    v8 = -118;
LABEL_3:
    LODWORD(v52) = SdbEntryTargets;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v8,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
      "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
      v52,
      (int)v53,
      v54);
    goto LABEL_124;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x18Au,
      "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
      "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
      "Failed to initialize RtlArray: [0x%x].",
      v6);
  MatchingMachineBlocks = SdbGetMatchingMachineBlocks(v77);
  if ( !MatchingMachineBlocks )
  {
    SdbEntryTargets = -2147467259;
    v54 = a3;
    v10 = "SdbGetMatchingMachineBlocks failed for: %ls.";
    v8 = -110;
LABEL_8:
    LODWORD(v53) = (_DWORD)v10;
    goto LABEL_3;
  }
  v11 = 0;
  v66 = 0;
  LOBYTE(MatchingMachineBlocks) = BYTE3(v74);
  v59 = MatchingMachineBlocks;
  v12 = v64;
  do
  {
    v13 = &v77[v11];
    if ( !*v13 )
      break;
    v14 = 0;
    v15 = v62;
    if ( !v62[2] )
    {
LABEL_20:
      RtlArray<unsigned int>::Append(v15, v13);
      v80[0] = 0;
      lpMem = 0;
      v60 = 0;
      if ( (_QWORD)v71 )
      {
        *(_QWORD *)v58 = 0;
        if ( is_mul_ok(v71, (unsigned __int64)v70[1]) )
        {
          memset_0(
            v72[1],
            ((unsigned __int64)v71 * (unsigned __int128)(unsigned __int64)v70[1]) >> 64,
            v71 * (__int128)v70[1]);
          *(_QWORD *)&v71 = 0;
        }
      }
      if ( v12 )
      {
        *(_QWORD *)v58 = 0;
        if ( is_mul_ok(v12, v5) )
        {
          memset_0(v65[1], (v12 * (unsigned __int128)v5) >> 64, v12 * v5);
          *(_QWORD *)&v64 = 0;
        }
      }
      v18 = v73;
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::GetSdbEntryTargets(
                          v70,
                          v73 + 176,
                          *(_QWORD *)(v73 + 16),
                          *v13);
      if ( SdbEntryTargets < 0 )
      {
        LODWORD(v54) = SdbEntryTargets;
        v10 = "Failed to get entry targets: [0x%x].";
        v8 = -78;
        goto LABEL_8;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x1B2u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
          "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
          "Failed to get entry targets: [0x%x].",
          SdbEntryTargets);
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::GetTargetListIntersection(hHeap, v70, v18 + 24);
      if ( SdbEntryTargets < 0 )
      {
        LODWORD(v54) = SdbEntryTargets;
        v10 = "Failed to get applicable targets: [0x%x].";
        v8 = -75;
        goto LABEL_8;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x1B5u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
          "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
          "Failed to get applicable targets: [0x%x].",
          SdbEntryTargets);
      v12 = v64;
      if ( !(_QWORD)v64 )
      {
        v5 = (unsigned __int64)hHeap[1];
        goto LABEL_119;
      }
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::GetExeGuid(v78, *(void **)(v18 + 16), *v13);
      if ( SdbEntryTargets < 0 )
      {
        LODWORD(v54) = SdbEntryTargets;
        v10 = "Failed to read GUID from device entry: [0x%x].";
        v8 = -63;
        goto LABEL_8;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x1C1u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
          "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
          "Failed to read GUID from device entry: [0x%x].",
          SdbEntryTargets);
      SdbEntryTargets = Windows::Compat::Appraiser::Utilities::GetAppGuid(v79, *(void **)(v18 + 16), *v13);
      if ( SdbEntryTargets < 0 )
      {
        LODWORD(v54) = SdbEntryTargets;
        v10 = "Failed to read app GUID from os upgrade entry: [0x%x].";
        v8 = -60;
        goto LABEL_8;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x1C4u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
          "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
          "Failed to read app GUID from os upgrade entry: [0x%x].",
          SdbEntryTargets);
      SdbStringForTag = Windows::Compat::Appraiser::Utilities::GetSdbStringForTag(
                          v81,
                          0x104u,
                          *(void **)(v18 + 16),
                          *v13,
                          0x6006u);
      SdbEntryTargets = SdbStringForTag;
      if ( SdbStringForTag == 1 )
      {
        SdbEntryTargets = -2147467259;
      }
      else if ( SdbStringForTag >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x1C7u,
            "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
            "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
            "Failed to read app name from os upgrade entry: [0x%x].",
            SdbStringForTag);
        v20 = Windows::Compat::Appraiser::Utilities::GetSdbStringForTag(
                v82,
                0x104u,
                *(void **)(v18 + 16),
                *v13,
                0x6005u);
        SdbEntryTargets = v20;
        if ( v20 == 1 )
        {
          SdbEntryTargets = -2147467259;
        }
        else if ( v20 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x1CAu,
              "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
              "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
              "Failed to read app vendor from os upgrade entry: [0x%x].",
              v20);
          SdbEntryTargets = Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTagsInternal(
                              (RtlStringArray *)v67,
                              v18 + 232);
          if ( SdbEntryTargets < 0 )
          {
            LODWORD(v54) = SdbEntryTargets;
            v10 = "Failed to get appraiser data tags: [0x%x].";
            v8 = -51;
            goto LABEL_8;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x1CDu,
              "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
              "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
              "Failed to get appraiser data tags: [0x%x].",
              SdbEntryTargets);
          FirstTagRef = SdbFindFirstTagRef(*(void **)(v18 + 16), *v13, 0x7029u);
          v23 = (unsigned __int8)v59;
          if ( FirstTagRef )
            v23 = 1;
          v59 = v23;
          BYTE3(v74) = v23;
          if ( (_BYTE)v23 && !v75[22] )
          {
            Windows::Compat::Appraiser::SdbUtils::GetHyperlinkInfo(
              &v75[22],
              &v60,
              v80,
              v22,
              *(void **)(v18 + 16),
              FirstTagRef,
              (const unsigned __int16 *)(v18 + 232));
            lpMem = v60;
            LOBYTE(v23) = BYTE3(v74);
            v59 = v23;
          }
          v24 = v61;
          v58[0] = (*(__int64 (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyAppender *))(*(_QWORD *)v61 + 8LL))(v61);
          if ( (_BYTE)v23 )
          {
            appended = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                         L"SdbBlockType",
                         L"BlockUpgrade",
                         v58,
                         v24);
            SdbEntryTargets = appended;
            if ( appended < 0 )
            {
              v56 = appended;
              v55 = L"BlockUpgrade";
              v26 = -19;
LABEL_58:
              LODWORD(v52) = SdbEntryTargets;
              Windows::Compat::Appraiser::WriteLog(
                (Windows::Compat::Appraiser *)1,
                v26,
                (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
                "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
                v52,
                (int)"Failed to append %ls: [0x%x].",
                (const char *)v55,
                v56);
              goto LABEL_121;
            }
          }
          else
          {
            SdbEntryTargets = 0;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x1EDu,
              "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
              "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
              "Failed to append %ls: [0x%x].",
              L"BlockUpgrade",
              SdbEntryTargets);
          SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(L"SdbAppGuid", v79, v58, v24);
          if ( SdbEntryTargets < 0 )
          {
            v56 = SdbEntryTargets;
            v55 = L"SdbAppGuid";
            v26 = -13;
            goto LABEL_58;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x1F3u,
              "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
              "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
              "Failed to append %ls: [0x%x].",
              L"SdbAppGuid",
              SdbEntryTargets);
          SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                              L"SdbEntryGuid",
                              v78,
                              v58,
                              v24);
          if ( SdbEntryTargets < 0 )
          {
            v56 = SdbEntryTargets;
            v55 = L"SdbEntryGuid";
            v26 = -7;
            goto LABEL_58;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x1F9u,
              "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
              "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
              "Failed to append %ls: [0x%x].",
              L"SdbEntryGuid",
              SdbEntryTargets);
          SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(L"SdbAppName", v81, v58, v24);
          if ( SdbEntryTargets < 0 )
          {
            v56 = SdbEntryTargets;
            v55 = L"SdbAppName";
            v26 = -1;
            goto LABEL_58;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x1FFu,
              "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
              "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
              "Failed to append %ls: [0x%x].",
              L"SdbAppName",
              SdbEntryTargets);
          SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                              L"SdbAppVendor",
                              v82,
                              v58,
                              v24);
          if ( SdbEntryTargets < 0 )
          {
            v56 = SdbEntryTargets;
            v55 = L"SdbAppVendor";
            v26 = 5;
            goto LABEL_58;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x205u,
              "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
              "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
              "Failed to append %ls: [0x%x].",
              L"SdbAppVendor",
              SdbEntryTargets);
          v27 = 0;
          LODWORD(v60) = 0;
          v28 = v68;
          if ( (_QWORD)v68 )
          {
            v29 = (const wchar_t **)v69[1];
            while ( 1 )
            {
              v30 = v27;
              v31 = 0;
              if ( v27 < v28 )
              {
                if ( !is_mul_ok((unsigned __int64)v67[1], v27)
                  || (v31 = (const wchar_t **)((char *)v29 + (unsigned __int64)v67[1] * v27), v31 < v29) )
                {
                  v31 = 0;
                }
              }
              v32 = *v31;
              v33 = -1;
              do
                ++v33;
              while ( v32[v33] );
              v34 = &v32[v33];
              v35 = 0;
              if ( v30 < v28 )
              {
                v36 = (unsigned __int64)v67[1] * v30;
                if ( !is_mul_ok((unsigned __int64)v67[1], v30)
                  || (v35 = (const wchar_t **)((char *)v29 + v36), (const wchar_t **)((char *)v29 + v36) < v29) )
                {
                  v35 = 0;
                }
              }
              SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(*v35, v34 + 1, v58, v61);
              if ( SdbEntryTargets < 0 )
                break;
              if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              {
                v37 = 0;
                if ( v30 < v28 )
                {
                  if ( !is_mul_ok((unsigned __int64)v67[1], v30)
                    || (v37 = (const wchar_t **)((char *)v29 + (unsigned __int64)v67[1] * v30), v37 < v29) )
                  {
                    v37 = 0;
                  }
                }
                Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                  0x20Du,
                  "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
                  "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
                  "Failed to append %ls: [0x%x].",
                  *v37,
                  SdbEntryTargets);
              }
              v27 = (_DWORD)v60 + 1;
              LODWORD(v60) = v27;
              if ( v27 >= v28 )
                goto LABEL_94;
            }
            v51 = 0;
            if ( v30 < v28 )
            {
              if ( !is_mul_ok((unsigned __int64)v67[1], v30)
                || (v51 = (const wchar_t **)((char *)v29 + (unsigned __int64)v67[1] * v30), v51 < v29) )
              {
                v51 = 0;
              }
            }
            v56 = SdbEntryTargets;
            v55 = *v51;
            v26 = 13;
            goto LABEL_58;
          }
LABEL_94:
          v38 = 0;
          v5 = (unsigned __int64)hHeap[1];
          v39 = v64;
          if ( (_QWORD)v64 )
          {
            while ( 1 )
            {
              v40 = 0;
              if ( v38 < v39 )
              {
                v41 = v5 * v38;
                if ( !is_mul_ok(v5, v38)
                  || (v40 = (const unsigned __int16 **)((char *)v65[1] + v41), (char *)v65[1] + v41 < v65[1]) )
                {
                  v40 = 0;
                }
              }
              SdbEntryTargets = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                                  L"ApplicableTargetVersion",
                                  *v40,
                                  v58,
                                  v61);
              if ( SdbEntryTargets < 0 )
                break;
              if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                  0x216u,
                  "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
                  "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
                  "Failed to append %ls: [0x%x].",
                  L"ApplicableTargetVersion",
                  SdbEntryTargets);
              if ( ++v38 >= v39 )
                goto LABEL_103;
            }
            v56 = SdbEntryTargets;
            v55 = L"ApplicableTargetVersion";
            v26 = 22;
            goto LABEL_58;
          }
LABEL_103:
          v42 = v75[22];
          v43 = v61;
          if ( v75[22] )
          {
            v44 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(L"SdbHyperlinkTarget", v80, v58, v61);
            SdbEntryTargets = v44;
            if ( v44 < 0 )
            {
              v56 = v44;
              v55 = (const wchar_t *)L"SdbHyperlinkTarget";
              v26 = 34;
              goto LABEL_58;
            }
          }
          else
          {
            SdbEntryTargets = 0;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x222u,
              "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
              "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
              "Failed to append %ls: [0x%x].",
              (const wchar_t *)L"SdbHyperlinkTarget",
              SdbEntryTargets);
          if ( v42 )
          {
            v45 = v43;
            v46 = lpMem;
            v47 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(L"SdbHyperlinkText", lpMem, v58, v45);
            SdbEntryTargets = v47;
            if ( v47 < 0 )
            {
              LODWORD(v52) = v47;
              Windows::Compat::Appraiser::WriteLog(
                (Windows::Compat::Appraiser *)1,
                41,
                (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
                "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
                v52,
                (int)"Failed to append %ls: [0x%x].",
                L"SdbHyperlinkText",
                v47);
              goto LABEL_122;
            }
          }
          else
          {
            SdbEntryTargets = 0;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x229u,
              "onecore\\base\\appcompat\\appraiser\\datasource\\machinesdb.cpp",
              "Windows::Compat::Appraiser::MachineSdbDataSource::LookupMachineBlocks",
              "Failed to append %ls: [0x%x].",
              (const wchar_t *)L"SdbHyperlinkText",
              SdbEntryTargets);
          if ( lpMem )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, lpMem);
            lpMem = 0;
          }
          v12 = v64;
          goto LABEL_119;
        }
        LODWORD(v54) = SdbEntryTargets;
        v10 = "Failed to read app vendor from os upgrade entry: [0x%x].";
        v8 = -54;
        goto LABEL_8;
      }
      LODWORD(v54) = SdbEntryTargets;
      v10 = "Failed to read app name from os upgrade entry: [0x%x].";
      v8 = -57;
      goto LABEL_8;
    }
    while ( 1 )
    {
      v60 = 0;
      v16 = v15[1] * v14;
      if ( !is_mul_ok(v15[1], v14) )
        goto LABEL_16;
      v17 = v15[5];
      if ( v17 + v16 < v17 )
        goto LABEL_16;
      if ( RtlCompareMemory(v13, (const void *)(v17 + v16), 4u) == 4 )
        break;
      v15 = v62;
LABEL_16:
      if ( ++v14 >= v15[2] )
        goto LABEL_20;
    }
    if ( v14 == -1 )
    {
      v15 = v62;
      goto LABEL_20;
    }
LABEL_119:
    v11 = v66 + 1;
    v66 = v11;
  }
  while ( v11 < 0x10 );
  SdbEntryTargets = 0;
LABEL_121:
  v46 = lpMem;
LABEL_122:
  if ( v46 )
  {
    v49 = GetProcessHeap();
    HeapFree(v49, 0, v46);
  }
LABEL_124:
  if ( v65[1] )
    HeapFree(hHeap[0], 0, v65[1]);
  if ( v72[1] )
    HeapFree(v70[0], 0, v72[1]);
  RtlStringArray::Clear((RtlStringArray *)v67);
  if ( v69[1] )
    HeapFree(v67[0], 0, v69[1]);
  return (unsigned int)SdbEntryTargets;
}

```

## disassembly

```asm
0x1801ec93c  push    rbp
0x1801ec93e  push    rbx
0x1801ec93f  push    rsi
0x1801ec940  push    rdi
0x1801ec941  push    r12
0x1801ec943  push    r13
0x1801ec945  push    r14
0x1801ec947  push    r15
0x1801ec949  lea     rbp, [rsp-778h]
0x1801ec951  sub     rsp, 878h
0x1801ec958  mov     [rbp+7B0h+var_770], 0FFFFFFFFFFFFFFFEh
0x1801ec960  mov     rax, cs:__security_cookie
0x1801ec967  xor     rax, rsp
0x1801ec96a  mov     [rbp+7B0h+var_50], rax
0x1801ec971  mov     [rsp+8B0h+var_850], r9
0x1801ec976  mov     r15, r8
0x1801ec979  mov     [rsp+8B0h+var_840], rdx
0x1801ec97e  mov     r12, rcx
0x1801ec981  mov     [rbp+7B0h+var_7A0], rcx
0x1801ec985  call    cs:__imp_GetProcessHeap
0x1801ec98b  xorps   xmm0, xmm0
0x1801ec98e  movups  xmmword ptr [rbp+7B0h+var_800], xmm0
0x1801ec992  movups  xmmword ptr [rbp+7B0h+var_7E0], xmm0
0x1801ec996  call    cs:__imp_GetProcessHeap
0x1801ec99c  mov     [rbp+7B0h+var_800], rax
0x1801ec9a0  mov     ebx, 10h
0x1801ec9a5  mov     [rbp+7B0h+var_7E0], rbx
0x1801ec9a9  xorps   xmm0, xmm0
0x1801ec9ac  movdqu  [rbp+7B0h+var_7F0], xmm0
0x1801ec9b1  xor     edi, edi
0x1801ec9b3  mov     [rbp+7B0h+var_7E0+8], rdi
0x1801ec9b7  lea     r13d, [rbx-8]
0x1801ec9bb  mov     [rbp+7B0h+var_800+8], r13
0x1801ec9bf  movups  xmmword ptr [rbp+7B0h+var_7D0], xmm0
0x1801ec9c3  movups  xmmword ptr [rbp+7B0h+var_7B0], xmm0
0x1801ec9c7  call    cs:__imp_GetProcessHeap
0x1801ec9cd  mov     [rbp+7B0h+var_7D0], rax
0x1801ec9d1  mov     [rbp+7B0h+var_7B0], rbx
0x1801ec9d5  xorps   xmm0, xmm0
0x1801ec9d8  movdqu  [rbp+7B0h+var_7C0], xmm0
0x1801ec9dd  mov     [rbp+7B0h+var_7B0+8], rdi
0x1801ec9e1  mov     [rbp+7B0h+var_7D0+8], r13
0x1801ec9e5  movups  xmmword ptr [rsp+8B0h+hHeap], xmm0
0x1801ec9ea  movups  xmmword ptr [rbp+7B0h+var_818], xmm0
0x1801ec9ee  call    cs:__imp_GetProcessHeap
0x1801ec9f4  mov     [rsp+8B0h+hHeap], rax
0x1801ec9f9  mov     [rbp+7B0h+var_818], rbx
0x1801ec9fd  xorps   xmm0, xmm0
0x1801eca00  movdqu  [rbp+7B0h+var_828], xmm0
0x1801eca05  mov     [rbp+7B0h+var_818+8], rdi
0x1801eca09  mov     [rbp+7B0h+hHeap+8], r13
0x1801eca0d  xor     edx, edx; Val
0x1801eca0f  lea     r8d, [rbx+40h]; Size
0x1801eca13  lea     rcx, [rbp+7B0h+var_720]; void *
0x1801eca1a  call    memset_0
0x1801eca1f  xorps   xmm0, xmm0
0x1801eca22  xor     eax, eax
0x1801eca24  movups  [rbp+7B0h+var_798], xmm0
0x1801eca28  movups  [rbp+7B0h+var_788], xmm0
0x1801eca2c  mov     qword ptr [rbp+7B0h+var_788+0Fh], rax
0x1801eca30  mov     [rsp+8B0h+lpMem], rdi
0x1801eca35  lea     rcx, [rbp+7B0h+var_7D0]
0x1801eca39  call    ?Initialize@?$RtlArray@PEAVIProperty@Appraiser@Compat@Windows@@@@QEAAJ_K@Z; RtlArray<Windows::Compat::Appraiser::IProperty *>::Initialize(unsigned __int64)
0x1801eca3e  mov     ebx, eax
0x1801eca40  test    eax, eax
0x1801eca42  jns     short loc_1801ECA78
0x1801eca44  mov     dword ptr [rsp+8B0h+var_880], eax; char *
0x1801eca48  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1801eca4f  mov     qword ptr [rsp+8B0h+var_888], r9; int
0x1801eca54  lea     r9, aWindowsCompatA_689; "Windows::Compat::Appraiser::MachineSdbD"...
0x1801eca5b  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801eca62  mov     edx, 18Ah; bool
0x1801eca67  lea     ecx, [rdi+1]; this
0x1801eca6a  mov     dword ptr [rsp+8B0h+var_890], ebx; char *
0x1801eca6e  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801eca73  jmp     loc_1801ED398
0x1801eca78  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801eca7e  mov     edi, 1
0x1801eca83  and     eax, edi
0x1801eca85  lea     rsi, aWindowsCompatA_689; "Windows::Compat::Appraiser::MachineSdbD"...
0x1801eca8c  lea     r14, aOnecoreBaseApp_2; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801eca93  test    al, al
0x1801eca95  jz      short loc_1801ECAB2
0x1801eca97  mov     dword ptr [rsp+8B0h+var_890], ebx
0x1801eca9b  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x1801ecaa2  mov     r8, rsi; char *
0x1801ecaa5  mov     rdx, r14; char *
0x1801ecaa8  mov     ecx, 18Ah; unsigned int
0x1801ecaad  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801ecab2  mov     r9, r15
0x1801ecab5  mov     r8, [r12+10h]
0x1801ecaba  lea     rcx, [rbp+7B0h+var_760]; void *
0x1801ecabe  call    SdbGetMatchingMachineBlocks
0x1801ecac3  xor     r8d, r8d
0x1801ecac6  test    eax, eax
0x1801ecac8  jnz     short loc_1801ECAF2
0x1801ecaca  mov     ebx, 80004005h
0x1801ecacf  mov     [rsp+8B0h+var_880], r15
0x1801ecad4  lea     rax, aSdbgetmatching; "SdbGetMatchingMachineBlocks failed for:"...
0x1801ecadb  mov     edx, 192h
0x1801ecae0  mov     qword ptr [rsp+8B0h+var_888], rax
0x1801ecae5  mov     r8, r14
0x1801ecae8  mov     r9, rsi
0x1801ecaeb  mov     ecx, edi
0x1801ecaed  jmp     loc_1801ECA6A
0x1801ecaf2  mov     rcx, r8
0x1801ecaf5  mov     [rbp+7B0h+var_808], rcx
0x1801ecaf9  mov     al, byte ptr [rbp+7B0h+var_798+3]
0x1801ecafc  mov     [rsp+8B0h+var_860], eax
0x1801ecb00  mov     r15, qword ptr [rbp+7B0h+var_828]
0x1801ecb04  lea     r12, [rbp+7B0h+var_760]
0x1801ecb08  lea     r12, [r12+rcx*4]
0x1801ecb0c  cmp     [r12], r8d
0x1801ecb10  jz      loc_1801ED376
0x1801ecb16  mov     rbx, r8
0x1801ecb19  mov     r8, [rsp+8B0h+var_840]
0x1801ecb1e  cmp     qword ptr [r8+10h], 0
0x1801ecb23  jbe     short loc_1801ECB7B
0x1801ecb25  mov     [rsp+8B0h+var_858], 0
0x1801ecb2e  mov     rax, rbx
0x1801ecb31  mul     qword ptr [r8+8]
0x1801ecb35  test    rdx, rdx
0x1801ecb38  jnz     short loc_1801ECB61
0x1801ecb3a  mov     rcx, [r8+28h]
0x1801ecb3e  lea     rdx, [rcx+rax]; Source2
0x1801ecb42  cmp     rdx, rcx
0x1801ecb45  jb      short loc_1801ECB61
0x1801ecb47  mov     r8d, 4; Length
0x1801ecb4d  mov     rcx, r12; Source1
0x1801ecb50  call    cs:__imp_RtlCompareMemory
0x1801ecb56  cmp     rax, 4
0x1801ecb5a  jz      short loc_1801ECB6C
0x1801ecb5c  mov     r8, [rsp+8B0h+var_840]
0x1801ecb61  add     rbx, rdi
0x1801ecb64  cmp     rbx, [r8+10h]
0x1801ecb68  jb      short loc_1801ECB25
0x1801ecb6a  jmp     short loc_1801ECB7B
0x1801ecb6c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801ecb70  jnz     loc_1801ED35E
0x1801ecb76  mov     r8, [rsp+8B0h+var_840]
0x1801ecb7b  mov     rdx, r12
0x1801ecb7e  mov     rcx, r8
0x1801ecb81  call    ?Append@?$RtlArray@I@@QEAAJAEBI@Z; RtlArray<uint>::Append(uint const &)
0x1801ecb86  xor     ebx, ebx
0x1801ecb88  mov     [rbp+7B0h+var_680], bx
0x1801ecb8f  mov     [rsp+8B0h+lpMem], rbx
0x1801ecb94  mov     [rsp+8B0h+var_858], rbx
0x1801ecb99  mov     rcx, qword ptr [rbp+7B0h+var_7C0]
0x1801ecb9d  test    rcx, rcx
0x1801ecba0  jz      short loc_1801ECBC3
0x1801ecba2  mov     qword ptr [rsp+8B0h+var_868], rbx
0x1801ecba7  mov     rax, [rbp+7B0h+var_7D0+8]
0x1801ecbab  mul     rcx
0x1801ecbae  test    rdx, rdx
0x1801ecbb1  jnz     short loc_1801ECBC3
0x1801ecbb3  mov     r8, rax; Size
0x1801ecbb6  mov     rcx, [rbp+7B0h+var_7B0+8]; void *
0x1801ecbba  call    memset_0
0x1801ecbbf  mov     qword ptr [rbp+7B0h+var_7C0], rbx
0x1801ecbc3  test    r15, r15
0x1801ecbc6  jz      short loc_1801ECBE8
0x1801ecbc8  mov     qword ptr [rsp+8B0h+var_868], rbx
0x1801ecbcd  mov     rax, r13
0x1801ecbd0  mul     r15
0x1801ecbd3  test    rdx, rdx
0x1801ecbd6  jnz     short loc_1801ECBE8
0x1801ecbd8  mov     r8, rax; Size
0x1801ecbdb  mov     rcx, [rbp+7B0h+var_818+8]; void *
0x1801ecbdf  call    memset_0
0x1801ecbe4  mov     qword ptr [rbp+7B0h+var_828], rbx
0x1801ecbe8  mov     r13, [rbp+7B0h+var_7A0]
0x1801ecbec  lea     rdx, [r13+0B0h]
0x1801ecbf3  mov     r9d, [r12]
0x1801ecbf7  mov     r8, [r13+10h]
0x1801ecbfb  lea     rcx, [rbp+7B0h+var_7D0]
0x1801ecbff  call    ?GetSdbEntryTargets@Utilities@Appraiser@Compat@Windows@@SAJAEAV?$RtlArray@PEBG@@AEAVRtlStringArray@@PEAXK@Z; Windows::Compat::Appraiser::Utilities::GetSdbEntryTargets(RtlArray<ushort const *> &,RtlStringArray &,void *,ulong)
0x1801ecc04  mov     ebx, eax
0x1801ecc06  test    eax, eax
0x1801ecc08  js      loc_1801ED554
0x1801ecc0e  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801ecc14  and     eax, edi
0x1801ecc16  test    al, al
0x1801ecc18  jz      short loc_1801ECC35
0x1801ecc1a  mov     dword ptr [rsp+8B0h+var_890], ebx
0x1801ecc1e  lea     r9, aFailedToGetEnt; "Failed to get entry targets: [0x%x]."
0x1801ecc25  mov     r8, rsi; char *
0x1801ecc28  mov     rdx, r14; char *
0x1801ecc2b  mov     ecx, 1B2h; unsigned int
0x1801ecc30  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801ecc35  lea     r8, [r13+18h]
0x1801ecc39  lea     rdx, [rbp+7B0h+var_7D0]
0x1801ecc3d  lea     rcx, [rsp+8B0h+hHeap]
0x1801ecc42  call    ?GetTargetListIntersection@Utilities@Appraiser@Compat@Windows@@SAJAEAV?$RtlArray@PEBG@@00@Z; Windows::Compat::Appraiser::Utilities::GetTargetListIntersection(RtlArray<ushort const *> &,RtlArray<ushort const *> &,RtlArray<ushort const *> &)
0x1801ecc47  mov     ebx, eax
0x1801ecc49  xor     r8d, r8d
0x1801ecc4c  test    eax, eax
0x1801ecc4e  js      loc_1801ED53F
0x1801ecc54  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801ecc5a  and     eax, edi
0x1801ecc5c  test    al, al
0x1801ecc5e  jz      short loc_1801ECC7E
0x1801ecc60  mov     dword ptr [rsp+8B0h+var_890], ebx
0x1801ecc64  lea     r9, aFailedToGetApp_1; "Failed to get applicable targets: [0x%x"...
0x1801ecc6b  mov     r8, rsi; char *
0x1801ecc6e  mov     rdx, r14; char *
0x1801ecc71  mov     ecx, 1B5h; unsigned int
0x1801ecc76  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801ecc7b  xor     r8d, r8d
0x1801ecc7e  mov     r15, qword ptr [rbp+7B0h+var_828]
0x1801ecc82  test    r15, r15
0x1801ecc85  jz      loc_1801ED358
0x1801ecc8b  mov     r8d, [r12]; unsigned int
0x1801ecc8f  mov     rdx, [r13+10h]; void *
0x1801ecc93  lea     rcx, [rbp+7B0h+var_720]; unsigned __int16 *
0x1801ecc9a  call    ?GetExeGuid@Utilities@Appraiser@Compat@Windows@@SAJPEAGPEAXK@Z; Windows::Compat::Appraiser::Utilities::GetExeGuid(ushort *,void *,ulong)
0x1801ecc9f  mov     ebx, eax
0x1801ecca1  test    eax, eax
0x1801ecca3  js      loc_1801ED52A
0x1801ecca9  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801eccaf  and     eax, edi
0x1801eccb1  test    al, al
0x1801eccb3  jz      short loc_1801ECCD0
0x1801eccb5  mov     dword ptr [rsp+8B0h+var_890], ebx
0x1801eccb9  lea     r9, aFailedToReadGu; "Failed to read GUID from device entry: "...
0x1801eccc0  mov     r8, rsi; char *
0x1801eccc3  mov     rdx, r14; char *
0x1801eccc6  mov     ecx, 1C1h; unsigned int
0x1801ecccb  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801eccd0  mov     r8d, [r12]; unsigned int
0x1801eccd4  mov     rdx, [r13+10h]; void *
0x1801eccd8  lea     rcx, [rbp+7B0h+var_6D0]; unsigned __int16 *
0x1801eccdf  call    ?GetAppGuid@Utilities@Appraiser@Compat@Windows@@SAJPEAGPEAXK@Z; Windows::Compat::Appraiser::Utilities::GetAppGuid(ushort *,void *,ulong)
0x1801ecce4  mov     ebx, eax
0x1801ecce6  test    eax, eax
0x1801ecce8  js      loc_1801ED515
0x1801eccee  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801eccf4  and     eax, edi
0x1801eccf6  test    al, al
0x1801eccf8  jz      short loc_1801ECD15
0x1801eccfa  mov     dword ptr [rsp+8B0h+var_890], ebx
0x1801eccfe  lea     r9, aFailedToReadAp_2; "Failed to read app GUID from os upgrade"...
0x1801ecd05  mov     r8, rsi; char *
0x1801ecd08  mov     rdx, r14; char *
0x1801ecd0b  mov     ecx, 1C4h; unsigned int
0x1801ecd10  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801ecd15  mov     word ptr [rsp+8B0h+var_890], 6006h; unsigned __int16
0x1801ecd1c  mov     r9d, [r12]; unsigned int
0x1801ecd20  mov     r8, [r13+10h]; void *
0x1801ecd24  mov     r15d, 104h
0x1801ecd2a  mov     edx, r15d; unsigned __int64
0x1801ecd2d  lea     rcx, [rbp+7B0h+var_470]; unsigned __int16 *
0x1801ecd34  call    ?GetSdbStringForTag@Utilities@Appraiser@Compat@Windows@@CAJPEAG_KPEAXKG@Z; Windows::Compat::Appraiser::Utilities::GetSdbStringForTag(ushort *,unsigned __int64,void *,ulong,ushort)
0x1801ecd39  mov     ebx, eax
0x1801ecd3b  cmp     eax, edi
0x1801ecd3d  jz      loc_1801ED4FB
0x1801ecd43  test    eax, eax
0x1801ecd45  js      loc_1801ED500
0x1801ecd4b  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801ecd51  and     eax, edi
0x1801ecd53  test    al, al
0x1801ecd55  jz      short loc_1801ECD72
0x1801ecd57  mov     dword ptr [rsp+8B0h+var_890], ebx
0x1801ecd5b  lea     r9, aFailedToReadAp_1; "Failed to read app name from os upgrade"...
0x1801ecd62  mov     r8, rsi; char *
0x1801ecd65  mov     rdx, r14; char *
0x1801ecd68  mov     ecx, 1C7h; unsigned int
0x1801ecd6d  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801ecd72  mov     word ptr [rsp+8B0h+var_890], 6005h; unsigned __int16
0x1801ecd79  mov     r9d, [r12]; unsigned int
0x1801ecd7d  mov     r8, [r13+10h]; void *
0x1801ecd81  mov     rdx, r15; unsigned __int64
0x1801ecd84  lea     rcx, [rbp+7B0h+var_260]; unsigned __int16 *
0x1801ecd8b  call    ?GetSdbStringForTag@Utilities@Appraiser@Compat@Windows@@CAJPEAG_KPEAXKG@Z; Windows::Compat::Appraiser::Utilities::GetSdbStringForTag(ushort *,unsigned __int64,void *,ulong,ushort)
0x1801ecd90  mov     ebx, eax
0x1801ecd92  cmp     eax, edi
0x1801ecd94  jz      loc_1801ED4E1
0x1801ecd9a  test    eax, eax
0x1801ecd9c  js      loc_1801ED4E6
0x1801ecda2  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801ecda8  and     eax, edi
0x1801ecdaa  test    al, al
0x1801ecdac  jz      short loc_1801ECDC9
0x1801ecdae  mov     dword ptr [rsp+8B0h+var_890], ebx
0x1801ecdb2  lea     r9, aFailedToReadAp_0; "Failed to read app vendor from os upgra"...
0x1801ecdb9  mov     r8, rsi; char *
0x1801ecdbc  mov     rdx, r14; char *
0x1801ecdbf  mov     ecx, 1CAh; unsigned int
0x1801ecdc4  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801ecdc9  lea     r15, [r13+0E8h]
0x1801ecdd0  mov     [rsp+8B0h+var_890], r15; __int64
0x1801ecdd5  mov     r9d, [r12]
0x1801ecdd9  mov     r8, [r13+10h]
0x1801ecddd  xor     edx, edx
0x1801ecddf  lea     rcx, [rbp+7B0h+var_800]; this
0x1801ecde3  call    ?GetAppraiserDataTagsInternal@SdbUtils@Appraiser@Compat@Windows@@CAJPEAVRtlNameValueArray@@PEAV?$RtlArray@PEBG@@PEAXKPEBG@Z; Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTagsInternal(RtlNameValueArray *,RtlArray<ushort const *> *,void *,ulong,ushort const *)
0x1801ecde8  mov     ebx, eax
0x1801ecdea  test    eax, eax
0x1801ecdec  js      loc_1801ED4CC
0x1801ecdf2  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801ecdf8  and     eax, edi
  ... truncated ...
```
