# CfOpenFileWithOplock

- ea: `0x180003be0`
- end: `0x18000440b`
- name: `CfOpenFileWithOplock`
- size: `2091`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180001070`
- `0x180001a80`
- `0x1800022ee`
- `0x180003be0`
- `0x18000446c`
- `0x180004590`
- `0x180011e18`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003fc1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004249`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003fc1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004249`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003fee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000426a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003fee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000426a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000425b`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000425b`
- `ntdll!RtlInitializeSRWLock` at `0x180003cda`
- `ntdll!RtlInitializeSRWLock` at `0x180003cda`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180003d03`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180003d03`
- `ntdll!RtlNtStatusToDosError` at `0x180003e3d`
- `ntdll!RtlNtStatusToDosError` at `0x180003e3d`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180003fde`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180003fde`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003e6a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180003e6a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003d31`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003d31`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180003d7b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180003d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004190`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180003c6b`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180003c6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ea3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ea3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003eb5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003f77`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003eb5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003f77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003f03`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004047`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003f03`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004047`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180003c89`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800040a1`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180003c89`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800040a1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000415c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000415c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ccd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003db2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004224`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004298`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ccd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003db2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004224`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004298`

## string_xrefs

- `0x180003cb1`: `CreateIoCompletionPort For IOCP failed`
- `0x180003da3`: `TerminateThread for OplockCompletionWorker failed`
- `0x180003d59`: `CreateThread for OplockCompletionWorker failed`
- `0x180003e57`: `Failed to open file with reparse point and oplock`
- `0x180003e97`: `ResumeThread for OplockCompletionWorker failed`
- `0x180004014`: `Failed to insert element into OplockCompletionKeyTable`
- `0x180003fa2`: `Failed to allocate completion context`
- `0x180004088`: `Failed to create overlapped event`
- `0x1800042ad`: `CfOpenFileWithOplock`

## pseudocode

```c
__int64 __fastcall CfOpenFileWithOplock(const WCHAR *a1, int a2, _QWORD *a3)
{
  signed int v3; // edi
  __int64 v4; // r15
  unsigned int v5; // esi
  unsigned int v6; // r14d
  unsigned int v7; // r12d
  unsigned __int64 v8; // rbx
  HANDLE IoCompletionPort; // r13
  signed int LastError; // eax
  const wchar_t *v11; // rdx
  HANDLE Thread; // r13
  signed int v13; // eax
  signed int v14; // eax
  char v15; // dl
  int v16; // r13d
  unsigned int v17; // eax
  NTSTATUS v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  HANDLE ProcessHeap; // rax
  HANDLE EventW; // rax
  signed int v23; // eax
  HANDLE v24; // rax
  char *v25; // rax
  PVOID inserted; // rbx
  _QWORD **v27; // rbx
  HANDLE **v28; // r8
  signed int v29; // eax
  signed int v30; // eax
  __int64 v31; // rcx
  signed int v32; // eax
  BOOLEAN v33; // bl
  _QWORD **v34; // rax
  _QWORD *v35; // rcx
  const WCHAR *v36; // rax
  int v37; // ecx
  HANDLE v38; // rax
  _QWORD **Buffer; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 NewElement[8]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v46; // [rsp+80h] [rbp-80h] BYREF
  const WCHAR *v47; // [rsp+88h] [rbp-78h] BYREF
  DWORD BytesReturned; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v50; // [rsp+A0h] [rbp-60h] BYREF
  char v51[8]; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v52; // [rsp+B8h] [rbp-48h]
  const WCHAR *v53; // [rsp+C0h] [rbp-40h]
  unsigned int v54; // [rsp+C8h] [rbp-38h]
  int v55; // [rsp+CCh] [rbp-34h]
  int v56; // [rsp+D0h] [rbp-30h]
  unsigned int v57; // [rsp+D4h] [rbp-2Ch]
  char *v58; // [rsp+D8h] [rbp-28h]
  _QWORD *v59; // [rsp+E0h] [rbp-20h]
  __int64 v60; // [rsp+E8h] [rbp-18h]
  int v61; // [rsp+F0h] [rbp-10h]
  __int64 v62; // [rsp+F8h] [rbp-8h]
  char *v63; // [rsp+100h] [rbp+0h]
  __int64 InBuffer; // [rsp+110h] [rbp+10h] BYREF
  int v65; // [rsp+118h] [rbp+18h]
  char v66[32]; // [rsp+120h] [rbp+20h] BYREF
  const wchar_t *v67; // [rsp+140h] [rbp+40h]
  __int64 v68; // [rsp+148h] [rbp+48h]
  unsigned __int64 *v69; // [rsp+150h] [rbp+50h]
  __int64 v70; // [rsp+158h] [rbp+58h]
  _QWORD **v71; // [rsp+160h] [rbp+60h]
  __int64 v72; // [rsp+168h] [rbp+68h]
  const WCHAR *v73; // [rsp+170h] [rbp+70h]
  int v74; // [rsp+178h] [rbp+78h]
  int v75; // [rsp+17Ch] [rbp+7Ch]
  const WCHAR **v76; // [rsp+180h] [rbp+80h]
  __int64 v77; // [rsp+188h] [rbp+88h]
  _QWORD *v78; // [rsp+190h] [rbp+90h]
  __int64 v79; // [rsp+198h] [rbp+98h]
  __int64 *v80; // [rsp+1A0h] [rbp+A0h]
  __int64 v81; // [rsp+1A8h] [rbp+A8h]
  __int64 *v82; // [rsp+1B0h] [rbp+B0h]
  __int64 v83; // [rsp+1B8h] [rbp+B8h]

  v3 = 0;
  v46 = a3;
  v4 = -1;
  LODWORD(v44) = a2;
  v47 = a1;
  hObject = (HANDLE)-1LL;
  LODWORD(v43) = 129;
  InBuffer = 0;
  v5 = 0x200000;
  v65 = 0;
  v6 = 7;
  Buffer = 0;
  v7 = 1;
  NewElement[0] = 0;
  v8 = 0;
  BytesReturned = 0;
  UnbiasedTime = 0;
  memset_0(v51, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  if ( !CompletionPort )
  {
    IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
    if ( !IoCompletionPort )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v3 <= -1 )
    {
      v11 = L"CreateIoCompletionPort For IOCP failed";
      goto LABEL_80;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&CompletionPort, (signed __int64)IoCompletionPort, 0) )
      CloseHandle(IoCompletionPort);
    RtlInitializeSRWLock(&qword_180028C88);
    v3 = 0;
    RtlInitializeGenericTableAvl(
      &stru_180028C20,
      CfpOplockCompletionKeyTableCompare,
      CfpOplockCompletionKeyTableAllocate,
      CfpSyncRootTableFree,
      0);
  }
  if ( !hThread )
  {
    Thread = CreateThread(0, 0, CfpOplockCompletionWorker, 0, 4u, 0);
    if ( !Thread )
    {
      v13 = GetLastError();
      v3 = v13;
      if ( v13 > 0 )
        v3 = (unsigned __int16)v13 | 0x80070000;
    }
    if ( v3 <= -1 )
    {
      v11 = L"CreateThread for OplockCompletionWorker failed";
      goto LABEL_80;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hThread, (signed __int64)Thread, 0) )
    {
      if ( TerminateThread(Thread, 0) )
      {
        v3 = 0;
      }
      else
      {
        v14 = GetLastError();
        v3 = v14;
        if ( v14 > 0 )
          v3 = (unsigned __int16)v14 | 0x80070000;
      }
      if ( v3 <= -1 )
      {
        v11 = L"TerminateThread for OplockCompletionWorker failed";
        goto LABEL_80;
      }
      CloseHandle(Thread);
    }
    else
    {
      if ( ResumeThread(hThread) == -1 )
      {
        v20 = GetLastError();
        v3 = v20;
        if ( v20 > 0 )
          v3 = (unsigned __int16)v20 | 0x80070000;
      }
      else
      {
        v3 = 0;
      }
      if ( v3 <= -1 )
      {
        v11 = L"ResumeThread for OplockCompletionWorker failed";
        goto LABEL_80;
      }
    }
  }
  v15 = v44;
  v5 = ~((_DWORD)v44 << 13) & 0x10000 | 0x200000;
  LODWORD(v44) = v44 & 1;
  v16 = 2 * (unsigned __int8)v44 + 1;
  v6 = (_BYTE)v44 == 0 ? 7 : 0;
  v17 = (v15 & 2) != 0 ? 387 : 129;
  if ( (v15 & 4) != 0 )
    v17 |= 0x10000u;
  LODWORD(v43) = v17;
  v53 = v47;
  v54 = v17;
  v55 = (_BYTE)v44 == 0 ? 7 : 0;
  v57 = v5;
  v56 = 2 * (unsigned __int8)v44 + 1;
  v18 = CfpCreateFile(v47, &hObject, v17, v6);
  v19 = RtlNtStatusToDosError(v18);
  v3 = v19;
  if ( v19 > 0 )
    v3 = (unsigned __int16)v19 | 0x80070000;
  if ( v3 > -1 )
  {
    ProcessHeap = GetProcessHeap();
    v8 = (unsigned __int64)HeapAlloc(ProcessHeap, 8u, 0x20u);
    v42 = (_QWORD *)v8;
    v3 = v8 == 0 ? 8 : 0;
    if ( !v8 )
      v3 |= 0x80070000;
    if ( v3 > -1 )
    {
      v50 = (unsigned __int64)hObject;
      v59 = (_QWORD *)v8;
      EventW = CreateEventW(0, 1, 0, 0);
      *(_QWORD *)(v8 + 8) = EventW;
      if ( EventW )
      {
        v3 = 0;
      }
      else
      {
        v23 = GetLastError();
        v3 = v23;
        if ( v23 > 0 )
          v3 = (unsigned __int16)v23 | 0x80070000;
      }
      if ( v3 >= 0 )
      {
        *(_QWORD *)v8 = v50;
        *(_BYTE *)(v8 + 28) = v44;
        *(_QWORD *)(v8 + 16) = 1;
        *(_DWORD *)(v8 + 24) = 1;
      }
      if ( v3 > -1 )
      {
        hObject = (HANDLE)-1LL;
        if ( (v5 & 0x10000) == 0 )
        {
          v11 = 0;
          *v46 = v8 | 1;
          v8 = 0;
          goto LABEL_79;
        }
        v24 = GetProcessHeap();
        v25 = (char *)HeapAlloc(v24, 8u, 0x40u);
        Buffer = (_QWORD **)v25;
        v3 = v25 == 0 ? 8 : 0;
        if ( !v25 )
          v3 |= 0x80070000;
        if ( v3 > -1 )
        {
          v63 = v25;
          v58 = v25 + 8;
          RtlAcquireSRWLockExclusive(&qword_180028C88);
          inserted = RtlInsertElementGenericTableAvl(&stru_180028C20, &Buffer, 8u, NewElement);
          RtlReleaseSRWLockExclusive(&qword_180028C88);
          v3 = inserted == 0 ? 8 : 0;
          if ( !inserted )
            v3 |= 0x80070000;
          if ( v3 > -1 )
          {
            *Buffer = v42;
            v27 = Buffer;
            v42 = 0;
            v27[4] = CreateEventW(0, 1, 0, 0);
            v28 = (HANDLE **)Buffer;
            if ( Buffer[4] )
            {
              v3 = 0;
            }
            else
            {
              v29 = GetLastError();
              v28 = (HANDLE **)Buffer;
              v3 = v29;
              if ( v29 > 0 )
                v3 = (unsigned __int16)v29 | 0x80070000;
            }
            if ( v3 > -1 )
            {
              if ( CreateIoCompletionPort(**v28, CompletionPort, (ULONG_PTR)v28, 0) )
              {
                v3 = 0;
              }
              else
              {
                v30 = GetLastError();
                v3 = v30;
                if ( v30 > 0 )
                  v3 = (unsigned __int16)v30 | 0x80070000;
              }
              if ( v3 > -1 )
              {
                LODWORD(InBuffer) = 786433;
                HIDWORD(InBuffer) = v16;
                v65 = 1;
                *((_DWORD *)*Buffer + 6) = 2;
                v59 = *Buffer;
                v62 = **Buffer;
                v61 = *((_DWORD *)*Buffer + 6);
                v60 = (*Buffer)[2];
                if ( DeviceIoControl(
                       (HANDLE)**Buffer,
                       0x90240u,
                       &InBuffer,
                       0xCu,
                       Buffer + 5,
                       0x18u,
                       &BytesReturned,
                       (LPOVERLAPPED)(Buffer + 1)) )
                {
                  v3 = -2147467259;
                  v11 = L"DeviceIoControl returned an unexpected success";
                }
                else
                {
                  if ( GetLastError() == 997 )
                  {
                    v11 = 0;
                    v8 = 0;
                    v31 = (unsigned __int64)*Buffer | 1;
                    Buffer = 0;
                    *v46 = v31;
                    goto LABEL_79;
                  }
                  v32 = GetLastError();
                  v3 = v32;
                  if ( v32 > 0 )
                    v3 = (unsigned __int16)v32 | 0x80070000;
                  v11 = L"DeviceIoControl failed to request oplock";
                }
                *((_DWORD *)*Buffer + 6) = 1;
                v61 = *((_DWORD *)*Buffer + 6);
              }
              else
              {
                v11 = L"Failed to associate handle with IOCP";
              }
            }
            else
            {
              v11 = L"Failed to create overlapped event";
            }
          }
          else
          {
            v11 = L"Failed to insert element into OplockCompletionKeyTable";
          }
          v8 = (unsigned __int64)v42;
        }
        else
        {
          v11 = L"Failed to allocate completion context";
        }
      }
      else
      {
        v11 = L"Failed to initialize protected handle structure";
      }
    }
    else
    {
      v11 = L"Failed to allocate protected handle structure";
    }
  }
  else
  {
    v11 = L"Failed to open file with reparse point and oplock";
  }
LABEL_79:
  v7 = v16;
LABEL_80:
  v52 = v11;
  TlmLogApiReliability(34, 0, 0, 0, 0, UnbiasedTime, (__int64)v51, v3);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v8 )
    CfpDrainProtectedHandle(v8);
  if ( Buffer )
  {
    RtlAcquireSRWLockExclusive(&qword_180028C88);
    v33 = RtlDeleteElementGenericTableAvl(&stru_180028C20, &Buffer);
    RtlReleaseSRWLockExclusive(&qword_180028C88);
    if ( v33 )
    {
      v34 = Buffer;
      if ( *Buffer )
      {
        CfpDrainProtectedHandle(*Buffer);
        v34 = Buffer;
      }
      v35 = v34[4];
      if ( v35 )
        CloseHandle(v35);
      if ( (unsigned int)dword_1800281A0 > 4 )
      {
        v68 = 42;
        v67 = L"CfOpenFileWithOplock";
        v50 = UnbiasedTime;
        v69 = &v50;
        v46 = Buffer;
        v71 = &v46;
        v36 = v47;
        v70 = 8;
        v72 = 8;
        if ( v47 )
        {
          do
            ++v4;
          while ( v47[v4] );
          v37 = 2 * v4 + 2;
        }
        else
        {
          v36 = &SourceString;
          v37 = 2;
        }
        v73 = v36;
        v47 = (const WCHAR *)(unsigned int)v43;
        v74 = v37;
        v76 = &v47;
        v42 = (_QWORD *)v6;
        v78 = &v42;
        v44 = v7;
        v80 = &v44;
        v43 = v5;
        v82 = &v43;
        v75 = 0;
        v77 = 8;
        v79 = 8;
        v81 = 8;
        v83 = 8;
        tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_180021771, 0, 0, 10, v66);
      }
      v38 = GetProcessHeap();
      HeapFree(v38, 0, Buffer);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003be0  mov     [rsp-8+arg_8], rbx
0x180003be5  push    rbp
0x180003be6  push    rsi
0x180003be7  push    rdi
0x180003be8  push    r12
0x180003bea  push    r13
0x180003bec  push    r14
0x180003bee  push    r15
0x180003bf0  lea     rbp, [rsp-0D0h]
0x180003bf8  sub     rsp, 1D0h
0x180003bff  mov     rax, cs:__security_cookie
0x180003c06  xor     rax, rsp
0x180003c09  mov     [rbp+100h+var_40], rax
0x180003c10  xor     edi, edi
0x180003c12  mov     [rbp+100h+var_180], r8
0x180003c16  or      r15, 0FFFFFFFFFFFFFFFFh
0x180003c1a  mov     dword ptr [rsp+200h+var_190], edx
0x180003c1e  xor     eax, eax
0x180003c20  mov     [rbp+100h+var_178], rcx
0x180003c24  xor     edx, edx; Val
0x180003c26  mov     [rsp+200h+hObject], r15
0x180003c2b  lea     rcx, [rbp+100h+var_150]; void *
0x180003c2f  mov     dword ptr [rsp+200h+var_198], 81h
0x180003c37  lea     r8d, [r15+59h]; Size
0x180003c3b  mov     [rbp+100h+InBuffer], rax
0x180003c3f  mov     esi, 200000h
0x180003c44  mov     [rbp+100h+var_E8], eax
0x180003c47  lea     r14d, [r15+8]
0x180003c4b  mov     [rsp+200h+Buffer], rdi
0x180003c50  lea     r12d, [r15+2]
0x180003c54  mov     [rsp+200h+NewElement], dil
0x180003c59  mov     ebx, edi
0x180003c5b  mov     [rbp+100h+BytesReturned], edi
0x180003c5e  mov     [rbp+100h+UnbiasedTime], rdi
0x180003c62  call    memset_0
0x180003c67  lea     rcx, [rbp+100h+UnbiasedTime]; UnbiasedTime
0x180003c6b  call    cs:__imp_QueryUnbiasedInterruptTime
0x180003c71  cmp     cs:CompletionPort, rdi
0x180003c78  jnz     loc_180003D09
0x180003c7e  xor     r9d, r9d; NumberOfConcurrentThreads
0x180003c81  xor     r8d, r8d; CompletionKey
0x180003c84  xor     edx, edx; ExistingCompletionPort
0x180003c86  mov     rcx, r15; FileHandle
0x180003c89  call    cs:__imp_CreateIoCompletionPort
0x180003c8f  mov     r13, rax
0x180003c92  test    rax, rax
0x180003c95  jnz     short loc_180003CAC
0x180003c97  call    cs:__imp_GetLastError
0x180003c9d  mov     edi, eax
0x180003c9f  test    eax, eax
0x180003ca1  jle     short loc_180003CAC
0x180003ca3  movzx   edi, ax
0x180003ca6  or      edi, 80070000h
0x180003cac  cmp     edi, r15d
0x180003caf  jg      short loc_180003CBD
0x180003cb1  lea     rdx, aCreateiocomple; "CreateIoCompletionPort For IOCP failed"
0x180003cb8  jmp     loc_1800041E6
0x180003cbd  xor     eax, eax
0x180003cbf  lock cmpxchg cs:CompletionPort, r13
0x180003cc8  jz      short loc_180003CD3
0x180003cca  mov     rcx, r13; hObject
0x180003ccd  call    cs:__imp_CloseHandle
0x180003cd3  lea     rcx, qword_180028C88
0x180003cda  call    cs:__imp_RtlInitializeSRWLock
0x180003ce0  xor     edi, edi
0x180003ce2  lea     r9, CfpSyncRootTableFree; FreeRoutine
0x180003ce9  lea     r8, CfpOplockCompletionKeyTableAllocate; AllocateRoutine
0x180003cf0  mov     [rsp+200h+TableContext], rdi; TableContext
0x180003cf5  lea     rdx, CfpOplockCompletionKeyTableCompare; CompareRoutine
0x180003cfc  lea     rcx, stru_180028C20; Table
0x180003d03  call    cs:__imp_RtlInitializeGenericTableAvl
0x180003d09  cmp     cs:hThread, rdi
0x180003d10  jnz     loc_180003DB8
0x180003d16  mov     [rsp+200h+lpThreadId], rdi; lpThreadId
0x180003d1b  lea     r8, CfpOplockCompletionWorker; lpStartAddress
0x180003d22  xor     r9d, r9d; lpParameter
0x180003d25  mov     dword ptr [rsp+200h+TableContext], 4; dwCreationFlags
0x180003d2d  xor     edx, edx; dwStackSize
0x180003d2f  xor     ecx, ecx; lpThreadAttributes
0x180003d31  call    cs:__imp_CreateThread
0x180003d37  mov     r13, rax
0x180003d3a  test    rax, rax
0x180003d3d  jnz     short loc_180003D54
0x180003d3f  call    cs:__imp_GetLastError
0x180003d45  mov     edi, eax
0x180003d47  test    eax, eax
0x180003d49  jle     short loc_180003D54
0x180003d4b  movzx   edi, ax
0x180003d4e  or      edi, 80070000h
0x180003d54  cmp     edi, r15d
0x180003d57  jg      short loc_180003D65
0x180003d59  lea     rdx, aCreatethreadFo; "CreateThread for OplockCompletionWorker"...
0x180003d60  jmp     loc_1800041E6
0x180003d65  xor     eax, eax
0x180003d67  lock cmpxchg cs:hThread, r13
0x180003d70  jz      loc_180003E63
0x180003d76  xor     edx, edx; dwExitCode
0x180003d78  mov     rcx, r13; hThread
0x180003d7b  call    cs:__imp_TerminateThread
0x180003d81  test    eax, eax
0x180003d83  jz      short loc_180003D89
0x180003d85  xor     edi, edi
0x180003d87  jmp     short loc_180003D9E
0x180003d89  call    cs:__imp_GetLastError
0x180003d8f  mov     edi, eax
0x180003d91  test    eax, eax
0x180003d93  jle     short loc_180003D9E
0x180003d95  movzx   edi, ax
0x180003d98  or      edi, 80070000h
0x180003d9e  cmp     edi, r15d
0x180003da1  jg      short loc_180003DAF
0x180003da3  lea     rdx, aTerminatethrea; "TerminateThread for OplockCompletionWor"...
0x180003daa  jmp     loc_1800041E6
0x180003daf  mov     rcx, r13; hObject
0x180003db2  call    cs:__imp_CloseHandle
0x180003db8  mov     edx, dword ptr [rsp+200h+var_190]
0x180003dbc  mov     r8d, 10000h
0x180003dc2  mov     eax, edx
0x180003dc4  shl     eax, 0Dh
0x180003dc7  not     eax
0x180003dc9  and     eax, r8d
0x180003dcc  or      esi, eax
0x180003dce  mov     eax, edx
0x180003dd0  and     eax, r12d
0x180003dd3  mov     dword ptr [rsp+200h+var_190], eax
0x180003dd7  movzx   eax, al
0x180003dda  lea     r13d, ds:1[rax*2]
0x180003de2  neg     al
0x180003de4  sbb     eax, eax
0x180003de6  not     eax
0x180003de8  and     r14d, eax
0x180003deb  mov     eax, edx
0x180003ded  and     al, 2
0x180003def  neg     al
0x180003df1  mov     eax, 81h
0x180003df6  sbb     ecx, ecx
0x180003df8  and     ecx, 102h
0x180003dfe  add     eax, ecx
0x180003e00  test    dl, 4
0x180003e03  jz      short loc_180003E08
0x180003e05  or      eax, r8d
0x180003e08  mov     rcx, [rbp+100h+var_178]
0x180003e0c  lea     rdx, [rsp+200h+hObject]
0x180003e11  mov     [rsp+200h+lpOverlapped], rdx
0x180003e16  mov     r9d, r14d
0x180003e19  mov     r8d, eax
0x180003e1c  mov     dword ptr [rsp+200h+lpThreadId], esi
0x180003e20  mov     dword ptr [rsp+200h+var_198], eax
0x180003e24  mov     [rbp+100h+var_140], rcx
0x180003e28  mov     [rbp+100h+var_138], eax
0x180003e2b  mov     [rbp+100h+var_134], r14d
0x180003e2f  mov     [rbp+100h+var_12C], esi
0x180003e32  mov     [rbp+100h+var_130], r13d
0x180003e36  call    CfpCreateFile
0x180003e3b  mov     ecx, eax; Status
0x180003e3d  call    cs:__imp_RtlNtStatusToDosError
0x180003e43  mov     edi, eax
0x180003e45  test    eax, eax
0x180003e47  jle     short loc_180003E52
0x180003e49  movzx   edi, ax
0x180003e4c  or      edi, 80070000h
0x180003e52  cmp     edi, r15d
0x180003e55  jg      short loc_180003EA3
0x180003e57  lea     rdx, aFailedToOpenFi; "Failed to open file with reparse point "...
0x180003e5e  jmp     loc_1800041E3
0x180003e63  mov     rcx, cs:hThread; hThread
0x180003e6a  call    cs:__imp_ResumeThread
0x180003e70  cmp     eax, 0FFFFFFFFh
0x180003e73  jz      short loc_180003E79
0x180003e75  xor     edi, edi
0x180003e77  jmp     short loc_180003E8E
0x180003e79  call    cs:__imp_GetLastError
0x180003e7f  mov     edi, eax
0x180003e81  test    eax, eax
0x180003e83  jle     short loc_180003E8E
0x180003e85  movzx   edi, ax
0x180003e88  or      edi, 80070000h
0x180003e8e  cmp     edi, r15d
0x180003e91  jg      loc_180003DB8
0x180003e97  lea     rdx, aResumethreadFo; "ResumeThread for OplockCompletionWorker"...
0x180003e9e  jmp     loc_1800041E6
0x180003ea3  call    cs:__imp_GetProcessHeap
0x180003ea9  mov     edx, 8; dwFlags
0x180003eae  mov     rcx, rax; hHeap
0x180003eb1  lea     r8d, [rdx+18h]; dwBytes
0x180003eb5  call    cs:__imp_HeapAlloc
0x180003ebb  mov     rbx, rax
0x180003ebe  mov     [rsp+200h+var_1A0], rax
0x180003ec3  neg     rax
0x180003ec6  sbb     edi, edi
0x180003ec8  not     edi
0x180003eca  and     edi, 8
0x180003ecd  mov     eax, edi
0x180003ecf  or      eax, 80070000h
0x180003ed4  test    rbx, rbx
0x180003ed7  cmovz   edi, eax
0x180003eda  cmp     edi, r15d
0x180003edd  jg      short loc_180003EEB
0x180003edf  lea     rdx, aFailedToAlloca_0; "Failed to allocate protected handle str"...
0x180003ee6  jmp     loc_1800041E3
0x180003eeb  mov     rax, [rsp+200h+hObject]
0x180003ef0  xor     r9d, r9d; lpName
0x180003ef3  xor     r8d, r8d; bInitialState
0x180003ef6  mov     [rbp+100h+var_160], rax
0x180003efa  mov     edx, r12d; bManualReset
0x180003efd  mov     [rbp+100h+var_120], rbx
0x180003f01  xor     ecx, ecx; lpEventAttributes
0x180003f03  call    cs:__imp_CreateEventW
0x180003f09  mov     [rbx+8], rax
0x180003f0d  test    rax, rax
0x180003f10  jz      short loc_180003F16
0x180003f12  xor     edi, edi
0x180003f14  jmp     short loc_180003F2B
0x180003f16  call    cs:__imp_GetLastError
0x180003f1c  mov     edi, eax
0x180003f1e  test    eax, eax
0x180003f20  jle     short loc_180003F2B
0x180003f22  movzx   edi, ax
0x180003f25  or      edi, 80070000h
0x180003f2b  test    edi, edi
0x180003f2d  js      short loc_180003F45
0x180003f2f  mov     rax, [rbp+100h+var_160]
0x180003f33  mov     [rbx], rax
0x180003f36  mov     eax, dword ptr [rsp+200h+var_190]
0x180003f3a  mov     [rbx+1Ch], al
0x180003f3d  mov     [rbx+10h], r12
0x180003f41  mov     [rbx+18h], r12d
0x180003f45  cmp     edi, r15d
0x180003f48  jg      short loc_180003F56
0x180003f4a  lea     rdx, aFailedToInitia; "Failed to initialize protected handle s"...
0x180003f51  jmp     loc_1800041E3
0x180003f56  mov     [rsp+200h+hObject], r15
0x180003f5b  bt      esi, 10h
0x180003f5f  jnb     loc_1800041D5
0x180003f65  call    cs:__imp_GetProcessHeap
0x180003f6b  mov     edx, 8; dwFlags
0x180003f70  mov     rcx, rax; hHeap
0x180003f73  lea     r8d, [rdx+38h]; dwBytes
0x180003f77  call    cs:__imp_HeapAlloc
0x180003f7d  mov     rcx, rax
0x180003f80  mov     [rsp+200h+Buffer], rax
0x180003f85  neg     rcx
0x180003f88  sbb     edi, edi
0x180003f8a  not     edi
0x180003f8c  and     edi, 8
0x180003f8f  mov     ecx, edi
0x180003f91  or      ecx, 80070000h
0x180003f97  test    rax, rax
0x180003f9a  cmovz   edi, ecx
0x180003f9d  cmp     edi, r15d
0x180003fa0  jg      short loc_180003FAE
0x180003fa2  lea     rdx, aFailedToAlloca; "Failed to allocate completion context"
0x180003fa9  jmp     loc_1800041E3
0x180003fae  mov     [rbp+100h+var_100], rax
0x180003fb2  lea     rcx, qword_180028C88
0x180003fb9  add     rax, 8
0x180003fbd  mov     [rbp+100h+var_128], rax
0x180003fc1  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180003fc7  lea     r9, [rsp+200h+NewElement]; NewElement
0x180003fcc  mov     r8d, 8; BufferSize
0x180003fd2  lea     rdx, [rsp+200h+Buffer]; Buffer
0x180003fd7  lea     rcx, stru_180028C20; Table
0x180003fde  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180003fe4  lea     rcx, qword_180028C88
0x180003feb  mov     rbx, rax
0x180003fee  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180003ff4  mov     rcx, rbx
0x180003ff7  neg     rcx
0x180003ffa  sbb     edi, edi
0x180003ffc  not     edi
0x180003ffe  and     edi, 8
0x180004001  mov     ecx, edi
0x180004003  or      ecx, 80070000h
0x180004009  test    rbx, rbx
0x18000400c  cmovz   edi, ecx
0x18000400f  cmp     edi, r15d
0x180004012  jg      short loc_180004025
0x180004014  lea     rdx, aFailedToInsert; "Failed to insert element into OplockCom"...
0x18000401b  mov     rbx, [rsp+200h+var_1A0]
0x180004020  jmp     loc_1800041E3
0x180004025  mov     rcx, [rsp+200h+var_1A0]
0x18000402a  xor     r9d, r9d; lpName
0x18000402d  mov     rax, [rsp+200h+Buffer]
0x180004032  xor     r8d, r8d; bInitialState
0x180004035  mov     edx, r12d; bManualReset
0x180004038  mov     [rax], rcx
0x18000403b  xor     ecx, ecx; lpEventAttributes
0x18000403d  mov     rbx, [rsp+200h+Buffer]
0x180004042  mov     [rsp+200h+var_1A0], rcx
0x180004047  call    cs:__imp_CreateEventW
0x18000404d  mov     [rbx+20h], rax
0x180004051  mov     r8, [rsp+200h+Buffer]
0x180004056  cmp     qword ptr [r8+20h], 0
0x18000405b  jz      short loc_180004061
0x18000405d  xor     edi, edi
0x18000405f  jmp     short loc_180004072
0x180004061  call    cs:__imp_GetLastError
0x180004067  mov     r8, [rsp+200h+Buffer]; CompletionKey
0x18000406c  mov     edi, eax
0x18000406e  test    eax, eax
  ... truncated ...
```
