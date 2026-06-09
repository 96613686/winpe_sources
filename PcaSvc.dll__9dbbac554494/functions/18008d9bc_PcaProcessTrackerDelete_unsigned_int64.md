# PcaProcessTrackerDelete(unsigned __int64)

- ea: `0x18008d9bc`
- end: `0x18008db25`
- name: `?PcaProcessTrackerDelete@@YAX_K@Z`
- size: `361`
- prototype: `void __fastcall(struct _PCA_PROCESS_TRACKER *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ba0c`
- `0x1800858d4`

## callees

- `0x180012920`
- `0x1800317cc`
- `0x18008d9bc`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18008dadf`
- `ntdll!RtlFreeHeap` at `0x18008db0f`
- `ntdll!RtlFreeHeap` at `0x18008dadf`
- `ntdll!RtlFreeHeap` at `0x18008db0f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008daf7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008daf7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008da3a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008da3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008da07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008da07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008daa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008dab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008daa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008dab8`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18008d9fd`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18008d9fd`

## string_xrefs

- `0x18008da54`: `Waiting for job thread to end: %d`
- `0x18008da76`: `Failed to shut down job thread: %08lx`
- `0x18008da0d`: `Failed to post quit completion status [%d]`
- `0x18008da1a`: `PcaProcessTrackerDelete`
- `0x18008da61`: `PcaProcessTrackerDelete`
- `0x18008da87`: `PcaProcessTrackerDelete`

## pseudocode

```c
void __fastcall PcaProcessTrackerDelete(struct _PCA_PROCESS_TRACKER *a1)
{
  bool v1; // zf
  void *v3; // rcx
  __int64 v4; // rdi
  DWORD v5; // esi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // r8
  __int64 v9; // [rsp+20h] [rbp-18h]
  DWORD LastError; // [rsp+20h] [rbp-18h]

  if ( a1 )
  {
    v1 = *((_QWORD *)a1 + 11) == 0;
    *((_DWORD *)a1 + 26) = 1;
    if ( !v1 )
    {
      v3 = (void *)*((_QWORD *)a1 + 12);
      if ( v3 && !PostQueuedCompletionStatus(v3, 0x3E7u, 0, 0) )
      {
        LastError = GetLastError();
        AslLogCallPrintf(
          1,
          (unsigned int)"PcaProcessTrackerDelete",
          270,
          (unsigned int)"Failed to post quit completion status [%d]",
          LastError);
      }
      v4 = 0;
      while ( 1 )
      {
        v5 = WaitForSingleObject(*((HANDLE *)a1 + 11), 0x1F4u);
        if ( !v5 )
          break;
        LODWORD(v9) = v4 + 1;
        AslLogCallPrintf(
          2,
          (unsigned int)"PcaProcessTrackerDelete",
          286,
          (unsigned int)"Waiting for job thread to end: %d",
          v9);
        if ( (unsigned __int64)++v4 >= 5 )
        {
          LODWORD(v9) = v5;
          AslLogCallPrintf(
            1,
            (unsigned int)"PcaProcessTrackerDelete",
            290,
            (unsigned int)"Failed to shut down job thread: %08lx",
            v9);
          break;
        }
      }
    }
    v6 = (void *)*((_QWORD *)a1 + 12);
    if ( v6 )
    {
      CloseHandle(v6);
      *((_QWORD *)a1 + 12) = 0;
    }
    v7 = (void *)*((_QWORD *)a1 + 11);
    if ( v7 )
    {
      CloseHandle(v7);
      *((_QWORD *)a1 + 11) = 0;
    }
    PcapProcessTrackerFreeChainContexts(a1, 0);
    v8 = (void *)*((_QWORD *)a1 + 10);
    if ( v8 )
      RtlFreeHeap(*((HANDLE *)a1 + 5), 0, v8);
    *(_OWORD *)((char *)a1 + 40) = 0;
    *(_OWORD *)((char *)a1 + 56) = 0;
    *(_OWORD *)((char *)a1 + 72) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)a1);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
  }
}

```

## disassembly

```asm
0x18008d9bc  test    rcx, rcx
0x18008d9bf  jz      locret_18008DB24
0x18008d9c5  mov     [rsp+arg_0], rbx
0x18008d9ca  mov     [rsp+arg_8], rsi
0x18008d9cf  push    rdi
0x18008d9d0  sub     rsp, 30h
0x18008d9d4  cmp     qword ptr [rcx+58h], 0
0x18008d9d9  mov     rbx, rcx
0x18008d9dc  mov     dword ptr [rcx+68h], 1
0x18008d9e3  jz      loc_18008DA98
0x18008d9e9  mov     rcx, [rcx+60h]; CompletionPort
0x18008d9ed  test    rcx, rcx
0x18008d9f0  jz      short loc_18008DA2F
0x18008d9f2  xor     r9d, r9d; lpOverlapped
0x18008d9f5  xor     r8d, r8d; dwCompletionKey
0x18008d9f8  mov     edx, 3E7h; dwNumberOfBytesTransferred
0x18008d9fd  call    cs:__imp_PostQueuedCompletionStatus
0x18008da03  test    eax, eax
0x18008da05  jnz     short loc_18008DA2F
0x18008da07  call    cs:__imp_GetLastError
0x18008da0d  lea     r9, aFailedToPostQu; "Failed to post quit completion status ["...
0x18008da14  mov     r8d, 10Eh
0x18008da1a  lea     rdx, aPcaprocesstrac_1; "PcaProcessTrackerDelete"
0x18008da21  mov     dword ptr [rsp+38h+var_18], eax
0x18008da25  mov     ecx, 1
0x18008da2a  call    AslLogCallPrintf
0x18008da2f  xor     edi, edi
0x18008da31  mov     rcx, [rbx+58h]; hHandle
0x18008da35  mov     edx, 1F4h; dwMilliseconds
0x18008da3a  call    cs:__imp_WaitForSingleObject
0x18008da40  mov     esi, eax
0x18008da42  test    eax, eax
0x18008da44  jz      short loc_18008DA98
0x18008da46  lea     r8d, [rdi+1]
0x18008da4a  mov     ecx, 2
0x18008da4f  mov     dword ptr [rsp+38h+var_18], r8d
0x18008da54  lea     r9, aWaitingForJobT; "Waiting for job thread to end: %d"
0x18008da5b  mov     r8d, 11Eh
0x18008da61  lea     rdx, aPcaprocesstrac_1; "PcaProcessTrackerDelete"
0x18008da68  call    AslLogCallPrintf
0x18008da6d  inc     rdi
0x18008da70  cmp     rdi, 5
0x18008da74  jb      short loc_18008DA31
0x18008da76  lea     r9, aFailedToShutDo; "Failed to shut down job thread: %08lx"
0x18008da7d  mov     dword ptr [rsp+38h+var_18], esi
0x18008da81  mov     r8d, 122h
0x18008da87  lea     rdx, aPcaprocesstrac_1; "PcaProcessTrackerDelete"
0x18008da8e  mov     ecx, 1
0x18008da93  call    AslLogCallPrintf
0x18008da98  mov     rcx, [rbx+60h]; hObject
0x18008da9c  test    rcx, rcx
0x18008da9f  jz      short loc_18008DAAF
0x18008daa1  call    cs:__imp_CloseHandle
0x18008daa7  mov     qword ptr [rbx+60h], 0
0x18008daaf  mov     rcx, [rbx+58h]; hObject
0x18008dab3  test    rcx, rcx
0x18008dab6  jz      short loc_18008DAC6
0x18008dab8  call    cs:__imp_CloseHandle
0x18008dabe  mov     qword ptr [rbx+58h], 0
0x18008dac6  xor     edx, edx; int
0x18008dac8  mov     rcx, rbx; struct _PCA_PROCESS_TRACKER *
0x18008dacb  call    ?PcapProcessTrackerFreeChainContexts@@YAXPEAU_PCA_PROCESS_TRACKER@@H@Z; PcapProcessTrackerFreeChainContexts(_PCA_PROCESS_TRACKER *,int)
0x18008dad0  mov     r8, [rbx+50h]; P
0x18008dad4  test    r8, r8
0x18008dad7  jz      short loc_18008DAE5
0x18008dad9  mov     rcx, [rbx+28h]; HeapHandle
0x18008dadd  xor     edx, edx; Flags
0x18008dadf  call    cs:__imp_RtlFreeHeap
0x18008dae5  xorps   xmm0, xmm0
0x18008dae8  mov     rcx, rbx; lpCriticalSection
0x18008daeb  movups  xmmword ptr [rbx+28h], xmm0
0x18008daef  movups  xmmword ptr [rbx+38h], xmm0
0x18008daf3  movups  xmmword ptr [rbx+48h], xmm0
0x18008daf7  call    cs:__imp_DeleteCriticalSection
0x18008dafd  mov     rcx, gs:60h
0x18008db06  mov     r8, rbx; P
0x18008db09  xor     edx, edx; Flags
0x18008db0b  mov     rcx, [rcx+30h]; HeapHandle
0x18008db0f  call    cs:__imp_RtlFreeHeap
0x18008db15  mov     rbx, [rsp+38h+arg_0]
0x18008db1a  mov     rsi, [rsp+38h+arg_8]
0x18008db1f  add     rsp, 30h
0x18008db23  pop     rdi
0x18008db24  retn
```
