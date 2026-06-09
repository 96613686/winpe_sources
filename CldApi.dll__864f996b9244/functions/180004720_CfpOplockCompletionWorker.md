# CfpOplockCompletionWorker

- ea: `0x180004720`
- end: `0x180004a07`
- name: `CfpOplockCompletionWorker`
- size: `743`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800022ee`
- `0x180004590`
- `0x180004720`
- `0x180011e18`
- `0x18001b9b0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800047f2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800047f2`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180004803`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180004803`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000493c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000493c`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180004864`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180004864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004968`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180004792`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180004792`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048cc`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180004778`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180004778`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048b7`

## string_xrefs

- `0x1800047aa`: ` >>>>>>>>>>  Dequeued completionContext from IOCP >>>>>`
- `0x1800048dd`: ` Found CompletionContext in OplockCompletionKeyTable, but not the one we are looking for `
- `0x180004872`: ` >>>>>>>>>>  Freeing CompletionContext from IOCP >>>>>`
- `0x1800049c1`: `OplockCompletionPort HANDLE Closed`
- `0x1800048ee`: `completionContext not found in OplockCompletionKeyTable`
- `0x18000495d`: `GetQueuedCompletionStatus Failed`

## pseudocode

```c
__int64 __fastcall CfpOplockCompletionWorker(PVOID Parameter)
{
  __int64 v1; // rcx
  HANDLE ProcessHeap; // rax
  signed int LastError; // eax
  signed int v4; // eax
  LPOVERLAPPED Overlapped; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int64 CompletionKey; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v8[8]; // [rsp+50h] [rbp-19h] BYREF
  const wchar_t *v9; // [rsp+58h] [rbp-11h]
  const wchar_t *v10; // [rsp+60h] [rbp-9h]
  LPOVERLAPPED v11; // [rsp+68h] [rbp-1h]
  char *v12; // [rsp+70h] [rbp+7h]
  _QWORD *v13; // [rsp+78h] [rbp+Fh]
  __int64 v14; // [rsp+80h] [rbp+17h]
  int v15; // [rsp+88h] [rbp+1Fh]
  __int64 v16; // [rsp+90h] [rbp+27h]
  HANDLE *v17; // [rsp+98h] [rbp+2Fh]
  DWORD NumberOfBytesTransferred; // [rsp+D8h] [rbp+6Fh] BYREF
  HANDLE *Buffer; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+E8h] [rbp+7Fh] BYREF

  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  Buffer = 0;
  Overlapped = 0;
  UnbiasedTime = 0;
  while ( dword_180028BE8 )
  {
    if ( GetQueuedCompletionStatus(CompletionPort, &NumberOfBytesTransferred, &CompletionKey, &Overlapped, 0xFFFFFFFF) )
    {
      Buffer = (HANDLE *)CompletionKey;
      QueryUnbiasedInterruptTime(&UnbiasedTime);
      memset_0(v8, 0, 0x58u);
      v10 = L" >>>>>>>>>>  Dequeued completionContext from IOCP >>>>>";
      v17 = Buffer;
      v11 = Overlapped;
      TlmLogApiReliability(35, 0, 0, 0, 0, UnbiasedTime, (__int64)v8, 0);
      RtlAcquireSRWLockExclusive(&qword_180028C88);
      if ( RtlLookupElementGenericTableAvl(&stru_180028C20, &Buffer) )
      {
        v13 = *Buffer;
        v12 = (char *)(Buffer + 1);
        v16 = *(_QWORD *)*Buffer;
        v15 = *((_DWORD *)*Buffer + 6);
        v14 = *((_QWORD *)*Buffer + 2);
        if ( Overlapped == (LPOVERLAPPED)(Buffer + 1) )
        {
          if ( RtlDeleteElementGenericTableAvl(&stru_180028C20, &Buffer) )
          {
            v10 = L" >>>>>>>>>>  Freeing CompletionContext from IOCP >>>>>";
            TlmLogApiReliability(35, 0, 0, 0, 0, UnbiasedTime, (__int64)v8, 0);
            CfpDrainProtectedHandle(*Buffer);
            CloseHandle(Buffer[4]);
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, Buffer);
          }
          else
          {
            MicrosoftTelemetryAssertTriggeredArgs(v1, 0);
          }
        }
        else
        {
          v10 = L" Found CompletionContext in OplockCompletionKeyTable, but not the one we are looking for ";
          TlmLogApiReliability(35, 0, 0, 0, 0, UnbiasedTime, (__int64)v8, 0);
        }
      }
      else
      {
        v10 = L"completionContext not found in OplockCompletionKeyTable";
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        TlmLogApiReliability(35, 0, 0, 0, 0, UnbiasedTime, (__int64)v8, LastError);
      }
      RtlReleaseSRWLockExclusive(&qword_180028C88);
    }
    else
    {
      if ( GetLastError() == 6 )
      {
        memset_0(v8, 0, 0x58u);
        v9 = L"OplockCompletionPort HANDLE Closed";
        TlmLogApiReliability(35, 0, 0, 0, 0, UnbiasedTime, (__int64)v8, -2147024890);
        return 0;
      }
      memset_0(v8, 0, 0x58u);
      v9 = L"GetQueuedCompletionStatus Failed";
      v4 = GetLastError();
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      TlmLogApiReliability(35, 0, 0, 0, 0, UnbiasedTime, (__int64)v8, v4);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004720  mov     [rsp-8+arg_0], rbx
0x180004725  push    rbp
0x180004726  push    rsi
0x180004727  push    rdi
0x180004728  lea     rbp, [rsp-47h]
0x18000472d  sub     rsp, 0B0h
0x180004734  mov     eax, cs:dword_180028BE8
0x18000473a  xor     ebx, ebx
0x18000473c  mov     [rbp+57h+NumberOfBytesTransferred], ebx
0x18000473f  mov     [rbp+57h+CompletionKey], rbx
0x180004743  mov     [rbp+57h+Buffer], rbx
0x180004747  mov     [rbp+57h+Overlapped], rbx
0x18000474b  mov     [rbp+57h+UnbiasedTime], rbx
0x18000474f  test    eax, eax
0x180004751  jz      loc_1800049F2
0x180004757  lea     esi, [rbx+58h]
0x18000475a  lea     edi, [rbx+23h]
0x18000475d  mov     rcx, cs:CompletionPort; CompletionPort
0x180004764  lea     r9, [rbp+57h+Overlapped]; lpOverlapped
0x180004768  lea     r8, [rbp+57h+CompletionKey]; lpCompletionKey
0x18000476c  mov     [rsp+0C0h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180004774  lea     rdx, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180004778  call    cs:__imp_GetQueuedCompletionStatus
0x18000477e  test    eax, eax
0x180004780  jz      loc_180004944
0x180004786  mov     rax, [rbp+57h+CompletionKey]
0x18000478a  lea     rcx, [rbp+57h+UnbiasedTime]; UnbiasedTime
0x18000478e  mov     [rbp+57h+Buffer], rax
0x180004792  call    cs:__imp_QueryUnbiasedInterruptTime
0x180004798  mov     r8, rsi; Size
0x18000479b  lea     rcx, [rbp+57h+var_70]; void *
0x18000479f  xor     edx, edx; Val
0x1800047a1  call    memset_0
0x1800047a6  mov     [rsp+0C0h+var_88], ebx
0x1800047aa  lea     rax, aDequeuedComple; " >>>>>>>>>>  Dequeued completionContext"...
0x1800047b1  mov     [rbp+57h+var_60], rax
0x1800047b5  mov     ecx, edi
0x1800047b7  mov     rax, [rbp+57h+Buffer]
0x1800047bb  xor     r9d, r9d
0x1800047be  mov     [rbp+57h+var_28], rax
0x1800047c2  xor     r8d, r8d
0x1800047c5  mov     rax, [rbp+57h+Overlapped]
0x1800047c9  xor     edx, edx
0x1800047cb  mov     [rbp+57h+var_58], rax
0x1800047cf  lea     rax, [rbp+57h+var_70]
0x1800047d3  mov     [rsp+0C0h+var_90], rax
0x1800047d8  mov     rax, [rbp+57h+UnbiasedTime]
0x1800047dc  mov     [rsp+0C0h+var_98], rax
0x1800047e1  mov     qword ptr [rsp+0C0h+dwMilliseconds], rbx
0x1800047e6  call    TlmLogApiReliability
0x1800047eb  lea     rcx, qword_180028C88
0x1800047f2  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800047f8  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1800047fc  lea     rcx, stru_180028C20; Table
0x180004803  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180004809  test    rax, rax
0x18000480c  jz      loc_1800048EE
0x180004812  mov     rdx, [rbp+57h+Buffer]
0x180004816  mov     rax, [rdx]
0x180004819  mov     [rbp+57h+var_48], rax
0x18000481d  lea     rax, [rdx+8]
0x180004821  mov     [rbp+57h+var_50], rax
0x180004825  mov     rax, [rdx]
0x180004828  mov     rcx, [rax]
0x18000482b  mov     [rbp+57h+var_30], rcx
0x18000482f  mov     rax, [rdx]
0x180004832  mov     ecx, [rax+18h]
0x180004835  mov     rax, [rbp+57h+Buffer]
0x180004839  mov     [rbp+57h+var_38], ecx
0x18000483c  mov     rcx, [rax]
0x18000483f  mov     rax, [rcx+10h]
0x180004843  mov     [rbp+57h+var_40], rax
0x180004847  mov     rax, [rbp+57h+Buffer]
0x18000484b  add     rax, 8
0x18000484f  cmp     [rbp+57h+Overlapped], rax
0x180004853  jnz     loc_1800048DD
0x180004859  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18000485d  lea     rcx, stru_180028C20; Table
0x180004864  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18000486a  test    al, al
0x18000486c  jz      short loc_1800048D4
0x18000486e  mov     [rsp+0C0h+var_88], ebx
0x180004872  lea     rax, aFreeingComplet; " >>>>>>>>>>  Freeing CompletionContext "...
0x180004879  mov     [rbp+57h+var_60], rax
0x18000487d  mov     ecx, edi
0x18000487f  lea     rax, [rbp+57h+var_70]
0x180004883  xor     r9d, r9d
0x180004886  mov     [rsp+0C0h+var_90], rax
0x18000488b  xor     r8d, r8d
0x18000488e  mov     rax, [rbp+57h+UnbiasedTime]
0x180004892  xor     edx, edx
0x180004894  mov     [rsp+0C0h+var_98], rax
0x180004899  mov     qword ptr [rsp+0C0h+dwMilliseconds], rbx
0x18000489e  call    TlmLogApiReliability
0x1800048a3  mov     rcx, [rbp+57h+Buffer]
0x1800048a7  mov     rcx, [rcx]
0x1800048aa  call    CfpDrainProtectedHandle
0x1800048af  mov     rcx, [rbp+57h+Buffer]
0x1800048b3  mov     rcx, [rcx+20h]; hObject
0x1800048b7  call    cs:__imp_CloseHandle
0x1800048bd  call    cs:__imp_GetProcessHeap
0x1800048c3  mov     r8, [rbp+57h+Buffer]; lpMem
0x1800048c7  xor     edx, edx; dwFlags
0x1800048c9  mov     rcx, rax; hHeap
0x1800048cc  call    cs:__imp_HeapFree
0x1800048d2  jmp     short loc_180004935
0x1800048d4  xor     edx, edx
0x1800048d6  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800048db  jmp     short loc_180004935
0x1800048dd  lea     rax, aFoundCompletio; " Found CompletionContext in OplockCompl"...
0x1800048e4  mov     [rsp+0C0h+var_88], ebx
0x1800048e8  mov     [rbp+57h+var_60], rax
0x1800048ec  jmp     short loc_18000490F
0x1800048ee  lea     rax, aCompletioncont; "completionContext not found in OplockCo"...
0x1800048f5  mov     [rbp+57h+var_60], rax
0x1800048f9  call    cs:__imp_GetLastError
0x1800048ff  test    eax, eax
0x180004901  jle     short loc_18000490B
0x180004903  movzx   eax, ax
0x180004906  or      eax, 80070000h
0x18000490b  mov     [rsp+0C0h+var_88], eax
0x18000490f  lea     rax, [rbp+57h+var_70]
0x180004913  xor     r9d, r9d
0x180004916  mov     [rsp+0C0h+var_90], rax
0x18000491b  xor     r8d, r8d
0x18000491e  mov     rax, [rbp+57h+UnbiasedTime]
0x180004922  xor     edx, edx
0x180004924  mov     [rsp+0C0h+var_98], rax
0x180004929  mov     ecx, edi
0x18000492b  mov     qword ptr [rsp+0C0h+dwMilliseconds], rbx
0x180004930  call    TlmLogApiReliability
0x180004935  lea     rcx, qword_180028C88
0x18000493c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004942  jmp     short loc_1800049A4
0x180004944  call    cs:__imp_GetLastError
0x18000494a  xor     edx, edx; Val
0x18000494c  lea     rcx, [rbp+57h+var_70]; void *
0x180004950  mov     r8, rsi; Size
0x180004953  cmp     eax, 6
0x180004956  jz      short loc_1800049B4
0x180004958  call    memset_0
0x18000495d  lea     rax, aGetqueuedcompl; "GetQueuedCompletionStatus Failed"
0x180004964  mov     [rbp+57h+var_68], rax
0x180004968  call    cs:__imp_GetLastError
0x18000496e  test    eax, eax
0x180004970  jle     short loc_18000497A
0x180004972  movzx   eax, ax
0x180004975  or      eax, 80070000h
0x18000497a  mov     [rsp+0C0h+var_88], eax
0x18000497e  mov     ecx, edi
0x180004980  lea     rax, [rbp+57h+var_70]
0x180004984  xor     r9d, r9d
0x180004987  mov     [rsp+0C0h+var_90], rax
0x18000498c  xor     r8d, r8d
0x18000498f  mov     rax, [rbp+57h+UnbiasedTime]
0x180004993  xor     edx, edx
0x180004995  mov     [rsp+0C0h+var_98], rax
0x18000499a  mov     qword ptr [rsp+0C0h+dwMilliseconds], rbx
0x18000499f  call    TlmLogApiReliability
0x1800049a4  mov     eax, cs:dword_180028BE8
0x1800049aa  test    eax, eax
0x1800049ac  jnz     loc_18000475D
0x1800049b2  jmp     short loc_1800049F2
0x1800049b4  call    memset_0
0x1800049b9  mov     [rsp+0C0h+var_88], 80070006h
0x1800049c1  lea     rax, aOplockcompleti; "OplockCompletionPort HANDLE Closed"
0x1800049c8  mov     [rbp+57h+var_68], rax
0x1800049cc  mov     ecx, edi
0x1800049ce  lea     rax, [rbp+57h+var_70]
0x1800049d2  xor     r9d, r9d
0x1800049d5  mov     [rsp+0C0h+var_90], rax
0x1800049da  xor     r8d, r8d
0x1800049dd  mov     rax, [rbp+57h+UnbiasedTime]
0x1800049e1  xor     edx, edx
0x1800049e3  mov     [rsp+0C0h+var_98], rax
0x1800049e8  mov     qword ptr [rsp+0C0h+dwMilliseconds], rbx
0x1800049ed  call    TlmLogApiReliability
0x1800049f2  mov     rbx, [rsp+0C0h+arg_0]
0x1800049fa  xor     eax, eax
0x1800049fc  add     rsp, 0B0h
0x180004a03  pop     rdi
0x180004a04  pop     rsi
0x180004a05  pop     rbp
0x180004a06  retn
```
