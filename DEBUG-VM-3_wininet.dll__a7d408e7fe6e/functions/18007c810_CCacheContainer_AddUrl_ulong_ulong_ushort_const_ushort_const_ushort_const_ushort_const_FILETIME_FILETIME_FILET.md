# CCacheContainer::AddUrl(ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,_FILETIME,_FILETIME,_FILETIME,uchar const *,ulong,uchar const *,ulong,ulong,ushort * *,int)

- ea: `0x18007c810`
- end: `0x18007e53d`
- name: `?AddUrl@CCacheContainer@@QEAAJKKPEBG000U_FILETIME@@11PEBEK2KKPEAPEAGH@Z`
- size: `7469`
- prototype: `__int64 __fastcall(CCacheContainer *__hidden this, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _FILETIME, struct _FILETIME, struct _FILETIME, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, unsigned int, unsigned __int16 **, int)`
- caller_count: `3`
- callee_count: `41`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180086d80`
- `0x180115e60`
- `0x1801aa40c`

## callees

- `0x180020fc4`
- `0x180023590`
- `0x1800701d0`
- `0x18007c810`
- `0x18007e620`
- `0x18007ec9c`
- `0x180082700`
- `0x180083540`
- `0x180083dc4`
- `0x180085414`
- `0x180085460`
- `0x180085898`
- `0x180085988`
- `0x180085a44`
- `0x1800867cc`
- `0x180086aa4`
- `0x1800b4a7c`
- `0x1800b5bdc`
- `0x1800b6bac`
- `0x1800d6ea4`
- `0x1800ec97c`
- `0x1800f125c`
- `0x1800fc68c`
- `0x1800ffb10`
- `0x18011a46c`
- `0x18014a3a4`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801ab060`
- `0x1801e0b60`
- `0x1801e0ff0`
- `0x1801e1790`
- `0x1801e17f0`
- `0x1801e1b00`
- `0x1801e1b60`
- `0x1801e1c40`
- `0x1801e2f9c`
- `0x1801e3c78`
- `0x1801e4988`
- `0x1801e4c70`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e08d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007e08d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007e0e7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007e0e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cab6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cbd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cc55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cc7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cff0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007da6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007daf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007db09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dc66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007df14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cab6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cbd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cc55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cc7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cff0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007da6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007daf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007db09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007dc66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007df14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ca7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cad8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cbe6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cc1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cf7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007da79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dabc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dc25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dedb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ca7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cad8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cbe6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cc1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cf7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007da79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dabc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dc25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007dedb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18007dfcf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18007dfcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007da61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007da61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007cbf4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007cbf4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007df8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007df8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007dbcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007dbcb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007ca2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007ca2b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007e388`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007e388`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18007de38`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18007e402`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18007de38`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18007e402`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007e3b9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007e3b9`
- `ESENT!JetSetCurrentIndex2W` at `0x18007e049`
- `ESENT!JetSetCurrentIndex2W` at `0x18007e049`
- `ESENT!JetSetColumn` at `0x18007ce30`
- `ESENT!JetSetColumn` at `0x18007ce9e`
- `ESENT!JetSetColumn` at `0x18007d021`
- `ESENT!JetSetColumn` at `0x18007d05e`
- `ESENT!JetSetColumn` at `0x18007d0eb`
- `ESENT!JetSetColumn` at `0x18007d1ab`
- `ESENT!JetSetColumn` at `0x18007d219`
- `ESENT!JetSetColumn` at `0x18007d256`
- `ESENT!JetSetColumn` at `0x18007d2d4`
- `ESENT!JetSetColumn` at `0x18007d37e`
- `ESENT!JetSetColumn` at `0x18007d40e`
- `ESENT!JetSetColumn` at `0x18007d479`
- `ESENT!JetSetColumn` at `0x18007d4b6`
- `ESENT!JetSetColumn` at `0x18007d4f3`
- `ESENT!JetSetColumn` at `0x18007d530`
- `ESENT!JetSetColumn` at `0x18007d56d`
- `ESENT!JetSetColumn` at `0x18007d5aa`
- `ESENT!JetSetColumn` at `0x18007d5e7`
- `ESENT!JetSetColumn` at `0x18007d624`
- `ESENT!JetSetColumn` at `0x18007d661`
- `ESENT!JetSetColumn` at `0x18007d69e`
- `ESENT!JetSetColumn` at `0x18007d6db`
- `ESENT!JetSetColumn` at `0x18007d75c`
- `ESENT!JetSetColumn` at `0x18007d7f4`
- `ESENT!JetSetColumn` at `0x18007ce30`
- `ESENT!JetSetColumn` at `0x18007ce9e`
- `ESENT!JetSetColumn` at `0x18007d021`
- `ESENT!JetSetColumn` at `0x18007d05e`
- `ESENT!JetSetColumn` at `0x18007d0eb`
- `ESENT!JetSetColumn` at `0x18007d1ab`
- `ESENT!JetSetColumn` at `0x18007d219`
- `ESENT!JetSetColumn` at `0x18007d256`
- `ESENT!JetSetColumn` at `0x18007d2d4`
- `ESENT!JetSetColumn` at `0x18007d37e`
- `ESENT!JetSetColumn` at `0x18007d40e`
- `ESENT!JetSetColumn` at `0x18007d479`
- `ESENT!JetSetColumn` at `0x18007d4b6`
- `ESENT!JetSetColumn` at `0x18007d4f3`
- `ESENT!JetSetColumn` at `0x18007d530`
- `ESENT!JetSetColumn` at `0x18007d56d`
- `ESENT!JetSetColumn` at `0x18007d5aa`
- `ESENT!JetSetColumn` at `0x18007d5e7`
- `ESENT!JetSetColumn` at `0x18007d624`
- `ESENT!JetSetColumn` at `0x18007d661`
- `ESENT!JetSetColumn` at `0x18007d69e`
- `ESENT!JetSetColumn` at `0x18007d6db`
- `ESENT!JetSetColumn` at `0x18007d75c`
- `ESENT!JetSetColumn` at `0x18007d7f4`
- `ESENT!JetCommitTransaction` at `0x18007d86a`
- `ESENT!JetCommitTransaction` at `0x18007d86a`
- `ESENT!JetUpdate` at `0x18007d847`
- `ESENT!JetUpdate` at `0x18007d847`
- `ESENT!JetPrepareUpdate` at `0x18007cd91`
- `ESENT!JetPrepareUpdate` at `0x18007e521`
- `ESENT!JetPrepareUpdate` at `0x18007cd91`
- `ESENT!JetPrepareUpdate` at `0x18007e521`
- `ESENT!JetRollback` at `0x18007e532`
- `ESENT!JetRollback` at `0x18007e532`
- `ESENT!JetBeginTransaction` at `0x18007cd20`
- `ESENT!JetBeginTransaction` at `0x18007cd20`

## pseudocode

```c
__int64 __fastcall CCacheContainer::AddUrl(
        CContainerProps **this,
        unsigned int a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned __int16 *a7,
        struct _FILETIME a8,
        FILETIME a9,
        struct _FILETIME a10,
        unsigned __int8 *a11,
        unsigned int a12,
        unsigned __int8 *a13,
        unsigned int a14,
        unsigned int a15,
        unsigned __int16 **a16,
        int a17)
{
  char v17; // r12
  char v18; // r15
  volatile signed __int32 *v19; // r14
  int v20; // edx
  __int64 *j; // rcx
  int v22; // r8d
  WCHAR *v23; // rsi
  const unsigned __int16 *v24; // rbx
  CCacheContainer *v25; // r12
  int v26; // r15d
  bool v27; // zf
  int updated; // edi
  unsigned __int64 v29; // rax
  __int64 v30; // rcx
  unsigned __int64 v31; // r13
  int v32; // r12d
  __int64 v33; // rbx
  char *v34; // r15
  struct _RTL_CRITICAL_SECTION *v35; // r13
  volatile signed __int32 *Ptr; // rax
  __int64 v37; // rdi
  __int64 *i; // rsi
  int v39; // eax
  int v40; // r12d
  _OWORD *v41; // rax
  _OWORD *v42; // rbx
  volatile signed __int32 **v43; // rbx
  volatile signed __int32 *v44; // rbx
  RTL_SRWLOCK *v45; // rsi
  char *v46; // rsi
  int v47; // r13d
  int v48; // eax
  int v49; // edx
  CJetContext *v50; // r13
  JET_ERR v51; // eax
  const unsigned __int16 *v52; // rbx
  int v53; // eax
  unsigned int v54; // ebx
  JET_ERR v55; // eax
  JET_TABLEID v56; // rsi
  unsigned int cbData; // ebx
  JET_SESID v58; // r15
  __int64 v59; // rcx
  JET_COLUMNID v60; // edi
  __int64 v61; // rax
  JET_ERR v62; // eax
  unsigned int v63; // eax
  __int64 v64; // rbx
  int v65; // esi
  const unsigned __int16 *v66; // r10
  int v67; // edx
  const unsigned __int16 *v68; // r9
  int v69; // r8d
  unsigned __int16 v70; // cx
  int v71; // eax
  const unsigned __int16 *v72; // rdx
  JET_TABLEID v73; // rsi
  unsigned int v74; // ebx
  JET_SESID v75; // r15
  JET_COLUMNID v76; // edi
  __int64 v77; // rax
  JET_ERR v78; // eax
  unsigned int v79; // eax
  JET_TABLEID v80; // rsi
  unsigned int v81; // ebx
  JET_SESID v82; // r15
  JET_COLUMNID v83; // edi
  __int64 v84; // rax
  JET_ERR v85; // eax
  unsigned int v86; // eax
  int v87; // edx
  JET_TABLEID v88; // rdi
  JET_SESID v89; // rsi
  JET_COLUMNID v90; // ebx
  void *v91; // r15
  const void *v92; // r9
  JET_ERR v93; // eax
  unsigned int v94; // eax
  int v95; // edx
  JET_TABLEID v96; // rdi
  JET_SESID v97; // rsi
  JET_COLUMNID v98; // ebx
  void *v99; // r9
  JET_ERR v100; // eax
  unsigned int v101; // eax
  int v102; // edx
  JET_TABLEID v103; // rdi
  JET_SESID v104; // rsi
  __int64 v105; // rcx
  JET_COLUMNID v106; // ebx
  JET_ERR v107; // eax
  unsigned int v108; // eax
  int v109; // edx
  JET_TABLEID v110; // r15
  JET_SESID v111; // r12
  unsigned __int64 *v112; // rbx
  unsigned int v113; // edi
  JET_COLUMNID v114; // esi
  JET_ERR v115; // eax
  unsigned int v116; // eax
  int v117; // edx
  JET_TABLEID v118; // rdi
  JET_SESID v119; // rsi
  __int64 v120; // rcx
  JET_COLUMNID v121; // ebx
  JET_ERR v122; // eax
  unsigned int v123; // eax
  JET_ERR v124; // eax
  JET_SESID v125; // rcx
  JET_ERR v126; // eax
  CContainerProps *v127; // rax
  __int64 v128; // rbx
  CJetContext *v129; // rdi
  unsigned __int64 v130; // rcx
  unsigned __int64 v131; // r9
  unsigned __int16 **v132; // rbx
  __int64 v133; // rbx
  CInFlightEntry *v134; // rbx
  __int64 v135; // rax
  int v136; // r15d
  __int64 v137; // rsi
  struct _RTL_CRITICAL_SECTION *v138; // r12
  int v139; // r13d
  __int64 v140; // rsi
  void *v141; // r8
  int v143; // edx
  LPCWSTR v144; // rdi
  char v145; // si
  char v146; // bl
  _OWORD *v147; // rdx
  char v148; // al
  JET_TABLEID v149; // rdx
  JET_SESID v150; // rcx
  JET_ERR v151; // eax
  int LastError; // eax
  char grbit; // [rsp+28h] [rbp-F8h]
  CJetContext *v156; // [rsp+B8h] [rbp-68h] BYREF
  unsigned int v157; // [rsp+C0h] [rbp-60h] BYREF
  int v158; // [rsp+C4h] [rbp-5Ch]
  int v159; // [rsp+C8h] [rbp-58h]
  int v160; // [rsp+CCh] [rbp-54h]
  LPCRITICAL_SECTION v161; // [rsp+D0h] [rbp-50h]
  void *v162; // [rsp+D8h] [rbp-48h]
  LPCWSTR lpFileName; // [rsp+E8h] [rbp-38h]
  void *v164; // [rsp+F0h] [rbp-30h]
  void *v165; // [rsp+F8h] [rbp-28h]
  void *v166; // [rsp+100h] [rbp-20h]
  RTL_SRWLOCK *v167; // [rsp+108h] [rbp-18h]
  unsigned __int16 **v168; // [rsp+110h] [rbp-10h]
  CInFlightEntry *v169; // [rsp+118h] [rbp-8h] BYREF
  unsigned int v170; // [rsp+120h] [rbp+0h] BYREF
  volatile signed __int32 *v171; // [rsp+128h] [rbp+8h] BYREF
  unsigned __int64 v172[2]; // [rsp+130h] [rbp+10h] BYREF
  char v173[8]; // [rsp+140h] [rbp+20h] BYREF
  char v174[8]; // [rsp+148h] [rbp+28h] BYREF
  LPCWSTR v175; // [rsp+150h] [rbp+30h] BYREF
  char v176[8]; // [rsp+158h] [rbp+38h] BYREF
  unsigned int v177; // [rsp+160h] [rbp+40h]
  int v178; // [rsp+164h] [rbp+44h]
  int v179; // [rsp+16Ch] [rbp+4Ch]
  unsigned __int64 v180; // [rsp+170h] [rbp+50h]
  FILETIME FileTime1; // [rsp+198h] [rbp+78h] BYREF
  char v182[16]; // [rsp+1A8h] [rbp+88h] BYREF
  char v183[24]; // [rsp+1B8h] [rbp+98h] BYREF
  unsigned __int64 *v184; // [rsp+1D0h] [rbp+B0h] BYREF
  unsigned int v185; // [rsp+1D8h] [rbp+B8h]
  char v186[16]; // [rsp+1E0h] [rbp+C0h] BYREF
  unsigned int v187; // [rsp+1F0h] [rbp+D0h] BYREF
  unsigned int v188; // [rsp+1F8h] [rbp+D8h] BYREF
  unsigned int v189; // [rsp+1FCh] [rbp+DCh] BYREF
  int v190; // [rsp+200h] [rbp+E0h] BYREF
  int v191; // [rsp+204h] [rbp+E4h] BYREF
  LPVOID lpMem; // [rsp+208h] [rbp+E8h] BYREF
  unsigned int v193; // [rsp+210h] [rbp+F0h] BYREF
  unsigned __int64 v194; // [rsp+218h] [rbp+F8h] BYREF
  unsigned __int64 v195; // [rsp+220h] [rbp+100h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+228h] [rbp+108h] BYREF
  FILETIME FileTime2; // [rsp+230h] [rbp+110h] BYREF
  __int64 v198; // [rsp+238h] [rbp+118h] BYREF
  struct _FILETIME v199; // [rsp+240h] [rbp+120h] BYREF
  struct _FILETIME v200; // [rsp+248h] [rbp+128h] BYREF
  __int64 v201; // [rsp+250h] [rbp+130h] BYREF
  __int128 FileInformation; // [rsp+258h] [rbp+138h] BYREF
  __int128 v203; // [rsp+268h] [rbp+148h]
  unsigned int v204; // [rsp+278h] [rbp+158h]
  _BYTE v205[36]; // [rsp+280h] [rbp+160h] BYREF

  v17 = a3;
  v18 = a2;
  v162 = a13;
  v165 = a11;
  lpFileName = a6;
  v166 = a7;
  v187 = a2;
  v19 = 0;
  v193 = a3;
  v168 = a16;
  v156 = 0;
  v160 = 0;
  v159 = 0;
  v194 = 0;
  v188 = 0;
  v198 = 0;
  v201 = 0;
  SystemTimeAsFileTime = 0;
  v195 = 0;
  v169 = 0;
  v189 = 0;
  v190 = 0;
  v157 = 0;
  v170 = 0;
  lpMem = 0;
  v200 = a8;
  FileTime2 = a9;
  v199 = a10;
  v204 = 0;
  FileInformation = 0;
  v191 = 1;
  v203 = 0;
  memset_0(v172, 0, 0xC0u);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
  {
    v23 = (WCHAR *)lpFileName;
    v24 = a4;
    grbit = v17;
    v25 = (CCacheContainer *)this;
    WPP_SF_qddSSSSiiiqdqddql(
      (_DWORD)j,
      v20,
      v22,
      (_DWORD)this,
      v18,
      grbit,
      (__int64)a4,
      (__int64)a5,
      (__int64)lpFileName,
      (__int64)v166,
      a8.dwLowDateTime,
      a9.dwLowDateTime,
      a10.dwLowDateTime,
      (__int64)v165,
      a12,
      (__int64)v162,
      a14,
      a15,
      (__int64)v168,
      a17);
  }
  else
  {
    v25 = (CCacheContainer *)this;
    v24 = a4;
    v23 = (WCHAR *)lpFileName;
  }
  v26 = 0;
  if ( v168 )
    *v168 = 0;
  v27 = (*((_BYTE *)v25 + 32) & 2) == 0;
  HIDWORD(v161) = 0;
  if ( v27 )
  {
    HIDWORD(v161) = 3123;
    updated = -2147024891;
    v50 = 0;
    goto LABEL_176;
  }
  updated = CContainerProps::UpdateLastAccessTime(*((CContainerProps **)v25 + 5));
  if ( updated < 0 )
  {
    v50 = 0;
    goto LABEL_176;
  }
  v164 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( v23 && *v23 )
  {
    v27 = (*((_BYTE *)v25 + 32) & 8) == 0;
    HIDWORD(v161) = 0;
    if ( v27 )
    {
      HIDWORD(v161) = 3123;
      updated = -2147024891;
      v50 = 0;
      goto LABEL_176;
    }
    if ( !GetFileAttributesExW(v23, GetFileExInfoStandard, &FileInformation) )
    {
      LastError = WxGetLastError();
      updated = LastError;
      if ( LastError > 0 )
        updated = (unsigned __int16)LastError | 0x80070000;
      v50 = 0;
      if ( updated >= 0 )
        updated = -2147418113;
      goto LABEL_176;
    }
    v198 = *(_QWORD *)((char *)&FileInformation + 4);
    v194 = v204 | ((unsigned __int64)HIDWORD(v203) << 32);
    if ( (v187 & 8) != 0 )
    {
      v164 = v23;
    }
    else
    {
      updated = CContainerProps::VerifyCacheEntryPath(*((CContainerProps **)v25 + 5), v23, &v170, &v188);
      if ( updated < 0 )
      {
        v50 = 0;
        goto LABEL_176;
      }
      v164 = &v23[v170];
    }
  }
  v29 = WxComputeUrlHash(v24);
  v30 = *((_QWORD *)v25 + 5);
  v31 = v29;
  v195 = v29;
  v32 = 0;
  v158 = 0;
  j = *(__int64 **)(v30 + 144);
  v167 = (RTL_SRWLOCK *)j;
  v33 = j[8];
  v161 = (LPCRITICAL_SECTION)(j + 2);
  if ( v33 != -8 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v33 + 8));
    v32 = 1;
  }
  v34 = *(char **)(v33 + 48);
  if ( v34 )
  {
    updated = 0;
    *(_QWORD *)(v33 + 48) = *((_QWORD *)v34 + 1);
    *((_QWORD *)v34 + 1) = 0;
  }
  else
  {
    v34 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x48u);
    if ( !v34 )
    {
      v34 = 0;
      updated = -2147024882;
      goto LABEL_13;
    }
    *(_QWORD *)v34 = 1;
    *(_QWORD *)(v34 + 28) = 0;
    *(_QWORD *)(v34 + 36) = 0;
    *(_QWORD *)(v34 + 44) = 0;
    *(_QWORD *)(v34 + 52) = 0;
    *(_QWORD *)(v34 + 60) = 0;
    *((_DWORD *)v34 + 17) = 0;
    *((_QWORD *)v34 + 1) = 0;
    *((_QWORD *)v34 + 2) = 0;
    *((_DWORD *)v34 + 6) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v34 + 32));
    updated = 0;
    *((_QWORD *)v34 + 1) = 0;
    ++*(_DWORD *)(v33 + 56);
  }
  ++*(_DWORD *)(v33 + 60);
LABEL_13:
  if ( v32 && v33 != -8 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v33 + 8));
  if ( updated < 0 )
    goto LABEL_231;
  *((_DWORD *)v34 + 6) = 0;
  *((_QWORD *)v34 + 2) = v31;
  v35 = v161;
  if ( v161 )
  {
    EnterCriticalSection(v161);
    v158 = 1;
  }
  v171 = (volatile signed __int32 *)v34;
  Ptr = (volatile signed __int32 *)v167[7].Ptr;
  _InterlockedIncrement(Ptr + 2);
  v37 = *(_QWORD *)Ptr;
  if ( *(_DWORD *)(*(_QWORD *)Ptr + 44LL) )
  {
    for ( i = *(__int64 **)(v37 + 16); ; i = (__int64 *)i[2] )
    {
      while ( 1 )
      {
        v39 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 **, __int64 *))(v37 + 72))(v37, &v171, i + 4);
        if ( v39 )
          break;
        if ( !i[1] )
        {
          v40 = 2;
          goto LABEL_25;
        }
        i = (__int64 *)i[1];
      }
      if ( v39 != 1 )
      {
        v40 = 1;
        v42 = i;
        goto LABEL_29;
      }
      if ( !i[2] )
        break;
    }
    v40 = 3;
  }
  else
  {
    i = 0;
    v40 = 0;
  }
LABEL_25:
  v41 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, __int64))(v37 + 80))(v37, 40);
  v42 = v41;
  if ( !v41 )
    goto LABEL_257;
  *v41 = 0;
  v41[1] = 0;
  ++*(_DWORD *)(v37 + 44);
  if ( v40 )
  {
    v147 = v41;
    if ( v40 == 2 )
      i[1] = (__int64)v41;
    else
      i[2] = (__int64)v41;
    *(_QWORD *)v41 = i;
    v22 = 1;
    *(_BYTE *)(v37 + 24) = -1;
    for ( j = *(__int64 **)v41; ; i = j )
    {
      v27 = j[1] == (_QWORD)v147;
      v148 = -1;
      LODWORD(j) = *((unsigned __int8 *)i + 24);
      if ( !v27 )
        v148 = 1;
      if ( (_BYTE)j )
        break;
      j = (__int64 *)*i;
      v147 = i;
      *((_BYTE *)i + 24) = v148;
    }
    if ( (_BYTE)j == v148 )
    {
      RebalanceNode((struct _WX_BALANCED_LINKS *)i);
    }
    else
    {
      *((_BYTE *)i + 24) = 0;
      if ( !*(_BYTE *)(v37 + 24) )
        ++*(_DWORD *)(v37 + 48);
    }
  }
  else
  {
    *(_QWORD *)(v37 + 16) = v41;
    *(_QWORD *)v41 = v37;
    *(_DWORD *)(v37 + 48) = 1;
  }
  v35 = v161;
  *((_QWORD *)v42 + 4) = v171;
LABEL_29:
  v43 = (volatile signed __int32 **)(v42 + 2);
  if ( !v43 )
  {
LABEL_257:
    updated = -2147024882;
LABEL_231:
    v45 = v167;
    goto LABEL_38;
  }
  if ( v40 == 1 )
  {
    _InterlockedIncrement(*v43);
    v44 = *v43;
    updated = 1;
  }
  else
  {
    _InterlockedIncrement(v171);
    _InterlockedIncrement(*v43);
    v44 = *v43;
    updated = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v34, 0xFFFFFFFF) == 1 )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)(v34 + 32));
      operator delete(v34, 0x48u);
    }
    v34 = 0;
  }
  ++*((_DWORD *)v44 + 6);
  if ( v35 && v158 )
  {
    LeaveCriticalSection(v35);
    v158 = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v44 + 8));
  v45 = v167;
  AcquireSRWLockShared(v167 + 1);
  v169 = (CInFlightEntry *)v44;
LABEL_38:
  if ( v34 )
  {
    v46 = (char *)v45[8].Ptr;
    v47 = 0;
    *((_QWORD *)v34 + 1) = 0;
    if ( v46 != (char *)-8LL )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v46 + 8));
      v47 = 1;
    }
    --*((_DWORD *)v46 + 15);
    LODWORD(j) = *((_DWORD *)v46 + 14);
    if ( (unsigned int)((_DWORD)j - *((_DWORD *)v46 + 15)) > *((_DWORD *)v46 + 16) )
    {
      *((_DWORD *)v46 + 14) = (_DWORD)j - 1;
      CInFlightEntry::Release((CInFlightEntry *)v34);
      if ( v47 && v46 != (char *)-8LL )
        goto LABEL_44;
    }
    else
    {
      *((_QWORD *)v34 + 1) = *((_QWORD *)v46 + 6);
      *((_QWORD *)v46 + 6) = v34;
      if ( v47 && v46 != (char *)-8LL )
LABEL_44:
        LeaveCriticalSection((LPCRITICAL_SECTION)(v46 + 8));
    }
  }
  if ( v158 && v161 )
    LeaveCriticalSection(v161);
  v25 = (CCacheContainer *)this;
  if ( updated < 0 )
  {
    v50 = 0;
    v26 = 0;
    goto LABEL_176;
  }
  v48 = CJetContextList::AcquireContext(*((CJetContextList **)this[5] + 19), &v156, 0);
  v50 = v156;
  v26 = 0;
  updated = v48;
  if ( v48 < 0 )
    goto LABEL_176;
  HIDWORD(v156) = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qdSD((_DWORD)j, v49, v22, (_DWORD)v50, 0, (__int64)L"HashEntryIdIndex", 0);
  if ( *((_DWORD *)v50 + 12) )
  {
    v149 = *((_QWORD *)v50 + 4);
    v150 = *((_QWORD *)v50 + 2);
    *((_DWORD *)v50 + 12) = -1;
    v151 = JetSetCurrentIndex2W(v150, v149, L"HashEntryIdIndex", 0);
    updated = HRESULTFromJET_ERR(v151, 1);
    if ( updated >= 0 )
      *((_DWORD *)v50 + 12) = 0;
  }
  else
  {
    updated = 0;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 14, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)updated);
  if ( updated < 0 )
    goto LABEL_176;
  v51 = JetBeginTransaction(*((_QWORD *)v50 + 2));
  v52 = a4;
  updated = HRESULTFromJET_ERR(v51, 1);
  if ( updated >= 0 )
  {
    v189 = a15;
    v160 = 1;
    v53 = SeekToEntry(v50, a4, v195);
    updated = v53;
    if ( v53 >= 0 )
    {
      v54 = 0;
      if ( !v53 )
      {
        updated = GetEntryFixedInfoAtCursor(
                    *((_QWORD *)v50 + 2),
                    *((_QWORD *)v50 + 4),
                    *(unsigned int **)(*((_QWORD *)v50 + 5) + 8LL),
                    (struct ENTRY_INFO *)v172);
        if ( updated < 0 )
          goto LABEL_176;
        v19 = (volatile signed __int32 *)*((_QWORD *)this[5] + 17);
        if ( v19 )
          _InterlockedIncrement(v19 + 4);
        updated = CAggregateLocks::GetLockCount((CAggregateLocks *)v19, v172[0], &v157);
        if ( updated < 0 )
          goto LABEL_176;
        if ( v157 )
        {
          updated = -2147024864;
          goto LABEL_176;
        }
        updated = GetEntryFilenameGroupInfoAtCursor(
                    *((_QWORD *)v50 + 2),
                    *((_QWORD *)v50 + 4),
                    *(unsigned int **)(*((_QWORD *)v50 + 5) + 8LL),
                    (struct ENTRY_INFO *)v172);
        if ( updated < 0 )
          goto LABEL_176;
        if ( a17 && CompareFileTime(&FileTime1, &FileTime2) > 0 )
        {
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_(1036, 21, &WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids);
          DeleteFileW(lpFileName);
          DeleteRoamingData(lpFileName);
          updated = -2147024864;
          goto LABEL_176;
        }
        v144 = v175;
        v145 = v178;
        v146 = v187;
        v191 = v179 + 1;
        v189 = 0;
        HIDWORD(v156) = 0;
        memset(v205, 0, sizeof(v205));
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_ddS((_DWORD)j, v143, v22, v187, v178, (__int64)v175);
        if ( (v146 & 8) == 0
          && (v145 & 8) != 0
          && v144
          && *v144
          && GetFileAttributesExW(v144, GetFileExInfoStandard, v205)
          && *(_QWORD *)&v205[28] )
        {
          updated = -2147024864;
          HIDWORD(v156) = 367;
        }
        else
        {
          updated = 0;
        }
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_d(1036, 17, &WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, (unsigned int)updated);
        if ( updated < 0 )
          goto LABEL_176;
        v54 = 2;
      }
      if ( (v187 & 4) != 0 )
        v190 = 86400;
      v55 = JetPrepareUpdate(*((_QWORD *)v50 + 2), *((_QWORD *)v50 + 4), v54);
      updated = HRESULTFromJET_ERR(v55, 1);
      if ( updated < 0 )
        goto LABEL_176;
      v159 = 1;
      if ( !v54 )
      {
        v56 = *((_QWORD *)v50 + 4);
        cbData = 0;
        v58 = *((_QWORD *)v50 + 2);
        v59 = *(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL);
        v60 = *(_DWORD *)(v59 + 16);
        HIDWORD(v156) = 0;
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_iiiS(v59, 0, (_DWORD)a4, v58, v56, v60, (__int64)a4);
        if ( a4 )
        {
          v61 = -1;
          do
            v27 = a4[++v61] == 0;
          while ( !v27 );
          cbData = 2 * v61 + 2;
        }
        v62 = JetSetColumn(v58, v56, v60, a4, cbData, 0, 0);
        v63 = HRESULTFromJET_ERR(v62, 1);
        updated = v63;
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_d(1036, 19, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v63);
        v26 = 0;
        if ( updated < 0 )
          goto LABEL_176;
        updated = JetSetColumn(
                    *((_QWORD *)v50 + 2),
                    *((_QWORD *)v50 + 4),
                    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 12LL),
                    &v195,
                    8u,
                    0,
                    0);
        if ( updated < 0 )
          goto LABEL_176;
        v64 = *((_QWORD *)this[5] + 24);
        if ( v64 )
        {
          v65 = 0;
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_qSq(1036, 22, (unsigned int)&WPP_fd8c4a12b4fc3ea928353dabf2ce535f_Traceguids, v64, (__int64)a4, 0);
          v66 = a4;
          v67 = 0;
          v68 = a4;
          v69 = 0;
          if ( a4 )
          {
            do
            {
              v67 = dword_180226530[(unsigned __int64)*v68 >> 8]
                  ^ __ROL4__(dword_180226530[(unsigned __int8)*v68] ^ __ROL4__(v67, 1), 1);
              if ( !*v68 )
                break;
              ++v68;
              ++v69;
            }
            while ( v69 != -1 );
          }
          v70 = *a4;
          v71 = 5381;
          LODWORD(v156) = v67;
          if ( v70 )
          {
            v72 = a4;
            do
            {
              ++v72;
              v71 = v70 ^ (33 * v71);
              v70 = *v72;
            }
            while ( *v72 );
          }
          HIDWORD(v156) = v71;
          if ( v64 != -16 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(v64 + 16));
            v66 = a4;
            v65 = 1;
          }
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_S(1036, 24, &WPP_fd8c4a12b4fc3ea928353dabf2ce535f_Traceguids, v66);
          WxBloomFilterAddPreHashedMember(
            (const struct WxBloomEntryHashes *)&v156,
            *(unsigned __int8 **)(v64 + 64),
            *(_DWORD *)(v64 + 84),
            *(_DWORD *)(v64 + 88));
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_(1036, 25, &WPP_fd8c4a12b4fc3ea928353dabf2ce535f_Traceguids);
          if ( v65 && v64 != -16 )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v64 + 16));
        }
      }
      updated = JetSetColumn(
                  *((_QWORD *)v50 + 2),
                  *((_QWORD *)v50 + 4),
                  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 4LL),
                  this + 3,
                  8u,
                  0,
                  0);
      if ( updated >= 0 )
      {
        updated = JetSetColumn(
                    *((_QWORD *)v50 + 2),
                    *((_QWORD *)v50 + 4),
                    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 8LL),
                    &v201,
                    8u,
                    0,
                    0);
        if ( updated >= 0 )
        {
          v73 = *((_QWORD *)v50 + 4);
          v74 = 0;
          v75 = *((_QWORD *)v50 + 2);
          v76 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 20LL);
          HIDWORD(v156) = 0;
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_iiiS((_DWORD)v164, 0, v22, v75, v73, v76, (__int64)v164);
          if ( v164 )
          {
            v77 = -1;
            do
              v27 = *((_WORD *)v164 + ++v77) == 0;
            while ( !v27 );
            v74 = 2 * v77 + 2;
          }
          v78 = JetSetColumn(v75, v73, v76, v164, v74, 0, 0);
          v79 = HRESULTFromJET_ERR(v78, 1);
          updated = v79;
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_d(1036, 19, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v79);
          if ( updated < 0 )
          {
            v26 = 0;
          }
          else
          {
            v80 = *((_QWORD *)v50 + 4);
            v81 = 0;
            v82 = *((_QWORD *)v50 + 2);
            v83 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 28LL);
            HIDWORD(v156) = 0;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_iiiS((_DWORD)v166, 0, v22, v82, v80, v83, (__int64)v166);
            if ( v166 )
            {
              v84 = -1;
              do
                v27 = *((_WORD *)v166 + ++v84) == 0;
              while ( !v27 );
              v81 = 2 * v84 + 2;
            }
            v85 = JetSetColumn(v82, v80, v83, v166, v81, 0, 0);
            v86 = HRESULTFromJET_ERR(v85, 1);
            updated = v86;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 19, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v86);
            v26 = 0;
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v50 + 2),
                        *((_QWORD *)v50 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 24LL),
                        &v188,
                        4u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v50 + 2),
                        *((_QWORD *)v50 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 32LL),
                        &v194,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            v88 = *((_QWORD *)v50 + 4);
            v89 = *((_QWORD *)v50 + 2);
            v90 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 36LL);
            HIDWORD(v166) = 0;
            v91 = v165;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_iiiqd(a12, v87, v22, v89, v88, v90, (__int64)v165);
            v92 = 0;
            if ( a12 )
              v92 = v91;
            v26 = 0;
            v93 = JetSetColumn(v89, v88, v90, v92, a12, 0, 0);
            v94 = HRESULTFromJET_ERR(v93, 1);
            updated = v94;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 21, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v94);
            if ( updated < 0 )
              goto LABEL_176;
            v96 = *((_QWORD *)v50 + 4);
            v97 = *((_QWORD *)v50 + 2);
            v98 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 40LL);
            HIDWORD(v165) = 0;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_iiiqd((_DWORD)v162, v95, v22, v97, v96, v98, (__int64)v162);
            v99 = 0;
            if ( a14 )
              v99 = v162;
            v100 = JetSetColumn(v97, v96, v98, v99, a14, 0, 0);
            v101 = HRESULTFromJET_ERR(v100, 1);
            updated = v101;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 21, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v101);
            if ( updated < 0 )
              goto LABEL_176;
            v103 = *((_QWORD *)v50 + 4);
            v104 = *((_QWORD *)v50 + 2);
            v105 = *(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL);
            v106 = *(_DWORD *)(v105 + 44);
            HIDWORD(v162) = 0;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_iiiS(v105, v102, v22, v104, v103, v106, 0);
            v107 = JetSetColumn(v104, v103, v106, 0, 0, 0, 0);
            v108 = HRESULTFromJET_ERR(v107, 1);
            updated = v108;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 19, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v108);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v50 + 2),
                        *((_QWORD *)v50 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 48LL),
                        &v187,
                        4u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v50 + 2),
                        *((_QWORD *)v50 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 52LL),
                        &v193,
                        4u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v50 + 2),
                        *((_QWORD *)v50 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 56LL),
                        &v191,
                        4u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v50 + 2),
                        *((_QWORD *)v50 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 60LL),
                        &SystemTimeAsFileTime,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v50 + 2),
                        *((_QWORD *)v50 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 64LL),
                        &v198,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v50 + 2),
                        *((_QWORD *)v50 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 68LL),
                        &v200,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v50 + 2),
                        *((_QWORD *)v50 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 72LL),
                        &FileTime2,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v50 + 2),
                        *((_QWORD *)v50 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 76LL),
                        &SystemTimeAsFileTime,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v50 + 2),
                        *((_QWORD *)v50 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 80LL),
                        &v199,
                        8u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v50 + 2),
                        *((_QWORD *)v50 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 84LL),
                        &v189,
                        4u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            updated = JetSetColumn(
                        *((_QWORD *)v50 + 2),
                        *((_QWORD *)v50 + 4),
                        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 88LL),
                        &v190,
                        4u,
                        0,
                        0);
            if ( updated < 0 )
              goto LABEL_176;
            v110 = *((_QWORD *)v50 + 4);
            v111 = *((_QWORD *)v50 + 2);
            v112 = v184;
            v113 = 8 * v185;
            v114 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL) + 92LL);
            HIDWORD(v162) = 0;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_iiiqd(0, v109, v22, v111, v110, v114, (__int64)v184);
            if ( !v113 )
              v112 = 0;
            v115 = JetSetColumn(v111, v110, v114, v112, v113, 0, 0);
            v116 = HRESULTFromJET_ERR(v115, 1);
            updated = v116;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 21, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v116);
            v26 = 0;
            if ( updated < 0 )
              goto LABEL_348;
            v118 = *((_QWORD *)v50 + 4);
            v119 = *((_QWORD *)v50 + 2);
            v120 = *(_QWORD *)(*((_QWORD *)v50 + 5) + 8LL);
            v121 = *(_DWORD *)(v120 + 96);
            HIDWORD(v162) = 0;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_iiiqd(v120, v117, v22, v119, v118, v121, 0);
            v122 = JetSetColumn(v119, v118, v121, 0, 0, 0, 0);
            v123 = HRESULTFromJET_ERR(v122, 1);
            updated = v123;
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 21, &WPP_70a08f364de0374d8b8fa0ef849ee242_Traceguids, v123);
            if ( updated < 0
              || (v124 = JetUpdate(*((_QWORD *)v50 + 2), *((_QWORD *)v50 + 4), 0, 0, 0),
                  updated = HRESULTFromJET_ERR(v124, 1),
                  updated < 0) )
            {
LABEL_348:
              v25 = (CCacheContainer *)this;
            }
            else
            {
              v125 = *((_QWORD *)v50 + 2);
              v159 = 0;
              v126 = JetCommitTransaction(v125, 1u);
              v25 = (CCacheContainer *)this;
              updated = HRESULTFromJET_ERR(v126, 1);
              if ( updated >= 0 )
              {
                v127 = this[5];
                v160 = 0;
                if ( *((_DWORD *)v127 + 56) )
                {
                  if ( !a17 )
                  {
                    v52 = a4;
                    updated = WriteRoamingData(
                                lpFileName,
                                v187,
                                v193,
                                a4,
                                (union FILETIMEEX *)&v200,
                                (union FILETIMEEX *)&FileTime2,
                                (union FILETIMEEX *)&v199,
                                *((_DWORD *)v127 + 58));
                    if ( updated < 0 )
                      goto LABEL_177;
                  }
                }
                v128 = *((_QWORD *)this[5] + 19);
                CCacheStore::EndActivity(*(CCacheStore **)(v128 + 80));
                v129 = v50;
                if ( !v50 )
                  goto LABEL_160;
                v50 = 0;
                *((_QWORD *)v129 + 1) = 0;
                if ( v128 != -8 )
                {
                  EnterCriticalSection((LPCRITICAL_SECTION)(v128 + 8));
                  v26 = 1;
                }
                --*(_DWORD *)(v128 + 60);
                if ( (unsigned int)(*(_DWORD *)(v128 + 56) - *(_DWORD *)(v128 + 60)) > *(_DWORD *)(v128 + 64) )
                {
                  --*(_DWORD *)(v128 + 56);
                  CJetContext::Release(v129);
                  if ( !v26 || v128 == -8 )
                    goto LABEL_256;
                }
                else
                {
                  *((_QWORD *)v129 + 1) = *(_QWORD *)(v128 + 48);
                  *(_QWORD *)(v128 + 48) = v129;
                  if ( !v26 || v128 == -8 )
                    goto LABEL_256;
                }
                LeaveCriticalSection((LPCRITICAL_SECTION)(v128 + 8));
LABEL_256:
                v26 = 0;
LABEL_160:
                CInFlightLocks::ReleaseLock(*((CInFlightLocks **)this[5] + 18), &v169);
                if ( lpFileName && *lpFileName && (v187 & 8) == 0 )
                {
                  v130 = v194;
                }
                else
                {
                  v130 = 0;
                  v194 = 0;
                }
                if ( v175 && *v175 && (v178 & 8) == 0 )
                {
                  v131 = v180;
                }
                else
                {
                  v131 = 0;
                  v180 = 0;
                }
                updated = CContainerProps::AdjustContainerUsage(this[5], v184, v185, v131, v177, v130, v188);
                if ( updated >= 0 )
                {
                  v132 = v168;
                  if ( !v168
                    || !lpFileName
                    || !*lpFileName
                    || (updated = CContainerProps::GetNextDirectoryAsCaller(this[5], (unsigned __int16 **)&lpMem),
                        updated >= 0) )
                  {
                    if ( v188 == v177 && v164 && v175 && !(unsigned int)_o__wcsicmp(v164, v175)
                      || (updated = CContainerProps::DeleteEntryFile(this[5], (struct ENTRY_INFO *)v172, 0, 1, 1, 1),
                          updated >= 0) )
                    {
                      if ( v132 && lpMem )
                      {
                        *v132 = (unsigned __int16 *)lpMem;
                        lpMem = 0;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
LABEL_176:
      v52 = a4;
    }
  }
LABEL_177:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_ISDD((_DWORD)j, 22, v22, *((_QWORD *)v25 + 3), (__int64)v52, a14, updated);
  if ( v159 )
    JetPrepareUpdate(*((_QWORD *)v50 + 2), *((_QWORD *)v50 + 4), 3u);
  if ( v160 )
    JetRollback(*((_QWORD *)v50 + 2), 0);
  v133 = *(_QWORD *)(*((_QWORD *)v25 + 5) + 152LL);
  if ( v50 )
  {
    CCacheStore::EndActivity(*(CCacheStore **)(v133 + 80));
    *((_QWORD *)v50 + 1) = 0;
    if ( v133 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v133 + 8));
      v26 = 1;
    }
    --*(_DWORD *)(v133 + 60);
    if ( (unsigned int)(*(_DWORD *)(v133 + 56) - *(_DWORD *)(v133 + 60)) > *(_DWORD *)(v133 + 64) )
    {
      --*(_DWORD *)(v133 + 56);
      CJetContext::Release(v50);
      if ( v26 && v133 != -8 )
        goto LABEL_213;
    }
    else
    {
      *((_QWORD *)v50 + 1) = *(_QWORD *)(v133 + 48);
      *(_QWORD *)(v133 + 48) = v50;
      if ( v26 && v133 != -8 )
LABEL_213:
        LeaveCriticalSection((LPCRITICAL_SECTION)(v133 + 8));
    }
  }
  v134 = v169;
  if ( !v169 )
    goto LABEL_199;
  v135 = *((_QWORD *)v25 + 5);
  v136 = 0;
  v157 = 0;
  v137 = *(_QWORD *)(v135 + 144);
  v138 = (struct _RTL_CRITICAL_SECTION *)(v137 + 16);
  ReleaseSRWLockShared((PSRWLOCK)(v137 + 8));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v134 + 32));
  if ( v137 != -16 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v137 + 16));
    v136 = 1;
    v157 = 1;
  }
  v27 = (*((_DWORD *)v134 + 6))-- == 1;
  if ( v27 )
  {
    CWxRefMap<CInFlightMap,CInFlightEntry>::Delete(*(_QWORD *)(v137 + 56), v134);
    *((_QWORD *)v134 + 2) = 0;
    v139 = 0;
    v140 = *(_QWORD *)(v137 + 64);
    *((_QWORD *)v134 + 1) = 0;
    if ( v140 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v140 + 8));
      v139 = 1;
    }
    --*(_DWORD *)(v140 + 60);
    if ( (unsigned int)(*(_DWORD *)(v140 + 56) - *(_DWORD *)(v140 + 60)) > *(_DWORD *)(v140 + 64) )
    {
      --*(_DWORD *)(v140 + 56);
      CInFlightEntry::Release(v134);
      if ( v139 && v140 != -8 )
        goto LABEL_194;
    }
    else
    {
      *((_QWORD *)v134 + 1) = *(_QWORD *)(v140 + 48);
      *(_QWORD *)(v140 + 48) = v134;
      if ( v139 && v140 != -8 )
LABEL_194:
        LeaveCriticalSection((LPCRITICAL_SECTION)(v140 + 8));
    }
    if ( !v157 || !v138 )
      goto LABEL_198;
    goto LABEL_197;
  }
  CInFlightEntry::Release(v134);
  if ( !v136 || v137 == -16 )
    goto LABEL_198;
LABEL_197:
  LeaveCriticalSection(v138);
LABEL_198:
  v25 = (CCacheContainer *)this;
LABEL_199:
  WxHeapFree<_WX_AVL_TABLE>(v173);
  WxHeapFree<_WX_AVL_TABLE>(v174);
  WxHeapFree<_WX_AVL_TABLE>(&v175);
  WxHeapFree<_WX_AVL_TABLE>(v176);
  WxHeapFree<_WX_AVL_TABLE>(v182);
  WxHeapFree<_WX_AVL_TABLE>(v183);
  WxHeapFree<unsigned __int64>(&v184);
  WxHeapFree<_WX_AVL_TABLE>(v186);
  memset_0(v172, 0, 0xC0u);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qD(1036, 23, &WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, v25, updated);
  v141 = lpMem;
  if ( lpMem )
  {
    lpMem = 0;
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v141);
    else
      HeapFree(g_hWxProcessHeap, 0, v141);
  }
  if ( v19 && _InterlockedExchangeAdd(v19 + 4, 0xFFFFFFFF) == 1 )
  {
    CAggregateLocks::~CAggregateLocks((CAggregateLocks *)v19);
    operator delete((void *)v19, 0x48u);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18007c810  push    rbp
0x18007c812  push    rbx
0x18007c813  push    rsi
0x18007c814  push    rdi
0x18007c815  push    r12
0x18007c817  push    r13
0x18007c819  push    r14
0x18007c81b  push    r15
0x18007c81d  lea     rbp, [rsp-198h]
0x18007c825  sub     rsp, 2B8h
0x18007c82c  mov     rax, cs:__security_cookie
0x18007c833  xor     rax, rsp
0x18007c836  mov     [rbp+1D0h+var_48], rax
0x18007c83d  mov     rax, [rbp+1D0h+arg_60]
0x18007c844  xorps   xmm0, xmm0
0x18007c847  mov     rbx, qword ptr [rbp+1D0h+arg_38.dwLowDateTime]
0x18007c84e  mov     r12d, r8d
0x18007c851  mov     rdi, qword ptr [rbp+1D0h+arg_40.dwLowDateTime]
0x18007c858  mov     r15d, edx
0x18007c85b  mov     rsi, qword ptr [rbp+1D0h+arg_48.dwLowDateTime]
0x18007c862  mov     r13, [rbp+1D0h+arg_20]
0x18007c869  mov     [rbp+1D0h+var_218], rax
0x18007c86d  mov     rax, [rbp+1D0h+arg_50]
0x18007c874  mov     [rbp+1D0h+var_1F8], rax
0x18007c878  mov     rax, [rbp+1D0h+arg_28]
0x18007c87f  mov     [rbp+1D0h+lpFileName], rax
0x18007c883  mov     rax, [rbp+1D0h+arg_30]
0x18007c88a  mov     [rbp+1D0h+var_1F0], rax
0x18007c88e  mov     rax, [rbp+1D0h+arg_78]
0x18007c895  mov     [rbp+1D0h+var_240], rcx
0x18007c899  xor     ecx, ecx
0x18007c89b  mov     [rbp+1D0h+var_100], edx
0x18007c8a1  mov     r14d, ecx
0x18007c8a4  mov     [rbp+1D0h+var_E0], r8d
0x18007c8ab  xor     edx, edx; Val
0x18007c8ad  mov     [rbp+1D0h+var_1E0], rax
0x18007c8b1  mov     r8d, 0C0h; Size
0x18007c8b7  xor     eax, eax
0x18007c8b9  mov     [rbp+1D0h+var_238], rcx
0x18007c8bd  mov     [rbp+1D0h+var_224], ecx
0x18007c8c0  mov     [rbp+1D0h+var_228], ecx
0x18007c8c3  mov     [rbp+1D0h+var_D8], rcx
0x18007c8ca  mov     [rbp+1D0h+var_F8], ecx
0x18007c8d0  mov     [rbp+1D0h+var_B8], rcx
0x18007c8d7  mov     [rbp+1D0h+var_A0], rcx
0x18007c8de  mov     qword ptr [rbp+1D0h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18007c8e5  mov     [rbp+1D0h+var_D0], rcx
0x18007c8ec  mov     [rbp+1D0h+var_1D8], rcx
0x18007c8f0  mov     [rbp+1D0h+var_F4], ecx
0x18007c8f6  mov     [rbp+1D0h+var_F0], ecx
0x18007c8fc  mov     [rbp+1D0h+var_230], ecx
0x18007c8ff  mov     [rbp+1D0h+var_1D0], ecx
0x18007c902  mov     [rbp+1D0h+lpMem], rcx
0x18007c909  mov     [rbp+1D0h+var_A8], rbx
0x18007c910  mov     qword ptr [rbp+1D0h+FileTime2.dwLowDateTime], rdi
0x18007c917  mov     [rbp+1D0h+var_B0], rsi
0x18007c91e  mov     [rbp+1D0h+var_244], ecx
0x18007c921  lea     rcx, [rbp+1D0h+var_1C0]; void *
0x18007c925  mov     [rbp+1D0h+var_78], eax
0x18007c92b  mov     [rbp+1D0h+pvData], r9
0x18007c92f  movups  [rbp+1D0h+FileInformation], xmm0
0x18007c936  mov     [rbp+1D0h+var_EC], 1
0x18007c940  movups  [rbp+1D0h+var_88], xmm0
0x18007c947  call    memset_0
0x18007c94c  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18007c953  jz      loc_18007DDA8
0x18007c959  mov     eax, [rbp+1D0h+arg_80]
0x18007c95f  mov     [rsp+2F0h+var_258], eax
0x18007c966  mov     rax, [rbp+1D0h+var_1E0]
0x18007c96a  mov     [rsp+2F0h+var_260], rax
0x18007c972  mov     eax, [rbp+1D0h+arg_70]
0x18007c978  mov     [rsp+2F0h+var_268], eax
0x18007c97f  mov     eax, [rbp+1D0h+arg_68]
0x18007c985  mov     [rsp+2F0h+var_270], eax
0x18007c98c  mov     rax, [rbp+1D0h+var_218]
0x18007c990  mov     [rsp+2F0h+var_278], rax
0x18007c995  mov     eax, [rbp+1D0h+arg_58]
0x18007c99b  mov     [rsp+2F0h+var_280], eax
0x18007c99f  mov     rax, [rbp+1D0h+var_1F8]
0x18007c9a3  mov     [rsp+2F0h+var_288], rax
0x18007c9a8  mov     rax, [rbp+1D0h+var_1F0]
0x18007c9ac  mov     [rsp+2F0h+var_290], rsi
0x18007c9b1  mov     rsi, [rbp+1D0h+lpFileName]
0x18007c9b5  mov     [rsp+2F0h+var_298], rdi
0x18007c9ba  mov     [rsp+2F0h+var_2A0], rbx
0x18007c9bf  mov     rbx, [rbp+1D0h+pvData]
0x18007c9c3  mov     [rsp+2F0h+var_2A8], rax
0x18007c9c8  mov     [rsp+2F0h+var_2B0], rsi
0x18007c9cd  mov     qword ptr [rsp+2F0h+var_2B8], r13
0x18007c9d2  mov     [rsp+2F0h+psetinfo], rbx
0x18007c9d7  mov     [rsp+2F0h+grbit], r12d
0x18007c9dc  mov     r12, [rbp+1D0h+var_240]
0x18007c9e0  mov     r9, r12
0x18007c9e3  mov     [rsp+2F0h+cbData], r15d
0x18007c9e8  call    WPP_SF_qddSSSSiiiqdqddql
0x18007c9ed  mov     rax, [rbp+1D0h+var_1E0]
0x18007c9f1  xor     r15d, r15d
0x18007c9f4  test    rax, rax
0x18007c9f7  jz      short loc_18007C9FC
0x18007c9f9  mov     [rax], r15
0x18007c9fc  test    byte ptr [r12+20h], 2
0x18007ca02  mov     [rbp+1D0h+var_21C], r15d
0x18007ca06  jz      loc_18007E2DC
0x18007ca0c  mov     rcx, [r12+28h]; this
0x18007ca11  call    ?UpdateLastAccessTime@CContainerProps@@QEAAJXZ; CContainerProps::UpdateLastAccessTime(void)
0x18007ca16  mov     edi, eax
0x18007ca18  test    eax, eax
0x18007ca1a  js      loc_18007E200
0x18007ca20  lea     rcx, [rbp+1D0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18007ca27  mov     [rbp+1D0h+var_200], r15
0x18007ca2b  call    cs:__imp_GetSystemTimeAsFileTime
0x18007ca31  test    rsi, rsi
0x18007ca34  jnz     loc_18007DE12
0x18007ca3a  mov     rcx, rbx
0x18007ca3d  call    WxComputeUrlHash
0x18007ca42  mov     rcx, [r12+28h]
0x18007ca47  mov     r13, rax
0x18007ca4a  mov     [rbp+1D0h+var_D0], rax
0x18007ca51  mov     r12d, r15d
0x18007ca54  mov     [rbp+1D0h+var_22C], r15d
0x18007ca58  mov     rcx, [rcx+90h]
0x18007ca5f  mov     [rbp+1D0h+var_1E8], rcx
0x18007ca63  mov     [rbp+1D0h+var_244], r15d
0x18007ca67  mov     rbx, [rcx+40h]
0x18007ca6b  lea     rax, [rcx+10h]
0x18007ca6f  mov     [rbp-50h], rax
0x18007ca73  lea     rsi, [rbx+8]
0x18007ca77  test    rsi, rsi
0x18007ca7a  jz      short loc_18007CA8B
0x18007ca7c  mov     rcx, rsi; lpCriticalSection
0x18007ca7f  call    cs:__imp_EnterCriticalSection
0x18007ca85  mov     r12d, 1
0x18007ca8b  mov     r15, [rbx+30h]
0x18007ca8f  test    r15, r15
0x18007ca92  jz      loc_18007DF7D
0x18007ca98  mov     rax, [r15+8]
0x18007ca9c  xor     edi, edi
0x18007ca9e  mov     [rbx+30h], rax
0x18007caa2  mov     [r15+8], rdi
0x18007caa6  inc     dword ptr [rbx+3Ch]
0x18007caa9  test    r12d, r12d
0x18007caac  jz      short loc_18007CABC
0x18007caae  test    rsi, rsi
0x18007cab1  jz      short loc_18007CABC
0x18007cab3  mov     rcx, rsi; lpCriticalSection
0x18007cab6  call    cs:__imp_LeaveCriticalSection
0x18007cabc  test    edi, edi
0x18007cabe  js      loc_18007DD98
0x18007cac4  mov     [r15+18h], r14d
0x18007cac8  mov     [r15+10h], r13
0x18007cacc  mov     r13, [rbp-50h]
0x18007cad0  test    r13, r13
0x18007cad3  jz      short loc_18007CAE5
0x18007cad5  mov     rcx, r13; lpCriticalSection
0x18007cad8  call    cs:__imp_EnterCriticalSection
0x18007cade  mov     [rbp+1D0h+var_22C], 1
0x18007cae5  mov     rax, [rbp+1D0h+var_1E8]
0x18007cae9  mov     [rbp+1D0h+var_1C8], r15
0x18007caed  mov     rax, [rax+38h]
0x18007caf1  lock inc dword ptr [rax+8]
0x18007caf5  mov     rdi, [rax]
0x18007caf8  cmp     [rdi+2Ch], r14d
0x18007cafc  jz      short loc_18007CB33
0x18007cafe  mov     rsi, [rdi+10h]
0x18007cb02  mov     rax, [rdi+48h]
0x18007cb06  lea     r8, [rsi+20h]
0x18007cb0a  lea     rdx, [rbp+1D0h+var_1C8]
0x18007cb0e  mov     rcx, rdi
0x18007cb11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb16  test    eax, eax
0x18007cb18  jnz     loc_18007D9AE
0x18007cb1e  mov     rax, [rsi+8]
0x18007cb22  test    rax, rax
0x18007cb25  jnz     loc_18007DC7F
0x18007cb2b  mov     r12d, 2
0x18007cb31  jmp     short loc_18007CB38
0x18007cb33  xor     esi, esi
0x18007cb35  xor     r12d, r12d
0x18007cb38  mov     rax, [rdi+50h]
0x18007cb3c  mov     edx, 28h ; '('
0x18007cb41  mov     rcx, rdi
0x18007cb44  mov     r13d, 10h
0x18007cb4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cb4f  mov     rbx, rax
0x18007cb52  test    rax, rax
0x18007cb55  jz      loc_18007DF22
0x18007cb5b  xorps   xmm0, xmm0
0x18007cb5e  movups  xmmword ptr [rax], xmm0
0x18007cb61  movups  xmmword ptr [rax+10h], xmm0
0x18007cb65  inc     dword ptr [rdi+2Ch]
0x18007cb68  test    r12d, r12d
0x18007cb6b  jnz     loc_18007DDB9
0x18007cb71  mov     [rdi+r13], rax
0x18007cb75  mov     [rax], rdi
0x18007cb78  mov     dword ptr [rdi+30h], 1
0x18007cb7f  mov     rax, [rbp+1D0h+var_1C8]
0x18007cb83  mov     r13, [rbp-50h]
0x18007cb87  mov     [rbx+20h], rax
0x18007cb8b  add     rbx, 20h ; ' '
0x18007cb8f  jz      loc_18007DF22
0x18007cb95  cmp     r12d, 1
0x18007cb99  jz      loc_18007E00A
0x18007cb9f  mov     rax, [rbp+1D0h+var_1C8]
0x18007cba3  lock inc dword ptr [rax]
0x18007cba6  mov     rax, [rbx]
0x18007cba9  lock inc dword ptr [rax]
0x18007cbac  mov     rbx, [rbx]
0x18007cbaf  xor     edi, edi
0x18007cbb1  mov     eax, 0FFFFFFFFh
0x18007cbb6  lock xadd [r15], eax
0x18007cbbb  cmp     eax, 1
0x18007cbbe  jz      loc_18007E0E3
0x18007cbc4  xor     r15d, r15d
0x18007cbc7  inc     dword ptr [rbx+18h]
0x18007cbca  test    r13, r13
0x18007cbcd  jz      short loc_18007CBE2
0x18007cbcf  cmp     [rbp+1D0h+var_22C], r14d
0x18007cbd3  jz      short loc_18007CBE2
0x18007cbd5  mov     rcx, r13; lpCriticalSection
0x18007cbd8  call    cs:__imp_LeaveCriticalSection
0x18007cbde  mov     [rbp+1D0h+var_22C], r14d
0x18007cbe2  lea     rcx, [rbx+20h]; lpCriticalSection
0x18007cbe6  call    cs:__imp_EnterCriticalSection
0x18007cbec  mov     rsi, [rbp+1D0h+var_1E8]
0x18007cbf0  lea     rcx, [rsi+8]; SRWLock
0x18007cbf4  call    cs:__imp_AcquireSRWLockShared
0x18007cbfa  mov     [rbp+1D0h+var_1D8], rbx
0x18007cbfe  xor     ebx, ebx
0x18007cc00  test    r15, r15
0x18007cc03  jz      short loc_18007CC5B
0x18007cc05  mov     rsi, [rsi+40h]
0x18007cc09  xor     r13d, r13d
0x18007cc0c  mov     [r15+8], r13
0x18007cc10  lea     r12, [rsi+8]
0x18007cc14  test    r12, r12
0x18007cc17  jz      short loc_18007CC28
0x18007cc19  mov     rcx, r12; lpCriticalSection
0x18007cc1c  call    cs:__imp_EnterCriticalSection
0x18007cc22  mov     r13d, 1
0x18007cc28  dec     dword ptr [rsi+3Ch]
0x18007cc2b  mov     ecx, [rsi+38h]
0x18007cc2e  mov     eax, ecx
0x18007cc30  sub     eax, [rsi+3Ch]
0x18007cc33  cmp     eax, [rsi+40h]
0x18007cc36  ja      loc_18007E21B
0x18007cc3c  mov     rax, [rsi+30h]
0x18007cc40  mov     [r15+8], rax
0x18007cc44  mov     [rsi+30h], r15
0x18007cc48  test    r13d, r13d
0x18007cc4b  jz      short loc_18007CC5B
0x18007cc4d  test    r12, r12
0x18007cc50  jz      short loc_18007CC5B
0x18007cc52  mov     rcx, r12; lpCriticalSection
0x18007cc55  call    cs:__imp_LeaveCriticalSection
0x18007cc5b  test    rbx, rbx
0x18007cc5e  jz      short loc_18007CC68
0x18007cc60  mov     rcx, rbx; this
0x18007cc63  call    ?Release@CInFlightEntry@@QEAAKXZ; CInFlightEntry::Release(void)
0x18007cc68  cmp     [rbp+1D0h+var_22C], r14d
0x18007cc6c  jz      short loc_18007CC80
0x18007cc6e  mov     rax, [rbp-50h]
0x18007cc72  test    rax, rax
0x18007cc75  jz      short loc_18007CC80
0x18007cc77  mov     rcx, rax; lpCriticalSection
0x18007cc7a  call    cs:__imp_LeaveCriticalSection
0x18007cc80  mov     r12, [rbp+1D0h+var_240]
0x18007cc84  test    edi, edi
0x18007cc86  js      loc_18007E32A
0x18007cc8c  mov     rcx, [r12+28h]
0x18007cc91  lea     rdx, [rbp+1D0h+var_238]; struct CJetContext **
0x18007cc95  xor     r8d, r8d; int *
0x18007cc98  mov     rcx, [rcx+98h]; this
0x18007cc9f  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x18007cca4  mov     r13, [rbp+1D0h+var_238]
0x18007cca8  xor     r15d, r15d
0x18007ccab  mov     edi, eax
0x18007ccad  test    eax, eax
0x18007ccaf  js      loc_18007E33C
0x18007ccb5  mov     dword ptr [rbp+1D0h+var_238+4], r15d
0x18007ccb9  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18007ccc0  lea     rbx, aHashentryidind; "HashEntryIdIndex"
0x18007ccc7  jz      short loc_18007CCE0
0x18007ccc9  mov     dword ptr [rsp+2F0h+psetinfo], r15d
0x18007ccce  mov     r9, r13
0x18007ccd1  mov     qword ptr [rsp+2F0h+grbit], rbx
0x18007ccd6  mov     [rsp+2F0h+cbData], r15d
0x18007ccdb  call    WPP_SF_qdSD
0x18007cce0  cmp     [r13+30h], r14d
0x18007cce4  jnz     loc_18007E033
0x18007ccea  mov     edi, r15d
0x18007cced  mov     esi, 1
0x18007ccf2  test    byte ptr cs:xmmword_180266B60+1, 10h
0x18007ccf9  jz      short loc_18007CD14
0x18007ccfb  mov     edx, 0Eh
0x18007cd00  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x18007cd07  mov     ecx, 40Ch
0x18007cd0c  mov     r9d, edi
0x18007cd0f  call    WPP_SF_d
0x18007cd14  test    edi, edi
0x18007cd16  js      loc_18007E348
  ... truncated ...
```
