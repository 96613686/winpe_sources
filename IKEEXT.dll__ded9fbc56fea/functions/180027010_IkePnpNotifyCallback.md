# IkePnpNotifyCallback

- ea: `0x180027010`
- end: `0x180027a7b`
- name: `IkePnpNotifyCallback`
- size: `2667`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180006df0`
- `0x180010db0`
- `0x180011680`
- `0x180027010`
- `0x18004882c`
- `0x180050850`
- `0x1800529a4`
- `0x18005bc40`
- `0x180110d3c`
- `0x180117fa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800270ab`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800270f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027209`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027242`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800272a3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800272e8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027412`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002744c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800274a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800274eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800275d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800276eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027943`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027988`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800270ab`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800270f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027209`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027242`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800272a3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800272e8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027412`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002744c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800274a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800274eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800275d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800276eb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027943`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027988`
- `ntdll!EtwEventWriteTransfer` at `0x1800271bf`
- `ntdll!EtwEventWriteTransfer` at `0x1800273ba`
- `ntdll!EtwEventWriteTransfer` at `0x180027a55`
- `ntdll!EtwEventWriteTransfer` at `0x1800271bf`
- `ntdll!EtwEventWriteTransfer` at `0x1800273ba`
- `ntdll!EtwEventWriteTransfer` at `0x180027a55`
- `ntdll!RtlNtStatusToDosError` at `0x180027617`
- `ntdll!RtlNtStatusToDosError` at `0x18002772b`
- `ntdll!RtlNtStatusToDosError` at `0x180027617`
- `ntdll!RtlNtStatusToDosError` at `0x18002772b`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800278ce`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800278ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027890`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800278e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027890`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800278e9`

## string_xrefs

- `0x1800277d1`: `WfpBufferCopy`

## pseudocode

```c
__int64 __fastcall IkePnpNotifyCallback(_DWORD *Src)
{
  void *v2; // r14
  __int64 v3; // rbx
  LPCRITICAL_SECTION v4; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v7; // rcx
  DWORD v8; // ecx
  char *v9; // rax
  const WCHAR *v10; // rdx
  __int64 v11; // rax
  bool v12; // zf
  int v13; // eax
  _QWORD *v14; // rcx
  LPCRITICAL_SECTION v15; // rdx
  DWORD v16; // eax
  LPVOID v17; // rax
  LPVOID v18; // r8
  __int64 v19; // rdi
  DWORD v20; // eax
  __int64 *v21; // rax
  __int64 v22; // r9
  LPCRITICAL_SECTION v23; // rax
  DWORD v24; // ecx
  __int64 *v25; // rax
  __int64 v26; // rcx
  DWORD v27; // ecx
  char *v28; // rax
  const WCHAR *v29; // rdx
  __int64 v30; // rax
  int v31; // eax
  LPCRITICAL_SECTION v32; // r8
  _QWORD *v33; // rcx
  DWORD v34; // eax
  LPVOID v35; // rax
  LPVOID v36; // rdx
  __int64 v37; // rdi
  DWORD v38; // eax
  __int64 *v39; // rax
  __int64 v40; // r9
  __int64 result; // rax
  LPCRITICAL_SECTION v42; // rax
  DWORD v43; // ecx
  __int64 *v44; // rax
  __int64 v45; // rcx
  DWORD v46; // ecx
  char *v47; // rax
  const WCHAR *v48; // rdx
  int v49; // ebx
  char *v50; // rax
  unsigned int v51; // ecx
  int v52; // esi
  _QWORD *v53; // rcx
  DWORD v54; // eax
  LPVOID v55; // rax
  LPVOID v56; // rdx
  __int64 v57; // rcx
  int v58; // r9d
  ULONG v59; // eax
  int v60; // r8d
  __int64 v61; // rdi
  _QWORD *v62; // rcx
  DWORD v63; // eax
  LPVOID v64; // rax
  LPVOID v65; // rdx
  __int64 v66; // rcx
  int v67; // r9d
  ULONG v68; // eax
  int v69; // r8d
  size_t v70; // rsi
  __int64 v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  int IsEnabledDeviceUsageNoInline; // eax
  BOOL v76; // eax
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  LPCRITICAL_SECTION v80; // rax
  DWORD v81; // ecx
  __int64 *v82; // rax
  __int64 v83; // rcx
  DWORD v84; // ecx
  char *v85; // rax
  const WCHAR *v86; // rdx
  int v87; // ebx
  unsigned int v88; // [rsp+30h] [rbp-79h] BYREF
  void *v89; // [rsp+38h] [rbp-71h]
  __int64 v90; // [rsp+40h] [rbp-69h] BYREF
  int v91; // [rsp+48h] [rbp-61h] BYREF
  int v92; // [rsp+4Ch] [rbp-5Dh]
  __int64 v93; // [rsp+50h] [rbp-59h]
  char *v94; // [rsp+60h] [rbp-49h] BYREF
  int v95; // [rsp+68h] [rbp-41h]
  int v96; // [rsp+6Ch] [rbp-3Dh]
  const char *v97; // [rsp+70h] [rbp-39h]
  __int64 v98; // [rsp+78h] [rbp-31h]
  unsigned int *v99; // [rsp+80h] [rbp-29h]
  __int64 v100; // [rsp+88h] [rbp-21h]
  const WCHAR *v101; // [rsp+90h] [rbp-19h]
  int v102; // [rsp+98h] [rbp-11h]
  int v103; // [rsp+9Ch] [rbp-Dh]
  const char *v104; // [rsp+A0h] [rbp-9h]
  __int64 v105; // [rsp+A8h] [rbp-1h]

  v89 = 0;
  v2 = 0;
  v3 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v4 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v4 = gIkeExtGlobals;
LABEL_9:
    v7 = 0;
    goto LABEL_10;
  }
  v7 = *Value;
  v4 = gIkeExtGlobals;
LABEL_10:
  v90 = v7;
  v99 = (unsigned int *)&v90;
  v100 = 8;
  if ( !v4 )
    goto LABEL_18;
  v8 = (DWORD)v4[86].LockSemaphore;
  if ( v8 == -1 )
    goto LABEL_18;
  v9 = (char *)TlsGetValue(v8);
  v10 = (const WCHAR *)(v9 + 8);
  if ( !v9 )
    v10 = 0;
  if ( v10 )
  {
    v11 = -1;
    do
      v12 = v10[++v11] == 0;
    while ( !v12 );
    v13 = 2 * v11 + 2;
  }
  else
  {
LABEL_18:
    v10 = &LocaleName;
    v13 = 2;
  }
  v102 = v13;
  v92 = 5;
  v94 = off_180173280;
  v101 = v10;
  v103 = 0;
  v104 = "IkePnpNotifyCallback";
  v105 = 21;
  v91 = 184549376;
  v93 = 1;
  v95 = *(unsigned __int16 *)off_180173280;
  v97 = (const char *)&dword_180166EA4;
  v96 = 2;
  v98 = 0x10000002DLL;
  v88 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EtwEventWriteTransfer(qword_180173298, &v91, 0, 0, 5, &v94);
LABEL_20:
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v15 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v16 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v16 == -1) )
    {
      v18 = 0;
    }
    else
    {
      v17 = TlsGetValue(v16);
      v14 = WPP_GLOBAL_Control;
      v18 = v17;
      v15 = gIkeExtGlobals;
    }
    v19 = (__int64)v18 + 8;
    if ( !v18 )
      v19 = 0;
    if ( v15
      && (v20 = (DWORD)v15[86].LockSemaphore, v20 != -1)
      && (v21 = (__int64 *)TlsGetValue(v20), v14 = WPP_GLOBAL_Control, v21) )
    {
      v22 = *v21;
    }
    else
    {
      LODWORD(v22) = 0;
    }
    WPP_SF_iS(v14[2], 27, (unsigned int)WPP_cc00778c82d836298410d94d06f43a3d_Traceguids, v22, v19);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v23 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v24 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v24 != -1 )
      {
        v25 = (__int64 *)TlsGetValue(v24);
        if ( v25 )
        {
          v26 = *v25;
          v23 = gIkeExtGlobals;
LABEL_42:
          v90 = v26;
          v99 = (unsigned int *)&v90;
          v100 = 8;
          if ( !v23 )
            goto LABEL_50;
          v27 = (DWORD)v23[86].LockSemaphore;
          if ( v27 == -1 )
            goto LABEL_50;
          v28 = (char *)TlsGetValue(v27);
          v29 = (const WCHAR *)(v28 + 8);
          if ( !v28 )
            v29 = 0;
          if ( v29 )
          {
            v30 = -1;
            do
              v12 = v29[++v30] == 0;
            while ( !v12 );
            v31 = 2 * v30 + 2;
          }
          else
          {
LABEL_50:
            v29 = &LocaleName;
            v31 = 2;
          }
          v102 = v31;
          v101 = v29;
          v104 = "Received PnP notification";
          v92 = 4;
          v94 = off_180173280;
          v103 = 0;
          v105 = 26;
          v91 = 184549376;
          v93 = 0;
          v95 = *(unsigned __int16 *)off_180173280;
          v97 = (const char *)&unk_18014FAB8;
          v96 = 2;
          v98 = 0x100000037LL;
          v88 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_180173298, &v91, 0, 0, 5, &v94);
          goto LABEL_52;
        }
        v23 = gIkeExtGlobals;
      }
    }
    v26 = 0;
    goto LABEL_42;
  }
LABEL_52:
  _InterlockedIncrement64((volatile signed __int64 *)&gIkeExtGlobals[84].SpinCount);
  v32 = gIkeExtGlobals;
  if ( LODWORD(gIkeExtGlobals[50].SpinCount) != 2 )
  {
    if ( !Src )
      goto LABEL_144;
    v51 = Src[1];
    if ( v51 && 0xFFFFFFFF / v51 < 0x28 )
    {
      v52 = 0;
      v53 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v54 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
        if ( v54 == -1 )
        {
          v56 = 0;
        }
        else
        {
          v55 = TlsGetValue(v54);
          v53 = WPP_GLOBAL_Control;
          v56 = v55;
        }
        v57 = v53[2];
        v58 = (_DWORD)v56 + 8;
        if ( !v56 )
          v58 = 0;
        WPP_SF_Ssd(v57, 22, (_DWORD)v32, v58, (__int64)"WfpUINT32Multiply", 149);
      }
      v59 = RtlNtStatusToDosError(-1073741675);
      LODWORD(v61) = v59;
      if ( gWfpLogUserModeErrors && (byte_180178161 & 1) != 0 )
      {
        v88 = v59;
        v98 = 18;
        v97 = "WfpUINT32Multiply";
        v100 = 4;
        v99 = &v88;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
          (unsigned int)WFP_USERMODE_ERROR,
          v60,
          3,
          (__int64)&v94);
      }
      if ( (int)v61 > 0 )
        LODWORD(v61) = (unsigned __int16)v61 | 0x80070000;
      v61 = (int)v61;
      if ( (_DWORD)v61 )
      {
        WfpReportError((int)v61, "WfpUINT32Multiply");
        goto LABEL_125;
      }
    }
    else
    {
      v52 = 40 * v51;
      if ( ~(40 * v51) < 8 )
      {
        v62 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( !gIkeExtGlobals || (v63 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v63 == -1) )
          {
            v65 = 0;
          }
          else
          {
            v64 = TlsGetValue(v63);
            v62 = WPP_GLOBAL_Control;
            v65 = v64;
          }
          v66 = v62[2];
          v67 = (_DWORD)v65 + 8;
          if ( !v65 )
            v67 = 0;
          WPP_SF_Ssd(v66, 22, (_DWORD)v32, v67, (__int64)"WfpUINT32Add", 149);
        }
        v68 = RtlNtStatusToDosError(-1073741675);
        LODWORD(v61) = v68;
        if ( gWfpLogUserModeErrors && (byte_180178161 & 1) != 0 )
        {
          v88 = v68;
          v97 = "WfpUINT32Add";
          v99 = &v88;
          v98 = 13;
          v100 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
            (unsigned int)WFP_USERMODE_ERROR,
            v69,
            3,
            (__int64)&v94);
        }
        if ( (int)v61 > 0 )
          LODWORD(v61) = (unsigned __int16)v61 | 0x80070000;
        v61 = (int)v61;
        if ( (_DWORD)v61 )
        {
          WfpReportError((int)v61, "WfpUINT32Add");
          goto LABEL_125;
        }
LABEL_124:
        v61 = IkeQueueWorkItem(&IkeHandlePnPNotify, v2);
        if ( !v61 )
          goto LABEL_144;
        goto LABEL_125;
      }
    }
    v70 = (unsigned int)(v52 + 8);
    if ( (_DWORD)v70 )
    {
      v71 = WfpMemAlloc((unsigned int)v70, 0);
      v61 = v71;
      if ( v71 )
      {
        WfpReportError(v71, "WfpPoolAllocNonPaged");
        WfpReportError(v61, "WfpBufferCopy");
        v2 = v89;
LABEL_125:
        WfpReportError(v61, "IkePnpNotifyCallback");
        if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
          IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
        else
          IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
        if ( IsEnabledDeviceUsageNoInline )
        {
          if ( gWfpTrackHeapAllocs && v2 && _InterlockedDecrement(&gWfpNumHeapAllocs) < 0 )
          {
            if ( !gMisalignedHeapTelemFired )
            {
              if ( gWfpNumHeapAllocs <= 0 )
                MicrosoftTelemetryAssertTriggeredNoArgs(v73, v72, v74);
              gMisalignedHeapTelemFired = 1;
            }
            _InterlockedIncrement(&gWfpNumHeapAllocs);
          }
          else
          {
            v76 = HeapFree(gWfpHeap, 0, v2);
            if ( !gHeapFreeFailedFired && !v76 )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(v78, v77, v79);
              gHeapFreeFailedFired = 1;
            }
          }
        }
        else
        {
          if ( gWfpTrackHeapBytes && v2 )
            _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v2));
          HeapFree(gWfpHeap, 0, v2);
        }
LABEL_144:
        result = (unsigned int)dword_180173278;
        if ( (unsigned int)dword_180173278 <= 5 )
          return result;
        result = qword_180173288;
        if ( (qword_180173288 & 1) == 0 )
          return result;
        result = qword_180173290 & 1;
        if ( result != qword_180173290 )
          return result;
        v80 = gIkeExtGlobals;
        if ( gIkeExtGlobals )
        {
          v81 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
          if ( v81 != -1 )
          {
            v82 = (__int64 *)TlsGetValue(v81);
            if ( v82 )
            {
              v83 = *v82;
              v80 = gIkeExtGlobals;
LABEL_153:
              v90 = v83;
              v99 = (unsigned int *)&v90;
              v100 = 8;
              if ( !v80 )
                goto LABEL_160;
              v84 = (DWORD)v80[86].LockSemaphore;
              if ( v84 == -1 )
                goto LABEL_160;
              v85 = (char *)TlsGetValue(v84);
              v86 = (const WCHAR *)(v85 + 8);
              if ( !v85 )
                v86 = 0;
              if ( v86 )
              {
                do
                  v12 = v86[++v3] == 0;
                while ( !v12 );
                v87 = 2 * v3 + 2;
              }
              else
              {
LABEL_160:
                v86 = &LocaleName;
                v87 = 2;
              }
              v92 = 5;
              v94 = off_180173280;
              v101 = v86;
              v102 = v87;
              v103 = 0;
              v104 = "IkePnpNotifyCallback";
              v105 = 21;
              v91 = 184549376;
              v93 = 1;
              v95 = *(unsigned __int16 *)off_180173280;
              v50 = byte_180166E6B;
              LODWORD(v98) = 45;
              goto LABEL_162;
            }
            v80 = gIkeExtGlobals;
          }
        }
        v83 = 0;
        goto LABEL_153;
      }
      v2 = v89;
      memcpy_0(v89, Src, v70);
    }
    goto LABEL_124;
  }
  v33 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v34 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
    if ( v34 == -1 )
    {
      v36 = 0;
    }
    else
    {
      v35 = TlsGetValue(v34);
      v33 = WPP_GLOBAL_Control;
      v36 = v35;
      v32 = gIkeExtGlobals;
    }
    v37 = (__int64)v36 + 8;
    if ( !v36 )
      v37 = 0;
    if ( v32
      && (v38 = (DWORD)v32[86].LockSemaphore, v38 != -1)
      && (v39 = (__int64 *)TlsGetValue(v38), v33 = WPP_GLOBAL_Control, v39) )
    {
      v40 = *v39;
    }
    else
    {
      LODWORD(v40) = 0;
    }
    WPP_SF_iS(v33[2], 28, (unsigned int)WPP_cc00778c82d836298410d94d06f43a3d_Traceguids, v40, v37);
  }
  result = (unsigned int)dword_180173278;
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v42 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v43 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v43 != -1 )
      {
        v44 = (__int64 *)TlsGetValue(v43);
        if ( v44 )
        {
          v45 = *v44;
          v42 = gIkeExtGlobals;
LABEL_74:
          v90 = v45;
          v99 = (unsigned int *)&v90;
          v100 = 8;
          if ( !v42 )
            goto LABEL_81;
          v46 = (DWORD)v42[86].LockSemaphore;
          if ( v46 == -1 )
            goto LABEL_81;
          v47 = (char *)TlsGetValue(v46);
          v48 = (const WCHAR *)(v47 + 8);
          if ( !v47 )
            v48 = 0;
          if ( v48 )
          {
            do
              v12 = v48[++v3] == 0;
            while ( !v12 );
            v49 = 2 * v3 + 2;
          }
          else
          {
LABEL_81:
            v48 = &LocaleName;
            v49 = 2;
          }
          v101 = v48;
          v104 = "Ignoring notification due to shutdown";
          v92 = 4;
          v94 = off_180173280;
          v102 = v49;
          v103 = 0;
          v105 = 38;
          v91 = 184549376;
          v93 = 0;
          v95 = *(unsigned __int16 *)off_180173280;
          v50 = byte_18014FAFB;
          LODWORD(v98) = 63;
LABEL_162:
          v97 = v50;
          v96 = 2;
          HIDWORD(v98) = 1;
          v88 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          return EtwEventWriteTransfer(qword_180173298, &v91, 0, 0, 5, &v94);
        }
        v42 = gIkeExtGlobals;
      }
    }
    v45 = 0;
    goto LABEL_74;
  }
  return result;
}

```

## disassembly

```asm
0x180027010  push    rbp
0x180027012  push    rbx
0x180027013  push    rsi
0x180027014  push    rdi
0x180027015  push    r12
0x180027017  push    r13
0x180027019  push    r14
0x18002701b  push    r15
0x18002701d  lea     rbp, [rsp-1Fh]
0x180027022  sub     rsp, 0C8h
0x180027029  mov     rax, cs:__security_cookie
0x180027030  xor     rax, rsp
0x180027033  mov     [rbp+57h+var_50], rax
0x180027037  mov     eax, cs:dword_180173278
0x18002703d  lea     rsi, aIkepnpnotifyca; "IkePnpNotifyCallback"
0x180027044  xor     r13d, r13d
0x180027047  lea     r12, _TraceLoggingMetadataEnd
0x18002704e  mov     [rbp+57h+var_C8], r13
0x180027052  mov     r15, rcx
0x180027055  lea     rdi, _TraceLoggingMetadata
0x18002705c  mov     r14d, r13d
0x18002705f  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180027066  cmp     eax, 5
0x180027069  jbe     loc_1800271C5
0x18002706f  mov     rcx, cs:qword_180173290
0x180027076  mov     rax, cs:qword_180173288
0x18002707d  test    al, 1
0x18002707f  jz      loc_1800271C5
0x180027085  mov     rax, rcx
0x180027088  and     eax, 1
0x18002708b  cmp     rax, rcx
0x18002708e  jnz     loc_1800271C5
0x180027094  mov     rax, cs:gIkeExtGlobals
0x18002709b  test    rax, rax
0x18002709e  jz      short loc_1800270C9
0x1800270a0  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800270a6  cmp     ecx, 0FFFFFFFFh
0x1800270a9  jz      short loc_1800270C9
0x1800270ab  call    cs:__imp_TlsGetValue
0x1800270b1  test    rax, rax
0x1800270b4  jz      short loc_1800270C2
0x1800270b6  mov     rcx, [rax]
0x1800270b9  mov     rax, cs:gIkeExtGlobals
0x1800270c0  jmp     short loc_1800270CC
0x1800270c2  mov     rax, cs:gIkeExtGlobals
0x1800270c9  mov     rcx, r13
0x1800270cc  mov     [rbp+57h+var_C0], rcx
0x1800270d0  lea     rcx, [rbp+57h+var_C0]
0x1800270d4  mov     [rbp+57h+var_80], rcx
0x1800270d8  mov     [rbp+57h+var_78], 8
0x1800270e0  test    rax, rax
0x1800270e3  jz      short loc_180027125
0x1800270e5  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800270eb  cmp     ecx, 0FFFFFFFFh
0x1800270ee  jz      short loc_180027125
0x1800270f0  call    cs:__imp_TlsGetValue
0x1800270f6  test    rax, rax
0x1800270f9  lea     rdx, [rax+8]
0x1800270fd  cmovz   rdx, r13
0x180027101  test    rdx, rdx
0x180027104  jz      short loc_180027125
0x180027106  mov     rax, rbx
0x180027109  nop     dword ptr [rax+00000000h]
0x180027110  cmp     [rdx+rax*2+2], r13w
0x180027116  lea     rax, [rax+1]
0x18002711a  jnz     short loc_180027110
0x18002711c  lea     eax, ds:2[rax*2]
0x180027123  jmp     short loc_180027131
0x180027125  lea     rdx, LocaleName
0x18002712c  mov     eax, 2
0x180027131  mov     [rbp+57h+var_68], eax
0x180027134  xor     r9d, r9d
0x180027137  movzx   eax, cs:word_180166E9A
0x18002713e  xor     r8d, r8d
0x180027141  mov     [rbp+57h+var_B4], eax
0x180027144  mov     rax, cs:off_180173280
0x18002714b  mov     [rbp+57h+var_A0], rax
0x18002714f  mov     [rbp+57h+var_70], rdx
0x180027153  lea     rdx, [rbp+57h+var_B8]
0x180027157  mov     [rbp+57h+var_64], r13d
0x18002715b  mov     [rbp+57h+var_60], rsi
0x18002715f  mov     [rbp+57h+var_58], 15h
0x180027167  mov     [rbp+57h+var_B8], 0B000000h
0x18002716e  mov     [rbp+57h+var_B0], 1
0x180027176  movzx   eax, word ptr [rax]
0x180027179  mov     [rbp+57h+var_98], eax
0x18002717c  lea     rax, dword_180166EA4
0x180027183  mov     [rbp+57h+var_90], rax
0x180027187  mov     rax, r12
0x18002718a  sub     eax, edi
0x18002718c  mov     [rbp+57h+var_94], 2
0x180027193  mov     dword ptr [rbp+57h+var_88], 2Dh ; '-'
0x18002719a  mov     dword ptr [rbp+57h+var_88+4], 1
0x1800271a1  mov     [rbp+57h+var_D0], eax
0x1800271a4  mov     eax, [rbp+57h+var_D0]
0x1800271a7  mov     rcx, cs:qword_180173298
0x1800271ae  lea     rax, [rbp+57h+var_A0]
0x1800271b2  mov     [rsp+100h+var_D8], rax
0x1800271b7  mov     dword ptr [rsp+100h+var_E0], 5
0x1800271bf  call    cs:__imp_EtwEventWriteTransfer
0x1800271c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800271cc  lea     rdi, WPP_GLOBAL_Control
0x1800271d3  cmp     rcx, rdi
0x1800271d6  jz      loc_18002727D
0x1800271dc  cmp     byte ptr [rcx+19h], 4
0x1800271e0  jb      loc_18002727D
0x1800271e6  test    byte ptr [rcx+1Ch], 10h
0x1800271ea  jz      loc_18002727D
0x1800271f0  mov     rdx, cs:gIkeExtGlobals
0x1800271f7  test    rdx, rdx
0x1800271fa  jz      short loc_180027222
0x1800271fc  mov     eax, [rdx+0D88h]
0x180027202  cmp     eax, 0FFFFFFFFh
0x180027205  jz      short loc_180027222
0x180027207  mov     ecx, eax; dwTlsIndex
0x180027209  call    cs:__imp_TlsGetValue
0x18002720f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027216  mov     r8, rax
0x180027219  mov     rdx, cs:gIkeExtGlobals
0x180027220  jmp     short loc_180027225
0x180027222  mov     r8, r13
0x180027225  test    r8, r8
0x180027228  lea     rdi, [r8+8]
0x18002722c  cmovz   rdi, r13
0x180027230  test    rdx, rdx
0x180027233  jz      short loc_180027259
0x180027235  mov     eax, [rdx+0D88h]
0x18002723b  cmp     eax, 0FFFFFFFFh
0x18002723e  jz      short loc_180027259
0x180027240  mov     ecx, eax; dwTlsIndex
0x180027242  call    cs:__imp_TlsGetValue
0x180027248  mov     rcx, cs:WPP_GLOBAL_Control
0x18002724f  test    rax, rax
0x180027252  jz      short loc_180027259
0x180027254  mov     r9, [rax]
0x180027257  jmp     short loc_18002725C
0x180027259  mov     r9, r13
0x18002725c  mov     rcx, [rcx+10h]
0x180027260  lea     r8, WPP_cc00778c82d836298410d94d06f43a3d_Traceguids
0x180027267  mov     edx, 1Bh
0x18002726c  mov     [rsp+100h+var_E0], rdi
0x180027271  call    WPP_SF_iS
0x180027276  lea     rdi, WPP_GLOBAL_Control
0x18002727d  mov     eax, cs:dword_180173278
0x180027283  cmp     eax, 4
0x180027286  jbe     loc_1800273C0
0x18002728c  mov     rax, cs:gIkeExtGlobals
0x180027293  test    rax, rax
0x180027296  jz      short loc_1800272C1
0x180027298  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002729e  cmp     ecx, 0FFFFFFFFh
0x1800272a1  jz      short loc_1800272C1
0x1800272a3  call    cs:__imp_TlsGetValue
0x1800272a9  test    rax, rax
0x1800272ac  jz      short loc_1800272BA
0x1800272ae  mov     rcx, [rax]
0x1800272b1  mov     rax, cs:gIkeExtGlobals
0x1800272b8  jmp     short loc_1800272C4
0x1800272ba  mov     rax, cs:gIkeExtGlobals
0x1800272c1  mov     rcx, r13
0x1800272c4  mov     [rbp+57h+var_C0], rcx
0x1800272c8  lea     rcx, [rbp+57h+var_C0]
0x1800272cc  mov     [rbp+57h+var_80], rcx
0x1800272d0  mov     [rbp+57h+var_78], 8
0x1800272d8  test    rax, rax
0x1800272db  jz      short loc_180027316
0x1800272dd  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800272e3  cmp     ecx, 0FFFFFFFFh
0x1800272e6  jz      short loc_180027316
0x1800272e8  call    cs:__imp_TlsGetValue
0x1800272ee  test    rax, rax
0x1800272f1  lea     rdx, [rax+8]
0x1800272f5  cmovz   rdx, r13
0x1800272f9  test    rdx, rdx
0x1800272fc  jz      short loc_180027316
0x1800272fe  mov     rax, rbx
0x180027301  cmp     [rdx+rax*2+2], r13w
0x180027307  lea     rax, [rax+1]
0x18002730b  jnz     short loc_180027301
0x18002730d  lea     eax, ds:2[rax*2]
0x180027314  jmp     short loc_180027322
0x180027316  lea     rdx, LocaleName
0x18002731d  mov     eax, 2
0x180027322  mov     [rbp+57h+var_68], eax
0x180027325  lea     rcx, _TraceLoggingMetadata
0x18002732c  mov     [rbp+57h+var_70], rdx
0x180027330  lea     rax, aReceivedPnpNot; "Received PnP notification"
0x180027337  mov     [rbp+57h+var_60], rax
0x18002733b  lea     rdx, [rbp+57h+var_B8]
0x18002733f  movzx   eax, cs:word_18014FAAE
0x180027346  xor     r9d, r9d
0x180027349  mov     [rbp+57h+var_B4], eax
0x18002734c  xor     r8d, r8d
0x18002734f  mov     rax, cs:off_180173280
0x180027356  mov     [rbp+57h+var_A0], rax
0x18002735a  mov     [rbp+57h+var_64], r13d
0x18002735e  mov     [rbp+57h+var_58], 1Ah
0x180027366  mov     [rbp+57h+var_B8], 0B000000h
0x18002736d  mov     [rbp+57h+var_B0], r13
0x180027371  movzx   eax, word ptr [rax]
0x180027374  mov     [rbp+57h+var_98], eax
0x180027377  lea     rax, unk_18014FAB8
0x18002737e  mov     [rbp+57h+var_90], rax
0x180027382  mov     rax, r12
0x180027385  sub     eax, ecx
0x180027387  mov     [rbp+57h+var_94], 2
0x18002738e  mov     dword ptr [rbp+57h+var_88], 37h ; '7'
0x180027395  mov     dword ptr [rbp+57h+var_88+4], 1
0x18002739c  mov     [rbp+57h+var_D0], eax
0x18002739f  mov     eax, [rbp+57h+var_D0]
0x1800273a2  mov     rcx, cs:qword_180173298
0x1800273a9  lea     rax, [rbp+57h+var_A0]
0x1800273ad  mov     [rsp+100h+var_D8], rax
0x1800273b2  mov     dword ptr [rsp+100h+var_E0], 5
0x1800273ba  call    cs:__imp_EtwEventWriteTransfer
0x1800273c0  mov     rax, cs:gIkeExtGlobals
0x1800273c7  lock inc qword ptr [rax+0D40h]
0x1800273cf  mov     r8, cs:gIkeExtGlobals
0x1800273d6  cmp     dword ptr [r8+7F0h], 2
0x1800273de  jnz     loc_180027579
0x1800273e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273eb  cmp     rcx, rdi
0x1800273ee  jz      loc_180027480
0x1800273f4  cmp     byte ptr [rcx+19h], 4
0x1800273f8  jb      loc_180027480
0x1800273fe  test    byte ptr [rcx+1Ch], 10h
0x180027402  jz      short loc_180027480
0x180027404  mov     eax, [r8+0D88h]
0x18002740b  cmp     eax, 0FFFFFFFFh
0x18002740e  jz      short loc_18002742B
0x180027410  mov     ecx, eax; dwTlsIndex
0x180027412  call    cs:__imp_TlsGetValue
0x180027418  mov     rcx, cs:WPP_GLOBAL_Control
0x18002741f  mov     rdx, rax
0x180027422  mov     r8, cs:gIkeExtGlobals
0x180027429  jmp     short loc_18002742E
0x18002742b  mov     rdx, r13
0x18002742e  test    rdx, rdx
0x180027431  lea     rdi, [rdx+8]
0x180027435  cmovz   rdi, r13
0x180027439  test    r8, r8
0x18002743c  jz      short loc_180027463
0x18002743e  mov     eax, [r8+0D88h]
0x180027445  cmp     eax, 0FFFFFFFFh
0x180027448  jz      short loc_180027463
0x18002744a  mov     ecx, eax; dwTlsIndex
0x18002744c  call    cs:__imp_TlsGetValue
0x180027452  mov     rcx, cs:WPP_GLOBAL_Control
0x180027459  test    rax, rax
0x18002745c  jz      short loc_180027463
0x18002745e  mov     r9, [rax]
0x180027461  jmp     short loc_180027466
0x180027463  mov     r9, r13
0x180027466  mov     rcx, [rcx+10h]
0x18002746a  lea     r8, WPP_cc00778c82d836298410d94d06f43a3d_Traceguids
0x180027471  mov     edx, 1Ch
0x180027476  mov     [rsp+100h+var_E0], rdi
0x18002747b  call    WPP_SF_iS
0x180027480  mov     eax, cs:dword_180173278
0x180027486  cmp     eax, 4
0x180027489  jbe     loc_180027A5B
0x18002748f  mov     rax, cs:gIkeExtGlobals
0x180027496  test    rax, rax
0x180027499  jz      short loc_1800274C4
0x18002749b  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800274a1  cmp     ecx, 0FFFFFFFFh
0x1800274a4  jz      short loc_1800274C4
0x1800274a6  call    cs:__imp_TlsGetValue
0x1800274ac  test    rax, rax
0x1800274af  jz      short loc_1800274BD
0x1800274b1  mov     rcx, [rax]
0x1800274b4  mov     rax, cs:gIkeExtGlobals
0x1800274bb  jmp     short loc_1800274C7
0x1800274bd  mov     rax, cs:gIkeExtGlobals
0x1800274c4  mov     rcx, r13
0x1800274c7  mov     [rbp+57h+var_C0], rcx
0x1800274cb  lea     rcx, [rbp+57h+var_C0]
0x1800274cf  mov     [rbp+57h+var_80], rcx
0x1800274d3  mov     [rbp+57h+var_78], 8
0x1800274db  test    rax, rax
0x1800274de  jz      short loc_180027516
0x1800274e0  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800274e6  cmp     ecx, 0FFFFFFFFh
0x1800274e9  jz      short loc_180027516
0x1800274eb  call    cs:__imp_TlsGetValue
0x1800274f1  test    rax, rax
0x1800274f4  lea     rdx, [rax+8]
0x1800274f8  cmovz   rdx, r13
0x1800274fc  test    rdx, rdx
0x1800274ff  jz      short loc_180027516
0x180027501  cmp     [rdx+rbx*2+2], r13w
0x180027507  lea     rbx, [rbx+1]
0x18002750b  jnz     short loc_180027501
0x18002750d  lea     ebx, ds:2[rbx*2]
0x180027514  jmp     short loc_180027522
0x180027516  lea     rdx, LocaleName
0x18002751d  mov     ebx, 2
0x180027522  lea     rax, aIgnoringNotifi; "Ignoring notification due to shutdown"
0x180027529  mov     [rbp+57h+var_70], rdx
0x18002752d  mov     [rbp+57h+var_60], rax
  ... truncated ...
```
