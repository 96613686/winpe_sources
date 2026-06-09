# Windows::Compat::Appraiser::DataMigrationOutputter::WriteRegistryEntry(HKEY__ *,Windows::Compat::Appraiser::PostupgradeRegistryData &)

- ea: `0x1800f4b34`
- end: `0x1800f53d2`
- name: `?WriteRegistryEntry@DataMigrationOutputter@Appraiser@Compat@Windows@@CAJPEAUHKEY__@@AEAUPostupgradeRegistryData@234@@Z`
- size: `2206`
- prototype: `__int64 __fastcall(HKEY, struct Windows::Compat::Appraiser::PostupgradeRegistryData *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800f35d0`

## callees

- `0x1800301d0`
- `0x1800f4b34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800f4fb5`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800f4fc2`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800f50b0`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800f5130`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800f4fb5`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800f4fc2`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800f50b0`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1800f5130`
- `ADVAPI32!RegCloseKey` at `0x1800f53b2`
- `ADVAPI32!RegCloseKey` at `0x1800f53b2`
- `ADVAPI32!RegCreateKeyExW` at `0x1800f4b8d`
- `ADVAPI32!RegCreateKeyExW` at `0x1800f4b8d`
- `ADVAPI32!RegSetValueExW` at `0x1800f4c31`
- `ADVAPI32!RegSetValueExW` at `0x1800f4cd7`
- `ADVAPI32!RegSetValueExW` at `0x1800f4d33`
- `ADVAPI32!RegSetValueExW` at `0x1800f4d8f`
- `ADVAPI32!RegSetValueExW` at `0x1800f4deb`
- `ADVAPI32!RegSetValueExW` at `0x1800f4e47`
- `ADVAPI32!RegSetValueExW` at `0x1800f4ea3`
- `ADVAPI32!RegSetValueExW` at `0x1800f4efe`
- `ADVAPI32!RegSetValueExW` at `0x1800f4f4d`
- `ADVAPI32!RegSetValueExW` at `0x1800f4fed`
- `ADVAPI32!RegSetValueExW` at `0x1800f505b`
- `ADVAPI32!RegSetValueExW` at `0x1800f50db`
- `ADVAPI32!RegSetValueExW` at `0x1800f515b`
- `ADVAPI32!RegSetValueExW` at `0x1800f51e1`
- `ADVAPI32!RegSetValueExW` at `0x1800f522a`
- `ADVAPI32!RegSetValueExW` at `0x1800f529d`
- `ADVAPI32!RegSetValueExW` at `0x1800f5328`
- `ADVAPI32!RegSetValueExW` at `0x1800f5384`
- `ADVAPI32!RegSetValueExW` at `0x1800f4c31`
- `ADVAPI32!RegSetValueExW` at `0x1800f4cd7`
- `ADVAPI32!RegSetValueExW` at `0x1800f4d33`
- `ADVAPI32!RegSetValueExW` at `0x1800f4d8f`
- `ADVAPI32!RegSetValueExW` at `0x1800f4deb`
- `ADVAPI32!RegSetValueExW` at `0x1800f4e47`
- `ADVAPI32!RegSetValueExW` at `0x1800f4ea3`
- `ADVAPI32!RegSetValueExW` at `0x1800f4efe`
- `ADVAPI32!RegSetValueExW` at `0x1800f4f4d`
- `ADVAPI32!RegSetValueExW` at `0x1800f4fed`
- `ADVAPI32!RegSetValueExW` at `0x1800f505b`
- `ADVAPI32!RegSetValueExW` at `0x1800f50db`
- `ADVAPI32!RegSetValueExW` at `0x1800f515b`
- `ADVAPI32!RegSetValueExW` at `0x1800f51e1`
- `ADVAPI32!RegSetValueExW` at `0x1800f522a`
- `ADVAPI32!RegSetValueExW` at `0x1800f529d`
- `ADVAPI32!RegSetValueExW` at `0x1800f5328`
- `ADVAPI32!RegSetValueExW` at `0x1800f5384`

## string_xrefs

- `0x1800f4bd9`: `Could not open/create regkey %ls: [%d].`
- `0x1800f4bb7`: `onecore\base\appcompat\appraiser\outputters\datamigration.cpp`
- `0x1800f4c84`: `onecore\base\appcompat\appraiser\outputters\datamigration.cpp`
- `0x1800f4bae`: `Windows::Compat::Appraiser::DataMigrationOutputter::WriteRegistryEntry`
- `0x1800f4c8b`: `Windows::Compat::Appraiser::DataMigrationOutputter::WriteRegistryEntry`
- `0x1800f4cc1`: `ExeFullPath`
- `0x1800f4c73`: `Failed to create registry value: %ls / %ls under %ls: [%d].`
- `0x1800f4e31`: `ArpFullPath`
- `0x1800f50ba`: `FwLink`
- `0x1800f4f8d`: `Failed to create registry value: %ls / %u under %ls: [%d].`
- `0x1800f502d`: `Failed to create registry value: %ls / %u under %ls: [%d].`
- `0x1800f509b`: `Failed to create registry value: %ls / %u under %ls: [%d].`
- `0x1800f511b`: `Failed to create registry value: %ls / %u under %ls: [%d].`
- `0x1800f519b`: `Failed to create registry value: %ls / %u under %ls: [%d].`
- `0x1800f526a`: `Failed to create registry value: %ls / %u under %ls: [%d].`
- `0x1800f52dd`: `Failed to create registry value: %ls / %u under %ls: [%d].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::DataMigrationOutputter::WriteRegistryEntry(
        HKEY a1,
        struct Windows::Compat::Appraiser::PostupgradeRegistryData *a2)
{
  const WCHAR *v3; // rdx
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  const BYTE *v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rax
  const wchar_t *v9; // r14
  LSTATUS v10; // eax
  LSTATUS v11; // ecx
  char v12; // dl
  const char *v13; // rax
  const BYTE *v14; // rcx
  __int64 v15; // rax
  LSTATUS v16; // eax
  const BYTE *v17; // rcx
  __int64 v18; // rax
  LSTATUS v19; // eax
  const BYTE *v20; // rcx
  __int64 v21; // rax
  LSTATUS v22; // eax
  const BYTE *v23; // rcx
  __int64 v24; // rax
  LSTATUS v25; // eax
  const BYTE *v26; // rcx
  __int64 v27; // rax
  LSTATUS v28; // eax
  const BYTE *v29; // rcx
  __int64 v30; // rax
  LSTATUS v31; // eax
  const BYTE *v32; // rcx
  __int64 v33; // rax
  LSTATUS v34; // eax
  LSTATUS v35; // eax
  __int64 v36; // rcx
  int v37; // eax
  __int64 v38; // rcx
  LSTATUS v39; // eax
  LSTATUS v40; // eax
  __int64 v41; // rcx
  LSTATUS v42; // eax
  __int64 v43; // rcx
  LSTATUS v44; // eax
  const BYTE *v45; // rcx
  __int64 v46; // rax
  LSTATUS v47; // eax
  LSTATUS v48; // eax
  LSTATUS v49; // eax
  const BYTE *v50; // rcx
  __int64 v51; // rax
  LSTATUS v52; // eax
  const BYTE *v53; // rcx
  LSTATUS v54; // eax
  BYTE *lpData; // [rsp+20h] [rbp-40h]
  BYTE *lpDataa; // [rsp+20h] [rbp-40h]
  const WCHAR *v58; // [rsp+30h] [rbp-30h]
  __int64 v59; // [rsp+38h] [rbp-28h]
  __int64 v60; // [rsp+40h] [rbp-20h]
  LSTATUS v61; // [rsp+48h] [rbp-18h]
  __int64 v62; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  int Data; // [rsp+A8h] [rbp+48h] BYREF
  int v65; // [rsp+B0h] [rbp+50h] BYREF
  int v66; // [rsp+B8h] [rbp+58h] BYREF

  v3 = (const WCHAR *)*((_QWORD *)a2 + 7);
  Data = 0;
  v65 = 0;
  v66 = 0;
  LODWORD(v62) = 0;
  hKey = 0;
  v4 = RegCreateKeyExW(a1, v3, 0, 0, 0, 0x20106u, 0, &hKey, 0);
  if ( !v4 )
  {
    v6 = (const BYTE *)*((_QWORD *)a2 + 8);
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&v6[2 * v8] );
    v9 = L"ExeName";
    v10 = RegSetValueExW(hKey, L"ExeName", 0, 1u, v6, 2 * v8 + 2);
    v11 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
      else
        v5 = v10;
      v12 = -34;
    }
    else
    {
      v14 = (const BYTE *)*((_QWORD *)a2 + 6);
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)&v14[2 * v15] );
      v9 = L"ExeFullPath";
      v16 = RegSetValueExW(hKey, L"ExeFullPath", 0, 1u, v14, 2 * v15 + 2);
      v11 = v16;
      if ( v16 )
      {
        if ( v16 > 0 )
          v5 = (unsigned __int16)v16 | 0x80070000;
        else
          v5 = v16;
        v12 = -33;
      }
      else
      {
        v17 = (const BYTE *)*((_QWORD *)a2 + 2);
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)&v17[2 * v18] );
        v9 = L"AppName";
        v19 = RegSetValueExW(hKey, L"AppName", 0, 1u, v17, 2 * v18 + 2);
        v11 = v19;
        if ( v19 )
        {
          if ( v19 > 0 )
            v5 = (unsigned __int16)v19 | 0x80070000;
          else
            v5 = v19;
          v12 = -32;
        }
        else
        {
          v20 = (const BYTE *)*((_QWORD *)a2 + 5);
          v21 = -1;
          do
            ++v21;
          while ( *(_WORD *)&v20[2 * v21] );
          v9 = L"DbGuid";
          v22 = RegSetValueExW(hKey, L"DbGuid", 0, 1u, v20, 2 * v21 + 2);
          v11 = v22;
          if ( v22 )
          {
            if ( v22 > 0 )
              v5 = (unsigned __int16)v22 | 0x80070000;
            else
              v5 = v22;
            v12 = -31;
          }
          else
          {
            v23 = (const BYTE *)*((_QWORD *)a2 + 7);
            v24 = -1;
            do
              ++v24;
            while ( *(_WORD *)&v23[2 * v24] );
            v9 = L"ExeGuid";
            v25 = RegSetValueExW(hKey, L"ExeGuid", 0, 1u, v23, 2 * v24 + 2);
            v11 = v25;
            if ( v25 )
            {
              if ( v25 > 0 )
                v5 = (unsigned __int16)v25 | 0x80070000;
              else
                v5 = v25;
              v12 = -30;
            }
            else
            {
              v26 = (const BYTE *)*((_QWORD *)a2 + 3);
              v27 = -1;
              do
                ++v27;
              while ( *(_WORD *)&v26[2 * v27] );
              v9 = L"ArpFullPath";
              v28 = RegSetValueExW(hKey, L"ArpFullPath", 0, 1u, v26, 2 * v27 + 2);
              v11 = v28;
              if ( v28 )
              {
                if ( v28 > 0 )
                  v5 = (unsigned __int16)v28 | 0x80070000;
                else
                  v5 = v28;
                v12 = -29;
              }
              else
              {
                v29 = (const BYTE *)*((_QWORD *)a2 + 1);
                v30 = -1;
                do
                  ++v30;
                while ( *(_WORD *)&v29[2 * v30] );
                v9 = L"ProgramId";
                v31 = RegSetValueExW(hKey, L"ProgramId", 0, 1u, v29, 2 * v30 + 2);
                v11 = v31;
                if ( v31 )
                {
                  if ( v31 > 0 )
                    v5 = (unsigned __int16)v31 | 0x80070000;
                  else
                    v5 = v31;
                  v12 = -28;
                }
                else
                {
                  v32 = *(const BYTE **)a2;
                  v33 = -1;
                  do
                    ++v33;
                  while ( *(_WORD *)&v32[2 * v33] );
                  v9 = L"ActionType";
                  v34 = RegSetValueExW(hKey, L"ActionType", 0, 1u, v32, 2 * v33 + 2);
                  v11 = v34;
                  if ( v34 )
                  {
                    if ( v34 > 0 )
                      v5 = (unsigned __int16)v34 | 0x80070000;
                    else
                      v5 = v34;
                    v12 = -27;
                  }
                  else
                  {
                    v35 = RegSetValueExW(hKey, L"ExeIndexInApp", 0, 4u, (const BYTE *)a2 + 72, 4u);
                    if ( v35 )
                    {
                      if ( v35 > 0 )
                        v5 = (unsigned __int16)v35 | 0x80070000;
                      else
                        v5 = v35;
                      v61 = v35;
                      v12 = -25;
                      v60 = *((_QWORD *)a2 + 7);
                      LODWORD(v59) = *((_DWORD *)a2 + 18);
                      v13 = "Failed to create registry value: %ls / %u under %ls: [%d].";
                      v58 = L"ExeIndexInApp";
                      goto LABEL_15;
                    }
                    v36 = *((_QWORD *)a2 + 13);
                    if ( v36 && *((_QWORD *)a2 + 14) )
                    {
                      v37 = _o__wtoi(v36);
                      v38 = *((_QWORD *)a2 + 14);
                      Data = v37;
                      v9 = L"NTFSFileIdHigh";
                      v65 = _o__wtoi(v38);
                      v39 = RegSetValueExW(hKey, L"NTFSFileIdHigh", 0, 4u, (const BYTE *)&Data, 4u);
                      if ( v39 )
                      {
                        if ( v39 > 0 )
                          v5 = (unsigned __int16)v39 | 0x80070000;
                        else
                          v5 = v39;
                        v61 = v39;
                        v12 = -15;
                        v60 = *((_QWORD *)a2 + 7);
                        LODWORD(v59) = Data;
                        v13 = "Failed to create registry value: %ls / %u under %ls: [%d].";
                        goto LABEL_14;
                      }
                      v9 = L"NTFSFileIdLow";
                      v40 = RegSetValueExW(hKey, L"NTFSFileIdLow", 0, 4u, (const BYTE *)&v65, 4u);
                      if ( v40 )
                      {
                        if ( v40 > 0 )
                          v5 = (unsigned __int16)v40 | 0x80070000;
                        else
                          v5 = v40;
                        v61 = v40;
                        v12 = -14;
                        v60 = *((_QWORD *)a2 + 7);
                        LODWORD(v59) = v65;
                        v13 = "Failed to create registry value: %ls / %u under %ls: [%d].";
                        goto LABEL_14;
                      }
                    }
                    v41 = *((_QWORD *)a2 + 10);
                    if ( v41 )
                    {
                      v9 = L"FwLink";
                      v66 = _o__wtoi(v41);
                      v42 = RegSetValueExW(hKey, L"FwLink", 0, 4u, (const BYTE *)&v66, 4u);
                      if ( v42 )
                      {
                        if ( v42 > 0 )
                          v5 = (unsigned __int16)v42 | 0x80070000;
                        else
                          v5 = v42;
                        v61 = v42;
                        v12 = -6;
                        v60 = *((_QWORD *)a2 + 7);
                        LODWORD(v59) = v66;
                        v13 = "Failed to create registry value: %ls / %u under %ls: [%d].";
                        goto LABEL_14;
                      }
                    }
                    v43 = *((_QWORD *)a2 + 12);
                    if ( v43 )
                    {
                      v9 = L"KbArticle";
                      LODWORD(v62) = _o__wtoi(v43);
                      v44 = RegSetValueExW(hKey, L"KbArticle", 0, 4u, (const BYTE *)&v62, 4u);
                      if ( v44 )
                      {
                        if ( v44 > 0 )
                          v5 = (unsigned __int16)v44 | 0x80070000;
                        else
                          v5 = v44;
                        v61 = v44;
                        v12 = 2;
                        v60 = *((_QWORD *)a2 + 7);
                        LODWORD(v59) = v62;
                        v13 = "Failed to create registry value: %ls / %u under %ls: [%d].";
                        goto LABEL_14;
                      }
                    }
                    v45 = (const BYTE *)*((_QWORD *)a2 + 15);
                    if ( !v45 )
                      goto LABEL_102;
                    v46 = -1;
                    do
                      ++v46;
                    while ( *(_WORD *)&v45[2 * v46] );
                    v9 = L"StoreUrl";
                    v47 = RegSetValueExW(hKey, L"StoreUrl", 0, 1u, v45, 2 * v46 + 2);
                    v11 = v47;
                    if ( v47 )
                    {
                      if ( v47 > 0 )
                        v5 = (unsigned __int16)v47 | 0x80070000;
                      else
                        v5 = v47;
                      v12 = 7;
                    }
                    else
                    {
LABEL_102:
                      v48 = RegSetValueExW(hKey, L"IsAntiMalware", 0, 4u, (const BYTE *)a2 + 88, 4u);
                      if ( v48 )
                      {
                        if ( v48 > 0 )
                          v5 = (unsigned __int16)v48 | 0x80070000;
                        else
                          v5 = v48;
                        v61 = v48;
                        v12 = 10;
                        v60 = *((_QWORD *)a2 + 7);
                        LODWORD(v59) = *((_DWORD *)a2 + 22);
                        v13 = "Failed to create registry value: %ls / %u under %ls: [%d].";
                        v58 = L"IsAntiMalware";
                        goto LABEL_15;
                      }
                      v49 = RegSetValueExW(hKey, L"IsExpired", 0, 4u, (const BYTE *)a2 + 92, 4u);
                      if ( v49 )
                      {
                        if ( v49 > 0 )
                          v5 = (unsigned __int16)v49 | 0x80070000;
                        else
                          v5 = v49;
                        v61 = v49;
                        v12 = 11;
                        v60 = *((_QWORD *)a2 + 7);
                        LODWORD(v59) = *((_DWORD *)a2 + 23);
                        v13 = "Failed to create registry value: %ls / %u under %ls: [%d].";
                        v58 = L"IsExpired";
                        goto LABEL_15;
                      }
                      v50 = (const BYTE *)*((_QWORD *)a2 + 4);
                      if ( !v50 )
                        goto LABEL_120;
                      v51 = -1;
                      do
                        ++v51;
                      while ( *(_WORD *)&v50[2 * v51] );
                      v9 = L"AvDisplayName";
                      v52 = RegSetValueExW(hKey, L"AvDisplayName", 0, 1u, v50, 2 * v51 + 2);
                      v11 = v52;
                      if ( v52 )
                      {
                        if ( v52 > 0 )
                          v5 = (unsigned __int16)v52 | 0x80070000;
                        else
                          v5 = v52;
                        v12 = 14;
                      }
                      else
                      {
LABEL_120:
                        v53 = (const BYTE *)*((_QWORD *)a2 + 16);
                        do
                          ++v7;
                        while ( *(_WORD *)&v53[2 * v7] );
                        v9 = L"VendorName";
                        v54 = RegSetValueExW(hKey, L"VendorName", 0, 1u, v53, 2 * v7 + 2);
                        v11 = v54;
                        if ( !v54 )
                        {
                          v5 = 0;
                          goto LABEL_128;
                        }
                        if ( v54 > 0 )
                          v5 = (unsigned __int16)v54 | 0x80070000;
                        else
                          v5 = v54;
                        v12 = 17;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    v61 = v11;
    v60 = *((_QWORD *)a2 + 7);
    v59 = *((_QWORD *)a2 + 8);
    v13 = "Failed to create registry value: %ls / %ls under %ls: [%d].";
LABEL_14:
    v58 = v9;
LABEL_15:
    LODWORD(lpDataa) = v5;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v12,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\datamigration.cpp",
      "Windows::Compat::Appraiser::DataMigrationOutputter::WriteRegistryEntry",
      (const char *)lpDataa,
      (int)v13,
      (const char *)v58,
      v59,
      v60,
      v61,
      v62);
    goto LABEL_128;
  }
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  else
    v5 = v4;
  LODWORD(v59) = v4;
  LODWORD(lpData) = v5;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    219,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\datamigration.cpp",
    "Windows::Compat::Appraiser::DataMigrationOutputter::WriteRegistryEntry",
    (const char *)lpData,
    (int)"Could not open/create regkey %ls: [%d].",
    *((const char **)a2 + 7),
    v59);
LABEL_128:
  RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x1800f4b34  mov     r11, rsp
0x1800f4b37  mov     [r11+8], rbx
0x1800f4b3b  push    rbp
0x1800f4b3c  push    rsi
0x1800f4b3d  push    rdi
0x1800f4b3e  push    r12
0x1800f4b40  push    r13
0x1800f4b42  push    r14
0x1800f4b44  push    r15
0x1800f4b46  mov     rbp, rsp
0x1800f4b49  sub     rsp, 60h
0x1800f4b4d  xor     r15d, r15d
0x1800f4b50  lea     rax, [rbp+hKey]
0x1800f4b54  mov     [r11-58h], r15
0x1800f4b58  mov     rdi, rdx
0x1800f4b5b  mov     rdx, [rdx+38h]; lpSubKey
0x1800f4b5f  xor     r9d, r9d; lpClass
0x1800f4b62  mov     [r11-60h], rax
0x1800f4b66  xor     r8d, r8d; Reserved
0x1800f4b69  mov     [r11-68h], r15
0x1800f4b6d  mov     [rsp+60h+samDesired], 20106h; samDesired
0x1800f4b75  mov     [r11-78h], r15d
0x1800f4b79  mov     [rbp+Data], r15d
0x1800f4b7d  mov     [rbp+arg_10], r15d
0x1800f4b81  mov     [rbp+arg_18], r15d
0x1800f4b85  mov     dword ptr [rbp+var_10], r15d
0x1800f4b89  mov     [rbp+hKey], r15
0x1800f4b8d  call    cs:__imp_RegCreateKeyExW
0x1800f4b93  mov     ecx, eax
0x1800f4b95  test    eax, eax
0x1800f4b97  jz      short loc_1800F4BF3
0x1800f4b99  test    eax, eax
0x1800f4b9b  jg      short loc_1800F4BA1
0x1800f4b9d  mov     ebx, eax
0x1800f4b9f  jmp     short loc_1800F4BAA
0x1800f4ba1  movzx   ebx, cx
0x1800f4ba4  or      ebx, 80070000h
0x1800f4baa  mov     dword ptr [rsp+60h+var_28], ecx
0x1800f4bae  lea     r9, aWindowsCompatA_752; "Windows::Compat::Appraiser::DataMigrati"...
0x1800f4bb5  test    ebx, ebx
0x1800f4bb7  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800f4bbe  mov     eax, 80004005h
0x1800f4bc3  mov     edx, 1DBh; bool
0x1800f4bc8  cmovns  ebx, eax
0x1800f4bcb  mov     ecx, 1; this
0x1800f4bd0  mov     rax, [rdi+38h]
0x1800f4bd4  mov     [rsp+60h+var_30], rax; char *
0x1800f4bd9  lea     rax, aCouldNotOpenCr; "Could not open/create regkey %ls: [%d]."
0x1800f4be0  mov     qword ptr [rsp+60h+samDesired], rax; int
0x1800f4be5  mov     dword ptr [rsp+60h+lpData], ebx; char *
0x1800f4be9  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800f4bee  jmp     loc_1800F53AE
0x1800f4bf3  mov     rcx, [rdi+40h]
0x1800f4bf7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f4bfb  mov     rax, rbx
0x1800f4bfe  inc     rax
0x1800f4c01  cmp     [rcx+rax*2], r15w
0x1800f4c06  jnz     short loc_1800F4BFE
0x1800f4c08  lea     eax, ds:2[rax*2]
0x1800f4c0f  mov     esi, 1
0x1800f4c14  mov     [rsp+60h+samDesired], eax; cbData
0x1800f4c18  lea     r14, aExename; "ExeName"
0x1800f4c1f  mov     [rsp+60h+lpData], rcx; lpData
0x1800f4c24  mov     r9d, esi; dwType
0x1800f4c27  mov     rcx, [rbp+hKey]; hKey
0x1800f4c2b  xor     r8d, r8d; Reserved
0x1800f4c2e  mov     rdx, r14; lpValueName
0x1800f4c31  call    cs:__imp_RegSetValueExW
0x1800f4c37  mov     ecx, eax
0x1800f4c39  test    eax, eax
0x1800f4c3b  jz      short loc_1800F4CA2
0x1800f4c3d  test    eax, eax
0x1800f4c3f  jg      short loc_1800F4C45
0x1800f4c41  mov     ebx, eax
0x1800f4c43  jmp     short loc_1800F4C4E
0x1800f4c45  movzx   ebx, cx
0x1800f4c48  or      ebx, 80070000h
0x1800f4c4e  mov     edx, 1DEh; bool
0x1800f4c53  mov     eax, 80004005h
0x1800f4c58  mov     [rsp+60h+var_18], ecx
0x1800f4c5c  test    ebx, ebx
0x1800f4c5e  cmovns  ebx, eax
0x1800f4c61  mov     rax, [rdi+38h]
0x1800f4c65  mov     [rsp+60h+var_20], rax
0x1800f4c6a  mov     rax, [rdi+40h]
0x1800f4c6e  mov     [rsp+60h+var_28], rax
0x1800f4c73  lea     rax, aFailedToCreate_35; "Failed to create registry value: %ls / "...
0x1800f4c7a  mov     [rsp+60h+var_30], r14; char *
0x1800f4c7f  mov     qword ptr [rsp+60h+samDesired], rax; int
0x1800f4c84  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800f4c8b  lea     r9, aWindowsCompatA_752; "Windows::Compat::Appraiser::DataMigrati"...
0x1800f4c92  mov     dword ptr [rsp+60h+lpData], ebx; char *
0x1800f4c96  mov     ecx, esi; this
0x1800f4c98  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800f4c9d  jmp     loc_1800F53AE
0x1800f4ca2  mov     rcx, [rdi+30h]
0x1800f4ca6  mov     rax, rbx
0x1800f4ca9  inc     rax
0x1800f4cac  cmp     [rcx+rax*2], r15w
0x1800f4cb1  jnz     short loc_1800F4CA9
0x1800f4cb3  lea     eax, ds:2[rax*2]
0x1800f4cba  mov     r9d, esi; dwType
0x1800f4cbd  mov     [rsp+60h+samDesired], eax; cbData
0x1800f4cc1  lea     r14, aExefullpath; "ExeFullPath"
0x1800f4cc8  mov     [rsp+60h+lpData], rcx; lpData
0x1800f4ccd  xor     r8d, r8d; Reserved
0x1800f4cd0  mov     rcx, [rbp+hKey]; hKey
0x1800f4cd4  mov     rdx, r14; lpValueName
0x1800f4cd7  call    cs:__imp_RegSetValueExW
0x1800f4cdd  mov     ecx, eax
0x1800f4cdf  test    eax, eax
0x1800f4ce1  jz      short loc_1800F4CFE
0x1800f4ce3  test    eax, eax
0x1800f4ce5  jg      short loc_1800F4CEB
0x1800f4ce7  mov     ebx, eax
0x1800f4ce9  jmp     short loc_1800F4CF4
0x1800f4ceb  movzx   ebx, cx
0x1800f4cee  or      ebx, 80070000h
0x1800f4cf4  mov     edx, 1DFh
0x1800f4cf9  jmp     loc_1800F4C53
0x1800f4cfe  mov     rcx, [rdi+10h]
0x1800f4d02  mov     rax, rbx
0x1800f4d05  inc     rax
0x1800f4d08  cmp     [rcx+rax*2], r15w
0x1800f4d0d  jnz     short loc_1800F4D05
0x1800f4d0f  lea     eax, ds:2[rax*2]
0x1800f4d16  mov     r9d, esi; dwType
0x1800f4d19  mov     [rsp+60h+samDesired], eax; cbData
0x1800f4d1d  lea     r14, aAppname_0; "AppName"
0x1800f4d24  mov     [rsp+60h+lpData], rcx; lpData
0x1800f4d29  xor     r8d, r8d; Reserved
0x1800f4d2c  mov     rcx, [rbp+hKey]; hKey
0x1800f4d30  mov     rdx, r14; lpValueName
0x1800f4d33  call    cs:__imp_RegSetValueExW
0x1800f4d39  mov     ecx, eax
0x1800f4d3b  test    eax, eax
0x1800f4d3d  jz      short loc_1800F4D5A
0x1800f4d3f  test    eax, eax
0x1800f4d41  jg      short loc_1800F4D47
0x1800f4d43  mov     ebx, eax
0x1800f4d45  jmp     short loc_1800F4D50
0x1800f4d47  movzx   ebx, cx
0x1800f4d4a  or      ebx, 80070000h
0x1800f4d50  mov     edx, 1E0h
0x1800f4d55  jmp     loc_1800F4C53
0x1800f4d5a  mov     rcx, [rdi+28h]
0x1800f4d5e  mov     rax, rbx
0x1800f4d61  inc     rax
0x1800f4d64  cmp     [rcx+rax*2], r15w
0x1800f4d69  jnz     short loc_1800F4D61
0x1800f4d6b  lea     eax, ds:2[rax*2]
0x1800f4d72  mov     r9d, esi; dwType
0x1800f4d75  mov     [rsp+60h+samDesired], eax; cbData
0x1800f4d79  lea     r14, aDbguid; "DbGuid"
0x1800f4d80  mov     [rsp+60h+lpData], rcx; lpData
0x1800f4d85  xor     r8d, r8d; Reserved
0x1800f4d88  mov     rcx, [rbp+hKey]; hKey
0x1800f4d8c  mov     rdx, r14; lpValueName
0x1800f4d8f  call    cs:__imp_RegSetValueExW
0x1800f4d95  mov     ecx, eax
0x1800f4d97  test    eax, eax
0x1800f4d99  jz      short loc_1800F4DB6
0x1800f4d9b  test    eax, eax
0x1800f4d9d  jg      short loc_1800F4DA3
0x1800f4d9f  mov     ebx, eax
0x1800f4da1  jmp     short loc_1800F4DAC
0x1800f4da3  movzx   ebx, cx
0x1800f4da6  or      ebx, 80070000h
0x1800f4dac  mov     edx, 1E1h
0x1800f4db1  jmp     loc_1800F4C53
0x1800f4db6  mov     rcx, [rdi+38h]
0x1800f4dba  mov     rax, rbx
0x1800f4dbd  inc     rax
0x1800f4dc0  cmp     [rcx+rax*2], r15w
0x1800f4dc5  jnz     short loc_1800F4DBD
0x1800f4dc7  lea     eax, ds:2[rax*2]
0x1800f4dce  mov     r9d, esi; dwType
0x1800f4dd1  mov     [rsp+60h+samDesired], eax; cbData
0x1800f4dd5  lea     r14, aExeguid; "ExeGuid"
0x1800f4ddc  mov     [rsp+60h+lpData], rcx; lpData
0x1800f4de1  xor     r8d, r8d; Reserved
0x1800f4de4  mov     rcx, [rbp+hKey]; hKey
0x1800f4de8  mov     rdx, r14; lpValueName
0x1800f4deb  call    cs:__imp_RegSetValueExW
0x1800f4df1  mov     ecx, eax
0x1800f4df3  test    eax, eax
0x1800f4df5  jz      short loc_1800F4E12
0x1800f4df7  test    eax, eax
0x1800f4df9  jg      short loc_1800F4DFF
0x1800f4dfb  mov     ebx, eax
0x1800f4dfd  jmp     short loc_1800F4E08
0x1800f4dff  movzx   ebx, cx
0x1800f4e02  or      ebx, 80070000h
0x1800f4e08  mov     edx, 1E2h
0x1800f4e0d  jmp     loc_1800F4C53
0x1800f4e12  mov     rcx, [rdi+18h]
0x1800f4e16  mov     rax, rbx
0x1800f4e19  inc     rax
0x1800f4e1c  cmp     [rcx+rax*2], r15w
0x1800f4e21  jnz     short loc_1800F4E19
0x1800f4e23  lea     eax, ds:2[rax*2]
0x1800f4e2a  mov     r9d, esi; dwType
0x1800f4e2d  mov     [rsp+60h+samDesired], eax; cbData
0x1800f4e31  lea     r14, aArpfullpath; "ArpFullPath"
0x1800f4e38  mov     [rsp+60h+lpData], rcx; lpData
0x1800f4e3d  xor     r8d, r8d; Reserved
0x1800f4e40  mov     rcx, [rbp+hKey]; hKey
0x1800f4e44  mov     rdx, r14; lpValueName
0x1800f4e47  call    cs:__imp_RegSetValueExW
0x1800f4e4d  mov     ecx, eax
0x1800f4e4f  test    eax, eax
0x1800f4e51  jz      short loc_1800F4E6E
0x1800f4e53  test    eax, eax
0x1800f4e55  jg      short loc_1800F4E5B
0x1800f4e57  mov     ebx, eax
0x1800f4e59  jmp     short loc_1800F4E64
0x1800f4e5b  movzx   ebx, cx
0x1800f4e5e  or      ebx, 80070000h
0x1800f4e64  mov     edx, 1E3h
0x1800f4e69  jmp     loc_1800F4C53
0x1800f4e6e  mov     rcx, [rdi+8]
0x1800f4e72  mov     rax, rbx
0x1800f4e75  inc     rax
0x1800f4e78  cmp     [rcx+rax*2], r15w
0x1800f4e7d  jnz     short loc_1800F4E75
0x1800f4e7f  lea     eax, ds:2[rax*2]
0x1800f4e86  mov     r9d, esi; dwType
0x1800f4e89  mov     [rsp+60h+samDesired], eax; cbData
0x1800f4e8d  lea     r14, aProgramid_2; "ProgramId"
0x1800f4e94  mov     [rsp+60h+lpData], rcx; lpData
0x1800f4e99  xor     r8d, r8d; Reserved
0x1800f4e9c  mov     rcx, [rbp+hKey]; hKey
0x1800f4ea0  mov     rdx, r14; lpValueName
0x1800f4ea3  call    cs:__imp_RegSetValueExW
0x1800f4ea9  mov     ecx, eax
0x1800f4eab  test    eax, eax
0x1800f4ead  jz      short loc_1800F4ECA
0x1800f4eaf  test    eax, eax
0x1800f4eb1  jg      short loc_1800F4EB7
0x1800f4eb3  mov     ebx, eax
0x1800f4eb5  jmp     short loc_1800F4EC0
0x1800f4eb7  movzx   ebx, cx
0x1800f4eba  or      ebx, 80070000h
0x1800f4ec0  mov     edx, 1E4h
0x1800f4ec5  jmp     loc_1800F4C53
0x1800f4eca  mov     rcx, [rdi]
0x1800f4ecd  mov     rax, rbx
0x1800f4ed0  inc     rax
0x1800f4ed3  cmp     [rcx+rax*2], r15w
0x1800f4ed8  jnz     short loc_1800F4ED0
0x1800f4eda  lea     eax, ds:2[rax*2]
0x1800f4ee1  mov     r9d, esi; dwType
0x1800f4ee4  mov     [rsp+60h+samDesired], eax; cbData
0x1800f4ee8  lea     r14, aActiontype; "ActionType"
0x1800f4eef  mov     [rsp+60h+lpData], rcx; lpData
0x1800f4ef4  xor     r8d, r8d; Reserved
0x1800f4ef7  mov     rcx, [rbp+hKey]; hKey
0x1800f4efb  mov     rdx, r14; lpValueName
0x1800f4efe  call    cs:__imp_RegSetValueExW
0x1800f4f04  mov     ecx, eax
0x1800f4f06  test    eax, eax
0x1800f4f08  jz      short loc_1800F4F25
0x1800f4f0a  test    eax, eax
0x1800f4f0c  jg      short loc_1800F4F12
0x1800f4f0e  mov     ebx, eax
0x1800f4f10  jmp     short loc_1800F4F1B
0x1800f4f12  movzx   ebx, cx
0x1800f4f15  or      ebx, 80070000h
0x1800f4f1b  mov     edx, 1E5h
0x1800f4f20  jmp     loc_1800F4C53
0x1800f4f25  mov     rcx, [rbp+hKey]; hKey
0x1800f4f29  lea     r13, aExeindexinapp; "ExeIndexInApp"
0x1800f4f30  mov     r12d, 4
0x1800f4f36  lea     r14, [rdi+48h]
0x1800f4f3a  mov     [rsp+60h+samDesired], r12d; cbData
0x1800f4f3f  mov     r9d, r12d; dwType
0x1800f4f42  mov     rdx, r13; lpValueName
0x1800f4f45  mov     [rsp+60h+lpData], r14; lpData
0x1800f4f4a  xor     r8d, r8d; Reserved
0x1800f4f4d  call    cs:__imp_RegSetValueExW
0x1800f4f53  mov     ecx, eax
0x1800f4f55  test    eax, eax
0x1800f4f57  jz      short loc_1800F4F9E
0x1800f4f59  test    eax, eax
0x1800f4f5b  jg      short loc_1800F4F61
0x1800f4f5d  mov     ebx, eax
0x1800f4f5f  jmp     short loc_1800F4F6A
0x1800f4f61  movzx   ebx, cx
0x1800f4f64  or      ebx, 80070000h
0x1800f4f6a  mov     [rsp+60h+var_18], ecx
0x1800f4f6e  mov     eax, 80004005h
0x1800f4f73  test    ebx, ebx
0x1800f4f75  mov     edx, 1E7h
0x1800f4f7a  cmovns  ebx, eax
0x1800f4f7d  mov     rax, [rdi+38h]
0x1800f4f81  mov     [rsp+60h+var_20], rax
0x1800f4f86  mov     eax, [r14]
0x1800f4f89  mov     dword ptr [rsp+60h+var_28], eax
0x1800f4f8d  lea     rax, aFailedToCreate_44; "Failed to create registry value: %ls / "...
0x1800f4f94  mov     [rsp+60h+var_30], r13
  ... truncated ...
```
