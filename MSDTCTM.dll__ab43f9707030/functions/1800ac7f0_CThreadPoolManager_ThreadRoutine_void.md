# CThreadPoolManager::ThreadRoutine(void *)

- ea: `0x1800ac7f0`
- end: `0x1800aca29`
- name: `?ThreadRoutine@CThreadPoolManager@@CAKPEAX@Z`
- size: `569`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800063b0`
- `0x1800ac7f0`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac865`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac9d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac9d2`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800ac982`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800ac982`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800ac85a`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800ac85a`

## string_xrefs

- `0x1800ac823`: `com\complus\dtc\dtc\tipgw\commgr\src\threadpoolmanager.cpp`
- `0x1800ac994`: `Closing TIP thread pool completion port`
- `0x1800ac9a9`: `CThreadPoolManager::CloseCompletionPort`
- `0x1800ac9ea`: `Completion port closed unexpectedly`
- `0x1800ac870`: `Get queued completion status call failed.`
- `0x1800ac814`: `CThreadPoolManager::ThreadRoutine`
- `0x1800ac8fe`: `Completion event: Key=%d, bytes transferred=%d, overlap=%p`
- `0x1800ac8af`: `I/O completion status returned null overlap.`

## pseudocode

```c
__int64 __fastcall CThreadPoolManager::ThreadRoutine(PVOID Parameter)
{
  int v1; // ebx
  bool v2; // zf
  DWORD v3; // edx
  __int64 v5; // [rsp+40h] [rbp-20h]
  unsigned __int64 CompletionKey; // [rsp+50h] [rbp-10h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+98h] [rbp+38h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+A8h] [rbp+48h] BYREF

  v1 = 1;
  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  Overlapped = 0;
  while ( v1 )
  {
    if ( !CThreadPoolManager::m_hCompletionPort )
    {
      TraceStringInline(
        10,
        1,
        L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\threadpoolmanager.cpp",
        277,
        L"CThreadPoolManager::ThreadRoutine",
        0,
        L"Completion port closed unexpectedly");
      return 0;
    }
    if ( !GetQueuedCompletionStatus(
            CThreadPoolManager::m_hCompletionPort,
            &NumberOfBytesTransferred,
            &CompletionKey,
            &Overlapped,
            0xFFFFFFFF)
      && GetLastError() != 64 )
    {
      TraceStringInline(
        10,
        1,
        L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\threadpoolmanager.cpp",
        305,
        L"CThreadPoolManager::ThreadRoutine",
        0,
        L"Get queued completion status call failed.");
    }
    if ( Overlapped )
    {
      LODWORD(v5) = NumberOfBytesTransferred;
      TraceStringInline(
        10,
        4,
        L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\threadpoolmanager.cpp",
        320,
        L"CThreadPoolManager::ThreadRoutine",
        0,
        L"Completion event: Key=%d, bytes transferred=%d, overlap=%p",
        CompletionKey,
        v5,
        Overlapped);
      if ( CompletionKey == 1 || CompletionKey == 2 )
      {
LABEL_13:
        Overlapped[1].Offset = NumberOfBytesTransferred;
        (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)Overlapped[1].InternalHigh + 24LL))(Overlapped[1].InternalHigh);
      }
      else if ( CompletionKey == 3 )
      {
        v2 = NumberOfBytesTransferred == 1;
        v3 = --NumberOfBytesTransferred;
        if ( v2 )
        {
          if ( CThreadPoolManager::m_hCompletionPort )
          {
            TraceStringInline(
              10,
              4,
              L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\threadpoolmanager.cpp",
              168,
              L"CThreadPoolManager::CloseCompletionPort",
              0,
              L"Closing TIP thread pool completion port");
            CloseHandle(CThreadPoolManager::m_hCompletionPort);
            CThreadPoolManager::m_hCompletionPort = 0;
          }
        }
        else
        {
          PostQueuedCompletionStatus(CThreadPoolManager::m_hCompletionPort, v3, 3u, Overlapped);
        }
        v1 = 0;
      }
      else if ( CompletionKey - 4 <= 1 )
      {
        goto LABEL_13;
      }
    }
    else
    {
      TraceStringInline(
        10,
        1,
        L"com\\complus\\dtc\\dtc\\tipgw\\commgr\\src\\threadpoolmanager.cpp",
        312,
        L"CThreadPoolManager::ThreadRoutine",
        0,
        L"I/O completion status returned null overlap.");
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800ac7f0  push    rbp
0x1800ac7f2  push    rbx
0x1800ac7f3  push    r12
0x1800ac7f5  push    r14
0x1800ac7f7  push    r15
0x1800ac7f9  mov     rbp, rsp
0x1800ac7fc  sub     rsp, 60h
0x1800ac800  mov     ebx, 1
0x1800ac805  mov     [rbp+NumberOfBytesTransferred], 0
0x1800ac80c  mov     [rbp+CompletionKey], 0
0x1800ac814  lea     r12, aCthreadpoolman_1; "CThreadPoolManager::ThreadRoutine"
0x1800ac81b  mov     [rbp+Overlapped], 0
0x1800ac823  lea     r14, aComComplusDtcD_70; "com\\complus\\dtc\\dtc\\tipgw\\commgr\\"...
0x1800ac82a  lea     r15d, [rbx+9]
0x1800ac82e  test    ebx, ebx
0x1800ac830  jz      loc_1800ACA1A
0x1800ac836  mov     rcx, cs:?m_hCompletionPort@CThreadPoolManager@@0PEAXEA; CompletionPort
0x1800ac83d  test    rcx, rcx
0x1800ac840  jz      loc_1800AC9EA
0x1800ac846  lea     r9, [rbp+Overlapped]; lpOverlapped
0x1800ac84a  mov     [rsp+60h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1800ac852  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x1800ac856  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800ac85a  call    cs:__imp_GetQueuedCompletionStatus
0x1800ac860  cmp     eax, 1
0x1800ac863  jz      short loc_1800AC8A0
0x1800ac865  call    cs:__imp_GetLastError
0x1800ac86b  cmp     eax, 40h ; '@'
0x1800ac86e  jz      short loc_1800AC8A0
0x1800ac870  lea     rax, aGetQueuedCompl; "Get queued completion status call faile"...
0x1800ac877  mov     r9d, 131h
0x1800ac87d  mov     [rsp+60h+var_30], rax
0x1800ac882  mov     r8, r14
0x1800ac885  mov     [rsp+60h+var_38], 0
0x1800ac88e  mov     edx, 1
0x1800ac893  mov     ecx, r15d
0x1800ac896  mov     qword ptr [rsp+60h+dwMilliseconds], r12
0x1800ac89b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800ac8a0  mov     rax, [rbp+Overlapped]
0x1800ac8a4  mov     r8, r14
0x1800ac8a7  mov     ecx, r15d
0x1800ac8aa  test    rax, rax
0x1800ac8ad  jnz     short loc_1800AC8DE
0x1800ac8af  lea     rax, aIOCompletionSt; "I/O completion status returned null ove"...
0x1800ac8b6  mov     r9d, 138h
0x1800ac8bc  mov     [rsp+60h+var_30], rax
0x1800ac8c1  mov     edx, 1
0x1800ac8c6  mov     [rsp+60h+var_38], 0
0x1800ac8cf  mov     qword ptr [rsp+60h+dwMilliseconds], r12
0x1800ac8d4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800ac8d9  jmp     loc_1800AC82E
0x1800ac8de  mov     [rsp+60h+var_18], rax
0x1800ac8e3  mov     r9d, 140h
0x1800ac8e9  mov     eax, [rbp+NumberOfBytesTransferred]
0x1800ac8ec  mov     edx, 4
0x1800ac8f1  mov     dword ptr [rsp+60h+var_20], eax
0x1800ac8f5  mov     rax, [rbp+CompletionKey]
0x1800ac8f9  mov     [rsp+60h+var_28], rax
0x1800ac8fe  lea     rax, aCompletionEven; "Completion event: Key=%d, bytes transfe"...
0x1800ac905  mov     [rsp+60h+var_30], rax
0x1800ac90a  mov     [rsp+60h+var_38], 0
0x1800ac913  mov     qword ptr [rsp+60h+dwMilliseconds], r12
0x1800ac918  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800ac91d  mov     rax, [rbp+CompletionKey]
0x1800ac921  sub     rax, 1
0x1800ac925  jz      short loc_1800AC943
0x1800ac927  sub     rax, 1
0x1800ac92b  jz      short loc_1800AC943
0x1800ac92d  sub     rax, 1
0x1800ac931  jz      short loc_1800AC966
0x1800ac933  sub     rax, 1
0x1800ac937  jz      short loc_1800AC943
0x1800ac939  cmp     rax, 1
0x1800ac93d  jnz     loc_1800AC82E
0x1800ac943  mov     rax, [rbp+Overlapped]
0x1800ac947  mov     ecx, [rbp+NumberOfBytesTransferred]
0x1800ac94a  mov     [rax+30h], ecx
0x1800ac94d  mov     rdx, [rbp+Overlapped]
0x1800ac951  mov     rcx, [rdx+28h]
0x1800ac955  mov     rax, [rcx]
0x1800ac958  mov     rax, [rax+18h]
0x1800ac95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac961  jmp     loc_1800AC82E
0x1800ac966  mov     edx, [rbp+NumberOfBytesTransferred]
0x1800ac969  add     edx, 0FFFFFFFFh; dwNumberOfBytesTransferred
0x1800ac96c  mov     [rbp+NumberOfBytesTransferred], edx
0x1800ac96f  jz      short loc_1800AC98A
0x1800ac971  mov     r9, [rbp+Overlapped]; lpOverlapped
0x1800ac975  mov     r8d, 3; dwCompletionKey
0x1800ac97b  mov     rcx, cs:?m_hCompletionPort@CThreadPoolManager@@0PEAXEA; CompletionPort
0x1800ac982  call    cs:__imp_PostQueuedCompletionStatus
0x1800ac988  jmp     short loc_1800AC9E3
0x1800ac98a  cmp     cs:?m_hCompletionPort@CThreadPoolManager@@0PEAXEA, 0; void * CThreadPoolManager::m_hCompletionPort
0x1800ac992  jz      short loc_1800AC9E3
0x1800ac994  lea     rax, aClosingTipThre; "Closing TIP thread pool completion port"
0x1800ac99b  mov     r9d, 0A8h
0x1800ac9a1  mov     [rsp+60h+var_30], rax
0x1800ac9a6  mov     r8, r14
0x1800ac9a9  lea     rax, aCthreadpoolman_5; "CThreadPoolManager::CloseCompletionPort"
0x1800ac9b0  mov     [rsp+60h+var_38], 0
0x1800ac9b9  mov     edx, 4
0x1800ac9be  mov     qword ptr [rsp+60h+dwMilliseconds], rax
0x1800ac9c3  mov     ecx, r15d
0x1800ac9c6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800ac9cb  mov     rcx, cs:?m_hCompletionPort@CThreadPoolManager@@0PEAXEA; hObject
0x1800ac9d2  call    cs:__imp_CloseHandle
0x1800ac9d8  mov     cs:?m_hCompletionPort@CThreadPoolManager@@0PEAXEA, 0; void * CThreadPoolManager::m_hCompletionPort
0x1800ac9e3  xor     ebx, ebx
0x1800ac9e5  jmp     loc_1800AC82E
0x1800ac9ea  lea     rax, aCompletionPort; "Completion port closed unexpectedly"
0x1800ac9f1  mov     r9d, 115h
0x1800ac9f7  mov     [rsp+60h+var_30], rax
0x1800ac9fc  mov     r8, r14
0x1800ac9ff  mov     [rsp+60h+var_38], 0
0x1800aca08  mov     edx, 1
0x1800aca0d  mov     ecx, r15d
0x1800aca10  mov     qword ptr [rsp+60h+dwMilliseconds], r12
0x1800aca15  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800aca1a  xor     eax, eax
0x1800aca1c  add     rsp, 60h
0x1800aca20  pop     r15
0x1800aca22  pop     r14
0x1800aca24  pop     r12
0x1800aca26  pop     rbx
0x1800aca27  pop     rbp
0x1800aca28  retn
```
