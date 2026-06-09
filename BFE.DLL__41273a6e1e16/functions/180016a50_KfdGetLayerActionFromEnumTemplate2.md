# KfdGetLayerActionFromEnumTemplate2

- ea: `0x180016a50`
- end: `0x1800177c7`
- name: `KfdGetLayerActionFromEnumTemplate2`
- size: `3447`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017aa0`

## callees

- `0x18000e7e0`
- `0x18000fb34`
- `0x180011510`
- `0x1800135ac`
- `0x180015674`
- `0x180016230`
- `0x180016740`
- `0x180016a50`
- `0x180017a28`
- `0x1800197d0`
- `0x18001d588`
- `0x180028e2c`
- `0x18004f7a0`
- `0x180055f04`
- `0x1800560f8`
- `0x18005aa60`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016ae5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001705d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800170fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800171dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017310`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016ae5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001705d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800170fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800171dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017310`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001709f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017142`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001721e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017352`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001770b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001709f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017142`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001721e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017352`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001770b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001776b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001776b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016b67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016b67`

## string_xrefs

- `0x180016cd0`: `GetLayerFromIdRead`
- `0x180016b06`: `FeAcquireWriteEngineLock`
- `0x18001751a`: `KfdGetLayerActionFromEnumTemplate2`
- `0x180017717`: `FeAcquireReadEngineLock`

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
  void *v50; // rbx
  int v51; // eax
  __int64 v52; // r12
  __int64 v53; // r15
  void *v54; // r15
  __int64 v55; // rcx
  __int64 v56; // rsi
  __int64 v57; // rdi
  void *v58; // rdi
  __int64 v59; // rcx
  __int64 v60; // r14
  __int64 v61; // rsi
  void *v62; // rsi
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
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
  v8 = *((unsigned int *)gWfpGlobal + 28);
  if ( (_DWORD)v8 == 2 )
  {
    matched = WfpReportSysErrorAsNtStatus(v8, "FeAcquireWriteEngineLock", 3221225473LL);
    if ( matched )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
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
      if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
  if ( (unsigned __int16)v5 >= *((_WORD *)gWfpGlobal + 156) )
  {
    v10 = 0;
    v28 = WfpReportSysErrorAsNtStatus(gWfpGlobal, "GetLayerFromIdRead", 3221225485LL);
    matched = v28;
    if ( v28 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v29, 0, (__int64)"GetLayerFromIdRead", v28);
      }
      if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
    v10 = *((_QWORD *)gWfpGlobal + 38) + 176 * v5;
    matched = 0;
  }
  for ( i = 0; i < *(_DWORD *)(v10 + 112); ++i )
  {
    v31 = *(_QWORD *)(v10 + 144) + 16LL * i;
    v32 = *(int *)(v31 + 8);
    if ( (_DWORD)v32 != 4 )
    {
      v66 = 0;
      matched = (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD, LPVOID *))gWfpGlobal + 7 * v32 + 18))(
                  *(_QWORD *)v31,
                  a2,
                  0,
                  &lpMem);
      if ( matched )
        break;
    }
  }
LABEL_40:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
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
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
            if ( (unsigned int)v53 >= *((_DWORD *)gWfpGlobal + 84)
              || (v54 = (void *)(*((_QWORD *)gWfpGlobal + 43) + 120 * v53), !*((_DWORD *)v54 + 1)) )
            {
              v54 = gFeCallout;
            }
            _InterlockedIncrement((volatile signed __int32 *)v54 + 16);
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
            if ( (*((unsigned int (__fastcall **)(__int64, _QWORD, __int64))v54 + 4))(1, 0, v39) )
              v52 = WfpReportSysErrorAsNtStatus(v55, "FeNotifyFilterEx", 3223453751LL);
            _InterlockedDecrement((volatile signed __int32 *)v54 + 16);
            if ( v52 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v17, 0, (__int64)"FeNotifyFilterEx", v52);
              }
              if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
          if ( (unsigned int)v49 >= *((_DWORD *)gWfpGlobal + 84)
            || (v50 = (void *)(*((_QWORD *)gWfpGlobal + 43) + 120 * v49), !*((_DWORD *)v50 + 1)) )
          {
            v50 = gFeCallout;
          }
          _InterlockedIncrement((volatile signed __int32 *)v50 + 16);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
          v51 = *((_DWORD *)v50 + 14);
          _InterlockedDecrement((volatile signed __int32 *)v50 + 16);
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
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
            if ( (unsigned int)v57 >= *((_DWORD *)gWfpGlobal + 84)
              || (v58 = (void *)(*((_QWORD *)gWfpGlobal + 43) + 120 * v57), !*((_DWORD *)v58 + 1)) )
            {
              v58 = gFeCallout;
            }
            _InterlockedIncrement((volatile signed __int32 *)v58 + 16);
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
            if ( (*((unsigned int (__fastcall **)(__int64, _QWORD, __int64))v58 + 4))(1, 0, v27) )
              v56 = WfpReportSysErrorAsNtStatus(v59, "FeNotifyFilterEx", 3223453751LL);
            _InterlockedDecrement((volatile signed __int32 *)v58 + 16);
            if ( v56 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v17, 0, (__int64)"FeNotifyFilterEx", v56);
              }
              if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
        if ( (unsigned int)v61 >= *((_DWORD *)gWfpGlobal + 84)
          || (v62 = (void *)(*((_QWORD *)gWfpGlobal + 43) + 120 * v61), !*((_DWORD *)v62 + 1)) )
        {
          v62 = gFeCallout;
        }
        _InterlockedIncrement((volatile signed __int32 *)v62 + 16);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)gWfpGlobal + 8));
        if ( (*((unsigned int (__fastcall **)(__int64, _QWORD, __int64))v62 + 4))(1, 0, v47) )
          v60 = WfpReportSysErrorAsNtStatus(v63, "FeNotifyFilterEx", 3223453751LL);
        _InterlockedDecrement((volatile signed __int32 *)v62 + 16);
        if ( v60 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v17, 0, (__int64)"FeNotifyFilterEx", v60);
          }
          if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
0x180016a50  mov     r11, rsp
0x180016a53  push    rbp
0x180016a54  push    rdi
0x180016a55  push    r15
0x180016a57  lea     rbp, [r11-5Fh]
0x180016a5b  sub     rsp, 100h
0x180016a62  mov     rax, cs:__security_cookie
0x180016a69  xor     rax, rsp
0x180016a6c  mov     [rbp+57h+var_38], rax
0x180016a70  mov     [r11+18h], rbx
0x180016a74  xorps   xmm0, xmm0
0x180016a77  movups  xmmword ptr [r9], xmm0
0x180016a7b  mov     [r11-20h], rsi
0x180016a7f  xor     eax, eax
0x180016a81  movups  xmmword ptr [r9+10h], xmm0
0x180016a86  mov     [r9+20h], rax
0x180016a8a  mov     r15, r9
0x180016a8d  mov     dword ptr [r9+18h], 1
0x180016a95  mov     dword ptr [r9], 8
0x180016a9c  movups  xmm0, xmmword ptr [r9]
0x180016aa0  movzx   ebx, cx
0x180016aa3  movups  xmm1, xmmword ptr [r9+10h]
0x180016aa8  mov     rcx, cs:gWfpGlobal
0x180016aaf  mov     [r11-28h], r12
0x180016ab3  add     rcx, 8; lpCriticalSection
0x180016ab7  movups  [rbp+57h+var_90], xmm0
0x180016abb  mov     [r11-30h], r13
0x180016abf  movsd   xmm0, qword ptr [r9+20h]
0x180016ac5  mov     [r11-38h], r14
0x180016ac9  mov     r14, rdx
0x180016acc  movsd   [rbp+57h+var_70], xmm0
0x180016ad1  mov     [rbp+57h+var_B0], r9
0x180016ad5  mov     [rbp+57h+var_98], rdx
0x180016ad9  mov     [rbp+57h+lpMem], 0
0x180016ae1  movups  [rbp+57h+var_80], xmm1
0x180016ae5  call    cs:__imp_EnterCriticalSection
0x180016aec  nop     dword ptr [rax+rax+00h]
0x180016af1  mov     rax, cs:gWfpGlobal
0x180016af8  mov     ecx, [rax+70h]
0x180016afb  cmp     ecx, 2
0x180016afe  jnz     short loc_180016B1E
0x180016b00  mov     r8d, 0C0000001h
0x180016b06  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x180016b0d  call    WfpReportSysErrorAsNtStatus
0x180016b12  mov     rdi, rax
0x180016b15  test    rax, rax
0x180016b18  jnz     loc_180017700
0x180016b1e  mov     rcx, cs:gWfpGlobal
0x180016b25  lea     r12, WPP_GLOBAL_Control
0x180016b2c  cmp     bx, [rcx+138h]
0x180016b33  jnb     loc_180016CD0
0x180016b39  imul    rsi, rbx, 0B0h
0x180016b40  add     rsi, [rcx+130h]
0x180016b47  xor     edi, edi
0x180016b49  jmp     loc_180016D32
0x180016b4e  cmp     cs:gWfpTrackHeapBytes, 0
0x180016b55  jnz     loc_18001775F
0x180016b5b  mov     rcx, cs:gWfpHeap; hHeap
0x180016b62  mov     r8, rbx; lpMem
0x180016b65  xor     edx, edx; dwFlags
0x180016b67  call    cs:__imp_HeapFree
0x180016b6e  nop     dword ptr [rax+rax+00h]
0x180016b73  mov     rbx, r13
0x180016b76  test    r13, r13
0x180016b79  jz      loc_180016ECB
0x180016b7f  movsx   rcx, word ptr [rbx+1Ah]
0x180016b84  mov     r15, [rbx+rcx*8+28h]
0x180016b89  inc     cx
0x180016b8c  mov     [rbx+1Ah], cx
0x180016b90  lock inc qword ptr [r15+10h]
0x180016b95  xor     edi, edi
0x180016b97  mov     [rbp+57h+lpMem], rbx
0x180016b9b  test    r15, r15
0x180016b9e  jz      loc_180016ED5
0x180016ba4  mov     rcx, [r15+18h]
0x180016ba8  lea     rsi, [r15+18h]
0x180016bac  mov     [rbp+57h+var_C0], rsi
0x180016bb0  mov     rcx, [rcx]
0x180016bb3  call    BfeFeIsZombieFilter
0x180016bb8  test    eax, eax
0x180016bba  jnz     loc_18001748F
0x180016bc0  mov     r11, [rsi]
0x180016bc3  movzx   eax, word ptr [r11+18h]
0x180016bc8  cmp     word ptr [rsp+110h+var_D8], ax
0x180016bcd  jz      loc_180016F4D
0x180016bd3  xor     r13d, r13d
0x180016bd6  mov     [rbp+57h+var_D0], edi
0x180016bd9  mov     [rsp+110h+var_E0], r13d
0x180016bde  mov     [rsp+110h+var_D8], eax
0x180016be2  mov     [rbp+57h+var_B8], edi
0x180016be5  mov     r12d, [r11+1Ch]
0x180016be9  test    r12d, r12d
0x180016bec  jz      loc_180017785
0x180016bf2  mov     r14, [rbp+57h+var_98]
0x180016bf6  xor     esi, esi
0x180016bf8  mov     r10d, [r14+0Ch]
0x180016bfc  xor     r13d, r13d
0x180016bff  lea     rdx, [rsi+rsi*2]
0x180016c03  xor     eax, eax
0x180016c05  lea     rbx, ds:0[rdx*8]
0x180016c0d  nop     dword ptr [rax]
0x180016c10  xor     edi, edi
0x180016c12  cmp     eax, r10d
0x180016c15  jnb     short loc_180016C36
0x180016c17  mov     rcx, [r11+20h]
0x180016c1b  lea     r9, [rax+rax*2]
0x180016c1f  mov     r8, [r14+10h]
0x180016c23  movzx   edx, word ptr [rbx+rcx]
0x180016c27  cmp     [r8+r9*8], dx
0x180016c2c  jz      loc_180016CB7
0x180016c32  inc     eax
0x180016c34  jmp     short loc_180016C10
0x180016c36  mov     r12d, 1
0x180016c3c  mov     rsi, [rbp+57h+var_C0]
0x180016c40  mov     eax, [r11+28h]
0x180016c44  test    r13d, r13d
0x180016c47  jnz     loc_180017044
0x180016c4d  cmp     eax, 1002h
0x180016c52  jnz     loc_180016FAB
0x180016c58  mov     [rbp+57h+var_B8], r12d
0x180016c5c  xor     dl, dl
0x180016c5e  lock inc qword ptr [r15+10h]
0x180016c63  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016c6a  lock xadd [r15+10h], rcx
0x180016c70  sub     rcx, 2
0x180016c74  mov     rax, rcx
0x180016c77  shr     rax, 20h
0x180016c7b  cmp     ecx, eax
0x180016c7d  jz      loc_1800174D2
0x180016c83  mov     rbx, [rsi]
0x180016c86  test    dword ptr [rbx+28h], 4000h
0x180016c8d  jnz     loc_1800171C5
0x180016c93  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180016c9a  lock xadd [r15+10h], rax
0x180016ca0  cmp     rax, 1
0x180016ca4  jnz     loc_180016DE2
0x180016caa  mov     rcx, r15
0x180016cad  call    FreeWFPFilter
0x180016cb2  jmp     loc_180016DE2
0x180016cb7  inc     esi
0x180016cb9  mov     r13d, 1
0x180016cbf  cmp     esi, r12d
0x180016cc2  jb      loc_180016BFC
0x180016cc8  mov     r12d, r13d
0x180016ccb  jmp     loc_180016C3C
0x180016cd0  lea     rbx, aGetlayerfromid_0; "GetLayerFromIdRead"
0x180016cd7  xor     esi, esi
0x180016cd9  mov     rdx, rbx
0x180016cdc  mov     r8d, 0C000000Dh
0x180016ce2  call    WfpReportSysErrorAsNtStatus
0x180016ce7  mov     rdi, rax
0x180016cea  test    rax, rax
0x180016ced  jz      short loc_180016D2D
0x180016cef  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cf6  cmp     rcx, r12
0x180016cf9  jz      short loc_180016D21
0x180016cfb  cmp     byte ptr [rcx+19h], 2
0x180016cff  jb      short loc_180016D21
0x180016d01  test    byte ptr [rcx+1Ch], 1
0x180016d05  jz      short loc_180016D21
0x180016d07  mov     rcx, [rcx+10h]
0x180016d0b  mov     edx, 1Ah
0x180016d10  mov     [rsp+110h+var_E8], edi
0x180016d14  xor     r9d, r9d
0x180016d17  mov     [rsp+110h+var_F0], rbx
0x180016d1c  call    WPP_SF_Ssd
0x180016d21  cmp     cs:gWfpLogUserModeErrors, esi
0x180016d27  jnz     loc_180017657
0x180016d2d  test    rdi, rdi
0x180016d30  jnz     short loc_180016D93
0x180016d32  mov     eax, [rsi+70h]
0x180016d35  xor     ebx, ebx
0x180016d37  test    eax, eax
0x180016d39  jz      short loc_180016D93
0x180016d3b  cmp     ebx, eax
0x180016d3d  jnb     short loc_180016D8A
0x180016d3f  mov     ecx, ebx
0x180016d41  shl     rcx, 4
0x180016d45  add     rcx, [rsi+90h]
0x180016d4c  movsxd  rax, dword ptr [rcx+8]
0x180016d50  cmp     eax, 4
0x180016d53  jz      short loc_180016D8A
0x180016d55  mov     rcx, [rcx]
0x180016d58  lea     r9, [rbp+57h+lpMem]
0x180016d5c  imul    rdx, rax, 38h ; '8'
0x180016d60  mov     rax, cs:gWfpGlobal
0x180016d67  xor     r8d, r8d
0x180016d6a  mov     dword ptr [rsp+110h+var_F0], 0
0x180016d72  mov     rax, [rdx+rax+90h]
0x180016d7a  mov     rdx, r14
0x180016d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d82  mov     rdi, rax
0x180016d85  test    rax, rax
0x180016d88  jnz     short loc_180016D93
0x180016d8a  mov     eax, [rsi+70h]
0x180016d8d  inc     ebx
0x180016d8f  cmp     ebx, eax
0x180016d91  jb      short loc_180016D3F
0x180016d93  mov     rcx, cs:gWfpGlobal
0x180016d9a  add     rcx, 8; lpCriticalSection
0x180016d9e  call    cs:__imp_LeaveCriticalSection
0x180016da5  nop     dword ptr [rax+rax+00h]
0x180016daa  test    byte ptr [r14+8], 2
0x180016daf  jz      short loc_180016DC6
0x180016db1  test    rdi, rdi
0x180016db4  jnz     loc_180017590
0x180016dba  mov     rcx, [rbp+57h+lpMem]
0x180016dbe  call    SortMatchList
0x180016dc3  mov     rdi, rax
0x180016dc6  test    rdi, rdi
0x180016dc9  jnz     loc_180017590
0x180016dcf  mov     eax, 0FFFFh
0x180016dd4  mov     [rbp+57h+var_D0], edi
0x180016dd7  mov     [rsp+110h+var_D8], eax
0x180016ddb  mov     [rbp+57h+var_B8], edi
0x180016dde  mov     [rsp+110h+var_E0], edi
0x180016de2  mov     rbx, [rbp+57h+lpMem]
0x180016de6  test    rbx, rbx
0x180016de9  jz      loc_180016ECB
0x180016def  movzx   edx, word ptr [rbx+18h]
0x180016df3  movsx   eax, word ptr [rbx+1Ah]
0x180016df7  lea     ecx, [rdx-1]
0x180016dfa  cmp     eax, ecx
0x180016dfc  jnz     loc_180016B7F
0x180016e02  mov     rax, [rbx+10h]
0x180016e06  xor     r13d, r13d
0x180016e09  test    rax, rax
0x180016e0c  mov     [rbp+57h+var_A0], rbx
0x180016e10  cmovnz  r13, rax
0x180016e14  xor     esi, esi
0x180016e16  xor     eax, eax
0x180016e18  mov     [rbp+57h+var_A8], r13
0x180016e1c  cmp     ax, dx
0x180016e1f  jnb     short loc_180016E97
0x180016e21  lea     r13, WPP_GLOBAL_Control
0x180016e28  mov     r15d, 1
0x180016e2e  xchg    ax, ax
0x180016e30  mov     rdi, [rbx+rsi*8+20h]
0x180016e35  xor     dl, dl
0x180016e37  lock inc qword ptr [rdi+10h]
0x180016e3c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016e43  lock xadd [rdi+10h], rcx
0x180016e49  sub     rcx, 2
0x180016e4d  mov     rax, rcx
0x180016e50  shr     rax, 20h
0x180016e54  cmp     ecx, eax
0x180016e56  jz      loc_18001746E
0x180016e5c  mov     r14, [rdi+18h]
0x180016e60  test    dword ptr [r14+28h], 4000h
0x180016e68  jnz     loc_1800170E4
0x180016e6e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180016e75  lock xadd [rdi+10h], rax
0x180016e7b  cmp     rax, 1
0x180016e7f  jnz     short loc_180016E89
0x180016e81  mov     rcx, rdi
0x180016e84  call    FreeWFPFilter
0x180016e89  movzx   eax, word ptr [rbx+18h]
0x180016e8d  inc     esi
0x180016e8f  cmp     esi, eax
0x180016e91  jb      short loc_180016E30
0x180016e93  mov     r13, [rbp+57h+var_A8]
0x180016e97  test    byte ptr [rbx+1Ch], 1
0x180016e9b  jnz     loc_180016B73
0x180016ea1  cmp     qword ptr [rbx+58h], 0
0x180016ea6  lea     rcx, [rbx+58h]
0x180016eaa  jnz     loc_180017755
0x180016eb0  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180016eb5  test    eax, eax
0x180016eb7  jz      loc_180016B4E
0x180016ebd  lea     rcx, [rbp+57h+var_A0]
0x180016ec1  call    WfpMemFree25B
0x180016ec6  jmp     loc_180016B73
0x180016ecb  mov     [rbp+57h+lpMem], 0
0x180016ed3  xor     edi, edi
0x180016ed5  mov     r15, [rbp+57h+var_B0]
0x180016ed9  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180016edd  mov     r14, [rsp+110h+var_30]
0x180016ee5  mov     r13, [rsp+110h+var_28]
0x180016eed  mov     r12, [rsp+110h+var_20]
0x180016ef5  mov     rsi, [rsp+0F8h]
0x180016efd  test    rcx, rcx
0x180016f00  jz      short loc_180016F13
0x180016f02  mov     rbx, [rcx+10h]
0x180016f06  call    FreeMatchBufEntry
0x180016f0b  mov     rcx, rbx
0x180016f0e  test    rbx, rbx
0x180016f11  jnz     short loc_180016F02
0x180016f13  mov     rbx, [rsp+110h+arg_10]
0x180016f1b  test    rdi, rdi
0x180016f1e  jnz     loc_18001751A
0x180016f24  cmp     dword ptr [r15], 8
0x180016f28  jnz     short loc_180016F31
0x180016f2a  mov     dword ptr [r15], 1002h
0x180016f31  mov     rax, rdi
0x180016f34  mov     rcx, [rbp+57h+var_38]
0x180016f38  xor     rcx, rsp; StackCookie
0x180016f3b  call    __security_check_cookie
0x180016f40  add     rsp, 100h
0x180016f47  pop     r15
0x180016f49  pop     rdi
  ... truncated ...
```
