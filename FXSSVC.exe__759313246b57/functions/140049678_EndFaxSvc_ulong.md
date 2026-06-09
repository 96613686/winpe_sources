# EndFaxSvc(ulong)

- ea: `0x140049678`
- end: `0x140049f2b`
- name: `?EndFaxSvc@@YAXK@Z`
- size: `2227`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400246b0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140026388`
- `0x14002dc14`
- `0x14003a1bc`
- `0x14003a304`
- `0x14003a5d8`
- `0x140049678`
- `0x14004ac14`
- `0x14004bc64`
- `0x14004be0c`
- `0x14004bff8`
- `0x14004d5c4`
- `0x140058d78`
- `0x14006998c`
- `0x1400699d0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140049ce7`
- `KERNEL32!FreeLibrary` at `0x140049de2`
- `KERNEL32!FreeLibrary` at `0x140049ce7`
- `KERNEL32!FreeLibrary` at `0x140049de2`
- `KERNEL32!GetLastError` at `0x1400496ff`
- `KERNEL32!GetLastError` at `0x1400497cd`
- `KERNEL32!GetLastError` at `0x140049823`
- `KERNEL32!GetLastError` at `0x14004992b`
- `KERNEL32!GetLastError` at `0x14004997a`
- `KERNEL32!GetLastError` at `0x1400499df`
- `KERNEL32!GetLastError` at `0x140049a30`
- `KERNEL32!GetLastError` at `0x140049afb`
- `KERNEL32!GetLastError` at `0x140049baa`
- `KERNEL32!GetLastError` at `0x140049c09`
- `KERNEL32!GetLastError` at `0x140049c55`
- `KERNEL32!GetLastError` at `0x1400496ff`
- `KERNEL32!GetLastError` at `0x1400497cd`
- `KERNEL32!GetLastError` at `0x140049823`
- `KERNEL32!GetLastError` at `0x14004992b`
- `KERNEL32!GetLastError` at `0x14004997a`
- `KERNEL32!GetLastError` at `0x1400499df`
- `KERNEL32!GetLastError` at `0x140049a30`
- `KERNEL32!GetLastError` at `0x140049afb`
- `KERNEL32!GetLastError` at `0x140049baa`
- `KERNEL32!GetLastError` at `0x140049c09`
- `KERNEL32!GetLastError` at `0x140049c55`
- `KERNEL32!SetLastError` at `0x140049a0c`
- `KERNEL32!SetLastError` at `0x140049a0c`
- `KERNEL32!CloseHandle` at `0x1400497fb`
- `KERNEL32!CloseHandle` at `0x1400499b7`
- `KERNEL32!CloseHandle` at `0x1400497fb`
- `KERNEL32!CloseHandle` at `0x1400499b7`
- `KERNEL32!EnterCriticalSection` at `0x140049b3d`
- `KERNEL32!EnterCriticalSection` at `0x140049b3d`
- `KERNEL32!LeaveCriticalSection` at `0x140049b50`
- `KERNEL32!LeaveCriticalSection` at `0x140049b50`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140049b82`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140049b82`
- `KERNEL32!CreateThread` at `0x140049917`
- `KERNEL32!CreateThread` at `0x140049917`
- `KERNEL32!HeapDestroy` at `0x140049d07`
- `KERNEL32!HeapDestroy` at `0x140049e02`
- `KERNEL32!HeapDestroy` at `0x140049d07`
- `KERNEL32!HeapDestroy` at `0x140049e02`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x14004985d`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x14004985d`
- `RPCRT4!RpcMgmtStopServerListening` at `0x140049755`
- `RPCRT4!RpcMgmtStopServerListening` at `0x140049755`

## string_xrefs

- `0x140049965`: `Waiting for SetServiceIsDownFlagThread to terminate.`
- `0x1400497a5`: `Waiting for RPC listning thread to terminate.`
- `0x140049ad3`: `Waiting for all threads (except TapiWorkerThread) to terminate.`
- `0x140049be1`: `Waiting for TapiWorkerThread to terminate.`

## pseudocode

```c
void __fastcall EndFaxSvc(unsigned int a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  CMapDeviceId *v6; // rcx
  DWORD LastError; // eax
  unsigned int v8; // edi
  unsigned int v9; // eax
  unsigned int v10; // ebx
  DWORD v11; // eax
  DWORD v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  CMapDeviceId *v15; // rcx
  HANDLE Thread; // rax
  void *v17; // rdi
  DWORD v18; // eax
  DWORD v19; // ebx
  CMapDeviceId *v20; // rcx
  __int64 v21; // rdx
  DWORD v22; // eax
  DWORD v23; // eax
  unsigned int v24; // edx
  DWORD v25; // eax
  DWORD v26; // eax
  DWORD v27; // eax
  DWORD v28; // eax
  struct _DEVICE_PROVIDER *v29; // rbx
  struct _DEVICE_PROVIDER *v30; // rdx
  struct _DEVICE_PROVIDER *v31; // rdi
  struct _DEVICE_PROVIDER **v32; // rax
  HMODULE v33; // rcx
  void *v34; // rcx
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY *v36; // r8
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *v38; // rbx
  struct _LIST_ENTRY *v39; // rcx
  LPVOID *v40; // rbx
  LPVOID *v41; // rdx
  LPVOID *v42; // rdi
  LPVOID **v43; // rax
  HMODULE v44; // rcx
  void *v45; // rcx
  struct _HANDLE_ENTRY *v46; // rbx
  struct _HANDLE_ENTRY *v47; // rcx
  DWORD_PTR *v48; // rbx
  DWORD_PTR *v49; // rcx
  DWORD_PTR **v50; // rax
  struct _LINE_INFO *v51; // rbx
  struct _LINE_INFO *v52; // rcx
  struct _LINE_INFO **v53; // rax
  struct _LIST_ENTRY *v54; // rbx
  struct _LIST_ENTRY *v55; // rdx
  struct _LIST_ENTRY *v56; // rcx
  struct _LIST_ENTRY *v57; // rax
  bool v58; // zf
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
  }
  if ( (unsigned int)CreateFaxEvent(0, 0x14u, 0xFFFFFFFF, 0) )
    goto LABEL_10;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
    goto LABEL_15;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, LastError);
LABEL_10:
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_(*((_QWORD *)v6 + 2), 106, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
LABEL_15:
  v8 = 0;
  v9 = RpcMgmtStopServerListening(0);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v9);
    }
    v8 = v10;
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
      v11 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v11);
    }
    if ( !CloseHandle(g_hRPCListeningThread)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v12);
    }
    g_hRPCListeningThread = 0;
  }
  v13 = RpcServerUnregisterIfEx(qword_14008E220, 0, 0);
  v14 = v13;
  if ( !v13 )
    goto LABEL_38;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v13);
LABEL_38:
    v15 = WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    v14 = v8;
  }
  else if ( !v14 )
  {
    goto LABEL_47;
  }
  if ( v15 == (CMapDeviceId *)&WPP_GLOBAL_Control )
    goto LABEL_51;
  if ( (*((_BYTE *)v15 + 28) & 4) != 0 && *((_BYTE *)v15 + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)v15 + 2), 59, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v14);
    v15 = WPP_GLOBAL_Control;
  }
LABEL_47:
  if ( v15 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 && *((_BYTE *)v15 + 25) >= 5u )
    WPP_SF_(*((_QWORD *)v15 + 2), 64, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
LABEL_51:
  Thread = CreateThread(0, 0, SetServiceIsDownFlagThread, 0, 0, 0);
  v17 = Thread;
  if ( Thread )
  {
    v19 = 0;
    if ( !(unsigned int)WaitAndReportForThreadToTerminate(
                          Thread,
                          L"Waiting for SetServiceIsDownFlagThread to terminate.") )
    {
      v22 = GetLastError();
      v19 = v22;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v22);
      }
    }
    if ( !CloseHandle(v17)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = GetLastError();
      v20 = WPP_GLOBAL_Control;
      v21 = 67;
      goto LABEL_66;
    }
  }
  else
  {
    v18 = GetLastError();
    v19 = v18;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = 65;
LABEL_66:
      WPP_SF_d(*((_QWORD *)v20 + 2), v21, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v18);
    }
  }
  if ( v19 )
  {
    SetLastError(v19);
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v23);
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
      v25 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v25);
    }
    ReportServiceStatus(3u, v24, 0x1770u);
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
      v26 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v26);
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
    v27 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v27);
  }
  if ( !(unsigned int)StopFaxServiceProviders()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v28 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v28);
  }
  v29 = g_DeviceProvidersListHead;
  while ( v29 != (struct _DEVICE_PROVIDER *)&g_DeviceProvidersListHead )
  {
    v30 = v29;
    v31 = v29;
    v29 = *(struct _DEVICE_PROVIDER **)v29;
    v32 = (struct _DEVICE_PROVIDER **)*((_QWORD *)v30 + 1);
    *v32 = v29;
    *((_QWORD *)v29 + 1) = v32;
    *(_QWORD *)v30 = 0;
    *((_QWORD *)v30 + 1) = 0;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_200271385d87382553faba38592a1280_Traceguids);
    }
    v33 = (HMODULE)*((_QWORD *)v31 + 7);
    if ( v33 )
      FreeLibrary(v33);
    v34 = (void *)*((_QWORD *)v31 + 269);
    if ( v34 && !*((_DWORD *)v31 + 562) )
      HeapDestroy(v34);
    pMemFree(v31);
  }
  Flink = g_lstRoutingMethods.Flink;
  while ( Flink != &g_lstRoutingMethods )
  {
    v36 = Flink;
    Blink = Flink->Blink;
    v38 = Flink - 1;
    Flink = Flink->Flink;
    Blink->Flink = Flink;
    Flink->Blink = Blink;
    v39 = v38[4].Flink;
    v36->Flink = 0;
    v36->Blink = 0;
    pMemFree(v39);
    pMemFree(v38[3].Blink);
    pMemFree(v38[4].Blink);
    pMemFree(v38);
  }
  v40 = (LPVOID *)g_lstRoutingExtensions;
  while ( v40 != &g_lstRoutingExtensions )
  {
    v41 = v40;
    v42 = v40;
    v40 = (LPVOID *)*v40;
    v43 = (LPVOID **)v41[1];
    *v43 = v40;
    v40[1] = v43;
    *v41 = 0;
    v41[1] = 0;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
    }
    v44 = (HMODULE)v42[2];
    if ( v44 )
      FreeLibrary(v44);
    v45 = v42[202];
    if ( v45 && !*((_DWORD *)v42 + 406) )
      HeapDestroy(v45);
    pMemFree(v42);
  }
  v46 = g_HandleTableListHead;
  while ( v46 != (struct _HANDLE_ENTRY *)&g_HandleTableListHead )
  {
    v47 = v46;
    v46 = *(struct _HANDLE_ENTRY **)v46;
    CloseFaxHandle(v47);
  }
  v48 = (DWORD_PTR *)g_TapiLinesListHead;
  while ( v48 != &g_TapiLinesListHead )
  {
    v49 = v48;
    v48 = (DWORD_PTR *)*v48;
    v50 = (DWORD_PTR **)v49[1];
    *v50 = v48;
    v48[1] = (DWORD_PTR)v50;
    *v49 = 0;
    v49[1] = 0;
    FreeTapiLine((struct _LINE_INFO *)v49);
  }
  v51 = g_RemovedTapiLinesListHead;
  while ( v51 != (struct _LINE_INFO *)&g_RemovedTapiLinesListHead )
  {
    v52 = v51;
    v51 = *(struct _LINE_INFO **)v51;
    v53 = (struct _LINE_INFO **)*((_QWORD *)v52 + 1);
    *v53 = v51;
    *((_QWORD *)v51 + 1) = v53;
    *(_QWORD *)v52 = 0;
    *((_QWORD *)v52 + 1) = 0;
    FreeTapiLine(v52);
  }
  v54 = g_QueueListHead.Flink;
  while ( v54 != &g_QueueListHead )
  {
    v55 = v54->Flink;
    v56 = v54;
    v54 = v55;
    v57 = v56->Blink;
    v57->Flink = v55;
    v55->Blink = v57;
    v58 = HIDWORD(v56[2].Flink) == 32;
    v56->Flink = 0;
    v56->Blink = 0;
    if ( v58 )
    {
      FreeParentQueueEntry((struct _JOB_QUEUE *)v56, (int)v55);
    }
    else if ( HIDWORD(v56[2].Flink) == 2 )
    {
      FreeRecipientQueueEntry((struct _JOB_QUEUE *)v56);
    }
    else if ( HIDWORD(v56[2].Flink) == 8 )
    {
      FreeReceiveQueueEntry((struct _JOB_QUEUE *)v56, (int)v55);
    }
  }
  FaxLog(1u, a1, 0, 0x40007D12u, a5);
}

```

## disassembly

```asm
0x140049678  push    rbx
0x14004967a  push    rbp
0x14004967b  push    rsi
0x14004967c  push    rdi
0x14004967d  push    r12
0x14004967f  push    r13
0x140049681  push    r14
0x140049683  push    r15
0x140049685  sub     rsp, 58h
0x140049689  mov     esi, ecx
0x14004968b  mov     rcx, cs:WPP_GLOBAL_Control
0x140049692  lea     r15, WPP_GLOBAL_Control
0x140049699  mov     r14b, 4
0x14004969c  cmp     rcx, r15
0x14004969f  jz      short loc_1400496C2
0x1400496a1  test    [rcx+1Ch], r14b
0x1400496a5  jz      short loc_1400496C2
0x1400496a7  cmp     byte ptr [rcx+19h], 5
0x1400496ab  jb      short loc_1400496C2
0x1400496ad  mov     rcx, [rcx+10h]
0x1400496b1  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x1400496b8  mov     edx, 39h ; '9'
0x1400496bd  call    WPP_SF_
0x1400496c2  xor     r9d, r9d; void *
0x1400496c5  xor     ecx, ecx; unsigned int
0x1400496c7  mov     r8d, 0FFFFFFFFh; unsigned int
0x1400496cd  lea     edx, [r9+14h]; unsigned int
0x1400496d1  call    ?CreateFaxEvent@@YAHKKKPEAX@Z; CreateFaxEvent(ulong,ulong,ulong,void *)
0x1400496d6  xor     ebp, ebp
0x1400496d8  lea     r12, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400496df  lea     r13d, [rbp+2]
0x1400496e3  test    eax, eax
0x1400496e5  jnz     short loc_140049728
0x1400496e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400496ee  cmp     rcx, r15
0x1400496f1  jz      short loc_140049751
0x1400496f3  test    [rcx+1Ch], r14b
0x1400496f7  jz      short loc_14004972F
0x1400496f9  cmp     [rcx+19h], r13b
0x1400496fd  jb      short loc_14004972F
0x1400496ff  call    cs:__imp_GetLastError
0x140049706  nop     dword ptr [rax+rax+00h]
0x14004970b  mov     rcx, cs:WPP_GLOBAL_Control
0x140049712  lea     edx, [rbp+3Ah]
0x140049715  mov     r9d, eax
0x140049718  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x14004971f  mov     rcx, [rcx+10h]
0x140049723  call    WPP_SF_d
0x140049728  mov     rcx, cs:WPP_GLOBAL_Control
0x14004972f  cmp     rcx, r15
0x140049732  jz      short loc_140049751
0x140049734  test    [rcx+1Ch], r14b
0x140049738  jz      short loc_140049751
0x14004973a  cmp     byte ptr [rcx+19h], 5
0x14004973e  jb      short loc_140049751
0x140049740  mov     rcx, [rcx+10h]
0x140049744  mov     edx, 6Ah ; 'j'
0x140049749  mov     r8, r12
0x14004974c  call    WPP_SF_
0x140049751  xor     ecx, ecx; Binding
0x140049753  mov     edi, ebp
0x140049755  call    cs:__imp_RpcMgmtStopServerListening
0x14004975c  nop     dword ptr [rax+rax+00h]
0x140049761  mov     ebx, eax
0x140049763  test    eax, eax
0x140049765  jz      short loc_140049795
0x140049767  mov     rcx, cs:WPP_GLOBAL_Control
0x14004976e  cmp     rcx, r15
0x140049771  jz      short loc_140049793
0x140049773  test    [rcx+1Ch], r14b
0x140049777  jz      short loc_140049793
0x140049779  cmp     [rcx+19h], r13b
0x14004977d  jb      short loc_140049793
0x14004977f  mov     rcx, [rcx+10h]
0x140049783  mov     edx, 6Bh ; 'k'
0x140049788  mov     r9d, eax
0x14004978b  mov     r8, r12
0x14004978e  call    WPP_SF_d
0x140049793  mov     edi, ebx
0x140049795  mov     rcx, cs:?g_hRPCListeningThread@@3PEAXEA; hHandle
0x14004979c  test    rcx, rcx
0x14004979f  jz      loc_140049851
0x1400497a5  lea     rdx, aWaitingForRpcL; "Waiting for RPC listning thread to term"...
0x1400497ac  call    ?WaitAndReportForThreadToTerminate@@YAHPEAXPEBG@Z; WaitAndReportForThreadToTerminate(void *,ushort const *)
0x1400497b1  test    eax, eax
0x1400497b3  jnz     short loc_1400497F4
0x1400497b5  mov     rax, cs:WPP_GLOBAL_Control
0x1400497bc  cmp     rax, r15
0x1400497bf  jz      short loc_1400497F4
0x1400497c1  test    [rax+1Ch], r14b
0x1400497c5  jz      short loc_1400497F4
0x1400497c7  cmp     [rax+19h], r13b
0x1400497cb  jb      short loc_1400497F4
0x1400497cd  call    cs:__imp_GetLastError
0x1400497d4  nop     dword ptr [rax+rax+00h]
0x1400497d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400497e0  mov     edx, 6Ch ; 'l'
0x1400497e5  mov     r9d, eax
0x1400497e8  mov     r8, r12
0x1400497eb  mov     rcx, [rcx+10h]
0x1400497ef  call    WPP_SF_d
0x1400497f4  mov     rcx, cs:?g_hRPCListeningThread@@3PEAXEA; hObject
0x1400497fb  call    cs:__imp_CloseHandle
0x140049802  nop     dword ptr [rax+rax+00h]
0x140049807  test    eax, eax
0x140049809  jnz     short loc_14004984A
0x14004980b  mov     rax, cs:WPP_GLOBAL_Control
0x140049812  cmp     rax, r15
0x140049815  jz      short loc_14004984A
0x140049817  test    [rax+1Ch], r14b
0x14004981b  jz      short loc_14004984A
0x14004981d  cmp     [rax+19h], r13b
0x140049821  jb      short loc_14004984A
0x140049823  call    cs:__imp_GetLastError
0x14004982a  nop     dword ptr [rax+rax+00h]
0x14004982f  mov     rcx, cs:WPP_GLOBAL_Control
0x140049836  mov     edx, 6Dh ; 'm'
0x14004983b  mov     r9d, eax
0x14004983e  mov     r8, r12
0x140049841  mov     rcx, [rcx+10h]
0x140049845  call    WPP_SF_d
0x14004984a  mov     cs:?g_hRPCListeningThread@@3PEAXEA, rbp; void * g_hRPCListeningThread
0x140049851  xor     r8d, r8d; RundownContextHandles
0x140049854  lea     rcx, qword_14008E220; IfSpec
0x14004985b  xor     edx, edx; MgrTypeUuid
0x14004985d  call    cs:__imp_RpcServerUnregisterIfEx
0x140049864  nop     dword ptr [rax+rax+00h]
0x140049869  mov     ebx, eax
0x14004986b  test    eax, eax
0x14004986d  jz      short loc_14004989B
0x14004986f  mov     rcx, cs:WPP_GLOBAL_Control
0x140049876  cmp     rcx, r15
0x140049879  jz      short loc_1400498A2
0x14004987b  test    [rcx+1Ch], r14b
0x14004987f  jz      short loc_1400498A2
0x140049881  cmp     [rcx+19h], r13b
0x140049885  jb      short loc_1400498A2
0x140049887  mov     rcx, [rcx+10h]
0x14004988b  mov     edx, 6Eh ; 'n'
0x140049890  mov     r9d, eax
0x140049893  mov     r8, r12
0x140049896  call    WPP_SF_d
0x14004989b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400498a2  test    edi, edi
0x1400498a4  jnz     short loc_1400498AC
0x1400498a6  test    ebx, ebx
0x1400498a8  jz      short loc_1400498DE
0x1400498aa  jmp     short loc_1400498AE
0x1400498ac  mov     ebx, edi
0x1400498ae  cmp     rcx, r15
0x1400498b1  jz      short loc_140049900
0x1400498b3  test    [rcx+1Ch], r14b
0x1400498b7  jz      short loc_1400498DE
0x1400498b9  cmp     [rcx+19h], r13b
0x1400498bd  jb      short loc_1400498DE
0x1400498bf  mov     rcx, [rcx+10h]
0x1400498c3  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x1400498ca  mov     edx, 3Bh ; ';'
0x1400498cf  mov     r9d, ebx
0x1400498d2  call    WPP_SF_d
0x1400498d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400498de  cmp     rcx, r15
0x1400498e1  jz      short loc_140049900
0x1400498e3  test    [rcx+1Ch], r14b
0x1400498e7  jz      short loc_140049900
0x1400498e9  cmp     byte ptr [rcx+19h], 5
0x1400498ed  jb      short loc_140049900
0x1400498ef  mov     rcx, [rcx+10h]
0x1400498f3  mov     edx, 40h ; '@'
0x1400498f8  mov     r8, r12
0x1400498fb  call    WPP_SF_
0x140049900  mov     [rsp+98h+lpThreadId], rbp; lpThreadId
0x140049905  lea     r8, ?SetServiceIsDownFlagThread@@YAKPEAX@Z; lpStartAddress
0x14004990c  xor     r9d, r9d; lpParameter
0x14004990f  mov     [rsp+98h+dwCreationFlags], ebp; dwCreationFlags
0x140049913  xor     edx, edx; dwStackSize
0x140049915  xor     ecx, ecx; lpThreadAttributes
0x140049917  call    cs:__imp_CreateThread
0x14004991e  nop     dword ptr [rax+rax+00h]
0x140049923  mov     rdi, rax
0x140049926  test    rax, rax
0x140049929  jnz     short loc_140049965
0x14004992b  call    cs:__imp_GetLastError
0x140049932  nop     dword ptr [rax+rax+00h]
0x140049937  mov     ebx, eax
0x140049939  mov     rcx, cs:WPP_GLOBAL_Control
0x140049940  cmp     rcx, r15
0x140049943  jz      loc_140049A06
0x140049949  test    [rcx+1Ch], r14b
0x14004994d  jz      loc_140049A06
0x140049953  cmp     [rcx+19h], r13b
0x140049957  jb      loc_140049A06
0x14004995d  lea     edx, [rdi+41h]
0x140049960  jmp     loc_1400499F7
0x140049965  lea     rdx, aWaitingForSets; "Waiting for SetServiceIsDownFlagThread "...
0x14004996c  mov     rcx, rdi; hHandle
0x14004996f  mov     ebx, ebp
0x140049971  call    ?WaitAndReportForThreadToTerminate@@YAHPEAXPEBG@Z; WaitAndReportForThreadToTerminate(void *,ushort const *)
0x140049976  test    eax, eax
0x140049978  jnz     short loc_1400499B4
0x14004997a  call    cs:__imp_GetLastError
0x140049981  nop     dword ptr [rax+rax+00h]
0x140049986  mov     ebx, eax
0x140049988  mov     rcx, cs:WPP_GLOBAL_Control
0x14004998f  cmp     rcx, r15
0x140049992  jz      short loc_1400499B4
0x140049994  test    [rcx+1Ch], r14b
0x140049998  jz      short loc_1400499B4
0x14004999a  cmp     [rcx+19h], r13b
0x14004999e  jb      short loc_1400499B4
0x1400499a0  mov     rcx, [rcx+10h]
0x1400499a4  mov     edx, 42h ; 'B'
0x1400499a9  mov     r9d, eax
0x1400499ac  mov     r8, r12
0x1400499af  call    WPP_SF_d
0x1400499b4  mov     rcx, rdi; hObject
0x1400499b7  call    cs:__imp_CloseHandle
0x1400499be  nop     dword ptr [rax+rax+00h]
0x1400499c3  test    eax, eax
0x1400499c5  jnz     short loc_140049A06
0x1400499c7  mov     rax, cs:WPP_GLOBAL_Control
0x1400499ce  cmp     rax, r15
0x1400499d1  jz      short loc_140049A06
0x1400499d3  test    [rax+1Ch], r14b
0x1400499d7  jz      short loc_140049A06
0x1400499d9  cmp     [rax+19h], r13b
0x1400499dd  jb      short loc_140049A06
0x1400499df  call    cs:__imp_GetLastError
0x1400499e6  nop     dword ptr [rax+rax+00h]
0x1400499eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400499f2  mov     edx, 43h ; 'C'
0x1400499f7  mov     rcx, [rcx+10h]
0x1400499fb  mov     r9d, eax
0x1400499fe  mov     r8, r12
0x140049a01  call    WPP_SF_d
0x140049a06  test    ebx, ebx
0x140049a08  jz      short loc_140049A5B
0x140049a0a  mov     ecx, ebx; dwErrCode
0x140049a0c  call    cs:__imp_SetLastError
0x140049a13  nop     dword ptr [rax+rax+00h]
0x140049a18  mov     rax, cs:WPP_GLOBAL_Control
0x140049a1f  cmp     rax, r15
0x140049a22  jz      short loc_140049A5B
0x140049a24  test    [rax+1Ch], r14b
0x140049a28  jz      short loc_140049A5B
0x140049a2a  cmp     [rax+19h], r13b
0x140049a2e  jb      short loc_140049A5B
0x140049a30  call    cs:__imp_GetLastError
0x140049a37  nop     dword ptr [rax+rax+00h]
0x140049a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140049a43  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140049a4a  mov     edx, 3Ch ; '<'
0x140049a4f  mov     r9d, eax
0x140049a52  mov     rcx, [rcx+10h]
0x140049a56  call    WPP_SF_d
0x140049a5b  call    ?NotifyServiceThreadsToTerminate@@YAHXZ; NotifyServiceThreadsToTerminate(void)
0x140049a60  test    eax, eax
0x140049a62  jnz     short loc_140049A8F
0x140049a64  mov     rcx, cs:WPP_GLOBAL_Control
0x140049a6b  cmp     rcx, r15
0x140049a6e  jz      short loc_140049A8F
0x140049a70  test    [rcx+1Ch], r14b
0x140049a74  jz      short loc_140049A8F
0x140049a76  cmp     [rcx+19h], r13b
0x140049a7a  jb      short loc_140049A8F
0x140049a7c  mov     rcx, [rcx+10h]
0x140049a80  lea     edx, [rax+3Dh]
0x140049a83  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140049a8a  call    WPP_SF_
0x140049a8f  call    ?StopAllInProgressJobs@@YAHXZ; StopAllInProgressJobs(void)
0x140049a94  test    eax, eax
0x140049a96  jnz     short loc_140049AC3
0x140049a98  mov     rcx, cs:WPP_GLOBAL_Control
0x140049a9f  cmp     rcx, r15
0x140049aa2  jz      short loc_140049AC3
0x140049aa4  test    [rcx+1Ch], r14b
0x140049aa8  jz      short loc_140049AC3
0x140049aaa  cmp     [rcx+19h], r13b
0x140049aae  jb      short loc_140049AC3
0x140049ab0  mov     rcx, [rcx+10h]
0x140049ab4  lea     edx, [rax+3Eh]
0x140049ab7  lea     r8, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140049abe  call    WPP_SF_
0x140049ac3  mov     rcx, cs:?g_hThreadCountEvent@@3PEAXEA; hHandle
0x140049aca  test    rcx, rcx
0x140049acd  jz      loc_140049B5C
0x140049ad3  lea     rdx, aWaitingForAllT; "Waiting for all threads (except TapiWor"...
0x140049ada  call    ?WaitAndReportForThreadToTerminate@@YAHPEAXPEBG@Z; WaitAndReportForThreadToTerminate(void *,ushort const *)
0x140049adf  test    eax, eax
0x140049ae1  jnz     short loc_140049B26
0x140049ae3  mov     rax, cs:WPP_GLOBAL_Control
0x140049aea  cmp     rax, r15
0x140049aed  jz      short loc_140049B26
0x140049aef  test    [rax+1Ch], r14b
0x140049af3  jz      short loc_140049B26
0x140049af5  cmp     [rax+19h], r13b
0x140049af9  jb      short loc_140049B26
0x140049afb  call    cs:__imp_GetLastError
0x140049b02  nop     dword ptr [rax+rax+00h]
0x140049b07  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
