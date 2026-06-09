# EndFaxSvc(ulong)

- ea: `0x140046a7c`
- end: `0x140047295`
- name: `?EndFaxSvc@@YAXK@Z`
- size: `2073`
- prototype: `void __fastcall(unsigned int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400236a0`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140025194`
- `0x14002c70c`
- `0x1400382a4`
- `0x1400383e0`
- `0x1400386b4`
- `0x140046a7c`
- `0x140047edc`
- `0x140048e1c`
- `0x140048fac`
- `0x140049168`
- `0x14004a690`
- `0x14005584c`
- `0x140065dbc`
- `0x140065df8`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14004706c`
- `KERNEL32!FreeLibrary` at `0x140047158`
- `KERNEL32!FreeLibrary` at `0x14004706c`
- `KERNEL32!FreeLibrary` at `0x140047158`
- `KERNEL32!GetLastError` at `0x140046b03`
- `KERNEL32!GetLastError` at `0x140046bc5`
- `KERNEL32!GetLastError` at `0x140046c0f`
- `KERNEL32!GetLastError` at `0x140046d05`
- `KERNEL32!GetLastError` at `0x140046d4e`
- `KERNEL32!GetLastError` at `0x140046da7`
- `KERNEL32!GetLastError` at `0x140046dec`
- `KERNEL32!GetLastError` at `0x140046ead`
- `KERNEL32!GetLastError` at `0x140046f44`
- `KERNEL32!GetLastError` at `0x140046f9d`
- `KERNEL32!GetLastError` at `0x140046fe3`
- `KERNEL32!GetLastError` at `0x140046b03`
- `KERNEL32!GetLastError` at `0x140046bc5`
- `KERNEL32!GetLastError` at `0x140046c0f`
- `KERNEL32!GetLastError` at `0x140046d05`
- `KERNEL32!GetLastError` at `0x140046d4e`
- `KERNEL32!GetLastError` at `0x140046da7`
- `KERNEL32!GetLastError` at `0x140046dec`
- `KERNEL32!GetLastError` at `0x140046ead`
- `KERNEL32!GetLastError` at `0x140046f44`
- `KERNEL32!GetLastError` at `0x140046f9d`
- `KERNEL32!GetLastError` at `0x140046fe3`
- `KERNEL32!SetLastError` at `0x140046dce`
- `KERNEL32!SetLastError` at `0x140046dce`
- `KERNEL32!CloseHandle` at `0x140046bed`
- `KERNEL32!CloseHandle` at `0x140046d85`
- `KERNEL32!CloseHandle` at `0x140046bed`
- `KERNEL32!CloseHandle` at `0x140046d85`
- `KERNEL32!EnterCriticalSection` at `0x140046ee9`
- `KERNEL32!EnterCriticalSection` at `0x140046ee9`
- `KERNEL32!LeaveCriticalSection` at `0x140046ef6`
- `KERNEL32!LeaveCriticalSection` at `0x140046ef6`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140046f22`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140046f22`
- `KERNEL32!CreateThread` at `0x140046cf7`
- `KERNEL32!CreateThread` at `0x140046cf7`
- `KERNEL32!HeapDestroy` at `0x140047086`
- `KERNEL32!HeapDestroy` at `0x140047172`
- `KERNEL32!HeapDestroy` at `0x140047086`
- `KERNEL32!HeapDestroy` at `0x140047172`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x140046c43`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x140046c43`
- `RPCRT4!RpcMgmtStopServerListening` at `0x140046b53`
- `RPCRT4!RpcMgmtStopServerListening` at `0x140046b53`

## string_xrefs

- `0x140046d39`: `Waiting for SetServiceIsDownFlagThread to terminate.`
- `0x140046b9d`: `Waiting for RPC listning thread to terminate.`
- `0x140046e85`: `Waiting for all threads (except TapiWorkerThread) to terminate.`
- `0x140046f75`: `Waiting for TapiWorkerThread to terminate.`

## pseudocode

```c
void __fastcall EndFaxSvc(unsigned int a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  CMapDeviceId *v7; // rcx
  DWORD LastError; // eax
  unsigned int v9; // edi
  unsigned int v10; // eax
  unsigned int v11; // ebx
  DWORD v12; // eax
  DWORD v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // ebx
  CMapDeviceId *v16; // rcx
  HANDLE Thread; // rax
  void *v18; // rdi
  DWORD v19; // eax
  DWORD v20; // ebx
  CMapDeviceId *v21; // rcx
  __int64 v22; // rdx
  DWORD v23; // eax
  DWORD v24; // eax
  unsigned int v25; // edx
  DWORD v26; // eax
  DWORD v27; // eax
  DWORD v28; // eax
  DWORD v29; // eax
  struct _DEVICE_PROVIDER *v30; // rbx
  struct _DEVICE_PROVIDER *v31; // rdx
  struct _DEVICE_PROVIDER *v32; // rdi
  struct _DEVICE_PROVIDER **v33; // rax
  HMODULE v34; // rcx
  void *v35; // rcx
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY *v37; // r8
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *v39; // rbx
  struct _LIST_ENTRY *v40; // rcx
  LPVOID *v41; // rbx
  LPVOID *v42; // rdx
  LPVOID *v43; // rdi
  LPVOID **v44; // rax
  HMODULE v45; // rcx
  void *v46; // rcx
  struct _HANDLE_ENTRY *v47; // rbx
  struct _HANDLE_ENTRY *v48; // rcx
  DWORD_PTR *v49; // rbx
  DWORD_PTR *v50; // rcx
  DWORD_PTR **v51; // rax
  struct _LINE_INFO *v52; // rbx
  struct _LINE_INFO *v53; // rcx
  struct _LINE_INFO **v54; // rax
  struct _LIST_ENTRY *v55; // rbx
  struct _LIST_ENTRY *v56; // rdx
  struct _LIST_ENTRY *v57; // rcx
  struct _LIST_ENTRY *v58; // rax
  bool v59; // zf
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
  }
  if ( (unsigned int)CreateFaxEvent(0, 0x14u, 0xFFFFFFFF, 0) )
    goto LABEL_10;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
    goto LABEL_15;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, LastError);
LABEL_10:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 5u )
    WPP_SF_(*((_QWORD *)v7 + 2), 106, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
LABEL_15:
  v9 = 0;
  v10 = RpcMgmtStopServerListening(0);
  v11 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v10);
    }
    v9 = v11;
  }
  if ( g_hRPCListeningThread )
  {
    if ( !(unsigned int)WaitAndReportForThreadToTerminate(
                          g_hRPCListeningThread,
                          L"Waiting for RPC listning thread to terminate.")
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v12);
    }
    if ( !CloseHandle(g_hRPCListeningThread)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v13);
    }
    g_hRPCListeningThread = 0;
  }
  v14 = RpcServerUnregisterIfEx(qword_140088220, 0, 0);
  v15 = v14;
  if ( !v14 )
    goto LABEL_38;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v14);
LABEL_38:
    v16 = WPP_GLOBAL_Control;
  }
  if ( v9 )
  {
    v15 = v9;
  }
  else if ( !v15 )
  {
    goto LABEL_47;
  }
  if ( v16 == (CMapDeviceId *)&WPP_GLOBAL_Control )
    goto LABEL_51;
  if ( (*((_BYTE *)v16 + 28) & 4) != 0 && *((_BYTE *)v16 + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)v16 + 2), 59, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v15);
    v16 = WPP_GLOBAL_Control;
  }
LABEL_47:
  if ( v16 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 && *((_BYTE *)v16 + 25) >= 5u )
    WPP_SF_(*((_QWORD *)v16 + 2), 64, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
LABEL_51:
  Thread = CreateThread(0, 0, SetServiceIsDownFlagThread, 0, 0, 0);
  v18 = Thread;
  if ( Thread )
  {
    v20 = 0;
    if ( !(unsigned int)WaitAndReportForThreadToTerminate(
                          Thread,
                          L"Waiting for SetServiceIsDownFlagThread to terminate.") )
    {
      v23 = GetLastError();
      v20 = v23;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v23);
      }
    }
    if ( !CloseHandle(v18)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = GetLastError();
      v21 = WPP_GLOBAL_Control;
      v22 = 67;
      goto LABEL_66;
    }
  }
  else
  {
    v19 = GetLastError();
    v20 = v19;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = 65;
LABEL_66:
      WPP_SF_d(*((_QWORD *)v21 + 2), v22, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v19);
    }
  }
  if ( v20 )
  {
    SetLastError(v20);
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v24 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v24);
    }
  }
  if ( !(unsigned int)NotifyServiceThreadsToTerminate()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
  }
  if ( !(unsigned int)StopAllInProgressJobs()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
  }
  if ( g_hThreadCountEvent )
  {
    if ( !(unsigned int)WaitAndReportForThreadToTerminate(
                          g_hThreadCountEvent,
                          L"Waiting for all threads (except TapiWorkerThread) to terminate.")
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v26);
    }
    ReportServiceStatus(3u, v25, 0x1770u);
    EnterCriticalSection(&g_CsServiceThreads);
    LeaveCriticalSection(&g_CsServiceThreads);
  }
  if ( g_TapiCompletionPort )
  {
    memset(&Overlapped, 0, sizeof(Overlapped));
    if ( !PostQueuedCompletionStatus(g_TapiCompletionPort, 0, 0xFFFFFFFF, &Overlapped)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v27 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v27);
    }
  }
  if ( g_hTapiWorkerThread
    && !(unsigned int)WaitAndReportForThreadToTerminate(
                        g_hTapiWorkerThread,
                        L"Waiting for TapiWorkerThread to terminate.")
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v28 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v28);
  }
  if ( !(unsigned int)StopFaxServiceProviders()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v29 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v29);
  }
  v30 = g_DeviceProvidersListHead;
  while ( v30 != (struct _DEVICE_PROVIDER *)&g_DeviceProvidersListHead )
  {
    v31 = v30;
    v32 = v30;
    v30 = *(struct _DEVICE_PROVIDER **)v30;
    v33 = (struct _DEVICE_PROVIDER **)*((_QWORD *)v31 + 1);
    *v33 = v30;
    *((_QWORD *)v30 + 1) = v33;
    *(_QWORD *)v31 = 0;
    *((_QWORD *)v31 + 1) = 0;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_200271385d87382553faba38592a1280_Traceguids);
    }
    v34 = (HMODULE)*((_QWORD *)v32 + 7);
    if ( v34 )
      FreeLibrary(v34);
    v35 = (void *)*((_QWORD *)v32 + 269);
    if ( v35 && !*((_DWORD *)v32 + 562) )
      HeapDestroy(v35);
    pMemFree(v32);
  }
  Flink = g_lstRoutingMethods.Flink;
  while ( Flink != &g_lstRoutingMethods )
  {
    v37 = Flink;
    Blink = Flink->Blink;
    v39 = Flink - 1;
    Flink = Flink->Flink;
    Blink->Flink = Flink;
    Flink->Blink = Blink;
    v40 = v39[4].Flink;
    v37->Flink = 0;
    v37->Blink = 0;
    pMemFree(v40);
    pMemFree(v39[3].Blink);
    pMemFree(v39[4].Blink);
    pMemFree(v39);
  }
  v41 = (LPVOID *)g_lstRoutingExtensions;
  while ( v41 != &g_lstRoutingExtensions )
  {
    v42 = v41;
    v43 = v41;
    v41 = (LPVOID *)*v41;
    v44 = (LPVOID **)v42[1];
    *v44 = v41;
    v41[1] = v44;
    *v42 = 0;
    v42[1] = 0;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
    }
    v45 = (HMODULE)v43[2];
    if ( v45 )
      FreeLibrary(v45);
    v46 = v43[202];
    if ( v46 && !*((_DWORD *)v43 + 406) )
      HeapDestroy(v46);
    pMemFree(v43);
  }
  v47 = g_HandleTableListHead;
  while ( v47 != (struct _HANDLE_ENTRY *)&g_HandleTableListHead )
  {
    v48 = v47;
    v47 = *(struct _HANDLE_ENTRY **)v47;
    CloseFaxHandle(v48);
  }
  v49 = (DWORD_PTR *)g_TapiLinesListHead;
  while ( v49 != &g_TapiLinesListHead )
  {
    v50 = v49;
    v49 = (DWORD_PTR *)*v49;
    v51 = (DWORD_PTR **)v50[1];
    *v51 = v49;
    v49[1] = (DWORD_PTR)v51;
    *v50 = 0;
    v50[1] = 0;
    FreeTapiLine((struct _LINE_INFO *)v50);
  }
  v52 = g_RemovedTapiLinesListHead;
  while ( v52 != (struct _LINE_INFO *)&g_RemovedTapiLinesListHead )
  {
    v53 = v52;
    v52 = *(struct _LINE_INFO **)v52;
    v54 = (struct _LINE_INFO **)*((_QWORD *)v53 + 1);
    *v54 = v52;
    *((_QWORD *)v52 + 1) = v54;
    *(_QWORD *)v53 = 0;
    *((_QWORD *)v53 + 1) = 0;
    FreeTapiLine(v53);
  }
  v55 = g_QueueListHead.Flink;
  while ( v55 != &g_QueueListHead )
  {
    v56 = v55->Flink;
    v57 = v55;
    v55 = v56;
    v58 = v57->Blink;
    v58->Flink = v56;
    v56->Blink = v58;
    v59 = HIDWORD(v57[2].Flink) == 32;
    v57->Flink = 0;
    v57->Blink = 0;
    if ( v59 )
    {
      FreeParentQueueEntry((struct _JOB_QUEUE *)v57, (int)v56);
    }
    else if ( HIDWORD(v57[2].Flink) == 2 )
    {
      FreeRecipientQueueEntry((struct _JOB_QUEUE *)v57, (int)v56);
    }
    else if ( HIDWORD(v57[2].Flink) == 8 )
    {
      FreeReceiveQueueEntry((struct _JOB_QUEUE *)v57, (int)v56);
    }
  }
  FaxLog(1, a1, 0, 1073773842, a5, a6);
}

```

## disassembly

```asm
0x140046a7c  push    rbx
0x140046a7e  push    rbp
0x140046a7f  push    rsi
0x140046a80  push    rdi
0x140046a81  push    r12
0x140046a83  push    r13
0x140046a85  push    r14
0x140046a87  push    r15
0x140046a89  sub     rsp, 58h
0x140046a8d  mov     esi, ecx
0x140046a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140046a96  lea     r15, WPP_GLOBAL_Control
0x140046a9d  mov     r14b, 4
0x140046aa0  cmp     rcx, r15
0x140046aa3  jz      short loc_140046AC6
0x140046aa5  test    [rcx+1Ch], r14b
0x140046aa9  jz      short loc_140046AC6
0x140046aab  cmp     byte ptr [rcx+19h], 5
0x140046aaf  jb      short loc_140046AC6
0x140046ab1  mov     rcx, [rcx+10h]
0x140046ab5  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140046abc  mov     edx, 39h ; '9'
0x140046ac1  call    WPP_SF_
0x140046ac6  xor     r9d, r9d; void *
0x140046ac9  xor     ecx, ecx; unsigned int
0x140046acb  mov     r8d, 0FFFFFFFFh; unsigned int
0x140046ad1  lea     edx, [r9+14h]; unsigned int
0x140046ad5  call    ?CreateFaxEvent@@YAHKKKPEAX@Z; CreateFaxEvent(ulong,ulong,ulong,void *)
0x140046ada  xor     ebp, ebp
0x140046adc  lea     r12, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140046ae3  lea     r13d, [rbp+2]
0x140046ae7  test    eax, eax
0x140046ae9  jnz     short loc_140046B26
0x140046aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x140046af2  cmp     rcx, r15
0x140046af5  jz      short loc_140046B4F
0x140046af7  test    [rcx+1Ch], r14b
0x140046afb  jz      short loc_140046B2D
0x140046afd  cmp     [rcx+19h], r13b
0x140046b01  jb      short loc_140046B2D
0x140046b03  call    cs:__imp_GetLastError
0x140046b09  mov     rcx, cs:WPP_GLOBAL_Control
0x140046b10  lea     edx, [rbp+3Ah]
0x140046b13  mov     r9d, eax
0x140046b16  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140046b1d  mov     rcx, [rcx+10h]
0x140046b21  call    WPP_SF_d
0x140046b26  mov     rcx, cs:WPP_GLOBAL_Control
0x140046b2d  cmp     rcx, r15
0x140046b30  jz      short loc_140046B4F
0x140046b32  test    [rcx+1Ch], r14b
0x140046b36  jz      short loc_140046B4F
0x140046b38  cmp     byte ptr [rcx+19h], 5
0x140046b3c  jb      short loc_140046B4F
0x140046b3e  mov     rcx, [rcx+10h]
0x140046b42  mov     edx, 6Ah ; 'j'
0x140046b47  mov     r8, r12
0x140046b4a  call    WPP_SF_
0x140046b4f  xor     ecx, ecx; Binding
0x140046b51  mov     edi, ebp
0x140046b53  call    cs:__imp_RpcMgmtStopServerListening
0x140046b59  mov     ebx, eax
0x140046b5b  test    eax, eax
0x140046b5d  jz      short loc_140046B8D
0x140046b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140046b66  cmp     rcx, r15
0x140046b69  jz      short loc_140046B8B
0x140046b6b  test    [rcx+1Ch], r14b
0x140046b6f  jz      short loc_140046B8B
0x140046b71  cmp     [rcx+19h], r13b
0x140046b75  jb      short loc_140046B8B
0x140046b77  mov     rcx, [rcx+10h]
0x140046b7b  mov     edx, 6Bh ; 'k'
0x140046b80  mov     r9d, eax
0x140046b83  mov     r8, r12
0x140046b86  call    WPP_SF_d
0x140046b8b  mov     edi, ebx
0x140046b8d  mov     rcx, cs:?g_hRPCListeningThread@@3PEAXEA; hHandle
0x140046b94  test    rcx, rcx
0x140046b97  jz      loc_140046C37
0x140046b9d  lea     rdx, aWaitingForRpcL; "Waiting for RPC listning thread to term"...
0x140046ba4  call    ?WaitAndReportForThreadToTerminate@@YAHPEAXPEBG@Z; WaitAndReportForThreadToTerminate(void *,ushort const *)
0x140046ba9  test    eax, eax
0x140046bab  jnz     short loc_140046BE6
0x140046bad  mov     rax, cs:WPP_GLOBAL_Control
0x140046bb4  cmp     rax, r15
0x140046bb7  jz      short loc_140046BE6
0x140046bb9  test    [rax+1Ch], r14b
0x140046bbd  jz      short loc_140046BE6
0x140046bbf  cmp     [rax+19h], r13b
0x140046bc3  jb      short loc_140046BE6
0x140046bc5  call    cs:__imp_GetLastError
0x140046bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140046bd2  mov     edx, 6Ch ; 'l'
0x140046bd7  mov     r9d, eax
0x140046bda  mov     r8, r12
0x140046bdd  mov     rcx, [rcx+10h]
0x140046be1  call    WPP_SF_d
0x140046be6  mov     rcx, cs:?g_hRPCListeningThread@@3PEAXEA; hObject
0x140046bed  call    cs:__imp_CloseHandle
0x140046bf3  test    eax, eax
0x140046bf5  jnz     short loc_140046C30
0x140046bf7  mov     rax, cs:WPP_GLOBAL_Control
0x140046bfe  cmp     rax, r15
0x140046c01  jz      short loc_140046C30
0x140046c03  test    [rax+1Ch], r14b
0x140046c07  jz      short loc_140046C30
0x140046c09  cmp     [rax+19h], r13b
0x140046c0d  jb      short loc_140046C30
0x140046c0f  call    cs:__imp_GetLastError
0x140046c15  mov     rcx, cs:WPP_GLOBAL_Control
0x140046c1c  mov     edx, 6Dh ; 'm'
0x140046c21  mov     r9d, eax
0x140046c24  mov     r8, r12
0x140046c27  mov     rcx, [rcx+10h]
0x140046c2b  call    WPP_SF_d
0x140046c30  mov     cs:?g_hRPCListeningThread@@3PEAXEA, rbp; void * g_hRPCListeningThread
0x140046c37  xor     r8d, r8d; RundownContextHandles
0x140046c3a  lea     rcx, qword_140088220; IfSpec
0x140046c41  xor     edx, edx; MgrTypeUuid
0x140046c43  call    cs:__imp_RpcServerUnregisterIfEx
0x140046c49  mov     ebx, eax
0x140046c4b  test    eax, eax
0x140046c4d  jz      short loc_140046C7B
0x140046c4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140046c56  cmp     rcx, r15
0x140046c59  jz      short loc_140046C82
0x140046c5b  test    [rcx+1Ch], r14b
0x140046c5f  jz      short loc_140046C82
0x140046c61  cmp     [rcx+19h], r13b
0x140046c65  jb      short loc_140046C82
0x140046c67  mov     rcx, [rcx+10h]
0x140046c6b  mov     edx, 6Eh ; 'n'
0x140046c70  mov     r9d, eax
0x140046c73  mov     r8, r12
0x140046c76  call    WPP_SF_d
0x140046c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140046c82  test    edi, edi
0x140046c84  jnz     short loc_140046C8C
0x140046c86  test    ebx, ebx
0x140046c88  jz      short loc_140046CBE
0x140046c8a  jmp     short loc_140046C8E
0x140046c8c  mov     ebx, edi
0x140046c8e  cmp     rcx, r15
0x140046c91  jz      short loc_140046CE0
0x140046c93  test    [rcx+1Ch], r14b
0x140046c97  jz      short loc_140046CBE
0x140046c99  cmp     [rcx+19h], r13b
0x140046c9d  jb      short loc_140046CBE
0x140046c9f  mov     rcx, [rcx+10h]
0x140046ca3  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140046caa  mov     edx, 3Bh ; ';'
0x140046caf  mov     r9d, ebx
0x140046cb2  call    WPP_SF_d
0x140046cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140046cbe  cmp     rcx, r15
0x140046cc1  jz      short loc_140046CE0
0x140046cc3  test    [rcx+1Ch], r14b
0x140046cc7  jz      short loc_140046CE0
0x140046cc9  cmp     byte ptr [rcx+19h], 5
0x140046ccd  jb      short loc_140046CE0
0x140046ccf  mov     rcx, [rcx+10h]
0x140046cd3  mov     edx, 40h ; '@'
0x140046cd8  mov     r8, r12
0x140046cdb  call    WPP_SF_
0x140046ce0  mov     [rsp+98h+lpThreadId], rbp; lpThreadId
0x140046ce5  lea     r8, ?SetServiceIsDownFlagThread@@YAKPEAX@Z; lpStartAddress
0x140046cec  xor     r9d, r9d; lpParameter
0x140046cef  mov     [rsp+98h+dwCreationFlags], ebp; dwCreationFlags
0x140046cf3  xor     edx, edx; dwStackSize
0x140046cf5  xor     ecx, ecx; lpThreadAttributes
0x140046cf7  call    cs:__imp_CreateThread
0x140046cfd  mov     rdi, rax
0x140046d00  test    rax, rax
0x140046d03  jnz     short loc_140046D39
0x140046d05  call    cs:__imp_GetLastError
0x140046d0b  mov     ebx, eax
0x140046d0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140046d14  cmp     rcx, r15
0x140046d17  jz      loc_140046DC8
0x140046d1d  test    [rcx+1Ch], r14b
0x140046d21  jz      loc_140046DC8
0x140046d27  cmp     [rcx+19h], r13b
0x140046d2b  jb      loc_140046DC8
0x140046d31  lea     edx, [rdi+41h]
0x140046d34  jmp     loc_140046DB9
0x140046d39  lea     rdx, aWaitingForSets; "Waiting for SetServiceIsDownFlagThread "...
0x140046d40  mov     rcx, rdi; hHandle
0x140046d43  mov     ebx, ebp
0x140046d45  call    ?WaitAndReportForThreadToTerminate@@YAHPEAXPEBG@Z; WaitAndReportForThreadToTerminate(void *,ushort const *)
0x140046d4a  test    eax, eax
0x140046d4c  jnz     short loc_140046D82
0x140046d4e  call    cs:__imp_GetLastError
0x140046d54  mov     ebx, eax
0x140046d56  mov     rcx, cs:WPP_GLOBAL_Control
0x140046d5d  cmp     rcx, r15
0x140046d60  jz      short loc_140046D82
0x140046d62  test    [rcx+1Ch], r14b
0x140046d66  jz      short loc_140046D82
0x140046d68  cmp     [rcx+19h], r13b
0x140046d6c  jb      short loc_140046D82
0x140046d6e  mov     rcx, [rcx+10h]
0x140046d72  mov     edx, 42h ; 'B'
0x140046d77  mov     r9d, eax
0x140046d7a  mov     r8, r12
0x140046d7d  call    WPP_SF_d
0x140046d82  mov     rcx, rdi; hObject
0x140046d85  call    cs:__imp_CloseHandle
0x140046d8b  test    eax, eax
0x140046d8d  jnz     short loc_140046DC8
0x140046d8f  mov     rax, cs:WPP_GLOBAL_Control
0x140046d96  cmp     rax, r15
0x140046d99  jz      short loc_140046DC8
0x140046d9b  test    [rax+1Ch], r14b
0x140046d9f  jz      short loc_140046DC8
0x140046da1  cmp     [rax+19h], r13b
0x140046da5  jb      short loc_140046DC8
0x140046da7  call    cs:__imp_GetLastError
0x140046dad  mov     rcx, cs:WPP_GLOBAL_Control
0x140046db4  mov     edx, 43h ; 'C'
0x140046db9  mov     rcx, [rcx+10h]
0x140046dbd  mov     r9d, eax
0x140046dc0  mov     r8, r12
0x140046dc3  call    WPP_SF_d
0x140046dc8  test    ebx, ebx
0x140046dca  jz      short loc_140046E11
0x140046dcc  mov     ecx, ebx; dwErrCode
0x140046dce  call    cs:__imp_SetLastError
0x140046dd4  mov     rax, cs:WPP_GLOBAL_Control
0x140046ddb  cmp     rax, r15
0x140046dde  jz      short loc_140046E11
0x140046de0  test    [rax+1Ch], r14b
0x140046de4  jz      short loc_140046E11
0x140046de6  cmp     [rax+19h], r13b
0x140046dea  jb      short loc_140046E11
0x140046dec  call    cs:__imp_GetLastError
0x140046df2  mov     rcx, cs:WPP_GLOBAL_Control
0x140046df9  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140046e00  mov     edx, 3Ch ; '<'
0x140046e05  mov     r9d, eax
0x140046e08  mov     rcx, [rcx+10h]
0x140046e0c  call    WPP_SF_d
0x140046e11  call    ?NotifyServiceThreadsToTerminate@@YAHXZ; NotifyServiceThreadsToTerminate(void)
0x140046e16  test    eax, eax
0x140046e18  jnz     short loc_140046E45
0x140046e1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140046e21  cmp     rcx, r15
0x140046e24  jz      short loc_140046E45
0x140046e26  test    [rcx+1Ch], r14b
0x140046e2a  jz      short loc_140046E45
0x140046e2c  cmp     [rcx+19h], r13b
0x140046e30  jb      short loc_140046E45
0x140046e32  mov     rcx, [rcx+10h]
0x140046e36  lea     edx, [rax+3Dh]
0x140046e39  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140046e40  call    WPP_SF_
0x140046e45  call    ?StopAllInProgressJobs@@YAHXZ; StopAllInProgressJobs(void)
0x140046e4a  test    eax, eax
0x140046e4c  jnz     short loc_140046E79
0x140046e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140046e55  cmp     rcx, r15
0x140046e58  jz      short loc_140046E79
0x140046e5a  test    [rcx+1Ch], r14b
0x140046e5e  jz      short loc_140046E79
0x140046e60  cmp     [rcx+19h], r13b
0x140046e64  jb      short loc_140046E79
0x140046e66  mov     rcx, [rcx+10h]
0x140046e6a  lea     edx, [rax+3Eh]
0x140046e6d  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140046e74  call    WPP_SF_
0x140046e79  mov     rcx, cs:?g_hThreadCountEvent@@3PEAXEA; hHandle
0x140046e80  test    rcx, rcx
0x140046e83  jz      short loc_140046EFC
0x140046e85  lea     rdx, aWaitingForAllT; "Waiting for all threads (except TapiWor"...
0x140046e8c  call    ?WaitAndReportForThreadToTerminate@@YAHPEAXPEBG@Z; WaitAndReportForThreadToTerminate(void *,ushort const *)
0x140046e91  test    eax, eax
0x140046e93  jnz     short loc_140046ED2
0x140046e95  mov     rax, cs:WPP_GLOBAL_Control
0x140046e9c  cmp     rax, r15
0x140046e9f  jz      short loc_140046ED2
0x140046ea1  test    [rax+1Ch], r14b
0x140046ea5  jz      short loc_140046ED2
0x140046ea7  cmp     [rax+19h], r13b
0x140046eab  jb      short loc_140046ED2
0x140046ead  call    cs:__imp_GetLastError
0x140046eb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140046eba  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140046ec1  mov     edx, 3Fh ; '?'
0x140046ec6  mov     r9d, eax
0x140046ec9  mov     rcx, [rcx+10h]
0x140046ecd  call    WPP_SF_d
0x140046ed2  mov     ecx, 3; unsigned int
0x140046ed7  mov     r8d, 1770h; unsigned int
0x140046edd  call    ?ReportServiceStatus@@YAHKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x140046ee2  lea     rcx, ?g_CsServiceThreads@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140046ee9  call    cs:__imp_EnterCriticalSection
0x140046eef  lea     rcx, ?g_CsServiceThreads@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140046ef6  call    cs:__imp_LeaveCriticalSection
0x140046efc  mov     rcx, cs:?g_TapiCompletionPort@@3PEAXEA; CompletionPort
0x140046f03  test    rcx, rcx
  ... truncated ...
```
