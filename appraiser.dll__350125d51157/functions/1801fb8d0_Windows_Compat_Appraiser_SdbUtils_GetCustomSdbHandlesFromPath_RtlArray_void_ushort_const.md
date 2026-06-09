# Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath(RtlArray<void *> &,ushort const *)

- ea: `0x1801fb8d0`
- end: `0x1801fbe76`
- name: `?GetCustomSdbHandlesFromPath@SdbUtils@Appraiser@Compat@Windows@@SAJAEAV?$RtlArray@PEAX@@PEBG@Z`
- size: `1446`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180047688`
- `0x180064f4c`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x18002a778`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180087108`
- `0x1800a5d88`
- `0x1801abfd8`
- `0x1801b0af0`
- `0x1801fb8d0`
- `0x180215f48`
- `0x180215fd0`

## import_xrefs

- `KERNEL32!FindClose` at `0x1801fbcb2`
- `KERNEL32!FindClose` at `0x1801fbcb2`
- `KERNEL32!FindNextFileW` at `0x1801fbc8d`
- `KERNEL32!FindNextFileW` at `0x1801fbc8d`
- `KERNEL32!FindFirstFileW` at `0x1801fbac9`
- `KERNEL32!FindFirstFileW` at `0x1801fbac9`
- `KERNEL32!GetLastError` at `0x1801fbad8`
- `KERNEL32!GetLastError` at `0x1801fbae7`
- `KERNEL32!GetLastError` at `0x1801fbaf6`
- `KERNEL32!GetLastError` at `0x1801fbb15`
- `KERNEL32!GetLastError` at `0x1801fbad8`
- `KERNEL32!GetLastError` at `0x1801fbae7`
- `KERNEL32!GetLastError` at `0x1801fbaf6`
- `KERNEL32!GetLastError` at `0x1801fbb15`
- `SHLWAPI!PathFileExistsW` at `0x1801fb9ad`
- `SHLWAPI!PathFileExistsW` at `0x1801fbc10`
- `SHLWAPI!PathFileExistsW` at `0x1801fb9ad`
- `SHLWAPI!PathFileExistsW` at `0x1801fbc10`

## string_xrefs

- `0x1801fba7f`: `Failed to expand search directory: [0x%x].`
- `0x1801fbaa2`: `Failed to expand search directory: [0x%x].`
- `0x1801fba07`: `Failed to copy expanded path: [0x%x].`
- `0x1801fbbee`: `Failed to combine filename to delete: [0x%x].`
- `0x1801fbe3b`: `Failed to combine filename to delete: [0x%x].`
- `0x1801fb947`: `onecore\base\appcompat\appraiser\datasource\sdbutils.cpp`
- `0x1801fb97e`: `onecore\base\appcompat\appraiser\datasource\sdbutils.cpp`
- `0x1801fb94e`: `Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath`
- `0x1801fb972`: `Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath`
- `0x1801fb937`: `Failed to expand directory: [0x%x].`
- `0x1801fb98b`: `Failed to expand directory: [0x%x].`
- `0x1801fbb24`: `Failed to find file in directory: [%d]`
- `0x1801fbdcc`: `Using custom Sdb path at %ls`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath(
        __int64 a1,
        const unsigned __int16 *a2)
{
  unsigned int v3; // edx
  int v4; // eax
  signed int v5; // ebx
  char v6; // dl
  WCHAR *v7; // rcx
  __int64 v8; // rdx
  WCHAR *v9; // r8
  __int64 v10; // rax
  WCHAR *v11; // rcx
  HRESULT v12; // eax
  HANDLE FirstFileW; // r13
  signed int LastError; // eax
  __int64 v15; // rax
  WCHAR *v16; // rcx
  __int64 v17; // rdx
  WCHAR *v18; // r8
  WCHAR *v19; // rcx
  signed int v20; // r15d
  char v22; // dl
  char *v23; // [rsp+20h] [rbp-E0h]
  const char *v24; // [rsp+28h] [rbp-D8h]
  const char *v25; // [rsp+28h] [rbp-D8h]
  char *v26; // [rsp+30h] [rbp-D0h]
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 inited; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v31[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR pszPath[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR FileName[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  v29 = a1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v27 = 0;
  v4 = Windows::Compat::Appraiser::Utilities::ExpandDirectory(pszPath, v3, a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    LODWORD(v26) = v4;
    v24 = "Failed to expand directory: [0x%x].";
    v6 = 54;
LABEL_3:
    LODWORD(v23) = v5;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v6,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath",
      v23,
      (int)v24,
      v26);
    return (unsigned int)v5;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xD36u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath",
      "Failed to expand directory: [0x%x].",
      v4);
  if ( !PathFileExistsW(pszPath) )
    return 1;
  v7 = pszPath;
  v8 = 260;
  v9 = FileName;
  v10 = 2147483646;
  do
  {
    if ( !v10 )
      break;
    if ( !*v7 )
      break;
    *v9++ = *v7++;
    --v10;
    --v8;
  }
  while ( v8 );
  v11 = v9 - 1;
  v5 = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v11 = v9;
  *v11 = 0;
  if ( !v8 )
  {
    LODWORD(v26) = -2147024774;
    v6 = 63;
    v24 = "Failed to copy expanded path: [0x%x].";
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xD3Fu,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath",
      "Failed to copy expanded path: [0x%x].",
      v8 == 0 ? 0x8007007A : 0);
  v12 = PathCchAppend(FileName, 0x104u, L"*.sdb");
  v5 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v26) = v12;
    v24 = "Failed to expand search directory: [0x%x].";
    v6 = 66;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xD42u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath",
      "Failed to expand search directory: [0x%x].",
      v12);
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( GetLastError() != 2 && GetLastError() != 3 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
      LODWORD(v26) = GetLastError();
      v6 = 77;
      v24 = "Failed to find file in directory: [%d]";
      goto LABEL_3;
    }
    return 1;
  }
  while ( 1 )
  {
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      goto LABEL_49;
    v15 = 2147483646;
    v16 = pszPath;
    v17 = 260;
    v18 = v31;
    do
    {
      if ( !v15 )
        break;
      if ( !*v16 )
        break;
      *v18++ = *v16++;
      --v15;
      --v17;
    }
    while ( v17 );
    v19 = v18 - 1;
    v5 = v17 == 0 ? 0x8007007A : 0;
    if ( v17 )
      v19 = v18;
    *v19 = 0;
    if ( !v17 )
      break;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xD58u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath",
        "Failed to copy expanded path: [0x%x].",
        v17 == 0 ? 0x8007007A : 0);
    v5 = PathCchAppend(v31, 0x104u, FindFileData.cFileName);
    if ( v5 < 0 )
    {
      LODWORD(v26) = v5;
      v25 = "Failed to combine filename to delete: [0x%x].";
      v22 = 91;
      goto LABEL_68;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xD5Bu,
        "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath",
        "Failed to combine filename to delete: [0x%x].",
        v5);
    if ( PathFileExistsW(v31) )
    {
      v20 = SdbFileInfoGet(v31, &v27);
      if ( v20 )
      {
        if ( Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors() )
        {
          if ( v20 > 0 )
            v20 = (unsigned __int16)v20 | 0x80070000;
          LODWORD(v23) = v20;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            105,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
            "Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath",
            v23,
            (int)"SdbFileInfoGet failed for SDB database [%ls].",
            (const char *)v31);
        }
        else
        {
          Windows::Compat::Appraiser::WriteLog(
            0,
            105,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
            "Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath",
            0,
            (int)"SdbFileInfoGet failed for SDB database [%ls].",
            (const char *)v31);
        }
      }
      else if ( *(_DWORD *)(v27 + 40) == 420420 )
      {
        inited = SdbInitDatabase(3, v31);
        if ( !inited )
        {
          LODWORD(v23) = -2138546174;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            115,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
            "Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath",
            v23,
            (int)"Error initializing SDB database : [%ls].",
            (const char *)v31);
          goto LABEL_51;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xD73u,
            "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
            "Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath",
            "Error initializing SDB database : [%ls].",
            v31);
        v5 = RtlArray<JsonValue *>::Append(v29, &inited);
        if ( v5 < 0 )
        {
          LODWORD(v26) = v5;
          v25 = "RtlArray Append failed: [0x%x].";
          v22 = 117;
          goto LABEL_68;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xD75u,
            "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
            "Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath",
            "RtlArray Append failed: [0x%x].",
            v5);
        Windows::Compat::Appraiser::WriteLog(
          0,
          119,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
          "Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath",
          0,
          (int)"Using custom Sdb path at %ls",
          (const char *)v31);
        SdbFileInfoFree(&v27);
        v27 = 0;
      }
    }
LABEL_49:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      v5 = 0;
      goto LABEL_51;
    }
  }
  LODWORD(v26) = -2147024774;
  v22 = 88;
  v25 = "Failed to copy expanded path: [0x%x].";
LABEL_68:
  LODWORD(v23) = v5;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v22,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
    "Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath",
    v23,
    (int)v25,
    v26);
LABEL_51:
  if ( v27 )
    SdbFileInfoFree(&v27);
  FindClose(FirstFileW);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1801fb8d0  mov     [rsp-8+arg_10], rbx
0x1801fb8d5  push    rbp
0x1801fb8d6  push    rsi
0x1801fb8d7  push    rdi
0x1801fb8d8  push    r12
0x1801fb8da  push    r13
0x1801fb8dc  push    r14
0x1801fb8de  push    r15
0x1801fb8e0  lea     rbp, [rsp-7F0h]
0x1801fb8e8  sub     rsp, 8F0h
0x1801fb8ef  mov     rax, cs:__security_cookie
0x1801fb8f6  xor     rax, rsp
0x1801fb8f9  mov     [rbp+820h+var_40], rax
0x1801fb900  mov     rbx, rdx
0x1801fb903  mov     [rsp+920h+var_8D0], rcx
0x1801fb908  xor     edx, edx; Val
0x1801fb90a  lea     rcx, [rsp+920h+FindFileData]; void *
0x1801fb90f  mov     r8d, 250h; Size
0x1801fb915  call    memset_0
0x1801fb91a  xor     r15d, r15d
0x1801fb91d  lea     rcx, [rbp+820h+pszPath]; lpDst
0x1801fb924  mov     r8, rbx; unsigned __int16 *
0x1801fb927  mov     [rsp+920h+var_8E0], r15
0x1801fb92c  call    ?ExpandDirectory@Utilities@Appraiser@Compat@Windows@@SAJPEAGKPEBG@Z; Windows::Compat::Appraiser::Utilities::ExpandDirectory(ushort *,ulong,ushort const *)
0x1801fb931  mov     ebx, eax
0x1801fb933  test    eax, eax
0x1801fb935  jns     short loc_1801FB96C
0x1801fb937  lea     r9, aFailedToExpand_5; "Failed to expand directory: [0x%x]."
0x1801fb93e  mov     dword ptr [rsp+920h+var_8F0], eax; char *
0x1801fb942  mov     qword ptr [rsp+920h+var_8F8], r9; int
0x1801fb947  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801fb94e  lea     r9, aWindowsCompatA_282; "Windows::Compat::Appraiser::SdbUtils::G"...
0x1801fb955  mov     edx, 0D36h; bool
0x1801fb95a  lea     ecx, [r15+1]; this
0x1801fb95e  mov     dword ptr [rsp+920h+var_900], ebx; char *
0x1801fb962  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801fb967  jmp     loc_1801FBCB8
0x1801fb96c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801fb972  lea     rsi, aWindowsCompatA_282; "Windows::Compat::Appraiser::SdbUtils::G"...
0x1801fb979  mov     edi, 1
0x1801fb97e  lea     r14, aOnecoreBaseApp_63; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801fb985  and     eax, edi
0x1801fb987  test    al, al
0x1801fb989  jz      short loc_1801FB9A6
0x1801fb98b  lea     r9, aFailedToExpand_5; "Failed to expand directory: [0x%x]."
0x1801fb992  mov     dword ptr [rsp+920h+var_900], ebx
0x1801fb996  mov     r8, rsi; char *
0x1801fb999  mov     rdx, r14; char *
0x1801fb99c  mov     ecx, 0D36h; unsigned int
0x1801fb9a1  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801fb9a6  lea     rcx, [rbp+820h+pszPath]; pszPath
0x1801fb9ad  call    cs:__imp_PathFileExistsW
0x1801fb9b3  test    eax, eax
0x1801fb9b5  jnz     short loc_1801FB9BE
0x1801fb9b7  mov     ebx, edi
0x1801fb9b9  jmp     loc_1801FBCB8
0x1801fb9be  mov     r13d, 104h
0x1801fb9c4  lea     rcx, [rbp+820h+pszPath]
0x1801fb9cb  mov     edx, r13d
0x1801fb9ce  lea     r8, [rbp+820h+FileName]
0x1801fb9d5  mov     eax, 7FFFFFFEh
0x1801fb9da  test    rax, rax
0x1801fb9dd  jz      short loc_1801FB9FD
0x1801fb9df  movzx   r9d, word ptr [rcx]
0x1801fb9e3  test    r9w, r9w
0x1801fb9e7  jz      short loc_1801FB9FD
0x1801fb9e9  mov     [r8], r9w
0x1801fb9ed  add     rcx, 2
0x1801fb9f1  add     r8, 2
0x1801fb9f5  sub     rax, rdi
0x1801fb9f8  sub     rdx, rdi
0x1801fb9fb  jnz     short loc_1801FB9DA
0x1801fb9fd  mov     rax, rdx
0x1801fba00  lea     rcx, [r8-2]
0x1801fba04  neg     rax
0x1801fba07  lea     r12, aFailedToCopyEx_0; "Failed to copy expanded path: [0x%x]."
0x1801fba0e  sbb     ebx, ebx
0x1801fba10  not     ebx
0x1801fba12  and     ebx, 8007007Ah
0x1801fba18  test    rdx, rdx
0x1801fba1b  cmovnz  rcx, r8
0x1801fba1f  mov     [rcx], r15w
0x1801fba23  jnz     short loc_1801FBA40
0x1801fba25  mov     dword ptr [rsp+920h+var_8F0], ebx
0x1801fba29  mov     edx, 0D3Fh
0x1801fba2e  mov     qword ptr [rsp+920h+var_8F8], r12
0x1801fba33  mov     r9, rsi
0x1801fba36  mov     r8, r14
0x1801fba39  mov     ecx, edi
0x1801fba3b  jmp     loc_1801FB95E
0x1801fba40  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801fba46  and     eax, edi
0x1801fba48  test    al, al
0x1801fba4a  jz      short loc_1801FBA63
0x1801fba4c  mov     r9, r12; char *
0x1801fba4f  mov     dword ptr [rsp+920h+var_900], ebx
0x1801fba53  mov     r8, rsi; char *
0x1801fba56  mov     rdx, r14; char *
0x1801fba59  mov     ecx, 0D3Fh; unsigned int
0x1801fba5e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801fba63  lea     r8, aSdb; "*.sdb"
0x1801fba6a  mov     rdx, r13; cchPath
0x1801fba6d  lea     rcx, [rbp+820h+FileName]; pszPath
0x1801fba74  call    PathCchAppend
0x1801fba79  mov     ebx, eax
0x1801fba7b  test    eax, eax
0x1801fba7d  jns     short loc_1801FBA96
0x1801fba7f  lea     r9, aFailedToExpand_0; "Failed to expand search directory: [0x%"...
0x1801fba86  mov     dword ptr [rsp+920h+var_8F0], eax
0x1801fba8a  mov     qword ptr [rsp+920h+var_8F8], r9
0x1801fba8f  mov     edx, 0D42h
0x1801fba94  jmp     short loc_1801FBA33
0x1801fba96  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801fba9c  and     eax, edi
0x1801fba9e  test    al, al
0x1801fbaa0  jz      short loc_1801FBABD
0x1801fbaa2  lea     r9, aFailedToExpand_0; "Failed to expand search directory: [0x%"...
0x1801fbaa9  mov     dword ptr [rsp+920h+var_900], ebx
0x1801fbaad  mov     r8, rsi; char *
0x1801fbab0  mov     rdx, r14; char *
0x1801fbab3  mov     ecx, 0D42h; unsigned int
0x1801fbab8  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801fbabd  lea     rdx, [rsp+920h+FindFileData]; lpFindFileData
0x1801fbac2  lea     rcx, [rbp+820h+FileName]; lpFileName
0x1801fbac9  call    cs:__imp_FindFirstFileW
0x1801fbacf  mov     r13, rax
0x1801fbad2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801fbad6  jnz     short loc_1801FBB35
0x1801fbad8  call    cs:__imp_GetLastError
0x1801fbade  cmp     eax, 2
0x1801fbae1  jz      loc_1801FB9B7
0x1801fbae7  call    cs:__imp_GetLastError
0x1801fbaed  cmp     eax, 3
0x1801fbaf0  jz      loc_1801FB9B7
0x1801fbaf6  call    cs:__imp_GetLastError
0x1801fbafc  mov     ebx, eax
0x1801fbafe  test    eax, eax
0x1801fbb00  jle     short loc_1801FBB0B
0x1801fbb02  movzx   ebx, ax
0x1801fbb05  or      ebx, 80070000h
0x1801fbb0b  test    ebx, ebx
0x1801fbb0d  mov     eax, 80004005h
0x1801fbb12  cmovns  ebx, eax
0x1801fbb15  call    cs:__imp_GetLastError
0x1801fbb1b  mov     dword ptr [rsp+920h+var_8F0], eax
0x1801fbb1f  mov     edx, 0D4Dh
0x1801fbb24  lea     rax, aFailedToFindFi_0; "Failed to find file in directory: [%d]"
0x1801fbb2b  mov     qword ptr [rsp+920h+var_8F8], rax
0x1801fbb30  jmp     loc_1801FBA33
0x1801fbb35  test    byte ptr [rsp+920h+FindFileData.dwFileAttributes], 10h
0x1801fbb3a  jnz     loc_1801FBC85
0x1801fbb40  mov     eax, 7FFFFFFEh
0x1801fbb45  lea     rcx, [rbp+820h+pszPath]
0x1801fbb4c  mov     edx, 104h
0x1801fbb51  lea     r8, [rbp+820h+var_670]
0x1801fbb58  test    rax, rax
0x1801fbb5b  jz      short loc_1801FBB7B
0x1801fbb5d  movzx   r9d, word ptr [rcx]
0x1801fbb61  test    r9w, r9w
0x1801fbb65  jz      short loc_1801FBB7B
0x1801fbb67  mov     [r8], r9w
0x1801fbb6b  add     rcx, 2
0x1801fbb6f  add     r8, 2
0x1801fbb73  sub     rax, rdi
0x1801fbb76  sub     rdx, rdi
0x1801fbb79  jnz     short loc_1801FBB58
0x1801fbb7b  mov     rax, rdx
0x1801fbb7e  lea     rcx, [r8-2]
0x1801fbb82  neg     rax
0x1801fbb85  sbb     ebx, ebx
0x1801fbb87  not     ebx
0x1801fbb89  and     ebx, 8007007Ah
0x1801fbb8f  test    rdx, rdx
0x1801fbb92  cmovnz  rcx, r8
0x1801fbb96  mov     [rcx], r15w
0x1801fbb9a  jz      loc_1801FBE52
0x1801fbba0  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801fbba6  and     eax, edi
0x1801fbba8  test    al, al
0x1801fbbaa  jz      short loc_1801FBBC3
0x1801fbbac  mov     r9, r12; char *
0x1801fbbaf  mov     dword ptr [rsp+920h+var_900], ebx
0x1801fbbb3  mov     r8, rsi; char *
0x1801fbbb6  mov     rdx, r14; char *
0x1801fbbb9  mov     ecx, 0D58h; unsigned int
0x1801fbbbe  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801fbbc3  lea     r8, [rbp+820h+FindFileData.cFileName]; pszMore
0x1801fbbc7  mov     edx, 104h; cchPath
0x1801fbbcc  lea     rcx, [rbp+820h+var_670]; pszPath
0x1801fbbd3  call    PathCchAppend
0x1801fbbd8  mov     ebx, eax
0x1801fbbda  test    eax, eax
0x1801fbbdc  js      loc_1801FBE3B
0x1801fbbe2  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801fbbe8  and     eax, edi
0x1801fbbea  test    al, al
0x1801fbbec  jz      short loc_1801FBC09
0x1801fbbee  lea     r9, aFailedToCombin_3; "Failed to combine filename to delete: ["...
0x1801fbbf5  mov     dword ptr [rsp+920h+var_900], ebx
0x1801fbbf9  mov     r8, rsi; char *
0x1801fbbfc  mov     rdx, r14; char *
0x1801fbbff  mov     ecx, 0D5Bh; unsigned int
0x1801fbc04  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801fbc09  lea     rcx, [rbp+820h+var_670]; pszPath
0x1801fbc10  call    cs:__imp_PathFileExistsW
0x1801fbc16  test    eax, eax
0x1801fbc18  jz      short loc_1801FBC85
0x1801fbc1a  lea     rdx, [rsp+920h+var_8E0]
0x1801fbc1f  lea     rcx, [rbp+820h+var_670]
0x1801fbc26  call    SdbFileInfoGet
0x1801fbc2b  mov     r15d, eax
0x1801fbc2e  test    eax, eax
0x1801fbc30  jz      loc_1801FBD1B
0x1801fbc36  call    ?TreatWarningsAsErrors@AppraiserTestHooks@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors(void)
0x1801fbc3b  test    al, al
0x1801fbc3d  jz      loc_1801FBCE4
0x1801fbc43  test    r15d, r15d
0x1801fbc46  jle     short loc_1801FBC53
0x1801fbc48  movzx   r15d, r15w
0x1801fbc4c  or      r15d, 80070000h
0x1801fbc53  lea     rax, [rbp+820h+var_670]
0x1801fbc5a  mov     r9, rsi; char *
0x1801fbc5d  mov     [rsp+920h+var_8F0], rax; char *
0x1801fbc62  mov     r8, r14; unsigned int
0x1801fbc65  lea     rax, aSdbfileinfoget; "SdbFileInfoGet failed for SDB database "...
0x1801fbc6c  mov     edx, 0D69h; bool
0x1801fbc71  mov     qword ptr [rsp+920h+var_8F8], rax; int
0x1801fbc76  mov     ecx, edi; this
0x1801fbc78  mov     dword ptr [rsp+920h+var_900], r15d; char *
0x1801fbc7d  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801fbc82  xor     r15d, r15d
0x1801fbc85  lea     rdx, [rsp+920h+FindFileData]; lpFindFileData
0x1801fbc8a  mov     rcx, r13; hFindFile
0x1801fbc8d  call    cs:__imp_FindNextFileW
0x1801fbc93  test    eax, eax
0x1801fbc95  jnz     loc_1801FBB35
0x1801fbc9b  mov     ebx, r15d
0x1801fbc9e  cmp     [rsp+920h+var_8E0], r15
0x1801fbca3  jz      short loc_1801FBCAF
0x1801fbca5  lea     rcx, [rsp+920h+var_8E0]
0x1801fbcaa  call    SdbFileInfoFree
0x1801fbcaf  mov     rcx, r13; hFindFile
0x1801fbcb2  call    cs:__imp_FindClose
0x1801fbcb8  mov     eax, ebx
0x1801fbcba  mov     rcx, [rbp+820h+var_40]
0x1801fbcc1  xor     rcx, rsp; StackCookie
0x1801fbcc4  call    __security_check_cookie
0x1801fbcc9  mov     rbx, [rsp+920h+arg_10]
0x1801fbcd1  add     rsp, 8F0h
0x1801fbcd8  pop     r15
0x1801fbcda  pop     r14
0x1801fbcdc  pop     r13
0x1801fbcde  pop     r12
0x1801fbce0  pop     rdi
0x1801fbce1  pop     rsi
0x1801fbce2  pop     rbp
0x1801fbce3  retn
0x1801fbce4  lea     rax, [rbp+820h+var_670]
0x1801fbceb  xor     r15d, r15d
0x1801fbcee  mov     [rsp+920h+var_8F0], rax; char *
0x1801fbcf3  mov     r9, rsi; char *
0x1801fbcf6  lea     rax, aSdbfileinfoget; "SdbFileInfoGet failed for SDB database "...
0x1801fbcfd  mov     r8, r14; unsigned int
0x1801fbd00  mov     qword ptr [rsp+920h+var_8F8], rax; int
0x1801fbd05  mov     edx, 0D69h; bool
0x1801fbd0a  xor     ecx, ecx; this
0x1801fbd0c  mov     [rsp+920h+var_900], r15; char *
0x1801fbd11  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801fbd16  jmp     loc_1801FBC85
0x1801fbd1b  mov     rax, [rsp+920h+var_8E0]
0x1801fbd20  cmp     dword ptr [rax+28h], 66A44h
0x1801fbd27  jnz     loc_1801FBC82
0x1801fbd2d  lea     rdx, [rbp+820h+var_670]
0x1801fbd34  mov     ecx, 3
0x1801fbd39  call    SdbInitDatabase
0x1801fbd3e  xor     r15d, r15d
0x1801fbd41  mov     [rsp+920h+var_8D8], rax
0x1801fbd46  test    rax, rax
0x1801fbd49  jz      loc_1801FBE14
0x1801fbd4f  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801fbd55  and     eax, edi
0x1801fbd57  test    al, al
0x1801fbd59  jz      short loc_1801FBD7E
0x1801fbd5b  lea     rax, [rbp+820h+var_670]
0x1801fbd62  mov     r8, rsi; char *
0x1801fbd65  lea     r9, aErrorInitializ_30; "Error initializing SDB database : [%ls]"...
0x1801fbd6c  mov     [rsp+920h+var_900], rax
0x1801fbd71  mov     rdx, r14; char *
0x1801fbd74  mov     ecx, 0D73h; unsigned int
0x1801fbd79  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801fbd7e  mov     rcx, [rsp+920h+var_8D0]
0x1801fbd83  lea     rdx, [rsp+920h+var_8D8]
0x1801fbd88  call    ?Append@?$RtlArray@PEAUJsonValue@@@@QEAAJAEBQEAUJsonValue@@@Z; RtlArray<JsonValue *>::Append(JsonValue * const &)
0x1801fbd8d  mov     ebx, eax
0x1801fbd8f  test    eax, eax
0x1801fbd91  js      short loc_1801FBDFD
0x1801fbd93  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801fbd99  and     eax, edi
0x1801fbd9b  test    al, al
0x1801fbd9d  jz      short loc_1801FBDBA
  ... truncated ...
```
