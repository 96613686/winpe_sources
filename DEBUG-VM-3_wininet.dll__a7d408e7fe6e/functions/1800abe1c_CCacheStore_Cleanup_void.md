# CCacheStore::Cleanup(void)

- ea: `0x1800abe1c`
- end: `0x1800aca3e`
- name: `?Cleanup@CCacheStore@@AEAAJXZ`
- size: `3106`
- prototype: `__int64 __fastcall(CCacheStore *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180138c90`

## callees

- `0x180025910`
- `0x18007ec9c`
- `0x18007ed10`
- `0x180083dc4`
- `0x180086300`
- `0x1800a9974`
- `0x1800abe1c`
- `0x1800aca44`
- `0x1800acab8`
- `0x1800acdb0`
- `0x180136f78`
- `0x18014a7a0`
- `0x1801ad308`
- `0x1801d7bf8`
- `0x1801dcc90`
- `0x1801e1790`
- `0x1801e25fc`
- `0x1801e3c78`
- `0x1801e4988`
- `0x1801ea714`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ac2b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ac2b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ac27b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ac27b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800abe9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ac95f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800abe9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ac95f`
- `ESENT!JetRetrieveColumn` at `0x1800abfb5`
- `ESENT!JetRetrieveColumn` at `0x1800ac07d`
- `ESENT!JetRetrieveColumn` at `0x1800ac13f`
- `ESENT!JetRetrieveColumn` at `0x1800ac201`
- `ESENT!JetRetrieveColumn` at `0x1800ac3c7`
- `ESENT!JetRetrieveColumn` at `0x1800ac4d2`
- `ESENT!JetRetrieveColumn` at `0x1800ac592`
- `ESENT!JetRetrieveColumn` at `0x1800abfb5`
- `ESENT!JetRetrieveColumn` at `0x1800ac07d`
- `ESENT!JetRetrieveColumn` at `0x1800ac13f`
- `ESENT!JetRetrieveColumn` at `0x1800ac201`
- `ESENT!JetRetrieveColumn` at `0x1800ac3c7`
- `ESENT!JetRetrieveColumn` at `0x1800ac4d2`
- `ESENT!JetRetrieveColumn` at `0x1800ac592`
- `ESENT!JetRollback` at `0x1800ac2e7`
- `ESENT!JetRollback` at `0x1800ac60d`
- `ESENT!JetRollback` at `0x1800ac689`
- `ESENT!JetRollback` at `0x1800ac2e7`
- `ESENT!JetRollback` at `0x1800ac60d`
- `ESENT!JetRollback` at `0x1800ac689`
- `ESENT!JetBeginTransaction` at `0x1800abec6`
- `ESENT!JetBeginTransaction` at `0x1800ac2f1`
- `ESENT!JetBeginTransaction` at `0x1800abec6`
- `ESENT!JetBeginTransaction` at `0x1800ac2f1`
- `ESENT!JetMove` at `0x1800abf1f`
- `ESENT!JetMove` at `0x1800ac32e`
- `ESENT!JetMove` at `0x1800abf1f`
- `ESENT!JetMove` at `0x1800ac32e`

## pseudocode

```c
__int64 __fastcall CCacheStore::Cleanup(CCacheStore *this)
{
  int StringColumn; // ebx
  JET_SESID *v3; // rdi
  JET_ERR v4; // eax
  int v5; // r13d
  int v6; // ebx
  int v7; // esi
  JET_ERR v8; // eax
  JET_ERR v9; // eax
  char v10; // al
  JET_ERR v11; // eax
  char v12; // al
  JET_ERR v13; // eax
  char v14; // al
  JET_ERR v15; // eax
  unsigned int v16; // esi
  unsigned __int64 v17; // r15
  int v18; // eax
  unsigned __int64 v19; // rbx
  JET_ERR v20; // eax
  JET_ERR v21; // eax
  JET_ERR v22; // eax
  CCacheStore *v23; // rcx
  const unsigned __int16 *v24; // r8
  JET_ERR v25; // eax
  char v26; // al
  JET_ERR v27; // eax
  unsigned __int64 v28; // rcx
  unsigned int v29; // ecx
  __int64 v30; // rcx
  char v31; // r8
  struct CACHE_CLEANUP_STATS *v32; // r9
  unsigned int v33; // ecx
  CCacheStore *v35; // rcx
  const unsigned __int16 *v36; // r8
  unsigned __int64 v37; // rdi
  unsigned __int64 v38; // rcx
  __int32 v39; // r10d
  __int32 v40; // r11d
  __int64 v41; // rdx
  unsigned int *pcbActual; // [rsp+28h] [rbp-91h]
  int v43; // [rsp+48h] [rbp-71h]
  struct CJetContext *v44; // [rsp+50h] [rbp-69h] BYREF
  struct _FILETIME v45; // [rsp+58h] [rbp-61h]
  unsigned int v46; // [rsp+60h] [rbp-59h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-51h] BYREF
  int pvData; // [rsp+70h] [rbp-49h] BYREF
  unsigned __int64 v49; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int64 v50; // [rsp+80h] [rbp-39h] BYREF
  unsigned __int16 *v51[2]; // [rsp+88h] [rbp-31h] BYREF
  unsigned __int64 v52; // [rsp+98h] [rbp-21h] BYREF
  _QWORD v53[2]; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v54; // [rsp+B0h] [rbp-9h]

  SystemTimeAsFileTime.dwHighDateTime = 0;
  pvData = 0;
  v46 = 0;
  v51[0] = (unsigned __int16 *)&Data;
  v51[1] = 0;
  v52 = 0;
  v50 = 0;
  v49 = 0;
  v54 = 0;
  v44 = 0;
  v53[0] = &Data;
  v53[1] = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_(1036, 42, &WPP_97d300ac1e463af99b9229d7a7cae1bf_Traceguids);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  StringColumn = CJetContextList::AcquireContext(*((CJetContextList **)this + 40), &v44, 0);
  if ( StringColumn < 0 )
  {
    SystemTimeAsFileTime.dwHighDateTime = 1866;
    goto LABEL_104;
  }
  v3 = (JET_SESID *)v44;
  v4 = JetBeginTransaction(*((_QWORD *)v44 + 2));
  StringColumn = HRESULTFromJET_ERR(v4, 1);
  if ( StringColumn < 0 )
    goto LABEL_104;
  v5 = 0x80000000;
  v45 = SystemTimeAsFileTime;
  v6 = 0x80000000;
  v43 = 0;
  v7 = 0;
  while ( 1 )
  {
    if ( (unsigned int)CCacheStore::IsTerminating(this) )
    {
LABEL_102:
      StringColumn = 0;
LABEL_103:
      JetRollback(v3[2], 0);
      goto LABEL_104;
    }
    v8 = JetMove(v3[2], v3[4], v6, 0);
    if ( v8 == -1603 )
      break;
    StringColumn = HRESULTFromJET_ERR(v8, 1);
    if ( StringColumn < 0 )
      goto LABEL_103;
    SystemTimeAsFileTime.dwLowDateTime = 0;
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_dqd(1036, 17, (unsigned int)&WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 4, (__int64)&pvData);
    v9 = JetRetrieveColumn(
           v3[2],
           v3[4],
           *(_DWORD *)(*(_QWORD *)(v3[5] + 8) + 16LL),
           &pvData,
           4u,
           (unsigned int *)&SystemTimeAsFileTime,
           0,
           0);
    StringColumn = HRESULTFromJET_ERR(v9, 1);
    if ( StringColumn >= 0 )
    {
      if ( SystemTimeAsFileTime.dwLowDateTime == 4 )
        StringColumn = 0;
      else
        StringColumn = -2147418113;
    }
    v10 = BYTE1(xmmword_180266B60);
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    {
      WPP_SF_d(1036, 18, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)StringColumn);
      v10 = BYTE1(xmmword_180266B60);
    }
    if ( StringColumn < 0 )
    {
      SystemTimeAsFileTime.dwHighDateTime = 1892;
      goto LABEL_103;
    }
    if ( (pvData & 8) != 0 )
    {
      SystemTimeAsFileTime.dwLowDateTime = 0;
      if ( (v10 & 0x10) != 0 )
        WPP_SF_dqd(1036, 17, (unsigned int)&WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 5, (__int64)&v50);
      v11 = JetRetrieveColumn(
              v3[2],
              v3[4],
              *(_DWORD *)(*(_QWORD *)(v3[5] + 8) + 20LL),
              &v50,
              8u,
              (unsigned int *)&SystemTimeAsFileTime,
              0,
              0);
      StringColumn = HRESULTFromJET_ERR(v11, 1);
      if ( StringColumn >= 0 )
      {
        if ( SystemTimeAsFileTime.dwLowDateTime == 8 )
          StringColumn = 0;
        else
          StringColumn = -2147418113;
      }
      v12 = BYTE1(xmmword_180266B60);
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      {
        WPP_SF_d(1036, 18, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)StringColumn);
        v12 = BYTE1(xmmword_180266B60);
      }
      if ( StringColumn < 0 )
      {
        SystemTimeAsFileTime.dwHighDateTime = 1898;
        goto LABEL_103;
      }
      SystemTimeAsFileTime.dwLowDateTime = 0;
      if ( (v12 & 0x10) != 0 )
        WPP_SF_dqd(1036, 17, (unsigned int)&WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 6, (__int64)&v49);
      v13 = JetRetrieveColumn(
              v3[2],
              v3[4],
              *(_DWORD *)(*(_QWORD *)(v3[5] + 8) + 24LL),
              &v49,
              8u,
              (unsigned int *)&SystemTimeAsFileTime,
              0,
              0);
      StringColumn = HRESULTFromJET_ERR(v13, 1);
      if ( StringColumn >= 0 )
      {
        if ( SystemTimeAsFileTime.dwLowDateTime == 8 )
          StringColumn = 0;
        else
          StringColumn = -2147418113;
      }
      v14 = BYTE1(xmmword_180266B60);
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      {
        WPP_SF_d(1036, 18, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)StringColumn);
        v14 = BYTE1(xmmword_180266B60);
      }
      if ( StringColumn < 0 )
      {
        SystemTimeAsFileTime.dwHighDateTime = 1899;
        goto LABEL_103;
      }
      SystemTimeAsFileTime.dwLowDateTime = 0;
      if ( (v14 & 0x10) != 0 )
        WPP_SF_dqd(1036, 17, (unsigned int)&WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 3, (__int64)&v46);
      v15 = JetRetrieveColumn(
              v3[2],
              v3[4],
              *(_DWORD *)(*(_QWORD *)(v3[5] + 8) + 12LL),
              &v46,
              4u,
              (unsigned int *)&SystemTimeAsFileTime,
              0,
              0);
      StringColumn = HRESULTFromJET_ERR(v15, 1);
      if ( StringColumn >= 0 )
      {
        if ( SystemTimeAsFileTime.dwLowDateTime == 4 )
          StringColumn = 0;
        else
          StringColumn = -2147418113;
      }
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
        WPP_SF_d(1036, 18, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)StringColumn);
      if ( StringColumn < 0 )
      {
        SystemTimeAsFileTime.dwHighDateTime = 1900;
        goto LABEL_103;
      }
      v16 = v46;
      v17 = v49;
      v49 = 0;
      if ( v46 >= 2 )
      {
        StringColumn = -2147024809;
        SystemTimeAsFileTime.dwHighDateTime = 1902;
        goto LABEL_103;
      }
      v18 = 0;
      v19 = 0;
      if ( this != (CCacheStore *)-368LL )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
        v18 = 1;
      }
      if ( v16 )
      {
        if ( v16 == 1 )
          v19 = *((_QWORD *)this + 53);
      }
      else
      {
        v19 = *((_QWORD *)this + 51);
      }
      if ( !v19 )
        v19 = v17;
      v49 = v19;
      if ( v18 && this != (CCacheStore *)-368LL )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
        v19 = v49;
      }
      SystemTimeAsFileTime.dwLowDateTime = 0;
      if ( !v19 || v50 <= v19 )
        goto LABEL_56;
      StringColumn = CJetContext::GetStringColumn((CJetContext *)v3, 7u, (struct CWxString *)v53);
      if ( StringColumn < 0 )
      {
        SystemTimeAsFileTime.dwHighDateTime = 1913;
        goto LABEL_103;
      }
      v7 = 1;
      StringColumn = CJetContext::GetStringColumn((CJetContext *)v3, 1u, (struct CWxString *)v51);
      if ( StringColumn < 0 )
      {
        SystemTimeAsFileTime.dwHighDateTime = 1915;
        goto LABEL_103;
      }
      if ( (unsigned int)CCacheStore::IsPartitionOffline(v35, v51[0], v36) )
      {
        StringColumn = CJetContext::GetBasicColumn((CJetContext *)v3, 0, &v52, 8u);
        if ( StringColumn < 0 )
        {
          SystemTimeAsFileTime.dwHighDateTime = 1922;
          goto LABEL_103;
        }
        CCacheStore::CleanupContainer(this, v52, *((_DWORD *)this + 89), 0, 0, (struct CACHE_CLEANUP_STATS *)pcbActual);
        v43 = 1;
      }
      else
      {
LABEL_56:
        v7 = v43;
      }
    }
    v6 = 1;
  }
  JetRollback(v3[2], 0);
  v20 = JetBeginTransaction(v3[2]);
  StringColumn = HRESULTFromJET_ERR(v20, 1);
  if ( StringColumn < 0 )
    goto LABEL_104;
  while ( 1 )
  {
    do
    {
      do
      {
        if ( (unsigned int)CCacheStore::IsTerminating(this) )
          goto LABEL_102;
        v21 = JetMove(v3[2], v3[4], v5, 0);
        v5 = 1;
        if ( v21 == -1603 )
          goto LABEL_93;
        StringColumn = HRESULTFromJET_ERR(v21, 1);
        if ( StringColumn < 0 )
          goto LABEL_103;
        SystemTimeAsFileTime.dwLowDateTime = 0;
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_dqd(1036, 17, (unsigned int)&WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 4, (__int64)&pvData);
        v22 = JetRetrieveColumn(
                v3[2],
                v3[4],
                *(_DWORD *)(*(_QWORD *)(v3[5] + 8) + 16LL),
                &pvData,
                4u,
                (unsigned int *)&SystemTimeAsFileTime,
                0,
                0);
        StringColumn = HRESULTFromJET_ERR(v22, 1);
        if ( StringColumn >= 0 )
        {
          if ( SystemTimeAsFileTime.dwLowDateTime == 4 )
            StringColumn = 0;
          else
            StringColumn = -2147418113;
        }
        if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          WPP_SF_d(1036, 18, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)StringColumn);
        if ( StringColumn < 0 )
        {
          SystemTimeAsFileTime.dwHighDateTime = 1958;
          goto LABEL_103;
        }
      }
      while ( (pvData & 8) == 0 );
      StringColumn = CJetContext::GetStringColumn((CJetContext *)v3, 7u, (struct CWxString *)v53);
      if ( StringColumn < 0 )
      {
        SystemTimeAsFileTime.dwHighDateTime = 1968;
        goto LABEL_103;
      }
      StringColumn = CJetContext::GetStringColumn((CJetContext *)v3, 1u, (struct CWxString *)v51);
      if ( StringColumn < 0 )
      {
        SystemTimeAsFileTime.dwHighDateTime = 1970;
        goto LABEL_103;
      }
    }
    while ( !(unsigned int)CCacheStore::IsPartitionOffline(v23, v51[0], v24) );
    SystemTimeAsFileTime.dwLowDateTime = 0;
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_dqd(1036, 17, (unsigned int)&WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 5, (__int64)&v50);
    v25 = JetRetrieveColumn(
            v3[2],
            v3[4],
            *(_DWORD *)(*(_QWORD *)(v3[5] + 8) + 20LL),
            &v50,
            8u,
            (unsigned int *)&SystemTimeAsFileTime,
            0,
            0);
    StringColumn = HRESULTFromJET_ERR(v25, 1);
    if ( StringColumn >= 0 )
    {
      if ( SystemTimeAsFileTime.dwLowDateTime == 8 )
        StringColumn = 0;
      else
        StringColumn = -2147418113;
    }
    v26 = BYTE1(xmmword_180266B60);
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    {
      WPP_SF_d(1036, 18, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)StringColumn);
      v26 = BYTE1(xmmword_180266B60);
    }
    if ( StringColumn < 0 )
    {
      SystemTimeAsFileTime.dwHighDateTime = 1977;
      goto LABEL_103;
    }
    SystemTimeAsFileTime.dwLowDateTime = 0;
    if ( (v26 & 0x10) != 0 )
      WPP_SF_dqd(1036, 17, (unsigned int)&WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 3, (__int64)&v46);
    v27 = JetRetrieveColumn(
            v3[2],
            v3[4],
            *(_DWORD *)(*(_QWORD *)(v3[5] + 8) + 12LL),
            &v46,
            4u,
            (unsigned int *)&SystemTimeAsFileTime,
            0,
            0);
    StringColumn = HRESULTFromJET_ERR(v27, 1);
    if ( StringColumn >= 0 )
    {
      if ( SystemTimeAsFileTime.dwLowDateTime == 4 )
        StringColumn = 0;
      else
        StringColumn = -2147418113;
    }
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_d(1036, 18, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)StringColumn);
    if ( StringColumn < 0 )
    {
      SystemTimeAsFileTime.dwHighDateTime = 1978;
      goto LABEL_103;
    }
    v28 = *((_QWORD *)&v54 + v46);
    if ( v28 + v50 < v28 )
      break;
    *((_QWORD *)&v54 + v46) = v28 + v50;
  }
  *((_QWORD *)&v54 + v46) = -1;
LABEL_93:
  JetRollback(v3[2], 0);
  CCacheStore::ReleaseContainerContext(this, &v44);
  v29 = 0;
  v46 = 0;
  while ( 2 )
  {
    if ( v29 < 2 )
    {
      if ( (unsigned int)CCacheStore::IsTerminating(this) )
        goto LABEL_141;
      StringColumn = CCacheStore::GetTotalLimit(this, v46, &v49);
      if ( StringColumn < 0 )
      {
        SystemTimeAsFileTime.dwHighDateTime = 2008;
        goto LABEL_104;
      }
      v31 = BYTE1(xmmword_180266B60);
      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      {
        pcbActual = (unsigned int *)*((_QWORD *)&v54 + v46);
        WPP_SF_dII(v30, 43);
        v31 = BYTE1(xmmword_180266B60);
      }
      v32 = (struct CACHE_CLEANUP_STATS *)v49;
      if ( v49 )
      {
        v33 = v46;
        if ( *((_QWORD *)&v54 + v46) > v49 )
        {
          v37 = v49 * (unsigned int)(100 - *((_DWORD *)this + 89)) / 0x64;
          if ( (v31 & 0x10) != 0 )
          {
            HIDWORD(pcbActual) = (v49 * (unsigned int)(100 - *((_DWORD *)this + 89)) / 0x64) >> 32;
            WPP_SF_IdI(1036, 44, &WPP_97d300ac1e463af99b9229d7a7cae1bf_Traceguids);
            v33 = v46;
          }
          CCacheStore::CleanupContainerSet(this, v33, v37, v32);
          v7 = 1;
          goto LABEL_100;
        }
      }
      else
      {
LABEL_100:
        v33 = v46;
      }
      v29 = v33 + 1;
      v46 = v29;
      continue;
    }
    break;
  }
  if ( !v7 )
  {
LABEL_141:
    StringColumn = 0;
    goto LABEL_104;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v38 = *(_QWORD *)&v45 - CCacheStore::g_ullLastCleanup;
  CCacheStore::g_ullLastCleanup = (unsigned __int64)v45;
  v39 = _InterlockedExchange((volatile __int32 *)&CCacheStore::g_ulCacheReadCountSinceLastCleanup, 0);
  v40 = _InterlockedExchange((volatile __int32 *)&CCacheStore::g_ulCacheWriteCountSinceLastCleanup, 0);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
  {
    LODWORD(pcbActual) = v39;
    v41 = (v38 / 0xA * (unsigned __int128)0x624DD2F1A9FBE77uLL) >> 64;
    WPP_SF_IIdd(
      *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v45,
      45,
      (v41 + ((v38 / 0xA - v41) >> 1)) >> 9,
      (*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&v45) / 0xAuLL / 0x3E8,
      (v41 + ((v38 / 0xA - v41) >> 1)) >> 9,
      pcbActual,
      v40);
  }
LABEL_104:
  CCacheStore::ReleaseContainerContext(this, &v44);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qD(1036, 46, &WPP_97d300ac1e463af99b9229d7a7cae1bf_Traceguids, this, StringColumn);
  CWxString::_Release((CWxString *)v53);
  CWxString::_Release((CWxString *)v51);
  return (unsigned int)StringColumn;
}

```

## disassembly

```asm
0x1800abe1c  push    rbp
0x1800abe1e  push    rbx
0x1800abe1f  push    rsi
0x1800abe20  push    rdi
0x1800abe21  push    r12
0x1800abe23  push    r13
0x1800abe25  push    r14
0x1800abe27  push    r15
0x1800abe29  lea     rbp, [rsp-1Fh]
0x1800abe2e  sub     rsp, 0D8h
0x1800abe35  mov     rax, cs:__security_cookie
0x1800abe3c  xor     rax, rsp
0x1800abe3f  mov     [rbp+57h+var_50], rax
0x1800abe43  xor     r15d, r15d
0x1800abe46  lea     rax, Data
0x1800abe4d  xorps   xmm0, xmm0
0x1800abe50  mov     [rbp+57h+SystemTimeAsFileTime.dwHighDateTime], r15d
0x1800abe54  mov     [rbp+57h+pvData], r15d
0x1800abe58  mov     r14, rcx
0x1800abe5b  mov     [rbp+57h+var_B0], r15d
0x1800abe5f  mov     [rbp+57h+var_88], rax
0x1800abe63  mov     [rbp+57h+var_80], r15
0x1800abe67  mov     [rbp+57h+var_78], r15
0x1800abe6b  mov     [rbp+57h+var_90], r15
0x1800abe6f  mov     [rbp+57h+var_98], r15
0x1800abe73  movups  [rbp+57h+var_60], xmm0
0x1800abe77  mov     [rbp+57h+var_C0], r15
0x1800abe7b  mov     [rbp+57h+var_70], rax
0x1800abe7f  mov     [rbp+57h+var_68], r15
0x1800abe83  mov     r12b, 10h
0x1800abe86  test    byte ptr cs:xmmword_180266B60+1, r12b
0x1800abe8d  jnz     loc_1800AC7B0
0x1800abe93  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800abe97  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x1800abe9b  call    cs:__imp_GetSystemTimeAsFileTime
0x1800abea1  mov     rcx, [r14+140h]; this
0x1800abea8  lea     rdx, [rbp+57h+var_C0]; struct CJetContext **
0x1800abeac  xor     r8d, r8d; int *
0x1800abeaf  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800abeb4  mov     ebx, eax
0x1800abeb6  test    eax, eax
0x1800abeb8  js      loc_1800AC7CB
0x1800abebe  mov     rdi, [rbp+57h+var_C0]
0x1800abec2  mov     rcx, [rdi+10h]; sesid
0x1800abec6  call    cs:__imp_JetBeginTransaction
0x1800abecc  mov     ecx, eax; int
0x1800abece  mov     edx, 1; int
0x1800abed3  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800abed8  mov     ebx, eax
0x1800abeda  test    eax, eax
0x1800abedc  js      loc_1800AC692
0x1800abee2  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800abee6  lea     r12, [r14+170h]
0x1800abeed  mov     r13d, 80000000h
0x1800abef3  mov     [rbp+57h+var_B8], rax
0x1800abef7  mov     ebx, r13d
0x1800abefa  mov     [rbp+57h+var_C8], r15d
0x1800abefe  mov     esi, r15d
0x1800abf01  mov     rcx, r14; this
0x1800abf04  call    ?IsTerminating@CCacheStore@@QEAAHXZ; CCacheStore::IsTerminating(void)
0x1800abf09  test    eax, eax
0x1800abf0b  jnz     loc_1800AC680
0x1800abf11  mov     rdx, [rdi+20h]; tableid
0x1800abf15  xor     r9d, r9d; grbit
0x1800abf18  mov     rcx, [rdi+10h]; sesid
0x1800abf1c  mov     r8d, ebx; cRow
0x1800abf1f  call    cs:__imp_JetMove
0x1800abf25  cmp     eax, 0FFFFF9BDh
0x1800abf2a  jz      loc_1800AC2E1
0x1800abf30  mov     edx, 1; int
0x1800abf35  mov     ecx, eax; int
0x1800abf37  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800abf3c  mov     ebx, eax
0x1800abf3e  test    eax, eax
0x1800abf40  js      loc_1800AC683
0x1800abf46  mov     [rbp+57h+var_CC], r15d
0x1800abf4a  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15d
0x1800abf4e  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800abf55  jz      short loc_1800ABF82
0x1800abf57  mov     edx, 11h
0x1800abf5c  lea     rax, [rbp+57h+pvData]
0x1800abf60  mov     ecx, 40Ch
0x1800abf65  lea     r8d, [rdx-0Dh]
0x1800abf69  mov     dword ptr [rsp+110h+pcbActual], r8d
0x1800abf6e  mov     r9d, r8d
0x1800abf71  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800abf78  mov     qword ptr [rsp+110h+cbData], rax
0x1800abf7d  call    WPP_SF_dqd
0x1800abf82  mov     rax, [rdi+28h]
0x1800abf86  lea     r9, [rbp+57h+pvData]; pvData
0x1800abf8a  mov     rdx, [rdi+20h]; tableid
0x1800abf8e  mov     rcx, [rdi+10h]; sesid
0x1800abf92  mov     [rsp+110h+pretinfo], r15; pretinfo
0x1800abf97  mov     r8, [rax+8]
0x1800abf9b  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x1800abf9f  mov     [rsp+110h+grbit], r15d; grbit
0x1800abfa4  mov     [rsp+110h+pcbActual], rax; pcbActual
0x1800abfa9  mov     [rsp+110h+cbData], 4; cbData
0x1800abfb1  mov     r8d, [r8+10h]; columnid
0x1800abfb5  call    cs:__imp_JetRetrieveColumn
0x1800abfbb  mov     ecx, eax; int
0x1800abfbd  mov     edx, 1; int
0x1800abfc2  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800abfc7  mov     ebx, eax
0x1800abfc9  test    eax, eax
0x1800abfcb  js      short loc_1800ABFDA
0x1800abfcd  cmp     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 4
0x1800abfd1  jnz     loc_1800AC732
0x1800abfd7  mov     ebx, r15d
0x1800abfda  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800abfe0  test    al, 10h
0x1800abfe2  jz      short loc_1800AC003
0x1800abfe4  mov     edx, 12h
0x1800abfe9  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800abff0  mov     ecx, 40Ch
0x1800abff5  mov     r9d, ebx
0x1800abff8  call    WPP_SF_d
0x1800abffd  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800ac003  test    ebx, ebx
0x1800ac005  js      loc_1800AC89B
0x1800ac00b  mov     ebx, 8
0x1800ac010  test    byte ptr [rbp+57h+pvData], bl
0x1800ac013  jz      loc_1800AC2D7
0x1800ac019  mov     [rbp+57h+var_CC], r15d
0x1800ac01d  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15d
0x1800ac021  mov     sil, 10h
0x1800ac024  test    sil, al
0x1800ac027  jz      short loc_1800AC04E
0x1800ac029  lea     rax, [rbp+57h+var_90]
0x1800ac02d  mov     dword ptr [rsp+110h+pcbActual], ebx
0x1800ac031  lea     edx, [rbx+9]
0x1800ac034  mov     qword ptr [rsp+110h+cbData], rax
0x1800ac039  mov     ecx, 40Ch
0x1800ac03e  lea     r9d, [rbx-3]
0x1800ac042  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ac049  call    WPP_SF_dqd
0x1800ac04e  mov     rax, [rdi+28h]
0x1800ac052  lea     r9, [rbp+57h+var_90]; pvData
0x1800ac056  mov     rdx, [rdi+20h]; tableid
0x1800ac05a  mov     rcx, [rdi+10h]; sesid
0x1800ac05e  mov     [rsp+110h+pretinfo], r15; pretinfo
0x1800ac063  mov     r8, [rax+8]
0x1800ac067  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x1800ac06b  mov     [rsp+110h+grbit], r15d; grbit
0x1800ac070  mov     [rsp+110h+pcbActual], rax; pcbActual
0x1800ac075  mov     [rsp+110h+cbData], ebx; cbData
0x1800ac079  mov     r8d, [r8+14h]; columnid
0x1800ac07d  call    cs:__imp_JetRetrieveColumn
0x1800ac083  mov     ecx, eax; int
0x1800ac085  mov     edx, 1; int
0x1800ac08a  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ac08f  mov     ebx, eax
0x1800ac091  test    eax, eax
0x1800ac093  js      short loc_1800AC0A2
0x1800ac095  cmp     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 8
0x1800ac099  jnz     loc_1800AC765
0x1800ac09f  mov     ebx, r15d
0x1800ac0a2  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800ac0a8  test    sil, al
0x1800ac0ab  jz      short loc_1800AC0CC
0x1800ac0ad  mov     edx, 12h
0x1800ac0b2  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ac0b9  mov     ecx, 40Ch
0x1800ac0be  mov     r9d, ebx
0x1800ac0c1  call    WPP_SF_d
0x1800ac0c6  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800ac0cc  test    ebx, ebx
0x1800ac0ce  js      loc_1800AC6DF
0x1800ac0d4  mov     [rbp+57h+var_CC], r15d
0x1800ac0d8  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15d
0x1800ac0dc  test    sil, al
0x1800ac0df  jz      short loc_1800AC10C
0x1800ac0e1  mov     edx, 11h
0x1800ac0e6  mov     dword ptr [rsp+110h+pcbActual], 8
0x1800ac0ee  lea     rax, [rbp+57h+var_98]
0x1800ac0f2  mov     ecx, 40Ch
0x1800ac0f7  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ac0fe  mov     qword ptr [rsp+110h+cbData], rax
0x1800ac103  lea     r9d, [rdx-0Bh]
0x1800ac107  call    WPP_SF_dqd
0x1800ac10c  mov     rax, [rdi+28h]
0x1800ac110  lea     r9, [rbp+57h+var_98]; pvData
0x1800ac114  mov     rdx, [rdi+20h]; tableid
0x1800ac118  mov     rcx, [rdi+10h]; sesid
0x1800ac11c  mov     [rsp+110h+pretinfo], r15; pretinfo
0x1800ac121  mov     r8, [rax+8]
0x1800ac125  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x1800ac129  mov     [rsp+110h+grbit], r15d; grbit
0x1800ac12e  mov     [rsp+110h+pcbActual], rax; pcbActual
0x1800ac133  mov     [rsp+110h+cbData], 8; cbData
0x1800ac13b  mov     r8d, [r8+18h]; columnid
0x1800ac13f  call    cs:__imp_JetRetrieveColumn
0x1800ac145  mov     ecx, eax; int
0x1800ac147  mov     edx, 1; int
0x1800ac14c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ac151  mov     ebx, eax
0x1800ac153  test    eax, eax
0x1800ac155  js      short loc_1800AC164
0x1800ac157  cmp     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 8
0x1800ac15b  jnz     loc_1800AC776
0x1800ac161  mov     ebx, r15d
0x1800ac164  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800ac16a  test    sil, al
0x1800ac16d  jz      short loc_1800AC18E
0x1800ac16f  mov     edx, 12h
0x1800ac174  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ac17b  mov     ecx, 40Ch
0x1800ac180  mov     r9d, ebx
0x1800ac183  call    WPP_SF_d
0x1800ac188  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800ac18e  test    ebx, ebx
0x1800ac190  js      loc_1800AC88F
0x1800ac196  mov     [rbp+57h+var_CC], r15d
0x1800ac19a  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15d
0x1800ac19e  test    sil, al
0x1800ac1a1  jz      short loc_1800AC1CE
0x1800ac1a3  mov     edx, 11h
0x1800ac1a8  mov     dword ptr [rsp+110h+pcbActual], 4
0x1800ac1b0  lea     rax, [rbp+57h+var_B0]
0x1800ac1b4  mov     ecx, 40Ch
0x1800ac1b9  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ac1c0  mov     qword ptr [rsp+110h+cbData], rax
0x1800ac1c5  lea     r9d, [rdx-0Eh]
0x1800ac1c9  call    WPP_SF_dqd
0x1800ac1ce  mov     rax, [rdi+28h]
0x1800ac1d2  lea     r9, [rbp+57h+var_B0]; pvData
0x1800ac1d6  mov     rdx, [rdi+20h]; tableid
0x1800ac1da  mov     rcx, [rdi+10h]; sesid
0x1800ac1de  mov     [rsp+110h+pretinfo], r15; pretinfo
0x1800ac1e3  mov     r8, [rax+8]
0x1800ac1e7  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x1800ac1eb  mov     [rsp+110h+grbit], r15d; grbit
0x1800ac1f0  mov     [rsp+110h+pcbActual], rax; struct CACHE_CLEANUP_STATS *
0x1800ac1f5  mov     [rsp+110h+cbData], 4; cbData
0x1800ac1fd  mov     r8d, [r8+0Ch]; columnid
0x1800ac201  call    cs:__imp_JetRetrieveColumn
0x1800ac207  mov     ecx, eax; int
0x1800ac209  mov     edx, 1; int
0x1800ac20e  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ac213  mov     ebx, eax
0x1800ac215  test    eax, eax
0x1800ac217  js      short loc_1800AC226
0x1800ac219  cmp     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 4
0x1800ac21d  jnz     loc_1800AC787
0x1800ac223  mov     ebx, r15d
0x1800ac226  test    byte ptr cs:xmmword_180266B60+1, sil
0x1800ac22d  jz      short loc_1800AC248
0x1800ac22f  mov     edx, 12h
0x1800ac234  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ac23b  mov     ecx, 40Ch
0x1800ac240  mov     r9d, ebx
0x1800ac243  call    WPP_SF_d
0x1800ac248  test    ebx, ebx
0x1800ac24a  js      loc_1800AC715
0x1800ac250  mov     esi, [rbp+57h+var_B0]
0x1800ac253  mov     r15, [rbp+57h+var_98]
0x1800ac257  mov     [rbp+57h+var_CC], 0
0x1800ac25e  mov     [rbp+57h+var_98], 0
0x1800ac266  cmp     esi, 2
0x1800ac269  jnb     loc_1800AC877
0x1800ac26f  xor     eax, eax
0x1800ac271  xor     ebx, ebx
0x1800ac273  test    r12, r12
0x1800ac276  jz      short loc_1800AC284
0x1800ac278  mov     rcx, r12; lpCriticalSection
0x1800ac27b  call    cs:__imp_EnterCriticalSection
0x1800ac281  lea     eax, [rbx+1]
0x1800ac284  test    esi, esi
0x1800ac286  jz      short loc_1800AC296
0x1800ac288  cmp     esi, 1
0x1800ac28b  jnz     short loc_1800AC29D
0x1800ac28d  mov     rbx, [r14+1A8h]
0x1800ac294  jmp     short loc_1800AC29D
0x1800ac296  mov     rbx, [r14+198h]
0x1800ac29d  test    rbx, rbx
0x1800ac2a0  cmovz   rbx, r15
0x1800ac2a4  mov     [rbp+57h+var_98], rbx
0x1800ac2a8  xor     r15d, r15d
0x1800ac2ab  test    eax, eax
0x1800ac2ad  jz      short loc_1800AC2C1
0x1800ac2af  test    r12, r12
0x1800ac2b2  jz      short loc_1800AC2C1
0x1800ac2b4  mov     rcx, r12; lpCriticalSection
0x1800ac2b7  call    cs:__imp_LeaveCriticalSection
0x1800ac2bd  mov     rbx, [rbp+57h+var_98]
0x1800ac2c1  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15d
0x1800ac2c5  test    rbx, rbx
0x1800ac2c8  jz      short loc_1800AC2D4
0x1800ac2ca  cmp     [rbp+57h+var_90], rbx
0x1800ac2ce  ja      loc_1800AC7D7
0x1800ac2d4  mov     esi, [rbp+57h+var_C8]
0x1800ac2d7  mov     ebx, 1
0x1800ac2dc  jmp     loc_1800ABF01
0x1800ac2e1  mov     rcx, [rdi+10h]; sesid
0x1800ac2e5  xor     edx, edx; grbit
0x1800ac2e7  call    cs:__imp_JetRollback
0x1800ac2ed  mov     rcx, [rdi+10h]; sesid
0x1800ac2f1  call    cs:__imp_JetBeginTransaction
0x1800ac2f7  mov     ecx, eax; int
0x1800ac2f9  mov     edx, 1; int
  ... truncated ...
```
