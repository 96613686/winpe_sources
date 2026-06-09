# Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb(Windows::Compat::Appraiser::SetupRunInfo *)

- ea: `0x18004608c`
- end: `0x180046688`
- name: `?TryReuseInboxAdlSdb@SetupAppraiser@Appraiser@Compat@Windows@@AEAAJPEAUSetupRunInfo@234@@Z`
- size: `1532`
- prototype: `int(Windows::Compat::Appraiser::SetupAppraiser *__hidden this, struct Windows::Compat::Appraiser::SetupRunInfo *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180041b90`

## callees

- `0x180008570`
- `0x180011d94`
- `0x18002a8b4`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800425b8`
- `0x18004608c`
- `0x180086ec8`
- `0x180088ef0`
- `0x180093cfc`
- `0x180097108`
- `0x1800975e4`
- `0x1800a5d88`
- `0x1801afbd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180046465`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180046550`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180046465`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180046550`
- `KERNEL32!CopyFileW` at `0x1800461fc`
- `KERNEL32!CopyFileW` at `0x1800461fc`
- `KERNEL32!GetLastError` at `0x180046206`
- `KERNEL32!GetLastError` at `0x180046225`
- `KERNEL32!GetLastError` at `0x180046206`
- `KERNEL32!GetLastError` at `0x180046225`
- `SHLWAPI!PathFileExistsW` at `0x1800460d8`
- `SHLWAPI!PathFileExistsW` at `0x1800460d8`

## string_xrefs

- `0x180046139`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x180046168`: `onecore\base\appcompat\appraiser\heads\setup\setupappraiser.cpp`
- `0x18004612d`: `Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb`
- `0x18004615c`: `Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb`
- `0x180046234`: `Failed to copy file: [%d].`
- `0x180046257`: `Failed to check/create directory: [0x%x].`
- `0x18004627d`: `Failed to check/create directory: [0x%x].`
- `0x180046362`: `Failed to check adl data path for sdb version: [0x%x].`
- `0x180046388`: `Failed to check adl data path for sdb version: [0x%x].`
- `0x1800465a0`: `SDB will be replaced with inbox ADL's SDB.  Current SdbVer: [%d], New SdbVer: [%d].`
- `0x18004662e`: `SDB was replaced with inbox ADL's SDB.  Previous SdbVer: [%d], Current SdbVer: [%d].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb(
        Windows::Compat::Appraiser::SetupAppraiser *this,
        struct Windows::Compat::Appraiser::SetupRunInfo *a2)
{
  const unsigned __int16 *v2; // r12
  int v4; // eax
  signed int v5; // ebx
  char v6; // dl
  signed int LastError; // eax
  int v8; // eax
  void (*v9)(const unsigned __int16 *, void *); // r8
  void *v10; // r9
  int Cabinet; // eax
  int MetadataParameterFromFile; // eax
  int v13; // eax
  int v14; // eax
  const unsigned __int16 *v15; // rax
  unsigned int v16; // eax
  unsigned __int64 v17; // rdx
  int MapTableValueFromFile; // ebx
  __int64 v19; // rcx
  int v20; // eax
  bool v21; // al
  unsigned int v22; // r15d
  unsigned int v23; // r12d
  bool v24; // al
  Windows::Compat::Appraiser::SetupAppraiser *v25; // rcx
  int v26; // eax
  char *v28; // [rsp+20h] [rbp-E0h]
  char *v29; // [rsp+20h] [rbp-E0h]
  const char *v30; // [rsp+28h] [rbp-D8h]
  char *v31; // [rsp+30h] [rbp-D0h]
  __int64 v32; // [rsp+38h] [rbp-C8h]
  char v33; // [rsp+40h] [rbp-C0h]
  unsigned int v34; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v35; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v36; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v37; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v38[12]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v39[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v40[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR NewFileName[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v42[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v2 = Windows::Compat::Appraiser::WicaFactory::InboxDirectoryPathInputAlternateDataCab;
  v36 = 0;
  v35 = 0;
  v34 = 0;
  v37 = 0;
  if ( !PathFileExistsW(Windows::Compat::Appraiser::WicaFactory::InboxDirectoryPathInputAlternateDataCab)
    || (int)Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(0, 0, v2) < 0 )
  {
    return 1;
  }
  v4 = StringCchPrintfW(NewFileName, 0x104u, L"%ls\\Appraiser_InboxAlternateData.cab", *((_QWORD *)a2 + 1899));
  v5 = v4;
  if ( v4 < 0 )
  {
    LODWORD(v31) = v4;
    v30 = "Failed to print string: [0x%x].";
    v6 = 92;
LABEL_5:
    LODWORD(v28) = v5;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v6,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
      v28,
      (int)v30,
      v31);
    return (unsigned int)v5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x25Cu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
      "Failed to print string: [0x%x].",
      v4);
  v5 = StringCchPrintfW(v40, 0x104u, L"%ls\\InboxAlternateData", *((_QWORD *)a2 + 1899));
  if ( v5 < 0 )
  {
    v6 = 98;
LABEL_10:
    LODWORD(v31) = v5;
    v30 = "Failed to print string: [0x%x].";
    goto LABEL_5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x262u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
      "Failed to print string: [0x%x].",
      v5);
  if ( !CopyFileW(v2, NewFileName, 0) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    LODWORD(v31) = GetLastError();
    v6 = 103;
    v30 = "Failed to copy file: [%d].";
    goto LABEL_5;
  }
  v8 = Windows::Compat::Appraiser::Utilities::EnsureDirectoryExists(v40);
  v5 = v8;
  if ( v8 < 0 )
  {
    LODWORD(v31) = v8;
    v30 = "Failed to check/create directory: [0x%x].";
    v6 = 107;
    goto LABEL_5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x26Bu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
      "Failed to check/create directory: [0x%x].",
      v8);
  Cabinet = DiagExtractCabinet(NewFileName, v40, v9, v10);
  v5 = Cabinet;
  if ( Cabinet < 0 )
  {
    LODWORD(v31) = Cabinet;
    v30 = "Failed to extract cab file: [0x%x].";
    v6 = 110;
    goto LABEL_5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x26Eu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
      "Failed to extract cab file: [0x%x].",
      Cabinet);
  v5 = StringCchPrintfW(v39, 0x104u, L"%ls\\Appraiser_Data.ini", v40);
  if ( v5 < 0 )
  {
    v6 = 116;
    goto LABEL_10;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x274u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
      "Failed to print string: [0x%x].",
      v5);
  MetadataParameterFromFile = Windows::Compat::Appraiser::DataFile::GetMetadataParameterFromFile(
                                &v37,
                                v39,
                                L"AppraiserSdbVer");
  v5 = MetadataParameterFromFile;
  if ( MetadataParameterFromFile < 0 )
  {
    LODWORD(v31) = MetadataParameterFromFile;
    v30 = "Failed to check adl data path for sdb version: [0x%x].";
    v6 = 124;
    goto LABEL_5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x27Cu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
      "Failed to check adl data path for sdb version: [0x%x].",
      MetadataParameterFromFile);
  v13 = Windows::Compat::Appraiser::DataFile::GetMetadataParameterFromFile(&v34, v39, L"AppraiserMinCodeVerForSdbUse");
  v5 = v13;
  if ( v13 < 0 )
  {
    LODWORD(v31) = v13;
    v30 = "Failed to check min code ver for sdb use: [0x%x].";
    v6 = 127;
    goto LABEL_5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x27Fu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
      "Failed to check min code ver for sdb use: [0x%x].",
      v13);
  v14 = Windows::Compat::Appraiser::DataFile::GetMetadataParameterFromFile(&v35, v39, L"AppraiserMinDataVerForSdbUse");
  v5 = v14;
  if ( v14 < 0 )
  {
    LODWORD(v31) = v14;
    v30 = "Failed to check min data ver for sdb use: [0x%x].";
    v6 = -126;
    goto LABEL_5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x282u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
      "Failed to check min data ver for sdb use: [0x%x].",
      v14);
  v15 = Windows::Compat::Appraiser::WicaFactory::AppraiserVersion();
  v16 = _o__wtoi(v15);
  if ( v34 > v16 || v35 > *((_DWORD *)a2 + 3986) )
  {
    v33 = 0;
LABEL_56:
    v21 = 0;
    goto LABEL_57;
  }
  Windows::Compat::Appraiser::Utilities::GetAppraiserVersion(&v36);
  v5 = StringCchPrintfW(v42, 0x104u, L"MT_AppraiserTarget_%ls", *((_QWORD *)a2 + 1897));
  if ( v5 < 0 )
  {
    v6 = -107;
    goto LABEL_10;
  }
  v33 = 1;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x295u,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
      "Failed to print string: [0x%x].",
      v5);
  MapTableValueFromFile = Windows::Compat::Appraiser::DataFile::GetMapTableValueFromFile(
                            v38,
                            v17,
                            v42,
                            v39,
                            L"OsBuildNumber");
  if ( MapTableValueFromFile < 0 )
  {
    LODWORD(v31) = MapTableValueFromFile;
    if ( Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors() )
    {
      LODWORD(v29) = MapTableValueFromFile;
      v19 = 1;
    }
    else
    {
      v29 = 0;
      v19 = 0;
    }
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)v19,
      162,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
      v29,
      (int)"Failed to check target ver build number: [0x%x].",
      v31);
    goto LABEL_56;
  }
  v20 = _o__wtoi(v38);
  v21 = v36 == v20;
LABEL_57:
  v22 = *((_DWORD *)a2 + 3988);
  v23 = v37;
  v24 = v33 && v21 && v22 < v37;
  *((_BYTE *)a2 + 15152) = v24;
  if ( !v24 )
    return 1;
  LODWORD(v31) = v22;
  *(_DWORD *)((char *)a2 + 15169) = v22;
  Windows::Compat::Appraiser::WriteLog(
    0,
    199,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
    0,
    (int)"SDB will be replaced with inbox ADL's SDB.  Current SdbVer: [%d], New SdbVer: [%d].",
    v31,
    v23);
  v26 = Windows::Compat::Appraiser::SetupAppraiser::MergeInboxAdlSdb(v25, a2, *((const unsigned __int16 **)a2 + 1899));
  v5 = v26;
  if ( v26 < 0 )
  {
    LODWORD(v31) = v26;
    v30 = "Failed to merge ADL SDB: [0x%x].";
    v6 = -54;
    goto LABEL_5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x2CAu,
      "onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
      "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
      "Failed to merge ADL SDB: [0x%x].",
      v26);
  LODWORD(v32) = v23;
  LODWORD(v31) = v22;
  Windows::Compat::Appraiser::WriteLog(
    0,
    204,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\setup\\setupappraiser.cpp",
    "Windows::Compat::Appraiser::SetupAppraiser::TryReuseInboxAdlSdb",
    0,
    (int)"SDB was replaced with inbox ADL's SDB.  Previous SdbVer: [%d], Current SdbVer: [%d].",
    v31,
    v32);
  return 0;
}

```

## disassembly

```asm
0x18004608c  push    rbp
0x18004608e  push    rbx
0x18004608f  push    rsi
0x180046090  push    rdi
0x180046091  push    r12
0x180046093  push    r13
0x180046095  push    r14
0x180046097  push    r15
0x180046099  lea     rbp, [rsp-7C8h]
0x1800460a1  sub     rsp, 8C8h
0x1800460a8  mov     rax, cs:__security_cookie
0x1800460af  xor     rax, rsp
0x1800460b2  mov     [rbp+800h+var_50], rax
0x1800460b9  mov     r12, cs:?InboxDirectoryPathInputAlternateDataCab@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::InboxDirectoryPathInputAlternateDataCab
0x1800460c0  xor     edi, edi
0x1800460c2  mov     rcx, r12; pszPath
0x1800460c5  mov     [rsp+900h+var_8B4], edi
0x1800460c9  mov     r13, rdx
0x1800460cc  mov     [rsp+900h+var_8B8], edi
0x1800460d0  mov     [rsp+900h+var_8BC], edi
0x1800460d4  mov     [rsp+900h+var_8B0], edi
0x1800460d8  call    cs:__imp_PathFileExistsW
0x1800460de  test    eax, eax
0x1800460e0  jz      loc_18004665E
0x1800460e6  xor     r9d, r9d; bool
0x1800460e9  mov     r8, r12; unsigned __int16 *
0x1800460ec  xor     edx, edx; unsigned int *
0x1800460ee  xor     ecx, ecx; int *
0x1800460f0  call    ?VerifySignatureRecursive@Utilities@Appraiser@Compat@Windows@@SAJPEAJPEAKPEBG_N@Z; Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(long *,ulong *,ushort const *,bool)
0x1800460f5  test    eax, eax
0x1800460f7  js      loc_18004665E
0x1800460fd  mov     r9, [r13+3B58h]
0x180046104  lea     r8, aLsAppraiserInb; "%ls\\Appraiser_InboxAlternateData.cab"
0x18004610b  mov     edx, 104h; unsigned __int64
0x180046110  lea     rcx, [rbp+800h+NewFileName]; unsigned __int16 *
0x180046117  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004611c  lea     r15, aFailedToPrintS_1; "Failed to print string: [0x%x]."
0x180046123  mov     ebx, eax
0x180046125  test    eax, eax
0x180046127  jns     short loc_180046156
0x180046129  mov     dword ptr [rsp+900h+var_8D0], eax; char *
0x18004612d  lea     r9, aWindowsCompatA_607; "Windows::Compat::Appraiser::SetupApprai"...
0x180046134  mov     qword ptr [rsp+900h+var_8D8], r15; int
0x180046139  lea     r8, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x180046140  mov     edx, 25Ch; bool
0x180046145  lea     ecx, [rdi+1]; this
0x180046148  mov     dword ptr [rsp+900h+var_8E0], ebx; char *
0x18004614c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180046151  jmp     loc_180046663
0x180046156  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18004615c  lea     rsi, aWindowsCompatA_607; "Windows::Compat::Appraiser::SetupApprai"...
0x180046163  mov     edi, 1
0x180046168  lea     r14, aOnecoreBaseApp_72; "onecore\\base\\appcompat\\appraiser\\he"...
0x18004616f  and     eax, edi
0x180046171  test    al, al
0x180046173  jz      short loc_18004618C
0x180046175  mov     r9, r15; char *
0x180046178  mov     dword ptr [rsp+900h+var_8E0], ebx
0x18004617c  mov     r8, rsi; char *
0x18004617f  mov     rdx, r14; char *
0x180046182  mov     ecx, 25Ch; unsigned int
0x180046187  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18004618c  mov     r9, [r13+3B58h]
0x180046193  lea     r8, aLsInboxalterna_0; "%ls\\InboxAlternateData"
0x18004619a  mov     edx, 104h; unsigned __int64
0x18004619f  lea     rcx, [rbp+800h+var_680]; unsigned __int16 *
0x1800461a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800461ab  mov     ebx, eax
0x1800461ad  test    eax, eax
0x1800461af  jns     short loc_1800461CC
0x1800461b1  mov     edx, 262h
0x1800461b6  mov     dword ptr [rsp+900h+var_8D0], ebx
0x1800461ba  mov     qword ptr [rsp+900h+var_8D8], r15
0x1800461bf  mov     r8, r14
0x1800461c2  mov     r9, rsi
0x1800461c5  mov     ecx, edi
0x1800461c7  jmp     loc_180046148
0x1800461cc  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800461d2  and     eax, edi
0x1800461d4  test    al, al
0x1800461d6  jz      short loc_1800461EF
0x1800461d8  mov     r9, r15; char *
0x1800461db  mov     dword ptr [rsp+900h+var_8E0], ebx
0x1800461df  mov     r8, rsi; char *
0x1800461e2  mov     rdx, r14; char *
0x1800461e5  mov     ecx, 262h; unsigned int
0x1800461ea  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800461ef  xor     r8d, r8d; bFailIfExists
0x1800461f2  lea     rdx, [rbp+800h+NewFileName]; lpNewFileName
0x1800461f9  mov     rcx, r12; lpExistingFileName
0x1800461fc  call    cs:__imp_CopyFileW
0x180046202  test    eax, eax
0x180046204  jnz     short loc_180046245
0x180046206  call    cs:__imp_GetLastError
0x18004620c  mov     ebx, eax
0x18004620e  test    eax, eax
0x180046210  jle     short loc_18004621B
0x180046212  movzx   ebx, ax
0x180046215  or      ebx, 80070000h
0x18004621b  test    ebx, ebx
0x18004621d  mov     eax, 80004005h
0x180046222  cmovns  ebx, eax
0x180046225  call    cs:__imp_GetLastError
0x18004622b  mov     dword ptr [rsp+900h+var_8D0], eax
0x18004622f  mov     edx, 267h
0x180046234  lea     rax, aFailedToCopyFi_0; "Failed to copy file: [%d]."
0x18004623b  mov     qword ptr [rsp+900h+var_8D8], rax
0x180046240  jmp     loc_1800461BF
0x180046245  lea     rcx, [rbp+800h+var_680]; unsigned __int16 *
0x18004624c  call    ?EnsureDirectoryExists@Utilities@Appraiser@Compat@Windows@@SAJPEBG@Z; Windows::Compat::Appraiser::Utilities::EnsureDirectoryExists(ushort const *)
0x180046251  mov     ebx, eax
0x180046253  test    eax, eax
0x180046255  jns     short loc_180046271
0x180046257  lea     r9, aFailedToCheckC_0; "Failed to check/create directory: [0x%x"...
0x18004625e  mov     dword ptr [rsp+900h+var_8D0], eax
0x180046262  mov     qword ptr [rsp+900h+var_8D8], r9
0x180046267  mov     edx, 26Bh
0x18004626c  jmp     loc_1800461BF
0x180046271  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180046277  and     eax, edi
0x180046279  test    al, al
0x18004627b  jz      short loc_180046298
0x18004627d  lea     r9, aFailedToCheckC_0; "Failed to check/create directory: [0x%x"...
0x180046284  mov     dword ptr [rsp+900h+var_8E0], ebx
0x180046288  mov     r8, rsi; char *
0x18004628b  mov     rdx, r14; char *
0x18004628e  mov     ecx, 26Bh; unsigned int
0x180046293  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180046298  lea     rdx, [rbp+800h+var_680]; unsigned __int16 *
0x18004629f  lea     rcx, [rbp+800h+NewFileName]; lpFileName
0x1800462a6  call    ?DiagExtractCabinet@@YAJPEBG0P6AX0PEAX@Z1@Z; DiagExtractCabinet(ushort const *,ushort const *,void (*)(ushort const *,void *),void *)
0x1800462ab  mov     ebx, eax
0x1800462ad  test    eax, eax
0x1800462af  jns     short loc_1800462CB
0x1800462b1  lea     r9, aFailedToExtrac_8; "Failed to extract cab file: [0x%x]."
0x1800462b8  mov     dword ptr [rsp+900h+var_8D0], eax
0x1800462bc  mov     qword ptr [rsp+900h+var_8D8], r9
0x1800462c1  mov     edx, 26Eh
0x1800462c6  jmp     loc_1800461BF
0x1800462cb  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800462d1  and     eax, edi
0x1800462d3  test    al, al
0x1800462d5  jz      short loc_1800462F2
0x1800462d7  lea     r9, aFailedToExtrac_8; "Failed to extract cab file: [0x%x]."
0x1800462de  mov     dword ptr [rsp+900h+var_8E0], ebx
0x1800462e2  mov     r8, rsi; char *
0x1800462e5  mov     rdx, r14; char *
0x1800462e8  mov     ecx, 26Eh; unsigned int
0x1800462ed  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800462f2  mov     r12d, 104h
0x1800462f8  lea     r9, [rbp+800h+var_680]
0x1800462ff  mov     edx, r12d; unsigned __int64
0x180046302  lea     r8, aLsAppraiserDat; "%ls\\Appraiser_Data.ini"
0x180046309  lea     rcx, [rsp+900h+var_890]; unsigned __int16 *
0x18004630e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046313  mov     ebx, eax
0x180046315  test    eax, eax
0x180046317  jns     short loc_180046323
0x180046319  mov     edx, 274h
0x18004631e  jmp     loc_1800461B6
0x180046323  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180046329  and     eax, edi
0x18004632b  test    al, al
0x18004632d  jz      short loc_180046346
0x18004632f  mov     r9, r15; char *
0x180046332  mov     dword ptr [rsp+900h+var_8E0], ebx
0x180046336  mov     r8, rsi; char *
0x180046339  mov     rdx, r14; char *
0x18004633c  mov     ecx, 274h; unsigned int
0x180046341  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180046346  lea     r8, aAppraisersdbve; "AppraiserSdbVer"
0x18004634d  lea     rdx, [rsp+900h+var_890]; unsigned __int16 *
0x180046352  lea     rcx, [rsp+900h+var_8B0]; unsigned int *
0x180046357  call    ?GetMetadataParameterFromFile@DataFile@Appraiser@Compat@Windows@@SAJAEAKPEBG1@Z; Windows::Compat::Appraiser::DataFile::GetMetadataParameterFromFile(ulong &,ushort const *,ushort const *)
0x18004635c  mov     ebx, eax
0x18004635e  test    eax, eax
0x180046360  jns     short loc_18004637C
0x180046362  lea     r9, aFailedToCheckA; "Failed to check adl data path for sdb v"...
0x180046369  mov     dword ptr [rsp+900h+var_8D0], eax
0x18004636d  mov     qword ptr [rsp+900h+var_8D8], r9
0x180046372  mov     edx, 27Ch
0x180046377  jmp     loc_1800461BF
0x18004637c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180046382  and     eax, edi
0x180046384  test    al, al
0x180046386  jz      short loc_1800463A3
0x180046388  lea     r9, aFailedToCheckA; "Failed to check adl data path for sdb v"...
0x18004638f  mov     dword ptr [rsp+900h+var_8E0], ebx
0x180046393  mov     r8, rsi; char *
0x180046396  mov     rdx, r14; char *
0x180046399  mov     ecx, 27Ch; unsigned int
0x18004639e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800463a3  lea     r8, aAppraiserminco; "AppraiserMinCodeVerForSdbUse"
0x1800463aa  lea     rdx, [rsp+900h+var_890]; unsigned __int16 *
0x1800463af  lea     rcx, [rsp+900h+var_8BC]; unsigned int *
0x1800463b4  call    ?GetMetadataParameterFromFile@DataFile@Appraiser@Compat@Windows@@SAJAEAKPEBG1@Z; Windows::Compat::Appraiser::DataFile::GetMetadataParameterFromFile(ulong &,ushort const *,ushort const *)
0x1800463b9  mov     ebx, eax
0x1800463bb  test    eax, eax
0x1800463bd  jns     short loc_1800463D9
0x1800463bf  lea     r9, aFailedToCheckM_2; "Failed to check min code ver for sdb us"...
0x1800463c6  mov     dword ptr [rsp+900h+var_8D0], eax
0x1800463ca  mov     qword ptr [rsp+900h+var_8D8], r9
0x1800463cf  mov     edx, 27Fh
0x1800463d4  jmp     loc_1800461BF
0x1800463d9  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800463df  and     eax, edi
0x1800463e1  test    al, al
0x1800463e3  jz      short loc_180046400
0x1800463e5  lea     r9, aFailedToCheckM_2; "Failed to check min code ver for sdb us"...
0x1800463ec  mov     dword ptr [rsp+900h+var_8E0], ebx
0x1800463f0  mov     r8, rsi; char *
0x1800463f3  mov     rdx, r14; char *
0x1800463f6  mov     ecx, 27Fh; unsigned int
0x1800463fb  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180046400  lea     r8, aAppraiserminda; "AppraiserMinDataVerForSdbUse"
0x180046407  lea     rdx, [rsp+900h+var_890]; unsigned __int16 *
0x18004640c  lea     rcx, [rsp+900h+var_8B8]; unsigned int *
0x180046411  call    ?GetMetadataParameterFromFile@DataFile@Appraiser@Compat@Windows@@SAJAEAKPEBG1@Z; Windows::Compat::Appraiser::DataFile::GetMetadataParameterFromFile(ulong &,ushort const *,ushort const *)
0x180046416  mov     ebx, eax
0x180046418  test    eax, eax
0x18004641a  jns     short loc_180046436
0x18004641c  lea     r9, aFailedToCheckM_3; "Failed to check min data ver for sdb us"...
0x180046423  mov     dword ptr [rsp+900h+var_8D0], eax
0x180046427  mov     qword ptr [rsp+900h+var_8D8], r9
0x18004642c  mov     edx, 282h
0x180046431  jmp     loc_1800461BF
0x180046436  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18004643c  and     eax, edi
0x18004643e  test    al, al
0x180046440  jz      short loc_18004645D
0x180046442  lea     r9, aFailedToCheckM_3; "Failed to check min data ver for sdb us"...
0x180046449  mov     dword ptr [rsp+900h+var_8E0], ebx
0x18004644d  mov     r8, rsi; char *
0x180046450  mov     rdx, r14; char *
0x180046453  mov     ecx, 282h; unsigned int
0x180046458  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18004645d  call    ?AppraiserVersion@WicaFactory@Appraiser@Compat@Windows@@SAPEBGXZ; Windows::Compat::Appraiser::WicaFactory::AppraiserVersion(void)
0x180046462  mov     rcx, rax
0x180046465  call    cs:__imp__o__wtoi
0x18004646b  cmp     [rsp+900h+var_8BC], eax
0x18004646f  ja      loc_18004655F
0x180046475  mov     eax, [r13+3E48h]
0x18004647c  cmp     [rsp+900h+var_8B8], eax
0x180046480  ja      loc_18004655F
0x180046486  lea     rcx, [rsp+900h+var_8B4]; unsigned int *
0x18004648b  call    ?GetAppraiserVersion@Utilities@Appraiser@Compat@Windows@@SAXPEAK@Z; Windows::Compat::Appraiser::Utilities::GetAppraiserVersion(ulong *)
0x180046490  mov     r9, [r13+3B48h]
0x180046497  lea     r8, aMtAppraisertar_0; "MT_AppraiserTarget_%ls"
0x18004649e  mov     rdx, r12; unsigned __int64
0x1800464a1  lea     rcx, [rbp+800h+var_260]; unsigned __int16 *
0x1800464a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800464ad  mov     ebx, eax
0x1800464af  test    eax, eax
0x1800464b1  jns     short loc_1800464BD
0x1800464b3  mov     edx, 295h
0x1800464b8  jmp     loc_1800461B6
0x1800464bd  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800464c3  and     eax, edi
0x1800464c5  mov     [rsp+900h+var_8C0], dil
0x1800464ca  test    al, al
0x1800464cc  jz      short loc_1800464E5
0x1800464ce  mov     r9, r15; char *
0x1800464d1  mov     dword ptr [rsp+900h+var_8E0], ebx
0x1800464d5  mov     r8, rsi; char *
0x1800464d8  mov     rdx, r14; char *
0x1800464db  mov     ecx, 295h; unsigned int
0x1800464e0  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800464e5  lea     rax, aOsbuildnumber; "OsBuildNumber"
0x1800464ec  lea     r9, [rsp+900h+var_890]; unsigned __int16 *
0x1800464f1  mov     [rsp+900h+var_8E0], rax; unsigned __int16 *
0x1800464f6  lea     r8, [rbp+800h+var_260]; unsigned __int16 *
0x1800464fd  lea     rcx, [rsp+900h+var_8A8]; unsigned __int16 *
0x180046502  call    ?GetMapTableValueFromFile@DataFile@Appraiser@Compat@Windows@@SAJPEAG_KPEBG22@Z; Windows::Compat::Appraiser::DataFile::GetMapTableValueFromFile(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)
0x180046507  mov     ebx, eax
0x180046509  test    eax, eax
0x18004650b  jns     short loc_18004654B
0x18004650d  call    ?TreatWarningsAsErrors@AppraiserTestHooks@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors(void)
0x180046512  test    al, al
0x180046514  mov     dword ptr [rsp+900h+var_8D0], ebx; char *
0x180046518  lea     rax, aFailedToCheckT_0; "Failed to check target ver build number"...
0x18004651f  mov     r9, rsi; char *
0x180046522  mov     qword ptr [rsp+900h+var_8D8], rax; int
0x180046527  mov     r8, r14; unsigned int
0x18004652a  mov     edx, 2A2h; bool
0x18004652f  jz      short loc_180046539
0x180046531  mov     dword ptr [rsp+900h+var_8E0], ebx
0x180046535  mov     ecx, edi
0x180046537  jmp     short loc_180046544
0x180046539  mov     [rsp+900h+var_8E0], 0; char *
0x180046542  xor     ecx, ecx; this
0x180046544  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180046549  jmp     short loc_180046564
0x18004654b  lea     rcx, [rsp+900h+var_8A8]
0x180046550  call    cs:__imp__o__wtoi
0x180046556  cmp     [rsp+900h+var_8B4], eax
0x18004655a  setz    al
0x18004655d  jmp     short loc_180046566
0x18004655f  mov     [rsp+900h+var_8C0], 0
0x180046564  xor     al, al
0x180046566  cmp     [rsp+900h+var_8C0], 0
  ... truncated ...
```
