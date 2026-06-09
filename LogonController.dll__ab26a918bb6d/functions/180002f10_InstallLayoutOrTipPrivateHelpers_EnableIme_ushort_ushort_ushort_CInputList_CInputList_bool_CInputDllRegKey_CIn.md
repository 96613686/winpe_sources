# InstallLayoutOrTipPrivateHelpers::EnableIme(ushort,ushort *,ushort *,CInputList &,CInputList &,bool,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &)

- ea: `0x180002f10`
- end: `0x180003a72`
- name: `?EnableIme@InstallLayoutOrTipPrivateHelpers@@SAXGPEAG0AEAVCInputList@@1_NAEAVCInputDllRegKey@@33@Z`
- size: `2914`
- prototype: `void __fastcall(unsigned __int16, unsigned __int16 *, unsigned __int16 *, struct CInputList *, struct CInputList *, bool, struct CInputDllRegKey *, struct CInputDllRegKey *, struct CInputDllRegKey *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002f10`
- `0x180005500`

## callees

- `0x180002f10`
- `0x180003a80`
- `0x180004b70`
- `0x180007fc0`
- `0x180008b40`
- `0x1800325c0`
- `0x1800332d0`
- `0x18003b860`
- `0x18003bb00`
- `0x18006c000`
- `0x18006ca64`
- `0x18006caa0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800030ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003500`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003747`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800030ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003500`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003747`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000311c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003569`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000357f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800037ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800038bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000311c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003569`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000357f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800037ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800038bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a3e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800030fc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000354d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003795`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800030fc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000354d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003795`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180003082`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800034d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000371c`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180003082`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800034d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000371c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800037ee`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800037ee`

## string_xrefs

- `0x180003878`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall InstallLayoutOrTipPrivateHelpers::EnableIme(
        unsigned __int16 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct CInputList *a4,
        struct CInputList *a5,
        bool a6,
        struct CInputDllRegKey *a7,
        struct CInputDllRegKey *a8,
        struct CInputDllRegKey *a9)
{
  void *v9; // r12
  unsigned int v10; // ebx
  unsigned int v14; // r14d
  HKEY v15; // rdi
  unsigned int v16; // r15d
  HKEY v17; // rdi
  LSTATUS v18; // eax
  LSTATUS v19; // ebx
  struct InputContainer *v20; // rax
  bool v21; // di
  struct InputContainer *NextEmptyEntry; // r13
  char v23; // cl
  unsigned int v24; // r8d
  unsigned int v25; // edx
  __int64 v26; // rax
  int v27; // ebx
  __int64 v28; // r9
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  __int64 v31; // r8
  struct InputContainer *v32; // rax
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 *v44; // rax
  __int64 v45; // rcx
  __int128 v46; // xmm0
  wchar_t *v47; // rcx
  __int128 v48; // xmm1
  _OWORD *v49; // rax
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  __int128 v54; // xmm0
  __int128 v55; // xmm1
  __int128 v56; // xmm0
  __int128 v57; // xmm1
  __int128 v58; // xmm1
  __int128 v59; // xmm0
  __int128 v60; // xmm1
  HKEY v61; // r15
  HKEY v62; // r12
  LSTATUS v63; // eax
  LSTATUS v64; // edi
  int v65; // edx
  unsigned int v66; // r8d
  __int64 v67; // rcx
  __int64 v68; // r9
  __int64 v69; // rcx
  unsigned int v70; // edx
  __int64 v71; // rcx
  __int64 v72; // r8
  wchar_t *v73; // r13
  wchar_t *v74; // r12
  HKEY v75; // r15
  HKEY v76; // rbx
  HKEY v77; // r14
  LSTATUS v78; // eax
  DWORD v79; // r14d
  unsigned __int16 v80; // r15
  LSTATUS v81; // eax
  __int64 v82; // rdx
  int v83; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v85; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v86[2]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v87; // [rsp+70h] [rbp-90h]
  wchar_t *v88; // [rsp+80h] [rbp-80h]
  struct CInputDllRegKey *v89; // [rsp+88h] [rbp-78h]
  CInputList *v90; // [rsp+90h] [rbp-70h]
  struct CInputDllRegKey *v91; // [rsp+98h] [rbp-68h]
  void **v92; // [rsp+A0h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-58h]
  struct CInputDllRegKey *v94; // [rsp+B0h] [rbp-50h]
  HKEY phkResult[2]; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR Name[4]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR v97[12]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v98[12]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 v99[12]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v100[24]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v101[32]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t String1[88]; // [rsp+150h] [rbp+50h] BYREF
  wchar_t String2[352]; // [rsp+200h] [rbp+100h] BYREF
  WCHAR SubKey[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v9 = 0;
  v90 = a5;
  v10 = 0;
  v94 = a7;
  v91 = a8;
  v89 = a9;
  v87 = a3;
  v88 = a2;
  v14 = a1;
  v86[0] = 0;
  if ( !*(_DWORD *)a4 )
    goto LABEL_3;
  v15 = (HKEY)*((_QWORD *)a4 + 1);
  while ( v15 && v10 < *((_DWORD *)a4 + 1) )
  {
    if ( *(_WORD *)v15 == (_WORD)v14
      && !wcsicmp((const wchar_t *)v15 + 10, a2)
      && !wcsicmp((const wchar_t *)v15 + 49, a3) )
    {
      v9 = v15;
      v86[0] = v15;
      break;
    }
    if ( ++v10 >= *(_DWORD *)a4 )
LABEL_3:
      v15 = 0;
    else
      v15 = (HKEY)(*((_QWORD *)a4 + 1) + 700LL * v10);
  }
  v16 = v14;
  StringCchPrintfW(v98, 9u, L"%08x", v14);
  if ( !(*(unsigned int (__fastcall **)(struct CInputDllRegKey *, _BYTE *, unsigned __int16 *, __int64))(*(_QWORD *)v89 + 8LL))(
          v89,
          v100,
          v98,
          9) )
  {
    StringCchPrintfW(SubKey, 0x104u, L"%s\\LanguageProfile\\0x%08x\\%s", a2, v14, v87);
    v92 = &CInputDllRegKey::`vftable';
    hKey = 0;
    v85 = 0;
    v17 = (HKEY)*((_QWORD *)v94 + 1);
    phkResult[0] = 0;
    if ( v17 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, phkResult) )
      v17 = phkResult[0];
    v18 = RegOpenKeyExW(v17, SubKey, 0, 0x20019u, &v85);
    v19 = v18;
    if ( !v18
      || v18 == 5
      && (dwDisposition = 0, (v19 = RegCreateKeyExW(v17, SubKey, 0, 0, 4u, 0x20019u, 0, &v85, &dwDisposition)) == 0) )
    {
      v19 = 0;
      hKey = v85;
    }
    if ( phkResult[0] )
      RegCloseKey(phkResult[0]);
    if ( !v19 )
    {
      if ( v9 )
      {
        *((_BYTE *)v9 + 16) = 1;
LABEL_29:
        *((_BYTE *)v9 + 17) = 1;
        if ( (_WORD)v14 == 1028 || (unsigned __int16)(v14 - 1041) <= 1u || (_WORD)v14 == 2052 )
        {
          NextEmptyEntry = 0;
          v23 = 0;
          v24 = 0;
          v25 = *(_DWORD *)v90;
          if ( *(_DWORD *)v90 )
            v26 = *((_QWORD *)v90 + 1);
          else
            v26 = 0;
          v27 = 1;
          while ( v26 && v24 < *((_DWORD *)v90 + 1) )
          {
            if ( *(_BYTE *)(v26 + 16) )
              v23 = 1;
            if ( *(_WORD *)v26 == (_WORD)v14 && *(_DWORD *)(v26 + 4) == v14 )
            {
              NextEmptyEntry = (struct InputContainer *)v26;
              break;
            }
            if ( ++v24 >= v25 )
              v26 = 0;
            else
              v26 = *((_QWORD *)v90 + 1) + 700LL * v24;
          }
          if ( !v23 && NextEmptyEntry )
          {
            while ( 1 )
            {
              v28 = ++v24 >= v25 ? 0LL : *((_QWORD *)v90 + 1) + 700LL * v24;
              if ( !v28 || v24 >= *((_DWORD *)v90 + 1) )
                break;
              if ( *(_BYTE *)(v28 + 16) )
              {
                v29 = 5;
                v30 = String2;
                v31 = 5;
                v32 = NextEmptyEntry;
                do
                {
                  v30 += 64;
                  v33 = *(_OWORD *)v32;
                  v34 = *((_OWORD *)v32 + 1);
                  v32 = (struct InputContainer *)((char *)v32 + 128);
                  *((_OWORD *)v30 - 8) = v33;
                  v35 = *((_OWORD *)v32 - 6);
                  *((_OWORD *)v30 - 7) = v34;
                  v36 = *((_OWORD *)v32 - 5);
                  *((_OWORD *)v30 - 6) = v35;
                  v37 = *((_OWORD *)v32 - 4);
                  *((_OWORD *)v30 - 5) = v36;
                  v38 = *((_OWORD *)v32 - 3);
                  *((_OWORD *)v30 - 4) = v37;
                  v39 = *((_OWORD *)v32 - 2);
                  *((_OWORD *)v30 - 3) = v38;
                  v40 = *((_OWORD *)v32 - 1);
                  *((_OWORD *)v30 - 2) = v39;
                  *((_OWORD *)v30 - 1) = v40;
                  --v31;
                }
                while ( v31 );
                v41 = *((_OWORD *)v32 + 1);
                *(_OWORD *)v30 = *(_OWORD *)v32;
                v42 = *((_OWORD *)v32 + 2);
                *((_OWORD *)v30 + 1) = v41;
                v43 = *(_OWORD *)((char *)v32 + 44);
                v44 = (__int128 *)v28;
                *((_OWORD *)v30 + 2) = v42;
                *(_OWORD *)(v30 + 22) = v43;
                v45 = 5;
                do
                {
                  NextEmptyEntry = (struct InputContainer *)((char *)NextEmptyEntry + 128);
                  v46 = *v44;
                  v44 += 8;
                  *((_OWORD *)NextEmptyEntry - 8) = v46;
                  *((_OWORD *)NextEmptyEntry - 7) = *(v44 - 7);
                  *((_OWORD *)NextEmptyEntry - 6) = *(v44 - 6);
                  *((_OWORD *)NextEmptyEntry - 5) = *(v44 - 5);
                  *((_OWORD *)NextEmptyEntry - 4) = *(v44 - 4);
                  *((_OWORD *)NextEmptyEntry - 3) = *(v44 - 3);
                  *((_OWORD *)NextEmptyEntry - 2) = *(v44 - 2);
                  *((_OWORD *)NextEmptyEntry - 1) = *(v44 - 1);
                  --v45;
                }
                while ( v45 );
                v47 = String2;
                *(_OWORD *)NextEmptyEntry = *v44;
                *((_OWORD *)NextEmptyEntry + 1) = v44[1];
                *((_OWORD *)NextEmptyEntry + 2) = v44[2];
                v48 = *(__int128 *)((char *)v44 + 44);
                v49 = (_OWORD *)v28;
                *(_OWORD *)((char *)NextEmptyEntry + 44) = v48;
                do
                {
                  v49 += 8;
                  v50 = *(_OWORD *)v47;
                  v51 = *((_OWORD *)v47 + 1);
                  v47 += 64;
                  *(v49 - 8) = v50;
                  v52 = *((_OWORD *)v47 - 6);
                  *(v49 - 7) = v51;
                  v53 = *((_OWORD *)v47 - 5);
                  *(v49 - 6) = v52;
                  v54 = *((_OWORD *)v47 - 4);
                  *(v49 - 5) = v53;
                  v55 = *((_OWORD *)v47 - 3);
                  *(v49 - 4) = v54;
                  v56 = *((_OWORD *)v47 - 2);
                  *(v49 - 3) = v55;
                  v57 = *((_OWORD *)v47 - 1);
                  *(v49 - 2) = v56;
                  *(v49 - 1) = v57;
                  --v29;
                }
                while ( v29 );
                NextEmptyEntry = (struct InputContainer *)v28;
                v58 = *((_OWORD *)v47 + 1);
                *v49 = *(_OWORD *)v47;
                v59 = *((_OWORD *)v47 + 2);
                v49[1] = v58;
                v60 = *(_OWORD *)(v47 + 22);
                v49[2] = v59;
                *(_OWORD *)((char *)v49 + 44) = v60;
                break;
              }
            }
          }
          if ( (((_WORD)v14 - 0x2000) & 0xF3FF) == 0 && (_WORD)v14 != 11264
            || (_WORD)v14 == 11264
            || (StringCchPrintfW(v99, 9u, L"%08x", v14),
                !(*(unsigned int (__fastcall **)(struct CInputDllRegKey *, _BYTE *, unsigned __int16 *, __int64))(*(_QWORD *)v89 + 8LL))(
                   v89,
                   v101,
                   v99,
                   9)) )
          {
            StringCchPrintfW(v97, 9u, L"%08x", v14);
            v61 = 0;
            v85 = 0;
            phkResult[0] = 0;
            v62 = (HKEY)*((_QWORD *)v91 + 1);
            if ( v62 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, phkResult) )
              v62 = phkResult[0];
            v63 = RegOpenKeyExW(v62, v97, 0, 0x20019u, &v85);
            v64 = v63;
            if ( !v63
              || v63 == 5
              && (dwDisposition = 0, (v64 = RegCreateKeyExW(v62, v97, 0, 0, 4u, 0x20019u, 0, &v85, &dwDisposition)) == 0) )
            {
              v61 = v85;
              v64 = 0;
            }
            if ( phkResult[0] )
              RegCloseKey(phkResult[0]);
            if ( v64 )
            {
              if ( v61 )
                RegCloseKey(v61);
            }
            else
            {
              if ( v61 )
                RegCloseKey(v61);
              if ( NextEmptyEntry || (NextEmptyEntry = CInputList::GetNextEmptyEntry((const void **)v90)) != 0 )
              {
                *((_DWORD *)NextEmptyEntry + 3) = 1;
                *(_WORD *)NextEmptyEntry = v14;
                *((_DWORD *)NextEmptyEntry + 1) = v14;
                v16 = v14;
                *((_WORD *)NextEmptyEntry + 8) = 257;
                v65 = 1;
                *((_BYTE *)NextEmptyEntry + 18) = 1;
                v66 = 0;
                *((_WORD *)NextEmptyEntry + 10) = 123;
                do
                {
                  if ( v65 >= 36 )
                    break;
                  v67 = *((unsigned __int8 *)qword_1800B0EC0 + (int)v66);
                  v68 = 2LL * v65;
                  if ( (_BYTE)v67 == 45 )
                  {
                    *(_WORD *)((char *)NextEmptyEntry + v68 + 20) = 45;
                  }
                  else
                  {
                    ++v65;
                    *(_WORD *)((char *)NextEmptyEntry + v68 + 20) = word_1800B0E90[(unsigned __int64)*((unsigned __int8 *)&GUID_NULL.Data1 + v67) >> 4];
                    *((_WORD *)NextEmptyEntry + v65 + 10) = word_1800B0E90[*((_BYTE *)&_ImageBase + v67 + 709696) & 0xF];
                  }
                  ++v66;
                  ++v65;
                }
                while ( v66 < 0x14 );
                v69 = v65;
                v70 = 0;
                *(_DWORD *)((char *)NextEmptyEntry + 2 * v69 + 20) = 125;
                *((_WORD *)NextEmptyEntry + 49) = 123;
                do
                {
                  if ( v27 >= 36 )
                    break;
                  v71 = *((unsigned __int8 *)qword_1800B0EC0 + (int)v70);
                  v72 = 2LL * v27;
                  if ( (_BYTE)v71 == 45 )
                  {
                    *(_WORD *)((char *)NextEmptyEntry + v72 + 98) = 45;
                  }
                  else
                  {
                    ++v27;
                    *(_WORD *)((char *)NextEmptyEntry + v72 + 98) = word_1800B0E90[(unsigned __int64)*((unsigned __int8 *)&GUID_NULL.Data1 + v71) >> 4];
                    *((_WORD *)NextEmptyEntry + v27 + 49) = word_1800B0E90[*((_BYTE *)&_ImageBase + v71 + 709696) & 0xF];
                  }
                  ++v70;
                  ++v27;
                }
                while ( v70 < 0x14 );
                v21 = a6;
                *(_DWORD *)((char *)NextEmptyEntry + 2 * v27 + 98) = 125;
                if ( !a6 )
                  goto LABEL_93;
LABEL_118:
                if ( *((_BYTE *)v86[0] + 19)
                  && (int)((__int64 (__fastcall *)(_QWORD, wchar_t *, __int64))pfnBcp47BufferFromLcid)(v16, String2, 85) >= 0 )
                {
                  v83 = ((__int64 (__fastcall *)(__int64, wchar_t *))pfnAppendUserLanguages)(59, String2);
                  v73 = v87;
                  v74 = v88;
                  if ( v83 >= 0 )
                  {
                    StringCchPrintfW(String1, 0x57u, L"%04X:%s%s", v16, v88, v87);
                    ((void (__fastcall *)(wchar_t *, __int64, wchar_t *))pfnAppendUserLanguageInputMethods)(
                      String2,
                      59,
                      String1);
                  }
                  goto LABEL_94;
                }
LABEL_93:
                v73 = v87;
                v74 = v88;
LABEL_94:
                v75 = hKey;
                v76 = 0;
                v85 = 0;
                v77 = hKey;
                v86[0] = 0;
                if ( hKey == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, v86) )
                  v77 = v86[0];
                v78 = RegOpenKeyExW(v77, L"DependentProfileForEnabling", 0, 0x20019u, &v85);
                if ( !v78
                  || v78 == 5
                  && (dwDisposition = 0,
                      !RegCreateKeyExW(v77, L"DependentProfileForEnabling", 0, 0, 4u, 0x20019u, 0, &v85, &dwDisposition)) )
                {
                  v76 = v85;
                }
                if ( v86[0] )
                  RegCloseKey(v86[0]);
                v79 = 0;
                if ( v76 )
                {
LABEL_104:
                  v80 = 0;
                  while ( 1 )
                  {
                    dwDisposition = 3;
                    v81 = RegEnumKeyExW(v76, v79, Name, &dwDisposition, 0, 0, 0, 0);
                    v82 = 2;
                    if ( v81 )
                      v82 = 0;
                    Name[v82] = 0;
                    if ( v81 )
                      break;
                    v86[1] = 0;
                    v86[0] = (HKEY)&CInputDllRegKey::`vftable';
                    ++v79;
                    if ( !CInputDllRegKey::Open((CInputDllRegKey *)v86, v76, Name, 0x20019u) )
                    {
                      if ( !CInputDllRegKey::QueryValueCch(
                              (CInputDllRegKey *)v86,
                              (unsigned __int16 *)phkResult,
                              L"LangId",
                              8u) )
                        v80 = o_wcstoul_0((const wchar_t *)phkResult, 0, 16);
                      if ( CInputDllRegKey::QueryValueCch((CInputDllRegKey *)v86, String2, L"CLSID", 0x40u)
                        || CInputDllRegKey::QueryValueCch((CInputDllRegKey *)v86, String1, L"Profile", 0x40u) )
                      {
                        v86[0] = (HKEY)&CInputDllRegKey::`vftable';
                        CInputDllRegKey::Close((CInputDllRegKey *)v86);
                        goto LABEL_104;
                      }
                      if ( wcsicmp(String2, v74) || wcsicmp(String1, v73) )
                        InstallLayoutOrTipPrivateHelpers::EnableIme(v80, String2, String1, a4, v90, v21, v94, v91, v89);
                      v80 = 0;
                    }
                    v86[0] = (HKEY)&CInputDllRegKey::`vftable';
                    CInputDllRegKey::Close((CInputDllRegKey *)v86);
                  }
                  RegCloseKey(v76);
                  v75 = hKey;
                }
                if ( v75 )
                  RegCloseKey(v75);
                return;
              }
            }
            v16 = v14;
          }
          v21 = a6;
        }
        else
        {
          v21 = a6;
          InstallLayoutOrTipPrivateHelpers::EnableKeyboard(v14, 0x409u, 1, v90, a6, v91, v89);
        }
        if ( !v21 )
          goto LABEL_93;
        goto LABEL_118;
      }
      v20 = CInputList::GetNextEmptyEntry((const void **)a4);
      v86[0] = (HKEY)v20;
      v9 = v20;
      if ( v20 )
      {
        *(_WORD *)v20 = v14;
        if ( (int)StringCchCopyW((unsigned __int16 *)v20 + 10, 0x27u, a2) >= 0
          && (int)StringCchCopyW((unsigned __int16 *)v9 + 49, 0x27u, v87) >= 0 )
        {
          *((_DWORD *)v9 + 3) = 2;
          *((_BYTE *)v9 + 16) = 1;
          *((_BYTE *)v9 + 19) = InstallLayoutOrTipPrivateHelpers::IsTfCatTip((unsigned __int16 *)v9 + 10);
          goto LABEL_29;
        }
      }
    }
    CInputDllRegKey::Close((CInputDllRegKey *)&v92);
  }
}

```

## disassembly

```asm
0x180002f10  push    rbp
0x180002f12  push    rbx
0x180002f13  push    rsi
0x180002f14  push    rdi
0x180002f15  push    r12
0x180002f17  push    r13
0x180002f19  push    r14
0x180002f1b  push    r15
0x180002f1d  lea     rbp, [rsp-5E8h]
0x180002f25  sub     rsp, 6E8h
0x180002f2c  mov     rax, cs:__security_cookie
0x180002f33  xor     rax, rsp
0x180002f36  mov     [rbp+620h+var_50], rax
0x180002f3d  mov     rax, [rbp+620h+arg_20]
0x180002f44  xor     r12d, r12d
0x180002f47  mov     [rbp+620h+var_690], rax
0x180002f4b  xor     ebx, ebx
0x180002f4d  mov     rsi, r9
0x180002f50  mov     rax, [rbp+620h+arg_30]
0x180002f57  mov     r15, r8
0x180002f5a  mov     [rbp+620h+var_670], rax
0x180002f5e  mov     r13, rdx
0x180002f61  mov     rax, [rbp+620h+arg_38]
0x180002f68  mov     [rbp+620h+var_688], rax
0x180002f6c  mov     rax, [rbp+620h+arg_40]
0x180002f73  mov     [rbp+620h+var_698], rax
0x180002f77  mov     [rsp+720h+var_6B0], r8
0x180002f7c  mov     [rbp+620h+var_6A0], rdx
0x180002f80  movzx   r14d, cx
0x180002f84  mov     [rsp+720h+var_6C0], r12
0x180002f89  cmp     [r9], ebx
0x180002f8c  jbe     short loc_180002F94
0x180002f8e  mov     rdi, [r9+8]
0x180002f92  jmp     short loc_180002F96
0x180002f94  xor     edi, edi
0x180002f96  test    rdi, rdi
0x180002f99  jz      short loc_180002FE3
0x180002f9b  cmp     ebx, [rsi+4]
0x180002f9e  jnb     short loc_180002FE3
0x180002fa0  cmp     [rdi], r14w
0x180002fa4  jnz     short loc_180002FC6
0x180002fa6  lea     rcx, [rdi+14h]; String1
0x180002faa  mov     rdx, r13; String2
0x180002fad  call    _wcsicmp
0x180002fb2  test    eax, eax
0x180002fb4  jnz     short loc_180002FC6
0x180002fb6  lea     rcx, [rdi+62h]; String1
0x180002fba  mov     rdx, r15; String2
0x180002fbd  call    _wcsicmp
0x180002fc2  test    eax, eax
0x180002fc4  jz      short loc_180002FDB
0x180002fc6  inc     ebx
0x180002fc8  cmp     ebx, [rsi]
0x180002fca  jnb     short loc_180002F94
0x180002fcc  mov     eax, ebx
0x180002fce  imul    rdi, rax, 2BCh
0x180002fd5  add     rdi, [rsi+8]
0x180002fd9  jmp     short loc_180002F96
0x180002fdb  mov     r12, rdi
0x180002fde  mov     [rsp+720h+var_6C0], rdi
0x180002fe3  mov     r9d, r14d
0x180002fe6  lea     r8, a08x_1; "%08x"
0x180002fed  mov     edx, 9; unsigned __int64
0x180002ff2  lea     rcx, [rbp+620h+var_638]; unsigned __int16 *
0x180002ff6  mov     r15d, r14d
0x180002ff9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002ffe  mov     rcx, [rbp+620h+var_698]
0x180003002  lea     r8, [rbp+620h+var_638]
0x180003006  mov     r9d, 9
0x18000300c  lea     rdx, [rbp+620h+var_608]
0x180003010  mov     rax, [rcx]
0x180003013  mov     rax, [rax+8]
0x180003017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000301c  test    eax, eax
0x18000301e  jnz     loc_180003A4F
0x180003024  mov     rax, [rsp+720h+var_6B0]
0x180003029  lea     r8, aSLanguageprofi; "%s\\LanguageProfile\\0x%08x\\%s"
0x180003030  mov     qword ptr [rsp+720h+samDesired], rax
0x180003035  lea     rcx, [rbp+620h+SubKey]; unsigned __int16 *
0x18000303c  mov     r9, r13
0x18000303f  mov     dword ptr [rsp+720h+var_700], r14d
0x180003044  mov     edx, 104h; unsigned __int64
0x180003049  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000304e  mov     rdi, [rbp+620h+var_670]
0x180003052  lea     rax, ??_7CInputDllRegKey@@6B@; const CInputDllRegKey::`vftable'
0x180003059  mov     [rbp+620h+var_680], rax
0x18000305d  xor     eax, eax
0x18000305f  mov     [rbp+620h+hKey], rax
0x180003063  mov     [rsp+720h+var_6C8], rax
0x180003068  mov     rdi, [rdi+8]
0x18000306c  mov     [rbp+620h+phkResult], rax
0x180003070  cmp     rdi, 0FFFFFFFF80000001h
0x180003077  jnz     short loc_18000308F
0x180003079  lea     rdx, [rbp+620h+phkResult]; phkResult
0x18000307d  mov     ecx, 20019h; samDesired
0x180003082  call    cs:__imp_RegOpenCurrentUser
0x180003088  test    eax, eax
0x18000308a  cmovz   rdi, [rbp+620h+phkResult]
0x18000308f  lea     rax, [rsp+720h+var_6C8]
0x180003094  mov     r9d, 20019h; samDesired
0x18000309a  xor     r8d, r8d; ulOptions
0x18000309d  mov     [rsp+720h+var_700], rax; phkResult
0x1800030a2  lea     rdx, [rbp+620h+SubKey]; lpSubKey
0x1800030a9  mov     rcx, rdi; hKey
0x1800030ac  call    cs:__imp_RegOpenKeyExW
0x1800030b2  mov     ebx, eax
0x1800030b4  test    eax, eax
0x1800030b6  jz      short loc_180003108
0x1800030b8  cmp     eax, 5
0x1800030bb  jnz     short loc_180003113
0x1800030bd  xor     ecx, ecx
0x1800030bf  lea     rax, [rsp+720h+dwDisposition]
0x1800030c4  mov     [rsp+720h+lpdwDisposition], rax; lpdwDisposition
0x1800030c9  lea     rdx, [rbp+620h+SubKey]; lpSubKey
0x1800030d0  lea     rax, [rsp+720h+var_6C8]
0x1800030d5  mov     [rsp+720h+dwDisposition], ecx
0x1800030d9  mov     [rsp+720h+var_6E8], rax; phkResult
0x1800030de  xor     r9d, r9d; lpClass
0x1800030e1  mov     [rsp+720h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x1800030e6  xor     r8d, r8d; Reserved
0x1800030e9  mov     [rsp+720h+samDesired], 20019h; samDesired
0x1800030f1  mov     rcx, rdi; hKey
0x1800030f4  mov     dword ptr [rsp+720h+var_700], 4; dwOptions
0x1800030fc  call    cs:__imp_RegCreateKeyExW
0x180003102  mov     ebx, eax
0x180003104  test    eax, eax
0x180003106  jnz     short loc_180003113
0x180003108  mov     rax, [rsp+720h+var_6C8]
0x18000310d  xor     ebx, ebx
0x18000310f  mov     [rbp+620h+hKey], rax
0x180003113  mov     rcx, [rbp+620h+phkResult]; hKey
0x180003117  test    rcx, rcx
0x18000311a  jz      short loc_180003122
0x18000311c  call    cs:__imp_RegCloseKey
0x180003122  test    ebx, ebx
0x180003124  jnz     loc_180003A46
0x18000312a  test    r12, r12
0x18000312d  jz      short loc_180003137
0x18000312f  mov     byte ptr [r12+10h], 1
0x180003135  jmp     short loc_1800031A7
0x180003137  mov     rcx, rsi; this
0x18000313a  call    ?GetNextEmptyEntry@CInputList@@QEAAPEAUInputContainer@@XZ; CInputList::GetNextEmptyEntry(void)
0x18000313f  mov     [rsp+720h+var_6C0], rax
0x180003144  mov     r12, rax
0x180003147  test    rax, rax
0x18000314a  jz      loc_180003A46
0x180003150  mov     r8, r13; unsigned __int16 *
0x180003153  mov     [rax], r14w
0x180003157  mov     edx, 27h ; '''; unsigned __int64
0x18000315c  lea     rcx, [rax+14h]; unsigned __int16 *
0x180003160  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003165  test    eax, eax
0x180003167  js      loc_180003A46
0x18000316d  mov     r8, [rsp+720h+var_6B0]; unsigned __int16 *
0x180003172  lea     rcx, [r12+62h]; unsigned __int16 *
0x180003177  mov     edx, 27h ; '''; unsigned __int64
0x18000317c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003181  test    eax, eax
0x180003183  js      loc_180003A46
0x180003189  lea     rcx, [r12+14h]; unsigned __int16 *
0x18000318e  mov     dword ptr [r12+0Ch], 2
0x180003197  mov     byte ptr [r12+10h], 1
0x18000319d  call    ?IsTfCatTip@InstallLayoutOrTipPrivateHelpers@@SA_NPEAG@Z; InstallLayoutOrTipPrivateHelpers::IsTfCatTip(ushort *)
0x1800031a2  mov     [r12+13h], al
0x1800031a7  mov     eax, 404h
0x1800031ac  mov     byte ptr [r12+11h], 1
0x1800031b2  cmp     r14w, ax
0x1800031b6  jz      short loc_18000320D
0x1800031b8  mov     ecx, 411h
0x1800031bd  movzx   eax, r14w
0x1800031c1  sub     ax, cx
0x1800031c4  cmp     ax, 1
0x1800031c8  jbe     short loc_18000320D
0x1800031ca  mov     eax, 804h
0x1800031cf  cmp     r14w, ax
0x1800031d3  jz      short loc_18000320D
0x1800031d5  mov     rax, [rbp+620h+var_698]
0x1800031d9  mov     r8b, 1; bool
0x1800031dc  mov     r12, [rbp+620h+var_688]
0x1800031e0  mov     edx, 409h; unsigned int
0x1800031e5  movzx   edi, [rbp+620h+arg_28]
0x1800031ec  movzx   ecx, r14w; unsigned __int16
0x1800031f0  mov     r9, [rbp+620h+var_690]; struct CInputList *
0x1800031f4  mov     [rsp+720h+lpSecurityAttributes], rax; struct CInputDllRegKey *
0x1800031f9  mov     qword ptr [rsp+720h+samDesired], r12; struct CInputDllRegKey *
0x1800031fe  mov     byte ptr [rsp+720h+var_700], dil; bool
0x180003203  call    ?EnableKeyboard@InstallLayoutOrTipPrivateHelpers@@SAXGK_NAEAVCInputList@@0AEAVCInputDllRegKey@@2@Z; InstallLayoutOrTipPrivateHelpers::EnableKeyboard(ushort,ulong,bool,CInputList &,bool,CInputDllRegKey &,CInputDllRegKey &)
0x180003208  jmp     loc_1800038CB
0x18000320d  mov     r10, [rbp+620h+var_690]
0x180003211  xor     r13d, r13d
0x180003214  xor     cl, cl
0x180003216  xor     r8d, r8d
0x180003219  mov     edx, [r10]
0x18000321c  test    edx, edx
0x18000321e  jz      short loc_180003226
0x180003220  mov     rax, [r10+8]
0x180003224  jmp     short loc_180003228
0x180003226  xor     eax, eax
0x180003228  mov     ebx, 1
0x18000322d  test    rax, rax
0x180003230  jz      short loc_18000326D
0x180003232  cmp     r8d, [r10+4]
0x180003236  jnb     short loc_18000326D
0x180003238  cmp     [rax+10h], r13b
0x18000323c  movzx   ecx, cl
0x18000323f  cmovnz  ecx, ebx
0x180003242  cmp     [rax], r14w
0x180003246  jnz     short loc_18000324E
0x180003248  cmp     [rax+4], r14d
0x18000324c  jz      short loc_18000326A
0x18000324e  inc     r8d
0x180003251  cmp     r8d, edx
0x180003254  jnb     short loc_180003266
0x180003256  mov     eax, r8d
0x180003259  imul    rax, 2BCh
0x180003260  add     rax, [r10+8]
0x180003264  jmp     short loc_18000322D
0x180003266  xor     eax, eax
0x180003268  jmp     short loc_18000322D
0x18000326a  mov     r13, rax
0x18000326d  test    cl, cl
0x18000326f  jnz     loc_180003435
0x180003275  test    r13, r13
0x180003278  jz      loc_180003435
0x18000327e  inc     r8d
0x180003281  cmp     r8d, edx
0x180003284  jnb     short loc_180003296
0x180003286  mov     eax, r8d
0x180003289  imul    r9, rax, 2BCh
0x180003290  add     r9, [r10+8]
0x180003294  jmp     short loc_180003299
0x180003296  xor     r9d, r9d
0x180003299  test    r9, r9
0x18000329c  jz      loc_180003435
0x1800032a2  cmp     r8d, [r10+4]
0x1800032a6  jnb     loc_180003435
0x1800032ac  cmp     byte ptr [r9+10h], 0
0x1800032b1  jz      short loc_18000327E
0x1800032b3  mov     edx, 5
0x1800032b8  lea     rcx, [rbp+620h+String2]
0x1800032bf  mov     r8d, edx
0x1800032c2  mov     rax, r13
0x1800032c5  lea     rcx, [rcx+80h]
0x1800032cc  movups  xmm0, xmmword ptr [rax]
0x1800032cf  movups  xmm1, xmmword ptr [rax+10h]
0x1800032d3  lea     rax, [rax+80h]
0x1800032da  movups  xmmword ptr [rcx-80h], xmm0
0x1800032de  movups  xmm0, xmmword ptr [rax-60h]
0x1800032e2  movups  xmmword ptr [rcx-70h], xmm1
0x1800032e6  movups  xmm1, xmmword ptr [rax-50h]
0x1800032ea  movups  xmmword ptr [rcx-60h], xmm0
0x1800032ee  movups  xmm0, xmmword ptr [rax-40h]
0x1800032f2  movups  xmmword ptr [rcx-50h], xmm1
0x1800032f6  movups  xmm1, xmmword ptr [rax-30h]
0x1800032fa  movups  xmmword ptr [rcx-40h], xmm0
0x1800032fe  movups  xmm0, xmmword ptr [rax-20h]
0x180003302  movups  xmmword ptr [rcx-30h], xmm1
0x180003306  movups  xmm1, xmmword ptr [rax-10h]
0x18000330a  movups  xmmword ptr [rcx-20h], xmm0
0x18000330e  movups  xmmword ptr [rcx-10h], xmm1
0x180003312  sub     r8, rbx
0x180003315  jnz     short loc_1800032C5
0x180003317  movups  xmm0, xmmword ptr [rax]
0x18000331a  movups  xmm1, xmmword ptr [rax+10h]
0x18000331e  movups  xmmword ptr [rcx], xmm0
0x180003321  movups  xmm0, xmmword ptr [rax+20h]
0x180003325  movups  xmmword ptr [rcx+10h], xmm1
0x180003329  movups  xmm1, xmmword ptr [rax+2Ch]
0x18000332d  mov     rax, r9
0x180003330  movups  xmmword ptr [rcx+20h], xmm0
0x180003334  movups  xmmword ptr [rcx+2Ch], xmm1
0x180003338  mov     rcx, rdx
0x18000333b  lea     r13, [r13+80h]
0x180003342  movups  xmm0, xmmword ptr [rax]
0x180003345  lea     rax, [rax+80h]
0x18000334c  movups  xmmword ptr [r13-80h], xmm0
0x180003351  movups  xmm1, xmmword ptr [rax-70h]
0x180003355  movups  xmmword ptr [r13-70h], xmm1
0x18000335a  movups  xmm0, xmmword ptr [rax-60h]
0x18000335e  movups  xmmword ptr [r13-60h], xmm0
0x180003363  movups  xmm1, xmmword ptr [rax-50h]
0x180003367  movups  xmmword ptr [r13-50h], xmm1
0x18000336c  movups  xmm0, xmmword ptr [rax-40h]
0x180003370  movups  xmmword ptr [r13-40h], xmm0
0x180003375  movups  xmm1, xmmword ptr [rax-30h]
0x180003379  movups  xmmword ptr [r13-30h], xmm1
0x18000337e  movups  xmm0, xmmword ptr [rax-20h]
0x180003382  movups  xmmword ptr [r13-20h], xmm0
0x180003387  movups  xmm1, xmmword ptr [rax-10h]
0x18000338b  movups  xmmword ptr [r13-10h], xmm1
0x180003390  sub     rcx, rbx
0x180003393  jnz     short loc_18000333B
0x180003395  movups  xmm0, xmmword ptr [rax]
0x180003398  lea     rcx, [rbp+620h+String2]
0x18000339f  movups  xmmword ptr [r13+0], xmm0
0x1800033a4  movups  xmm1, xmmword ptr [rax+10h]
0x1800033a8  movups  xmmword ptr [r13+10h], xmm1
0x1800033ad  movups  xmm0, xmmword ptr [rax+20h]
0x1800033b1  movups  xmmword ptr [r13+20h], xmm0
0x1800033b6  movups  xmm1, xmmword ptr [rax+2Ch]
  ... truncated ...
```
