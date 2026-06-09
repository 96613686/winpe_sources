# I_XmlUnmarshallKeyInfo(void *,WS_CHARSET,ulong,WS_TYPE_KeyInfo *,_CRYPT_XML_WS_STATE *,_CRYPT_XML_KEY_INFO * *)

- ea: `0x180012d90`
- end: `0x180014154`
- name: `?I_XmlUnmarshallKeyInfo@@YAJPEAXW4WS_CHARSET@@KPEAUWS_TYPE_KeyInfo@@PEAU_CRYPT_XML_WS_STATE@@PEAPEAU_CRYPT_XML_KEY_INFO@@@Z`
- size: `5060`
- prototype: `__int64 __usercall@<rax>(HANDLE hHeap@<rcx>, enum WS_CHARSET@<edx>, unsigned int@<r8d>, struct WS_TYPE_KeyInfo *@<r9>, struct _CRYPT_XML_WS_STATE *, struct _CRYPT_XML_KEY_INFO **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002470`
- `0x180016820`

## callees

- `0x18000d500`
- `0x180012d90`
- `0x180014590`
- `0x180014ce0`
- `0x1800173f4`
- `0x18001860d`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800139fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013a75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013f05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800139fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013a75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013f05`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013392`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013392`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013f7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013fb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013fd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800140af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800140e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013f7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013fb8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013fd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800140af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800140e8`

## string_xrefs

- `0x180012e9e`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180012ff4`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18001310a`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18001328e`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800132ce`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180013313`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18001334e`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800133b2`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180013e56`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180013e87`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180013eb7`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180013ff8`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlUnmarshallKeyInfo(
        HANDLE hHeap,
        enum WS_CHARSET a2,
        unsigned int a3,
        struct WS_TYPE_KeyInfo *a4,
        WS_ERROR **a5,
        struct _CRYPT_XML_KEY_INFO **a6)
{
  enum WS_CHARSET v7; // r9d
  HANDLE v9; // r13
  unsigned int v10; // edx
  __int64 v11; // rax
  SIZE_T v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // r14
  int Encoded; // esi
  const char *v16; // r8
  char v17; // dl
  const char *v18; // r9
  bool v19; // zf
  int v20; // r9d
  __int64 v21; // rcx
  unsigned int v22; // edi
  __int64 v23; // r8
  char v24; // dl
  const char *v25; // r9
  bool v26; // zf
  int v27; // eax
  int v28; // eax
  char v29; // dl
  const char *v30; // r9
  bool v31; // zf
  int v32; // eax
  unsigned __int64 v33; // rcx
  char v34; // dl
  const char *v35; // r9
  bool v36; // zf
  char v37; // dl
  const char *v38; // r9
  bool v39; // zf
  char v40; // dl
  const char *v41; // r9
  bool v42; // zf
  char v43; // dl
  const char *v44; // r9
  bool v45; // zf
  char *v46; // rax
  __int16 *v47; // r10
  char *v48; // r14
  char v49; // dl
  const char *v50; // r9
  bool v51; // zf
  char *v52; // rbx
  char *v53; // r12
  unsigned int v54; // ecx
  char *v55; // r12
  __int64 v56; // rax
  __int64 v57; // rdi
  __int64 v58; // rsi
  unsigned __int64 v59; // rbp
  _DWORD *v60; // rdx
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r8
  __int64 v64; // r13
  unsigned __int64 v65; // rcx
  __int64 v66; // rdx
  __int64 v67; // rbp
  __int64 v68; // r9
  __int64 v69; // rax
  __int64 v70; // rdx
  __int16 *v71; // kr10_8
  __int64 v72; // rcx
  char *v73; // rbx
  __int64 v74; // rcx
  __int64 v75; // rcx
  int v76; // ecx
  _DWORD *v77; // rdx
  int v78; // eax
  __int64 v79; // rcx
  int v80; // esi
  __int64 v81; // rdi
  unsigned int v82; // esi
  unsigned __int64 v83; // rbx
  char *v84; // r12
  int v85; // eax
  int v86; // ebx
  HLOCAL v87; // rbx
  __int64 v88; // rdx
  char *v89; // rsi
  __int64 v90; // rcx
  char *v91; // rbx
  unsigned __int64 v92; // rbx
  const char *v93; // r8
  char v94; // cl
  const char *v95; // rdx
  bool v96; // zf
  int v97; // r9d
  char v98; // cl
  char v99; // cl
  unsigned int v100; // r15d
  unsigned int v101; // ebp
  __int64 v102; // rdx
  unsigned __int64 v103; // r9
  __int64 v104; // rcx
  void *v105; // r8
  __int64 v106; // rbx
  unsigned __int64 v107; // rsi
  unsigned __int64 v108; // rdi
  __int64 v109; // rax
  void *v110; // r8
  char v112; // dl
  const char *v113; // r9
  bool v114; // zf
  __int64 v115; // rbp
  __int64 v116; // rdx
  __int64 v117; // r9
  __int64 v118; // rcx
  void *v119; // r8
  unsigned int v120; // ebx
  __int64 v121; // r14
  __int64 v122; // rdi
  __int64 v123; // rcx
  __int64 v124; // rax
  void *v125; // r8
  unsigned int v126; // [rsp+30h] [rbp-68h]
  HLOCAL hMem; // [rsp+38h] [rbp-60h] BYREF
  __int64 v128; // [rsp+40h] [rbp-58h]
  __int64 v129; // [rsp+48h] [rbp-50h]
  unsigned __int64 v130; // [rsp+50h] [rbp-48h]
  int v133; // [rsp+B8h] [rbp+20h]

  v7 = a2;
  hMem = 0;
  v9 = hHeap;
  *a6 = 0;
  v10 = *((_DWORD *)a4 + 4);
  if ( v10 > 0x7FF8 || *(_DWORD *)a4 > 0x100u )
  {
    Encoded = -2146885375;
    v16 = "";
    do
    {
      v112 = *(v16 - 1);
      v113 = v16--;
      v114 = v112 == 92;
      if ( v112 == 92 )
        goto LABEL_214;
    }
    while ( v16 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" );
    v114 = v112 == 92;
LABEL_214:
    if ( v114 )
      v16 = v113;
    v20 = 1443;
    goto LABEL_217;
  }
  v11 = 0;
  v133 = 0;
  v12 = ((2LL * (unsigned int)(*(_DWORD *)a4 + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL) + ((unsigned __int64)v10 << 7) + 80;
  if ( !v10 )
  {
LABEL_93:
    v46 = (char *)HeapAlloc(v9, 8u, v12);
    v48 = v46;
    if ( !v46 )
    {
      Encoded = -2147024882;
      v16 = "";
      while ( 1 )
      {
        v49 = *(v16 - 1);
        v50 = v16--;
        v51 = v49 == 92;
        if ( v49 == 92 )
          break;
        if ( v16 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
        {
          v51 = v49 == 92;
          break;
        }
      }
      if ( v51 )
        v16 = v50;
      v20 = 1672;
      goto LABEL_217;
    }
    *(_DWORD *)v46 = 40;
    v52 = v46 + 40;
    if ( *(_DWORD *)a4 )
    {
      *((_QWORD *)v46 + 1) = v52;
      memcpy_0(v46 + 40, *((const void **)a4 + 1), 2LL * *(unsigned int *)a4);
      v53 = &v52[(2LL * (unsigned int)(*(_DWORD *)a4 + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL];
    }
    else
    {
      v53 = v46 + 40;
    }
    *((_QWORD *)v48 + 3) = v53;
    v54 = *((_DWORD *)a4 + 4);
    *((_DWORD *)v48 + 4) = v54;
    v55 = &v53[128 * (unsigned __int64)v54];
    v56 = 0;
    v126 = 0;
    while ( (unsigned int)v56 < *((_DWORD *)v48 + 4) )
    {
      v57 = 160 * v56;
      v58 = (unsigned int)v56;
      v59 = (unsigned __int64)(unsigned int)v56 << 7;
      *(_DWORD *)(*((_QWORD *)v48 + 3) + v59) = *(_DWORD *)(160 * v56 + *((_QWORD *)a4 + 3));
      v60 = (_DWORD *)(160 * v56 + *((_QWORD *)a4 + 3));
      switch ( *v60 )
      {
        case 1:
          *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 8) = v55;
          memcpy_0(
            v55,
            *(const void **)(*((_QWORD *)a4 + 3) + v57 + 16),
            2LL * *(unsigned int *)(*((_QWORD *)a4 + 3) + v57 + 8));
          v55 += (2LL * (unsigned int)(*(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 8) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          break;
        case 2:
          switch ( v60[2] )
          {
            case 1:
              v76 = 1;
              break;
            case 2:
              v76 = 2;
              break;
            case 3:
            case 5:
              v76 = 3;
              break;
            default:
              v76 = 4;
              break;
          }
          *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 8) = v76;
          v77 = (_DWORD *)(v57 + *((_QWORD *)a4 + 3));
          switch ( v77[2] )
          {
            case 1:
              if ( v77[4] )
              {
                *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 24) = v55;
                *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 16) = *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 16);
                memcpy_0(
                  v55,
                  *(const void **)(*((_QWORD *)a4 + 3) + v57 + 24),
                  *(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 16));
                v55 += (*(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 16) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              if ( *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 32) )
              {
                *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 40) = v55;
                *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 32) = *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 32);
                memcpy_0(
                  v55,
                  *(const void **)(*((_QWORD *)a4 + 3) + v57 + 40),
                  *(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 32));
                v55 += (*(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 32) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              if ( *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 80) )
              {
                *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 88) = v55;
                *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 80) = *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 80);
                memcpy_0(
                  v55,
                  *(const void **)(*((_QWORD *)a4 + 3) + v57 + 88),
                  *(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 80));
                v55 += (*(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 80) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              if ( *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 64) )
              {
                *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 72) = v55;
                *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 64) = *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 64);
                memcpy_0(
                  v55,
                  *(const void **)(*((_QWORD *)a4 + 3) + v57 + 72),
                  *(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 64));
                v55 += (*(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 64) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              if ( *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 48) )
              {
                *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 56) = v55;
                *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 48) = *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 48);
                memcpy_0(
                  v55,
                  *(const void **)(*((_QWORD *)a4 + 3) + v57 + 56),
                  *(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 48));
                v55 += (*(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 48) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              if ( *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 96) )
              {
                *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 104) = v55;
                *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 96) = *(_DWORD *)(160 * v58 + *((_QWORD *)a4 + 3) + 96);
                memcpy_0(
                  v55,
                  *(const void **)(160 * v58 + *((_QWORD *)a4 + 3) + 104),
                  *(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 96));
                v55 += (*(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 96) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              if ( *(_DWORD *)(160 * v58 + *((_QWORD *)a4 + 3) + 112) )
              {
                v92 = (unsigned __int64)v126 << 7;
                *(_QWORD *)((v58 << 7) + *((_QWORD *)v48 + 3) + 120) = v55;
                *(_DWORD *)(*((_QWORD *)v48 + 3) + v92 + 112) = *(_DWORD *)(160LL * v126 + *((_QWORD *)a4 + 3) + 112);
                memcpy_0(
                  v55,
                  *(const void **)(160LL * v126 + *((_QWORD *)a4 + 3) + 120),
                  *(unsigned int *)(*((_QWORD *)v48 + 3) + v92 + 112));
                v55 += (*(unsigned int *)(*((_QWORD *)v48 + 3) + v92 + 112) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
              }
              break;
            case 2:
              *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 24) = v55;
              *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 16) = *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 16);
              memcpy_0(
                v55,
                *(const void **)(*((_QWORD *)a4 + 3) + v57 + 24),
                *(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 16));
              v90 = *((_QWORD *)v48 + 3);
              v91 = &v55[(*(unsigned int *)(v90 + v59 + 16) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
              *(_QWORD *)(v90 + v59 + 40) = v91;
              *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 32) = *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 32);
              memcpy_0(
                v91,
                *(const void **)(*((_QWORD *)a4 + 3) + v57 + 40),
                *(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 32));
              v55 = &v91[(*(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 32) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
              break;
            case 3:
              v85 = v77[4];
              if ( v85 == 2 )
              {
                *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 16) = v55;
                memcpy_0(
                  v55,
                  *(const void **)(*((_QWORD *)a4 + 3) + v57 + 32),
                  2LL * *(unsigned int *)(*((_QWORD *)a4 + 3) + v57 + 24));
                v55 += (2LL * (unsigned int)(*(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 24) + 1) + 7)
                     & 0xFFFFFFFFFFFFFFF8uLL;
              }
              else if ( v85 == 1 )
              {
                *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 60) = v77[11];
                *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 64) = *(_QWORD *)(*((_QWORD *)a4 + 3) + v57 + 48);
                *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 56) = *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 40);
              }
              *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 32) = v55;
              if ( hMem )
              {
                LocalFree(hMem);
                hMem = 0;
              }
              v86 = I_DecStringToBigEndianBytes(
                      *(_QWORD *)(*((_QWORD *)a4 + 3) + v57 + 64),
                      *(unsigned int *)(*((_QWORD *)a4 + 3) + v57 + 56),
                      &hMem,
                      v59 + *((_QWORD *)v48 + 3) + 24LL);
              if ( v86 < 0 )
              {
                v93 = "";
                while ( 1 )
                {
                  v99 = *(v93 - 1);
                  v95 = v93--;
                  v96 = v99 == 92;
                  if ( v99 == 92 )
                    break;
                  if ( v93 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
                  {
                    v96 = v99 == 92;
                    break;
                  }
                }
                v97 = 1833;
LABEL_183:
                if ( v96 )
                  v93 = v95;
                WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v86, v93, v97);
                v100 = v86;
                goto LABEL_187;
              }
              v87 = hMem;
              memcpy_0(v55, hMem, *(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 24));
              v88 = *((_QWORD *)v48 + 3);
              v89 = &v55[(*(unsigned int *)(v88 + v59 + 24) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
              *(_QWORD *)(v88 + v59 + 48) = v89;
              if ( v87 )
              {
                LocalFree(v87);
                hMem = 0;
              }
              v86 = I_DecStringToBigEndianBytes(
                      *(_QWORD *)(*((_QWORD *)a4 + 3) + v57 + 80),
                      *(unsigned int *)(*((_QWORD *)a4 + 3) + v57 + 72),
                      &hMem,
                      v59 + *((_QWORD *)v48 + 3) + 40LL);
              if ( v86 < 0 )
              {
                v93 = "";
                while ( 1 )
                {
                  v98 = *(v93 - 1);
                  v95 = v93--;
                  v96 = v98 == 92;
                  if ( v98 == 92 )
                    break;
                  if ( v93 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
                  {
                    v96 = v98 == 92;
                    break;
                  }
                }
                v97 = 1860;
                goto LABEL_183;
              }
              memcpy_0(v89, hMem, *(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 40));
              v55 = &v89[(*(unsigned int *)(*((_QWORD *)v48 + 3) + v59 + 40) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL];
              break;
            case 4:
              *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 20) = v77[33];
              *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 24) = *(_QWORD *)(*((_QWORD *)a4 + 3) + v57 + 136);
              *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 16) = *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 128);
              break;
            case 5:
              v78 = v77[4];
              if ( v78 == 2 )
              {
                *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 16) = v55;
                memcpy_0(
                  v55,
                  *(const void **)(*((_QWORD *)a4 + 3) + v57 + 32),
                  2LL * *(unsigned int *)(*((_QWORD *)a4 + 3) + v57 + 24));
                v55 += (2LL * (unsigned int)(*(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 24) + 1) + 7)
                     & 0xFFFFFFFFFFFFFFF8uLL;
              }
              else if ( v78 == 1 )
              {
                *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 60) = v77[11];
                *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 64) = *(_QWORD *)(*((_QWORD *)a4 + 3) + v57 + 48);
                *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 56) = *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 40);
              }
              v79 = *((_QWORD *)a4 + 3);
              v80 = *(_DWORD *)(v79 + v57 + 56);
              v81 = *(_QWORD *)(v79 + v57 + 64);
              *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 32) = v55;
              v82 = (unsigned int)(v80 - 1) >> 1;
              *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 24) = v82;
              memcpy_0(v55, (const void *)(v81 + 1), v82);
              v83 = (v82 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
              v84 = &v55[v83];
              *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 48) = v84;
              *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 40) = v82;
              memcpy_0(v84, (const void *)(v81 + v82 + 1LL), v82);
              v55 = &v84[v83];
              break;
          }
          break;
        case 3:
          goto LABEL_110;
        case 4:
          *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 8) = v60[2];
          *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 16) = v55;
          v61 = *((_QWORD *)a4 + 3);
          v62 = *(unsigned int *)(v61 + v57 + 8);
          v55 += 24 * v62;
          if ( (_DWORD)v62 )
          {
            v63 = v57 + 16;
            v64 = 0;
            v65 = v59 + 16;
            v130 = v59 + 16;
            v129 = v57 + 8;
            do
            {
              v66 = *(_QWORD *)(v63 + v61);
              v67 = 56LL * (unsigned int)v64;
              v68 = 24 * v64;
              v69 = *((_QWORD *)v48 + 3);
              v128 = v68;
              *(_DWORD *)(v68 + *(_QWORD *)(v65 + v69)) = *(_DWORD *)(v66 + v67);
              v70 = *(_QWORD *)(v63 + *((_QWORD *)a4 + 3));
              v71 = v47;
              v47 = &_ImageBase;
              switch ( *(_DWORD *)(v70 + v67) )
              {
                case 1:
                  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v48 + 3) + (v58 << 7) + 16) + v68 + 8) = v55;
                  v72 = *(_QWORD *)(160 * v58 + *((_QWORD *)a4 + 3) + 16);
                  memcpy_0(v55, *(const void **)(v72 + v67 + 16), 2LL * *(unsigned int *)(v72 + v67 + 8));
                  v73 = &v55[(2LL
                            * (unsigned int)(*(_DWORD *)(*(_QWORD *)(160 * v58 + *((_QWORD *)a4 + 3) + 16) + v67 + 8) + 1)
                            + 7)
                           & 0xFFFFFFFFFFFFFFF8uLL];
                  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v48 + 3) + (v58 << 7) + 16) + v128 + 16) = v73;
                  v74 = *(_QWORD *)(160 * v58 + *((_QWORD *)a4 + 3) + 16);
                  memcpy_0(v73, *(const void **)(v74 + v67 + 32), 2LL * *(unsigned int *)(v74 + v67 + 24));
                  v63 = v57 + 16;
                  v55 = &v73[(2LL
                            * (unsigned int)(*(_DWORD *)(*(_QWORD *)(160 * v58 + *((_QWORD *)a4 + 3) + 16) + v67 + 24)
                                           + 1)
                            + 7)
                           & 0xFFFFFFFFFFFFFFF8uLL];
                  break;
                case 2:
                case 4:
                case 5:
                  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v48 + 3) + (v58 << 7) + 16) + v68 + 16) = v55;
                  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v48 + 3) + (v58 << 7) + 16) + v68 + 8) = *(_DWORD *)(*(_QWORD *)(160 * v58 + *((_QWORD *)a4 + 3) + 16) + v67 + 8);
                  memcpy_0(
                    v55,
                    *(const void **)(*(_QWORD *)(160 * v58 + *((_QWORD *)a4 + 3) + 16) + v67 + 16),
                    *(unsigned int *)(*(_QWORD *)(*((_QWORD *)v48 + 3) + (v58 << 7) + 16) + v68 + 8));
                  v63 = v57 + 16;
                  v55 += (*(unsigned int *)(*(_QWORD *)(160 * v58 + *((_QWORD *)a4 + 3) + 16) + v67 + 8) + 7LL)
                       & 0xFFFFFFFFFFFFFFF8uLL;
                  break;
                case 3:
                  *(_QWORD *)(*(_QWORD *)((v58 << 7) + *((_QWORD *)v48 + 3) + 16) + v68 + 8) = v55;
                  v75 = *(_QWORD *)(160 * v58 + *((_QWORD *)a4 + 3) + 16);
                  memcpy_0(v55, *(const void **)(v75 + v67 + 16), 2LL * *(unsigned int *)(v75 + v67 + 8));
                  v63 = v57 + 16;
                  v55 += (2LL
                        * (unsigned int)(*(_DWORD *)(*(_QWORD *)(160 * v58 + *((_QWORD *)a4 + 3) + 16) + v67 + 8) + 1)
                        + 7)
                       & 0xFFFFFFFFFFFFFFF8uLL;
                  break;
                case 6:
                  *(_DWORD *)(*(_QWORD *)((v58 << 7) + *((_QWORD *)v48 + 3) + 16) + v68 + 12) = *(_DWORD *)(v70 + v67 + 44);
                  *(_QWORD *)(*(_QWORD *)((v58 << 7) + *((_QWORD *)v48 + 3) + 16) + v68 + 16) = *(_QWORD *)(*(_QWORD *)(160 * v58 + *((_QWORD *)a4 + 3) + 16) + v67 + 48);
                  *(_DWORD *)(*(_QWORD *)((v58 << 7) + *((_QWORD *)v48 + 3) + 16) + v68 + 8) = *(_DWORD *)(*(_QWORD *)(160 * v58 + *((_QWORD *)a4 + 3) + 16) + v67 + 40);
                  break;
                default:
                  v47 = v71;
                  break;
              }
              v61 = *((_QWORD *)a4 + 3);
              v64 = (unsigned int)(v64 + 1);
              v65 = v130;
            }
            while ( (unsigned int)v64 < *(_DWORD *)(v129 + v61) );
            v9 = hHeap;
          }
          break;
        case 5:
LABEL_110:
          *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 12) = v60[37];
          *(_QWORD *)(*((_QWORD *)v48 + 3) + v59 + 16) = *(_QWORD *)(*((_QWORD *)a4 + 3) + v57 + 152);
          *(_DWORD *)(*((_QWORD *)v48 + 3) + v59 + 8) = *(_DWORD *)(*((_QWORD *)a4 + 3) + v57 + 144);
          break;
      }
      v56 = v126 + 1;
      v126 = v56;
    }
    v86 = I_XmlAllocAndCopyKeyInfo(v9);
    if ( v86 < 0 )
    {
      v93 = "";
      while ( 1 )
      {
        v94 = *(v93 - 1);
        v95 = v93--;
        v96 = v94 == 92;
        if ( v94 == 92 )
          break;
        if ( v93 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
        {
          v96 = v94 == 92;
          break;
        }
      }
      v97 = 2022;
      goto LABEL_183;
    }
    v100 = 0;
LABEL_187:
    if ( hMem )
      LocalFree(hMem);
    v101 = 0;
    if ( !*((_DWORD *)v48 + 4) )
    {
LABEL_209:
      HeapFree(v9, 0, v48);
      return v100;
    }
    while ( 1 )
    {
      v102 = *((_QWORD *)v48 + 3);
      v103 = (unsigned __int64)v101 << 7;
      v104 = v103 + v102;
      switch ( *(_DWORD *)(v103 + v102) )
      {
        case 2:
          if ( *(_DWORD *)(v104 + 8) == 3 )
          {
            v105 = *(void **)(v104 + 64);
LABEL_206:
            if ( v105 )
              HeapFree(v9, 0, v105);
            break;
          }
          if ( *(_DWORD *)(v104 + 8) == 4 )
          {
            v105 = *(void **)(v104 + 24);
            goto LABEL_206;
          }
          break;
        case 3:
          goto LABEL_194;
        case 4:
          if ( *(_DWORD *)(v104 + 8) )
          {
            v106 = 0;
            v107 = v103 + 16;
            v108 = v103 + 8;
            do
            {
              v109 = *(_QWORD *)(v107 + v102);
              if ( *(_DWORD *)(v109 + 24 * v106) == 6 )
              {
                v110 = *(void **)(v109 + 24 * v106 + 16);
                if ( v110 )
                  HeapFree(v9, 0, v110);
              }
              v102 = *((_QWORD *)v48 + 3);
              v106 = (unsigned int)(v106 + 1);
            }
            while ( (unsigned int)v106 < *(_DWORD *)(v102 + v108) );
          }
          break;
        case 5:
LABEL_194:
          v105 = *(void **)(v104 + 16);
          goto LABEL_206;
      }
      if ( ++v101 >= *((_DWORD *)v48 + 4) )
        goto LABEL_209;
    }
  }
  while ( 1 )
  {
    v13 = *((_QWORD *)a4 + 3);
    v14 = 160 * v11;
    if ( *(_DWORD *)(160 * v11 + v13) == 1 )
    {
      v12 += (2LL * (unsigned int)(*(_DWORD *)(v14 + v13 + 8) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      goto LABEL_63;
    }
    if ( *(_DWORD *)(160 * v11 + v13) != 2 )
      break;
    switch ( *(_DWORD *)(v14 + v13 + 8) )
    {
      case 1:
        v33 = ((*(unsigned int *)(v14 + v13 + 32) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
            + ((*(unsigned int *)(v14 + v13 + 48) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
            + ((*(unsigned int *)(v14 + v13 + 64) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
            + ((*(unsigned int *)(v14 + v13 + 80) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
            + ((*(unsigned int *)(v14 + v13 + 96) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
            + ((*(unsigned int *)(v14 + v13 + 112) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
        goto LABEL_61;
      case 2:
        v33 = (*(unsigned int *)(v14 + v13 + 32) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
LABEL_61:
        v12 += v33 + ((*(unsigned int *)(v14 + v13 + 16) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
        break;
      case 3:
        v32 = *(_DWORD *)(v14 + v13 + 16);
        if ( v32 == 2 )
        {
          v12 += (2LL * (unsigned int)(*(_DWORD *)(v14 + v13 + 24) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        }
        else if ( v32 == 1 )
        {
          Encoded = I_XmlGetEncoded(
                      v9,
                      a5,
                      *(struct _WS_XML_BUFFER **)(v14 + v13 + 24),
                      (CRYPT_XML_CHARSET)v7,
                      a3,
                      (struct _CRYPT_XML_BLOB *)(v14 + v13 + 40));
          if ( Encoded < 0 )
          {
            v16 = "";
            do
            {
              v43 = *(v16 - 1);
              v44 = v16--;
              v45 = v43 == 92;
              if ( v43 == 92 )
                goto LABEL_90;
            }
            while ( v16 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" );
            v45 = v43 == 92;
LABEL_90:
            if ( v45 )
              v16 = v44;
            v20 = 1499;
            goto LABEL_217;
          }
        }
        v12 += ((*(unsigned int *)(*((_QWORD *)a4 + 3) + v14 + 72) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL)
             + ((*(unsigned int *)(*((_QWORD *)a4 + 3) + v14 + 56) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
        break;
      case 4:
        Encoded = I_XmlGetEncoded(
                    v9,
                    a5,
                    *(struct _WS_XML_BUFFER **)(v14 + v13 + 16),
                    (CRYPT_XML_CHARSET)v7,
                    a3,
                    (struct _CRYPT_XML_BLOB *)(v14 + v13 + 128));
        if ( Encoded < 0 )
        {
          v16 = "";
          do
          {
            v29 = *(v16 - 1);
            v30 = v16--;
            v31 = v29 == 92;
            if ( v29 == 92 )
              goto LABEL_51;
          }
          while ( v16 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" );
          v31 = v29 == 92;
LABEL_51:
          if ( v31 )
            v16 = v30;
          v20 = 1567;
          goto LABEL_217;
        }
        break;
      case 5:
        v27 = *(_DWORD *)(v14 + v13 + 16);
        if ( v27 == 2 )
        {
          v12 += (2LL * (unsigned int)(*(_DWORD *)(v14 + v13 + 24) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        }
        else if ( v27 == 1 )
        {
          Encoded = I_XmlGetEncoded(
                      v9,
                      a5,
                      *(struct _WS_XML_BUFFER **)(v14 + v13 + 24),
                      (CRYPT_XML_CHARSET)v7,
                      a3,
                      (struct _CRYPT_XML_BLOB *)(v14 + v13 + 40));
          if ( Encoded < 0 )
          {
            v16 = "";
            do
            {
              v37 = *(v16 - 1);
              v38 = v16--;
              v39 = v37 == 92;
              if ( v37 == 92 )
                goto LABEL_76;
            }
            while ( v16 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" );
            v39 = v37 == 92;
LABEL_76:
            if ( v39 )
              v16 = v38;
            v20 = 1528;
            goto LABEL_217;
          }
        }
        v28 = *(_DWORD *)(*((_QWORD *)a4 + 3) + v14 + 56);
        if ( (v28 & 1) == 0 )
        {
          Encoded = -2146885361;
          v16 = "";
          do
          {
            v40 = *(v16 - 1);
            v41 = v16--;
            v42 = v40 == 92;
            if ( v40 == 92 )
              goto LABEL_83;
          }
          while ( v16 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" );
          v42 = v40 == 92;
LABEL_83:
          if ( v42 )
            v16 = v41;
          v20 = 1539;
          goto LABEL_217;
        }
        v12 += 2 * ((((unsigned __int64)(unsigned int)(v28 - 1) >> 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL);
        break;
    }
LABEL_63:
    v11 = (unsigned int)(v133 + 1);
    v133 = v11;
    if ( (unsigned int)v11 >= *((_DWORD *)a4 + 4) )
      goto LABEL_93;
    v7 = a2;
  }
  if ( *(_DWORD *)(160 * v11 + v13) == 3 )
  {
    Encoded = I_XmlGetEncoded(
                v9,
                a5,
                *(struct _WS_XML_BUFFER **)(v14 + v13 + 8),
                (CRYPT_XML_CHARSET)v7,
                a3,
                (struct _CRYPT_XML_BLOB *)(v14 + v13 + 144));
    if ( Encoded < 0 )
    {
      v16 = "";
      do
      {
        v24 = *(v16 - 1);
        v25 = v16--;
        v26 = v24 == 92;
        if ( v24 == 92 )
          goto LABEL_32;
      }
      while ( v16 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" );
      v26 = v24 == 92;
LABEL_32:
      if ( v26 )
        v16 = v25;
      v20 = 1587;
      goto LABEL_217;
    }
    goto LABEL_63;
  }
  if ( *(_DWORD *)(160 * v11 + v13) != 4 )
  {
    if ( *(_DWORD *)(160 * v11 + v13) == 5 )
    {
      Encoded = I_XmlGetEncoded(
                  v9,
                  a5,
                  *(struct _WS_XML_BUFFER **)(v14 + v13 + 8),
                  (CRYPT_XML_CHARSET)v7,
                  a3,
                  (struct _CRYPT_XML_BLOB *)(v14 + v13 + 144));
      if ( Encoded < 0 )
      {
        v16 = "";
        while ( 1 )
        {
          v17 = *(v16 - 1);
          v18 = v16--;
          v19 = v17 == 92;
          if ( v17 == 92 )
            break;
          if ( v16 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
          {
            v19 = v17 == 92;
            break;
          }
        }
        if ( v19 )
          v16 = v18;
        v20 = 1656;
        goto LABEL_217;
      }
    }
    goto LABEL_63;
  }
  v21 = *(unsigned int *)(v14 + v13 + 8);
  v12 += 24 * v21;
  if ( !(_DWORD)v21 )
    goto LABEL_63;
  v22 = 0;
  while ( 2 )
  {
    v23 = 56LL * v22 + *(_QWORD *)(v14 + v13 + 16);
    switch ( *(_DWORD *)v23 )
    {
      case 1:
        v12 += ((2LL * (unsigned int)(*(_DWORD *)(v23 + 24) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL)
             + ((2LL * (unsigned int)(*(_DWORD *)(v23 + 8) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL);
        goto LABEL_25;
      case 2:
      case 4:
      case 5:
        v12 += (*(unsigned int *)(v23 + 8) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
        goto LABEL_25;
      case 3:
        v12 += (2LL * (unsigned int)(*(_DWORD *)(v23 + 8) + 1) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        goto LABEL_25;
      case 6:
        Encoded = I_XmlGetEncoded(
                    v9,
                    a5,
                    *(struct _WS_XML_BUFFER **)(v23 + 8),
                    (CRYPT_XML_CHARSET)v7,
                    a3,
                    (struct _CRYPT_XML_BLOB *)(v23 + 40));
        if ( Encoded >= 0 )
        {
          v7 = a2;
LABEL_25:
          v13 = *((_QWORD *)a4 + 3);
          if ( ++v22 >= *(_DWORD *)(v13 + v14 + 8) )
            goto LABEL_63;
          continue;
        }
        v16 = "";
        while ( 1 )
        {
          v34 = *(v16 - 1);
          v35 = v16--;
          v36 = v34 == 92;
          if ( v34 == 92 )
            break;
          if ( v16 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp" )
          {
            v36 = v34 == 92;
            break;
          }
        }
        if ( v36 )
          v16 = v35;
        v20 = 1634;
LABEL_217:
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", Encoded, v16, v20);
        v115 = 0;
        if ( *((_DWORD *)a4 + 4) )
        {
          while ( 2 )
          {
            v116 = *((_QWORD *)a4 + 3);
            v117 = 160 * v115;
            v118 = 160 * v115 + v116;
            if ( *(_DWORD *)v118 == 2 )
            {
              switch ( *(_DWORD *)(v118 + 8) )
              {
                case 3:
                  goto LABEL_233;
                case 4:
                  v119 = *(void **)(v118 + 136);
                  goto LABEL_234;
                case 5:
LABEL_233:
                  v119 = *(void **)(v118 + 48);
                  goto LABEL_234;
              }
            }
            else
            {
              switch ( *(_DWORD *)(160 * v115 + v116) )
              {
                case 3:
                  goto LABEL_222;
                case 4:
                  if ( *(_DWORD *)(v118 + 8) )
                  {
                    v120 = 0;
                    v121 = v117 + 16;
                    v122 = v117 + 8;
                    do
                    {
                      v123 = 56LL * v120;
                      v124 = *(_QWORD *)(v121 + v116);
                      if ( *(_DWORD *)(v124 + v123) == 6 )
                      {
                        v125 = *(void **)(v124 + v123 + 48);
                        if ( v125 )
                          HeapFree(v9, 0, v125);
                      }
                      v116 = *((_QWORD *)a4 + 3);
                      ++v120;
                    }
                    while ( v120 < *(_DWORD *)(v122 + v116) );
                  }
                  break;
                case 5:
LABEL_222:
                  v119 = *(void **)(v118 + 152);
LABEL_234:
                  if ( v119 )
                    HeapFree(v9, 0, v119);
                  break;
              }
            }
            v115 = (unsigned int)(v115 + 1);
            if ( (unsigned int)v115 >= *((_DWORD *)a4 + 4) )
              return (unsigned int)Encoded;
            continue;
          }
        }
        return (unsigned int)Encoded;
      default:
        goto LABEL_25;
    }
  }
}

```

## disassembly

```asm
0x180012d90  mov     [rsp+arg_10], rbx
0x180012d95  mov     [rsp+arg_8], edx
0x180012d99  mov     [rsp+arg_0], rcx
0x180012d9e  push    rbp
0x180012d9f  push    rsi
0x180012da0  push    rdi
0x180012da1  push    r12
0x180012da3  push    r13
0x180012da5  push    r14
0x180012da7  push    r15
0x180012da9  sub     rsp, 60h
0x180012dad  mov     rax, [rsp+98h+arg_28]
0x180012db5  mov     r15, r9
0x180012db8  mov     r9d, edx; enum WS_CHARSET
0x180012dbb  mov     [rsp+98h+hMem], 0
0x180012dc4  mov     r12d, r8d
0x180012dc7  mov     r13, rcx
0x180012dca  mov     qword ptr [rax], 0
0x180012dd1  mov     edx, [r15+10h]
0x180012dd5  cmp     edx, 7FF8h
0x180012ddb  ja      loc_180013FEC
0x180012de1  mov     eax, [r15]
0x180012de4  cmp     eax, 100h
0x180012de9  ja      loc_180013FEC
0x180012def  inc     eax
0x180012df1  lea     r10, __ImageBase
0x180012df8  mov     ebx, edx
0x180012dfa  shl     rbx, 7
0x180012dfe  add     rbx, 50h ; 'P'
0x180012e02  lea     rcx, ds:7[rax*2]
0x180012e0a  xor     eax, eax
0x180012e0c  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180012e10  mov     dword ptr [rsp+98h+arg_18], eax
0x180012e17  add     rbx, rcx
0x180012e1a  test    edx, edx
0x180012e1c  jz      loc_180013387
0x180012e22  mov     rbp, [rsp+98h+arg_20]
0x180012e2a  nop     word ptr [rax+rax+00h]
0x180012e30  mov     rdx, [r15+18h]
0x180012e34  lea     r14, [rax+rax*4]
0x180012e38  shl     r14, 5
0x180012e3c  mov     ecx, [r14+rdx]
0x180012e40  sub     ecx, 1
0x180012e43  jz      loc_180013243
0x180012e49  sub     ecx, 1
0x180012e4c  jz      loc_180013027
0x180012e52  sub     ecx, 1
0x180012e55  jz      loc_180012FBF
0x180012e5b  sub     ecx, 1
0x180012e5e  jz      short loc_180012ED7
0x180012e60  cmp     ecx, 1
0x180012e63  jnz     loc_180013259
0x180012e69  mov     r8, [r14+rdx+8]; struct _WS_XML_BUFFER *
0x180012e6e  lea     rax, [rdx+90h]
0x180012e75  add     rax, r14
0x180012e78  mov     rdx, rbp; struct _CRYPT_XML_WS_STATE *
0x180012e7b  mov     [rsp+98h+var_70], rax; struct _CRYPT_XML_BLOB *
0x180012e80  mov     rcx, r13; hHeap
0x180012e83  mov     [rsp+98h+var_78], r12d; unsigned int
0x180012e88  call    ?I_XmlGetEncoded@@YAJPEAXPEAU_CRYPT_XML_WS_STATE@@PEAU_WS_XML_BUFFER@@W4WS_CHARSET@@KPEAU_CRYPT_XML_BLOB@@@Z; I_XmlGetEncoded(void *,_CRYPT_XML_WS_STATE *,_WS_XML_BUFFER *,WS_CHARSET,ulong,_CRYPT_XML_BLOB *)
0x180012e8d  mov     esi, eax
0x180012e8f  test    eax, eax
0x180012e91  jns     loc_180013259
0x180012e97  lea     r8, aOnecoreDsSecur_1+35h; ""
0x180012e9e  lea     rax, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180012ea5  nop     word ptr [rax+rax+00000000h]
0x180012eb0  movzx   edx, byte ptr [r8-1]
0x180012eb5  mov     r9, r8
0x180012eb8  dec     r8
0x180012ebb  cmp     dl, 5Ch ; '\'
0x180012ebe  jz      short loc_180012EC8
0x180012ec0  cmp     r8, rax
0x180012ec3  ja      short loc_180012EB0
0x180012ec5  cmp     dl, 5Ch ; '\'
0x180012ec8  cmovz   r8, r9
0x180012ecc  mov     r9d, 678h
0x180012ed2  jmp     loc_180014022
0x180012ed7  mov     ecx, [r14+rdx+8]
0x180012edc  lea     rax, [rcx+rcx*2]
0x180012ee0  lea     rbx, [rbx+rax*8]
0x180012ee4  test    ecx, ecx
0x180012ee6  jz      loc_180013259
0x180012eec  xor     edi, edi
0x180012eee  xchg    ax, ax
0x180012ef0  mov     r8, [r14+rdx+10h]
0x180012ef5  mov     eax, edi
0x180012ef7  imul    rcx, rax, 38h ; '8'
0x180012efb  add     r8, rcx
0x180012efe  mov     eax, [r8]
0x180012f01  dec     eax; switch 6 cases
0x180012f03  cmp     eax, 5
0x180012f06  ja      def_180012F19; jumptable 0000000180012F19 default case
0x180012f0c  cdqe
0x180012f0e  mov     ecx, ds:(jpt_180012F19 - 180000000h)[r10+rax*4]
0x180012f16  add     rcx, r10
0x180012f19  jmp     rcx; switch jump
0x180012f1f  mov     eax, [r8+18h]; jumptable 0000000180012F19 case 1
0x180012f23  inc     eax
0x180012f25  lea     rcx, ds:7[rax*2]
0x180012f2d  mov     eax, [r8+8]
0x180012f31  inc     eax
0x180012f33  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180012f37  lea     rax, ds:7[rax*2]
0x180012f3f  and     rax, 0FFFFFFFFFFFFFFF8h
0x180012f43  add     rbx, rax
0x180012f46  add     rbx, rcx
0x180012f49  jmp     short def_180012F19; jumptable 0000000180012F19 default case
0x180012f4b  mov     eax, [r8+8]; jumptable 0000000180012F19 cases 2,4,5
0x180012f4f  add     rax, 7
0x180012f53  and     rax, 0FFFFFFFFFFFFFFF8h
0x180012f57  add     rbx, rax
0x180012f5a  jmp     short def_180012F19; jumptable 0000000180012F19 default case
0x180012f5c  mov     eax, [r8+8]; jumptable 0000000180012F19 case 3
0x180012f60  inc     eax
0x180012f62  lea     rax, ds:7[rax*2]
0x180012f6a  and     rax, 0FFFFFFFFFFFFFFF8h
0x180012f6e  add     rbx, rax
0x180012f71  jmp     short def_180012F19; jumptable 0000000180012F19 default case
0x180012f73  lea     rax, [r8+28h]; jumptable 0000000180012F19 case 6
0x180012f77  mov     rdx, rbp; struct _CRYPT_XML_WS_STATE *
0x180012f7a  mov     r8, [r8+8]; struct _WS_XML_BUFFER *
0x180012f7e  mov     rcx, r13; hHeap
0x180012f81  mov     [rsp+98h+var_70], rax; struct _CRYPT_XML_BLOB *
0x180012f86  mov     [rsp+98h+var_78], r12d; unsigned int
0x180012f8b  call    ?I_XmlGetEncoded@@YAJPEAXPEAU_CRYPT_XML_WS_STATE@@PEAU_WS_XML_BUFFER@@W4WS_CHARSET@@KPEAU_CRYPT_XML_BLOB@@@Z; I_XmlGetEncoded(void *,_CRYPT_XML_WS_STATE *,_WS_XML_BUFFER *,WS_CHARSET,ulong,_CRYPT_XML_BLOB *)
0x180012f90  mov     esi, eax
0x180012f92  test    eax, eax
0x180012f94  js      loc_180013287
0x180012f9a  mov     r9d, [rsp+98h+arg_8]
0x180012fa2  lea     r10, __ImageBase
0x180012fa9  mov     rdx, [r15+18h]; jumptable 0000000180012F19 default case
0x180012fad  inc     edi
0x180012faf  cmp     edi, [rdx+r14+8]
0x180012fb4  jb      loc_180012EF0
0x180012fba  jmp     loc_180013259
0x180012fbf  mov     r8, [r14+rdx+8]; struct _WS_XML_BUFFER *
0x180012fc4  lea     rax, [rdx+90h]
0x180012fcb  add     rax, r14
0x180012fce  mov     rdx, rbp; struct _CRYPT_XML_WS_STATE *
0x180012fd1  mov     [rsp+98h+var_70], rax; struct _CRYPT_XML_BLOB *
0x180012fd6  mov     rcx, r13; hHeap
0x180012fd9  mov     [rsp+98h+var_78], r12d; unsigned int
0x180012fde  call    ?I_XmlGetEncoded@@YAJPEAXPEAU_CRYPT_XML_WS_STATE@@PEAU_WS_XML_BUFFER@@W4WS_CHARSET@@KPEAU_CRYPT_XML_BLOB@@@Z; I_XmlGetEncoded(void *,_CRYPT_XML_WS_STATE *,_WS_XML_BUFFER *,WS_CHARSET,ulong,_CRYPT_XML_BLOB *)
0x180012fe3  mov     esi, eax
0x180012fe5  test    eax, eax
0x180012fe7  jns     loc_180013259
0x180012fed  lea     r8, aOnecoreDsSecur_1+35h; ""
0x180012ff4  lea     rax, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180012ffb  nop     dword ptr [rax+rax+00h]
0x180013000  movzx   edx, byte ptr [r8-1]
0x180013005  mov     r9, r8
0x180013008  dec     r8
0x18001300b  cmp     dl, 5Ch ; '\'
0x18001300e  jz      short loc_180013018
0x180013010  cmp     r8, rax
0x180013013  ja      short loc_180013000
0x180013015  cmp     dl, 5Ch ; '\'
0x180013018  cmovz   r8, r9
0x18001301c  mov     r9d, 633h
0x180013022  jmp     loc_180014022
0x180013027  mov     ecx, [r14+rdx+8]
0x18001302c  sub     ecx, 1
0x18001302f  jz      loc_1800131D1
0x180013035  sub     ecx, 1
0x180013038  jz      loc_1800131C2
0x18001303e  sub     ecx, 1
0x180013041  jz      loc_180013147
0x180013047  sub     ecx, 1
0x18001304a  jz      loc_1800130D5
0x180013050  cmp     ecx, 1
0x180013053  jnz     loc_180013259
0x180013059  mov     eax, [r14+rdx+10h]
0x18001305e  cmp     eax, 2
0x180013061  jnz     short loc_18001307B
0x180013063  mov     eax, [r14+rdx+18h]
0x180013068  inc     eax
0x18001306a  lea     rax, ds:7[rax*2]
0x180013072  and     rax, 0FFFFFFFFFFFFFFF8h
0x180013076  add     rbx, rax
0x180013079  jmp     short loc_1800130AB
0x18001307b  cmp     eax, 1
0x18001307e  jnz     short loc_1800130AB
0x180013080  mov     r8, [r14+rdx+18h]; struct _WS_XML_BUFFER *
0x180013085  lea     rax, [rdx+28h]
0x180013089  add     rax, r14
0x18001308c  mov     rdx, rbp; struct _CRYPT_XML_WS_STATE *
0x18001308f  mov     [rsp+98h+var_70], rax; struct _CRYPT_XML_BLOB *
0x180013094  mov     rcx, r13; hHeap
0x180013097  mov     [rsp+98h+var_78], r12d; unsigned int
0x18001309c  call    ?I_XmlGetEncoded@@YAJPEAXPEAU_CRYPT_XML_WS_STATE@@PEAU_WS_XML_BUFFER@@W4WS_CHARSET@@KPEAU_CRYPT_XML_BLOB@@@Z; I_XmlGetEncoded(void *,_CRYPT_XML_WS_STATE *,_WS_XML_BUFFER *,WS_CHARSET,ulong,_CRYPT_XML_BLOB *)
0x1800130a1  mov     esi, eax
0x1800130a3  test    eax, eax
0x1800130a5  js      loc_1800132C7
0x1800130ab  mov     rax, [r15+18h]
0x1800130af  mov     eax, [rax+r14+38h]
0x1800130b4  test    al, 1
0x1800130b6  jz      loc_180013307
0x1800130bc  lea     ecx, [rax-1]
0x1800130bf  shr     rcx, 1
0x1800130c2  add     rcx, 7
0x1800130c6  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800130ca  add     rcx, rcx
0x1800130cd  add     rbx, rcx
0x1800130d0  jmp     loc_180013259
0x1800130d5  mov     r8, [r14+rdx+10h]; struct _WS_XML_BUFFER *
0x1800130da  lea     rax, [rdx+80h]
0x1800130e1  add     rax, r14
0x1800130e4  mov     rdx, rbp; struct _CRYPT_XML_WS_STATE *
0x1800130e7  mov     [rsp+98h+var_70], rax; struct _CRYPT_XML_BLOB *
0x1800130ec  mov     rcx, r13; hHeap
0x1800130ef  mov     [rsp+98h+var_78], r12d; unsigned int
0x1800130f4  call    ?I_XmlGetEncoded@@YAJPEAXPEAU_CRYPT_XML_WS_STATE@@PEAU_WS_XML_BUFFER@@W4WS_CHARSET@@KPEAU_CRYPT_XML_BLOB@@@Z; I_XmlGetEncoded(void *,_CRYPT_XML_WS_STATE *,_WS_XML_BUFFER *,WS_CHARSET,ulong,_CRYPT_XML_BLOB *)
0x1800130f9  mov     esi, eax
0x1800130fb  test    eax, eax
0x1800130fd  jns     loc_180013259
0x180013103  lea     r8, aOnecoreDsSecur_1+35h; ""
0x18001310a  lea     rax, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180013111  nop     dword ptr [rax+00h]
0x180013115  nop     word ptr [rax+rax+00000000h]
0x180013120  movzx   edx, byte ptr [r8-1]
0x180013125  mov     r9, r8
0x180013128  dec     r8
0x18001312b  cmp     dl, 5Ch ; '\'
0x18001312e  jz      short loc_180013138
0x180013130  cmp     r8, rax
0x180013133  ja      short loc_180013120
0x180013135  cmp     dl, 5Ch ; '\'
0x180013138  cmovz   r8, r9
0x18001313c  mov     r9d, 61Fh
0x180013142  jmp     loc_180014022
0x180013147  mov     eax, [r14+rdx+10h]
0x18001314c  cmp     eax, 2
0x18001314f  jnz     short loc_180013169
0x180013151  mov     eax, [r14+rdx+18h]
0x180013156  inc     eax
0x180013158  lea     rax, ds:7[rax*2]
0x180013160  and     rax, 0FFFFFFFFFFFFFFF8h
0x180013164  add     rbx, rax
0x180013167  jmp     short loc_180013199
0x180013169  cmp     eax, 1
0x18001316c  jnz     short loc_180013199
0x18001316e  mov     r8, [r14+rdx+18h]; struct _WS_XML_BUFFER *
0x180013173  lea     rax, [rdx+28h]
0x180013177  add     rax, r14
0x18001317a  mov     rdx, rbp; struct _CRYPT_XML_WS_STATE *
0x18001317d  mov     [rsp+98h+var_70], rax; struct _CRYPT_XML_BLOB *
0x180013182  mov     rcx, r13; hHeap
0x180013185  mov     [rsp+98h+var_78], r12d; unsigned int
0x18001318a  call    ?I_XmlGetEncoded@@YAJPEAXPEAU_CRYPT_XML_WS_STATE@@PEAU_WS_XML_BUFFER@@W4WS_CHARSET@@KPEAU_CRYPT_XML_BLOB@@@Z; I_XmlGetEncoded(void *,_CRYPT_XML_WS_STATE *,_WS_XML_BUFFER *,WS_CHARSET,ulong,_CRYPT_XML_BLOB *)
0x18001318f  mov     esi, eax
0x180013191  test    eax, eax
0x180013193  js      loc_180013347
0x180013199  mov     rax, [r15+18h]
0x18001319d  mov     ecx, [rax+r14+38h]
0x1800131a2  mov     edx, [rax+r14+48h]
0x1800131a7  add     rcx, 7
0x1800131ab  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800131af  add     rdx, 7
0x1800131b3  add     rbx, rcx
0x1800131b6  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800131ba  add     rbx, rdx
0x1800131bd  jmp     loc_180013259
0x1800131c2  mov     ecx, [r14+rdx+20h]
0x1800131c7  add     rcx, 7
0x1800131cb  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800131cf  jmp     short loc_18001322E
0x1800131d1  mov     ecx, [r14+rdx+70h]
0x1800131d6  mov     eax, [r14+rdx+60h]
0x1800131db  add     rcx, 7
0x1800131df  add     rax, 7
0x1800131e3  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800131e7  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800131eb  add     rcx, rax
0x1800131ee  mov     eax, [r14+rdx+50h]
0x1800131f3  add     rax, 7
0x1800131f7  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800131fb  add     rcx, rax
0x1800131fe  mov     eax, [r14+rdx+40h]
0x180013203  add     rax, 7
0x180013207  and     rax, 0FFFFFFFFFFFFFFF8h
0x18001320b  add     rcx, rax
0x18001320e  mov     eax, [r14+rdx+30h]
0x180013213  add     rax, 7
0x180013217  and     rax, 0FFFFFFFFFFFFFFF8h
0x18001321b  add     rcx, rax
0x18001321e  mov     eax, [r14+rdx+20h]
0x180013223  add     rax, 7
0x180013227  and     rax, 0FFFFFFFFFFFFFFF8h
0x18001322b  add     rcx, rax
0x18001322e  mov     eax, [r14+rdx+10h]
0x180013233  add     rax, 7
0x180013237  and     rax, 0FFFFFFFFFFFFFFF8h
0x18001323b  add     rbx, rax
0x18001323e  add     rbx, rcx
0x180013241  jmp     short loc_180013259
0x180013243  mov     eax, [r14+rdx+8]
0x180013248  inc     eax
0x18001324a  lea     rax, ds:7[rax*2]
0x180013252  and     rax, 0FFFFFFFFFFFFFFF8h
0x180013256  add     rbx, rax
  ... truncated ...
```
