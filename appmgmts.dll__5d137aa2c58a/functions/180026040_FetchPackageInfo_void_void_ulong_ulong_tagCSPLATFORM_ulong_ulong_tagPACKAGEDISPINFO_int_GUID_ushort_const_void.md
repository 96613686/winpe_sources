# FetchPackageInfo(void *,void *,ulong,ulong,tagCSPLATFORM *,ulong,ulong *,tagPACKAGEDISPINFO *,int *,_GUID *,ushort const *,void *)

- ea: `0x180026040`
- end: `0x180026d56`
- name: `?FetchPackageInfo@@YAJPEAX0KKPEAUtagCSPLATFORM@@KPEAKPEAUtagPACKAGEDISPINFO@@PEAHPEAU_GUID@@PEBG0@Z`
- size: `3350`
- prototype: `bool __fastcall(void *, void *, unsigned int, int, struct tagCSPLATFORM *, unsigned int, unsigned int *, struct tagPACKAGEDISPINFO *, int *, struct _GUID *, unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800283e0`

## callees

- `0x1800016d0`
- `0x180002024`
- `0x180002b14`
- `0x180013530`
- `0x18001b1a0`
- `0x18001c0e0`
- `0x18001c204`
- `0x18001e71c`
- `0x18001e754`
- `0x1800234b0`
- `0x180024b90`
- `0x180024ea0`
- `0x180024f20`
- `0x180026040`
- `0x180026d5c`
- `0x180027a58`
- `0x180027e1c`
- `0x180027e90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180026bd7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180026bd7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180026b46`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180026b46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026676`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800269ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026676`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800269ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026aba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026aba`
- `adsldpc!ADSIGetNextRow` at `0x180026139`
- `adsldpc!ADSIGetNextRow` at `0x180026139`
- `adsldpc!ADSIGetFirstRow` at `0x18002612b`
- `adsldpc!ADSIGetFirstRow` at `0x18002612b`
- `adsldpc!ADSIFreeColumn` at `0x1800261d9`
- `adsldpc!ADSIFreeColumn` at `0x18002623a`
- `adsldpc!ADSIFreeColumn` at `0x1800263b8`
- `adsldpc!ADSIFreeColumn` at `0x180026405`
- `adsldpc!ADSIFreeColumn` at `0x1800264d2`
- `adsldpc!ADSIFreeColumn` at `0x1800265db`
- `adsldpc!ADSIFreeColumn` at `0x180026732`
- `adsldpc!ADSIFreeColumn` at `0x1800267af`
- `adsldpc!ADSIFreeColumn` at `0x18002680c`
- `adsldpc!ADSIFreeColumn` at `0x18002686f`
- `adsldpc!ADSIFreeColumn` at `0x1800268c3`
- `adsldpc!ADSIFreeColumn` at `0x180026923`
- `adsldpc!ADSIFreeColumn` at `0x180026a22`
- `adsldpc!ADSIFreeColumn` at `0x180026aa2`
- `adsldpc!ADSIFreeColumn` at `0x1800261d9`
- `adsldpc!ADSIFreeColumn` at `0x18002623a`
- `adsldpc!ADSIFreeColumn` at `0x1800263b8`
- `adsldpc!ADSIFreeColumn` at `0x180026405`
- `adsldpc!ADSIFreeColumn` at `0x1800264d2`
- `adsldpc!ADSIFreeColumn` at `0x1800265db`
- `adsldpc!ADSIFreeColumn` at `0x180026732`
- `adsldpc!ADSIFreeColumn` at `0x1800267af`
- `adsldpc!ADSIFreeColumn` at `0x18002680c`
- `adsldpc!ADSIFreeColumn` at `0x18002686f`
- `adsldpc!ADSIFreeColumn` at `0x1800268c3`
- `adsldpc!ADSIFreeColumn` at `0x180026923`
- `adsldpc!ADSIFreeColumn` at `0x180026a22`
- `adsldpc!ADSIFreeColumn` at `0x180026aa2`

## string_xrefs

- `0x1800267c9`: `lastUpdateSequence`
- `0x180026cb2`: `lastUpdateSequence`
- `0x180026762`: `msiScriptPath`
- `0x1800263c9`: `installUiLevel`

## pseudocode

```c
bool __fastcall FetchPackageInfo(
        void *a1,
        void *a2,
        unsigned int a3,
        int a4,
        struct tagCSPLATFORM *a5,
        unsigned int a6,
        unsigned int *a7,
        struct tagPACKAGEDISPINFO *a8,
        int *a9,
        struct _GUID *a10,
        unsigned __int16 *a11,
        void *a12)
{
  unsigned int *v12; // r15
  unsigned int v13; // ebx
  int *v14; // rdi
  struct tagPACKAGEDISPINFO *v15; // rsi
  void *v16; // r12
  void *v17; // r14
  bool result; // al
  int Row; // eax
  int v20; // edi
  int v21; // r13d
  int v22; // eax
  ADS_BOOLEAN Boolean; // r15d
  unsigned int v24; // edx
  int v25; // eax
  __int64 v26; // r9
  unsigned int v27; // eax
  int v28; // eax
  ADS_BOOLEAN v29; // ecx
  int v30; // eax
  ADS_BOOLEAN v31; // ecx
  unsigned __int16 v32; // bx
  int v33; // r12d
  __int64 v34; // r9
  const unsigned __int16 *v35; // r8
  unsigned int v36; // ecx
  int Categories; // eax
  unsigned int v38; // r13d
  _DWORD *v39; // r12
  struct tagCSPLATFORM *v40; // r14
  BOOL v41; // r9d
  unsigned int v42; // r10d
  int v43; // r8d
  unsigned int v44; // ebx
  unsigned int v45; // eax
  int v46; // r10d
  const unsigned __int16 *v47; // r8
  void *v48; // rdi
  int v49; // ebx
  int v50; // r12d
  int v51; // eax
  const unsigned __int16 *DNString; // rcx
  int v53; // eax
  ADS_BOOLEAN v54; // ecx
  _QWORD *v55; // rbx
  int RsopSpecificAttributes; // eax
  bool v57; // zf
  unsigned int *v58; // r15
  void *v59; // rcx
  unsigned int v60; // r12d
  _QWORD *v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rbx
  __int64 v65; // r13
  void *v66; // rax
  wchar_t *v67; // rax
  __int64 v68; // r10
  struct ads_search_column *v69; // r8
  __int64 v70; // rcx
  __int64 v71; // r9
  struct ads_search_column *v72; // rcx
  __int64 v73; // rax
  __int64 v74; // rbx
  const wchar_t *v75; // r13
  unsigned int v76; // eax
  __int64 v77; // rdx
  unsigned __int16 *v78; // rcx
  unsigned __int16 *v79; // rax
  struct ads_search_column *v80; // [rsp+20h] [rbp-E0h]
  struct ads_search_column v83; // [rsp+48h] [rbp-B8h] BYREF
  ADS_BOOLEAN v84; // [rsp+70h] [rbp-90h]
  __int64 v85; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v86; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  int v88; // [rsp+90h] [rbp-70h]
  int v89; // [rsp+94h] [rbp-6Ch] BYREF
  struct tagCSPLATFORM *v90; // [rsp+98h] [rbp-68h]
  void *v91; // [rsp+A0h] [rbp-60h]
  int *v92; // [rsp+A8h] [rbp-58h]
  struct tagCSPLATFORM v93; // [rsp+B0h] [rbp-50h] BYREF
  void *v94; // [rsp+C0h] [rbp-40h]
  wchar_t *EndPtr; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v96; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v97; // [rsp+D8h] [rbp-28h]
  struct ads_search_column String[2]; // [rsp+E0h] [rbp-20h] BYREF

  v12 = a7;
  v13 = a3;
  v14 = a9;
  v15 = a8;
  v16 = a2;
  v90 = a5;
  v17 = a1;
  v97 = a11;
  v94 = a12;
  result = 0;
  v88 = a4;
  v91 = a1;
  v92 = a9;
  v93 = 0;
  memset(&v83, 0, sizeof(v83));
  v89 = 0;
  *a7 = 0;
  if ( !a6 )
    return result;
  memset_0(a8, 0, 0xD0u);
  while ( 1 )
  {
    ReleasePackageInfo(v15);
    memset_0(v15, 0, 0xD0u);
    if ( !*v14 || *v12 )
    {
      Row = ADSIGetNextRow(v17, v16);
    }
    else
    {
      *v14 = 0;
      Row = ADSIGetFirstRow(v17, v16);
    }
    v20 = Row;
    if ( Row < 0 || Row == 20498 )
      break;
    v21 = (v13 >> 27) & 1;
    v20 = DSGetAndValidateColumn(v17, v16, ADSTYPE_CASE_IGNORE_STRING, L"packageName", &v83);
    if ( v20 >= 0 )
    {
      String[0] = v83;
      v20 = UnpackStrAllocFrom<_ads_attr_info>((__int64)String, (HLOCAL *)v15);
      if ( gDebug )
        _DebugMsg(2, 0xC9Cu, *(_QWORD *)v15);
      ADSIFreeColumn(v17, &v83);
      if ( v20 >= 0 )
      {
        v22 = DSGetAndValidateColumn(v17, v16, ADSTYPE_INTEGER, L"packageFlags", &v83);
        v20 = v22;
        if ( v22 >= 0 )
        {
          if ( v83.dwNumValues )
          {
            Boolean = v83.pADsValues->Boolean;
            v84 = Boolean;
          }
          else
          {
            Boolean = 0;
            v84 = 0;
          }
          ADSIFreeColumn(v17, &v83);
          v24 = 0x200000;
          v25 = v13 & 0x200000;
          if ( (Boolean & 0x80u) != 0 && v25 )
          {
            if ( gDebug )
            {
              LODWORD(v80) = 128;
              goto LABEL_21;
            }
LABEL_76:
            v12 = a7;
            goto LABEL_77;
          }
          if ( (Boolean & 0x100) != 0 && v25 )
          {
            if ( !gDebug )
              goto LABEL_76;
            LODWORD(v80) = 256;
LABEL_21:
            v26 = v24;
LABEL_22:
            _DebugMsg(2, 0xC95u, *(_QWORD *)v15, v26, v80);
            goto LABEL_76;
          }
          v27 = 0x10000;
          if ( (v13 & 0x10000) != 0 && (Boolean & 8) == 0 )
          {
            if ( !gDebug )
              goto LABEL_76;
            LODWORD(v80) = 8;
            goto LABEL_31;
          }
          if ( (v13 & 1) != 0 && (Boolean & 0x400) != 0 )
            v21 = 1;
          LODWORD(v86) = v21;
          if ( (v13 & 2) != 0 )
          {
            if ( (Boolean & 0x40000) != 0 )
              v21 = 1;
            LODWORD(v86) = v21;
          }
          v24 = 0x80000;
          if ( (v13 & 0x80000) != 0 && (Boolean & 0x20) == 0 )
          {
            if ( !gDebug )
              goto LABEL_76;
            LODWORD(v80) = 32;
            goto LABEL_21;
          }
          v27 = 0x100000;
          if ( (v13 & 0x100000) != 0 && (Boolean & 0x40) == 0 )
          {
            if ( !gDebug )
              goto LABEL_76;
            LODWORD(v80) = 64;
LABEL_31:
            v26 = v27;
            goto LABEL_22;
          }
          if ( (Boolean & 0x10) != 0 )
          {
            *((_DWORD *)v15 + 3) = Boolean >> 29;
            *((_DWORD *)v15 + 10) = (Boolean & 0x80000) != 0 ? 3 : 5;
          }
          else
          {
            if ( v88 != 2 )
            {
              if ( gDebug )
                _DebugMsg(2, 0xCA4u);
              goto LABEL_76;
            }
            v28 = DSGetAndValidateColumn(v17, v16, ADSTYPE_INTEGER, L"packageType", &v83);
            v29 = 0;
            v20 = v28;
            if ( v28 < 0 )
              goto LABEL_76;
            if ( v83.dwNumValues )
              v29 = v83.pADsValues->Boolean;
            *((_DWORD *)v15 + 3) = v29;
            ADSIFreeColumn(v17, &v83);
            v30 = DSGetAndValidateColumn(v17, v16, ADSTYPE_INTEGER, L"installUiLevel", &v83);
            v31 = 0;
            v20 = v30;
            if ( v30 < 0 )
              goto LABEL_76;
            if ( v83.dwNumValues )
              v31 = v83.pADsValues->Boolean;
            *((_DWORD *)v15 + 10) = v31;
            ADSIFreeColumn(v17, &v83);
          }
          if ( (v13 & 0x40000) != 0 && *((_DWORD *)v15 + 3) != 5 )
          {
            if ( gDebug )
              _DebugMsg(2, 0xCA1u, *(_QWORD *)v15);
            goto LABEL_76;
          }
          *((_WORD *)v15 + 64) = 0;
          LODWORD(v85) = 0;
          v20 = DSGetAndValidateColumn(v17, v16, ADSTYPE_INTEGER, L"localeID", &v83);
          hMem = 0;
          if ( v20 < 0 )
          {
            if ( gDebug )
              _DebugMsg(2, 0xC93u, L"localeID");
            goto LABEL_76;
          }
          v32 = 0;
          String[0] = v83;
          UnpackDWArrFrom<ads_search_column>(String, &hMem, &v85);
          ADSIFreeColumn(v17, &v83);
          v33 = v85;
          if ( (_DWORD)v85 )
            v32 = *(_WORD *)hMem;
          LocalFree(hMem);
          if ( (a3 & 0x400000) != 0 && (Boolean & 0x20000) == 0 && (!v33 || !GetLanguagePriority(v32, Boolean)) )
          {
            if ( gDebug )
            {
              v34 = (unsigned int)v20;
              v35 = L"localeID";
              goto LABEL_73;
            }
            goto LABEL_74;
          }
          *((_WORD *)v15 + 64) = v32;
          if ( v90 )
          {
            v16 = a2;
            Categories = DSGetAndValidateColumn(v17, a2, ADSTYPE_INTEGER, L"machineArchitecture", &v83);
            LODWORD(v85) = 0;
            v20 = Categories;
            hMem = 0;
            if ( Categories >= 0 )
            {
              String[0] = v83;
              UnpackDWArrFrom<ads_search_column>(String, &hMem, &v85);
              ADSIFreeColumn(v17, &v83);
              v38 = 0;
              v39 = hMem;
              *((_DWORD *)v15 + 40) = 0xFFFF;
              if ( (_DWORD)v85 )
              {
                v40 = v90;
                v41 = *((_DWORD *)v15 + 3) == 6;
                v42 = 0;
                v43 = Boolean & 0x10000;
                do
                {
                  v44 = v39[v42];
                  v93.dwPlatformId = (unsigned __int8)v44;
                  v93.dwVersionHi = BYTE1(v44);
                  v93.dwVersionLo = BYTE2(v44);
                  v93.dwProcessorArch = HIBYTE(v44);
                  v45 = PlatformWt(v40, &v93, v43, v41);
                  if ( v45 > v38 )
                  {
                    *((_DWORD *)v15 + 40) = v44;
                    v38 = v45;
                  }
                  v42 = v46 + 1;
                }
                while ( v42 < (unsigned int)v85 );
                v17 = v91;
                Boolean = v84;
              }
              if ( v39 )
                LocalFree(v39);
              if ( !v38 )
              {
                if ( gDebug )
                  _DebugMsg(2, 0xC9Eu, *(_QWORD *)v15);
                goto LABEL_74;
              }
              v21 = (int)v86;
              goto LABEL_96;
            }
            if ( gDebug )
            {
              v47 = L"machineArchitecture";
              goto LABEL_94;
            }
            goto LABEL_75;
          }
LABEL_96:
          v48 = a2;
          *((_DWORD *)v15 + 2) = Boolean;
          if ( (int)DSGetAndValidateColumn(v17, a2, ADSTYPE_OCTET_STRING, L"objectGUID", &v83) >= 0 )
          {
            String[0] = v83;
            UnpackGUIDFrom<ads_search_column>(String, (char *)v15 + 60);
            ADSIFreeColumn(v17, &v83);
          }
          v49 = a3 & 0x4000000;
          v50 = a3 & 0x1000000;
          if ( (a3 & 0x1000000) == 0 || v49 )
          {
            if ( (int)DSGetAndValidateColumn(v17, a2, ADSTYPE_CASE_IGNORE_STRING, L"msiScriptPath", &v83) >= 0 )
            {
              String[0] = v83;
              UnpackStrAllocFrom<_ads_attr_info>((__int64)String, (HLOCAL *)v15 + 2);
              ADSIFreeColumn(v17, &v83);
            }
            if ( !v50 || v49 )
            {
              v51 = DSGetAndValidateColumn(v17, a2, ADSTYPE_CASE_IGNORE_STRING, L"lastUpdateSequence", &v83);
              DNString = 0;
              v20 = v51;
              if ( v51 < 0 )
              {
                if ( gDebug )
                {
                  v34 = (unsigned int)v51;
                  v35 = L"lastUpdateSequence";
LABEL_73:
                  _DebugMsg(2, 0xC93u, v35, v34);
                }
LABEL_74:
                v16 = a2;
                goto LABEL_75;
              }
              if ( v83.dwNumValues )
                DNString = v83.pADsValues->DNString;
              TimeToUsn(DNString, (struct _FILETIME *)v15 + 10);
              ADSIFreeColumn(v17, &v83);
              v48 = a2;
            }
          }
          if ( (int)DSGetAndValidateColumn(v17, v48, ADSTYPE_OCTET_STRING, L"productCode", &v83) >= 0 )
          {
            String[0] = v83;
            UnpackGUIDFrom<ads_search_column>(String, (char *)v15 + 44);
            ADSIFreeColumn(v17, &v83);
          }
          if ( (v88 & 0x1000000) == 0 || v49 )
          {
            v53 = DSGetAndValidateColumn(v17, v48, ADSTYPE_INTEGER, L"revision", &v83);
            v54 = 0;
            if ( v53 >= 0 )
            {
              if ( v83.dwNumValues )
                v54 = v83.pADsValues->Boolean;
              *((_DWORD *)v15 + 24) = v54;
              ADSIFreeColumn(v17, &v83);
            }
          }
          v20 = DSGetAndValidateColumn(v17, v48, ADSTYPE_CASE_IGNORE_STRING, L"url", &v83);
          if ( v20 >= 0 )
          {
            String[0] = v83;
            UnpackStrAllocFrom<_ads_attr_info>((__int64)String, (HLOCAL *)v15 + 4);
            ADSIFreeColumn(v17, &v83);
          }
          if ( v49 )
          {
            v55 = v94;
            v16 = a2;
            RsopSpecificAttributes = GetRsopSpecificAttributes(v17, a2, v94, v15, &v89);
            v20 = RsopSpecificAttributes;
            if ( RsopSpecificAttributes >= 0 )
            {
              if ( v55 )
              {
                v55 = 0;
                if ( !v89 )
                  goto LABEL_75;
              }
            }
            else
            {
              v55 = 0;
              if ( gDebug )
                _DebugMsg(2, 0xCA2u, (unsigned int)RsopSpecificAttributes);
            }
LABEL_126:
            Categories = GetCategories(v17, v16, v15);
            v20 = Categories;
            if ( Categories < 0 )
            {
              if ( gDebug != (_DWORD)v55 )
              {
                v47 = L"categories";
LABEL_94:
                _DebugMsg(2, 0xC93u, v47, (unsigned int)Categories);
              }
LABEL_75:
              v13 = a3;
              goto LABEL_76;
            }
            if ( (int)DSGetAndValidateColumn(v17, v16, ADSTYPE_CASE_IGNORE_STRING, L"url", &v83) >= 0 )
            {
              LocalFree(*((HLOCAL *)v15 + 4));
              String[0] = v83;
              UnpackStrAllocFrom<_ads_attr_info>((__int64)String, (HLOCAL *)v15 + 4);
              ADSIFreeColumn(v17, &v83);
              v55 = 0;
            }
            v20 = (int)v55;
          }
          else
          {
            v55 = 0;
            v57 = v50 == 0;
            v16 = a2;
            if ( !v57 )
              goto LABEL_126;
          }
          if ( (Boolean & 0x40000) != 0 )
          {
            v20 = DSGetAndValidateColumn(v17, v16, ADSTYPE_CASE_IGNORE_STRING, L"canUpgradeScript", &v83);
            if ( v20 >= 0 )
            {
              v58 = (unsigned int *)((char *)v15 + 116);
              v86 = v55;
              String[0] = v83;
              v20 = UnpackStrArrAllocFrom<ads_search_column>(String, &v86, (char *)v15 + 116);
              ADSIFreeColumn(v17, &v83);
              if ( *((_DWORD *)v15 + 29) != (_DWORD)v55 )
                *((_QWORD *)v15 + 15) = LocalAlloc(0, 48LL * *v58);
              v59 = (void *)*((_QWORD *)v15 + 15);
              if ( v59 )
              {
                memset_0(v59, 0, 48LL * *v58);
                v60 = (unsigned int)v55;
                if ( *v58 > (unsigned int)v55 )
                {
                  v61 = v86;
                  do
                  {
                    v62 = *((_QWORD *)v15 + 15);
                    EndPtr = 0;
                    v63 = v61[v60];
                    v64 = 48LL * v60;
                    v96 = v64;
                    v65 = -1;
                    *(_QWORD *)(v64 + v62) = v63;
                    v85 = *((_QWORD *)v15 + 15);
                    v66 = *(void **)(v85 + v64);
                    hMem = v66;
                    do
                      ++v65;
                    while ( *((_WORD *)v66 + v65) );
                    if ( (unsigned int)v65 > 0x29 )
                    {
                      v67 = wcschr((const wchar_t *)v66, 0x7Bu);
                      if ( v67 )
                      {
                        v68 = v85;
                        v69 = String;
                        v70 = 2147483646;
                        v71 = 39;
                        do
                        {
                          if ( !v70 )
                            break;
                          if ( !*v67 )
                            break;
                          LOWORD(v69->pszAttrName) = *v67++;
                          v69 = (struct ads_search_column *)((char *)v69 + 2);
                          --v70;
                          --v71;
                        }
                        while ( v71 );
                        v72 = (struct ads_search_column *)((char *)v69 - 2);
                        if ( v71 )
                          v72 = v69;
                        LOWORD(v72->pszAttrName) = 0;
                        StringToGuid((wchar_t *)String, (struct _GUID *)(v64 + v68 + 24));
                        v73 = (unsigned int)(v65 - 2);
                        v74 = (unsigned int)v65;
                        v75 = (const wchar_t *)hMem;
                        *((_WORD *)hMem + v74 - 3) = 0;
                        v76 = wcstoul(&v75[v73], &EndPtr, 16);
                        v77 = v96;
                        *(_DWORD *)(*((_QWORD *)v15 + 15) + v96 + 40) = v76;
                        v75[v74 - 41] = 0;
                        GUIDFromString(&v75[v74 - 39], (struct _GUID *)(*((_QWORD *)v15 + 15) + v77 + 8));
                      }
                      v61 = v86;
                    }
                    ++v60;
                  }
                  while ( v60 < *v58 );
                  v17 = v91;
                  LODWORD(v55) = 0;
                }
                *v58 = v60;
LABEL_154:
                v78 = v97;
                *(struct _GUID *)((char *)v15 + 100) = *a10;
                v79 = StringDuplicate(v78);
                v36 = a6;
                *((_QWORD *)v15 + 19) = v79;
                if ( !v79 )
                {
                  v20 = -2147024882;
                  goto LABEL_170;
                }
                v12 = a7;
                v36 = a6 - 1;
                a6 = v36;
                ++*a7;
                if ( !v36 )
                  goto LABEL_170;
                v16 = a2;
                v15 = (struct tagPACKAGEDISPINFO *)((char *)v15 + 208);
                v13 = a3;
                goto LABEL_157;
              }
            }
          }
          if ( v21 )
            goto LABEL_154;
          if ( gDebug != (_DWORD)v55 )
            _DebugMsg(2, 0xC96u, *(_QWORD *)v15);
          goto LABEL_75;
        }
        if ( gDebug )
          _DebugMsg(2, 0xC93u, L"packageFlags", (unsigned int)v22);
      }
    }
LABEL_77:
    v36 = a6;
    if ( !a6 )
      goto LABEL_169;
LABEL_157:
    v14 = v92;
  }
  v36 = a6;
LABEL_169:
  LODWORD(v55) = 0;
LABEL_170:
  if ( *a7 == (_DWORD)v55 && v20 < 0 )
    return v20;
  else
    return v36 != 0;
}

```

## disassembly

```asm
0x180026040  mov     [rsp-8+arg_10], rbx
0x180026045  push    rbp
0x180026046  push    rsi
0x180026047  push    rdi
0x180026048  push    r12
0x18002604a  push    r13
0x18002604c  push    r14
0x18002604e  push    r15
0x180026050  lea     rbp, [rsp-40h]
0x180026055  sub     rsp, 140h
0x18002605c  mov     rax, cs:__security_cookie
0x180026063  xor     rax, rsp
0x180026066  mov     [rbp+70h+var_40], rax
0x18002606a  mov     rax, [rbp+70h+arg_20]
0x180026071  xorps   xmm1, xmm1
0x180026074  mov     r15, [rbp+70h+arg_30]
0x18002607b  mov     ebx, r8d
0x18002607e  mov     rdi, [rbp+70h+arg_40]
0x180026085  xorps   xmm0, xmm0
0x180026088  mov     rsi, [rbp+70h+arg_38]
0x18002608f  mov     r12, rdx
0x180026092  mov     [rbp+70h+var_D8], rax
0x180026096  mov     r14, rcx
0x180026099  mov     rax, [rbp+70h+arg_50]
0x1800260a0  mov     [rbp+70h+var_98], rax
0x1800260a4  mov     rax, [rbp+70h+arg_58]
0x1800260ab  mov     [rbp+70h+var_B0], rax
0x1800260af  xor     eax, eax
0x1800260b1  mov     [rbp+70h+var_E0], r9d
0x1800260b5  mov     [rsp+170h+var_140], ebx
0x1800260b9  mov     [rsp+170h+var_130], rdx
0x1800260be  mov     [rbp+70h+var_D0], rcx
0x1800260c2  mov     [rsp+170h+var_138], r15
0x1800260c7  mov     [rbp+70h+var_C8], rdi
0x1800260cb  movups  xmmword ptr [rbp+70h+var_C0.dwPlatformId], xmm0
0x1800260cf  mov     [rsp+170h+var_128.hReserved], rax
0x1800260d4  movups  xmmword ptr [rsp+170h+var_128.pszAttrName], xmm1
0x1800260d9  mov     [rbp+70h+var_DC], eax
0x1800260dc  movups  xmmword ptr [rsp+170h+var_128.pADsValues], xmm1
0x1800260e1  mov     [r15], eax
0x1800260e4  cmp     [rbp+70h+arg_28], eax
0x1800260ea  jz      loc_180026D2F
0x1800260f0  xor     edx, edx; Val
0x1800260f2  mov     r8d, 0D0h; Size
0x1800260f8  mov     rcx, rsi; void *
0x1800260fb  call    memset_0
0x180026100  mov     rcx, rsi; void *
0x180026103  call    ReleasePackageInfo
0x180026108  xor     edx, edx; Val
0x18002610a  mov     r8d, 0D0h; Size
0x180026110  mov     rcx, rsi; void *
0x180026113  call    memset_0
0x180026118  xor     eax, eax
0x18002611a  cmp     [rdi], eax
0x18002611c  jz      short loc_180026133
0x18002611e  cmp     [r15], eax
0x180026121  jnz     short loc_180026133
0x180026123  mov     rdx, r12
0x180026126  mov     [rdi], eax
0x180026128  mov     rcx, r14
0x18002612b  call    cs:__imp_ADSIGetFirstRow
0x180026131  jmp     short loc_18002613F
0x180026133  mov     rdx, r12
0x180026136  mov     rcx, r14
0x180026139  call    cs:__imp_ADSIGetNextRow
0x18002613f  mov     edi, eax
0x180026141  test    eax, eax
0x180026143  js      loc_180026D0F
0x180026149  cmp     eax, 5012h
0x18002614e  jz      loc_180026D0F
0x180026154  lea     rax, [rsp+170h+var_128]
0x180026159  mov     r13d, ebx
0x18002615c  shr     r13d, 1Bh
0x180026160  lea     r9, aPackagename_0; "packageName"
0x180026167  mov     r8d, 3; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x18002616d  mov     [rsp+170h+var_150], rax; struct ads_search_column *
0x180026172  mov     rdx, r12; void *
0x180026175  mov     rcx, r14; void *
0x180026178  and     r13d, 1
0x18002617c  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180026181  mov     edi, eax
0x180026183  test    eax, eax
0x180026185  js      loc_180026547
0x18002618b  movups  xmm0, xmmword ptr [rsp+170h+var_128.pszAttrName]
0x180026190  mov     rdx, rsi
0x180026193  lea     rcx, [rbp+70h+String]
0x180026197  movups  xmm1, xmmword ptr [rsp+170h+var_128.pADsValues]
0x18002619c  movaps  xmmword ptr [rbp+70h+String], xmm0
0x1800261a0  movsd   xmm0, [rsp+170h+var_128.hReserved]
0x1800261a6  movsd   [rbp+70h+var_70], xmm0
0x1800261ab  movaps  [rbp+70h+var_80], xmm1
0x1800261af  call    ??$UnpackStrAllocFrom@U_ads_attr_info@@@@YAJU_ads_attr_info@@PEAPEAG@Z; UnpackStrAllocFrom<_ads_attr_info>(_ads_attr_info,ushort * *)
0x1800261b4  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x1800261bb  mov     edi, eax
0x1800261bd  jz      short loc_1800261D1
0x1800261bf  mov     r8, [rsi]
0x1800261c2  mov     edx, 0C9Ch; unsigned int
0x1800261c7  mov     ecx, 2; unsigned int
0x1800261cc  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800261d1  lea     rdx, [rsp+170h+var_128]
0x1800261d6  mov     rcx, r14
0x1800261d9  call    cs:__imp_ADSIFreeColumn
0x1800261df  test    edi, edi
0x1800261e1  js      loc_180026547
0x1800261e7  lea     rax, [rsp+170h+var_128]
0x1800261ec  mov     r8d, 7; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x1800261f2  lea     r9, aPackageflags; "packageFlags"
0x1800261f9  mov     [rsp+170h+var_150], rax; struct ads_search_column *
0x1800261fe  mov     rdx, r12; void *
0x180026201  mov     rcx, r14; void *
0x180026204  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180026209  xor     ecx, ecx
0x18002620b  mov     edi, eax
0x18002620d  test    eax, eax
0x18002620f  js      loc_180026CDE
0x180026215  cmp     [rsp+170h+var_128.dwNumValues], ecx
0x180026219  jz      short loc_18002622B
0x18002621b  mov     rax, [rsp+170h+var_128.pADsValues]
0x180026220  mov     r15d, [rax+8]
0x180026224  mov     [rsp+170h+var_100], r15d
0x180026229  jmp     short loc_180026232
0x18002622b  mov     r15d, ecx
0x18002622e  mov     [rsp+170h+var_100], ecx
0x180026232  lea     rdx, [rsp+170h+var_128]
0x180026237  mov     rcx, r14
0x18002623a  call    cs:__imp_ADSIFreeColumn
0x180026240  mov     eax, ebx
0x180026242  mov     edx, 200000h
0x180026247  and     eax, edx
0x180026249  xor     ecx, ecx
0x18002624b  test    r15b, r15b
0x18002624e  jns     short loc_180026282
0x180026250  test    eax, eax
0x180026252  jz      short loc_180026282
0x180026254  cmp     cs:?gDebug@@3KA, ecx; ulong gDebug
0x18002625a  jz      loc_180026542
0x180026260  mov     dword ptr [rsp+170h+var_150], 80h
0x180026268  mov     r9d, edx
0x18002626b  mov     r8, [rsi]
0x18002626e  mov     edx, 0C95h; unsigned int
0x180026273  mov     ecx, 2; unsigned int
0x180026278  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18002627d  jmp     loc_180026542
0x180026282  mov     r8d, 100h
0x180026288  test    r8d, r15d
0x18002628b  jz      short loc_1800262A4
0x18002628d  test    eax, eax
0x18002628f  jz      short loc_1800262A4
0x180026291  cmp     cs:?gDebug@@3KA, ecx; ulong gDebug
0x180026297  jz      loc_180026542
0x18002629d  mov     dword ptr [rsp+170h+var_150], r8d
0x1800262a2  jmp     short loc_180026268
0x1800262a4  mov     eax, 10000h
0x1800262a9  test    eax, ebx
0x1800262ab  jz      short loc_1800262CC
0x1800262ad  test    r15b, 8
0x1800262b1  jnz     short loc_1800262CC
0x1800262b3  cmp     cs:?gDebug@@3KA, ecx; ulong gDebug
0x1800262b9  jz      loc_180026542
0x1800262bf  mov     dword ptr [rsp+170h+var_150], 8
0x1800262c7  mov     r9d, eax
0x1800262ca  jmp     short loc_18002626B
0x1800262cc  mov     eax, 1
0x1800262d1  test    al, bl
0x1800262d3  jz      short loc_1800262DE
0x1800262d5  bt      r15d, 0Ah
0x1800262da  cmovb   r13d, eax
0x1800262de  mov     dword ptr [rbp+70h+var_F0], r13d
0x1800262e2  test    bl, 2
0x1800262e5  jz      short loc_1800262F4
0x1800262e7  bt      r15d, 12h
0x1800262ec  cmovb   r13d, eax
0x1800262f0  mov     dword ptr [rbp+70h+var_F0], r13d
0x1800262f4  mov     edx, 80000h
0x1800262f9  test    edx, ebx
0x1800262fb  jz      short loc_18002631C
0x1800262fd  test    r15b, 20h
0x180026301  jnz     short loc_18002631C
0x180026303  cmp     cs:?gDebug@@3KA, ecx; ulong gDebug
0x180026309  jz      loc_180026542
0x18002630f  mov     dword ptr [rsp+170h+var_150], 20h ; ' '
0x180026317  jmp     loc_180026268
0x18002631c  mov     eax, 100000h
0x180026321  test    eax, ebx
0x180026323  jz      short loc_180026341
0x180026325  test    r15b, 40h
0x180026329  jnz     short loc_180026341
0x18002632b  cmp     cs:?gDebug@@3KA, ecx; ulong gDebug
0x180026331  jz      loc_180026542
0x180026337  mov     dword ptr [rsp+170h+var_150], 40h ; '@'
0x18002633f  jmp     short loc_1800262C7
0x180026341  test    r15b, 10h
0x180026345  jnz     loc_18002640D
0x18002634b  cmp     [rbp+70h+var_E0], 2
0x18002634f  jz      short loc_180026371
0x180026351  cmp     cs:?gDebug@@3KA, ecx; ulong gDebug
0x180026357  jz      loc_180026542
0x18002635d  mov     edx, 0CA4h; unsigned int
0x180026362  mov     ecx, 2; unsigned int
0x180026367  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18002636c  jmp     loc_180026542
0x180026371  lea     rax, [rsp+170h+var_128]
0x180026376  mov     r8d, 7; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x18002637c  lea     r9, aPackagetype; "packageType"
0x180026383  mov     [rsp+170h+var_150], rax; struct ads_search_column *
0x180026388  mov     rdx, r12; void *
0x18002638b  mov     rcx, r14; void *
0x18002638e  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180026393  xor     ecx, ecx
0x180026395  mov     edi, eax
0x180026397  test    eax, eax
0x180026399  js      loc_180026542
0x18002639f  cmp     [rsp+170h+var_128.dwNumValues], ecx
0x1800263a3  jz      short loc_1800263AD
0x1800263a5  mov     rax, [rsp+170h+var_128.pADsValues]
0x1800263aa  mov     ecx, [rax+8]
0x1800263ad  mov     [rsi+0Ch], ecx
0x1800263b0  lea     rdx, [rsp+170h+var_128]
0x1800263b5  mov     rcx, r14
0x1800263b8  call    cs:__imp_ADSIFreeColumn
0x1800263be  lea     rax, [rsp+170h+var_128]
0x1800263c3  mov     r8d, 7; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x1800263c9  lea     r9, aInstalluilevel; "installUiLevel"
0x1800263d0  mov     [rsp+170h+var_150], rax; struct ads_search_column *
0x1800263d5  mov     rdx, r12; void *
0x1800263d8  mov     rcx, r14; void *
0x1800263db  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x1800263e0  xor     ecx, ecx
0x1800263e2  mov     edi, eax
0x1800263e4  test    eax, eax
0x1800263e6  js      loc_180026542
0x1800263ec  cmp     [rsp+170h+var_128.dwNumValues], ecx
0x1800263f0  jz      short loc_1800263FA
0x1800263f2  mov     rax, [rsp+170h+var_128.pADsValues]
0x1800263f7  mov     ecx, [rax+8]
0x1800263fa  mov     [rsi+28h], ecx
0x1800263fd  lea     rdx, [rsp+170h+var_128]
0x180026402  mov     rcx, r14
0x180026405  call    cs:__imp_ADSIFreeColumn
0x18002640b  jmp     short loc_180026428
0x18002640d  mov     eax, r15d
0x180026410  and     eax, edx
0x180026412  neg     eax
0x180026414  mov     eax, r15d
0x180026417  sbb     ecx, ecx
0x180026419  and     ecx, 0FFFFFFFEh
0x18002641c  add     ecx, 5
0x18002641f  shr     eax, 1Dh
0x180026422  mov     [rsi+0Ch], eax
0x180026425  mov     [rsi+28h], ecx
0x180026428  bt      ebx, 12h
0x18002642c  jnb     short loc_18002645C
0x18002642e  mov     r9d, [rsi+0Ch]
0x180026432  cmp     r9d, 5
0x180026436  jz      short loc_18002645C
0x180026438  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x18002643f  jz      loc_180026542
0x180026445  mov     r8, [rsi]
0x180026448  mov     edx, 0CA1h; unsigned int
0x18002644d  mov     ecx, 2; unsigned int
0x180026452  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180026457  jmp     loc_180026542
0x18002645c  xor     ecx, ecx
0x18002645e  lea     rax, [rsp+170h+var_128]
0x180026463  mov     [rsi+80h], cx
0x18002646a  lea     r9, aLocaleid; "localeID"
0x180026471  mov     dword ptr [rsp+170h+var_F8], ecx
0x180026475  mov     rdx, r12; void *
0x180026478  mov     [rsp+170h+var_150], rax; struct ads_search_column *
0x18002647d  lea     r8d, [rcx+7]; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x180026481  mov     rcx, r14; void *
0x180026484  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180026489  xor     ecx, ecx
0x18002648b  mov     edi, eax
0x18002648d  mov     [rbp+70h+hMem], rcx
0x180026491  test    eax, eax
0x180026493  js      loc_180026CBE
0x180026499  movups  xmm0, xmmword ptr [rsp+170h+var_128.pszAttrName]
0x18002649e  mov     ebx, ecx
0x1800264a0  lea     r8, [rsp+170h+var_F8]
0x1800264a5  movups  xmm1, xmmword ptr [rsp+170h+var_128.pADsValues]
0x1800264aa  lea     rdx, [rbp+70h+hMem]
0x1800264ae  movaps  xmmword ptr [rbp+70h+String], xmm0
0x1800264b2  lea     rcx, [rbp+70h+String]
0x1800264b6  movsd   xmm0, [rsp+170h+var_128.hReserved]
0x1800264bc  movsd   [rbp+70h+var_70], xmm0
0x1800264c1  movaps  [rbp+70h+var_80], xmm1
0x1800264c5  call    ??$UnpackDWArrFrom@Uads_search_column@@@@YAJUads_search_column@@PEAPEAKPEAK@Z; UnpackDWArrFrom<ads_search_column>(ads_search_column,ulong * *,ulong *)
0x1800264ca  lea     rdx, [rsp+170h+var_128]
0x1800264cf  mov     rcx, r14
0x1800264d2  call    cs:__imp_ADSIFreeColumn
0x1800264d8  mov     r12d, dword ptr [rsp+170h+var_F8]
0x1800264dd  mov     rcx, [rbp+70h+hMem]; hMem
0x1800264e1  test    r12d, r12d
0x1800264e4  jz      short loc_1800264E9
0x1800264e6  movzx   ebx, word ptr [rcx]
0x1800264e9  call    cs:__imp_LocalFree
0x1800264ef  test    [rsp+170h+var_140], 400000h
0x1800264f7  jz      short loc_18002655A
0x1800264f9  bt      r15d, 11h
  ... truncated ...
```
