# CCookieJar::SetCookieParsed(HTTP_REQUEST_HANDLE_OBJECT *,char const *,char *,char *,char *,char *,ulong &,P3PCookieState *,_FILETIME,ulong *,int,int,_LIST_ENTRY *)

- ea: `0x18006a6b0`
- end: `0x18006c0c8`
- name: `?SetCookieParsed@CCookieJar@@SAKPEAVHTTP_REQUEST_HANDLE_OBJECT@@PEBDPEAD222AEAKPEAUP3PCookieState@@U_FILETIME@@PEAKHHPEAU_LIST_ENTRY@@@Z`
- size: `6680`
- prototype: `static unsigned int(struct HTTP_REQUEST_HANDLE_OBJECT *, const char *, char *, char *, char *, char *, unsigned int *, struct P3PCookieState *, struct _FILETIME, unsigned int *, int, int, struct _LIST_ENTRY *)`
- caller_count: `3`
- callee_count: `40`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800697d0`
- `0x18006c5b0`
- `0x1800c6418`

## callees

- `0x18000660c`
- `0x180009cf0`
- `0x180011930`
- `0x180018d2c`
- `0x18006a6b0`
- `0x18006c0d0`
- `0x18006c4b0`
- `0x18006dd10`
- `0x1800701d0`
- `0x180095350`
- `0x1800955f0`
- `0x180096edc`
- `0x180096ef0`
- `0x18009726c`
- `0x1800e0780`
- `0x1800e08a0`
- `0x1800f5c60`
- `0x1800f6500`
- `0x1800fa3ac`
- `0x1800fa4d4`
- `0x1800fafcc`
- `0x1800fb0f8`
- `0x180108864`
- `0x18013a158`
- `0x18014a3a4`
- `0x18014a7a0`
- `0x1801538e4`
- `0x18017fb54`
- `0x180180214`
- `0x1801c9c31`
- `0x1801d6198`
- `0x1801d6234`
- `0x1801d62f0`
- `0x1801d6670`
- `0x1801d675c`
- `0x1801e0700`
- `0x1801e1790`
- `0x1801e3714`
- `0x1801e3c78`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c05f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c07e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c05f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c07e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b60a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b68e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b6e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b7b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006be9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b60a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b68e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b6e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b7b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006be9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b3ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b3ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a87c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a87c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18006adf9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18006adf9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b065`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b065`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b0c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b30e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b34a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b3d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006beee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bf06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bf7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bff0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c030`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c045`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b0c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b30e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b34a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b3d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006beee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bf06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bf7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bff0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c030`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c045`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006a98c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006a98c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006aff8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006b032`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006b095`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006aff8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006b032`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006b095`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18006b835`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18006b835`

## pseudocode

```c
__int64 __fastcall CCookieJar::SetCookieParsed(
        struct HTTP_REQUEST_HANDLE_OBJECT *a1,
        char *a2,
        char *a3,
        char *a4,
        char *a5,
        char *a6,
        unsigned int *a7,
        struct P3PCookieState *a8,
        __int64 Buf1,
        unsigned int *a10,
        int a11,
        int a12,
        struct _LIST_ENTRY *a13)
{
  char *v13; // r14
  char *v15; // r13
  unsigned int *v16; // rcx
  int v17; // edi
  __int64 v18; // rbx
  int v19; // esi
  unsigned int v20; // r12d
  LPCSTR v21; // r8
  CHAR v22; // cl
  char *v23; // rax
  CHAR *v24; // rax
  CHAR i; // cl
  char v26; // cl
  char *v27; // rax
  CHAR v28; // cl
  CHAR *v29; // rax
  unsigned int v30; // eax
  char v31; // al
  char *v32; // rcx
  int v33; // edi
  BOOL v34; // r8d
  unsigned int v35; // eax
  int v36; // ecx
  int v37; // eax
  int v38; // edx
  int v39; // r12d
  int v40; // eax
  int v41; // r15d
  int v42; // eax
  int v43; // edx
  unsigned int *v44; // rdi
  int v45; // eax
  unsigned __int16 v46; // ax
  __int16 v47; // r9
  __int16 v48; // r10
  __int16 v49; // r11
  unsigned __int16 v50; // ax
  __int16 v51; // r9
  __int16 v52; // r10
  __int16 v53; // r11
  WCHAR *v54; // rsi
  __int64 v55; // rcx
  int LastError; // eax
  signed int HostInternal; // edi
  unsigned __int16 *v58; // r12
  _BYTE *v59; // r9
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // rcx
  _BYTE *v63; // rax
  unsigned __int64 v64; // r10
  WCHAR *v65; // r13
  CHAR v66; // cl
  unsigned int v67; // edx
  CHAR *v68; // r8
  CHAR *v69; // r8
  CHAR *j; // r9
  CHAR v71; // cl
  __int64 k; // r9
  CHAR *v73; // r8
  CHAR *m; // r9
  CHAR v75; // cl
  __int64 v76; // rcx
  __int64 v77; // r15
  __int64 v78; // rcx
  __int64 v79; // rcx
  unsigned __int64 v80; // rcx
  unsigned int v81; // r14d
  WCHAR *lpWideCharStr; // rax
  int v83; // eax
  unsigned __int16 *v84; // rax
  __int64 v85; // rcx
  unsigned int v86; // esi
  __int64 v87; // r8
  unsigned int v88; // edi
  unsigned int v89; // r9d
  unsigned int v90; // r10d
  unsigned int v91; // r11d
  unsigned int v92; // r14d
  __int64 v93; // rdx
  unsigned __int64 v95; // rax
  unsigned int v96; // esi
  void *v97; // r8
  int v98; // edx
  int v99; // ecx
  int v100; // r8d
  int v101; // r12d
  struct CCookieHost *v102; // rsi
  int v103; // edi
  char *v104; // r14
  int v105; // edi
  __int64 v106; // r10
  __int64 v107; // r9
  struct CCookieLocation **v108; // rsi
  char *v109; // rax
  signed __int64 v110; // r8
  int v111; // ecx
  int v112; // edx
  const CHAR *v113; // rax
  const CHAR *v114; // r8
  int v115; // ecx
  int v116; // edx
  struct CCookieLocation *v117; // rcx
  unsigned int *v118; // rsi
  const char *v119; // rdi
  struct CCookie *Cookie; // rax
  int v121; // eax
  struct CCookie *v122; // rax
  struct CCookie *v123; // rbx
  int v124; // eax
  __int64 v125; // rdx
  struct _LIST_ENTRY *v126; // rcx
  CCookieLocation *v127; // r15
  BOOL v128; // r12d
  LPCCH *v129; // r13
  CHAR *v130; // rsi
  int v131; // r14d
  LPCCH *v132; // rdi
  LPCCH v133; // r9
  const CHAR *v134; // rax
  const CHAR *v135; // r8
  int v136; // ecx
  int v137; // edx
  int v138; // edx
  unsigned int *v139; // r13
  CCookieLocation *v140; // rsi
  char *v141; // r12
  _QWORD *v142; // rdi
  int v143; // r9d
  char v144; // r15
  _QWORD *v145; // r14
  LPCCH v146; // rax
  __int64 v147; // r8
  int v148; // ecx
  int v149; // edx
  struct CCookie *v150; // rax
  struct HTTP_REQUEST_HANDLE_OBJECT *v151; // r14
  int v152; // esi
  __int64 v153; // rdx
  __int64 v154; // rax
  unsigned int v155; // esi
  LPCCH v156; // r14
  __int64 v157; // rcx
  _BYTE *v158; // rax
  unsigned int v159; // r8d
  __int16 v160; // r13
  __int64 v161; // rcx
  char *v162; // rax
  unsigned int v163; // r8d
  __int16 v164; // r12
  struct _RTL_CRITICAL_SECTION *v165; // rdx
  __int64 v166; // rcx
  struct _RTL_CRITICAL_SECTION *v167; // rax
  unsigned int v168; // r8d
  unsigned __int16 v169; // r14
  _BYTE *v170; // r15
  __int64 v171; // rcx
  _BYTE *v172; // rax
  unsigned int v173; // edx
  const CHAR *v174; // rsi
  const char *v175; // rdx
  int v176; // esi
  unsigned int v177; // r8d
  struct CCookieHost *v178; // r14
  void **v179; // rbx
  void *v180; // r8
  bool v181; // zf
  void **v182; // rsi
  void **v183; // rdi
  void **v184; // rbx
  void *v185; // r8
  void **v186; // rbx
  void *v187; // r8
  __int64 v188; // rbx
  int v190; // [rsp+60h] [rbp-A0h]
  int v191; // [rsp+64h] [rbp-9Ch]
  unsigned int v192; // [rsp+68h] [rbp-98h]
  int v193; // [rsp+6Ch] [rbp-94h]
  __int16 v194; // [rsp+6Ch] [rbp-94h]
  int v195; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v196; // [rsp+78h] [rbp-88h] BYREF
  int v197; // [rsp+80h] [rbp-80h]
  struct _FILETIME v198; // [rsp+88h] [rbp-78h] BYREF
  int v199; // [rsp+90h] [rbp-70h] BYREF
  int v200; // [rsp+94h] [rbp-6Ch]
  LPCCH lpMultiByteStr; // [rsp+98h] [rbp-68h]
  LPCCH v202; // [rsp+A0h] [rbp-60h]
  LPCSTR lpString1; // [rsp+A8h] [rbp-58h]
  int v204; // [rsp+B0h] [rbp-50h]
  int v205; // [rsp+B4h] [rbp-4Ch]
  unsigned int *v206; // [rsp+B8h] [rbp-48h]
  const char *v207; // [rsp+C0h] [rbp-40h]
  LPVOID Src; // [rsp+C8h] [rbp-38h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+D0h] [rbp-30h]
  char *v210; // [rsp+D8h] [rbp-28h]
  struct HTTP_REQUEST_HANDLE_OBJECT *v211; // [rsp+E0h] [rbp-20h]
  struct _LIST_ENTRY *v212; // [rsp+E8h] [rbp-18h]
  LPVOID v213; // [rsp+F0h] [rbp-10h]
  unsigned int *v214; // [rsp+F8h] [rbp-8h]
  CCookieLocation *v215; // [rsp+100h] [rbp+0h] BYREF
  LPVOID lpMem; // [rsp+108h] [rbp+8h] BYREF
  struct CCookieHost *v217; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v218; // [rsp+118h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+120h] [rbp+20h] BYREF
  char *v220; // [rsp+130h] [rbp+30h] BYREF
  LPCSTR v221; // [rsp+138h] [rbp+38h]
  _QWORD v222[2]; // [rsp+140h] [rbp+40h] BYREF
  LPCCH v223; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v224; // [rsp+158h] [rbp+58h]
  _BYTE v225[20]; // [rsp+15Ch] [rbp+5Ch] BYREF
  CHAR MultiByteStr[272]; // [rsp+170h] [rbp+70h] BYREF
  char v227[256]; // [rsp+280h] [rbp+180h] BYREF

  v13 = a6;
  v15 = a2;
  lpMultiByteStr = a3;
  v207 = a2;
  v211 = a1;
  v16 = a10;
  lpString1 = a5;
  v214 = a10;
  v215 = 0;
  v192 = 0;
  SystemTimeAsFileTime = 0;
  v198 = 0;
  Src = 0;
  v213 = 0;
  v217 = 0;
  v202 = a4;
  v210 = a6;
  v206 = a7;
  v212 = a13;
  v17 = a12;
  v18 = Buf1;
  if ( (xmmword_180266B60 & 2) != 0 )
  {
    WPP_SF_sssssDill(
      Buf1,
      (_DWORD)a5,
      0,
      (_DWORD)a2,
      (__int64)a3,
      (__int64)a4,
      (__int64)a5,
      (__int64)a6,
      *a7,
      Buf1,
      a11,
      a12);
    v16 = v214;
  }
  if ( v16 )
    *v16 = 0;
  if ( !(unsigned int)PathAndRDomainFromURL(v15, 1) )
  {
    if ( (xmmword_180266B50 & 2) != 0 )
      WPP_SF_(513, 48, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
    v19 = 0;
    v20 = 0;
    goto LABEL_419;
  }
  v205 = GlobalSuppressCookiePersist;
  if ( GlobalSuppressCookiePersist )
    *a7 |= 2u;
  v21 = lpString1;
  if ( lpString1 )
  {
    if ( !(unsigned int)IsDomainLegal(lpString1, Src) )
    {
LABEL_17:
      if ( (xmmword_180266B50 & 2) != 0 )
        WPP_SF_(513, 49, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
      SetLastError(0x57u);
      v19 = 0;
      v20 = 0;
      goto LABEL_419;
    }
    v21 = lpString1;
  }
  if ( a6 && *a6 && *a6 != 47 )
    goto LABEL_17;
  if ( a3 )
  {
    v22 = *a3;
    if ( *a3 )
    {
      v23 = a3;
      do
      {
        if ( (unsigned __int8)v22 <= 0x1Fu )
          *v23 = 95;
        v22 = *++v23;
      }
      while ( v22 );
    }
  }
  v24 = (CHAR *)v202;
  if ( v202 )
  {
    for ( i = *v202; i; ++v24 )
    {
      if ( (unsigned __int8)i <= 0x1Fu )
        *v24 = 95;
      i = v24[1];
    }
  }
  if ( a6 )
  {
    v26 = *a6;
    if ( *a6 )
    {
      v27 = a6;
      do
      {
        if ( (unsigned __int8)v26 <= 0x1Fu )
          *v27 = 95;
        v26 = *++v27;
      }
      while ( v26 );
    }
  }
  if ( v21 )
  {
    v28 = *v21;
    if ( *v21 )
    {
      v29 = (CHAR *)v21;
      do
      {
        if ( (unsigned __int8)v28 <= 0x1Fu )
          *v29 = 95;
        v28 = *++v29;
      }
      while ( v28 );
    }
    v30 = *a7;
  }
  else
  {
    v30 = *a7;
    if ( v17 )
    {
      v30 |= 0x4000u;
      *a7 = v30;
    }
    lpString1 = (LPCSTR)Src;
  }
  if ( v17 )
    *a7 = v30 | 0x80000;
  if ( a6 || (v13 = (char *)v213, (v210 = (char *)v213) != 0) )
  {
    v31 = *v13;
    if ( *v13 )
    {
      v32 = v13;
      while ( v31 != 63 && v31 != 35 )
      {
        v31 = *++v32;
        if ( !v31 )
          goto LABEL_58;
      }
      *v32 = 0;
    }
  }
LABEL_58:
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( *(_QWORD *)&SystemTimeAsFileTime <= v18 )
    v33 = -(v18 != SystemTimeAsFileTime);
  else
    v33 = 1;
  v34 = v33 > 0;
  v197 = v34;
  if ( v211 && *((_DWORD *)v211 + 1336) || (v35 = *a7, (*a7 & 0x10) != 0) )
  {
    v204 = 1;
    if ( (xmmword_180266B60 & 2) != 0 )
    {
      WPP_SF_(1025, 50, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
      v34 = v197;
    }
    *a7 |= 0x80000000;
    v36 = 33;
    v35 = *a7;
  }
  else
  {
    v204 = 0;
    v36 = 1;
  }
  v37 = v35 & 2;
  v38 = 8;
  if ( !v37 )
    v38 = 16;
  v39 = 0;
  v193 = 0;
  v195 = v36 | v38;
  if ( v33 <= 0 && a8 && (!v37 || (*((_BYTE *)a8 + 12) & 4) != 0) )
  {
    v40 = 1;
  }
  else
  {
    v40 = 0;
    if ( !a8 )
      goto LABEL_90;
  }
  if ( !*((_DWORD *)a8 + 4) )
  {
    v41 = 1;
    goto LABEL_78;
  }
LABEL_90:
  v41 = 0;
  v190 = 0;
  if ( !a8 )
    goto LABEL_79;
  if ( *((_DWORD *)a8 + 4) == 3 )
  {
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_(1025, 51, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
    v45 = 5;
    v190 = 0;
    goto LABEL_97;
  }
LABEL_78:
  v190 = v41;
LABEL_79:
  if ( !v40 || v41 )
  {
    v45 = 1;
    v197 = v34;
LABEL_97:
    v44 = v206;
    v191 = v45;
    goto LABEL_98;
  }
  v42 = 0;
  if ( a8 )
  {
    v43 = 512;
    if ( *((_DWORD *)a8 + 2) != 3 )
      v43 = 0;
    v42 = v43 | 2;
    if ( *((_DWORD *)a8 + 2) != 4 )
      v42 = v43;
  }
  v44 = v206;
  *v206 |= v42;
  v45 = *((_DWORD *)a8 + 2);
  v191 = v45;
  if ( v45 == 5 )
  {
    if ( (xmmword_180266B60 & 2) != 0 )
    {
      WPP_SF_(1025, 52, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
      v45 = 5;
    }
    v39 = 1;
    v193 = 1;
    v197 = 1;
  }
  else
  {
    v197 = v34;
  }
LABEL_98:
  if ( (*(_BYTE *)v44 & 0x20) == 0 && v45 != 2 )
  {
    v19 = v191;
    if ( v191 == 5 )
    {
      v192 = 0;
      LOBYTE(v199) = BYTE1(Microsoft_Windows_WinINetEnableBits) & 0x10;
      if ( (Microsoft_Windows_WinINetEnableBits & 0x1000) != 0 )
      {
        StringCchCopyA(v227, 0x100u, lpString1);
        FormatReverseDomain(v227);
      }
      if ( !v39 )
      {
        if ( (xmmword_180266B50 & 2) != 0 )
          WPP_SF_(513, 57, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
        if ( (Microsoft_Windows_WinINetEnableBits & 0x1000) != 0 )
        {
          inetstrlenUShortA(v202);
          inetstrlenUShortA(lpMultiByteStr);
          inetstrlenUShortA(v13);
          v50 = inetstrlenUShortA(v227);
          McTemplateU0hsr0hsr2hsr4hsr6_EventWriteTransfer(
            (unsigned int)&WININET_Context,
            (unsigned int)&WININET_COOKIE_BLOCKED,
            v50,
            (unsigned int)v227,
            v51,
            (__int64)v13,
            v52,
            (__int64)lpMultiByteStr,
            v53,
            (__int64)v202);
        }
        goto LABEL_418;
      }
      if ( (xmmword_180266B50 & 2) != 0 )
        WPP_SF_(513, 56, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
      if ( (Microsoft_Windows_WinINetEnableBits & 0x1000) != 0 )
      {
        inetstrlenUShortA(v202);
        inetstrlenUShortA(lpMultiByteStr);
        inetstrlenUShortA(v13);
        v46 = inetstrlenUShortA(v227);
        McTemplateU0hsr0hsr2hsr4hsr6_EventWriteTransfer(
          (unsigned int)&WININET_Context,
          (unsigned int)&WININET_COOKIE_P3P_REJECTED,
          v46,
          (unsigned int)v227,
          v47,
          (__int64)v13,
          v48,
          (__int64)lpMultiByteStr,
          v49,
          (__int64)v202);
      }
    }
LABEL_123:
    v54 = 0;
    lpMem = 0;
    v218 = 0;
    v217 = 0;
    HIDWORD(v196) = 0;
    if ( InitOnceExecuteOnce(&CCookieJar::g_InitOnce, CCookieJar::InitOnceCallback, 0, 0) )
    {
      HostInternal = 0;
      lpCriticalSection = (LPCRITICAL_SECTION)CCookieJar::g_pInstance;
    }
    else
    {
      lpCriticalSection = 0;
      LastError = WxGetLastError(v55);
      HostInternal = LastError;
      if ( LastError > 0 )
        HostInternal = (unsigned __int16)LastError | 0x80070000;
      HIDWORD(v196) = 622;
      if ( HostInternal >= 0 )
        HostInternal = -2147418113;
    }
    if ( HostInternal < 0 )
    {
      HIDWORD(v196) = 724;
LABEL_228:
      v97 = lpMem;
      if ( lpMem )
      {
        lpMem = 0;
        if ( g_fWxHeapExtensionInitialized )
          g_WxHeapExtensionInterfaces(v97);
        else
          HeapFree(g_hWxProcessHeap, 0, v97);
        lpMem = 0;
      }
      if ( HostInternal >= 0 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v217 + 56));
        CCookieHost::Sync(v217);
        v101 = v197;
        v102 = v217;
        v103 = v197 ^ 1;
        HIDWORD(v207) = 0;
        v104 = v210;
        if ( (xmmword_180266B60 & 2) != 0 )
          WPP_SF_sslq(v99, v98, v100, (_DWORD)lpString1, (__int64)v210, v197 ^ 1, (__int64)&v215);
        if ( !lpString1 )
        {
          v105 = -2147024809;
          HIDWORD(v207) = 1085;
          goto LABEL_261;
        }
        if ( !v104 )
        {
          v105 = -2147024809;
          HIDWORD(v207) = 1086;
          goto LABEL_261;
        }
        v215 = 0;
        v106 = -1;
        do
          ++v106;
        while ( v104[v106] );
        v107 = *((_QWORD *)v102 + 5);
        v108 = (struct CCookieLocation **)((char *)v102 + 40);
        if ( v107 )
        {
          while ( 1 )
          {
            if ( *(_DWORD *)(v107 + 40) < (unsigned int)v106 )
              goto LABEL_254;
            if ( *(_DWORD *)(v107 + 40) == (_DWORD)v106 )
            {
              v109 = *(char **)(v107 + 32);
              v110 = v104 - v109;
              do
              {
                v111 = (unsigned __int8)v109[v110];
                v112 = (unsigned __int8)*v109 - v111;
                if ( v112 )
                  break;
                ++v109;
              }
              while ( v111 );
              if ( !v112 )
              {
                v113 = *(const CHAR **)(v107 + 16);
                v114 = (const CHAR *)(lpString1 - v113);
                do
                {
                  v115 = (unsigned __int8)v114[(_QWORD)v113];
                  v116 = *(unsigned __int8 *)v113 - v115;
                  if ( v116 )
                    break;
                  ++v113;
                }
                while ( v115 );
                if ( !v116 )
                  break;
              }
            }
            v108 = (struct CCookieLocation **)(v107 + 8);
            v107 = *(_QWORD *)(v107 + 8);
            if ( !v107 )
              goto LABEL_254;
          }
          v215 = (CCookieLocation *)v107;
        }
        else
        {
LABEL_254:
          if ( !v103 )
          {
            v105 = 1;
            goto LABEL_261;
          }
          v117 = CCookieLocation::Construct(lpString1, v104);
          if ( !v117 )
          {
            v105 = -2147024882;
            HIDWORD(v207) = 1114;
            goto LABEL_261;
          }
          *((_QWORD *)v117 + 1) = *v108;
          *v108 = v117;
          v215 = v117;
        }
        v105 = 0;
LABEL_261:
        if ( (xmmword_180266B60 & 2) != 0 )
          WPP_SF_d(1025, 24, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids, (unsigned int)v105);
        if ( v105 < 0 )
          goto LABEL_302;
        if ( !v215 )
        {
          v20 = 1;
          goto LABEL_303;
        }
        v118 = v206;
        v119 = lpMultiByteStr;
        if ( !a11 )
        {
          Cookie = CCookieLocation::GetCookie(v215, lpMultiByteStr, (*v206 >> 19) & 1, (*v206 >> 14) & 1, 0);
          if ( Cookie )
          {
            if ( (*((_DWORD *)Cookie + 4) & 0x2000) != 0 && !(unsigned int)CCookie::IsExpired(Cookie) )
            {
              v19 = 5;
              v20 = 4;
              if ( (xmmword_180266B60 & 2) != 0 )
              {
                WPP_SF_ss(
                  1025,
                  58,
                  (unsigned int)&WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids,
                  (_DWORD)v15,
                  (__int64)v119);
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v217 + 56));
                goto LABEL_419;
              }
              goto LABEL_304;
            }
          }
        }
        v121 = *v118 & 0x4000;
        if ( !v101 )
        {
          v127 = v215;
          lpCriticalSection = (LPCRITICAL_SECTION)v217;
          v128 = v121 != 0;
          v129 = 0;
          v130 = 0;
          v131 = 0;
          v132 = (LPCCH *)*((_QWORD *)v217 + 5);
          v198 = 0;
          if ( !v132 )
            goto LABEL_329;
          while ( 1 )
          {
            if ( CompareStringA(0x7Fu, 1u, *((PCNZCH *)v127 + 2), -1, v132[2], -1) == 2 )
            {
              v133 = *v132;
              if ( *v132 )
                break;
            }
LABEL_321:
            v132 = (LPCCH *)v132[1];
            if ( !v132 )
            {
              if ( v131 >= 180 )
              {
                if ( v212 )
                  PrepareInternetCallbackCookie(
                    *((LPCCH *)v130 + 4),
                    0,
                    v129[3],
                    v129[4],
                    &v198,
                    *((_DWORD *)v130 + 4),
                    v212);
                if ( !v205 && (v130[16] & 2) == 0 )
                  CCookieHost::UpdateCookieInternal(
                    (CCookieHost *)lpCriticalSection,
                    (struct CCookieLocation *)v129,
                    (struct CCookie *)v130,
                    1);
                CCookieLocation::Purge(v129, CCookie::PurgeThis, v130);
              }
              goto LABEL_329;
            }
          }
          while ( 1 )
          {
            if ( v132 == (LPCCH *)v127 )
            {
              v134 = (const CHAR *)*((_QWORD *)v133 + 4);
              v135 = (const CHAR *)(lpMultiByteStr - v134);
              do
              {
                v136 = (unsigned __int8)v135[(_QWORD)v134];
                v137 = *(unsigned __int8 *)v134 - v136;
                if ( v137 )
                  break;
                ++v134;
              }
              while ( v136 );
              if ( !v137 )
              {
                v138 = *((_DWORD *)v133 + 4);
                if ( ((v138 & 0x4000) != 0) == v128 || (*((_DWORD *)v133 + 4) & 0x4000) == 0 && (v138 & 0x80000) == 0 )
                  break;
              }
            }
            ++v131;
            if ( !v130 || *((_QWORD *)v133 + 1) < *((_QWORD *)v130 + 1) )
            {
              v130 = (CHAR *)v133;
              v129 = v132;
            }
            v133 = (LPCCH)*((_QWORD *)v133 + 3);
            if ( !v133 )
              goto LABEL_321;
          }
LABEL_329:
          v139 = v206;
          v140 = v215;
          v141 = (char *)lpMultiByteStr;
          v142 = *(_QWORD **)v215;
          v143 = *v206 & 0x80000;
          v144 = v143 != 0;
          v145 = 0;
          if ( !*(_QWORD *)v215 )
          {
LABEL_351:
            v150 = CCookie::Construct(lpMultiByteStr, (*v206 & 0x80000) != 0, (*v206 & 0x4000) != 0);
            v142 = v150;
            if ( v150 )
            {
              *((_QWORD *)v150 + 3) = 0;
              *(_QWORD *)v140 = v150;
              goto LABEL_353;
            }
            goto LABEL_302;
          }
          while ( 1 )
          {
            v146 = lpMultiByteStr;
            v147 = v142[4] - (_QWORD)lpMultiByteStr;
            do
            {
              v148 = (unsigned __int8)v146[v147];
              v149 = *(unsigned __int8 *)v146 - v148;
              if ( v149 )
                break;
              ++v146;
            }
            while ( v148 );
            if ( !v149 )
            {
              LODWORD(v147) = *((_DWORD *)v142 + 4);
              v148 = v147 & 0x4000;
              if ( (v148 != 0) == ((*v206 & 0x4000) != 0) )
              {
                if ( !v143 && (v147 & 0x80000) != 0 && (xmmword_180266B60 & 2) != 0 )
                  WPP_SF_sDll(v148, 36, v147, (_DWORD)lpMultiByteStr, v147, v144, (*v206 & 0x4000) != 0);
                if ( !v142 )
                  goto LABEL_302;
LABEL_353:
                if ( (*v139 & 0x300000) != 0 )
                {
                  v151 = v211;
                  v152 = *v139 & 0x100000;
                  TraceLoggingSameSiteSetCookie(v152 != 0, *((const unsigned __int16 **)v217 + 1), v211 == 0);
                  if ( v151 )
                  {
                    v153 = *((_QWORD *)v151 + 709);
                    if ( v153 )
                    {
                      if ( dword_180266100
                        && (qword_180266110 & 0x400000000000LL) != 0
                        && (qword_180266118 & 0x400000000000LL) == qword_180266118 )
                      {
                        v154 = 500;
                        if ( v152 )
                          v154 = 504;
                        _InterlockedIncrement((volatile signed __int32 *)(v154 + v153));
                      }
                    }
                  }
                }
                v156 = v202;
                if ( (*v139 & 0x400) == 0 )
                {
                  v155 = *v139;
                  *v139 = v155 | RestrictPolicyNonEvaluatedCookies(v141, (char *)v202);
                }
                if ( (Microsoft_Windows_WinINetEnableBits & 0x2000) != 0 )
                {
                  v194 = 0;
                  if ( v156 )
                  {
                    v198.dwHighDateTime = 0;
                    v157 = 0xFFFF;
                    v158 = v156;
                    do
                    {
                      if ( !*v158 )
                        break;
                      ++v158;
                      --v157;
                    }
                    while ( v157 );
                    v159 = -2147024809;
                    if ( v157 )
                    {
                      v159 = 0;
                      v194 = -1 - v157;
                    }
                    else
                    {
                      v198.dwHighDateTime = 135;
                      v194 = 0;
                    }
                    WX_WIN32_FROM_HR(v159);
                  }
                  v160 = 0;
                  if ( v141 )
                  {
                    v198.dwHighDateTime = 0;
                    v161 = 0xFFFF;
                    v162 = v141;
                    do
                    {
                      if ( !*v162 )
                        break;
                      ++v162;
                      --v161;
                    }
                    while ( v161 );
                    v163 = -2147024809;
                    if ( v161 )
                    {
                      v163 = 0;
                      v160 = -1 - v161;
                    }
                    else
                    {
                      v198.dwHighDateTime = 135;
                      v160 = 0;
                    }
                    WX_WIN32_FROM_HR(v163);
                  }
                  v164 = 0;
                  v165 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v215 + 4);
                  lpCriticalSection = v165;
                  if ( v165 )
                  {
                    v198.dwHighDateTime = 0;
                    v166 = 0xFFFF;
                    v167 = v165;
                    do
                    {
                      if ( !LOBYTE(v167->DebugInfo) )
                        break;
                      v167 = (struct _RTL_CRITICAL_SECTION *)((char *)v167 + 1);
                      --v166;
                    }
                    while ( v166 );
                    v168 = -2147024809;
                    if ( v166 )
                    {
                      v168 = 0;
                      v164 = -1 - v166;
                    }
                    else
                    {
                      v198.dwHighDateTime = 135;
                      v164 = 0;
                    }
                    WX_WIN32_FROM_HR(v168);
                  }
                  v169 = 0;
                  v170 = (_BYTE *)*((_QWORD *)v215 + 3);
                  if ( v170 )
                  {
                    v198.dwHighDateTime = 0;
                    v171 = 0xFFFF;
                    v172 = v170;
                    do
                    {
                      if ( !*v172 )
                        break;
                      ++v172;
                      --v171;
                    }
                    while ( v171 );
                    v173 = -2147024809;
                    if ( v171 )
                    {
                      v173 = 0;
                      v169 = -1 - v171;
                    }
                    else
                    {
                      v198.dwHighDateTime = 135;
                      v169 = 0;
                    }
                    WX_WIN32_FROM_HR(v173);
                  }
                  v174 = v202;
                  McTemplateU0hsr0hsr2hsr4hsr6_EventWriteTransfer(
                    (unsigned int)&WININET_Context,
                    (unsigned int)&WININET_COOKIE_STORED,
                    v169,
                    (_DWORD)v170,
                    v164,
                    (__int64)lpCriticalSection,
                    v160,
                    (__int64)lpMultiByteStr,
                    v194,
                    (__int64)v202);
                  v141 = (char *)lpMultiByteStr;
                  v139 = v206;
                }
                else
                {
                  v174 = v202;
                }
                v142[1] = SystemTimeAsFileTime;
                if ( v212 && (*v141 || *v174) )
                  PrepareInternetCallbackCookie(
                    v141,
                    v174,
                    *((LPCCH *)v215 + 3),
                    *((const char **)v215 + 4),
                    (struct _FILETIME *)&Buf1,
                    *v139,
                    v212);
                if ( !memcmp_0(&Buf1, v142, 8u)
                  && !strcmp(v174, (const char *)v142[5])
                  && *v139 == *((_DWORD *)v142 + 4) )
                {
                  if ( (xmmword_180266B60 & 2) != 0 )
                    WPP_SF_(1025, 64, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
                  goto LABEL_416;
                }
                v175 = v202;
                v176 = v142[2] & 2;
                *v142 = v18;
                *((_DWORD *)v142 + 4) = *v139;
                CCookie::SetValue((CCookie *)v142, v175);
                v177 = ((v195 & 8 | 4u) >> 2) | 4;
                if ( (v195 & 0x20) == 0 )
                  v177 = (v195 & 8 | 4u) >> 2;
                *((_DWORD *)v142 + 13) = v177;
                if ( (xmmword_180266B60 & 2) != 0 )
                  WPP_SF_sqDD(
                    1025,
                    63,
                    (unsigned int)&WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids,
                    (_DWORD)lpString1,
                    (__int64)v142,
                    v177,
                    *((_DWORD *)v142 + 4));
                if ( v205
                  || v176 && (v142[2] & 2) != 0
                  || CCookieHost::UpdateCookieInternal(v217, v215, (struct CCookie *)v142, 0) >= 0 )
                {
LABEL_416:
                  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v217 + 56));
                  v19 = v191;
                  v20 = 1;
                  goto LABEL_419;
                }
LABEL_302:
                v20 = v192;
LABEL_303:
                v19 = v191;
LABEL_304:
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v217 + 56));
                goto LABEL_419;
              }
              if ( (v147 & 0x4000) == 0 && (v147 & 0x80000) == 0 || !v143 && (*v206 & 0x4000) == 0 )
                v145 = v142;
            }
            v140 = (CCookieLocation *)(v142 + 3);
            v142 = (_QWORD *)v142[3];
            if ( !v142 )
            {
              if ( !v145 )
                goto LABEL_351;
              if ( (xmmword_180266B60 & 2) != 0 )
                WPP_SF_sDll(v148, 37, v147, (_DWORD)lpMultiByteStr, *((_DWORD *)v145 + 4), v144, (*v206 & 0x4000) != 0);
              v142 = v145;
              goto LABEL_353;
            }
          }
        }
        v122 = CCookieLocation::GetCookie(v215, v119, (*v118 >> 19) & 1, v121 != 0, 0);
        v123 = v122;
        if ( !v122 )
        {
          if ( (xmmword_180266B60 & 2) != 0 )
            WPP_SF_(1025, 59, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
          v19 = v191;
          if ( !v193 )
          {
            v20 = 1;
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v217 + 56));
            goto LABEL_419;
          }
          goto LABEL_286;
        }
        v124 = *((_DWORD *)v122 + 4);
        if ( (v124 & 0x200) == 0 || !v204 || v41 || (v124 & 0x800) != 0 )
        {
          if ( !v193 || !v204 || v124 < 0 )
          {
            v126 = v212;
            if ( v212 )
            {
              if ( (v124 & 2) != 0 )
                *v118 |= 2u;
              PrepareInternetCallbackCookie(
                v119,
                0,
                *((LPCCH *)v215 + 3),
                *((const char **)v215 + 4),
                &v198,
                *v118,
                v126);
            }
            if ( (xmmword_180266B60 & 2) != 0 )
              WPP_SF_(1025, 62, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
            if ( !v205 && (*((_BYTE *)v123 + 16) & 2) == 0 && CCookieHost::UpdateCookieInternal(v217, v215, v123, 1) < 0 )
            {
              CCookieLocation::Purge(v215, CCookie::PurgeThis, v123);
              goto LABEL_302;
            }
            CCookieLocation::Purge(v215, CCookie::PurgeThis, v123);
            v20 = 1;
            goto LABEL_303;
          }
          if ( (xmmword_180266B60 & 2) == 0 )
            goto LABEL_285;
          v125 = 61;
        }
        else
        {
          if ( (xmmword_180266B60 & 2) == 0 )
          {
LABEL_285:
            v19 = 5;
LABEL_286:
            v20 = v192;
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v217 + 56));
            goto LABEL_419;
          }
          v125 = 60;
        }
        WPP_SF_(1025, v125, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
        goto LABEL_285;
      }
      v19 = v191;
LABEL_418:
      v20 = v192;
      goto LABEL_419;
    }
    v200 = 0;
    v58 = 0;
    v196 = 0;
    if ( (xmmword_180266B60 & 2) != 0 )
      WPP_SF_sqq(
        1025,
        10,
        (unsigned int)&WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids,
        (_DWORD)Src,
        (__int64)&lpMem,
        (__int64)&v218);
    v59 = Src;
    v60 = (__int64)MultiByteStr;
    lpMem = 0;
    v61 = 2147483646;
    v218 = 0;
    v62 = 257;
    do
    {
      if ( !v61 )
        break;
      if ( !*v59 )
        break;
      *(_BYTE *)v60++ = *v59++;
      --v61;
      --v62;
    }
    while ( v62 );
    v63 = (_BYTE *)(v60 - 1);
    HostInternal = -2147024774;
    if ( v62 )
    {
      v63 = (_BYTE *)v60;
      HostInternal = 0;
    }
    *v63 = 0;
    if ( !v62 )
    {
      v200 = 652;
LABEL_218:
      if ( v58 )
      {
        if ( g_fWxHeapExtensionInitialized )
          g_WxHeapExtensionInterfaces(v58, v60, v61, v59);
        else
          HeapFree(g_hWxProcessHeap, 0, v58);
      }
      if ( (xmmword_180266B60 & 2) != 0 )
        WPP_SF_d(1025, 12, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids, (unsigned int)HostInternal);
      if ( HostInternal >= 0 )
      {
        HostInternal = CCookieJar::GetHostInternal(lpCriticalSection, (const unsigned __int16 *)lpMem, v218, &v217);
        if ( HostInternal < 0 )
          HIDWORD(v196) = 730;
      }
      else
      {
        HIDWORD(v196) = 728;
      }
      goto LABEL_228;
    }
    v64 = -1;
    v65 = 0;
    do
      ++v64;
    while ( MultiByteStr[v64] );
    if ( v64 > 1 )
    {
      v66 = MultiByteStr[0];
      v67 = 0;
      if ( MultiByteStr[0] )
      {
        v68 = MultiByteStr;
        do
        {
          if ( (unsigned __int8)(v66 - 65) <= 0x19u )
            *v68 = v66 + 32;
          v66 = *++v68;
        }
        while ( v66 );
      }
      v69 = &v225[v64 + 19];
      for ( j = MultiByteStr; j < v69; --v69 )
      {
        v71 = *j;
        *j++ = *v69;
        *v69 = v71;
      }
      do
      {
        for ( ; v67 < v64; ++v67 )
        {
          if ( MultiByteStr[v67] != 46 )
            break;
        }
        for ( k = v67; v67 < v64; ++v67 )
        {
          if ( MultiByteStr[v67] == 46 )
            break;
        }
        v73 = &MultiByteStr[v67 - 1];
        for ( m = &MultiByteStr[k]; m < v73; --v73 )
        {
          v75 = *m;
          *m++ = *v73;
          *v73 = v75;
        }
        ++v67;
      }
      while ( v67 < v64 );
    }
    HostInternal = 0;
    LODWORD(v77) = MultiByteToWideChar(0, 0, MultiByteStr, -1, 0, 0);
    v60 = 0xFFFFFFFFLL;
    if ( !(_DWORD)v77 )
    {
      HostInternal = WxGetLastError(v76);
      if ( HostInternal != 1004 )
        goto LABEL_170;
      HostInternal = 0;
      LODWORD(v77) = MultiByteToWideChar(0, 0, MultiByteStr, -1, 0, 0);
      if ( !(_DWORD)v77 )
      {
LABEL_169:
        HostInternal = WxGetLastError(v78);
LABEL_170:
        if ( HostInternal )
        {
          if ( v54 )
            HeapFree(g_hWxProcessHeap, 0, v54);
          if ( HostInternal > 0 )
            goto LABEL_179;
        }
        else if ( v54 )
        {
          v65 = v54;
        }
LABEL_180:
        if ( HostInternal < 0 )
        {
          v200 = 664;
LABEL_213:
          if ( v65 )
          {
            if ( g_fWxHeapExtensionInitialized )
              g_WxHeapExtensionInterfaces(v65);
            else
              HeapFree(g_hWxProcessHeap, 0, v65);
          }
          v41 = v190;
          LODWORD(v15) = (_DWORD)v207;
          goto LABEL_218;
        }
        v83 = ConvertCacheIdnToAscii(v65, (unsigned int)v77, 1, &v196);
        v58 = v196;
        HostInternal = v83;
        if ( v83 < 0 )
        {
          v200 = 668;
          goto LABEL_213;
        }
        HIDWORD(v196) = 0;
        v199 = 0;
        if ( !v58 )
        {
          HIDWORD(v196) = 77;
          HostInternal = -2147024809;
          v200 = 670;
          goto LABEL_213;
        }
        v84 = v58;
        v85 = 0x7FFFFFFF;
        do
        {
          if ( !*v84 )
            break;
          ++v84;
          --v85;
        }
        while ( v85 );
        HostInternal = -2147024809;
        if ( v85 )
          HostInternal = 0;
        v86 = 0x7FFFFFFF - v85;
        if ( !v85 )
        {
          HIDWORD(v196) = 81;
          v200 = 670;
          goto LABEL_213;
        }
        LabelEntry::LabelEntry((LabelEntry *)&v220);
        LabelEntry::LabelEntry((LabelEntry *)v222);
        LabelEntry::LabelEntry((LabelEntry *)&v223);
        LabelEntry::LabelEntry((LabelEntry *)&v225[4]);
        v199 = 0;
        v88 = 4;
        v89 = 0;
        v90 = v86;
        v91 = v86;
        v92 = v86;
        if ( !v86 )
          goto LABEL_202;
        do
        {
          v87 = v90 - 1;
          if ( !v90 || v58[v87] == 46 )
          {
            if ( v89 < 4 )
            {
              v93 = 2LL * v89;
              (&v220)[v93] = (char *)&v58[v90];
              LODWORD(v222[v93 - 1]) = v91 - v90;
              if ( v90 )
                v91 = v90 - 1;
            }
            ++v89;
          }
        }
        while ( v90-- );
        if ( v89 < 4 )
LABEL_202:
          v88 = v89;
        DetermineNumberOfLabelsInDomain(&v220, v88, v87, &v199);
        if ( v199 )
        {
          v60 = (__int64)(&v220)[2 * (unsigned int)(v199 - 1)];
          v95 = (v60 - (__int64)v58) >> 1;
          if ( v95 > 0xFFFFFFFF )
          {
            HostInternal = -2147024362;
            v200 = 676;
            goto LABEL_213;
          }
          v96 = v86 - v95;
          HostInternal = 0;
          if ( v60 )
          {
LABEL_210:
            FormatReverseDomainW(v58, v92);
            v58[v96] = 0;
            if ( (xmmword_180266B60 & 2) != 0 )
              WPP_SF_Sd(1025, 11, (unsigned int)&WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids, (_DWORD)v58, v96);
            lpMem = v58;
            v58 = 0;
            v218 = v96;
            goto LABEL_213;
          }
        }
        else
        {
          HostInternal = 0;
        }
        v96 = v92;
        goto LABEL_210;
      }
      v60 = 0xFFFFFFFFLL;
    }
    v79 = (unsigned int)v77;
    v77 = (unsigned int)(v77 - 1);
    v80 = 2 * v79;
    if ( v80 > 0xFFFFFFFF )
    {
      LOWORD(HostInternal) = 534;
      goto LABEL_179;
    }
    v81 = v80;
    lpWideCharStr = (WCHAR *)HeapAlloc(g_hWxProcessHeap, 0, (unsigned int)v80);
    v54 = lpWideCharStr;
    if ( !lpWideCharStr )
    {
      LOWORD(HostInternal) = 8;
LABEL_179:
      HostInternal = (unsigned __int16)HostInternal | 0x80070000;
      goto LABEL_180;
    }
    if ( MultiByteToWideChar(0, 0, MultiByteStr, -1, lpWideCharStr, v81 >> 1) )
    {
      v65 = v54;
      v54[v77] = 0;
      goto LABEL_180;
    }
    goto LABEL_169;
  }
  if ( !(unsigned __int8)IsMessageBoxWPresent() )
  {
    if ( (xmmword_180266B50 & 2) != 0 )
      WPP_SF_(513, 53, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
    v19 = 5;
    goto LABEL_418;
  }
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_(1025, 54, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
  v221 = lpString1;
  *(_OWORD *)v225 = 0;
  v222[1] = lpMultiByteStr;
  v224 = *v44;
  *(_DWORD *)&v225[4] = HIDWORD(Buf1);
  v220 = v15;
  v222[0] = v13;
  v223 = v202;
  *(_DWORD *)v225 = v18;
  *(_QWORD *)&v225[12] = a8;
  v192 = CCookieJar::CheckCookiePolicy(v211, (struct CookieInfo *)&v220, v195);
  v20 = v192;
  if ( v192 == 1 )
  {
    v191 = 1;
    goto LABEL_123;
  }
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_(1025, 55, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids);
  v19 = 5;
LABEL_419:
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_d(1025, 65, &WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids, v20);
  if ( Src )
    HeapFree(g_hWxProcessHeap, 0, Src);
  if ( v213 )
    HeapFree(g_hWxProcessHeap, 0, v213);
  if ( v214 )
    *v214 = v19;
  v178 = v217;
  if ( v217 && _InterlockedExchangeAdd((volatile signed __int32 *)v217, 0xFFFFFFFF) == 1 && v178 )
  {
    v179 = (void **)((char *)v178 + 8);
    if ( v178 != (struct CCookieHost *)-8LL )
    {
      v180 = *v179;
      if ( *v179 )
      {
        v181 = g_fWxHeapExtensionInitialized == 0;
        *v179 = 0;
        if ( v181 )
          HeapFree(g_hWxProcessHeap, 0, v180);
        else
          g_WxHeapExtensionInterfaces(v180);
        *v179 = 0;
      }
    }
    v182 = (void **)*((_QWORD *)v178 + 5);
    *((_DWORD *)v178 + 4) = 0;
    *((_QWORD *)v178 + 3) = 0;
    *((_QWORD *)v178 + 5) = 0;
    while ( v182 )
    {
      v183 = v182;
      v182 = (void **)v182[1];
      CCookieLocation::Purge(v183, CCookie::PurgeAll, 0);
      v184 = v183 + 6;
      if ( v183 != (void **)-48LL )
      {
        v185 = *v184;
        if ( *v184 )
        {
          v181 = g_fWxHeapExtensionInitialized == 0;
          *v184 = 0;
          if ( v181 )
            HeapFree(g_hWxProcessHeap, 0, v185);
          else
            g_WxHeapExtensionInterfaces(v185);
          *v184 = 0;
        }
      }
      v186 = v183 + 7;
      if ( v183 != (void **)-56LL )
      {
        v187 = *v186;
        if ( *v186 )
        {
          v181 = g_fWxHeapExtensionInitialized == 0;
          *v186 = 0;
          if ( v181 )
            HeapFree(g_hWxProcessHeap, 0, v187);
          else
            g_WxHeapExtensionInterfaces(v187);
          *v186 = 0;
        }
      }
      HeapFree(g_hWxProcessHeap, 0, v183);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v178 + 56));
    v188 = *((_QWORD *)v178 + 6);
    if ( v188 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v188, 0xFFFFFFFF) == 1 )
      {
        DeleteCriticalSection((LPCRITICAL_SECTION)(v188 + 9224));
        operator delete((void *)v188, 0x2430u);
      }
      *((_QWORD *)v178 + 6) = 0;
    }
    operator delete(v178, 0x60u);
  }
  return v20;
}

```

## disassembly

```asm
0x18006a6b0  push    rbp
0x18006a6b2  push    rbx
0x18006a6b3  push    rsi
0x18006a6b4  push    rdi
0x18006a6b5  push    r12
0x18006a6b7  push    r13
0x18006a6b9  push    r14
0x18006a6bb  push    r15
0x18006a6bd  lea     rbp, [rsp-298h]
0x18006a6c5  sub     rsp, 398h
0x18006a6cc  mov     rax, cs:__security_cookie
0x18006a6d3  xor     rax, rsp
0x18006a6d6  mov     [rbp+2D0h+var_50], rax
0x18006a6dd  mov     r14, [rbp+2D0h+arg_28]
0x18006a6e4  mov     r15, r8
0x18006a6e7  mov     r12, [rbp+2D0h+arg_30]
0x18006a6ee  mov     r13, rdx
0x18006a6f1  mov     rax, [rbp+2D0h+arg_60]
0x18006a6f8  mov     rsi, [rbp+2D0h+arg_38]
0x18006a6ff  mov     [rbp+2D0h+lpMultiByteStr], r8
0x18006a703  xor     r8d, r8d
0x18006a706  mov     [rbp+2D0h+var_310], rdx
0x18006a70a  mov     rdx, [rbp+2D0h+arg_20]
0x18006a711  mov     [rbp+2D0h+var_2F0], rcx
0x18006a715  mov     rcx, [rbp+2D0h+arg_48]
0x18006a71c  mov     [rbp+2D0h+lpString1], rdx
0x18006a720  mov     [rbp+2D0h+var_2D8], rcx
0x18006a724  mov     [rbp+2D0h+var_2D0], r8
0x18006a728  mov     [rsp+3D0h+var_368], r8d
0x18006a72d  mov     qword ptr [rbp+2D0h+SystemTimeAsFileTime.dwLowDateTime], r8
0x18006a731  mov     qword ptr [rbp+2D0h+var_348.dwLowDateTime], r8
0x18006a735  mov     [rsp+3D0h+var_36C], r8d
0x18006a73a  mov     [rbp+2D0h+Src], r8
0x18006a73e  mov     [rbp+2D0h+var_2E0], r8
0x18006a742  mov     [rsp+3D0h+var_360], r8d
0x18006a747  mov     [rbp+2D0h+var_2C0], r8
0x18006a74b  mov     [rbp+2D0h+var_330], r9
0x18006a74f  mov     [rbp+2D0h+var_2F8], r14
0x18006a753  mov     [rbp+2D0h+var_318], r12
0x18006a757  mov     [rbp+2D0h+var_2E8], rax
0x18006a75b  test    byte ptr cs:xmmword_180266B60, 2
0x18006a762  mov     edi, [rbp+2D0h+arg_58]
0x18006a768  mov     rbx, [rbp+2D0h+Buf1]
0x18006a76f  jz      short loc_18006A7C4
0x18006a771  mov     [rsp+3D0h+var_378], edi
0x18006a775  mov     rax, 0FFFFFFFF00000000h
0x18006a77f  mov     rcx, rbx
0x18006a782  and     rcx, rax
0x18006a785  mov     eax, ebx
0x18006a787  or      rcx, rax
0x18006a78a  mov     eax, [rbp+2D0h+arg_50]
0x18006a790  mov     [rsp+3D0h+var_380], eax
0x18006a794  mov     eax, [r12]
0x18006a798  mov     [rsp+3D0h+var_388], rcx
0x18006a79d  mov     [rsp+3D0h+var_390], eax
0x18006a7a1  mov     [rsp+3D0h+var_398], r14
0x18006a7a6  mov     [rsp+3D0h+var_3A0], rdx
0x18006a7ab  mov     qword ptr [rsp+3D0h+cchWideChar], r9
0x18006a7b0  mov     r9, r13
0x18006a7b3  mov     [rsp+3D0h+lpWideCharStr], r15
0x18006a7b8  call    WPP_SF_sssssDill
0x18006a7bd  mov     rcx, [rbp+2D0h+var_2D8]
0x18006a7c1  xor     r8d, r8d
0x18006a7c4  test    rcx, rcx
0x18006a7c7  jz      short loc_18006A7CC
0x18006a7c9  mov     [rcx], r8d
0x18006a7cc  lea     r9, [rsp+3D0h+var_360]
0x18006a7d1  mov     dword ptr [rsp+3D0h+lpWideCharStr], 1; int
0x18006a7d9  lea     r8, [rbp+2D0h+var_2E0]
0x18006a7dd  mov     rcx, r13; Src
0x18006a7e0  lea     rdx, [rbp+2D0h+Src]
0x18006a7e4  call    PathAndRDomainFromURL
0x18006a7e9  test    eax, eax
0x18006a7eb  jnz     short loc_18006A818
0x18006a7ed  test    byte ptr cs:xmmword_180266B50, 2
0x18006a7f4  jz      short loc_18006A80C
0x18006a7f6  mov     edx, 30h ; '0'
0x18006a7fb  lea     r8, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids
0x18006a802  mov     ecx, 201h
0x18006a807  call    WPP_SF_
0x18006a80c  mov     esi, [rsp+3D0h+var_36C]
0x18006a810  mov     r12d, esi
0x18006a813  jmp     loc_18006BEB7
0x18006a818  mov     eax, cs:GlobalSuppressCookiePersist
0x18006a81e  mov     [rbp+2D0h+var_31C], eax
0x18006a821  test    eax, eax
0x18006a823  jz      short loc_18006A82A
0x18006a825  or      dword ptr [r12], 2
0x18006a82a  mov     r8, [rbp+2D0h+lpString1]
0x18006a82e  test    r8, r8
0x18006a831  jz      short loc_18006A847
0x18006a833  mov     rdx, [rbp+2D0h+Src]; Src
0x18006a837  mov     rcx, r8; lpString1
0x18006a83a  call    IsDomainLegal
0x18006a83f  test    eax, eax
0x18006a841  jz      short loc_18006A858
0x18006a843  mov     r8, [rbp+2D0h+lpString1]
0x18006a847  test    r14, r14
0x18006a84a  jz      short loc_18006A88E
0x18006a84c  movzx   eax, byte ptr [r14]
0x18006a850  test    al, al
0x18006a852  jz      short loc_18006A88E
0x18006a854  cmp     al, 2Fh ; '/'
0x18006a856  jz      short loc_18006A88E
0x18006a858  test    byte ptr cs:xmmword_180266B50, 2
0x18006a85f  jz      short loc_18006A877
0x18006a861  mov     edx, 31h ; '1'
0x18006a866  lea     r8, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids
0x18006a86d  mov     ecx, 201h
0x18006a872  call    WPP_SF_
0x18006a877  mov     ecx, 57h ; 'W'; dwErrCode
0x18006a87c  call    cs:__imp_SetLastError
0x18006a882  mov     esi, [rsp+3D0h+var_36C]
0x18006a886  mov     r12d, esi
0x18006a889  jmp     loc_18006BEB7
0x18006a88e  test    r15, r15
0x18006a891  jz      short loc_18006A8B3
0x18006a893  movzx   ecx, byte ptr [r15]
0x18006a897  test    cl, cl
0x18006a899  jz      short loc_18006A8B3
0x18006a89b  mov     rax, r15
0x18006a89e  xchg    ax, ax
0x18006a8a0  cmp     cl, 1Fh
0x18006a8a3  ja      short loc_18006A8A8
0x18006a8a5  mov     byte ptr [rax], 5Fh ; '_'
0x18006a8a8  movzx   ecx, byte ptr [rax+1]
0x18006a8ac  inc     rax
0x18006a8af  test    cl, cl
0x18006a8b1  jnz     short loc_18006A8A0
0x18006a8b3  mov     rax, [rbp+2D0h+var_330]
0x18006a8b7  test    rax, rax
0x18006a8ba  jz      short loc_18006A8D6
0x18006a8bc  movzx   ecx, byte ptr [rax]
0x18006a8bf  test    cl, cl
0x18006a8c1  jz      short loc_18006A8D6
0x18006a8c3  cmp     cl, 1Fh
0x18006a8c6  ja      short loc_18006A8CB
0x18006a8c8  mov     byte ptr [rax], 5Fh ; '_'
0x18006a8cb  movzx   ecx, byte ptr [rax+1]
0x18006a8cf  inc     rax
0x18006a8d2  test    cl, cl
0x18006a8d4  jnz     short loc_18006A8C3
0x18006a8d6  test    r14, r14
0x18006a8d9  jz      short loc_18006A8F9
0x18006a8db  movzx   ecx, byte ptr [r14]
0x18006a8df  test    cl, cl
0x18006a8e1  jz      short loc_18006A8F9
0x18006a8e3  mov     rax, r14
0x18006a8e6  cmp     cl, 1Fh
0x18006a8e9  ja      short loc_18006A8EE
0x18006a8eb  mov     byte ptr [rax], 5Fh ; '_'
0x18006a8ee  movzx   ecx, byte ptr [rax+1]
0x18006a8f2  inc     rax
0x18006a8f5  test    cl, cl
0x18006a8f7  jnz     short loc_18006A8E6
0x18006a8f9  test    r8, r8
0x18006a8fc  jz      short loc_18006A929
0x18006a8fe  movzx   ecx, byte ptr [r8]
0x18006a902  test    cl, cl
0x18006a904  jz      short loc_18006A923
0x18006a906  mov     rax, r8
0x18006a909  nop     dword ptr [rax+00000000h]
0x18006a910  cmp     cl, 1Fh
0x18006a913  ja      short loc_18006A918
0x18006a915  mov     byte ptr [rax], 5Fh ; '_'
0x18006a918  movzx   ecx, byte ptr [rax+1]
0x18006a91c  inc     rax
0x18006a91f  test    cl, cl
0x18006a921  jnz     short loc_18006A910
0x18006a923  mov     eax, [r12]
0x18006a927  jmp     short loc_18006A941
0x18006a929  mov     eax, [r12]
0x18006a92d  test    edi, edi
0x18006a92f  jz      short loc_18006A939
0x18006a931  bts     eax, 0Eh
0x18006a935  mov     [r12], eax
0x18006a939  mov     rcx, [rbp+2D0h+Src]
0x18006a93d  mov     [rbp+2D0h+lpString1], rcx
0x18006a941  test    edi, edi
0x18006a943  jz      short loc_18006A94D
0x18006a945  bts     eax, 13h
0x18006a949  mov     [r12], eax
0x18006a94d  test    r14, r14
0x18006a950  jnz     short loc_18006A95F
0x18006a952  mov     r14, [rbp+2D0h+var_2E0]
0x18006a956  mov     [rbp+2D0h+var_2F8], r14
0x18006a95a  test    r14, r14
0x18006a95d  jz      short loc_18006A988
0x18006a95f  movzx   eax, byte ptr [r14]
0x18006a963  test    al, al
0x18006a965  jz      short loc_18006A988
0x18006a967  mov     rcx, r14
0x18006a96a  nop     word ptr [rax+rax+00h]
0x18006a970  cmp     al, 3Fh ; '?'
0x18006a972  jz      short loc_18006A985
0x18006a974  cmp     al, 23h ; '#'
0x18006a976  jz      short loc_18006A985
0x18006a978  movzx   eax, byte ptr [rcx+1]
0x18006a97c  inc     rcx
0x18006a97f  test    al, al
0x18006a981  jnz     short loc_18006A970
0x18006a983  jmp     short loc_18006A988
0x18006a985  mov     byte ptr [rcx], 0
0x18006a988  lea     rcx, [rbp+2D0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006a98c  call    cs:__imp_GetSystemTimeAsFileTime
0x18006a992  mov     rax, qword ptr [rbp+2D0h+SystemTimeAsFileTime.dwLowDateTime]
0x18006a996  cmp     rax, rbx
0x18006a999  jle     short loc_18006A9A2
0x18006a99b  mov     edi, 1
0x18006a9a0  jmp     short loc_18006A9AA
0x18006a9a2  sub     rax, rbx
0x18006a9a5  neg     rax
0x18006a9a8  sbb     edi, edi
0x18006a9aa  mov     rax, [rbp+2D0h+var_2F0]
0x18006a9ae  xor     r8d, r8d
0x18006a9b1  test    edi, edi
0x18006a9b3  setnle  r8b
0x18006a9b7  mov     [rbp+2D0h+var_350], r8d
0x18006a9bb  test    rax, rax
0x18006a9be  jz      short loc_18006A9C9
0x18006a9c0  cmp     dword ptr [rax+14E0h], 0
0x18006a9c7  jnz     short loc_18006A9DF
0x18006a9c9  mov     eax, [r12]
0x18006a9cd  test    al, 10h
0x18006a9cf  jnz     short loc_18006A9DF
0x18006a9d1  mov     [rbp+2D0h+var_320], 0
0x18006a9d8  mov     ecx, 1
0x18006a9dd  jmp     short loc_18006AA1A
0x18006a9df  mov     [rbp+2D0h+var_320], 1
0x18006a9e6  test    byte ptr cs:xmmword_180266B60, 2
0x18006a9ed  jz      short loc_18006AA09
0x18006a9ef  mov     edx, 32h ; '2'
0x18006a9f4  lea     r8, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids
0x18006a9fb  mov     ecx, 401h
0x18006aa00  call    WPP_SF_
0x18006aa05  mov     r8d, [rbp+2D0h+var_350]
0x18006aa09  or      dword ptr [r12], 80000000h
0x18006aa11  mov     ecx, 21h ; '!'
0x18006aa16  mov     eax, [r12]
0x18006aa1a  and     eax, 2
0x18006aa1d  mov     edx, 8
0x18006aa22  mov     r9d, 10h
0x18006aa28  cmovz   edx, r9d
0x18006aa2c  xor     r12d, r12d
0x18006aa2f  or      edx, ecx
0x18006aa31  mov     [rsp+3D0h+var_364], r12d
0x18006aa36  mov     [rsp+3D0h+var_360], edx
0x18006aa3a  test    edi, edi
0x18006aa3c  jg      short loc_18006AA54
0x18006aa3e  test    rsi, rsi
0x18006aa41  jz      short loc_18006AA54
0x18006aa43  test    eax, eax
0x18006aa45  jz      short loc_18006AA4D
0x18006aa47  test    byte ptr [rsi+0Ch], 4
0x18006aa4b  jz      short loc_18006AA54
0x18006aa4d  mov     eax, 1
0x18006aa52  jmp     short loc_18006AA5F
0x18006aa54  xor     eax, eax
0x18006aa56  test    rsi, rsi
0x18006aa59  jz      loc_18006AAEA
0x18006aa5f  cmp     [rsi+10h], r12d
0x18006aa63  jnz     loc_18006AAEA
0x18006aa69  mov     r15d, 1
0x18006aa6f  mov     [rsp+3D0h+var_370], r15d
0x18006aa74  test    eax, eax
0x18006aa76  jz      loc_18006AB36
0x18006aa7c  test    r15d, r15d
0x18006aa7f  jnz     loc_18006AB36
0x18006aa85  xor     eax, eax
0x18006aa87  test    rsi, rsi
0x18006aa8a  jz      short loc_18006AAA4
0x18006aa8c  cmp     dword ptr [rsi+8], 3
0x18006aa90  mov     edx, 200h
0x18006aa95  cmovnz  edx, eax
0x18006aa98  mov     eax, edx
0x18006aa9a  or      eax, 2
0x18006aa9d  cmp     dword ptr [rsi+8], 4
0x18006aaa1  cmovnz  eax, edx
0x18006aaa4  mov     rdi, [rbp+2D0h+var_318]
0x18006aaa8  or      [rdi], eax
0x18006aaaa  mov     eax, [rsi+8]
0x18006aaad  mov     [rsp+3D0h+var_36C], eax
0x18006aab1  cmp     eax, 5
0x18006aab4  jnz     short loc_18006AB30
0x18006aab6  test    byte ptr cs:xmmword_180266B60, 2
0x18006aabd  jz      short loc_18006AAD9
0x18006aabf  mov     edx, 34h ; '4'
0x18006aac4  lea     r8, WPP_b3279233de863157ecd5f2ca4df94c83_Traceguids
0x18006aacb  mov     ecx, 401h
0x18006aad0  call    WPP_SF_
0x18006aad5  mov     eax, [rsp+3D0h+var_36C]
0x18006aad9  mov     r12d, 1
0x18006aadf  mov     [rsp+3D0h+var_364], r12d
0x18006aae4  mov     [rbp+2D0h+var_350], r12d
0x18006aae8  jmp     short loc_18006AB47
0x18006aaea  xor     r15d, r15d
0x18006aaed  mov     [rsp+3D0h+var_370], r15d
0x18006aaf2  test    rsi, rsi
0x18006aaf5  jz      loc_18006AA74
0x18006aafb  cmp     dword ptr [rsi+10h], 3
  ... truncated ...
```
