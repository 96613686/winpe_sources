# DataCollectorCreate(ulong,void *)

- ea: `0x14001628c`
- end: `0x140016b28`
- name: `?DataCollectorCreate@@YAJKPEAX@Z`
- size: `2204`
- prototype: `__int64 __fastcall(DWORD dwProcessId, HANDLE hFileMappingObject)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14000e49c`

## callees

- `0x140003230`
- `0x14000473c`
- `0x14000e318`
- `0x14000e340`
- `0x14001628c`
- `0x14001a21c`
- `0x14001a504`
- `0x14001c9a8`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400163ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140016476`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001686f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400163ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140016476`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001686f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400162e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001635d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400163d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400164a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400167e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400168a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400169a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400162e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001635d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400163d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400164a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400167e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400168a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400169a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016830`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400168fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400169f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016a34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016ae6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016b05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016830`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400168fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400169f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016a34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016ae6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016b05`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400163cc`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140016496`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140016896`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1400163cc`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140016496`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140016896`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14001634b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1400167d1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14001634b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1400167d1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400168f1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400169ec`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140016a2a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140016af5`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400168f1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1400169ec`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140016a2a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140016af5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140016730`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140016730`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400164ef`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400164ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400165d4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400165d4`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x14001655a`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x14001655a`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1400166a9`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1400166a9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400167b0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140016a5a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140016abe`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400167b0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140016a5a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140016abe`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400162c8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400162c8`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140016982`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140016982`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140016935`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140016ad2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140016935`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140016ad2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140016425`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140016425`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall DataCollectorCreate(DWORD dwProcessId, HANDLE hFileMappingObject)
{
  _DWORD *v3; // rsi
  char *v4; // r15
  unsigned __int64 v5; // r12
  signed int LastError; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _DWORD *v10; // rax
  signed int v11; // eax
  HANDLE *v12; // rbx
  HANDLE CurrentProcess; // rax
  signed int v14; // eax
  HANDLE EventW; // r13
  signed int v16; // eax
  HANDLE v17; // rax
  signed int v18; // eax
  HRESULT v19; // eax
  HRESULT v20; // eax
  LPUNKNOWN v21; // rcx
  unsigned int *v22; // r14
  HRESULT v23; // eax
  size_t v24; // rbx
  const void *v25; // rdi
  HANDLE FileMappingW; // rax
  void *v27; // r15
  signed int v28; // eax
  void *v29; // rax
  const void *v30; // r12
  signed int v31; // eax
  HANDLE v32; // rax
  signed int v33; // eax
  DWORD v34; // eax
  signed int v35; // eax
  HANDLE v36; // rcx
  char *hTargetProcessHandle; // [rsp+50h] [rbp-49h]
  HANDLE hEvent; // [rsp+58h] [rbp-41h] BYREF
  char *v40; // [rsp+60h] [rbp-39h]
  HANDLE TargetHandle; // [rsp+68h] [rbp-31h] BYREF
  HANDLE v42[2]; // [rsp+70h] [rbp-29h] BYREF
  HANDLE Handles[2]; // [rsp+80h] [rbp-19h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp-9h] BYREF
  LPUNKNOWN *p_pUnk; // [rsp+98h] [rbp-1h]
  _DWORD *v46; // [rsp+A8h] [rbp+Fh]
  HANDLE v47; // [rsp+B0h] [rbp+17h]
  void *v48; // [rsp+B8h] [rbp+1Fh]
  LPUNKNOWN pUnk; // [rsp+118h] [rbp+7Fh] BYREF

  v3 = 0;
  hEvent = 0;
  TargetHandle = 0;
  *(_OWORD *)Handles = 0;
  v4 = (char *)OpenProcess(0x100040u, 0, dwProcessId);
  hTargetProcessHandle = v4;
  v5 = (unsigned __int64)(v4 + 1);
  v40 = v4 + 1;
  if ( (unsigned __int64)(v4 + 1) <= 1 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 10;
LABEL_7:
      WPP_SF_d(v8[2], v9, WPP_9855411f486d3087210a318e055e6d56_Traceguids, v7);
      goto LABEL_107;
    }
    goto LABEL_107;
  }
  v10 = MapViewOfFile(hFileMappingObject, 2u, 0, 0, 0);
  v3 = v10;
  v46 = v10;
  if ( !v10 )
  {
    v11 = GetLastError();
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 11;
      goto LABEL_7;
    }
LABEL_107:
    if ( (v7 & 0x80000000) == 0 )
      goto LABEL_117;
    goto LABEL_115;
  }
  v10[2] = -2147467259;
  v12 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&hEvent);
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(v4, *(HANDLE *)v3, CurrentProcess, v12, 2u, 0, 0) )
  {
    v14 = GetLastError();
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    v3[2] = v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 12;
      goto LABEL_7;
    }
    goto LABEL_107;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW )
  {
    v16 = GetLastError();
    v7 = v16;
    if ( v16 > 0 )
      v7 = (unsigned __int16)v16 | 0x80070000;
    v3[2] = v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 13;
      goto LABEL_7;
    }
    goto LABEL_107;
  }
  v17 = GetCurrentProcess();
  if ( !DuplicateHandle(v17, EventW, v4, &TargetHandle, 2u, 0, 0) )
  {
    v18 = GetLastError();
    v7 = v18;
    if ( v18 > 0 )
      v7 = (unsigned __int16)v18 | 0x80070000;
    v3[2] = v7;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 14;
      goto LABEL_7;
    }
    goto LABEL_107;
  }
  *((_QWORD *)v3 + 2) = TargetHandle;
  v19 = CoInitializeEx(0, 0);
  v7 = v19;
  if ( v19 < 0 )
  {
    v3[2] = v19;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_9855411f486d3087210a318e055e6d56_Traceguids,
        (unsigned int)v19);
    goto LABEL_115;
  }
  v20 = CoInitializeSecurity(0, -1, 0, 0, 0, 2u, 0, 0, 0);
  v7 = v20;
  if ( v20 >= 0 )
  {
    ppv = 0;
    p_pUnk = &pUnk;
    pUnk = 0;
    v7 = CoCreateInstance(
           &GUID_2c256447_3f0d_4cbb_9d12_575bb20cda0a,
           0,
           1u,
           &GUID_f61082c5_ed37_4a0e_a1b1_08ee41314935,
           &ppv);
    if ( ppv )
    {
      v21 = *p_pUnk;
      *p_pUnk = (LPUNKNOWN)ppv;
      if ( v21 )
        ((void (__fastcall *)(LPUNKNOWN))v21->lpVtbl->Release)(v21);
    }
    if ( (v7 & 0x80000000) != 0 )
    {
      v3[2] = v7;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9855411f486d3087210a318e055e6d56_Traceguids, v7);
      if ( pUnk )
        ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
      goto LABEL_114;
    }
    v22 = (unsigned int *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v22 )
    {
      v7 = -2147024882;
      v3[2] = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9855411f486d3087210a318e055e6d56_Traceguids, 2147942414LL);
      if ( pUnk )
        ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
      goto LABEL_114;
    }
    *(_QWORD *)v22 = &MEMORY_STREAM::`vftable';
    *((_QWORD *)v22 + 1) = 0;
    *((_QWORD *)v22 + 2) = 0;
    *((_WORD *)v22 + 12) = 257;
    v42[1] = v22;
    v23 = CoMarshalInterface((LPSTREAM)v22, &GUID_f61082c5_ed37_4a0e_a1b1_08ee41314935, pUnk, 0, 0, 0);
    v7 = v23;
    if ( v23 < 0 )
    {
      v3[2] = v23;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_9855411f486d3087210a318e055e6d56_Traceguids,
          (unsigned int)v23);
      MstmFree((struct IStream *)v22);
      if ( pUnk )
        ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
      goto LABEL_114;
    }
    v24 = v22[4];
    v25 = (const void *)*((_QWORD *)v22 + 1);
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, v22[4], 0);
    v27 = FileMappingW;
    v47 = FileMappingW;
    if ( (unsigned __int64)FileMappingW + 1 <= 1 )
    {
      v28 = GetLastError();
      v7 = v28;
      if ( v28 > 0 )
        v7 = (unsigned __int16)v28 | 0x80070000;
      v3[2] = v7;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_9855411f486d3087210a318e055e6d56_Traceguids, v7);
      MstmFree((struct IStream *)v22);
      if ( pUnk )
        ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
      CoUninitialize();
      goto LABEL_106;
    }
    v29 = MapViewOfFile(FileMappingW, 2u, 0, 0, 0);
    v30 = v29;
    v48 = v29;
    if ( v29 )
    {
      memcpy_0(v29, v25, v24);
      v42[0] = 0;
      v32 = GetCurrentProcess();
      if ( DuplicateHandle(v32, v27, hTargetProcessHandle, v42, 4u, 0, 0) )
      {
        v3[2] = 0;
        *((HANDLE *)v3 + 3) = v42[0];
        SetEvent(hEvent);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_9855411f486d3087210a318e055e6d56_Traceguids);
        Handles[0] = EventW;
        Handles[1] = hTargetProcessHandle;
        v34 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
        if ( v34 )
        {
          if ( v34 == 1 )
          {
            v7 = -2147023829;
          }
          else
          {
            if ( v34 == -1 )
            {
              v35 = GetLastError();
              v7 = v35;
              if ( v35 > 0 )
                v7 = (unsigned __int16)v35 | 0x80070000;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_9855411f486d3087210a318e055e6d56_Traceguids, v7);
              }
              UnmapViewOfFile(v30);
              CloseHandle(v27);
              MstmFree((struct IStream *)v22);
              if ( pUnk )
                ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
              goto LABEL_105;
            }
            v7 = -2147467259;
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
        }
        else
        {
          v7 = 0;
        }
        UnmapViewOfFile(v30);
        CloseHandle(v27);
        MstmFree((struct IStream *)v22);
        if ( pUnk )
          ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
      }
      else
      {
        v33 = GetLastError();
        v7 = v33;
        if ( v33 > 0 )
          v7 = (unsigned __int16)v33 | 0x80070000;
        v3[2] = v7;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_9855411f486d3087210a318e055e6d56_Traceguids, v7);
        UnmapViewOfFile(v30);
        CloseHandle(v27);
        MstmFree((struct IStream *)v22);
        if ( pUnk )
          ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
      }
    }
    else
    {
      v31 = GetLastError();
      v7 = v31;
      if ( v31 > 0 )
        v7 = (unsigned __int16)v31 | 0x80070000;
      v3[2] = v7;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_9855411f486d3087210a318e055e6d56_Traceguids, v7);
      CloseHandle(v27);
      MstmFree((struct IStream *)v22);
      if ( pUnk )
        ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
    }
LABEL_105:
    CoUninitialize();
    v5 = (unsigned __int64)v40;
LABEL_106:
    v4 = hTargetProcessHandle;
    goto LABEL_107;
  }
  v3[2] = v20;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_9855411f486d3087210a318e055e6d56_Traceguids,
      (unsigned int)v20);
LABEL_114:
  CoUninitialize();
LABEL_115:
  v36 = hEvent;
  if ( (unsigned __int64)hEvent + 1 <= 1 )
    goto LABEL_118;
  SetEvent(hEvent);
LABEL_117:
  v36 = hEvent;
LABEL_118:
  if ( (unsigned __int64)v36 + 1 > 1 )
    CloseHandle(v36);
  if ( v3 )
    UnmapViewOfFile(v3);
  if ( v5 > 1 )
    CloseHandle(v4);
  return v7;
}

```

## disassembly

```asm
0x14001628c  mov     [rsp-8+arg_0], rbx
0x140016291  push    rbp
0x140016292  push    rsi
0x140016293  push    rdi
0x140016294  push    r12
0x140016296  push    r13
0x140016298  push    r14
0x14001629a  push    r15
0x14001629c  lea     rbp, [rsp-27h]
0x1400162a1  sub     rsp, 0C0h
0x1400162a8  mov     rbx, rdx
0x1400162ab  xor     edi, edi
0x1400162ad  mov     esi, edi
0x1400162af  mov     [rbp+57h+hEvent], rdi
0x1400162b3  mov     [rbp+57h+TargetHandle], rdi
0x1400162b7  xorps   xmm0, xmm0
0x1400162ba  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x1400162be  mov     r8d, ecx; dwProcessId
0x1400162c1  xor     edx, edx; bInheritHandle
0x1400162c3  mov     ecx, 100040h; dwDesiredAccess
0x1400162c8  call    cs:__imp_OpenProcess
0x1400162ce  mov     r15, rax
0x1400162d1  mov     [rbp+57h+hTargetProcessHandle], rax
0x1400162d5  lea     r12, [rax+1]
0x1400162d9  mov     [rbp+57h+var_90], r12
0x1400162dd  cmp     r12, 1
0x1400162e1  ja      short loc_140016336
0x1400162e3  call    cs:__imp_GetLastError
0x1400162e9  mov     ebx, eax
0x1400162eb  test    eax, eax
0x1400162ed  jle     short loc_1400162F8
0x1400162ef  movzx   ebx, ax
0x1400162f2  or      ebx, 80070000h
0x1400162f8  lea     rdi, WPP_GLOBAL_Control
0x1400162ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140016306  cmp     rcx, rdi
0x140016309  jz      loc_140016A68
0x14001630f  test    byte ptr [rcx+1Ch], 1
0x140016313  jz      loc_140016A68
0x140016319  mov     edx, 0Ah
0x14001631e  mov     r9d, ebx
0x140016321  lea     r8, WPP_9855411f486d3087210a318e055e6d56_Traceguids
0x140016328  mov     rcx, [rcx+10h]
0x14001632c  call    WPP_SF_d
0x140016331  jmp     loc_140016A68
0x140016336  mov     [rsp+0F0h+dwNumberOfBytesToMap], rdi; dwNumberOfBytesToMap
0x14001633b  xor     r9d, r9d; dwFileOffsetLow
0x14001633e  xor     r8d, r8d; dwFileOffsetHigh
0x140016341  lea     r14d, [r9+2]
0x140016345  mov     edx, r14d; dwDesiredAccess
0x140016348  mov     rcx, rbx; hFileMappingObject
0x14001634b  call    cs:__imp_MapViewOfFile
0x140016351  mov     rsi, rax
0x140016354  mov     [rbp+57h+var_48], rax
0x140016358  test    rax, rax
0x14001635b  jnz     short loc_14001639A
0x14001635d  call    cs:__imp_GetLastError
0x140016363  mov     ebx, eax
0x140016365  test    eax, eax
0x140016367  jle     short loc_140016372
0x140016369  movzx   ebx, ax
0x14001636c  or      ebx, 80070000h
0x140016372  lea     rdi, WPP_GLOBAL_Control
0x140016379  mov     rcx, cs:WPP_GLOBAL_Control
0x140016380  cmp     rcx, rdi
0x140016383  jz      loc_140016A68
0x140016389  test    byte ptr [rcx+1Ch], 1
0x14001638d  jz      loc_140016A68
0x140016393  mov     edx, 0Bh
0x140016398  jmp     short loc_14001631E
0x14001639a  mov     dword ptr [rax+8], 80004005h
0x1400163a1  lea     rcx, [rbp+57h+hEvent]
0x1400163a5  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1400163aa  mov     rbx, rax
0x1400163ad  call    cs:__imp_GetCurrentProcess
0x1400163b3  mov     rdx, [rsi]; hSourceHandle
0x1400163b6  mov     [rsp+0F0h+dwOptions], edi; dwOptions
0x1400163ba  mov     [rsp+0F0h+bInheritHandle], edi; bInheritHandle
0x1400163be  mov     dword ptr [rsp+0F0h+dwNumberOfBytesToMap], r14d; dwDesiredAccess
0x1400163c3  mov     r9, rbx; lpTargetHandle
0x1400163c6  mov     r8, rax; hTargetProcessHandle
0x1400163c9  mov     rcx, r15; hSourceProcessHandle
0x1400163cc  call    cs:__imp_DuplicateHandle
0x1400163d2  test    eax, eax
0x1400163d4  jnz     short loc_140016419
0x1400163d6  call    cs:__imp_GetLastError
0x1400163dc  mov     ebx, eax
0x1400163de  test    eax, eax
0x1400163e0  jle     short loc_1400163EB
0x1400163e2  movzx   ebx, ax
0x1400163e5  or      ebx, 80070000h
0x1400163eb  mov     [rsi+8], ebx
0x1400163ee  lea     rdi, WPP_GLOBAL_Control
0x1400163f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400163fc  cmp     rcx, rdi
0x1400163ff  jz      loc_140016A68
0x140016405  test    byte ptr [rcx+1Ch], 1
0x140016409  jz      loc_140016A68
0x14001640f  mov     edx, 0Ch
0x140016414  jmp     loc_14001631E
0x140016419  xor     r9d, r9d; lpName
0x14001641c  xor     r8d, r8d; bInitialState
0x14001641f  lea     edx, [r9+1]; bManualReset
0x140016423  xor     ecx, ecx; lpEventAttributes
0x140016425  call    cs:__imp_CreateEventW
0x14001642b  mov     r13, rax
0x14001642e  test    rax, rax
0x140016431  jnz     short loc_140016476
0x140016433  call    cs:__imp_GetLastError
0x140016439  mov     ebx, eax
0x14001643b  test    eax, eax
0x14001643d  jle     short loc_140016448
0x14001643f  movzx   ebx, ax
0x140016442  or      ebx, 80070000h
0x140016448  mov     [rsi+8], ebx
0x14001644b  lea     rdi, WPP_GLOBAL_Control
0x140016452  mov     rcx, cs:WPP_GLOBAL_Control
0x140016459  cmp     rcx, rdi
0x14001645c  jz      loc_140016A68
0x140016462  test    byte ptr [rcx+1Ch], 1
0x140016466  jz      loc_140016A68
0x14001646c  mov     edx, 0Dh
0x140016471  jmp     loc_14001631E
0x140016476  call    cs:__imp_GetCurrentProcess
0x14001647c  mov     [rsp+0F0h+dwOptions], edi; dwOptions
0x140016480  mov     [rsp+0F0h+bInheritHandle], edi; bInheritHandle
0x140016484  mov     dword ptr [rsp+0F0h+dwNumberOfBytesToMap], r14d; dwDesiredAccess
0x140016489  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x14001648d  mov     r8, r15; hTargetProcessHandle
0x140016490  mov     rdx, r13; hSourceHandle
0x140016493  mov     rcx, rax; hSourceProcessHandle
0x140016496  call    cs:__imp_DuplicateHandle
0x14001649c  test    eax, eax
0x14001649e  jnz     short loc_1400164E3
0x1400164a0  call    cs:__imp_GetLastError
0x1400164a6  mov     ebx, eax
0x1400164a8  test    eax, eax
0x1400164aa  jle     short loc_1400164B5
0x1400164ac  movzx   ebx, ax
0x1400164af  or      ebx, 80070000h
0x1400164b5  mov     [rsi+8], ebx
0x1400164b8  lea     rdi, WPP_GLOBAL_Control
0x1400164bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400164c6  cmp     rcx, rdi
0x1400164c9  jz      loc_140016A68
0x1400164cf  test    byte ptr [rcx+1Ch], 1
0x1400164d3  jz      loc_140016A68
0x1400164d9  mov     edx, 0Eh
0x1400164de  jmp     loc_14001631E
0x1400164e3  mov     rax, [rbp+57h+TargetHandle]
0x1400164e7  mov     [rsi+10h], rax
0x1400164eb  xor     edx, edx; dwCoInit
0x1400164ed  xor     ecx, ecx; pvReserved
0x1400164ef  call    cs:__imp_CoInitializeEx
0x1400164f5  mov     ebx, eax
0x1400164f7  mov     [rbp+57h+arg_10], eax
0x1400164fa  test    eax, eax
0x1400164fc  jns     short loc_140016538
0x1400164fe  mov     [rsi+8], eax
0x140016501  lea     rdi, WPP_GLOBAL_Control
0x140016508  mov     rcx, cs:WPP_GLOBAL_Control
0x14001650f  cmp     rcx, rdi
0x140016512  jz      short loc_140016533
0x140016514  test    byte ptr [rcx+1Ch], 1
0x140016518  jz      short loc_140016533
0x14001651a  mov     edx, 0Fh
0x14001651f  mov     r9d, eax
0x140016522  lea     r8, WPP_9855411f486d3087210a318e055e6d56_Traceguids
0x140016529  mov     rcx, [rcx+10h]
0x14001652d  call    WPP_SF_d
0x140016532  nop
0x140016533  jmp     loc_140016AC4
0x140016538  mov     [rsp+0F0h+pReserved3], rdi; pReserved3
0x14001653d  mov     [rsp+0F0h+dwCapabilities], edi; dwCapabilities
0x140016541  mov     qword ptr [rsp+0F0h+dwOptions], rdi; pAuthList
0x140016546  mov     [rsp+0F0h+bInheritHandle], r14d; dwImpLevel
0x14001654b  mov     dword ptr [rsp+0F0h+dwNumberOfBytesToMap], edi; dwAuthnLevel
0x14001654f  xor     r9d, r9d; pReserved1
0x140016552  xor     r8d, r8d; asAuthSvc
0x140016555  or      edx, 0FFFFFFFFh; cAuthSvc
0x140016558  xor     ecx, ecx; pSecDesc
0x14001655a  call    cs:__imp_CoInitializeSecurity
0x140016560  mov     ebx, eax
0x140016562  test    eax, eax
0x140016564  jns     short loc_1400165A7
0x140016566  mov     [rsi+8], eax
0x140016569  lea     rdi, WPP_GLOBAL_Control
0x140016570  mov     rcx, cs:WPP_GLOBAL_Control
0x140016577  cmp     rcx, rdi
0x14001657a  jz      loc_140016ABE
0x140016580  test    byte ptr [rcx+1Ch], 1
0x140016584  jz      loc_140016ABE
0x14001658a  mov     edx, 10h
0x14001658f  mov     r9d, eax
0x140016592  lea     r8, WPP_9855411f486d3087210a318e055e6d56_Traceguids
0x140016599  mov     rcx, [rcx+10h]
0x14001659d  call    WPP_SF_d
0x1400165a2  jmp     loc_140016ABE
0x1400165a7  mov     [rbp+57h+ppv], rdi
0x1400165ab  lea     rax, [rbp+57h+pUnk]
0x1400165af  mov     [rbp+57h+var_58], rax
0x1400165b3  mov     [rbp+57h+pUnk], rdi
0x1400165b7  lea     rax, [rbp+57h+ppv]
0x1400165bb  mov     [rsp+0F0h+dwNumberOfBytesToMap], rax; ppv
0x1400165c0  lea     r9, _GUID_f61082c5_ed37_4a0e_a1b1_08ee41314935; riid
0x1400165c7  xor     edx, edx; pUnkOuter
0x1400165c9  lea     r8d, [rdx+1]; dwClsContext
0x1400165cd  lea     rcx, _GUID_2c256447_3f0d_4cbb_9d12_575bb20cda0a; rclsid
0x1400165d4  call    cs:__imp_CoCreateInstance
0x1400165da  mov     ebx, eax
0x1400165dc  mov     rdx, [rbp+57h+ppv]
0x1400165e0  test    rdx, rdx
0x1400165e3  jz      short loc_140016601
0x1400165e5  mov     rax, [rbp+57h+var_58]
0x1400165e9  mov     rcx, [rax]
0x1400165ec  mov     [rax], rdx
0x1400165ef  test    rcx, rcx
0x1400165f2  jz      short loc_140016601
0x1400165f4  mov     rax, [rcx]
0x1400165f7  mov     rax, [rax+10h]
0x1400165fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016600  nop
0x140016601  test    ebx, ebx
0x140016603  jns     short loc_140016655
0x140016605  mov     [rsi+8], ebx
0x140016608  lea     rdi, WPP_GLOBAL_Control
0x14001660f  mov     rcx, cs:WPP_GLOBAL_Control
0x140016616  cmp     rcx, rdi
0x140016619  jz      short loc_14001663A
0x14001661b  test    byte ptr [rcx+1Ch], 1
0x14001661f  jz      short loc_14001663A
0x140016621  mov     edx, 11h
0x140016626  mov     r9d, ebx
0x140016629  lea     r8, WPP_9855411f486d3087210a318e055e6d56_Traceguids
0x140016630  mov     rcx, [rcx+10h]
0x140016634  call    WPP_SF_d
0x140016639  nop
0x14001663a  mov     rcx, [rbp+57h+pUnk]
0x14001663e  test    rcx, rcx
0x140016641  jz      short loc_140016650
0x140016643  mov     rax, [rcx]
0x140016646  mov     rax, [rax+10h]
0x14001664a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001664f  nop
0x140016650  jmp     loc_140016ABE
0x140016655  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001665c  mov     ecx, 20h ; ' '; unsigned __int64
0x140016661  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140016666  mov     r14, rax
0x140016669  test    rax, rax
0x14001666c  jz      loc_140016A6E
0x140016672  lea     rax, ??_7MEMORY_STREAM@@6B@; const MEMORY_STREAM::`vftable'
0x140016679  mov     [r14], rax
0x14001667c  mov     [r14+8], rdi
0x140016680  mov     [r14+10h], rdi
0x140016684  mov     word ptr [r14+18h], 101h
0x14001668b  mov     [rbp+57h+var_78], r14
0x14001668f  mov     [rsp+0F0h+bInheritHandle], edi; mshlflags
0x140016693  mov     [rsp+0F0h+dwNumberOfBytesToMap], rdi; pvDestContext
0x140016698  xor     r9d, r9d; dwDestContext
0x14001669b  mov     r8, [rbp+57h+pUnk]; pUnk
0x14001669f  lea     rdx, _GUID_f61082c5_ed37_4a0e_a1b1_08ee41314935; riid
0x1400166a6  mov     rcx, r14; pStm
0x1400166a9  call    cs:__imp_CoMarshalInterface
0x1400166af  mov     ebx, eax
0x1400166b1  test    eax, eax
0x1400166b3  jns     short loc_14001670E
0x1400166b5  mov     [rsi+8], eax
0x1400166b8  lea     rdi, WPP_GLOBAL_Control
0x1400166bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400166c6  cmp     rcx, rdi
0x1400166c9  jz      short loc_1400166EA
0x1400166cb  test    byte ptr [rcx+1Ch], 1
0x1400166cf  jz      short loc_1400166EA
0x1400166d1  mov     edx, 13h
0x1400166d6  mov     r9d, eax
0x1400166d9  lea     r8, WPP_9855411f486d3087210a318e055e6d56_Traceguids
0x1400166e0  mov     rcx, [rcx+10h]
0x1400166e4  call    WPP_SF_d
0x1400166e9  nop
0x1400166ea  mov     rcx, r14; struct IStream *
0x1400166ed  call    ?MstmFree@@YAXPEAUIStream@@@Z; MstmFree(IStream *)
0x1400166f2  nop
0x1400166f3  mov     rcx, [rbp+57h+pUnk]
0x1400166f7  test    rcx, rcx
0x1400166fa  jz      short loc_140016709
0x1400166fc  mov     rax, [rcx]
0x1400166ff  mov     rax, [rax+10h]
0x140016703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016708  nop
0x140016709  jmp     loc_140016ABE
0x14001670e  mov     ebx, [r14+10h]
0x140016712  mov     rdi, [r14+8]
0x140016716  mov     qword ptr [rsp+0F0h+bInheritHandle], 0; lpName
0x14001671f  mov     dword ptr [rsp+0F0h+dwNumberOfBytesToMap], ebx; dwMaximumSizeLow
0x140016723  xor     r9d, r9d; dwMaximumSizeHigh
0x140016726  xor     edx, edx; lpFileMappingAttributes
0x140016728  lea     r8d, [r9+4]; flProtect
0x14001672c  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x140016730  call    cs:__imp_CreateFileMappingW
  ... truncated ...
```
