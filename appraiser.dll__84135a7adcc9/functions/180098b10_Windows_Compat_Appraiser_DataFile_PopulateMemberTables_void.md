# Windows::Compat::Appraiser::DataFile::PopulateMemberTables(void)

- ea: `0x180098b10`
- end: `0x18009936c`
- name: `?PopulateMemberTables@DataFile@Appraiser@Compat@Windows@@AEAAJXZ`
- size: `2140`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::DataFile *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180097f20`

## callees

- `0x18002a778`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180096ef0`
- `0x180098820`
- `0x180098b10`
- `0x18009aa18`
- `0x1802174cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180098ce6`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180098ce6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180098ea6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180098ebb`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180098ef7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180099126`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180098ea6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180098ebb`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180098ef7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180099126`
- `KERNEL32!GetProcessHeap` at `0x180098b37`
- `KERNEL32!GetProcessHeap` at `0x180098b49`
- `KERNEL32!GetProcessHeap` at `0x180098b37`
- `KERNEL32!GetProcessHeap` at `0x180098b49`
- `KERNEL32!HeapFree` at `0x180099349`
- `KERNEL32!HeapFree` at `0x180099349`

## string_xrefs

- `0x180098eed`: `_CompatMarker_`
- `0x180098b92`: `onecore\base\appcompat\appraiser\helpers\datafile.cpp`
- `0x180098da2`: `onecore\base\appcompat\appraiser\helpers\datafile.cpp`
- `0x180098f38`: `onecore\base\appcompat\appraiser\helpers\datafile.cpp`
- `0x180099027`: `onecore\base\appcompat\appraiser\helpers\datafile.cpp`
- `0x18009907f`: `onecore\base\appcompat\appraiser\helpers\datafile.cpp`
- `0x1800990b8`: `onecore\base\appcompat\appraiser\helpers\datafile.cpp`
- `0x180099167`: `onecore\base\appcompat\appraiser\helpers\datafile.cpp`
- `0x1800991f3`: `onecore\base\appcompat\appraiser\helpers\datafile.cpp`
- `0x18009925f`: `onecore\base\appcompat\appraiser\helpers\datafile.cpp`
- `0x180099325`: `onecore\base\appcompat\appraiser\helpers\datafile.cpp`
- `0x180098b8b`: `Windows::Compat::Appraiser::DataFile::PopulateMemberTables`
- `0x180098da9`: `Windows::Compat::Appraiser::DataFile::PopulateMemberTables`
- `0x180098f31`: `Windows::Compat::Appraiser::DataFile::PopulateMemberTables`
- `0x18009902e`: `Windows::Compat::Appraiser::DataFile::PopulateMemberTables`
- `0x180099078`: `Windows::Compat::Appraiser::DataFile::PopulateMemberTables`
- `0x1800990b1`: `Windows::Compat::Appraiser::DataFile::PopulateMemberTables`
- `0x180099160`: `Windows::Compat::Appraiser::DataFile::PopulateMemberTables`
- `0x1800991ec`: `Windows::Compat::Appraiser::DataFile::PopulateMemberTables`
- `0x180099258`: `Windows::Compat::Appraiser::DataFile::PopulateMemberTables`
- `0x18009931e`: `Windows::Compat::Appraiser::DataFile::PopulateMemberTables`
- `0x180098c5c`: `LT_NonFatalComponentTypes`
- `0x18009911f`: `_CompatIndicator_`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Appraiser::DataFile::PopulateMemberTables(
        Windows::Compat::Appraiser::DataFile *this)
{
  unsigned __int64 v2; // r14
  const wchar_t **v3; // r15
  unsigned __int64 v4; // r12
  unsigned __int64 *v5; // r13
  unsigned __int64 v6; // rax
  unsigned __int64 i; // rsi
  __int64 *v8; // rdi
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  __int64 v11; // rdi
  _QWORD *v12; // rax
  int v13; // eax
  unsigned __int64 v14; // rax
  unsigned __int64 j; // rsi
  const wchar_t **v16; // rdi
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rcx
  const wchar_t *v19; // rdi
  const char *v20; // rax
  char v21; // dl
  int v22; // edi
  unsigned int v23; // ecx
  unsigned __int64 v24; // rsi
  unsigned __int64 v25; // r8
  const wchar_t **v26; // rax
  const wchar_t **v27; // rax
  const wchar_t *v28; // r9
  char **v29; // rax
  char *v30; // rax
  signed __int64 v31; // r9
  int v32; // ecx
  int v33; // edx
  char v34; // dl
  char v35; // dl
  const char *v36; // rax
  unsigned __int64 v37; // rax
  unsigned __int64 k; // rsi
  const wchar_t **v39; // rdx
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rcx
  struct Windows::Compat::Appraiser::MapTable *ListTableByName; // rax
  int v43; // eax
  struct Windows::Compat::Appraiser::MapTable *v44; // rax
  int v45; // eax
  char *v47; // [rsp+20h] [rbp-60h]
  const char *v48; // [rsp+28h] [rbp-58h]
  char *v49; // [rsp+30h] [rbp-50h]
  HANDLE hHeap[2]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v51; // [rsp+58h] [rbp-28h]
  __int128 v52; // [rsp+68h] [rbp-18h]
  const wchar_t *v53; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v54; // [rsp+D0h] [rbp+50h]

  GetProcessHeap();
  hHeap[0] = GetProcessHeap();
  v52 = 0x10u;
  v51 = 0;
  v2 = 0;
  v3 = 0;
  v4 = 8;
  hHeap[1] = (HANDLE)8;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x6A8u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\datafile.cpp",
      "Windows::Compat::Appraiser::DataFile::PopulateMemberTables",
      "Failed to initialize RtlArray: [0x%x].",
      0);
  v5 = 0;
  v6 = *((_QWORD *)this + 38);
  if ( v6 )
  {
    for ( i = 0; i < v6; ++i )
    {
      v8 = 0;
      if ( i < v6 )
      {
        v53 = 0;
        v9 = *((_QWORD *)this + 37) * i;
        if ( !is_mul_ok(*((_QWORD *)this + 37), i)
          || (v10 = *((_QWORD *)this + 41), v8 = (__int64 *)(v10 + v9), v10 + v9 < v10) )
        {
          v8 = 0;
        }
      }
      v11 = *v8;
      if ( !wcscmp_0((const wchar_t *)v11, L"LT_AssetTypesForSetupApplicationScan") )
      {
        *((_QWORD *)this + 61) = v11 + 128;
      }
      else if ( !wcscmp_0((const wchar_t *)v11, L"LT_AssetTypesForSetupDeviceScan") )
      {
        *((_QWORD *)this + 62) = v11 + 128;
      }
      else if ( !wcscmp_0((const wchar_t *)v11, L"LT_AssetTypesForSetupSystemScan") )
      {
        *((_QWORD *)this + 63) = v11 + 128;
      }
      else if ( !wcscmp_0((const wchar_t *)v11, L"LT_NonFatalComponentTypes") )
      {
        *((_QWORD *)this + 60) = v11 + 128;
      }
      else if ( !wcscmp_0((const wchar_t *)v11, L"LT_BucketOrder") )
      {
        v5 = (unsigned __int64 *)(v11 + 128);
      }
      else if ( !wcscmp_0((const wchar_t *)v11, L"LT_AppraiserTelemetryRoundNumberParameter") )
      {
        if ( !*(_QWORD *)(v11 + 144) )
        {
          v20 = "Data file has no rows in round number table.";
          v21 = -57;
          goto LABEL_36;
        }
        v53 = 0;
        if ( is_mul_ok(*(_QWORD *)(v11 + 136), 0) )
          v12 = *(_QWORD **)(v11 + 168);
        else
          v12 = 0;
        v13 = _o__wtoi(*v12);
        *((_DWORD *)this + 161) = v13;
        if ( !v13 )
        {
          v20 = "Data file is missing round number parameter.";
          v21 = -50;
LABEL_36:
          v22 = -2147024883;
          LODWORD(v47) = -2147024883;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            v21,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\datafile.cpp",
            "Windows::Compat::Appraiser::DataFile::PopulateMemberTables",
            v47,
            (int)v20,
            v49);
          goto LABEL_134;
        }
      }
      v6 = *((_QWORD *)this + 38);
    }
  }
  v14 = *((_QWORD *)this + 20);
  if ( !v14 )
    goto LABEL_63;
  for ( j = 0; j < v14; ++j )
  {
    v16 = 0;
    if ( j < v14 )
    {
      v53 = 0;
      v17 = *((_QWORD *)this + 19) * j;
      if ( !is_mul_ok(*((_QWORD *)this + 19), j)
        || (v18 = *((_QWORD *)this + 23), v16 = (const wchar_t **)(v18 + v17), v18 + v17 < v18) )
      {
        v16 = 0;
      }
    }
    v19 = *v16;
    v53 = v19;
    if ( !wcscmp_0(v19, L"FT_ALL_AssetTypesForSetupGatedScan") )
    {
      *((_QWORD *)this + 64) = v19;
      goto LABEL_61;
    }
    if ( !wcscmp_0(v19, L"FT_ALL_AssetTypesForSetupSystemScan") )
    {
      *((_QWORD *)this + 65) = v19;
      goto LABEL_61;
    }
    if ( !wcscmp_0(v19, L"FT_ALL_HumanRedableInterestingAssets") )
    {
      *((_QWORD *)this + 66) = v19;
      goto LABEL_61;
    }
    if ( !wcscmp_0(v19, L"FT_ALL_AppInterestingAssets") )
    {
      *((_QWORD *)this + 67) = v19;
      goto LABEL_61;
    }
    if ( !wcscmp_0(v19, L"FT_ALL_AppNotInterestingAssets") )
    {
      *((_QWORD *)this + 68) = v19;
      goto LABEL_61;
    }
    if ( !wcscmp_0(v19, L"FT_ALL_DevInterestingAssets") )
    {
      *((_QWORD *)this + 69) = v19;
      goto LABEL_61;
    }
    if ( !wcscmp_0(v19, L"FT_ALL_DevNotInterestingAssets") )
    {
      *((_QWORD *)this + 70) = v19;
      goto LABEL_61;
    }
    if ( !wcscmp_0(v19, L"FT_ANY_NeedsIcon") )
    {
      *((_QWORD *)this + 71) = v19;
      goto LABEL_61;
    }
    if ( wcsstr(v19, L"Bucket") && !wcsstr(v19, L"SubBucket") )
    {
      v22 = RtlArray<JsonValue *>::Append(hHeap, &v53);
      if ( v22 < 0 )
      {
        v34 = -5;
LABEL_85:
        LODWORD(v49) = v22;
        LODWORD(v47) = v22;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          v34,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\datafile.cpp",
          "Windows::Compat::Appraiser::DataFile::PopulateMemberTables",
          v47,
          (int)"RtlArray Append failed: [0x%x].",
          v49);
        v3 = (const wchar_t **)*((_QWORD *)&v52 + 1);
        goto LABEL_134;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
        goto LABEL_61;
      v23 = 1787;
      goto LABEL_60;
    }
    if ( !wcsstr(v19, L"_CompatMarker_") )
      goto LABEL_61;
    v22 = RtlArray<JsonValue *>::Append((char *)this + 48, &v53);
    if ( v22 < 0 )
    {
      v34 = 0;
      goto LABEL_85;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    {
      v23 = 1792;
LABEL_60:
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        v23,
        "onecore\\base\\appcompat\\appraiser\\helpers\\datafile.cpp",
        "Windows::Compat::Appraiser::DataFile::PopulateMemberTables",
        "RtlArray Append failed: [0x%x].",
        v22);
    }
LABEL_61:
    v14 = *((_QWORD *)this + 20);
  }
  v3 = (const wchar_t **)*((_QWORD *)&v52 + 1);
  v4 = (unsigned __int64)hHeap[1];
LABEL_63:
  if ( v5 )
  {
    v24 = v51;
    while ( v2 < v5[2] )
    {
      v25 = 0;
      if ( v24 )
      {
        while ( 1 )
        {
          v26 = 0;
          if ( v25 < v24 )
          {
            v53 = 0;
            if ( !is_mul_ok(v4, v25) || (v26 = (const wchar_t **)((char *)v3 + v4 * v25), v26 < v3) )
              v26 = 0;
          }
          v53 = *v26;
          v27 = 0;
          if ( v25 < v24 )
          {
            if ( !is_mul_ok(v4, v25) || (v27 = (const wchar_t **)((char *)v3 + v4 * v25), v27 < v3) )
              v27 = 0;
          }
          v28 = *v27;
          v54 = 0;
          if ( !is_mul_ok(v5[1], v2) || (v29 = (char **)(v5[5] + v5[1] * v2), (unsigned __int64)v29 < v5[5]) )
            v29 = 0;
          v30 = *v29;
          v31 = (char *)v28 - v30;
          do
          {
            v32 = *(unsigned __int16 *)&v30[v31];
            v33 = *(unsigned __int16 *)v30 - v32;
            if ( v33 )
              break;
            v30 += 2;
          }
          while ( v32 );
          if ( !v33 )
            break;
          if ( ++v25 >= v24 )
            goto LABEL_90;
        }
        v22 = RtlArray<JsonValue *>::Append(this, &v53);
        if ( v22 < 0 )
        {
          v35 = 17;
          goto LABEL_92;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x711u,
            "onecore\\base\\appcompat\\appraiser\\helpers\\datafile.cpp",
            "Windows::Compat::Appraiser::DataFile::PopulateMemberTables",
            "RtlArray Append failed: [0x%x].",
            v22);
      }
LABEL_90:
      ++v2;
    }
  }
  v37 = *((_QWORD *)this + 50);
  if ( v37 )
  {
    for ( k = 0; k < v37; ++k )
    {
      v39 = 0;
      if ( k < v37 )
      {
        v53 = 0;
        v40 = *((_QWORD *)this + 49) * k;
        if ( !is_mul_ok(*((_QWORD *)this + 49), k)
          || (v41 = *((_QWORD *)this + 53), v39 = (const wchar_t **)(v41 + v40), v41 + v40 < v41) )
        {
          v39 = 0;
        }
      }
      v53 = *v39;
      if ( wcsstr(v53, L"_CompatIndicator_") )
      {
        v22 = RtlArray<JsonValue *>::Append((char *)this + 336, &v53);
        if ( v22 < 0 )
        {
          v35 = 31;
LABEL_92:
          LODWORD(v49) = v22;
          v36 = "RtlArray Append failed: [0x%x].";
LABEL_93:
          LODWORD(v48) = (_DWORD)v36;
LABEL_94:
          LODWORD(v47) = v22;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            v35,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\datafile.cpp",
            "Windows::Compat::Appraiser::DataFile::PopulateMemberTables",
            v47,
            (int)v48,
            v49);
          goto LABEL_134;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x71Fu,
            "onecore\\base\\appcompat\\appraiser\\helpers\\datafile.cpp",
            "Windows::Compat::Appraiser::DataFile::PopulateMemberTables",
            "RtlArray Append failed: [0x%x].",
            v22);
      }
      v37 = *((_QWORD *)this + 50);
    }
  }
  ListTableByName = (struct Windows::Compat::Appraiser::MapTable *)Windows::Compat::Appraiser::DataFile::FindListTableByName(
                                                                     (char *)this + 432,
                                                                     L"MT_AppraiserDataFileParameters");
  if ( ListTableByName )
  {
    v43 = Windows::Compat::Appraiser::DataFile::PopulateDataFileParametersFromMapTable(this, ListTableByName);
    v22 = v43;
    if ( v43 < 0 )
    {
      LODWORD(v49) = v43;
      v48 = "Failed to populate data file parameters: [0x%x].";
      v35 = 39;
      goto LABEL_94;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x727u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\datafile.cpp",
        "Windows::Compat::Appraiser::DataFile::PopulateMemberTables",
        "Failed to populate data file parameters: [0x%x].",
        v43);
  }
  v44 = (struct Windows::Compat::Appraiser::MapTable *)Windows::Compat::Appraiser::DataFile::FindListTableByName(
                                                         (char *)this + 432,
                                                         L"MT_UniqueIdententifierTable");
  if ( v44 )
  {
    v45 = Windows::Compat::Appraiser::DataFile::ProcessUniqueIdentifierTable(this, v44);
    v22 = v45;
    if ( v45 < 0 )
    {
      LODWORD(v49) = v45;
      v48 = "Error Processing UniqueIdentifierTable: [0x%x]";
      v35 = 46;
      goto LABEL_94;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x72Eu,
        "onecore\\base\\appcompat\\appraiser\\helpers\\datafile.cpp",
        "Windows::Compat::Appraiser::DataFile::PopulateMemberTables",
        "Error Processing UniqueIdentifierTable: [0x%x]",
        v45);
  }
  if ( v5 && v5[2] != *((_QWORD *)this + 2) )
  {
    v22 = -2147024809;
    v49 = (char *)L"LT_BucketOrder";
    v36 = "Failure ordering buckets. Not all buckets in %ls were found.";
    v35 = 58;
    goto LABEL_93;
  }
  if ( !*((_QWORD *)this + 61)
    || !*((_QWORD *)this + 62)
    || !*((_QWORD *)this + 63)
    || !*((_QWORD *)this + 60)
    || !*((_QWORD *)this + 64)
    || !*((_QWORD *)this + 65)
    || !*((_QWORD *)this + 66)
    || !*((_QWORD *)this + 67)
    || !*((_QWORD *)this + 68)
    || !*((_QWORD *)this + 69)
    || !*((_QWORD *)this + 70)
    || !*((_QWORD *)this + 71) )
  {
    Windows::Compat::Appraiser::WriteLog(
      0,
      74,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\datafile.cpp",
      "Windows::Compat::Appraiser::DataFile::PopulateMemberTables",
      0,
      (int)"Missing semi-required table.",
      v49);
  }
  v22 = 0;
LABEL_134:
  if ( v3 )
    HeapFree(hHeap[0], 0, v3);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180098b10  mov     rax, rsp
0x180098b13  push    rbp
0x180098b14  push    rsi
0x180098b15  push    rdi
0x180098b16  push    r12
0x180098b18  push    r13
0x180098b1a  push    r14
0x180098b1c  push    r15
0x180098b1e  mov     rbp, rsp
0x180098b21  sub     rsp, 80h
0x180098b28  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x180098b30  mov     [rax+8], rbx
0x180098b34  mov     rbx, rcx
0x180098b37  call    cs:__imp_GetProcessHeap
0x180098b3d  nop
0x180098b3e  xorps   xmm0, xmm0
0x180098b41  movups  xmmword ptr [rbp+hHeap], xmm0
0x180098b45  movups  [rbp+var_18], xmm0
0x180098b49  call    cs:__imp_GetProcessHeap
0x180098b4f  mov     [rbp+hHeap], rax
0x180098b53  mov     qword ptr [rbp+var_18], 10h
0x180098b5b  xorps   xmm0, xmm0
0x180098b5e  movdqu  [rbp+var_28], xmm0
0x180098b63  xor     r14d, r14d
0x180098b66  mov     r15d, r14d
0x180098b69  mov     qword ptr [rbp+var_18+8], r14
0x180098b6d  lea     r12d, [r14+8]
0x180098b71  mov     [rbp+hHeap+8], r12
0x180098b75  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180098b7b  test    al, 1
0x180098b7d  jz      short loc_180098BA3
0x180098b7f  mov     dword ptr [rsp+80h+var_60], r14d
0x180098b84  lea     r9, aFailedToInitia_32; "Failed to initialize RtlArray: [0x%x]."
0x180098b8b  lea     r8, aWindowsCompatA_140; "Windows::Compat::Appraiser::DataFile::P"...
0x180098b92  lea     rdx, aOnecoreBaseApp_70; "onecore\\base\\appcompat\\appraiser\\he"...
0x180098b99  mov     ecx, 6A8h; unsigned int
0x180098b9e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180098ba3  mov     r13, r14
0x180098ba6  mov     rax, [rbx+130h]
0x180098bad  test    rax, rax
0x180098bb0  jz      loc_180098D0D
0x180098bb6  mov     rsi, r14
0x180098bb9  mov     rdi, r14
0x180098bbc  cmp     rsi, rax
0x180098bbf  jnb     short loc_180098BE7
0x180098bc1  mov     [rbp+arg_8], r14
0x180098bc5  mov     rax, rsi
0x180098bc8  mul     qword ptr [rbx+128h]
0x180098bcf  test    rdx, rdx
0x180098bd2  jnz     short loc_180098BE4
0x180098bd4  mov     rcx, [rbx+148h]
0x180098bdb  lea     rdi, [rcx+rax]
0x180098bdf  cmp     rdi, rcx
0x180098be2  jnb     short loc_180098BE7
0x180098be4  mov     rdi, r14
0x180098be7  mov     rdi, [rdi]
0x180098bea  lea     rdx, aLtAssettypesfo_0; "LT_AssetTypesForSetupApplicationScan"
0x180098bf1  mov     rcx, rdi; String1
0x180098bf4  call    wcscmp_0
0x180098bf9  test    eax, eax
0x180098bfb  jnz     short loc_180098C10
0x180098bfd  lea     rax, [rdi+80h]
0x180098c04  mov     [rbx+1E8h], rax
0x180098c0b  jmp     loc_180098CFA
0x180098c10  lea     rdx, aLtAssettypesfo; "LT_AssetTypesForSetupDeviceScan"
0x180098c17  mov     rcx, rdi; String1
0x180098c1a  call    wcscmp_0
0x180098c1f  test    eax, eax
0x180098c21  jnz     short loc_180098C36
0x180098c23  lea     rax, [rdi+80h]
0x180098c2a  mov     [rbx+1F0h], rax
0x180098c31  jmp     loc_180098CFA
0x180098c36  lea     rdx, aLtAssettypesfo_1; "LT_AssetTypesForSetupSystemScan"
0x180098c3d  mov     rcx, rdi; String1
0x180098c40  call    wcscmp_0
0x180098c45  test    eax, eax
0x180098c47  jnz     short loc_180098C5C
0x180098c49  lea     rax, [rdi+80h]
0x180098c50  mov     [rbx+1F8h], rax
0x180098c57  jmp     loc_180098CFA
0x180098c5c  lea     rdx, aLtNonfatalcomp; "LT_NonFatalComponentTypes"
0x180098c63  mov     rcx, rdi; String1
0x180098c66  call    wcscmp_0
0x180098c6b  test    eax, eax
0x180098c6d  jnz     short loc_180098C7F
0x180098c6f  lea     rax, [rdi+80h]
0x180098c76  mov     [rbx+1E0h], rax
0x180098c7d  jmp     short loc_180098CFA
0x180098c7f  lea     rdx, aLtBucketorder; "LT_BucketOrder"
0x180098c86  mov     rcx, rdi; String1
0x180098c89  call    wcscmp_0
0x180098c8e  test    eax, eax
0x180098c90  jnz     short loc_180098C9B
0x180098c92  lea     r13, [rdi+80h]
0x180098c99  jmp     short loc_180098CFA
0x180098c9b  lea     rdx, aLtAppraisertel; "LT_AppraiserTelemetryRoundNumberParamet"...
0x180098ca2  mov     rcx, rdi; String1
0x180098ca5  call    wcscmp_0
0x180098caa  test    eax, eax
0x180098cac  jnz     short loc_180098CFA
0x180098cae  mov     rcx, [rdi+90h]
0x180098cb5  test    rcx, rcx
0x180098cb8  jz      loc_180098D8C
0x180098cbe  mov     rax, r14
0x180098cc1  mov     [rbp+arg_8], r14
0x180098cc5  mul     qword ptr [rdi+88h]
0x180098ccc  test    rdx, rdx
0x180098ccf  jnz     short loc_180098CE0
0x180098cd1  mov     rcx, [rdi+0A8h]
0x180098cd8  add     rax, rcx
0x180098cdb  cmp     rax, rcx
0x180098cde  jnb     short loc_180098CE3
0x180098ce0  mov     rax, r14
0x180098ce3  mov     rcx, [rax]
0x180098ce6  call    cs:__imp__o__wtoi
0x180098cec  mov     [rbx+284h], eax
0x180098cf2  test    eax, eax
0x180098cf4  jz      loc_180098D7E
0x180098cfa  inc     rsi
0x180098cfd  mov     rax, [rbx+130h]
0x180098d04  cmp     rsi, rax
0x180098d07  jb      loc_180098BB9
0x180098d0d  mov     rax, [rbx+0A0h]
0x180098d14  test    rax, rax
0x180098d17  jz      loc_180098F5F
0x180098d1d  mov     rsi, r14
0x180098d20  mov     r15d, 6FBh
0x180098d26  lea     r12d, [r15+5]
0x180098d2a  mov     rdi, r14
0x180098d2d  cmp     rsi, rax
0x180098d30  jnb     short loc_180098D58
0x180098d32  mov     [rbp+arg_8], r14
0x180098d36  mov     rax, rsi
0x180098d39  mul     qword ptr [rbx+98h]
0x180098d40  test    rdx, rdx
0x180098d43  jnz     short loc_180098D55
0x180098d45  mov     rcx, [rbx+0B8h]
0x180098d4c  lea     rdi, [rcx+rax]
0x180098d50  cmp     rdi, rcx
0x180098d53  jnb     short loc_180098D58
0x180098d55  mov     rdi, r14
0x180098d58  mov     rdi, [rdi]
0x180098d5b  mov     [rbp+arg_8], rdi
0x180098d5f  lea     rdx, aFtAllAssettype; "FT_ALL_AssetTypesForSetupGatedScan"
0x180098d66  mov     rcx, rdi; String1
0x180098d69  call    wcscmp_0
0x180098d6e  test    eax, eax
0x180098d70  jnz     short loc_180098DC3
0x180098d72  mov     [rbx+200h], rdi
0x180098d79  jmp     loc_180098F44
0x180098d7e  lea     rax, aDataFileIsMiss_0; "Data file is missing round number param"...
0x180098d85  mov     edx, 6CEh
0x180098d8a  jmp     short loc_180098D98
0x180098d8c  lea     rax, aDataFileHasNoR; "Data file has no rows in round number t"...
0x180098d93  mov     edx, 6C7h; bool
0x180098d98  mov     qword ptr [rsp+80h+var_58], rax; int
0x180098d9d  mov     edi, 8007000Dh
0x180098da2  lea     r8, aOnecoreBaseApp_70; "onecore\\base\\appcompat\\appraiser\\he"...
0x180098da9  lea     r9, aWindowsCompatA_140; "Windows::Compat::Appraiser::DataFile::P"...
0x180098db0  mov     dword ptr [rsp+80h+var_60], edi; char *
0x180098db4  mov     ecx, 1; this
0x180098db9  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180098dbe  jmp     loc_18009933B
0x180098dc3  lea     rdx, aFtAllAssettype_0; "FT_ALL_AssetTypesForSetupSystemScan"
0x180098dca  mov     rcx, rdi; String1
0x180098dcd  call    wcscmp_0
0x180098dd2  test    eax, eax
0x180098dd4  jnz     short loc_180098DE2
0x180098dd6  mov     [rbx+208h], rdi
0x180098ddd  jmp     loc_180098F44
0x180098de2  lea     rdx, aFtAllHumanreda; "FT_ALL_HumanRedableInterestingAssets"
0x180098de9  mov     rcx, rdi; String1
0x180098dec  call    wcscmp_0
0x180098df1  test    eax, eax
0x180098df3  jnz     short loc_180098E01
0x180098df5  mov     [rbx+210h], rdi
0x180098dfc  jmp     loc_180098F44
0x180098e01  lea     rdx, aFtAllAppintere; "FT_ALL_AppInterestingAssets"
0x180098e08  mov     rcx, rdi; String1
0x180098e0b  call    wcscmp_0
0x180098e10  test    eax, eax
0x180098e12  jnz     short loc_180098E20
0x180098e14  mov     [rbx+218h], rdi
0x180098e1b  jmp     loc_180098F44
0x180098e20  lea     rdx, aFtAllAppnotint; "FT_ALL_AppNotInterestingAssets"
0x180098e27  mov     rcx, rdi; String1
0x180098e2a  call    wcscmp_0
0x180098e2f  test    eax, eax
0x180098e31  jnz     short loc_180098E3F
0x180098e33  mov     [rbx+220h], rdi
0x180098e3a  jmp     loc_180098F44
0x180098e3f  lea     rdx, aFtAllDevintere; "FT_ALL_DevInterestingAssets"
0x180098e46  mov     rcx, rdi; String1
0x180098e49  call    wcscmp_0
0x180098e4e  test    eax, eax
0x180098e50  jnz     short loc_180098E5E
0x180098e52  mov     [rbx+228h], rdi
0x180098e59  jmp     loc_180098F44
0x180098e5e  lea     rdx, aFtAllDevnotint; "FT_ALL_DevNotInterestingAssets"
0x180098e65  mov     rcx, rdi; String1
0x180098e68  call    wcscmp_0
0x180098e6d  test    eax, eax
0x180098e6f  jnz     short loc_180098E7D
0x180098e71  mov     [rbx+230h], rdi
0x180098e78  jmp     loc_180098F44
0x180098e7d  lea     rdx, aFtAnyNeedsicon; "FT_ANY_NeedsIcon"
0x180098e84  mov     rcx, rdi; String1
0x180098e87  call    wcscmp_0
0x180098e8c  test    eax, eax
0x180098e8e  jnz     short loc_180098E9C
0x180098e90  mov     [rbx+238h], rdi
0x180098e97  jmp     loc_180098F44
0x180098e9c  lea     rdx, aBucket; "Bucket"
0x180098ea3  mov     rcx, rdi; Str
0x180098ea6  call    cs:__imp_wcsstr
0x180098eac  test    rax, rax
0x180098eaf  jz      short loc_180098EED
0x180098eb1  lea     rdx, aSubbucket; "SubBucket"
0x180098eb8  mov     rcx, rdi; Str
0x180098ebb  call    cs:__imp_wcsstr
0x180098ec1  test    rax, rax
0x180098ec4  jnz     short loc_180098EED
0x180098ec6  lea     rdx, [rbp+arg_8]
0x180098eca  lea     rcx, [rbp+hHeap]
0x180098ece  call    ?Append@?$RtlArray@PEAUJsonValue@@@@QEAAJAEBQEAUJsonValue@@@Z; RtlArray<JsonValue *>::Append(JsonValue * const &)
0x180098ed3  mov     edi, eax
0x180098ed5  test    eax, eax
0x180098ed7  js      loc_180099014
0x180098edd  mov     ecx, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180098ee3  test    cl, 1
0x180098ee6  jz      short loc_180098F44
0x180098ee8  mov     ecx, r15d
0x180098eeb  jmp     short loc_180098F26
0x180098eed  lea     rdx, aCompatmarker; "_CompatMarker_"
0x180098ef4  mov     rcx, rdi; Str
0x180098ef7  call    cs:__imp_wcsstr
0x180098efd  test    rax, rax
0x180098f00  jz      short loc_180098F44
0x180098f02  lea     rcx, [rbx+30h]
0x180098f06  lea     rdx, [rbp+arg_8]
0x180098f0a  call    ?Append@?$RtlArray@PEAUJsonValue@@@@QEAAJAEBQEAUJsonValue@@@Z; RtlArray<JsonValue *>::Append(JsonValue * const &)
0x180098f0f  mov     edi, eax
0x180098f11  test    eax, eax
0x180098f13  js      loc_18009904C
0x180098f19  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180098f1f  test    al, 1
0x180098f21  jz      short loc_180098F44
0x180098f23  mov     ecx, r12d; unsigned int
0x180098f26  mov     dword ptr [rsp+80h+var_60], edi
0x180098f2a  lea     r9, aRtlarrayAppend_2; "RtlArray Append failed: [0x%x]."
0x180098f31  lea     r8, aWindowsCompatA_140; "Windows::Compat::Appraiser::DataFile::P"...
0x180098f38  lea     rdx, aOnecoreBaseApp_70; "onecore\\base\\appcompat\\appraiser\\he"...
0x180098f3f  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180098f44  inc     rsi
0x180098f47  mov     rax, [rbx+0A0h]
0x180098f4e  cmp     rsi, rax
0x180098f51  jb      loc_180098D2A
0x180098f57  mov     r15, qword ptr [rbp+var_18+8]
0x180098f5b  mov     r12, [rbp+hHeap+8]
0x180098f5f  test    r13, r13
0x180098f62  jz      loc_1800990D1
0x180098f68  mov     rsi, qword ptr [rbp+var_28]
0x180098f6c  cmp     r14, [r13+10h]
0x180098f70  jnb     loc_1800990CE
0x180098f76  xor     r8d, r8d
0x180098f79  test    rsi, rsi
0x180098f7c  jz      loc_180099090
0x180098f82  xor     eax, eax
0x180098f84  cmp     r8, rsi
0x180098f87  jnb     short loc_180098FA2
0x180098f89  mov     [rbp+arg_8], rax
0x180098f8d  mov     rax, r8
0x180098f90  mul     r12
0x180098f93  test    rdx, rdx
0x180098f96  jnz     short loc_180098FA0
0x180098f98  add     rax, r15
0x180098f9b  cmp     rax, r15
0x180098f9e  jnb     short loc_180098FA2
0x180098fa0  xor     eax, eax
0x180098fa2  mov     rax, [rax]
0x180098fa5  mov     [rbp+arg_8], rax
0x180098fa9  xor     eax, eax
0x180098fab  cmp     r8, rsi
0x180098fae  jnb     short loc_180098FC5
0x180098fb0  mov     rax, r8
0x180098fb3  mul     r12
0x180098fb6  test    rdx, rdx
0x180098fb9  jnz     short loc_180098FC3
0x180098fbb  add     rax, r15
0x180098fbe  cmp     rax, r15
0x180098fc1  jnb     short loc_180098FC5
0x180098fc3  xor     eax, eax
0x180098fc5  mov     r9, [rax]
0x180098fc8  mov     [rbp+arg_10], 0
0x180098fd0  mov     rax, r14
0x180098fd3  mul     qword ptr [r13+8]
0x180098fd7  test    rdx, rdx
0x180098fda  jnz     short loc_180098FE6
0x180098fdc  add     rax, [r13+28h]
0x180098fe0  cmp     rax, [r13+28h]
  ... truncated ...
```
