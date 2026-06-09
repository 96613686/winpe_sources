# KfdGetLayerActionFromEnumTemplate2

- ea: `0x180015ec0`
- end: `0x180016bea`
- name: `KfdGetLayerActionFromEnumTemplate2`
- size: `3370`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016eb0`

## callees

- `0x18000e000`
- `0x18000f1a8`
- `0x180010ad0`
- `0x180012b54`
- `0x180014b78`
- `0x180015700`
- `0x180015bd0`
- `0x180015ec0`
- `0x180016e3c`
- `0x180018b74`
- `0x18001c7f4`
- `0x18002764c`
- `0x18004de84`
- `0x1800540ec`
- `0x1800542bc`
- `0x180058b30`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015f55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800164bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016551`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016624`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001674b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015f55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800164bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016551`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016624`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001674b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800161ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800164f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001658f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001665f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016787`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016b3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800161ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800164f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001658f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001665f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016787`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016b3a`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180016b94`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180016b94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015fd1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015fd1`

## string_xrefs

- `0x180016131`: `GetLayerFromIdRead`
- `0x180015f70`: `FeAcquireWriteEngineLock`
- `0x180016949`: `KfdGetLayerActionFromEnumTemplate2`
- `0x180016b40`: `FeAcquireReadEngineLock`

## pseudocode

```c
__int64 __fastcall KfdGetLayerActionFromEnumTemplate2(unsigned __int16 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _DWORD *v4; // r15
  __int64 v5; // rbx
  __int128 v6; // xmm1
  __int64 v8; // rcx
  __int64 matched; // rdi
  __int64 v10; // rsi
  char *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // r15
  _QWORD *v14; // rcx
  __int64 *v15; // rsi
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // r9d
  __int64 v19; // r11
  int v20; // eax
  unsigned int v21; // r12d
  __int64 v22; // rsi
  int v23; // r13d
  __int64 j; // rax
  int v25; // eax
  signed __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // r8
  unsigned int i; // ebx
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  _QWORD *v34; // rax
  _QWORD *v35; // r13
  __int64 v36; // rsi
  __int64 v37; // rdi
  signed __int64 v38; // rcx
  __int64 v39; // r14
  char *v40; // rcx
  _QWORD *v41; // rcx
  _QWORD *v42; // rbx
  signed __int64 v44; // rcx
  int v45; // r13d
  signed __int64 v46; // rcx
  __int64 v47; // rbx
  _DWORD *v48; // rax
  __int64 v49; // rbx
  __int64 v50; // rbx
  int v51; // eax
  __int64 v52; // r12
  __int64 v53; // r15
  __int64 v54; // r15
  __int64 v55; // rcx
  __int64 v56; // rsi
  __int64 v57; // rdi
  __int64 v58; // rdi
  __int64 v59; // rcx
  __int64 v60; // r14
  __int64 v61; // rsi
  __int64 v62; // rsi
  __int64 v63; // rcx
  int v64; // ecx
  __int64 v65; // r8
  int v66; // [rsp+28h] [rbp-99h]
  int v67; // [rsp+38h] [rbp-89h]
  int v68; // [rsp+40h] [rbp-81h] BYREF
  int v69; // [rsp+48h] [rbp-79h]
  LPVOID lpMem; // [rsp+50h] [rbp-71h] BYREF
  __int64 *v71; // [rsp+58h] [rbp-69h] BYREF
  int v72; // [rsp+60h] [rbp-61h]
  _DWORD *v73; // [rsp+68h] [rbp-59h]
  _QWORD *v74; // [rsp+70h] [rbp-51h]
  LPVOID v75; // [rsp+78h] [rbp-49h] BYREF
  __int64 v76; // [rsp+80h] [rbp-41h]
  _OWORD v77[2]; // [rsp+88h] [rbp-39h] BYREF
  __int64 v78; // [rsp+A8h] [rbp-19h]
  _BYTE v79[16]; // [rsp+B0h] [rbp-11h] BYREF
  const char *v80; // [rsp+C0h] [rbp-1h]
  __int64 v81; // [rsp+C8h] [rbp+7h]
  int *v82; // [rsp+D0h] [rbp+Fh]
  __int64 v83; // [rsp+D8h] [rbp+17h]

  *(_OWORD *)a4 = 0;
  *(_OWORD *)(a4 + 16) = 0;
  *(_QWORD *)(a4 + 32) = 0;
  v4 = (_DWORD *)a4;
  *(_DWORD *)(a4 + 24) = 1;
  *(_DWORD *)a4 = 8;
  v5 = a1;
  v6 = *(_OWORD *)(a4 + 16);
  v77[0] = *(_OWORD *)a4;
  v78 = *(_QWORD *)(a4 + 32);
  v73 = (_DWORD *)a4;
  v76 = a2;
  lpMem = 0;
  v77[1] = v6;
  EnterCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
  v8 = *(unsigned int *)(MEMORY[0x1800EF368][58] + 112LL);
  if ( (_DWORD)v8 == 2 )
  {
    matched = WfpReportSysErrorAsNtStatus(v8, "FeAcquireWriteEngineLock", 3221225473LL);
    if ( matched )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
      WfpReportError(matched, "FeAcquireReadEngineLock");
      FreeMatchBufListInternal(lpMem);
LABEL_150:
      lpMem = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v65, 0, (__int64)"FeEnumLayer", matched);
      }
      if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
      {
        v68 = matched;
        v82 = &v68;
        v80 = "FeEnumLayer";
        v81 = 12;
        v83 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v65,
          3,
          (__int64)v79);
      }
      goto LABEL_64;
    }
  }
  if ( (unsigned __int16)v5 >= *(_WORD *)(MEMORY[0x1800EF368][58] + 312LL) )
  {
    v10 = 0;
    v28 = WfpReportSysErrorAsNtStatus(MEMORY[0x1800EF368][58], "GetLayerFromIdRead", 3221225485LL);
    matched = v28;
    if ( v28 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v29, 0, (__int64)"GetLayerFromIdRead", v28);
      }
      if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
      {
        v68 = matched;
        v82 = &v68;
        v80 = "GetLayerFromIdRead";
        v81 = 19;
        v83 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v29,
          3,
          (__int64)v79);
        goto LABEL_40;
      }
    }
    if ( matched )
      goto LABEL_40;
  }
  else
  {
    v10 = *(_QWORD *)(MEMORY[0x1800EF368][58] + 304LL) + 176 * v5;
    matched = 0;
  }
  for ( i = 0; i < *(_DWORD *)(v10 + 112); ++i )
  {
    v31 = *(_QWORD *)(v10 + 144) + 16LL * i;
    v32 = *(int *)(v31 + 8);
    if ( (_DWORD)v32 != 4 )
    {
      v66 = 0;
      matched = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, LPVOID *))(56 * v32 + MEMORY[0x1800EF368][58] + 144))(
                  *(_QWORD *)v31,
                  a2,
                  0,
                  &lpMem);
      if ( matched )
        break;
    }
  }
LABEL_40:
  LeaveCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
  if ( (*(_BYTE *)(a2 + 8) & 2) != 0 )
  {
    if ( matched )
    {
LABEL_149:
      FreeMatchBufListInternal(lpMem);
      goto LABEL_150;
    }
    matched = SortMatchList(lpMem);
  }
  if ( matched )
    goto LABEL_149;
  v69 = 0;
  v68 = 0xFFFF;
  v72 = 0;
  v67 = 0;
  while ( 1 )
  {
    v11 = (char *)lpMem;
    if ( !lpMem )
      break;
    v33 = *((unsigned __int16 *)lpMem + 12);
    if ( *((__int16 *)lpMem + 13) == (_DWORD)v33 - 1 )
    {
      v34 = (_QWORD *)*((_QWORD *)lpMem + 2);
      v35 = 0;
      v75 = lpMem;
      if ( v34 )
        v35 = v34;
      v36 = 0;
      v74 = v35;
      if ( (_WORD)v33 )
      {
        do
        {
          v37 = *(_QWORD *)&v11[8 * v36 + 32];
          LOBYTE(v33) = 0;
          _InterlockedIncrement64((volatile signed __int64 *)(v37 + 16));
          v38 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v37 + 16), 0xFFFFFFFFFFFFFFFFuLL) - 2;
          if ( (_DWORD)v38 == HIDWORD(v38) )
          {
            _m_prefetchw((const void *)(v37 + 52));
            v33 = (_InterlockedOr((volatile signed __int32 *)(v37 + 52), 0x10u) & 0x10) == 0;
          }
          v39 = *(_QWORD *)(v37 + 24);
          if ( (*(_DWORD *)(v39 + 40) & 0x4000) != 0 && (_BYTE)v33 )
          {
            v52 = 0;
            v53 = *(unsigned int *)(v39 + 44);
            EnterCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
            if ( (unsigned int)v53 >= *(_DWORD *)(MEMORY[0x1800EF368][58] + 336LL)
              || (v54 = *(_QWORD *)(MEMORY[0x1800EF368][58] + 344LL) + 120 * v53, !*(_DWORD *)(v54 + 4)) )
            {
              v54 = MEMORY[0x1800EF368][5];
            }
            _InterlockedIncrement((volatile signed __int32 *)(v54 + 64));
            LeaveCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
            if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(v54 + 32))(1, 0, v39) )
              v52 = WfpReportSysErrorAsNtStatus(v55, "FeNotifyFilterEx", 3223453751LL);
            _InterlockedDecrement((volatile signed __int32 *)(v54 + 64));
            if ( v52 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v17, 0, (__int64)"FeNotifyFilterEx", v52);
              }
              if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
              {
                LODWORD(v71) = v52;
                v80 = "FeNotifyFilterEx";
                v81 = 17;
                v82 = (int *)&v71;
                v83 = 4;
                McGenEventWrite_EtwEventWriteTransfer(
                  &MICROSOFT_WFP_PROVIDER_Context,
                  (__int64)WFP_USERMODE_ERROR,
                  v17,
                  3,
                  (__int64)v79);
              }
            }
          }
          if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(v37 + 16), 0xFFFFFFFFFFFFFFFFuLL) == 1 )
            FreeWFPFilter(v37, v33);
          v36 = (unsigned int)(v36 + 1);
        }
        while ( (unsigned int)v36 < *((unsigned __int16 *)v11 + 12) );
        v35 = v74;
      }
      if ( (v11[28] & 1) == 0 )
      {
        v40 = v11 + 88;
        if ( *((_QWORD *)v11 + 11) )
          WfpMemFree(v40);
        if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(v40, v33, v17) )
        {
          WfpMemFree25B(&v75);
        }
        else
        {
          if ( gWfpTrackHeapBytes )
            _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v11));
          HeapFree(gWfpHeap, 0, v11);
        }
      }
      v11 = (char *)v35;
      if ( !v35 )
        break;
    }
    v12 = *((__int16 *)v11 + 13);
    v13 = *(_QWORD *)&v11[8 * v12 + 40];
    *((_WORD *)v11 + 13) = v12 + 1;
    _InterlockedIncrement64((volatile signed __int64 *)(v13 + 16));
    matched = 0;
    lpMem = v11;
    if ( !v13 )
      goto LABEL_63;
    v14 = *(_QWORD **)(v13 + 24);
    v15 = (__int64 *)(v13 + 24);
    v71 = (__int64 *)(v13 + 24);
    if ( (unsigned int)BfeFeIsZombieFilter(*v14) )
    {
      LOBYTE(v16) = 0;
      _InterlockedIncrement64((volatile signed __int64 *)(v13 + 16));
      v44 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v13 + 16), 0xFFFFFFFFFFFFFFFFuLL) - 2;
      if ( (_DWORD)v44 == HIDWORD(v44) )
      {
        _m_prefetchw((const void *)(v13 + 52));
        v44 = *(_DWORD *)(v13 + 52) | 0x10u;
        v16 = (_InterlockedOr((volatile signed __int32 *)(v13 + 52), 0x10u) & 0x10) == 0;
      }
      v17 = *v15;
      if ( (*(_DWORD *)(*v15 + 40) & 0x4000) != 0 )
      {
LABEL_74:
        if ( (_BYTE)v16 )
          FeNotifyFilterEx(v44, 0, v17, 1);
      }
LABEL_25:
      if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(v13 + 16), 0xFFFFFFFFFFFFFFFFuLL) == 1 )
        FreeWFPFilter(v13, v16);
    }
    else
    {
      v19 = *v15;
      v20 = *(unsigned __int16 *)(*v15 + 24);
      if ( (_WORD)v68 != (_WORD)v20 )
      {
        v69 = 0;
        v67 = 0;
        v68 = v20;
        v72 = 0;
        goto LABEL_13;
      }
      if ( v69 )
      {
        LOBYTE(v16) = 0;
        _InterlockedIncrement64((volatile signed __int64 *)(v13 + 16));
        v44 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v13 + 16), 0xFFFFFFFFFFFFFFFFuLL) - 2;
        if ( (_DWORD)v44 == HIDWORD(v44) )
        {
          _m_prefetchw((const void *)(v13 + 52));
          v44 = *(_DWORD *)(v13 + 52) | 0x10u;
          v16 = (_InterlockedOr((volatile signed __int32 *)(v13 + 52), 0x10u) & 0x10) == 0;
        }
        v17 = *v15;
        if ( (*(_DWORD *)(*v15 + 40) & 0x4000) != 0 )
          goto LABEL_74;
        goto LABEL_25;
      }
LABEL_13:
      v21 = *(_DWORD *)(v19 + 28);
      if ( v21 )
      {
        v22 = 0;
LABEL_15:
        v23 = 0;
        v16 = 3 * v22;
        for ( j = 0; ; j = (unsigned int)(j + 1) )
        {
          matched = 0;
          if ( (unsigned int)j >= *(_DWORD *)(v76 + 12) )
            break;
          v18 = 3 * j;
          v17 = *(_QWORD *)(v76 + 16);
          v16 = *(unsigned __int16 *)(24 * v22 + *(_QWORD *)(v19 + 32));
          if ( *(_WORD *)(v17 + 24 * j) == (_WORD)v16 )
          {
            v22 = (unsigned int)(v22 + 1);
            v23 = 1;
            if ( (unsigned int)v22 < v21 )
              goto LABEL_15;
            break;
          }
        }
        v15 = v71;
      }
      else
      {
        v23 = 1;
      }
      v25 = *(_DWORD *)(v19 + 40);
      if ( v23 )
      {
        if ( (v25 & 0x4000) != 0 )
        {
          v49 = *(unsigned int *)(v19 + 44);
          EnterCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
          if ( (unsigned int)v49 >= *(_DWORD *)(MEMORY[0x1800EF368][58] + 336LL)
            || (v50 = *(_QWORD *)(MEMORY[0x1800EF368][58] + 344LL) + 120 * v49, !*(_DWORD *)(v50 + 4)) )
          {
            v50 = MEMORY[0x1800EF368][5];
          }
          _InterlockedIncrement((volatile signed __int32 *)(v50 + 64));
          LeaveCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
          v51 = *(_DWORD *)(v50 + 56);
          _InterlockedDecrement((volatile signed __int32 *)(v50 + 64));
          v45 = v67;
          if ( (v51 & 1) != 0 || (*(_DWORD *)(*v15 + 40) & 0x1000) == 0 )
            goto LABEL_78;
          *v73 = 7;
        }
        else
        {
          if ( *v73 != 7 || v25 == 4097 )
            UpdateClassifyOut((unsigned int)v77, (_DWORD)v73, v13, v18, v66, 0);
          v45 = v67;
          v64 = *(_DWORD *)(*v15 + 40);
          if ( (v64 & 0x1000) == 0 )
            goto LABEL_78;
          if ( v64 == 4097 )
            v45 = 1;
          v67 = v45;
        }
        v69 = 1;
      }
      else
      {
        if ( v25 == 4098 )
        {
          v72 = 1;
          LOBYTE(v16) = 0;
          _InterlockedIncrement64((volatile signed __int64 *)(v13 + 16));
          v26 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v13 + 16), 0xFFFFFFFFFFFFFFFFuLL) - 2;
          if ( (_DWORD)v26 == HIDWORD(v26) )
          {
            _m_prefetchw((const void *)(v13 + 52));
            v16 = (_InterlockedOr((volatile signed __int32 *)(v13 + 52), 0x10u) & 0x10) == 0;
          }
          v27 = *v15;
          if ( (*(_DWORD *)(*v15 + 40) & 0x4000) != 0 && (_BYTE)v16 )
          {
            v56 = 0;
            v57 = *(unsigned int *)(v27 + 44);
            EnterCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
            if ( (unsigned int)v57 >= *(_DWORD *)(MEMORY[0x1800EF368][58] + 336LL)
              || (v58 = *(_QWORD *)(MEMORY[0x1800EF368][58] + 344LL) + 120 * v57, !*(_DWORD *)(v58 + 4)) )
            {
              v58 = MEMORY[0x1800EF368][5];
            }
            _InterlockedIncrement((volatile signed __int32 *)(v58 + 64));
            LeaveCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
            if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(v58 + 32))(1, 0, v27) )
              v56 = WfpReportSysErrorAsNtStatus(v59, "FeNotifyFilterEx", 3223453751LL);
            _InterlockedDecrement((volatile signed __int32 *)(v58 + 64));
            if ( v56 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v17, 0, (__int64)"FeNotifyFilterEx", v56);
              }
              if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
              {
                LODWORD(v71) = v56;
                v80 = "FeNotifyFilterEx";
                v81 = 17;
                v82 = (int *)&v71;
                v83 = 4;
                McGenEventWrite_EtwEventWriteTransfer(
                  &MICROSOFT_WFP_PROVIDER_Context,
                  (__int64)WFP_USERMODE_ERROR,
                  v17,
                  3,
                  (__int64)v79);
              }
            }
          }
          goto LABEL_25;
        }
        v45 = v67;
        if ( (v25 & 0x1000) != 0 )
          *v73 = 7;
      }
LABEL_78:
      LOBYTE(v16) = 0;
      _InterlockedIncrement64((volatile signed __int64 *)(v13 + 16));
      v46 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v13 + 16), 0xFFFFFFFFFFFFFFFFuLL) - 2;
      if ( (_DWORD)v46 == HIDWORD(v46) )
      {
        _m_prefetchw((const void *)(v13 + 52));
        v16 = (_InterlockedOr((volatile signed __int32 *)(v13 + 52), 0x10u) & 0x10) == 0;
      }
      v47 = *v15;
      if ( (*(_DWORD *)(*v15 + 40) & 0x4000) != 0 && (_BYTE)v16 )
      {
        v60 = 0;
        v61 = *(unsigned int *)(v47 + 44);
        EnterCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
        if ( (unsigned int)v61 >= *(_DWORD *)(MEMORY[0x1800EF368][58] + 336LL)
          || (v62 = *(_QWORD *)(MEMORY[0x1800EF368][58] + 344LL) + 120 * v61, !*(_DWORD *)(v62 + 4)) )
        {
          v62 = MEMORY[0x1800EF368][5];
        }
        _InterlockedIncrement((volatile signed __int32 *)(v62 + 64));
        LeaveCriticalSection((LPCRITICAL_SECTION)(MEMORY[0x1800EF368][58] + 8LL));
        if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(v62 + 32))(1, 0, v47) )
          v60 = WfpReportSysErrorAsNtStatus(v63, "FeNotifyFilterEx", 3223453751LL);
        _InterlockedDecrement((volatile signed __int32 *)(v62 + 64));
        if ( v60 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v17, 0, (__int64)"FeNotifyFilterEx", v60);
          }
          if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
          {
            LODWORD(v71) = v60;
            v80 = "FeNotifyFilterEx";
            v81 = 17;
            v82 = (int *)&v71;
            v83 = 4;
            McGenEventWrite_EtwEventWriteTransfer(
              &MICROSOFT_WFP_PROVIDER_Context,
              (__int64)WFP_USERMODE_ERROR,
              v17,
              3,
              (__int64)v79);
          }
        }
      }
      if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(v13 + 16), 0xFFFFFFFFFFFFFFFFuLL) == 1 )
        FreeWFPFilter(v13, v16);
      if ( v45 )
      {
        if ( !v72 )
          goto LABEL_63;
        v48 = v73;
        if ( *v73 == 4097 )
        {
          *v73 = 7;
          v48[6] = 1;
        }
      }
    }
  }
  lpMem = 0;
  matched = 0;
LABEL_63:
  v4 = v73;
LABEL_64:
  v41 = lpMem;
  if ( lpMem )
  {
    do
    {
      v42 = (_QWORD *)v41[2];
      FreeMatchBufEntry(v41);
      v41 = v42;
    }
    while ( v42 );
  }
  if ( matched )
  {
    *v4 = 7;
    WfpReportError(matched, "KfdGetLayerActionFromEnumTemplate2");
  }
  else if ( *v4 == 8 )
  {
    *v4 = 4098;
  }
  return matched;
}

```

## disassembly

```asm
0x180015ec0  mov     r11, rsp
0x180015ec3  push    rbp
0x180015ec4  push    rdi
0x180015ec5  push    r15
0x180015ec7  lea     rbp, [r11-5Fh]
0x180015ecb  sub     rsp, 100h
0x180015ed2  mov     rax, cs:__security_cookie
0x180015ed9  xor     rax, rsp
0x180015edc  mov     [rbp+57h+var_38], rax
0x180015ee0  mov     [r11+18h], rbx
0x180015ee4  xorps   xmm0, xmm0
0x180015ee7  movups  xmmword ptr [r9], xmm0
0x180015eeb  mov     [r11-20h], rsi
0x180015eef  xor     eax, eax
0x180015ef1  movups  xmmword ptr [r9+10h], xmm0
0x180015ef6  mov     [r9+20h], rax
0x180015efa  mov     r15, r9
0x180015efd  mov     dword ptr [r9+18h], 1
0x180015f05  mov     dword ptr [r9], 8
0x180015f0c  movups  xmm0, xmmword ptr [r9]
0x180015f10  movzx   ebx, cx
0x180015f13  movups  xmm1, xmmword ptr [r9+10h]
0x180015f18  mov     rcx, cs:1800EF538h
0x180015f1f  mov     [r11-28h], r12
0x180015f23  add     rcx, 8; lpCriticalSection
0x180015f27  movups  [rbp+57h+var_90], xmm0
0x180015f2b  mov     [r11-30h], r13
0x180015f2f  movsd   xmm0, qword ptr [r9+20h]
0x180015f35  mov     [r11-38h], r14
0x180015f39  mov     r14, rdx
0x180015f3c  movsd   [rbp+57h+var_70], xmm0
0x180015f41  mov     [rbp+57h+var_B0], r9
0x180015f45  mov     [rbp+57h+var_98], rdx
0x180015f49  mov     [rbp+57h+lpMem], 0
0x180015f51  movups  [rbp+57h+var_80], xmm1
0x180015f55  call    cs:__imp_EnterCriticalSection
0x180015f5b  mov     rax, cs:1800EF538h
0x180015f62  mov     ecx, [rax+70h]
0x180015f65  cmp     ecx, 2
0x180015f68  jnz     short loc_180015F88
0x180015f6a  mov     r8d, 0C0000001h
0x180015f70  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x180015f77  call    WfpReportSysErrorAsNtStatus
0x180015f7c  mov     rdi, rax
0x180015f7f  test    rax, rax
0x180015f82  jnz     loc_180016B2F
0x180015f88  mov     rcx, cs:1800EF538h
0x180015f8f  lea     r12, WPP_GLOBAL_Control
0x180015f96  cmp     bx, [rcx+138h]
0x180015f9d  jnb     loc_180016131
0x180015fa3  imul    rsi, rbx, 0B0h
0x180015faa  add     rsi, [rcx+130h]
0x180015fb1  xor     edi, edi
0x180015fb3  jmp     loc_180016193
0x180015fb8  cmp     cs:gWfpTrackHeapBytes, 0
0x180015fbf  jnz     loc_180016B88
0x180015fc5  mov     rcx, cs:gWfpHeap; hHeap
0x180015fcc  mov     r8, rbx; lpMem
0x180015fcf  xor     edx, edx; dwFlags
0x180015fd1  call    cs:__imp_HeapFree
0x180015fd7  mov     rbx, r13
0x180015fda  test    r13, r13
0x180015fdd  jz      loc_18001632B
0x180015fe3  movsx   rcx, word ptr [rbx+1Ah]
0x180015fe8  mov     r15, [rbx+rcx*8+28h]
0x180015fed  inc     cx
0x180015ff0  mov     [rbx+1Ah], cx
0x180015ff4  lock inc qword ptr [r15+10h]
0x180015ff9  xor     edi, edi
0x180015ffb  mov     [rbp+57h+lpMem], rbx
0x180015fff  test    r15, r15
0x180016002  jz      loc_180016335
0x180016008  mov     rcx, [r15+18h]
0x18001600c  lea     rsi, [r15+18h]
0x180016010  mov     [rbp+57h+var_C0], rsi
0x180016014  mov     rcx, [rcx]
0x180016017  call    BfeFeIsZombieFilter
0x18001601c  test    eax, eax
0x18001601e  jnz     loc_1800168BE
0x180016024  mov     r11, [rsi]
0x180016027  movzx   eax, word ptr [r11+18h]
0x18001602c  cmp     word ptr [rsp+110h+var_D8], ax
0x180016031  jz      loc_1800163AC
0x180016037  xor     r13d, r13d
0x18001603a  mov     [rbp+57h+var_D0], edi
0x18001603d  mov     [rsp+110h+var_E0], r13d
0x180016042  mov     [rsp+110h+var_D8], eax
0x180016046  mov     [rbp+57h+var_B8], edi
0x180016049  mov     r12d, [r11+1Ch]
0x18001604d  test    r12d, r12d
0x180016050  jz      loc_180016BA8
0x180016056  mov     r14, [rbp+57h+var_98]
0x18001605a  xor     esi, esi
0x18001605c  mov     r10d, [r14+0Ch]
0x180016060  xor     r13d, r13d
0x180016063  lea     rdx, [rsi+rsi*2]
0x180016067  xor     eax, eax
0x180016069  lea     rbx, ds:0[rdx*8]
0x180016071  xor     edi, edi
0x180016073  cmp     eax, r10d
0x180016076  jnb     short loc_180016097
0x180016078  mov     rcx, [r11+20h]
0x18001607c  lea     r9, [rax+rax*2]
0x180016080  mov     r8, [r14+10h]
0x180016084  movzx   edx, word ptr [rbx+rcx]
0x180016088  cmp     [r8+r9*8], dx
0x18001608d  jz      loc_180016118
0x180016093  inc     eax
0x180016095  jmp     short loc_180016071
0x180016097  mov     r12d, 1
0x18001609d  mov     rsi, [rbp+57h+var_C0]
0x1800160a1  mov     eax, [r11+28h]
0x1800160a5  test    r13d, r13d
0x1800160a8  jnz     loc_1800164A3
0x1800160ae  cmp     eax, 1002h
0x1800160b3  jnz     loc_18001640A
0x1800160b9  mov     [rbp+57h+var_B8], r12d
0x1800160bd  xor     dl, dl
0x1800160bf  lock inc qword ptr [r15+10h]
0x1800160c4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800160cb  lock xadd [r15+10h], rcx
0x1800160d1  sub     rcx, 2
0x1800160d5  mov     rax, rcx
0x1800160d8  shr     rax, 20h
0x1800160dc  cmp     ecx, eax
0x1800160de  jz      loc_180016901
0x1800160e4  mov     rbx, [rsi]
0x1800160e7  test    dword ptr [rbx+28h], 4000h
0x1800160ee  jnz     loc_18001660C
0x1800160f4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800160fb  lock xadd [r15+10h], rax
0x180016101  cmp     rax, 1
0x180016105  jnz     loc_180016240
0x18001610b  mov     rcx, r15
0x18001610e  call    FreeWFPFilter
0x180016113  jmp     loc_180016240
0x180016118  inc     esi
0x18001611a  mov     r13d, 1
0x180016120  cmp     esi, r12d
0x180016123  jb      loc_180016060
0x180016129  mov     r12d, r13d
0x18001612c  jmp     loc_18001609D
0x180016131  lea     rbx, aGetlayerfromid_0; "GetLayerFromIdRead"
0x180016138  xor     esi, esi
0x18001613a  mov     rdx, rbx
0x18001613d  mov     r8d, 0C000000Dh
0x180016143  call    WfpReportSysErrorAsNtStatus
0x180016148  mov     rdi, rax
0x18001614b  test    rax, rax
0x18001614e  jz      short loc_18001618E
0x180016150  mov     rcx, cs:WPP_GLOBAL_Control
0x180016157  cmp     rcx, r12
0x18001615a  jz      short loc_180016182
0x18001615c  cmp     byte ptr [rcx+19h], 2
0x180016160  jb      short loc_180016182
0x180016162  test    byte ptr [rcx+1Ch], 1
0x180016166  jz      short loc_180016182
0x180016168  mov     rcx, [rcx+10h]
0x18001616c  mov     edx, 1Ah
0x180016171  mov     [rsp+110h+var_E8], edi
0x180016175  xor     r9d, r9d
0x180016178  mov     [rsp+110h+var_F0], rbx
0x18001617d  call    WPP_SF_Ssd
0x180016182  cmp     cs:1800EF078h, esi
0x180016188  jnz     loc_180016A86
0x18001618e  test    rdi, rdi
0x180016191  jnz     short loc_1800161F4
0x180016193  mov     eax, [rsi+70h]
0x180016196  xor     ebx, ebx
0x180016198  test    eax, eax
0x18001619a  jz      short loc_1800161F4
0x18001619c  cmp     ebx, eax
0x18001619e  jnb     short loc_1800161EB
0x1800161a0  mov     ecx, ebx
0x1800161a2  shl     rcx, 4
0x1800161a6  add     rcx, [rsi+90h]
0x1800161ad  movsxd  rax, dword ptr [rcx+8]
0x1800161b1  cmp     eax, 4
0x1800161b4  jz      short loc_1800161EB
0x1800161b6  mov     rcx, [rcx]
0x1800161b9  lea     r9, [rbp+57h+lpMem]
0x1800161bd  imul    rdx, rax, 38h ; '8'
0x1800161c1  mov     rax, cs:1800EF538h
0x1800161c8  xor     r8d, r8d
0x1800161cb  mov     dword ptr [rsp+110h+var_F0], 0
0x1800161d3  mov     rax, [rdx+rax+90h]
0x1800161db  mov     rdx, r14
0x1800161de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161e3  mov     rdi, rax
0x1800161e6  test    rax, rax
0x1800161e9  jnz     short loc_1800161F4
0x1800161eb  mov     eax, [rsi+70h]
0x1800161ee  inc     ebx
0x1800161f0  cmp     ebx, eax
0x1800161f2  jb      short loc_1800161A0
0x1800161f4  mov     rcx, cs:1800EF538h
0x1800161fb  add     rcx, 8; lpCriticalSection
0x1800161ff  call    cs:__imp_LeaveCriticalSection
0x180016205  test    byte ptr [r14+8], 2
0x18001620a  jz      short loc_180016221
0x18001620c  test    rdi, rdi
0x18001620f  jnz     loc_1800169BF
0x180016215  mov     rcx, [rbp+57h+lpMem]
0x180016219  call    SortMatchList
0x18001621e  mov     rdi, rax
0x180016221  test    rdi, rdi
0x180016224  jnz     loc_1800169BF
0x18001622a  mov     eax, 0FFFFh
0x18001622f  mov     [rbp+57h+var_D0], edi
0x180016232  mov     [rsp+110h+var_D8], eax
0x180016236  mov     [rbp+57h+var_B8], edi
0x180016239  mov     [rsp+110h+var_E0], edi
0x18001623d  nop     dword ptr [rax]
0x180016240  mov     rbx, [rbp+57h+lpMem]
0x180016244  test    rbx, rbx
0x180016247  jz      loc_18001632B
0x18001624d  movzx   edx, word ptr [rbx+18h]
0x180016251  movsx   eax, word ptr [rbx+1Ah]
0x180016255  lea     ecx, [rdx-1]
0x180016258  cmp     eax, ecx
0x18001625a  jnz     loc_180015FE3
0x180016260  mov     rax, [rbx+10h]
0x180016264  xor     r13d, r13d
0x180016267  test    rax, rax
0x18001626a  mov     [rbp+57h+var_A0], rbx
0x18001626e  cmovnz  r13, rax
0x180016272  xor     esi, esi
0x180016274  xor     eax, eax
0x180016276  mov     [rbp+57h+var_A8], r13
0x18001627a  cmp     ax, dx
0x18001627d  jnb     short loc_1800162F7
0x18001627f  lea     r13, WPP_GLOBAL_Control
0x180016286  mov     r15d, 1
0x18001628c  nop     dword ptr [rax+00h]
0x180016290  mov     rdi, [rbx+rsi*8+20h]
0x180016295  xor     dl, dl
0x180016297  lock inc qword ptr [rdi+10h]
0x18001629c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800162a3  lock xadd [rdi+10h], rcx
0x1800162a9  sub     rcx, 2
0x1800162ad  mov     rax, rcx
0x1800162b0  shr     rax, 20h
0x1800162b4  cmp     ecx, eax
0x1800162b6  jz      loc_18001689D
0x1800162bc  mov     r14, [rdi+18h]
0x1800162c0  test    dword ptr [r14+28h], 4000h
0x1800162c8  jnz     loc_180016537
0x1800162ce  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800162d5  lock xadd [rdi+10h], rax
0x1800162db  cmp     rax, 1
0x1800162df  jnz     short loc_1800162E9
0x1800162e1  mov     rcx, rdi
0x1800162e4  call    FreeWFPFilter
0x1800162e9  movzx   eax, word ptr [rbx+18h]
0x1800162ed  inc     esi
0x1800162ef  cmp     esi, eax
0x1800162f1  jb      short loc_180016290
0x1800162f3  mov     r13, [rbp+57h+var_A8]
0x1800162f7  test    byte ptr [rbx+1Ch], 1
0x1800162fb  jnz     loc_180015FD7
0x180016301  cmp     qword ptr [rbx+58h], 0
0x180016306  lea     rcx, [rbx+58h]
0x18001630a  jnz     loc_180016B7E
0x180016310  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180016315  test    eax, eax
0x180016317  jz      loc_180015FB8
0x18001631d  lea     rcx, [rbp+57h+var_A0]
0x180016321  call    WfpMemFree25B
0x180016326  jmp     loc_180015FD7
0x18001632b  mov     [rbp+57h+lpMem], 0
0x180016333  xor     edi, edi
0x180016335  mov     r15, [rbp+57h+var_B0]
0x180016339  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18001633d  mov     r14, [rsp+110h+var_30]
0x180016345  mov     r13, [rsp+110h+var_28]
0x18001634d  mov     r12, [rsp+110h+var_20]
0x180016355  mov     rsi, [rsp+0F8h]
0x18001635d  test    rcx, rcx
0x180016360  jz      short loc_180016373
0x180016362  mov     rbx, [rcx+10h]
0x180016366  call    FreeMatchBufEntry
0x18001636b  mov     rcx, rbx
0x18001636e  test    rbx, rbx
0x180016371  jnz     short loc_180016362
0x180016373  mov     rbx, [rsp+110h+arg_10]
0x18001637b  test    rdi, rdi
0x18001637e  jnz     loc_180016949
0x180016384  cmp     dword ptr [r15], 8
0x180016388  jnz     short loc_180016391
0x18001638a  mov     dword ptr [r15], 1002h
0x180016391  mov     rax, rdi
0x180016394  mov     rcx, [rbp+57h+var_38]
0x180016398  xor     rcx, rsp; StackCookie
0x18001639b  call    __security_check_cookie
0x1800163a0  add     rsp, 100h
0x1800163a7  pop     r15
0x1800163a9  pop     rdi
0x1800163aa  pop     rbp
0x1800163ab  retn
0x1800163ac  cmp     [rbp+57h+var_D0], edi
  ... truncated ...
```
