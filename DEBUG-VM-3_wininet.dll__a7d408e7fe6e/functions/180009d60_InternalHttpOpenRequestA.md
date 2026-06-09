# InternalHttpOpenRequestA

- ea: `0x180009d60`
- end: `0x18000b8ab`
- name: `InternalHttpOpenRequestA`
- size: `6987`
- prototype: ``
- caller_count: `5`
- callee_count: `44`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800ccce4`
- `0x1800d79c0`
- `0x1800ea2e0`
- `0x18010e820`
- `0x180181514`

## callees

- `0x180009cf0`
- `0x180009d60`
- `0x18000baa0`
- `0x18000bc58`
- `0x18000c694`
- `0x18000c940`
- `0x18000f490`
- `0x1800100d0`
- `0x180011930`
- `0x180012a40`
- `0x180014fec`
- `0x180019d20`
- `0x180025980`
- `0x180029810`
- `0x18002a54c`
- `0x1800353ec`
- `0x180064060`
- `0x1800641c0`
- `0x180064560`
- `0x1800672d0`
- `0x18007ad20`
- `0x18008a970`
- `0x1800c156c`
- `0x1800c60c8`
- `0x1800cc758`
- `0x1800ce264`
- `0x1800e3b34`
- `0x1800f20bc`
- `0x1800fc53c`
- `0x18010f598`
- `0x1801145e8`
- `0x180132b18`
- `0x18013f7b8`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x180154882`
- `0x1801c9c31`
- `0x1801e1790`
- `0x1801e3c24`
- `0x1801e41b0`
- `0x1801e5e10`
- `0x1801e76e4`
- `0x1801e9e9c`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b04a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b7da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ae1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b04a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b7da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a687`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a687`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a917`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a917`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009efc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a6ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000af92`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180009efc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a6ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000af92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009f04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a6d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000af9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009f04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a6d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000af9a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18000b600`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x18000b600`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18000b0cf`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18000b107`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18000b0cf`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18000b107`
- `ntdll!EtwEventActivityIdControl` at `0x180009eba`
- `ntdll!EtwEventActivityIdControl` at `0x180009f3e`
- `ntdll!EtwEventActivityIdControl` at `0x18000a1ea`
- `ntdll!EtwEventActivityIdControl` at `0x18000a231`
- `ntdll!EtwEventActivityIdControl` at `0x18000aa33`
- `ntdll!EtwEventActivityIdControl` at `0x180009eba`
- `ntdll!EtwEventActivityIdControl` at `0x180009f3e`
- `ntdll!EtwEventActivityIdControl` at `0x18000a1ea`
- `ntdll!EtwEventActivityIdControl` at `0x18000a231`
- `ntdll!EtwEventActivityIdControl` at `0x18000aa33`

## pseudocode

```c
unsigned int (*__fastcall InternalHttpOpenRequestA(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        char *a5,
        unsigned int (*a6)(enum INTERNET_SCHEME, char *, char *, char *, char *, unsigned int, char **, unsigned int *),
        unsigned int a7,
        const struct _GUID *a8,
        int a9))(enum INTERNET_SCHEME, char *, char *, char *, char *, unsigned int, char **, unsigned int *)
{
  char *v9; // r14
  __int64 v11; // rcx
  struct _GUID *v12; // rax
  struct _GUID *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  struct _GUID *v16; // rax
  int v17; // eax
  bool v18; // sf
  signed __int32 v19; // esi
  DWORD TickCount; // ebx
  DWORD CurrentProcessId; // eax
  int v22; // eax
  bool v23; // sf
  _QWORD *ThreadInfo; // r14
  DWORD IsValid; // eax
  struct INTERNET_CONNECT_HANDLE_OBJECT *v26; // rbx
  HANDLE_OBJECT *v27; // r12
  unsigned __int8 *v28; // rsi
  __int64 v29; // rcx
  _BYTE *v30; // rax
  unsigned int v31; // edx
  unsigned int v32; // edi
  unsigned __int8 v33; // al
  unsigned __int8 *v34; // rdx
  size_t i; // rbx
  char v36; // al
  const void *v37; // rsi
  __int64 v38; // rcx
  CHAR *Heap; // rax
  CHAR *v40; // rdi
  const CHAR *v41; // rsi
  unsigned int v42; // edi
  unsigned int v43; // eax
  DWORD v44; // r13d
  __int64 v45; // rcx
  struct _GUID *v46; // rax
  const struct _GUID *v47; // rbx
  struct _GUID *v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rcx
  struct _GUID *v51; // rax
  int v52; // eax
  bool v53; // sf
  int v54; // eax
  bool v55; // sf
  const struct _EVENT_DESCRIPTOR *v56; // rdx
  unsigned __int64 v57; // rcx
  unsigned int (*v58)(enum INTERNET_SCHEME, char *, char *, char *, char *, unsigned int, char **, unsigned int *); // r12
  HANDLE_OBJECT *v59; // rsi
  struct INTERNET_CONNECT_HANDLE_OBJECT *v60; // rcx
  char v61; // al
  unsigned __int16 v62; // bx
  __int64 v63; // rcx
  char *v64; // rax
  unsigned int v65; // edx
  unsigned __int16 v66; // si
  int v67; // r14d
  __int64 v68; // rcx
  char *v69; // rax
  unsigned int v70; // edx
  unsigned __int16 v71; // di
  __int64 v72; // rcx
  char *v73; // rax
  unsigned int v74; // edx
  struct _GUID *v75; // rdx
  unsigned __int16 v76; // bx
  __int64 v77; // rcx
  _BYTE *v78; // rax
  unsigned int v79; // edx
  signed __int32 v81; // esi
  DWORD v82; // ebx
  char *v83; // rdi
  __int64 v84; // rcx
  const CHAR *v85; // rax
  __int64 v86; // r9
  __int64 v87; // rdx
  const CHAR *v88; // rax
  __int64 v89; // rcx
  __int64 v90; // rcx
  const CHAR *v91; // rax
  __int64 v92; // r9
  __int64 v93; // rdx
  const CHAR *v94; // rax
  __int64 v95; // rcx
  unsigned int v96; // ebx
  int v97; // eax
  unsigned int v98; // eax
  char *v99; // rcx
  int v100; // eax
  struct INTERNET_CONNECT_HANDLE_OBJECT *v101; // rbx
  HANDLE v102; // rcx
  struct INTERNET_CONNECT_HANDLE_OBJECT *v103; // rdi
  char *v104; // r14
  HTTP_REQUEST_HANDLE_OBJECT *v105; // rax
  HTTP_REQUEST_HANDLE_OBJECT *v106; // rbx
  HTTP_REQUEST_HANDLE_OBJECT *v107; // rax
  HANDLE_OBJECT *v108; // rbx
  int v109; // edi
  __int64 v110; // rcx
  struct _GUID *v111; // rax
  const struct _GUID *p_Buf1; // rbx
  struct _GUID *v113; // rax
  __int64 v114; // rcx
  int v115; // eax
  bool v116; // sf
  struct _RTL_CRITICAL_SECTION *v117; // rdi
  size_t v118; // r13
  unsigned int v119; // eax
  size_t v120; // rbx
  unsigned int v121; // eax
  __int64 v122; // rcx
  size_t v123; // r12
  unsigned __int8 *v124; // r8
  unsigned int v125; // edx
  unsigned __int8 v126; // al
  int v127; // edx
  __int64 v128; // r8
  int v129; // r9d
  int v130; // eax
  signed int AllocationEntry; // esi
  int v132; // esi
  unsigned int v133; // r15d
  __int64 v134; // r9
  __int64 *v135; // rcx
  unsigned int j; // r8d
  unsigned int v137; // eax
  char *v138; // rdx
  int v139; // eax
  char *v140; // rdi
  char *v141; // rbx
  __int64 v142; // rcx
  unsigned int v143; // eax
  __int64 v144; // rdx
  void *v145; // r9
  unsigned __int64 v146; // rsi
  int v147; // r14d
  _BYTE *v148; // rax
  __int64 v149; // rcx
  __int64 v150; // rbx
  __int64 v151; // rdi
  char *v152; // r8
  unsigned int v153; // ecx
  int v154; // eax
  signed __int32 v155; // esi
  DWORD v156; // ebx
  DWORD v157; // eax
  __int64 k; // rbx
  __int64 v159; // rcx
  __int16 *v160; // rbx
  __int64 v161; // rcx
  __int64 v162; // r11
  unsigned __int16 v163; // ax
  unsigned __int16 v164; // r10
  char *v165; // r11
  __int64 v166; // r8
  _BYTE *v167; // rdx
  __int64 v168; // rdx
  _BYTE *v169; // rbx
  __int64 v170; // rdx
  int v171; // ecx
  unsigned int v172; // eax
  PCNZCH lpString2; // [rsp+20h] [rbp-258h]
  const struct _GUID *cchCount2; // [rsp+28h] [rbp-250h]
  unsigned int v175; // [rsp+30h] [rbp-248h]
  char *v176; // [rsp+60h] [rbp-218h]
  char *v177; // [rsp+68h] [rbp-210h]
  char *pszStr1; // [rsp+70h] [rbp-208h]
  HANDLE_OBJECT *v180; // [rsp+80h] [rbp-1F8h]
  struct INTERNET_CONNECT_HANDLE_OBJECT *v181; // [rsp+88h] [rbp-1F0h]
  CHAR *v182; // [rsp+90h] [rbp-1E8h] BYREF
  unsigned int (*v183)(enum INTERNET_SCHEME, char *, char *, char *, char *, unsigned int, char **, unsigned int *); // [rsp+98h] [rbp-1E0h] BYREF
  struct INTERNET_CONNECT_HANDLE_OBJECT *v184; // [rsp+A0h] [rbp-1D8h] BYREF
  unsigned int v185; // [rsp+A8h] [rbp-1D0h] BYREF
  unsigned __int16 v186; // [rsp+B0h] [rbp-1C8h] BYREF
  __int128 v187; // [rsp+B8h] [rbp-1C0h] BYREF
  unsigned int v188; // [rsp+C8h] [rbp-1B0h] BYREF
  void *Src; // [rsp+D0h] [rbp-1A8h] BYREF
  struct _GUID v190; // [rsp+E0h] [rbp-198h] BYREF
  struct _GUID Buf1; // [rsp+F0h] [rbp-188h] BYREF
  unsigned int v192; // [rsp+100h] [rbp-178h] BYREF
  struct _GUID v193; // [rsp+108h] [rbp-170h] BYREF
  int v194; // [rsp+118h] [rbp-160h]
  struct _GUID v195; // [rsp+120h] [rbp-158h] BYREF
  _BYTE v196[16]; // [rsp+130h] [rbp-148h] BYREF
  unsigned int (**v197)(enum INTERNET_SCHEME, char *, char *, char *, char *, unsigned int, char **, unsigned int *); // [rsp+140h] [rbp-138h]
  __int64 v198; // [rsp+148h] [rbp-130h]
  unsigned int *v199; // [rsp+150h] [rbp-128h]
  __int64 v200; // [rsp+158h] [rbp-120h]
  __int16 *v201; // [rsp+160h] [rbp-118h]
  __int64 v202; // [rsp+168h] [rbp-110h]
  struct _GUID *v203; // [rsp+170h] [rbp-108h]
  __int64 v204; // [rsp+178h] [rbp-100h]
  unsigned int *v205; // [rsp+180h] [rbp-F8h]
  __int64 v206; // [rsp+188h] [rbp-F0h]
  char *v207; // [rsp+190h] [rbp-E8h]
  int v208; // [rsp+198h] [rbp-E0h]
  int v209; // [rsp+19Ch] [rbp-DCh]
  unsigned int *v210; // [rsp+1A0h] [rbp-D8h]
  __int64 v211; // [rsp+1A8h] [rbp-D0h]
  char *v212; // [rsp+1B0h] [rbp-C8h]
  int v213; // [rsp+1B8h] [rbp-C0h]
  int v214; // [rsp+1BCh] [rbp-BCh]
  void **p_Src; // [rsp+1C0h] [rbp-B8h]
  __int64 v216; // [rsp+1C8h] [rbp-B0h]
  char *v217; // [rsp+1D0h] [rbp-A8h]
  int v218; // [rsp+1D8h] [rbp-A0h]
  int v219; // [rsp+1DCh] [rbp-9Ch]
  unsigned int *v220; // [rsp+1E0h] [rbp-98h]
  __int64 v221; // [rsp+1E8h] [rbp-90h]
  __int64 v222; // [rsp+1F0h] [rbp-88h]
  __int64 v223; // [rsp+1F8h] [rbp-80h]
  struct _GUID *v224; // [rsp+200h] [rbp-78h]
  __int64 v225; // [rsp+208h] [rbp-70h]
  char v226[32]; // [rsp+210h] [rbp-68h] BYREF
  _UNKNOWN *retaddr; // [rsp+278h] [rbp+0h]

  v9 = a5;
  Src = a2;
  pszStr1 = (char *)a4;
  v177 = (char *)a3;
  v194 = 0;
  v176 = a5;
  v183 = a6;
  v184 = 0;
  v181 = 0;
  v180 = 0;
  v193 = 0;
  v182 = 0;
  if ( (xmmword_180266B60 & 4) != 0 )
    WPP_SF_qssssqDP(a1, 0, a3, a1, (__int64)a2, a3, a4, (__int64)a5, (__int64)a6, a7, (char)a8);
  if ( !GlobalDataInitialized )
  {
    v44 = 12172;
    goto LABEL_246;
  }
  v11 = 16;
  v12 = &v193;
  do
  {
    LOBYTE(v12->Data1) = 0;
    v12 = (struct _GUID *)((char *)v12 + 1);
    --v11;
  }
  while ( v11 );
  v194 = 0;
  v13 = &v193;
  Buf1 = 0;
  v14 = 16;
  v190 = 0;
  do
  {
    LOBYTE(v13->Data1) = 0;
    v13 = (struct _GUID *)((char *)v13 + 1);
    --v14;
  }
  while ( v14 );
  DWORD1(v187) = 0;
  v195 = 0;
  v15 = 16;
  v16 = &v190;
  do
  {
    LOBYTE(v16->Data1) = 0;
    v16 = (struct _GUID *)((char *)v16 + 1);
    --v15;
  }
  while ( v15 );
  v17 = EtwEventActivityIdControl(1, &v195);
  v18 = v17 < 0;
  if ( v17 > 0 )
    v18 = 1;
  if ( v18 )
    DWORD1(v187) = 128;
  else
    v190 = v195;
  v19 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
  TickCount = GetTickCount();
  CurrentProcessId = GetCurrentProcessId();
  Buf1.Data1 = (unsigned int)retaddr;
  *(_DWORD *)&Buf1.Data4[4] = CurrentProcessId;
  *(_DWORD *)&Buf1.Data2 = v19;
  *(_DWORD *)Buf1.Data4 = TickCount;
  DWORD1(v187) = 0;
  v22 = EtwEventActivityIdControl(2, &Buf1);
  v23 = v22 < 0;
  if ( v22 > 0 )
    v23 = 1;
  if ( v23 )
    DWORD1(v187) = 144;
  WxEtwTransferActivityId(&Buf1, &v190);
  v193 = v190;
  v194 = 1;
  ThreadInfo = (_QWORD *)InternetGetThreadInfo();
  if ( !ThreadInfo )
  {
    v44 = 12004;
    goto LABEL_245;
  }
  IsValid = MapHandleToAddress(a1, &v184, 0);
  if ( IsValid || (v26 = v184, (IsValid = HANDLE_OBJECT::IsValid(v184, 1852785480)) != 0) )
  {
    v44 = IsValid;
    goto LABEL_245;
  }
  v27 = 0;
  (*(void (__fastcall **)(struct INTERNET_CONNECT_HANDLE_OBJECT *))(*(_QWORD *)v26 + 16LL))(v26);
  v181 = v184;
  if ( *((_DWORD *)v184 + 248) )
  {
    if ( Src || (v83 = v177) != 0 || pszStr1 || a5 || a6 || a7 )
    {
      v9 = a5;
      v44 = 87;
      v58 = 0;
      goto LABEL_66;
    }
    a7 = -2080374784;
    goto LABEL_107;
  }
  v28 = (unsigned __int8 *)Src;
  if ( !Src || !*(_BYTE *)Src )
  {
    v83 = v177;
LABEL_107:
    v41 = "GET";
    Src = (void *)"GET";
    goto LABEL_129;
  }
  v29 = 0x7FFFFFFF;
  *(_DWORD *)&v190.Data2 = 0;
  v30 = Src;
  DWORD1(v187) = 0;
  v185 = 0;
  do
  {
    if ( !*v30 )
      break;
    ++v30;
    --v29;
  }
  while ( v29 );
  v31 = -2147024809;
  if ( v29 )
  {
    v31 = 0;
    v32 = 0x7FFFFFFF - v29;
  }
  else
  {
    DWORD1(v187) = 54;
    v32 = 0;
  }
  WX_WIN32_FROM_HR(v31);
  if ( !v32 )
  {
    *(_DWORD *)&v190.Data2 = 135;
    v42 = -2147024809;
    goto LABEL_42;
  }
  v33 = *v28;
  v34 = v28;
  for ( i = 0; v33; v33 = *++v34 )
  {
    if ( v33 != 32 && v33 != 9 )
      break;
  }
  v36 = *v34;
  v37 = v34;
  if ( !*v34 )
    goto LABEL_40;
  do
  {
    if ( (unsigned __int8)(v36 - 33) > 0x5Du )
      break;
    v36 = *++v34;
    i = (unsigned int)(i + 1);
  }
  while ( v36 );
  if ( !(_DWORD)i )
  {
LABEL_40:
    *(_DWORD *)&v190.Data2 = 174;
LABEL_41:
    v42 = -2147024809;
LABEL_42:
    v43 = WX_WIN32_FROM_HR(v42);
    goto LABEL_43;
  }
  v38 = *v34;
  if ( (_BYTE)v38 )
  {
    while ( (unsigned int)IsLWS(v38) )
    {
      v38 = (unsigned __int8)v167[1];
      if ( !(_BYTE)v38 )
        goto LABEL_37;
    }
    if ( *v167 )
    {
      *(_DWORD *)&v190.Data2 = 190;
      goto LABEL_41;
    }
  }
LABEL_37:
  if ( (unsigned int)i >= v32 )
  {
    v41 = (const CHAR *)Src;
  }
  else
  {
    DWORD1(v187) = 0;
    Heap = (CHAR *)WxAllocateHeapEx(v38, (unsigned int)(i + 1));
    v40 = Heap;
    if ( !Heap )
    {
      DWORD1(v187) = 52;
      v42 = -2147024882;
      *(_DWORD *)&v190.Data2 = 209;
      goto LABEL_42;
    }
    memcpy_0(Heap, v37, i);
    v40[i] = 0;
    v41 = v40;
    v182 = v40;
    Src = v40;
  }
  if ( !GlobalEnableHttpTrace )
  {
    if ( !v41 )
      goto LABEL_281;
    v84 = 5;
    v85 = v41;
    do
    {
      if ( !*v85 )
        break;
      ++v85;
      --v84;
    }
    while ( v84 );
    v86 = 5 - v84;
    if ( !v84 )
LABEL_281:
      v86 = 5;
    v87 = 5;
    v88 = "TRACE";
    do
    {
      if ( !*v88 )
        break;
      ++v88;
      --v87;
    }
    while ( v87 );
    v89 = 5 - v87;
    if ( !v87 )
      v89 = 5;
    if ( v86 == v89 && CompareStringA(0x7Fu, 1u, v41, v86, "TRACE", v89) == 2 )
      goto LABEL_244;
    if ( !v41 )
      goto LABEL_284;
    v90 = 5;
    v91 = v41;
    do
    {
      if ( !*v91 )
        break;
      ++v91;
      --v90;
    }
    while ( v90 );
    v92 = 5 - v90;
    if ( !v90 )
LABEL_284:
      v92 = 5;
    v93 = 5;
    v94 = "TRACK";
    do
    {
      if ( !*v94 )
        break;
      ++v94;
      --v93;
    }
    while ( v93 );
    v95 = 5 - v93;
    if ( !v93 )
      v95 = 5;
    if ( v92 == v95 && CompareStringA(0x7Fu, 1u, v41, v92, "TRACK", v95) == 2 )
    {
LABEL_244:
      v44 = 12016;
      goto LABEL_245;
    }
  }
  v83 = v177;
LABEL_129:
  if ( !v83 || !*v83 )
    v177 = "/";
  v96 = 0;
  v185 = 0;
  v188 = 0;
  if ( pszStr1 && *pszStr1 )
  {
    if ( StrCmpNICA(pszStr1, "HTTP/", 5) )
    {
      v98 = 1;
    }
    else
    {
      *(_QWORD *)&v190.Data1 = pszStr1 + 5;
      if ( !(unsigned int)ExtractDword(&v190, v168, &v185) )
      {
        v44 = 534;
        goto LABEL_245;
      }
      v169 = *(_BYTE **)&v190.Data1;
      if ( !(unsigned int)SafeIsDigit(**(char **)&v190.Data1) )
      {
        do
        {
          if ( !*v169 )
            break;
          v171 = (char)*++v169;
        }
        while ( !(unsigned int)SafeIsDigit(v171) );
        *(_QWORD *)&v190.Data1 = v169;
      }
      if ( !(unsigned int)ExtractDword(&v190, v170, &v188) )
      {
        v44 = 534;
        goto LABEL_245;
      }
      v98 = v185;
      v96 = v188;
    }
LABEL_134:
    if ( !GlobalEnableHttp1_1 )
      goto LABEL_135;
    if ( v98 == 1 )
    {
      if ( v96 )
        goto LABEL_135;
    }
    else if ( v98 )
    {
LABEL_135:
      v99 = a5;
      if ( a5 )
      {
        if ( !*a5 )
          v99 = 0;
        v176 = v99;
      }
      v100 = *((_DWORD *)v181 + 234);
      if ( (!v100 || v100 == 3)
        && !*((_DWORD *)v181 + 248)
        && (unsigned int)IsInappropriateHTTPPort(*((unsigned __int16 *)v181 + 466)) )
      {
        v44 = 12005;
LABEL_245:
        v9 = v176;
LABEL_246:
        v58 = 0;
        goto LABEL_66;
      }
      v101 = v184;
      if ( (xmmword_180266B60 & 2) != 0 )
        WPP_SF_qqqqq(
          1025,
          43,
          (unsigned int)&WPP_269ea9d0988239ed4fc21e863914335a_Traceguids,
          (_DWORD)ThreadInfo,
          ThreadInfo[6],
          a1,
          ThreadInfo[7],
          (__int64)v184);
      ThreadInfo[6] = a1;
      ThreadInfo[7] = v101;
      if ( (xmmword_180266B60 & 2) != 0 )
      {
        cchCount2 = a8;
        lpString2 = (PCNZCH)ThreadInfo[5];
        WPP_SF_qPP(1025, 42, &WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, ThreadInfo);
      }
      v102 = g_hWxProcessHeap;
      ThreadInfo[5] = a8;
      v103 = v184;
      v104 = 0;
      DWORD1(v187) = 0;
      *(_QWORD *)&v190.Data1 = 0;
      v105 = (HTTP_REQUEST_HANDLE_OBJECT *)HeapAlloc(v102, 0, 0x16D0u);
      v106 = v105;
      if ( v105
        && (memset_0(v105, 0, 0x16D0u),
            v107 = HTTP_REQUEST_HANDLE_OBJECT::HTTP_REQUEST_HANDLE_OBJECT(v106),
            (v108 = v107) != 0) )
      {
        v109 = HTTP_REQUEST_HANDLE_OBJECT::Initialize(v107, v103, a7, (unsigned __int64)a8);
        if ( v109 < 0 )
        {
          DWORD1(v187) = 352;
          HANDLE_OBJECT::Invalidate(v108);
          HANDLE_OBJECT::Dereference(v108);
        }
        else
        {
          v27 = v108;
          *(_QWORD *)&v190.Data1 = v108;
        }
      }
      else
      {
        v109 = -2147024882;
        DWORD1(v187) = 346;
      }
      if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
      {
        v172 = WX_WIN32_FROM_HR((unsigned int)v109);
        WPP_SF_d(1032, 12, &WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids, v172);
      }
      v44 = WX_WIN32_FROM_HR((unsigned int)v109);
      if ( v44 )
        goto LABEL_222;
      v180 = v27;
      EtwEndActivityId(&v193);
      v110 = 16;
      v111 = &v193;
      p_Buf1 = (const struct _GUID *)((char *)v27 + 164);
      do
      {
        LOBYTE(v111->Data1) = 0;
        v111 = (struct _GUID *)((char *)v111 + 1);
        --v110;
      }
      while ( v110 );
      v194 = 0;
      v113 = &v193;
      Buf1 = 0;
      v114 = 16;
      v195 = 0;
      do
      {
        LOBYTE(v113->Data1) = 0;
        v113 = (struct _GUID *)((char *)v113 + 1);
        --v114;
      }
      while ( v114 );
      WxEtwGetActivityId(&v195);
      if ( v27 == (HANDLE_OBJECT *)-164LL )
      {
        v155 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
        v156 = GetTickCount();
        v157 = GetCurrentProcessId();
        *(_DWORD *)&Buf1.Data2 = v155;
        v41 = (const CHAR *)Src;
        *(_DWORD *)Buf1.Data4 = v156;
        p_Buf1 = &Buf1;
        *(_DWORD *)&Buf1.Data4[4] = v157;
        Buf1.Data1 = (unsigned int)retaddr;
      }
      DWORD1(v187) = 0;
      v115 = EtwEventActivityIdControl(2, p_Buf1);
      v116 = v115 < 0;
      if ( v115 > 0 )
        v116 = 1;
      if ( v116 )
        DWORD1(v187) = 144;
      WxEtwTransferActivityId(p_Buf1, &v195);
      v117 = (struct _RTL_CRITICAL_SECTION *)((char *)v27 + 3024);
      v194 = 1;
      *(_QWORD *)&Buf1.Data1 = (char *)v27 + 3024;
      v193 = v195;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v27 + 3024));
      v118 = (unsigned int)inetstrlenDWordA(pszStr1);
      v119 = inetstrlenDWordA(v177);
      v120 = v119;
      v185 = v119;
      v121 = inetstrlenDWordA(v41);
      v122 = 0;
      v188 = 0;
      v192 = 0;
      v123 = v121;
      DWORD1(v187) = 0;
      if ( v41 )
      {
        v124 = (unsigned __int8 *)v41;
        v125 = v121;
        if ( v121 )
        {
          while ( 1 )
          {
            v126 = *v124;
            if ( *v124 != 9 && v126 != 32 )
              break;
            if ( !--v125 )
              goto LABEL_170;
            ++v124;
          }
          if ( !v125 )
          {
LABEL_170:
            v122 = 0;
            goto LABEL_171;
          }
          while ( v126 > 0x20u && v126 < 0x7Fu )
          {
            if ( !--v125 )
              goto LABEL_170;
            v126 = *++v124;
          }
          while ( (unsigned int)IsLWS(*v124) )
          {
            v124 = (unsigned __int8 *)(v128 + 1);
            if ( !(v129 + v127) )
              goto LABEL_170;
          }
          v122 = 2147942487LL;
          DWORD1(v187) = 6479;
        }
      }
LABEL_171:
      v130 = WX_WIN32_FROM_HR(v122);
      AllocationEntry = v130;
      if ( v130 > 0 )
        AllocationEntry = (unsigned __int16)v130 | 0x80070000;
      if ( AllocationEntry < 0 )
      {
        v27 = *(HANDLE_OBJECT **)&v190.Data1;
        DWORD1(v187) = 5361;
      }
      else
      {
        v132 = 0;
        v133 = v118 + v123 + v120 + 2;
        v134 = *(_QWORD *)(*(_QWORD *)&v190.Data1 + 2864LL);
        *(_QWORD *)&v187 = 0;
        if ( v133 <= *(_DWORD *)(v134 + 4) )
        {
          v135 = *(__int64 **)(v134 + 8);
          for ( j = 0; j < 0xA && v135 != (__int64 *)(v134 + 8); ++j )
          {
            v137 = *((_DWORD *)v135 + 4);
            if ( v137 >= v133 )
            {
              v138 = (char *)v135[3];
              *((_DWORD *)v135 + 4) = v137 - v133;
              v135[3] = (__int64)&v138[v133];
              if ( !v138 )
                break;
              v104 = v138;
              *(_QWORD *)&v187 = v138;
              goto LABEL_181;
            }
            v135 = (__int64 *)*v135;
          }
        }
        v132 = 1;
LABEL_181:
        if ( !v132 )
          goto LABEL_184;
        AllocationEntry = WxFastHeapAllocator::CreateAllocationEntry((WxFastHeapAllocator *)v134, v133, (void **)&v187);
        if ( AllocationEntry >= 0 )
        {
          v104 = (char *)v187;
LABEL_184:
          v139 = _ParseHttpVersion(pszStr1, v118, &v188, &v192);
          AllocationEntry = v139;
          if ( v139 > 0 )
            AllocationEntry = (unsigned __int16)v139 | 0x80070000;
          if ( AllocationEntry < 0 )
          {
            v27 = *(HANDLE_OBJECT **)&v190.Data1;
            DWORD1(v187) = 5376;
          }
          else
          {
            memcpy_0(v104, Src, v123);
            v140 = &v104[v123 + 1];
            v104[v123] = 32;
            memcpy_0(v140, v177, v120);
            v140[v120] = 32;
            v141 = &v140[v120 + 1];
            memcpy_0(v141, pszStr1, v118);
            v142 = *(_QWORD *)&v190.Data1;
            *(_DWORD *)(*(_QWORD *)&v190.Data1 + 2872LL) += v133 + 2;
            *(_DWORD *)(v142 + 2904) = v185;
            *(_DWORD *)(v142 + 2956) = v188;
            v143 = v192;
            *(_DWORD *)(v142 + 2888) = v123;
            v27 = (HANDLE_OBJECT *)v142;
            *(_QWORD *)(v142 + 2896) = v140;
            v117 = *(struct _RTL_CRITICAL_SECTION **)&Buf1.Data1;
            *(_DWORD *)(v142 + 2960) = v143;
            *(_QWORD *)(v142 + 2880) = v104;
            *(_QWORD *)(v142 + 2912) = v141;
            *(_DWORD *)(v142 + 2920) = v118;
            *(_QWORD *)(v142 + 2968) = v104;
            *(_DWORD *)(v142 + 2976) = v133;
          }
          goto LABEL_188;
        }
        v27 = *(HANDLE_OBJECT **)&v190.Data1;
        DWORD1(v187) = 5367;
      }
LABEL_188:
      v44 = WX_WIN32_FROM_HR((unsigned int)AllocationEntry);
      if ( !v44 )
      {
        v145 = Src;
        v146 = -1;
        DWORD1(v187) = 0;
        v147 = -1;
        v190.Data1 = 0;
        if ( Src )
        {
          v144 = 0x7FFFFFFF;
          v148 = Src;
          v149 = 0x7FFFFFFF;
          while ( *v148 )
          {
            ++v148;
            if ( !--v149 )
            {
              DWORD1(v187) = 54;
              goto LABEL_199;
            }
          }
          v150 = 0;
          v144 = (unsigned int)(0x7FFFFFFF - v149);
          *(_QWORD *)&v187 = (unsigned int)v144;
          while ( (unsigned int)v150 < 0x1F )
          {
            v151 = 3 * v150;
            if ( dword_1801F1D50[6 * v150] == (_DWORD)v144 )
            {
              if ( !memcmp_0((&off_1801F1D58)[v151], v145, (unsigned int)v144) )
              {
                v147 = *(_DWORD *)((char *)&unk_1801F1D60 + v151 * 8);
                break;
              }
              v144 = v187;
              v145 = Src;
            }
            v150 = (unsigned int)(v150 + 1);
          }
        }
        else
        {
          DWORD1(v187) = 50;
        }
LABEL_199:
        *((_DWORD *)v27 + 766) = v147;
        v9 = v176;
        v185 = 0;
        if ( !v176 )
          goto LABEL_200;
        do
          ++v146;
        while ( v176[v146] );
        if ( v146 > 0xFFFFFFFF )
        {
          v185 = -1;
          goto LABEL_200;
        }
        v185 = v146;
        if ( !(_DWORD)v146
          || (v44 = CHttpHeaders::AddHeaderByIndex((HANDLE_OBJECT *)((char *)v27 + 1280), 0x23u, v176, v146, 0, 1u)) == 0 )
        {
LABEL_200:
          if ( v183 )
          {
            for ( k = 0; (unsigned int)k < 0x7D0; k = (unsigned int)(k + 1) )
            {
              v159 = *((_QWORD *)v183 + k);
              if ( !v159 || (int)ValidateDubiousStringA(v159, v144, &v185) < 0 )
                break;
              if ( v185 )
              {
                v44 = CHttpHeaders::AddHeaderByIndex(
                        (HANDLE_OBJECT *)((char *)v27 + 1280),
                        0x18u,
                        *((const char **)v183 + k),
                        v185,
                        0,
                        0x40000001u);
                if ( v44 )
                  goto LABEL_232;
              }
            }
          }
          LeaveCriticalSection(*(LPCRITICAL_SECTION *)&Buf1.Data1);
          if ( (xmmword_180266B60 & 2) != 0 )
            WPP_SF_dd(1025, 12, &WPP_d7bfcb29513b303c34446843d299ef9e_Traceguids, *((unsigned int *)v27 + 318), 65281);
          v153 = a7;
          *((_DWORD *)v27 + 318) = 65281;
          *((_DWORD *)v27 + 1288) = 0;
          v154 = *((_DWORD *)v27 + 766);
          if ( v154 && v154 != 2 )
          {
            v153 = a7 | 0x84000000;
            a7 |= 0x84000000;
          }
          if ( GlobalCacheMode == 1 )
          {
            v153 |= 0x800u;
          }
          else
          {
            if ( GlobalCacheMode != 2 )
              goto LABEL_208;
            v153 |= 0x80000000;
          }
          a7 = v153;
LABEL_208:
          *((_DWORD *)v27 + 191) = v153;
          v183 = (unsigned int (*)(enum INTERNET_SCHEME, char *, char *, char *, char *, unsigned int, char **, unsigned int *))pHttpGetUrlString;
          v44 = INTERNET_CONNECT_HANDLE_OBJECT::SetObjectName(v27, v177, v152, &v183);
          if ( !v44 )
          {
            if ( *v177 == 47 && !v177[1] )
              *((_DWORD *)v27 + 1319) |= 0x400u;
            goto LABEL_44;
          }
          goto LABEL_223;
        }
LABEL_232:
        LeaveCriticalSection(*(LPCRITICAL_SECTION *)&Buf1.Data1);
LABEL_223:
        if ( v27 )
          InternalInternetCloseHandle(*((_QWORD *)v27 + 16));
        goto LABEL_246;
      }
      LeaveCriticalSection(v117);
LABEL_222:
      v9 = v176;
      goto LABEL_223;
    }
    pszStr1 = "HTTP/1.1";
    goto LABEL_135;
  }
  v97 = StringCchPrintfA(v226, 0x1Bu, "HTTP/%d.%d", HttpVersionInfo, HIDWORD(HttpVersionInfo));
  if ( v97 >= 0 )
  {
    v98 = HttpVersionInfo;
    v96 = HIDWORD(HttpVersionInfo);
    pszStr1 = v226;
    goto LABEL_134;
  }
  v43 = MapHRtoWin32Error((unsigned int)v97);
LABEL_43:
  v185 = v43;
  v9 = a5;
  v44 = v43;
  if ( v43 )
    goto LABEL_223;
LABEL_44:
  EtwEndActivityId(&v193);
  v45 = 16;
  v46 = &v193;
  v47 = (const struct _GUID *)((char *)v27 + 164);
  do
  {
    LOBYTE(v46->Data1) = 0;
    v46 = (struct _GUID *)((char *)v46 + 1);
    --v45;
  }
  while ( v45 );
  v194 = 0;
  v48 = &v193;
  v187 = 0;
  v49 = 16;
  Buf1 = 0;
  do
  {
    LOBYTE(v48->Data1) = 0;
    v48 = (struct _GUID *)((char *)v48 + 1);
    --v49;
  }
  while ( v49 );
  HIDWORD(v183) = 0;
  v195 = 0;
  v50 = 16;
  v51 = &Buf1;
  do
  {
    LOBYTE(v51->Data1) = 0;
    v51 = (struct _GUID *)((char *)v51 + 1);
    --v50;
  }
  while ( v50 );
  v52 = EtwEventActivityIdControl(1, &v195);
  v53 = v52 < 0;
  if ( v52 > 0 )
    v53 = 1;
  if ( v53 )
    HIDWORD(v183) = 128;
  else
    Buf1 = v195;
  if ( v27 == (HANDLE_OBJECT *)-164LL )
  {
    v81 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    v82 = GetTickCount();
    *((_QWORD *)&v187 + 1) = __PAIR64__(GetCurrentProcessId(), v82);
    v47 = (const struct _GUID *)&v187;
    *(_QWORD *)&v187 = __PAIR64__(v81, (unsigned int)retaddr);
  }
  HIDWORD(v183) = 0;
  v54 = EtwEventActivityIdControl(2, v47);
  v55 = v54 < 0;
  if ( v54 > 0 )
    v55 = 1;
  if ( v55 )
    HIDWORD(v183) = 144;
  if ( g_fEtwCorrelationProviderInitialized
    && memcmp_0(&Buf1, &qword_18021DEE0, 0x10u)
    && memcmp_0(v47, &qword_18021DEE0, 0x10u)
    && Microsoft_Windows_Networking_CorrelationEnabled )
  {
    EtwEx_tidActivityInfoTransfer(v57, v56, v47, &Buf1, (unsigned __int8)lpString2, cchCount2, v175);
  }
  v193 = Buf1;
  v194 = 1;
  v58 = (unsigned int (*)(enum INTERNET_SCHEME, char *, char *, char *, char *, unsigned int, char **, unsigned int *))*((_QWORD *)v27 + 16);
LABEL_66:
  v59 = v180;
  if ( v180 && (!a9 || v44) && !(unsigned int)DereferenceObject(v180) && !v44 )
  {
    v44 = 12017;
    RecordInternetError(0, 12017);
    v58 = 0;
  }
  v60 = v184;
  if ( v184 )
    DereferenceObject(v184);
  if ( v58 )
  {
    v61 = Microsoft_Windows_WinINetEnableBits;
    if ( (Microsoft_Windows_WinINetEnableBits & 2) != 0 )
    {
      v62 = 0;
      if ( v9 )
      {
        HIDWORD(v183) = 0;
        v63 = 0xFFFF;
        v186 = 0;
        v64 = v9;
        do
        {
          if ( !*v64 )
            break;
          ++v64;
          --v63;
        }
        while ( v63 );
        v65 = -2147024809;
        if ( v63 )
        {
          v65 = 0;
          v62 = -1 - v63;
        }
        else
        {
          HIDWORD(v183) = 135;
        }
        WX_WIN32_FROM_HR(v65);
      }
      v66 = 0;
      v67 = v62;
      if ( pszStr1 )
      {
        HIDWORD(v183) = 0;
        v68 = 0xFFFF;
        v186 = 0;
        v69 = pszStr1;
        do
        {
          if ( !*v69 )
            break;
          ++v69;
          --v68;
        }
        while ( v68 );
        v70 = -2147024809;
        if ( v68 )
        {
          v70 = 0;
          v66 = -1 - v68;
        }
        else
        {
          HIDWORD(v183) = 135;
        }
        WX_WIN32_FROM_HR(v70);
      }
      v71 = 0;
      if ( v177 )
      {
        HIDWORD(v183) = 0;
        v72 = 0xFFFF;
        v186 = 0;
        v73 = v177;
        do
        {
          if ( !*v73 )
            break;
          ++v73;
          --v72;
        }
        while ( v72 );
        v74 = -2147024809;
        if ( v72 )
        {
          v74 = 0;
          v71 = -1 - v72;
        }
        else
        {
          HIDWORD(v183) = 135;
        }
        WX_WIN32_FROM_HR(v74);
      }
      v75 = (struct _GUID *)Src;
      v76 = 0;
      if ( Src )
      {
        HIDWORD(v183) = 0;
        v77 = 0xFFFF;
        v186 = 0;
        v78 = Src;
        do
        {
          if ( !*v78 )
            break;
          ++v78;
          --v77;
        }
        while ( v77 );
        v79 = -2147024809;
        if ( v77 )
        {
          v79 = 0;
          v76 = -1 - v77;
        }
        else
        {
          HIDWORD(v183) = 135;
        }
        WX_WIN32_FROM_HR(v79);
        v75 = (struct _GUID *)Src;
      }
      v190.Data1 = a7;
      *(_QWORD *)&v187 = a1;
      v197 = &v183;
      v199 = (unsigned int *)&v187;
      v201 = (__int16 *)&v186;
      v204 = v76;
      v205 = &v192;
      v207 = v177;
      v208 = v71;
      v210 = &v188;
      v212 = pszStr1;
      v213 = v66;
      p_Src = &Src;
      v217 = v176;
      v220 = &v185;
      v224 = &v190;
      v203 = v75;
      v186 = v76;
      v183 = v58;
      LOWORD(v185) = 0;
      LODWORD(Src) = v67;
      LOWORD(v188) = v66;
      LOWORD(v192) = v71;
      v198 = 8;
      v200 = 8;
      v202 = 2;
      v206 = 2;
      v209 = 0;
      v211 = 2;
      v214 = 0;
      v216 = 4;
      v218 = v67;
      v219 = 0;
      v221 = 2;
      v222 = 0;
      v223 = 0;
      v225 = 4;
      McGenEventWrite_EventWriteTransfer(&WININET_Context, "h", 0, 14, v196);
      v61 = Microsoft_Windows_WinINetEnableBits;
      v59 = v180;
    }
    if ( !v181 )
      goto LABEL_101;
    if ( *((_DWORD *)v181 + 216) )
      v160 = (__int16 *)*((_QWORD *)v181 + 107);
    else
      v160 = 0;
    v161 = *((unsigned int *)v59 + 234);
    if ( (_DWORD)v161 )
    {
      if ( (_DWORD)v161 != 3 )
      {
        if ( (int)v161 < 1 )
          goto LABEL_276;
        goto LABEL_275;
      }
    }
    else
    {
      v161 = 3;
    }
    if ( (*((_DWORD *)v59 + 317) & 0x800000) != 0 )
    {
      v161 = 4;
LABEL_267:
      v162 = qword_1801F0230[6 * v161];
      goto LABEL_268;
    }
LABEL_275:
    if ( (unsigned int)v161 <= 0xB )
      goto LABEL_267;
LABEL_276:
    v162 = 0;
LABEL_268:
    if ( (v61 & 2) != 0 )
    {
      v163 = inetstrlenUShortA(v162);
      v190.Data1 = *((unsigned __int16 *)v181 + 466);
      LOWORD(v185) = v164;
      v202 = v164;
      v203 = &v190;
      v197 = &v183;
      v205 = &v188;
      LOWORD(v188) = v163;
      v199 = &v185;
      v208 = v163;
      v183 = v58;
      v198 = 8;
      v200 = 2;
      v201 = v160;
      v204 = 4;
      v206 = 2;
      v207 = v165;
      v209 = 0;
      McGenEventWrite_EventWriteTransfer(&WININET_Context, "l", v166, 7, v196);
    }
    goto LABEL_101;
  }
  if ( (Microsoft_Windows_WinINetEnableBits & 4) != 0 )
    McTemplateU0pq_EventWriteTransfer(v60, &WININET_HANDLE_CREATE_FAILED, a1, v44);
  if ( (xmmword_180266B50 & 2) != 0 )
    WPP_SF_d(513, 11, &WPP_3b892b38db6931a8a6d65064a04e2efa_Traceguids, v44);
LABEL_101:
  if ( v182 )
    WxHeapFree<char>(&v182);
  if ( (xmmword_180266B60 & 4) != 0 )
    WPP_SF_q(1026, 12, &WPP_3b892b38db6931a8a6d65064a04e2efa_Traceguids, v58);
  EtwEndActivityId(&v193);
  SetLastError(v44);
  return v58;
}

```

## disassembly

```asm
0x180009d60  push    rbx
0x180009d62  push    rsi
0x180009d63  push    rdi
0x180009d64  push    r12
0x180009d66  push    r13
0x180009d68  push    r14
0x180009d6a  push    r15
0x180009d6c  sub     rsp, 240h
0x180009d73  mov     rax, cs:__security_cookie
0x180009d7a  xor     rax, rsp
0x180009d7d  mov     [rsp+278h+var_48], rax
0x180009d85  mov     r14, [rsp+278h+arg_20]
0x180009d8d  mov     rsi, rdx
0x180009d90  mov     r13, [rsp+278h+arg_28]
0x180009d98  mov     rbx, r9
0x180009d9b  mov     [rsp+278h+Src], rdx
0x180009da3  xorps   xmm0, xmm0
0x180009da6  xor     edx, edx
0x180009da8  mov     [rsp+278h+pszStr1], rbx
0x180009dad  xor     eax, eax
0x180009daf  mov     [rsp+278h+var_210], r8
0x180009db4  mov     [rsp+278h+var_160], eax
0x180009dbb  mov     r12, rcx
0x180009dbe  mov     [rsp+278h+var_200], rcx
0x180009dc3  mov     [rsp+278h+var_218], r14
0x180009dc8  mov     [rsp+278h+var_1E0], r13
0x180009dd0  mov     [rsp+278h+var_1D8], rdx
0x180009dd8  mov     [rsp+278h+var_1F0], rdx
0x180009de0  mov     [rsp+278h+var_1F8], rdx
0x180009de8  movups  [rsp+278h+var_170], xmm0
0x180009df0  mov     [rsp+278h+var_1E8], rdx
0x180009df8  test    byte ptr cs:xmmword_180266B60, 4
0x180009dff  mov     r15, [rsp+278h+arg_38]
0x180009e07  jnz     loc_18000B47B
0x180009e0d  cmp     cs:GlobalDataInitialized, 0
0x180009e14  jz      loc_18000B4E9
0x180009e1a  mov     ecx, 10h
0x180009e1f  lea     rax, [rsp+278h+var_170]
0x180009e27  nop     word ptr [rax+rax+00000000h]
0x180009e30  mov     byte ptr [rax], 0
0x180009e33  lea     rax, [rax+1]
0x180009e37  sub     rcx, 1
0x180009e3b  jnz     short loc_180009E30
0x180009e3d  xorps   xmm0, xmm0
0x180009e40  mov     [rsp+278h+var_160], edx
0x180009e47  xorps   xmm1, xmm1
0x180009e4a  lea     rax, [rsp+278h+var_170]
0x180009e52  movups  [rsp+278h+Buf1], xmm0
0x180009e5a  mov     ecx, 10h
0x180009e5f  movups  xmmword ptr [rsp+278h+var_198.Data1], xmm1
0x180009e67  nop     word ptr [rax+rax+00000000h]
0x180009e70  mov     byte ptr [rax], 0
0x180009e73  lea     rax, [rax+1]
0x180009e77  sub     rcx, 1
0x180009e7b  jnz     short loc_180009E70
0x180009e7d  xorps   xmm0, xmm0
0x180009e80  mov     dword ptr [rsp+278h+var_1C0+4], edx
0x180009e87  movups  xmmword ptr [rsp+278h+var_158.Data1], xmm0
0x180009e8f  mov     ecx, 10h
0x180009e94  lea     rax, [rsp+278h+var_198]
0x180009e9c  nop     dword ptr [rax+00h]
0x180009ea0  mov     byte ptr [rax], 0
0x180009ea3  lea     rax, [rax+1]
0x180009ea7  sub     rcx, 1
0x180009eab  jnz     short loc_180009EA0
0x180009ead  lea     rdx, [rsp+278h+var_158]
0x180009eb5  mov     ecx, 1
0x180009eba  call    cs:__imp_EtwEventActivityIdControl
0x180009ec0  test    eax, eax
0x180009ec2  jle     short loc_180009ECE
0x180009ec4  movzx   eax, ax
0x180009ec7  or      eax, 80070000h
0x180009ecc  test    eax, eax
0x180009ece  js      loc_18000B4F4
0x180009ed4  movaps  xmm0, xmmword ptr [rsp+278h+var_158.Data1]
0x180009edc  movdqa  xmmword ptr [rsp+278h+var_198.Data1], xmm0
0x180009ee5  mov     rdi, [rsp+278h]
0x180009eed  mov     esi, 1
0x180009ef2  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x180009efa  inc     esi
0x180009efc  call    cs:__imp_GetTickCount
0x180009f02  mov     ebx, eax
0x180009f04  call    cs:__imp_GetCurrentProcessId
0x180009f0a  mov     dword ptr [rsp+278h+Buf1], edi
0x180009f11  lea     rdx, [rsp+278h+Buf1]
0x180009f19  mov     dword ptr [rsp+278h+Buf1+0Ch], eax
0x180009f20  mov     ecx, 2
0x180009f25  mov     dword ptr [rsp+278h+Buf1+4], esi
0x180009f2c  mov     dword ptr [rsp+278h+Buf1+8], ebx
0x180009f33  mov     dword ptr [rsp+278h+var_1C0+4], 0
0x180009f3e  call    cs:__imp_EtwEventActivityIdControl
0x180009f44  test    eax, eax
0x180009f46  jle     short loc_180009F52
0x180009f48  movzx   eax, ax
0x180009f4b  or      eax, 80070000h
0x180009f50  test    eax, eax
0x180009f52  js      loc_18000B504
0x180009f58  lea     rdx, [rsp+278h+var_198]; struct _GUID *
0x180009f60  lea     rcx, [rsp+278h+Buf1]; struct _GUID *
0x180009f68  call    ?WxEtwTransferActivityId@@YAXPEBU_GUID@@0@Z; WxEtwTransferActivityId(_GUID const *,_GUID const *)
0x180009f6d  movaps  xmm0, xmmword ptr [rsp+278h+var_198.Data1]
0x180009f75  movups  [rsp+278h+var_170], xmm0
0x180009f7d  mov     [rsp+278h+var_160], 1
0x180009f88  call    InternetGetThreadInfo
0x180009f8d  mov     r14, rax
0x180009f90  test    rax, rax
0x180009f93  jz      loc_18000B514
0x180009f99  xor     r8d, r8d
0x180009f9c  lea     rdx, [rsp+278h+var_1D8]
0x180009fa4  mov     rcx, r12
0x180009fa7  call    MapHandleToAddress
0x180009fac  test    eax, eax
0x180009fae  jnz     loc_18000B82B
0x180009fb4  mov     rbx, [rsp+278h+var_1D8]
0x180009fbc  mov     edx, 6E6F4348h
0x180009fc1  mov     rcx, rbx
0x180009fc4  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x180009fc9  test    eax, eax
0x180009fcb  jnz     loc_18000B82B
0x180009fd1  mov     rax, [rbx]
0x180009fd4  xor     r12d, r12d
0x180009fd7  mov     rcx, rbx
0x180009fda  mov     rax, [rax+10h]
0x180009fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fe3  mov     rdx, [rsp+278h+var_1D8]
0x180009feb  mov     edi, 7FFFFFFFh
0x180009ff0  mov     [rsp+278h+var_1F0], rdx
0x180009ff8  mov     ebx, 80070057h
0x180009ffd  cmp     [rdx+3E0h], r12d
0x18000a004  jnz     loc_18000B3BC
0x18000a00a  mov     rsi, [rsp+278h+Src]
0x18000a012  test    rsi, rsi
0x18000a015  jz      loc_18000A701
0x18000a01b  cmp     [rsi], r12b
0x18000a01e  jz      loc_18000A701
0x18000a024  xor     r13d, r13d
0x18000a027  mov     ecx, edi
0x18000a029  mov     dword ptr [rsp+278h+var_198.Data2], r13d
0x18000a031  mov     rax, rsi
0x18000a034  mov     dword ptr [rsp+278h+var_1C0+4], r13d
0x18000a03c  mov     [rsp+278h+var_1D0], r13d
0x18000a044  cmp     [rax], r12b
0x18000a047  jz      short loc_18000A052
0x18000a049  inc     rax
0x18000a04c  sub     rcx, 1
0x18000a050  jnz     short loc_18000A044
0x18000a052  test    rcx, rcx
0x18000a055  mov     edx, ebx
0x18000a057  cmovnz  edx, r13d
0x18000a05b  jz      loc_18000B413
0x18000a061  sub     edi, ecx
0x18000a063  mov     ecx, edx
0x18000a065  call    WX_WIN32_FROM_HR
0x18000a06a  test    edi, edi
0x18000a06c  jz      loc_18000B56A
0x18000a072  movzx   eax, byte ptr [rsi]
0x18000a075  mov     rdx, rsi
0x18000a078  mov     ebx, r13d
0x18000a07b  test    al, al
0x18000a07d  jz      short loc_18000A08F
0x18000a07f  cmp     al, 20h ; ' '
0x18000a081  jz      loc_18000B57C
0x18000a087  cmp     al, 9
0x18000a089  jz      loc_18000B57C
0x18000a08f  movzx   eax, byte ptr [rdx]
0x18000a092  mov     rsi, rdx
0x18000a095  test    al, al
0x18000a097  jz      short loc_18000A107
0x18000a099  nop     dword ptr [rax+00000000h]
0x18000a0a0  sub     al, 21h ; '!'
0x18000a0a2  cmp     al, 5Dh ; ']'
0x18000a0a4  jbe     loc_18000B4D3
0x18000a0aa  test    ebx, ebx
0x18000a0ac  jz      short loc_18000A107
0x18000a0ae  movzx   ecx, byte ptr [rdx]; unsigned __int8
0x18000a0b1  test    cl, cl
0x18000a0b3  jnz     loc_18000B590
0x18000a0b9  cmp     ebx, edi
0x18000a0bb  jnb     loc_18000A71D
0x18000a0c1  lea     edx, [rbx+1]
0x18000a0c4  mov     dword ptr [rsp+278h+var_1C0+4], r13d
0x18000a0cc  call    WxAllocateHeapEx
0x18000a0d1  mov     rdi, rax
0x18000a0d4  test    rax, rax
0x18000a0d7  jz      loc_18000B4B3
0x18000a0dd  mov     r8, rbx; Size
0x18000a0e0  mov     rdx, rsi; Src
0x18000a0e3  mov     rcx, rax; void *
0x18000a0e6  call    memcpy_0
0x18000a0eb  mov     [rbx+rdi], r12b
0x18000a0ef  mov     rsi, rdi
0x18000a0f2  mov     [rsp+278h+var_1E8], rdi
0x18000a0fa  mov     [rsp+278h+Src], rdi
0x18000a102  jmp     loc_18000A725
0x18000a107  mov     dword ptr [rsp+278h+var_198.Data2], 0AEh
0x18000a112  mov     edi, 80070057h
0x18000a117  mov     ecx, edi
0x18000a119  call    WX_WIN32_FROM_HR
0x18000a11e  mov     esi, eax
0x18000a120  mov     [rsp+278h+var_1D0], eax
0x18000a127  mov     r14, [rsp+278h+var_218]
0x18000a12c  mov     r13d, eax
0x18000a12f  test    eax, eax
0x18000a131  jnz     loc_18000AF53
0x18000a137  lea     rcx, [rsp+278h+var_170]
0x18000a13f  call    EtwEndActivityId
0x18000a144  mov     ecx, 10h
0x18000a149  lea     rax, [rsp+278h+var_170]
0x18000a151  lea     rbx, [r12+0A4h]
0x18000a159  nop     dword ptr [rax+00000000h]
0x18000a160  mov     byte ptr [rax], 0
0x18000a163  lea     rax, [rax+1]
0x18000a167  sub     rcx, 1
0x18000a16b  jnz     short loc_18000A160
0x18000a16d  xorps   xmm0, xmm0
0x18000a170  mov     [rsp+278h+var_160], ecx
0x18000a177  xorps   xmm1, xmm1
0x18000a17a  lea     rax, [rsp+278h+var_170]
0x18000a182  movups  xmmword ptr [rsp+0B8h], xmm0
0x18000a18a  mov     ecx, 10h
0x18000a18f  movups  [rsp+278h+Buf1], xmm1
0x18000a197  nop     word ptr [rax+rax+00000000h]
0x18000a1a0  mov     byte ptr [rax], 0
0x18000a1a3  lea     rax, [rax+1]
0x18000a1a7  sub     rcx, 1
0x18000a1ab  jnz     short loc_18000A1A0
0x18000a1ad  xorps   xmm0, xmm0
0x18000a1b0  mov     dword ptr [rsp+278h+var_1E0+4], ecx
0x18000a1b7  movups  xmmword ptr [rsp+278h+var_158.Data1], xmm0
0x18000a1bf  mov     ecx, 10h
0x18000a1c4  lea     rax, [rsp+278h+Buf1]
0x18000a1cc  nop     dword ptr [rax+00h]
0x18000a1d0  mov     byte ptr [rax], 0
0x18000a1d3  lea     rax, [rax+1]
0x18000a1d7  sub     rcx, 1
0x18000a1db  jnz     short loc_18000A1D0
0x18000a1dd  lea     rdx, [rsp+278h+var_158]
0x18000a1e5  mov     ecx, 1
0x18000a1ea  call    cs:__imp_EtwEventActivityIdControl
0x18000a1f0  test    eax, eax
0x18000a1f2  jle     short loc_18000A1FE
0x18000a1f4  movzx   eax, ax
0x18000a1f7  or      eax, 80070000h
0x18000a1fc  test    eax, eax
0x18000a1fe  js      loc_18000B80B
0x18000a204  movaps  xmm0, xmmword ptr [rsp+278h+var_158.Data1]
0x18000a20c  movdqa  [rsp+278h+Buf1], xmm0
0x18000a215  test    rbx, rbx
0x18000a218  jz      loc_18000A6B3
0x18000a21e  mov     rdx, rbx
0x18000a221  mov     dword ptr [rsp+278h+var_1E0+4], 0
0x18000a22c  mov     ecx, 2
0x18000a231  call    cs:__imp_EtwEventActivityIdControl
0x18000a237  test    eax, eax
0x18000a239  jle     short loc_18000A245
0x18000a23b  movzx   eax, ax
0x18000a23e  or      eax, 80070000h
0x18000a243  test    eax, eax
0x18000a245  js      loc_18000B81B
0x18000a24b  cmp     cs:?g_fEtwCorrelationProviderInitialized@@3HA, 0; int g_fEtwCorrelationProviderInitialized
0x18000a252  jz      short loc_18000A299
0x18000a254  mov     r8d, 10h; Size
0x18000a25a  lea     rdx, qword_18021DEE0; Buf2
0x18000a261  lea     rcx, [rsp+278h+Buf1]; Buf1
0x18000a269  call    memcmp_0
0x18000a26e  test    eax, eax
0x18000a270  jz      short loc_18000A299
0x18000a272  mov     r8d, 10h; Size
0x18000a278  lea     rdx, qword_18021DEE0; Buf2
0x18000a27f  mov     rcx, rbx; Buf1
0x18000a282  call    memcmp_0
0x18000a287  test    eax, eax
0x18000a289  jz      short loc_18000A299
0x18000a28b  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18000a291  test    eax, eax
0x18000a293  jnz     loc_18000B466
0x18000a299  movaps  xmm0, [rsp+278h+Buf1]
0x18000a2a1  movups  [rsp+278h+var_170], xmm0
0x18000a2a9  mov     [rsp+278h+var_160], 1
0x18000a2b4  mov     r12, [r12+80h]
0x18000a2bc  mov     rsi, [rsp+278h+var_1F8]
0x18000a2c4  test    rsi, rsi
0x18000a2c7  jnz     loc_18000B18F
0x18000a2cd  mov     rcx, [rsp+278h+var_1D8]
0x18000a2d5  test    rcx, rcx
0x18000a2d8  jz      short loc_18000A2DF
0x18000a2da  call    DereferenceObject
0x18000a2df  test    r12, r12
0x18000a2e2  jz      loc_18000B833
0x18000a2e8  mov     eax, cs:Microsoft_Windows_WinINetEnableBits
0x18000a2ee  test    al, 2
0x18000a2f0  jz      loc_18000A64A
0x18000a2f6  xor     r8d, r8d
0x18000a2f9  mov     r15d, 0FFFFh
0x18000a2ff  mov     ebx, r8d
0x18000a302  test    r14, r14
0x18000a305  jz      short loc_18000A34F
0x18000a307  mov     dword ptr [rsp+278h+var_1E0+4], r8d
0x18000a30f  mov     ecx, r15d
0x18000a312  mov     [rsp+278h+var_1C8], r8w
  ... truncated ...
```
