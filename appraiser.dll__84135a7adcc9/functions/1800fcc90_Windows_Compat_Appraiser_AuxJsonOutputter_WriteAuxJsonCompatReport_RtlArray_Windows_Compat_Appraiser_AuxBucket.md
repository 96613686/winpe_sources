# Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport(RtlArray<Windows::Compat::Appraiser::AuxBucket *> *)

- ea: `0x1800fcc90`
- end: `0x1800fd881`
- name: `?WriteAuxJsonCompatReport@AuxJsonOutputter@Appraiser@Compat@Windows@@AEAAJPEAV?$RtlArray@PEAUAuxBucket@Appraiser@Compat@Windows@@@@@Z`
- size: `3057`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800fae10`

## callees

- `0x180008570`
- `0x180011d94`
- `0x18002750c`
- `0x18002a778`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18008b0f0`
- `0x18009c120`
- `0x18009c19c`
- `0x18009c244`
- `0x18009c2e0`
- `0x18009c680`
- `0x1800f9ed0`
- `0x1800fa588`
- `0x1800fa640`
- `0x1800fa6f8`
- `0x1800fa868`
- `0x1800fc3f0`
- `0x1800fcc90`
- `0x1800fdb64`
- `0x1802174cc`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x1800fd604`
- `KERNEL32!GetFullPathNameW` at `0x1800fd626`
- `KERNEL32!GetFullPathNameW` at `0x1800fd604`
- `KERNEL32!GetFullPathNameW` at `0x1800fd626`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800fcec4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800fcec4`
- `KERNEL32!GetProcessHeap` at `0x1800fd2ba`
- `KERNEL32!GetProcessHeap` at `0x1800fd2ba`
- `KERNEL32!HeapAlloc` at `0x1800fd2c9`
- `KERNEL32!HeapAlloc` at `0x1800fd2c9`
- `KERNEL32!GetLastError` at `0x1800fd7bd`
- `KERNEL32!GetLastError` at `0x1800fd7d9`
- `KERNEL32!GetLastError` at `0x1800fd7bd`
- `KERNEL32!GetLastError` at `0x1800fd7d9`

## string_xrefs

- `0x1800fcd0d`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fcd3b`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fcd66`: `JsonSuccessfullyWritten`
- `0x1800fcd14`: `Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport`
- `0x1800fcd2f`: `Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport`
- `0x1800fccfd`: `Failed to create JsonCompatReport: [0x%x].`
- `0x1800fcd48`: `Failed to create JsonCompatReport: [0x%x].`
- `0x1800fcf46`: `AuxJsonOutputFileCreationTime`
- `0x1800fd0ae`: `AuxJsonOutputFileCreationTime`
- `0x1800fce12`: `JsonVersion`
- `0x1800fcd7d`: `Failed to create JsonPair: [0x%x].`
- `0x1800fcd94`: `Failed to create JsonPair: [0x%x].`
- `0x1800fd12e`: `Failed to create JsonPair: [0x%x].`
- `0x1800fd145`: `Failed to create JsonPair: [0x%x].`
- `0x1800fd046`: `Writing AuxJson file creation time to registry failed: [0x%x].`
- `0x1800fcf70`: `Failed to create file creation time value: [0x%x].`
- `0x1800fcf96`: `Failed to create file creation time value: [0x%x].`
- `0x1800fd2fa`: `Failed to create JsonValue from CompatSectionObj: [0x%x].`
- `0x1800fd3f3`: `Failed to create JsonValue from CompatSectionObj: [0x%x].`
- `0x1800fd29f`: `Failed to create JsonBucket from AuxBucket: [0x%x].`
- `0x1800fd404`: `Failed to create JsonBucket from AuxBucket: [0x%x].`
- `0x1800fd1c9`: `Failed to create JsonValueList: [0x%x].`
- `0x1800fd1f2`: `Failed to create JsonValueList: [0x%x].`
- `0x1800fd114`: `JsonCreationTime`
- `0x1800fd5b4`: `Failed to add user read permissions to final Json file: [0x%x].`
- `0x1800fd5da`: `Failed to add user read permissions to final Json file: [0x%x].`
- `0x1800fd54e`: `Failed to Write JSON to file %ls: [0x%x].`
- `0x1800fd58a`: `Failed to Write JSON to file %ls: [0x%x].`
- `0x1800fd488`: `CompatSections`
- `0x1800fd3a1`: `CompatSectionCount`
- `0x1800fd6e8`: `Writing new AuxJson file path to registry failed: [0x%x].`
- `0x1800fd665`: `Failed to create file location value: [0x%x].`
- `0x1800fd68b`: `Failed to create file location value: [0x%x].`
- `0x1800fd63d`: `AuxJsonOutputFilePath`
- `0x1800fd753`: `AuxJsonOutputFilePath`
- `0x1800fd7fd`: `Failed to get full json file path: [0x%x].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport(
        __int64 a1,
        unsigned __int64 *a2)
{
  int v3; // eax
  signed int v4; // edi
  char v5; // dl
  const char *v6; // rax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  struct _FILETIME v10; // rbx
  int v11; // eax
  int v12; // eax
  unsigned int v13; // edx
  int PersistedLocation; // eax
  HKEY v15; // r9
  int v16; // eax
  HKEY v17; // r9
  int v18; // eax
  unsigned __int64 v19; // r12
  int v20; // eax
  int v21; // eax
  double v22; // xmm6_8
  unsigned __int64 *v23; // r10
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // rax
  _QWORD *v26; // rdx
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rcx
  HANDLE ProcessHeap; // rax
  struct JsonValue *v30; // rax
  _DWORD **v31; // rax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  __int64 v36; // r13
  char *v37; // rbx
  int v38; // eax
  int FileUserReadable; // eax
  int v40; // eax
  HKEY v41; // r9
  __int64 v42; // r12
  __int64 v43; // rdx
  int v44; // eax
  HKEY v45; // r9
  int v46; // eax
  signed int v47; // eax
  signed int LastError; // eax
  const char *lpSubKey; // [rsp+28h] [rbp-E0h]
  const char *v51; // [rsp+30h] [rbp-D8h]
  char *v52; // [rsp+38h] [rbp-D0h]
  int v53; // [rsp+40h] [rbp-C8h]
  struct JsonKeyValuePair *v54; // [rsp+48h] [rbp-C0h] BYREF
  BYTE Data[8]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v56; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v57; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v58; // [rsp+68h] [rbp-A0h] BYREF
  struct JsonValue *v59; // [rsp+70h] [rbp-98h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 *v61; // [rsp+80h] [rbp-88h]
  __int64 v62; // [rsp+88h] [rbp-80h]
  unsigned __int16 v63[32]; // [rsp+98h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+D8h] [rbp-30h] BYREF
  WCHAR SubKey[264]; // [rsp+2E8h] [rbp+1E0h] BYREF
  unsigned __int16 v66[264]; // [rsp+4F8h] [rbp+3F0h] BYREF

  v62 = a1;
  v59 = 0;
  v57 = 0;
  v54 = 0;
  v58 = 0;
  v56 = 0;
  v61 = a2;
  v3 = CreateJsonObjectAlloc(&v56);
  v4 = v3;
  if ( v3 < 0 )
  {
    LODWORD(v52) = v3;
    v51 = "Failed to create JsonCompatReport: [0x%x].";
    v5 = -115;
LABEL_136:
    LODWORD(lpSubKey) = v4;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v5,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      lpSubKey,
      (int)v51,
      v52);
    goto LABEL_137;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x38Du,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Failed to create JsonCompatReport: [0x%x].",
      v3);
  v4 = CreateJsonPairBooleanAlloc(&v54, L"JsonSuccessfullyWritten", 1);
  if ( v4 < 0 )
  {
    v6 = "Failed to create JsonPair: [0x%x].";
    v5 = -108;
    goto LABEL_135;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x394u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Failed to create JsonPair: [0x%x].",
      v4);
  v7 = RtlArray<JsonValue *>::Append(v56, &v54);
  v4 = v7;
  if ( v7 < 0 )
  {
    LODWORD(v52) = v7;
    v5 = -105;
    v51 = "RtlArray Append failed: [0x%x].";
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x397u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "RtlArray Append failed: [0x%x].",
      v7);
  v54 = 0;
  v8 = CreateJsonPairNumberAlloc(&v54, L"JsonVersion", 4.0);
  v4 = v8;
  if ( v8 < 0 )
  {
    LODWORD(v52) = v8;
    v5 = -97;
    v51 = "Failed to create JsonPair: [0x%x].";
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x39Fu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Failed to create JsonPair: [0x%x].",
      v8);
  v9 = RtlArray<JsonValue *>::Append(v56, &v54);
  v4 = v9;
  if ( v9 < 0 )
  {
    LODWORD(v52) = v9;
    v5 = -94;
    v51 = "RtlArray Append failed: [0x%x].";
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x3A2u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "RtlArray Append failed: [0x%x].",
      v9);
  v54 = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(struct _FILETIME *)Data = SystemTimeAsFileTime;
  v10 = SystemTimeAsFileTime;
  v11 = StringCchPrintfW(v63, 0x20u, L"%llu", SystemTimeAsFileTime);
  v4 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v52) = v11;
    v51 = "Failed to print time into string [0x%x].";
    v5 = -83;
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x3ADu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Failed to print time into string [0x%x].",
      v11);
  v12 = StringCchPrintfW(v66, 0x104u, L"%ls_%ls", L"AuxJsonOutputFileCreationTime", *(_QWORD *)(a1 + 1072));
  v4 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v52) = v12;
    v51 = "Failed to create file creation time value: [0x%x].";
    v5 = -76;
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x3B4u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Failed to create file creation time value: [0x%x].",
      v12);
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(
                        SubKey,
                        v13,
                        L"Appraiser",
                        Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
                        1);
  v4 = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    LODWORD(v52) = PersistedLocation;
    v51 = "Failed to get persisted reg location: [0x%x].";
    v5 = -73;
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x3B7u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Failed to get persisted reg location: [0x%x].",
      PersistedLocation);
  *(struct _FILETIME *)Data = v10;
  v16 = Windows::Compat::Shared::Registry::WriteValue(Data, 8u, 0xBu, v15, SubKey, v66);
  v4 = v16;
  if ( v16 < 0 )
  {
    LODWORD(v52) = v16;
    v5 = -70;
    v51 = "Writing AuxJson file creation time to registry failed: [0x%x].";
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x3BAu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Writing AuxJson file creation time to registry failed: [0x%x].",
      v16);
  if ( !wcscmp_0(L"TH2", *(const wchar_t **)(v62 + 1072)) )
  {
    *(struct _FILETIME *)Data = v10;
    v18 = Windows::Compat::Shared::Registry::WriteValue(Data, 8u, 0xBu, v17, SubKey, L"AuxJsonOutputFileCreationTime");
    v4 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v52) = v18;
      v5 = -61;
      v51 = "Writing AuxJson file creation time to registry failed: [0x%x].";
      goto LABEL_136;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x3C3u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
        "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
        "Writing AuxJson file creation time to registry failed: [0x%x].",
        v18);
  }
  v19 = 0;
  v4 = CreateJsonPairStringAlloc(&v54, L"JsonCreationTime", v63);
  if ( v4 < 0 )
  {
    v6 = "Failed to create JsonPair: [0x%x].";
    v5 = -57;
    goto LABEL_135;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x3C7u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Failed to create JsonPair: [0x%x].",
      v4);
  v20 = RtlArray<JsonValue *>::Append(v56, &v54);
  v4 = v20;
  if ( v20 < 0 )
  {
    LODWORD(v52) = v20;
    v5 = -54;
    v51 = "RtlArray Append failed: [0x%x].";
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x3CAu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "RtlArray Append failed: [0x%x].",
      v20);
  v54 = 0;
  v21 = CreateJsonObjectAlloc(&v58);
  v4 = v21;
  if ( v21 < 0 )
  {
    LODWORD(v52) = v21;
    v51 = "Failed to create JsonValueList: [0x%x].";
    v5 = -46;
    goto LABEL_136;
  }
  v22 = 0.0;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x3D2u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Failed to create JsonValueList: [0x%x].",
      v21);
  v23 = v61;
  v24 = v61[2];
  if ( v24 )
  {
    do
    {
      v25 = 0;
      if ( v19 < v24 )
      {
        if ( !is_mul_ok(v23[1], v19) || (v25 = v23[5] + v23[1] * v19, v25 < v23[5]) )
          v25 = 0;
      }
      if ( *(_QWORD *)(*(_QWORD *)v25 + 32LL) )
      {
        v57 = 0;
        v26 = 0;
        if ( v19 < v24 )
        {
          v27 = v23[1] * v19;
          if ( !is_mul_ok(v23[1], v19) || (v28 = v23[5], v26 = (_QWORD *)(v27 + v28), v27 + v28 < v28) )
            v26 = 0;
        }
        v4 = Windows::Compat::Appraiser::AuxJsonOutputter::CreateJsonObjectFromAuxBucketAlloc(&v57, *v26, v24, v24);
        if ( v4 < 0 )
        {
          v6 = "Failed to create JsonBucket from AuxBucket: [0x%x].";
          v5 = -30;
          goto LABEL_135;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x3E2u,
            "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
            "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
            "Failed to create JsonBucket from AuxBucket: [0x%x].",
            v4);
        ProcessHeap = GetProcessHeap();
        v30 = (struct JsonValue *)HeapAlloc(ProcessHeap, 0, 0x10u);
        if ( !v30 )
        {
          v4 = -2147024882;
          v6 = "Failed to create JsonValue from CompatSectionObj: [0x%x].";
          v5 = -27;
          goto LABEL_135;
        }
        *((_QWORD *)v30 + 1) = v57;
        *(_DWORD *)v30 = 5;
        v59 = v30;
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x3E5u,
            "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
            "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
            "Failed to create JsonValue from CompatSectionObj: [0x%x].",
            0);
        v57 = 0;
        v4 = RtlArray<JsonValue *>::Append(v58, &v59);
        if ( v4 < 0 )
        {
          LODWORD(v52) = v4;
          v5 = -23;
          v51 = "RtlArray Append failed: [0x%x].";
          goto LABEL_136;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x3E9u,
            "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
            "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
            "RtlArray Append failed: [0x%x].",
            v4);
        v23 = v61;
        v31 = 0;
        v22 = v22 + 1.0;
        v59 = 0;
        v24 = v61[2];
        if ( v19 < v24 )
        {
          if ( !is_mul_ok(v61[1], v19) || (v31 = (_DWORD **)(v61[5] + v61[1] * v19), (unsigned __int64)v31 < v61[5]) )
            v31 = 0;
        }
        if ( **v31 == 6 )
          break;
      }
      ++v19;
    }
    while ( v19 < v24 );
  }
  v32 = CreateJsonPairNumberAlloc(&v54, L"CompatSectionCount", v22);
  v4 = v32;
  if ( v32 < 0 )
  {
    LODWORD(v52) = v32;
    v5 = -2;
    v51 = "Failed to create JsonPair: [0x%x].";
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x3FEu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Failed to create JsonPair: [0x%x].",
      v32);
  v33 = RtlArray<JsonValue *>::Append(v56, &v54);
  v4 = v33;
  if ( v33 < 0 )
  {
    LODWORD(v52) = v33;
    v5 = 1;
    v51 = "RtlArray Append failed: [0x%x].";
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x401u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "RtlArray Append failed: [0x%x].",
      v33);
  v54 = 0;
  v34 = CreateJsonPairArrayAllocOwns(&v54, L"CompatSections", v58);
  v4 = v34;
  if ( v34 < 0 )
  {
    LODWORD(v52) = v34;
    v5 = 9;
    v51 = "Failed to create JsonPair: [0x%x].";
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x409u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Failed to create JsonPair: [0x%x].",
      v34);
  v58 = 0;
  v35 = RtlArray<JsonValue *>::Append(v56, &v54);
  v4 = v35;
  if ( v35 < 0 )
  {
    LODWORD(v52) = v35;
    v5 = 13;
    v51 = "RtlArray Append failed: [0x%x].";
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x40Du,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "RtlArray Append failed: [0x%x].",
      v35);
  v36 = v62;
  v54 = 0;
  v37 = (char *)(v62 + 16);
  v38 = WriteJsonObjectToFile(v56, v62 + 16);
  v4 = v38;
  if ( v38 < 0 )
  {
    v53 = v38;
    LODWORD(lpSubKey) = v38;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      21,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      lpSubKey,
      (int)"Failed to Write JSON to file %ls: [0x%x].",
      v37,
      v53);
    goto LABEL_137;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x415u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Failed to Write JSON to file %ls: [0x%x].",
      (const wchar_t *)v37,
      v38);
  FileUserReadable = Windows::Compat::Appraiser::AuxJsonOutputter::MakeFileUserReadable(v37);
  v4 = FileUserReadable;
  if ( FileUserReadable < 0 )
  {
    LODWORD(v52) = FileUserReadable;
    v51 = "Failed to add user read permissions to final Json file: [0x%x].";
    v5 = 28;
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x41Cu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Failed to add user read permissions to final Json file: [0x%x].",
      FileUserReadable);
  if ( GetFullPathNameW((LPCWSTR)v37, 0x104u, Buffer, 0) - 1 > 0x102 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = 36;
LABEL_132:
    if ( v4 >= 0 )
      v4 = -2147467259;
    v6 = "Failed to get full json file path: [0x%x].";
LABEL_135:
    LODWORD(v52) = v4;
    LODWORD(v51) = (_DWORD)v6;
    goto LABEL_136;
  }
  if ( GetFullPathNameW((LPCWSTR)v37, 0x104u, Buffer, 0) - 1 > 0x102 )
  {
    v47 = GetLastError();
    v4 = v47;
    if ( v47 > 0 )
      v4 = (unsigned __int16)v47 | 0x80070000;
    v5 = 42;
    goto LABEL_132;
  }
  v40 = StringCchPrintfW(v66, 0x104u, L"%ls_%ls", L"AuxJsonOutputFilePath", *(_QWORD *)(v36 + 1072));
  v4 = v40;
  if ( v40 < 0 )
  {
    LODWORD(v52) = v40;
    v51 = "Failed to create file location value: [0x%x].";
    v5 = 50;
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x432u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Failed to create file location value: [0x%x].",
      v40);
  v42 = -1;
  v43 = -1;
  do
    ++v43;
  while ( Buffer[v43] );
  v44 = Windows::Compat::Shared::Registry::WriteValue((BYTE *)Buffer, 2 * (int)v43 + 2, 1u, v41, SubKey, v66);
  v4 = v44;
  if ( v44 < 0 )
  {
    LODWORD(v52) = v44;
    v5 = 53;
    v51 = "Writing new AuxJson file path to registry failed: [0x%x].";
    goto LABEL_136;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x435u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
      "Writing new AuxJson file path to registry failed: [0x%x].",
      v44);
  if ( !wcscmp_0(L"TH2", *(const wchar_t **)(v36 + 1072)) )
  {
    do
      ++v42;
    while ( Buffer[v42] );
    v46 = Windows::Compat::Shared::Registry::WriteValue(
            (BYTE *)Buffer,
            2 * (int)v42 + 2,
            1u,
            v45,
            SubKey,
            L"AuxJsonOutputFilePath");
    v4 = v46;
    if ( v46 < 0 )
    {
      LODWORD(v52) = v46;
      v5 = 62;
      v51 = "Writing new AuxJson file path to registry failed: [0x%x].";
      goto LABEL_136;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x43Eu,
        "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
        "Windows::Compat::Appraiser::AuxJsonOutputter::WriteAuxJsonCompatReport",
        "Writing new AuxJson file path to registry failed: [0x%x].",
        v46);
  }
  v4 = 0;
LABEL_137:
  CleanupJsonObject(&v56);
  CleanupJsonObject(&v57);
  CleanupJsonKeyValuePair(&v54);
  CleanupJsonValue(&v59);
  CleanupJsonValueList(&v58);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800fcc90  mov     rax, rsp
0x1800fcc93  mov     [rax+18h], rbx
0x1800fcc97  push    rbp
0x1800fcc98  push    rsi
0x1800fcc99  push    rdi
0x1800fcc9a  push    r12
0x1800fcc9c  push    r13
0x1800fcc9e  push    r14
0x1800fcca0  push    r15
0x1800fcca2  lea     rbp, [rax-658h]
0x1800fcca9  sub     rsp, 720h
0x1800fccb0  movaps  xmmword ptr [rax-48h], xmm6
0x1800fccb4  mov     rax, cs:__security_cookie
0x1800fccbb  xor     rax, rsp
0x1800fccbe  mov     [rbp+650h+var_50], rax
0x1800fccc5  xor     r13d, r13d
0x1800fccc8  mov     [rbp+650h+var_6D0], rcx
0x1800fcccc  mov     r12, rcx
0x1800fcccf  mov     [rsp+750h+var_6E8], r13
0x1800fccd4  lea     rcx, [rsp+750h+var_700]
0x1800fccd9  mov     [rsp+750h+var_6F8], r13
0x1800fccde  mov     [rsp+750h+var_710], r13
0x1800fcce3  mov     [rsp+750h+var_6F0], r13
0x1800fcce8  mov     [rsp+750h+var_700], r13
0x1800fcced  mov     [rsp+750h+var_6D8], rdx
0x1800fccf2  call    ?CreateJsonObjectAlloc@@YAJPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; CreateJsonObjectAlloc(RtlArray<JsonKeyValuePair *> * *)
0x1800fccf7  mov     edi, eax
0x1800fccf9  test    eax, eax
0x1800fccfb  jns     short loc_1800FCD29
0x1800fccfd  lea     r9, aFailedToCreate_11; "Failed to create JsonCompatReport: [0x%"...
0x1800fcd04  mov     dword ptr [rsp+750h+var_720], eax
0x1800fcd08  mov     [rsp+750h+var_728], r9
0x1800fcd0d  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800fcd14  lea     r9, aWindowsCompatA_429; "Windows::Compat::Appraiser::AuxJsonOutp"...
0x1800fcd1b  mov     edx, 38Dh
0x1800fcd20  lea     ecx, [r13+1]
0x1800fcd24  jmp     loc_1800FD815
0x1800fcd29  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fcd2f  lea     r14, aWindowsCompatA_429; "Windows::Compat::Appraiser::AuxJsonOutp"...
0x1800fcd36  mov     esi, 1
0x1800fcd3b  lea     r15, aOnecoreBaseApp_62; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800fcd42  and     eax, esi
0x1800fcd44  test    al, al
0x1800fcd46  jz      short loc_1800FCD63
0x1800fcd48  lea     r9, aFailedToCreate_11; "Failed to create JsonCompatReport: [0x%"...
0x1800fcd4f  mov     dword ptr [rsp+750h+lpSubKey], edi
0x1800fcd53  mov     r8, r14; char *
0x1800fcd56  mov     rdx, r15; char *
0x1800fcd59  mov     ecx, 38Dh; unsigned int
0x1800fcd5e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fcd63  mov     r8b, sil; bool
0x1800fcd66  lea     rdx, aJsonsuccessful; "JsonSuccessfullyWritten"
0x1800fcd6d  lea     rcx, [rsp+750h+var_710]; struct JsonKeyValuePair **
0x1800fcd72  call    ?CreateJsonPairBooleanAlloc@@YAJPEAPEAUJsonKeyValuePair@@PEBG_N@Z; CreateJsonPairBooleanAlloc(JsonKeyValuePair * *,ushort const *,bool)
0x1800fcd77  mov     edi, eax
0x1800fcd79  test    eax, eax
0x1800fcd7b  jns     short loc_1800FCD8E
0x1800fcd7d  lea     rax, aFailedToCreate_18; "Failed to create JsonPair: [0x%x]."
0x1800fcd84  mov     edx, 394h
0x1800fcd89  jmp     loc_1800FD804
0x1800fcd8e  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fcd94  lea     rbx, aFailedToCreate_18; "Failed to create JsonPair: [0x%x]."
0x1800fcd9b  and     eax, esi
0x1800fcd9d  test    al, al
0x1800fcd9f  jz      short loc_1800FCDB8
0x1800fcda1  mov     r9, rbx; char *
0x1800fcda4  mov     dword ptr [rsp+750h+lpSubKey], edi
0x1800fcda8  mov     r8, r14; char *
0x1800fcdab  mov     rdx, r15; char *
0x1800fcdae  mov     ecx, 394h; unsigned int
0x1800fcdb3  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fcdb8  mov     rcx, [rsp+750h+var_700]
0x1800fcdbd  lea     rdx, [rsp+750h+var_710]
0x1800fcdc2  call    ?Append@?$RtlArray@PEAUJsonValue@@@@QEAAJAEBQEAUJsonValue@@@Z; RtlArray<JsonValue *>::Append(JsonValue * const &)
0x1800fcdc7  lea     r13, aRtlarrayAppend_2; "RtlArray Append failed: [0x%x]."
0x1800fcdce  mov     edi, eax
0x1800fcdd0  test    eax, eax
0x1800fcdd2  jns     short loc_1800FCDE7
0x1800fcdd4  mov     dword ptr [rsp+750h+var_720], eax
0x1800fcdd8  mov     edx, 397h
0x1800fcddd  mov     [rsp+750h+var_728], r13
0x1800fcde2  jmp     loc_1800FD80D
0x1800fcde7  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fcded  and     eax, esi
0x1800fcdef  test    al, al
0x1800fcdf1  jz      short loc_1800FCE0A
0x1800fcdf3  mov     r9, r13; char *
0x1800fcdf6  mov     dword ptr [rsp+750h+lpSubKey], edi
0x1800fcdfa  mov     r8, r14; char *
0x1800fcdfd  mov     rdx, r15; char *
0x1800fce00  mov     ecx, 397h; unsigned int
0x1800fce05  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fce0a  movsd   xmm2, cs:__real@4010000000000000; double
0x1800fce12  lea     rdx, aJsonversion; "JsonVersion"
0x1800fce19  lea     rcx, [rsp+750h+var_710]; struct JsonKeyValuePair **
0x1800fce1e  mov     [rsp+750h+var_710], 0
0x1800fce27  call    ?CreateJsonPairNumberAlloc@@YAJPEAPEAUJsonKeyValuePair@@PEBGN@Z; CreateJsonPairNumberAlloc(JsonKeyValuePair * *,ushort const *,double)
0x1800fce2c  mov     edi, eax
0x1800fce2e  test    eax, eax
0x1800fce30  jns     short loc_1800FCE45
0x1800fce32  mov     dword ptr [rsp+750h+var_720], eax
0x1800fce36  mov     edx, 39Fh
0x1800fce3b  mov     [rsp+750h+var_728], rbx
0x1800fce40  jmp     loc_1800FD80D
0x1800fce45  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fce4b  and     eax, esi
0x1800fce4d  test    al, al
0x1800fce4f  jz      short loc_1800FCE68
0x1800fce51  mov     r9, rbx; char *
0x1800fce54  mov     dword ptr [rsp+750h+lpSubKey], edi
0x1800fce58  mov     r8, r14; char *
0x1800fce5b  mov     rdx, r15; char *
0x1800fce5e  mov     ecx, 39Fh; unsigned int
0x1800fce63  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fce68  mov     rcx, [rsp+750h+var_700]
0x1800fce6d  lea     rdx, [rsp+750h+var_710]
0x1800fce72  call    ?Append@?$RtlArray@PEAUJsonValue@@@@QEAAJAEBQEAUJsonValue@@@Z; RtlArray<JsonValue *>::Append(JsonValue * const &)
0x1800fce77  xor     ebx, ebx
0x1800fce79  mov     edi, eax
0x1800fce7b  test    eax, eax
0x1800fce7d  jns     short loc_1800FCE92
0x1800fce7f  mov     dword ptr [rsp+750h+var_720], eax
0x1800fce83  mov     edx, 3A2h
0x1800fce88  mov     [rsp+750h+var_728], r13
0x1800fce8d  jmp     loc_1800FD80D
0x1800fce92  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fce98  and     eax, esi
0x1800fce9a  test    al, al
0x1800fce9c  jz      short loc_1800FCEB5
0x1800fce9e  mov     r9, r13; char *
0x1800fcea1  mov     dword ptr [rsp+750h+lpSubKey], edi
0x1800fcea5  mov     r8, r14; char *
0x1800fcea8  mov     rdx, r15; char *
0x1800fceab  mov     ecx, 3A2h; unsigned int
0x1800fceb0  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fceb5  lea     rcx, [rsp+750h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800fceba  mov     [rsp+750h+var_710], rbx
0x1800fcebf  mov     qword ptr [rsp+750h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1800fcec4  call    cs:__imp_GetSystemTimeAsFileTime
0x1800fceca  mov     eax, [rsp+750h+SystemTimeAsFileTime.dwHighDateTime]
0x1800fcece  lea     r8, aLlu_1; "%llu"
0x1800fced5  mov     dword ptr [rsp+750h+Data+4], eax
0x1800fced9  lea     rcx, [rbp+650h+var_6C0]; unsigned __int16 *
0x1800fcedd  mov     eax, [rsp+750h+SystemTimeAsFileTime.dwLowDateTime]
0x1800fcee1  mov     edx, 20h ; ' '; unsigned __int64
0x1800fcee6  mov     dword ptr [rsp+750h+Data], eax
0x1800fceea  mov     rbx, qword ptr [rsp+750h+Data]
0x1800fceef  mov     r9, rbx
0x1800fcef2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fcef7  mov     edi, eax
0x1800fcef9  test    eax, eax
0x1800fcefb  jns     short loc_1800FCF17
0x1800fcefd  lea     r9, aFailedToPrintT_4; "Failed to print time into string [0x%x]"...
0x1800fcf04  mov     dword ptr [rsp+750h+var_720], eax
0x1800fcf08  mov     [rsp+750h+var_728], r9
0x1800fcf0d  mov     edx, 3ADh
0x1800fcf12  jmp     loc_1800FD80D
0x1800fcf17  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fcf1d  and     eax, esi
0x1800fcf1f  test    al, al
0x1800fcf21  jz      short loc_1800FCF3E
0x1800fcf23  lea     r9, aFailedToPrintT_4; "Failed to print time into string [0x%x]"...
0x1800fcf2a  mov     dword ptr [rsp+750h+lpSubKey], edi
0x1800fcf2e  mov     r8, r14; char *
0x1800fcf31  mov     rdx, r15; char *
0x1800fcf34  mov     ecx, 3ADh; unsigned int
0x1800fcf39  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fcf3e  mov     rax, [r12+430h]
0x1800fcf46  lea     r9, aAuxjsonoutputf_0; "AuxJsonOutputFileCreationTime"
0x1800fcf4d  lea     r8, aLsLs_1; "%ls_%ls"
0x1800fcf54  mov     [rsp+750h+lpSubKey], rax
0x1800fcf59  mov     edx, 104h; unsigned __int64
0x1800fcf5e  lea     rcx, [rbp+650h+var_260]; unsigned __int16 *
0x1800fcf65  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fcf6a  mov     edi, eax
0x1800fcf6c  test    eax, eax
0x1800fcf6e  jns     short loc_1800FCF8A
0x1800fcf70  lea     r9, aFailedToCreate_31; "Failed to create file creation time val"...
0x1800fcf77  mov     dword ptr [rsp+750h+var_720], eax
0x1800fcf7b  mov     [rsp+750h+var_728], r9
0x1800fcf80  mov     edx, 3B4h
0x1800fcf85  jmp     loc_1800FD80D
0x1800fcf8a  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fcf90  and     eax, esi
0x1800fcf92  test    al, al
0x1800fcf94  jz      short loc_1800FCFB1
0x1800fcf96  lea     r9, aFailedToCreate_31; "Failed to create file creation time val"...
0x1800fcf9d  mov     dword ptr [rsp+750h+lpSubKey], edi
0x1800fcfa1  mov     r8, r14; char *
0x1800fcfa4  mov     rdx, r15; char *
0x1800fcfa7  mov     ecx, 3B4h; unsigned int
0x1800fcfac  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fcfb1  mov     r9, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; unsigned __int16 *
0x1800fcfb8  lea     r8, aAppraiser_0; "Appraiser"
0x1800fcfbf  lea     rcx, [rbp+650h+SubKey]; unsigned __int16 *
0x1800fcfc6  mov     dword ptr [rsp+750h+lpSubKey], esi; int
0x1800fcfca  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x1800fcfcf  mov     edi, eax
0x1800fcfd1  test    eax, eax
0x1800fcfd3  jns     short loc_1800FCFEF
0x1800fcfd5  lea     r9, aFailedToGetPer; "Failed to get persisted reg location: ["...
0x1800fcfdc  mov     dword ptr [rsp+750h+var_720], eax
0x1800fcfe0  mov     [rsp+750h+var_728], r9
0x1800fcfe5  mov     edx, 3B7h
0x1800fcfea  jmp     loc_1800FD80D
0x1800fcfef  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fcff5  and     eax, esi
0x1800fcff7  test    al, al
0x1800fcff9  jz      short loc_1800FD016
0x1800fcffb  lea     r9, aFailedToGetPer; "Failed to get persisted reg location: ["...
0x1800fd002  mov     dword ptr [rsp+750h+lpSubKey], edi
0x1800fd006  mov     r8, r14; char *
0x1800fd009  mov     rdx, r15; char *
0x1800fd00c  mov     ecx, 3B7h; unsigned int
0x1800fd011  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fd016  mov     edx, 8; cbData
0x1800fd01b  mov     qword ptr [rsp+750h+Data], rbx
0x1800fd020  lea     rax, [rbp+650h+var_260]
0x1800fd027  mov     [rsp+750h+var_728], rax; unsigned __int16 *
0x1800fd02c  lea     rcx, [rsp+750h+Data]; lpData
0x1800fd031  lea     rax, [rbp+650h+SubKey]
0x1800fd038  lea     r8d, [rdx+3]; dwType
0x1800fd03c  mov     [rsp+750h+lpSubKey], rax; lpSubKey
0x1800fd041  call    ?WriteValue@Registry@Shared@Compat@Windows@@SAJPEBE_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::WriteValue(uchar const *,unsigned __int64,ulong,HKEY__ *,ushort const *,ushort const *)
0x1800fd046  lea     r12, aWritingAuxjson; "Writing AuxJson file creation time to r"...
0x1800fd04d  mov     edi, eax
0x1800fd04f  test    eax, eax
0x1800fd051  jns     short loc_1800FD066
0x1800fd053  mov     dword ptr [rsp+750h+var_720], eax
0x1800fd057  mov     edx, 3BAh
0x1800fd05c  mov     [rsp+750h+var_728], r12
0x1800fd061  jmp     loc_1800FD80D
0x1800fd066  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fd06c  and     eax, esi
0x1800fd06e  test    al, al
0x1800fd070  jz      short loc_1800FD089
0x1800fd072  mov     r9, r12; char *
0x1800fd075  mov     dword ptr [rsp+750h+lpSubKey], edi
0x1800fd079  mov     r8, r14; char *
0x1800fd07c  mov     rdx, r15; char *
0x1800fd07f  mov     ecx, 3BAh; unsigned int
0x1800fd084  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fd089  mov     rdx, [rbp+650h+var_6D0]
0x1800fd08d  lea     rcx, aTh2; "TH2"
0x1800fd094  mov     rdx, [rdx+430h]; String2
0x1800fd09b  call    wcscmp_0
0x1800fd0a0  test    eax, eax
0x1800fd0a2  jnz     short loc_1800FD110
0x1800fd0a4  mov     edx, 8; cbData
0x1800fd0a9  mov     qword ptr [rsp+750h+Data], rbx
0x1800fd0ae  lea     rax, aAuxjsonoutputf_0; "AuxJsonOutputFileCreationTime"
0x1800fd0b5  mov     [rsp+750h+var_728], rax; unsigned __int16 *
0x1800fd0ba  lea     rcx, [rsp+750h+Data]; lpData
0x1800fd0bf  lea     rax, [rbp+650h+SubKey]
0x1800fd0c6  lea     r8d, [rdx+3]; dwType
0x1800fd0ca  mov     [rsp+750h+lpSubKey], rax; lpSubKey
0x1800fd0cf  call    ?WriteValue@Registry@Shared@Compat@Windows@@SAJPEBE_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::WriteValue(uchar const *,unsigned __int64,ulong,HKEY__ *,ushort const *,ushort const *)
0x1800fd0d4  mov     edi, eax
0x1800fd0d6  test    eax, eax
0x1800fd0d8  jns     short loc_1800FD0ED
0x1800fd0da  mov     dword ptr [rsp+750h+var_720], eax
0x1800fd0de  mov     edx, 3C3h
0x1800fd0e3  mov     [rsp+750h+var_728], r12
0x1800fd0e8  jmp     loc_1800FD80D
0x1800fd0ed  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fd0f3  and     eax, esi
0x1800fd0f5  test    al, al
0x1800fd0f7  jz      short loc_1800FD110
0x1800fd0f9  mov     r9, r12; char *
0x1800fd0fc  mov     dword ptr [rsp+750h+lpSubKey], edi
0x1800fd100  mov     r8, r14; char *
0x1800fd103  mov     rdx, r15; char *
0x1800fd106  mov     ecx, 3C3h; unsigned int
0x1800fd10b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fd110  lea     r8, [rbp+650h+var_6C0]; unsigned __int16 *
0x1800fd114  lea     rdx, aJsoncreationti; "JsonCreationTime"
0x1800fd11b  lea     rcx, [rsp+750h+var_710]; struct JsonKeyValuePair **
0x1800fd120  call    ?CreateJsonPairStringAlloc@@YAJPEAPEAUJsonKeyValuePair@@PEBG1@Z; CreateJsonPairStringAlloc(JsonKeyValuePair * *,ushort const *,ushort const *)
0x1800fd125  xor     r12d, r12d
0x1800fd128  mov     edi, eax
0x1800fd12a  test    eax, eax
0x1800fd12c  jns     short loc_1800FD13F
0x1800fd12e  lea     rax, aFailedToCreate_18; "Failed to create JsonPair: [0x%x]."
0x1800fd135  mov     edx, 3C7h
0x1800fd13a  jmp     loc_1800FD804
0x1800fd13f  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fd145  lea     rbx, aFailedToCreate_18; "Failed to create JsonPair: [0x%x]."
0x1800fd14c  and     eax, esi
0x1800fd14e  test    al, al
0x1800fd150  jz      short loc_1800FD169
0x1800fd152  mov     r9, rbx; char *
0x1800fd155  mov     dword ptr [rsp+750h+lpSubKey], edi
0x1800fd159  mov     r8, r14; char *
0x1800fd15c  mov     rdx, r15; char *
0x1800fd15f  mov     ecx, 3C7h; unsigned int
0x1800fd164  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fd169  mov     rcx, [rsp+750h+var_700]
0x1800fd16e  lea     rdx, [rsp+750h+var_710]
0x1800fd173  call    ?Append@?$RtlArray@PEAUJsonValue@@@@QEAAJAEBQEAUJsonValue@@@Z; RtlArray<JsonValue *>::Append(JsonValue * const &)
0x1800fd178  mov     edi, eax
  ... truncated ...
```
