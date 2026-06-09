# CHitObj::BrowserRequestInit(CIsapiReqInfo *,int *)

- ea: `0x18000a9d0`
- end: `0x18000b45f`
- name: `?BrowserRequestInit@CHitObj@@QEAAJPEAVCIsapiReqInfo@@PEAH@Z`
- size: `2703`
- prototype: `__int64 __fastcall(CHitObj *__hidden this, struct CIsapiReqInfo *, int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bcb0`

## callees

- `0x1800076e0`
- `0x180009180`
- `0x18000a9d0`
- `0x18000c4f0`
- `0x18000f780`
- `0x180011560`
- `0x1800121c0`
- `0x180013114`
- `0x180016988`
- `0x180016a48`
- `0x180019f44`
- `0x18001a600`
- `0x18001a768`
- `0x18001e7a0`
- `0x180023dd0`
- `0x180030df0`
- `0x180034160`
- `0x1800482a8`
- `0x180053360`
- `0x180064010`

## import_xrefs

- `msvcrt!strstr` at `0x18000af08`
- `msvcrt!strstr` at `0x180027a22`
- `msvcrt!strstr` at `0x180027a43`
- `msvcrt!strstr` at `0x18000af08`
- `msvcrt!strstr` at `0x180027a22`
- `msvcrt!strstr` at `0x180027a43`
- `msvcrt!_wcsicmp` at `0x18000ac3d`
- `msvcrt!_wcsicmp` at `0x18000ac3d`
- `msvcrt!atoi` at `0x18000b11b`
- `msvcrt!atoi` at `0x18000b11b`
- `msvcrt!_wcsupr` at `0x18000ab81`
- `msvcrt!_wcsupr` at `0x18000ab81`
- `USER32!CharNextW` at `0x18000ab9d`
- `USER32!CharNextW` at `0x18000ab9d`
- `KERNEL32!HeapFree` at `0x180027c0b`
- `KERNEL32!HeapFree` at `0x180027c0b`
- `KERNEL32!LeaveCriticalSection` at `0x18000b2a3`
- `KERNEL32!LeaveCriticalSection` at `0x18000b427`
- `KERNEL32!LeaveCriticalSection` at `0x18000b2a3`
- `KERNEL32!LeaveCriticalSection` at `0x18000b427`
- `KERNEL32!SetLastError` at `0x1800277c5`
- `KERNEL32!SetLastError` at `0x18002784d`
- `KERNEL32!SetLastError` at `0x1800279d2`
- `KERNEL32!SetLastError` at `0x180027aa0`
- `KERNEL32!SetLastError` at `0x1800277c5`
- `KERNEL32!SetLastError` at `0x18002784d`
- `KERNEL32!SetLastError` at `0x1800279d2`
- `KERNEL32!SetLastError` at `0x180027aa0`
- `KERNEL32!EnterCriticalSection` at `0x18000b15c`
- `KERNEL32!EnterCriticalSection` at `0x18000b15c`
- `KERNEL32!GetLastError` at `0x18000ae6d`
- `KERNEL32!GetLastError` at `0x18002779a`
- `KERNEL32!GetLastError` at `0x1800277fb`
- `KERNEL32!GetLastError` at `0x180027829`
- `KERNEL32!GetLastError` at `0x180027a7b`
- `KERNEL32!GetLastError` at `0x18000ae6d`
- `KERNEL32!GetLastError` at `0x18002779a`
- `KERNEL32!GetLastError` at `0x1800277fb`
- `KERNEL32!GetLastError` at `0x180027829`
- `KERNEL32!GetLastError` at `0x180027a7b`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000ac6d`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000adb3`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000ac6d`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000adb3`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000b0a2`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000b0a2`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000aa41`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000ab1f`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000ae2e`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000b0ac`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000aa41`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000ab1f`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000ae2e`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000b0ac`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180027b6a`
- `iisutil!?DeleteRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX@Z` at `0x180027b6a`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000b1b8`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000b1b8`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000ae7e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800277b6`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002783e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180027a91`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000ae7e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800277b6`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002783e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180027a91`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000aa4e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000aaa2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ab11`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ab36`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ab75`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000abcf`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000abec`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ac19`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ae22`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ae45`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ae9a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000aec6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b0c4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b112`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b14c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800277d7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027868`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800278a0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800278d3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027911`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027ac5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027b0f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000aa4e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000aaa2`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ab11`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ab36`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ab75`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000abcf`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000abec`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ac19`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ae22`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ae45`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ae9a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000aec6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b0c4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b112`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b14c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800277d7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027868`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800278a0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800278d3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027911`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027ac5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027b0f`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000aa33`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x18000aa33`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000b12b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000b39e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002780e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180027963`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002798c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180027d4d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180027d82`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000b12b`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000b39e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002780e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180027963`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18002798c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180027d4d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180027d82`

## string_xrefs

- `0x18000ab47`: `UNICODE_PATH_TRANSLATED`
- `0x180027879`: `UNICODE_PATH_TRANSLATED`
- `0x1800278a8`: `UNICODE_PATH_TRANSLATED`
- `0x1800278db`: `UNICODE_PATH_TRANSLATED`
- `0x180027920`: `UNICODE_PATH_TRANSLATED`
- `0x180027b1f`: `UNICODE_PATH_TRANSLATED`

## pseudocode

```c
__int64 __fastcall CHitObj::BrowserRequestInit(CHitObj *this, struct CIsapiReqInfo *a2, int *a3)
{
  _BYTE *Ptr; // rax
  int v7; // r13d
  _BYTE *v8; // rdi
  unsigned int v9; // eax
  _BYTE *v10; // rax
  int v11; // ecx
  __int64 v12; // rdi
  bool v13; // zf
  __int64 v14; // rax
  __int64 v15; // r14
  __int64 (__fastcall *v16)(_QWORD, const char *, void *, int *); // rbx
  void *v17; // rax
  int v18; // ebx
  wchar_t *v19; // rbx
  wchar_t i; // ax
  _DWORD *v21; // r14
  __int64 v22; // rbx
  _WORD *v23; // rax
  _DWORD *v24; // r14
  _WORD *v25; // rax
  unsigned int *v26; // rax
  unsigned int *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  unsigned int v30; // ecx
  unsigned int v31; // eax
  ALLOC_CACHE_HANDLER *v32; // rcx
  _DWORD *v33; // rax
  unsigned int v34; // edx
  _DWORD *v35; // r12
  __int64 v36; // r14
  unsigned int (__fastcall *v37)(_QWORD, const char *, void *, int *); // rbx
  void *v38; // rax
  void (__fastcall *v39)(_QWORD, const char *, void *, int *); // rbx
  void *v40; // rax
  const char *v41; // rax
  const char *v42; // rbx
  __int64 v43; // rcx
  const char *v44; // rdx
  char *v45; // rcx
  unsigned __int64 v46; // rax
  int v47; // r9d
  int v48; // r8d
  int v49; // r10d
  int v50; // r9d
  int v51; // r8d
  int v52; // edx
  int v53; // r8d
  int v54; // edx
  int v55; // r9d
  __int64 v56; // rax
  __int64 v57; // r14
  __int64 v58; // rdi
  int v59; // r14d
  __int64 (__fastcall *v60)(_QWORD, const char *, void *, int *); // rbx
  void *v61; // rax
  int v62; // r15d
  int *v63; // rbx
  const char *v64; // rax
  int v65; // r15d
  void *v66; // rbx
  CTemplateCacheManager::CTemplateHashTable *v67; // rdi
  volatile signed __int32 *v68; // rax
  volatile signed __int32 *v69; // rax
  int Key; // eax
  char *v71; // rdx
  CTemplate *v72; // rbx
  volatile signed __int32 *v73; // rax
  volatile signed __int32 *v74; // rax
  char *v75; // r15
  char *v76; // r13
  CTemplate *v77; // rcx
  unsigned int (__fastcall *v78)(CTemplate *__hidden); // rax
  unsigned int v79; // eax
  int v80; // eax
  __int64 v81; // r8
  CTemplate *v82; // rcx
  unsigned int (__fastcall *v83)(CTemplate *__hidden); // rax
  __int64 v84; // rax
  __int64 v85; // rax
  int v86; // ecx
  __int64 v87; // rax
  volatile signed __int32 *v89; // rax
  char *v90; // rax
  __int64 (__fastcall *v91)(_QWORD, const char *, void *, int *); // rbx
  void *v92; // rax
  int v93; // eax
  __int64 (__fastcall *v94)(_QWORD, const char *, void *, int *); // rbx
  void *v95; // rax
  CPerfData *v96; // rcx
  char *v97; // r12
  CPerfData *v98; // rcx
  CPerfData *v99; // rcx
  int v100; // eax
  CIsapiReqInfo *v101; // rcx
  unsigned int InstanceId; // edi
  const unsigned __int16 *PszPathTranslatedW; // rax
  CTemplateCacheManager *v104; // rcx
  CComponentCollection *v105; // rcx
  int Size; // [rsp+30h] [rbp-79h] BYREF
  CTemplate *v107; // [rsp+38h] [rbp-71h] BYREF
  unsigned int v108; // [rsp+40h] [rbp-69h] BYREF
  __int64 v109; // [rsp+48h] [rbp-61h] BYREF
  int *v110; // [rsp+50h] [rbp-59h]
  void *v111; // [rsp+58h] [rbp-51h] BYREF
  int v112; // [rsp+60h] [rbp-49h]
  _BYTE v113[48]; // [rsp+68h] [rbp-41h] BYREF
  _BYTE v114[48]; // [rsp+98h] [rbp-11h] BYREF

  v110 = a3;
  *((_QWORD *)this + 8) = a2;
  _InterlockedIncrement((volatile signed __int32 *)a2);
  *((_DWORD *)this + 2) &= 0xFFF1FFFF;
  *((_DWORD *)this + 2) |= 0x10000u;
  _InterlockedIncrement((volatile signed __int32 *)&g_nBrowserRequests);
  v109 = 0;
  BUFFER::BUFFER((BUFFER *)v113, (unsigned __int8 *)&v109, 8u);
  v108 = 0;
  Size = BUFFER::QuerySize((BUFFER *)v113);
  Ptr = BUFFER::QueryPtr((BUFFER *)v113);
  v7 = 1;
  v8 = Ptr;
  if ( a2
    && (*(unsigned int (__fastcall **)(_QWORD, const char *, _BYTE *, int *))(*((_QWORD *)a2 + 1) + 160LL))(
         *(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL),
         "SERVER_PORT_SECURE",
         Ptr,
         &Size) )
  {
    v9 = Size;
LABEL_4:
    v108 = v9;
    goto LABEL_5;
  }
  *v8 = 0;
  if ( !a2 || GetLastError() == 1413 || (unsigned int)Size > 0x19000 )
  {
    v9 = 1;
    Size = 1;
    goto LABEL_4;
  }
  if ( BUFFER::Resize((BUFFER *)v113, Size) )
  {
    v108 = Size;
    v90 = (char *)BUFFER::QueryPtr((BUFFER *)v113);
    if ( (unsigned int)Server_FindKey(a2, v90, &v108, "SERVER_PORT_SECURE") )
      goto LABEL_5;
  }
  else
  {
    SetLastError(0xEu);
  }
  if ( GetLastError() == 14 )
  {
    BUFFER::~BUFFER((BUFFER *)v113);
    return 2147942414LL;
  }
LABEL_5:
  v10 = BUFFER::QueryPtr((BUFFER *)v113);
  v11 = 0;
  v12 = -1;
  v13 = *v10 == 49;
  v14 = *((_QWORD *)this + 8);
  if ( v13 )
    v11 = 0x8000;
  v107 = (CTemplate *)-1LL;
  *((_DWORD *)this + 2) &= ~0x8000u;
  *((_DWORD *)this + 2) |= v11;
  (*(void (__fastcall **)(_QWORD, __int64, CTemplate **, _QWORD, _QWORD))(*(_QWORD *)(v14 + 8) + 184LL))(
    *(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL),
    1011,
    &v107,
    0,
    0);
  v15 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 12) = v107;
  if ( (*(_BYTE *)(v15 + 52) & 0x20) == 0 )
  {
    *(_WORD *)BUFFER::QueryPtr((BUFFER *)(v15 + 1080)) = 0;
    Size = BUFFER::QuerySize((BUFFER *)(v15 + 1080));
    v16 = *(__int64 (__fastcall **)(_QWORD, const char *, void *, int *))(*(_QWORD *)(v15 + 8) + 160LL);
    v17 = BUFFER::QueryPtr((BUFFER *)(v15 + 1080));
    v18 = v16(*(_QWORD *)(*(_QWORD *)(v15 + 8) + 8LL), "UNICODE_PATH_TRANSLATED", v17, &Size);
    if ( !v18 && GetLastError() == 122 )
    {
      if ( BUFFER::Resize((BUFFER *)(v15 + 1080), Size) )
      {
        v91 = *(__int64 (__fastcall **)(_QWORD, const char *, void *, int *))(*(_QWORD *)(v15 + 8) + 160LL);
        v92 = BUFFER::QueryPtr((BUFFER *)(v15 + 1080));
        v18 = v91(*(_QWORD *)(*(_QWORD *)(v15 + 8) + 8LL), "UNICODE_PATH_TRANSLATED", v92, &Size);
      }
      else
      {
        SetLastError(0xEu);
        v18 = 0;
      }
    }
    *(_DWORD *)(v15 + 52) ^= (*(_DWORD *)(v15 + 52) ^ (32 * v18)) & 0x20;
  }
  v19 = (wchar_t *)BUFFER::QueryPtr((BUFFER *)(v15 + 1080));
  _wcsupr(v19);
  for ( i = *v19; *v19; i = *v19 )
  {
    if ( i == 47 )
      *v19 = 92;
    v19 = CharNextW(v19);
  }
  v21 = (_DWORD *)*((_QWORD *)this + 8);
  LODWORD(v22) = v21[9];
  if ( (_DWORD)v22 == -1 )
  {
    if ( (v21[13] & 0x20) == 0 )
    {
      *(_WORD *)BUFFER::QueryPtr((BUFFER *)(v21 + 270)) = 0;
      v21[13] ^= (v21[13]
                ^ (32
                 * CIsapiReqInfo::InternalGetServerVariable(
                     (CIsapiReqInfo *)v21,
                     "UNICODE_PATH_TRANSLATED",
                     (struct BUFFER *)(v21 + 270))))
               & 0x20;
    }
    if ( BUFFER::QueryPtr((BUFFER *)(v21 + 270)) )
    {
      if ( (v21[13] & 0x20) == 0 )
      {
        *(_WORD *)BUFFER::QueryPtr((BUFFER *)(v21 + 270)) = 0;
        v21[13] ^= (v21[13]
                  ^ (32
                   * CIsapiReqInfo::InternalGetServerVariable(
                       (CIsapiReqInfo *)v21,
                       "UNICODE_PATH_TRANSLATED",
                       (struct BUFFER *)(v21 + 270))))
                 & 0x20;
      }
      v23 = BUFFER::QueryPtr((BUFFER *)(v21 + 270));
      v22 = -1;
      do
        ++v22;
      while ( v23[v22] );
    }
    else
    {
      LODWORD(v22) = 0;
    }
    v21[9] = v22;
  }
  v24 = (_DWORD *)*((_QWORD *)this + 8);
  if ( (v24[13] & 0x20) == 0 )
  {
    *(_WORD *)BUFFER::QueryPtr((BUFFER *)(v24 + 270)) = 0;
    v24[13] ^= (v24[13]
              ^ (32
               * CIsapiReqInfo::InternalGetServerVariable(
                   (CIsapiReqInfo *)v24,
                   "UNICODE_PATH_TRANSLATED",
                   (struct BUFFER *)(v24 + 270))))
             & 0x20;
  }
  v25 = BUFFER::QueryPtr((BUFFER *)(v24 + 270));
  if ( !(_DWORD)v22 )
  {
    v22 = -1;
    do
      ++v22;
    while ( v25[v22] );
  }
  if ( (unsigned int)v22 >= 0xA && !_wcsicmp(&v25[(unsigned int)(v22 - 10)], L"GLOBAL.ASA") )
  {
    *a3 = 4015;
    BUFFER::~BUFFER((BUFFER *)v113);
    return 2147500037LL;
  }
  Size = 0;
  if ( (int)CHitObj::AssignApplnToBrowserRequest(this, &Size) < 0 )
  {
    v93 = 4006;
    if ( Size )
      v93 = 4014;
    *a3 = v93;
    goto LABEL_148;
  }
  v26 = (unsigned int *)ALLOC_CACHE_HANDLER::Alloc(CComponentCollection::sm_pach);
  v27 = v26;
  if ( !v26 )
  {
LABEL_198:
    *((_QWORD *)this + 10) = 0;
    *a3 = 100;
    BUFFER::~BUFFER((BUFFER *)v113);
    return 2147942414LL;
  }
  *(_BYTE *)v26 = 0;
  v26[4] &= 0xFFFFFFFC;
  *((_QWORD *)v26 + 3) = 0;
  *((_QWORD *)v26 + 4) = 0;
  *((_QWORD *)v26 + 5) = 0;
  *((_QWORD *)v26 + 6) = UnicodeUpcaseHash;
  *((_QWORD *)v26 + 7) = 0;
  *((_QWORD *)v26 + 1) = &CHashTableStr::`vftable';
  v26[68] &= 0xFFFFFFFC;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  *((_QWORD *)v26 + 38) = UnicodeUpcaseHash;
  *((_QWORD *)v26 + 39) = 0;
  *((_QWORD *)v26 + 33) = &CHashTableStr::`vftable';
  *((_WORD *)v26 + 260) = 0;
  *((_QWORD *)v26 + 66) = 0;
  *((_QWORD *)v26 + 67) = 0;
  v26[136] = 0;
  v26[137] = 8;
  *((_QWORD *)v26 + 69) = 0;
  v26[140] = 0;
  v26[142] = 0;
  v26[143] = 8;
  *((_QWORD *)v26 + 72) = 0;
  v26[146] = 0;
  *((_QWORD *)v26 + 74) = 0;
  v28 = *((_QWORD *)this + 29);
  *((_QWORD *)this + 10) = v27;
  if ( !v28 )
    v28 = *(_QWORD *)(*((_QWORD *)this + 3) + 152LL);
  v29 = *(_DWORD *)(v28 + 92);
  v30 = *v27;
  v27[4] |= 1u;
  *((_QWORD *)v27 + 7) = 19;
  *((_QWORD *)v27 + 5) = 0;
  v31 = (v30 & 0xFFFFFFF0 | 4) ^ ((v30 & 0xF0 | 4) ^ (unsigned __int8)((_BYTE)v29 << 7)) & 0x80;
  v32 = CPageComponentManager::sm_pach;
  *v27 = v31;
  v27[68] |= 1u;
  *((_QWORD *)v27 + 39) = 17;
  *((_QWORD *)v27 + 37) = 0;
  v27[130] = 458775;
  v27[131] = 11;
  *((_QWORD *)v27 + 66) = 0;
  v33 = ALLOC_CACHE_HANDLER::Alloc(v32);
  if ( !v33 )
  {
    v105 = (CComponentCollection *)*((_QWORD *)this + 10);
    *((_QWORD *)this + 11) = 0;
    if ( v105 )
      CComponentCollection::`scalar deleting destructor'(v105, v34);
    goto LABEL_198;
  }
  *((_QWORD *)this + 11) = v33;
  *v33 = 458769;
  v33[1] = 11;
  *((_QWORD *)v33 + 1) = 0;
  *((_QWORD *)v33 + 2) = this;
  v35 = (_DWORD *)*((_QWORD *)this + 29);
  if ( !v35 )
    v35 = *(_DWORD **)(*((_QWORD *)this + 3) + 152LL);
  if ( v35[7] )
  {
    *((_DWORD *)this + 35) = -1;
    *((_BYTE *)this + 112) = 0;
  }
  else if ( !v35[9] )
  {
    goto LABEL_69;
  }
  v36 = *((_QWORD *)this + 8);
  if ( (*(_BYTE *)(v36 + 52) & 0x40) == 0 )
  {
    *(_BYTE *)BUFFER::QueryPtr((BUFFER *)(v36 + 1128)) = 0;
    Size = BUFFER::QuerySize((BUFFER *)(v36 + 1128));
    v37 = *(unsigned int (__fastcall **)(_QWORD, const char *, void *, int *))(*(_QWORD *)(v36 + 8) + 160LL);
    v38 = BUFFER::QueryPtr((BUFFER *)(v36 + 1128));
    if ( !v37(*(_QWORD *)(*(_QWORD *)(v36 + 8) + 8LL), "HTTP_COOKIE", v38, &Size) && GetLastError() == 122 )
    {
      if ( BUFFER::Resize((BUFFER *)(v36 + 1128), Size) )
      {
        v39 = *(void (__fastcall **)(_QWORD, const char *, void *, int *))(*(_QWORD *)(v36 + 8) + 160LL);
        v40 = BUFFER::QueryPtr((BUFFER *)(v36 + 1128));
        v39(*(_QWORD *)(*(_QWORD *)(v36 + 8) + 8LL), "HTTP_COOKIE", v40, &Size);
      }
      else
      {
        SetLastError(0xEu);
      }
    }
    *(_DWORD *)(v36 + 52) |= 0x40u;
  }
  v41 = (const char *)BUFFER::QueryPtr((BUFFER *)(v36 + 1128));
  v42 = v41;
  if ( v41 && *v41 )
  {
    if ( v35[7] )
    {
      v43 = *((_QWORD *)this + 3);
      if ( (*((_DWORD *)this + 2) & 0x8000) == 0
        || (v44 = (const char *)(v43 + 421), !*(_DWORD *)(*(_QWORD *)(v43 + 152) + 44LL)) )
      {
        v44 = (const char *)(v43 + 400);
      }
      v45 = strstr(v41, v44);
      if ( (v45
         || (*((_DWORD *)this + 2) & 0x8000) != 0
         && v35[11]
         && (v45 = strstr(v42, (const char *)(*((_QWORD *)this + 3) + 400LL))) != 0)
        && v45[20] == 61 )
      {
        v46 = -1;
        do
          ++v46;
        while ( v45[v46 + 21] );
        if ( v46 >= 0x18 )
        {
          *((_OWORD *)this + 7) = *(_OWORD *)(v45 + 21);
          *((_QWORD *)this + 16) = *(_QWORD *)(v45 + 37);
          *((_BYTE *)this + 136) = 0;
        }
      }
      if ( *((_BYTE *)this + 112) )
      {
        do
          ++v12;
        while ( *((_BYTE *)this + v12 + 112) );
        if ( v12 == 24 )
        {
          *((_DWORD *)this + 35) = 0;
          v47 = 0;
          v48 = 0;
          while ( 1 )
          {
            v49 = ((char *)this - (unsigned int)v47)[119];
            if ( (unsigned int)(v49 - 65) > 0xF )
              break;
            ++v47;
            *((_DWORD *)this + 35) = (16 * v48) | (v49 - 65);
            v48 = (16 * v48) | (v49 - 65);
            if ( v47 >= 8 )
            {
              *((_DWORD *)this + 36) = 0;
              v50 = 0;
              v51 = 0;
              while ( 1 )
              {
                v52 = ((char *)this - (unsigned int)v50)[127];
                if ( (unsigned int)(v52 - 65) > 0xF )
                  goto LABEL_67;
                ++v50;
                *((_DWORD *)this + 36) = (16 * v51) | (v52 - 65);
                v51 = (16 * v51) | (v52 - 65);
                if ( v50 >= 8 )
                {
                  *((_DWORD *)this + 37) = 0;
                  v53 = 0;
                  v54 = 0;
                  while ( 1 )
                  {
                    v55 = ((char *)this - (unsigned int)v53)[135];
                    if ( (unsigned int)(v55 - 65) > 0xF )
                      goto LABEL_67;
                    ++v53;
                    *((_DWORD *)this + 37) = (16 * v54) | (v55 - 65);
                    v54 = (16 * v54) | (v55 - 65);
                    if ( v53 >= 8 )
                      goto LABEL_68;
                  }
                }
              }
            }
          }
        }
LABEL_67:
        *((_DWORD *)this + 35) = -1;
        *((_BYTE *)this + 112) = 0;
      }
    }
LABEL_68:
    if ( v35[9] && strstr(v42, "ASPCLIENTDEBUG=") )
      *((_DWORD *)this + 2) |= 0x20u;
  }
LABEL_69:
  v56 = *((_QWORD *)this + 29);
  if ( !v56 )
    v56 = *(_QWORD *)(*((_QWORD *)this + 3) + 152LL);
  v57 = *((_QWORD *)this + 29);
  *((_DWORD *)this + 40) = *(_DWORD *)(v56 + 56);
  if ( !v57 )
    v57 = *(_QWORD *)(*((_QWORD *)this + 3) + 152LL);
  v58 = *((_QWORD *)this + 8);
  v59 = *(_DWORD *)(v57 + 28);
  if ( v58 )
  {
    if ( (*(_DWORD *)(v58 + 52) & 0x100) != 0 )
    {
      v63 = (int *)(v58 + 56);
      goto LABEL_79;
    }
    BUFFER::BUFFER((BUFFER *)v114);
    Size = BUFFER::QuerySize((BUFFER *)v114);
    v60 = *(__int64 (__fastcall **)(_QWORD, const char *, void *, int *))(*(_QWORD *)(v58 + 8) + 160LL);
    v61 = BUFFER::QueryPtr((BUFFER *)v114);
    v62 = v60(*(_QWORD *)(*(_QWORD *)(v58 + 8) + 8LL), "INSTANCE_ID", v61, &Size);
    if ( !v62 && GetLastError() == 122 )
    {
      if ( !BUFFER::Resize((BUFFER *)v114, Size) )
      {
        SetLastError(0xEu);
        *(_DWORD *)(v58 + 52) &= ~0x100u;
        v63 = (int *)(v58 + 56);
LABEL_78:
        *v63 = v7;
        BUFFER::~BUFFER((BUFFER *)v114);
        v58 = *((_QWORD *)this + 8);
LABEL_79:
        v65 = *v63;
        goto LABEL_80;
      }
      v94 = *(__int64 (__fastcall **)(_QWORD, const char *, void *, int *))(*(_QWORD *)(v58 + 8) + 160LL);
      v95 = BUFFER::QueryPtr((BUFFER *)v114);
      v62 = v94(*(_QWORD *)(*(_QWORD *)(v58 + 8) + 8LL), "INSTANCE_ID", v95, &Size);
    }
    v63 = (int *)(v58 + 56);
    *(_DWORD *)(v58 + 52) ^= (*(_DWORD *)(v58 + 52) ^ (v62 << 8)) & 0x100;
    if ( (v62 & 1) != 0 )
    {
      v64 = (const char *)BUFFER::QueryPtr((BUFFER *)v114);
      v7 = atoi(v64);
    }
    goto LABEL_78;
  }
  v65 = 0;
  v58 = 0;
LABEL_80:
  if ( (*(_BYTE *)(v58 + 52) & 0x20) == 0 )
  {
    *(_WORD *)BUFFER::QueryPtr((BUFFER *)(v58 + 1080)) = 0;
    *(_DWORD *)(v58 + 52) ^= (*(_DWORD *)(v58 + 52)
                            ^ (32
                             * CIsapiReqInfo::InternalGetServerVariable(
                                 (CIsapiReqInfo *)v58,
                                 "UNICODE_PATH_TRANSLATED",
                                 (struct BUFFER *)(v58 + 1080))))
                           & 0x20;
  }
  v66 = BUFFER::QueryPtr((BUFFER *)(v58 + 1080));
  EnterCriticalSection(&stru_180079DF0);
  v67 = lpParameter;
  v111 = v66;
  v112 = v65;
  if ( (dword_18007CB28 & 1) != 0 )
    v68 = (volatile signed __int32 *)(qword_18007CB88 + 148);
  else
    v68 = (volatile signed __int32 *)byte_18007CC28;
  _InterlockedIncrement(v68);
  if ( (dword_18007CB28 & 1) != 0 )
    v69 = (volatile signed __int32 *)(qword_18007CB88 + 112);
  else
    v69 = &dword_18007CC04;
  _InterlockedIncrement(v69);
  v107 = 0;
  Key = CLKRHashTable::FindKey(v67, &v111, &v107);
  v72 = v107;
  if ( !Key )
  {
    if ( (dword_18007CB28 & 1) != 0 )
      v73 = (volatile signed __int32 *)(qword_18007CB88 + 108);
    else
      v73 = (volatile signed __int32 *)byte_18007CC00;
    _InterlockedIncrement(v73);
    if ( (*((_DWORD *)v72 + 98) & 0x1000) != 0 )
    {
      *(_QWORD *)(*((_QWORD *)v72 + 2) + 8LL) = *((_QWORD *)v72 + 1);
      *(_QWORD *)(*((_QWORD *)v72 + 1) + 16LL) = *((_QWORD *)v72 + 2);
      *((_QWORD *)v72 + 1) = v72;
      *((_QWORD *)v72 + 2) = v72;
      --*((_DWORD *)v67 + 31);
      if ( (unsigned int)CTemplate::UnPersistData(v72) )
      {
        CLKRHashTable::DeleteRecord(v67, v72);
        (*(void (__fastcall **)(__int64))(*((_QWORD *)v72 + 3) + 16LL))((__int64)v72 + 24);
        _InterlockedDecrement((volatile signed __int32 *)CPerfData::PDWCounter(v96, 25));
LABEL_123:
        LeaveCriticalSection(&stru_180079DF0);
        goto LABEL_106;
      }
      if ( (dword_18007CB28 & 1) != 0 )
        v89 = (volatile signed __int32 *)(qword_18007CB88 + 140);
      else
        v89 = (volatile signed __int32 *)byte_18007CC20;
      _InterlockedIncrement(v89);
      ++*((_DWORD *)v67 + 30);
    }
    else
    {
      if ( (dword_18007CB28 & 1) != 0 )
        v74 = (volatile signed __int32 *)(qword_18007CB88 + 144);
      else
        v74 = &dword_18007CC24;
      _InterlockedIncrement(v74);
    }
    v71 = (char *)v67 + 72;
    *(_QWORD *)(*((_QWORD *)v72 + 2) + 8LL) = *((_QWORD *)v72 + 1);
    *(_QWORD *)(*((_QWORD *)v72 + 1) + 16LL) = *((_QWORD *)v72 + 2);
    *((_QWORD *)v72 + 1) = v72;
    *((_QWORD *)v72 + 2) = (char *)v67 + 72;
    *((_QWORD *)v72 + 1) = *((_QWORD *)v67 + 10);
    *(_QWORD *)(*((_QWORD *)v67 + 10) + 16LL) = v72;
    *((_QWORD *)v67 + 10) = v72;
  }
  v75 = (char *)*((_QWORD *)v67 + 13);
  v76 = (char *)v67 + 96;
  if ( v75 != (char *)v67 + 96 )
  {
    do
    {
      if ( !*((_QWORD *)v75 + 8) )
        break;
      v97 = (char *)*((_QWORD *)v75 + 1);
      if ( *((_DWORD *)v75 + 19) == 1 )
      {
        if ( *((_DWORD *)v75 + 20) == 1 )
        {
          ++g_nScavengedPurged;
          goto LABEL_176;
        }
        if ( (unsigned int)CTemplate::PersistData((CTemplate *)v75, v71) )
        {
          ++g_nScavengedPersistFailed;
LABEL_176:
          if ( !(unsigned int)CTemplateCacheManager::CTemplateHashTable::RemoveTemplate(v67, v75, 0, 0) )
          {
            if ( (v75[392] & 1) != 0 )
              (*(void (__fastcall **)(char *))(*((_QWORD *)v75 + 3) + 16LL))(v75 + 24);
            else
              CTemplate::End((CTemplate *)v75);
          }
          goto LABEL_181;
        }
        ++g_nScavengedPersisted;
        HeapFree(CTemplate::sm_hLargeHeap, 0, *((LPVOID *)v75 + 8));
        *((_QWORD *)v75 + 8) = 0;
      }
      else
      {
        *(_QWORD *)(*((_QWORD *)v75 + 2) + 8LL) = v97;
        *(_QWORD *)(*((_QWORD *)v75 + 1) + 16LL) = *((_QWORD *)v75 + 2);
        *((_QWORD *)v75 + 1) = v75;
        *((_QWORD *)v75 + 2) = v76;
        *((_QWORD *)v75 + 1) = *((_QWORD *)v67 + 13);
        *(_QWORD *)(*((_QWORD *)v67 + 13) + 16LL) = v75;
        *((_QWORD *)v67 + 13) = v75;
      }
LABEL_181:
      v75 = v97;
    }
    while ( v97 != v76 );
  }
  if ( !v72 || (*((_BYTE *)v72 + 392) & 8) == 0 )
    goto LABEL_123;
  v77 = (CTemplate *)((char *)v72 + 24);
  v78 = *(unsigned int (__fastcall **)(CTemplate *__hidden))(*((_QWORD *)v72 + 3) + 8LL);
  if ( v78 == CTemplate::AddRef )
    CTemplate::AddRef(v77);
  else
    v78(v77);
  LeaveCriticalSection(&stru_180079DF0);
  v79 = *((_DWORD *)v72 + 98);
  if ( v59 )
  {
    v59 = (v79 >> 6) & 1;
  }
  else if ( (v79 & 0x80u) != 0 && (*(_BYTE *)(*((_QWORD *)this + 3) + 72LL) & 0x20) == 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v72 + 20);
    if ( (int)CResponse::WriteScriptlessTemplate(*((struct CIsapiReqInfo **)this + 8), v72) >= 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)CPerfData::PDWCounter(v98, 19));
      _InterlockedIncrement((volatile signed __int32 *)CPerfData::PDWCounter(v99, 16));
      *((_DWORD *)this + 2) |= 0x800u;
    }
  }
  v80 = *((_DWORD *)this + 2);
  if ( (v80 & 0x800) == 0 )
  {
    v81 = *((_QWORD *)v72 + 56);
    if ( v81 )
    {
      if ( (v80 & 0x2000) == 0 )
      {
        v100 = Do449Processing(this, *((struct C449Cookie ***)v72 + 55), v81);
        *((_DWORD *)this + 2) |= 0x2000u;
        if ( v100 < 0 )
        {
          v101 = (CIsapiReqInfo *)*((_QWORD *)this + 8);
          if ( v101 )
            InstanceId = CIsapiReqInfo::QueryInstanceId(v101);
          else
            InstanceId = 0;
          PszPathTranslatedW = CIsapiReqInfo::QueryPszPathTranslatedW(*((CIsapiReqInfo **)this + 8));
          CTemplateCacheManager::Flush(v104, PszPathTranslatedW, InstanceId);
        }
      }
    }
  }
  v82 = (CTemplate *)((char *)v72 + 24);
  v83 = *(unsigned int (__fastcall **)(CTemplate *__hidden))(*((_QWORD *)v72 + 3) + 16LL);
  if ( v83 == CTemplate::Release )
    CTemplate::Release(v82);
  else
    v83(v82);
LABEL_106:
  v84 = *((_QWORD *)this + 29);
  if ( !v84 )
    v84 = *(_QWORD *)(*((_QWORD *)this + 3) + 152LL);
  *((_DWORD *)this + 41) = *(_DWORD *)(v84 + 52);
  v85 = *((_QWORD *)this + 29);
  if ( !v85 )
    v85 = *(_QWORD *)(*((_QWORD *)this + 3) + 152LL);
  *((_DWORD *)this + 42) = *(_DWORD *)(v85 + 96);
  if ( !v59 || (*((_DWORD *)this + 2) & 0x800) != 0 )
  {
    *((_DWORD *)this + 2) |= 1u;
    BUFFER::~BUFFER((BUFFER *)v113);
    return 0;
  }
  LODWORD(v107) = 0;
  Size = 0;
  if ( (int)CHitObj::AssignSessionToBrowserRequest(this, (int *)&v107, &Size, v110) < 0 )
  {
LABEL_148:
    BUFFER::~BUFFER((BUFFER *)v113);
    return 2147500037LL;
  }
  v86 = *((_DWORD *)this + 2);
  if ( Size )
    v86 |= 8u;
  if ( (_DWORD)v107 )
  {
    v87 = *((_QWORD *)this + 3);
    v86 |= 4u;
    *((_DWORD *)this + 2) = v86;
    if ( *(_QWORD *)(v87 + 128) )
      v86 |= 2u;
  }
  *((_DWORD *)this + 2) = v86 | 1;
  BUFFER::~BUFFER((BUFFER *)v113);
  return 0;
}

```

## disassembly

```asm
0x18000a9d0  push    rbp
0x18000a9d2  push    rbx
0x18000a9d3  push    rsi
0x18000a9d4  push    rdi
0x18000a9d5  push    r12
0x18000a9d7  push    r13
0x18000a9d9  push    r14
0x18000a9db  lea     rbp, [rsp-27h]
0x18000a9e0  sub     rsp, 0D0h
0x18000a9e7  mov     rax, cs:__security_cookie
0x18000a9ee  xor     rax, rsp
0x18000a9f1  mov     [rbp+57h+var_38], rax
0x18000a9f5  mov     r12, r8
0x18000a9f8  mov     [rbp+57h+var_B0], r8
0x18000a9fc  mov     rbx, rdx
0x18000a9ff  mov     [rcx+40h], rdx
0x18000aa03  mov     rsi, rcx
0x18000aa06  lock inc dword ptr [rdx]
0x18000aa09  and     dword ptr [rcx+8], 0FFF1FFFFh
0x18000aa10  or      dword ptr [rcx+8], 10000h
0x18000aa17  lock inc cs:?g_nBrowserRequests@@3KA; ulong g_nBrowserRequests
0x18000aa1e  xor     r14d, r14d
0x18000aa21  lea     rdx, [rbp+57h+var_B8]
0x18000aa25  mov     r8d, 8
0x18000aa2b  mov     [rbp+57h+var_B8], r14
0x18000aa2f  lea     rcx, [rbp+57h+var_98]
0x18000aa33  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18000aa39  lea     rcx, [rbp+57h+var_98]
0x18000aa3d  mov     [rbp+57h+var_C0], r14d
0x18000aa41  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000aa47  lea     rcx, [rbp+57h+var_98]
0x18000aa4b  mov     [rbp+57h+var_D0], eax
0x18000aa4e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000aa54  mov     r13d, 1
0x18000aa5a  mov     rdi, rax
0x18000aa5d  test    rbx, rbx
0x18000aa60  jz      loc_18002778E
0x18000aa66  mov     rcx, [rbx+8]
0x18000aa6a  lea     r9, [rbp+57h+var_D0]
0x18000aa6e  mov     r8, rdi
0x18000aa71  lea     rdx, aServerPortSecu_0; "SERVER_PORT_SECURE"
0x18000aa78  mov     rax, [rcx+0A0h]
0x18000aa7f  mov     rcx, [rcx+8]
0x18000aa83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa88  test    eax, eax
0x18000aa8a  jz      loc_18002778E
0x18000aa90  mov     eax, [rbp+57h+var_D0]
0x18000aa93  mov     [rbp+57h+var_C0], eax
0x18000aa96  lea     rcx, [rbp+57h+var_98]
0x18000aa9a  mov     [rsp+100h+arg_18], r15
0x18000aaa2  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000aaa8  mov     edx, 8000h
0x18000aaad  mov     [rsp+100h+var_E0], r14
0x18000aab2  mov     ecx, r14d
0x18000aab5  lea     r8, [rbp+57h+var_C8]
0x18000aab9  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000aac0  cmp     byte ptr [rax], 31h ; '1'
0x18000aac3  mov     rax, [rsi+40h]
0x18000aac7  cmovz   ecx, edx
0x18000aaca  mov     [rbp+57h+var_C8], rdi
0x18000aace  and     dword ptr [rsi+8], 0FFFF7FFFh
0x18000aad5  xor     r9d, r9d
0x18000aad8  or      [rsi+8], ecx
0x18000aadb  mov     edx, 3F3h
0x18000aae0  mov     rcx, [rax+8]
0x18000aae4  mov     rax, [rcx+0B8h]
0x18000aaeb  mov     rcx, [rcx+8]
0x18000aaef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaf4  mov     r14, [rsi+40h]
0x18000aaf8  mov     rax, [rbp+57h+var_C8]
0x18000aafc  mov     [rsi+60h], rax
0x18000ab00  test    byte ptr [r14+34h], 20h
0x18000ab05  lea     r15, [r14+438h]
0x18000ab0c  jnz     short loc_18000AB72
0x18000ab0e  mov     rcx, r15
0x18000ab11  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ab17  xor     ecx, ecx
0x18000ab19  mov     [rax], cx
0x18000ab1c  mov     rcx, r15
0x18000ab1f  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000ab25  mov     [rbp+57h+var_D0], eax
0x18000ab28  mov     rcx, r15
0x18000ab2b  mov     rax, [r14+8]
0x18000ab2f  mov     rbx, [rax+0A0h]
0x18000ab36  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ab3c  mov     rcx, [r14+8]
0x18000ab40  lea     r9, [rbp+57h+var_D0]
0x18000ab44  mov     r8, rax
0x18000ab47  lea     rdx, aUnicodePathTra; "UNICODE_PATH_TRANSLATED"
0x18000ab4e  mov     rax, rbx
0x18000ab51  mov     rcx, [rcx+8]
0x18000ab55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab5a  mov     ebx, eax
0x18000ab5c  test    eax, eax
0x18000ab5e  jz      loc_180027829
0x18000ab64  shl     ebx, 5
0x18000ab67  xor     ebx, [r14+34h]
0x18000ab6b  and     ebx, 20h
0x18000ab6e  xor     [r14+34h], ebx
0x18000ab72  mov     rcx, r15
0x18000ab75  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ab7b  mov     rcx, rax; String
0x18000ab7e  mov     rbx, rax
0x18000ab81  call    cs:__imp__wcsupr
0x18000ab87  movzx   eax, word ptr [rbx]
0x18000ab8a  test    ax, ax
0x18000ab8d  jz      short loc_18000ABAE
0x18000ab8f  nop
0x18000ab90  cmp     ax, 2Fh ; '/'
0x18000ab94  jz      loc_180027893
0x18000ab9a  mov     rcx, rbx; lpsz
0x18000ab9d  call    cs:__imp_CharNextW
0x18000aba3  mov     rbx, rax
0x18000aba6  movzx   eax, word ptr [rax]
0x18000aba9  test    ax, ax
0x18000abac  jnz     short loc_18000AB90
0x18000abae  mov     r14, [rsi+40h]
0x18000abb2  mov     ebx, [r14+24h]
0x18000abb6  cmp     ebx, edi
0x18000abb8  jnz     short loc_18000AC03
0x18000abba  test    byte ptr [r14+34h], 20h
0x18000abbf  lea     rbx, [r14+438h]
0x18000abc6  jz      loc_18002789D
0x18000abcc  mov     rcx, rbx
0x18000abcf  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000abd5  test    rax, rax
0x18000abd8  jz      loc_180027903
0x18000abde  test    byte ptr [r14+34h], 20h
0x18000abe3  jz      loc_1800278D0
0x18000abe9  mov     rcx, rbx
0x18000abec  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000abf2  mov     rbx, rdi
0x18000abf5  inc     rbx
0x18000abf8  cmp     word ptr [rax+rbx*2], 0
0x18000abfd  jnz     short loc_18000ABF5
0x18000abff  mov     [r14+24h], ebx
0x18000ac03  mov     r14, [rsi+40h]
0x18000ac07  test    byte ptr [r14+34h], 20h
0x18000ac0c  jz      loc_18002790A
0x18000ac12  lea     rcx, [r14+438h]
0x18000ac19  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ac1f  mov     rdx, rax
0x18000ac22  test    ebx, ebx
0x18000ac24  jz      loc_180027945
0x18000ac2a  cmp     ebx, 0Ah
0x18000ac2d  jb      short loc_18000AC4B
0x18000ac2f  lea     eax, [rbx-0Ah]
0x18000ac32  lea     rcx, [rdx+rax*2]; String1
0x18000ac36  lea     rdx, aGlobalAsa_0; "GLOBAL.ASA"
0x18000ac3d  call    cs:__imp__wcsicmp
0x18000ac43  test    eax, eax
0x18000ac45  jz      loc_180027957
0x18000ac4b  lea     rdx, [rbp+57h+var_D0]; int *
0x18000ac4f  mov     [rbp+57h+var_D0], 0
0x18000ac56  mov     rcx, rsi; this
0x18000ac59  call    ?AssignApplnToBrowserRequest@CHitObj@@QEAAJPEAH@Z; CHitObj::AssignApplnToBrowserRequest(int *)
0x18000ac5e  test    eax, eax
0x18000ac60  js      loc_180027973
0x18000ac66  mov     rcx, cs:?sm_pach@CComponentCollection@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CComponentCollection::sm_pach
0x18000ac6d  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000ac73  mov     rdx, rax
0x18000ac76  test    rax, rax
0x18000ac79  jz      loc_180027D70
0x18000ac7f  mov     byte ptr [rax], 0
0x18000ac82  lea     rcx, ?UnicodeUpcaseHash@@YAKPEBEH@Z; UnicodeUpcaseHash(uchar const *,int)
0x18000ac89  and     dword ptr [rax+10h], 0FFFFFFFCh
0x18000ac8d  xor     r8d, r8d
0x18000ac90  mov     [rax+18h], r8
0x18000ac94  mov     [rax+20h], r8
0x18000ac98  mov     [rax+28h], r8
0x18000ac9c  mov     [rax+30h], rcx
0x18000aca0  mov     [rax+38h], r8
0x18000aca4  lea     rax, ??_7CHashTableStr@@6B@; const CHashTableStr::`vftable'
0x18000acab  mov     [rdx+8], rax
0x18000acaf  and     dword ptr [rdx+110h], 0FFFFFFFCh
0x18000acb6  mov     [rdx+118h], r8
0x18000acbd  mov     [rdx+120h], r8
0x18000acc4  mov     [rdx+128h], r8
0x18000accb  mov     [rdx+130h], rcx
0x18000acd2  mov     [rdx+138h], r8
0x18000acd9  mov     [rdx+108h], rax
0x18000ace0  mov     [rdx+208h], r8w
0x18000ace8  mov     [rdx+210h], r8
0x18000acef  mov     [rdx+218h], r8
0x18000acf6  mov     [rdx+220h], r8d
0x18000acfd  mov     dword ptr [rdx+224h], 8
0x18000ad07  mov     [rdx+228h], r8
0x18000ad0e  mov     [rdx+230h], r8d
0x18000ad15  mov     [rdx+238h], r8d
0x18000ad1c  mov     dword ptr [rdx+23Ch], 8
0x18000ad26  mov     [rdx+240h], r8
0x18000ad2d  mov     [rdx+248h], r8d
0x18000ad34  mov     [rdx+250h], r8
0x18000ad3b  mov     rax, [rsi+0E8h]
0x18000ad42  mov     [rsi+50h], rdx
0x18000ad46  test    rax, rax
0x18000ad49  jz      loc_18002799C
0x18000ad4f  mov     eax, [rax+5Ch]
0x18000ad52  mov     ecx, [rdx]
0x18000ad54  or      [rdx+10h], r13d
0x18000ad58  and     ecx, 0FFFFFFF4h
0x18000ad5b  mov     qword ptr [rdx+38h], 13h
0x18000ad63  or      ecx, 4
0x18000ad66  mov     [rdx+28h], r8
0x18000ad6a  shl     eax, 7
0x18000ad6d  xor     eax, ecx
0x18000ad6f  and     eax, 80h
0x18000ad74  xor     eax, ecx
0x18000ad76  mov     rcx, cs:?sm_pach@CPageComponentManager@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CPageComponentManager::sm_pach
0x18000ad7d  mov     [rdx], eax
0x18000ad7f  or      [rdx+110h], r13d
0x18000ad86  mov     qword ptr [rdx+138h], 11h
0x18000ad91  mov     [rdx+128h], r8
0x18000ad98  mov     dword ptr [rdx+208h], 70017h
0x18000ada2  mov     dword ptr [rdx+20Ch], 0Bh
0x18000adac  mov     [rdx+210h], r8
0x18000adb3  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000adb9  test    rax, rax
0x18000adbc  jz      loc_180027D5A
0x18000adc2  mov     [rsi+58h], rax
0x18000adc6  mov     dword ptr [rax], 70011h
0x18000adcc  mov     dword ptr [rax+4], 0Bh
0x18000add3  mov     qword ptr [rax+8], 0
0x18000addb  mov     [rax+10h], rsi
0x18000addf  mov     r12, [rsi+0E8h]
0x18000ade6  test    r12, r12
0x18000ade9  jz      loc_1800279AC
0x18000adef  cmp     dword ptr [r12+1Ch], 0
0x18000adf5  jz      loc_1800279BC
0x18000adfb  mov     dword ptr [rsi+8Ch], 0FFFFFFFFh
0x18000ae05  mov     byte ptr [rsi+70h], 0
0x18000ae09  mov     r14, [rsi+40h]
0x18000ae0d  test    byte ptr [r14+34h], 40h
0x18000ae12  lea     r15, [r14+468h]
0x18000ae19  jnz     loc_18000AEC3
0x18000ae1f  mov     rcx, r15
0x18000ae22  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ae28  mov     rcx, r15
0x18000ae2b  mov     byte ptr [rax], 0
0x18000ae2e  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000ae34  mov     [rbp+57h+var_D0], eax
0x18000ae37  mov     rcx, r15
0x18000ae3a  mov     rax, [r14+8]
0x18000ae3e  mov     rbx, [rax+0A0h]
0x18000ae45  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ae4b  mov     rcx, [r14+8]
0x18000ae4f  lea     r9, [rbp+57h+var_D0]
0x18000ae53  mov     r8, rax
0x18000ae56  lea     rdx, aHttpCookie; "HTTP_COOKIE"
0x18000ae5d  mov     rax, rbx
0x18000ae60  mov     rcx, [rcx+8]
0x18000ae64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae69  test    eax, eax
0x18000ae6b  jnz     short loc_18000AEBE
0x18000ae6d  call    cs:__imp_GetLastError
0x18000ae73  cmp     eax, 7Ah ; 'z'
0x18000ae76  jnz     short loc_18000AEBE
0x18000ae78  mov     edx, [rbp+57h+var_D0]
0x18000ae7b  mov     rcx, r15
0x18000ae7e  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000ae84  test    al, al
0x18000ae86  jz      loc_1800279CD
0x18000ae8c  mov     rax, [r14+8]
0x18000ae90  mov     rcx, r15
0x18000ae93  mov     rbx, [rax+0A0h]
0x18000ae9a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000aea0  mov     rcx, [r14+8]
0x18000aea4  lea     r9, [rbp+57h+var_D0]
0x18000aea8  mov     r8, rax
0x18000aeab  lea     rdx, aHttpCookie; "HTTP_COOKIE"
0x18000aeb2  mov     rax, rbx
0x18000aeb5  mov     rcx, [rcx+8]
0x18000aeb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aebe  or      dword ptr [r14+34h], 40h
0x18000aec3  mov     rcx, r15
0x18000aec6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000aecc  mov     rbx, rax
0x18000aecf  test    rax, rax
0x18000aed2  jz      loc_18000B057
0x18000aed8  cmp     byte ptr [rax], 0
0x18000aedb  jz      loc_18000B057
0x18000aee1  cmp     dword ptr [r12+1Ch], 0
0x18000aee7  jz      loc_18000B04B
0x18000aeed  test    dword ptr [rsi+8], 8000h
0x18000aef4  mov     rcx, [rsi+18h]
0x18000aef8  jnz     loc_1800279DE
0x18000aefe  lea     rdx, [rcx+190h]; SubStr
0x18000af05  mov     rcx, rbx; Str
0x18000af08  call    cs:__imp_strstr
0x18000af0e  mov     rcx, rax
0x18000af11  test    rax, rax
0x18000af14  jz      loc_1800279FB
0x18000af1a  cmp     byte ptr [rcx+14h], 3Dh ; '='
0x18000af1e  jnz     short loc_18000AF4F
0x18000af20  mov     rax, rdi
0x18000af23  inc     rax
0x18000af26  cmp     byte ptr [rcx+rax+15h], 0
0x18000af2b  jnz     short loc_18000AF23
0x18000af2d  cmp     rax, 18h
0x18000af31  jb      short loc_18000AF4F
  ... truncated ...
```
