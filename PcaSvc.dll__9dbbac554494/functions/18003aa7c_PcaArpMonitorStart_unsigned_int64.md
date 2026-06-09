# PcaArpMonitorStart(unsigned __int64)

- ea: `0x18003aa7c`
- end: `0x18003ab52`
- name: `?PcaArpMonitorStart@@YAX_K@Z`
- size: `214`
- prototype: `void __fastcall(struct _PCA_ARP_MONITOR *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003a7c0`
- `0x18003aa20`

## callees

- `0x180012920`
- `0x18003aa7c`
- `0x18003c7bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003aac7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003aac7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ab26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ab26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aab6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003aab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aafb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aafb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003aaec`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003aaec`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18003aa92`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18003aa92`

## string_xrefs

- `0x18003ab01`: `Failed to create Arp monitor thread [%d]`
- `0x18003ab2e`: `No arp monitoring during OOBE.`

## pseudocode

```c
void __fastcall PcaArpMonitorStart(struct _PCA_ARP_MONITOR *a1)
{
  void *v2; // rcx
  HANDLE Thread; // rax
  __int64 dwCreationFlags; // [rsp+20h] [rbp-18h]
  int v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  if ( (unsigned int)OOBEComplete(&v5) && v5 )
  {
    PcapArpMonitorWaitForThread(a1);
    EnterCriticalSection((LPCRITICAL_SECTION)a1);
    v2 = (void *)*((_QWORD *)a1 + 6);
    *((_DWORD *)a1 + 10) = 0;
    ResetEvent(v2);
    Thread = CreateThread(0, 0, PcapArpMonitorThread, a1, 0, 0);
    *((_QWORD *)a1 + 7) = Thread;
    if ( !Thread )
    {
      LODWORD(dwCreationFlags) = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"PcaArpMonitorStart",
        1196,
        (unsigned int)"Failed to create Arp monitor thread [%d]",
        dwCreationFlags);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)a1);
  }
  else
  {
    AslLogCallPrintf(3, (unsigned int)"PcaArpMonitorStart", 1169, (unsigned int)"No arp monitoring during OOBE.");
  }
}

```

## disassembly

```asm
0x18003aa7c  push    rbx
0x18003aa7e  sub     rsp, 30h
0x18003aa82  mov     rbx, rcx
0x18003aa85  mov     [rsp+38h+arg_0], 0
0x18003aa8d  lea     rcx, [rsp+38h+arg_0]
0x18003aa92  call    cs:__imp_OOBEComplete
0x18003aa98  test    eax, eax
0x18003aa9a  jz      loc_18003AB2E
0x18003aaa0  cmp     [rsp+38h+arg_0], 0
0x18003aaa5  jz      loc_18003AB2E
0x18003aaab  mov     rcx, rbx; struct _PCA_ARP_MONITOR *
0x18003aaae  call    ?PcapArpMonitorWaitForThread@@YAXPEAU_PCA_ARP_MONITOR@@@Z; PcapArpMonitorWaitForThread(_PCA_ARP_MONITOR *)
0x18003aab3  mov     rcx, rbx; lpCriticalSection
0x18003aab6  call    cs:__imp_EnterCriticalSection
0x18003aabc  mov     rcx, [rbx+30h]; hEvent
0x18003aac0  mov     dword ptr [rbx+28h], 0
0x18003aac7  call    cs:__imp_ResetEvent
0x18003aacd  mov     r9, rbx; lpParameter
0x18003aad0  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x18003aad9  lea     r8, ?PcapArpMonitorThread@@YAKPEAX@Z; lpStartAddress
0x18003aae0  mov     dword ptr [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18003aae8  xor     edx, edx; dwStackSize
0x18003aaea  xor     ecx, ecx; lpThreadAttributes
0x18003aaec  call    cs:__imp_CreateThread
0x18003aaf2  mov     [rbx+38h], rax
0x18003aaf6  test    rax, rax
0x18003aaf9  jnz     short loc_18003AB23
0x18003aafb  call    cs:__imp_GetLastError
0x18003ab01  lea     r9, aFailedToCreate_7; "Failed to create Arp monitor thread [%d"...
0x18003ab08  mov     r8d, 4ACh
0x18003ab0e  lea     rdx, aPcaarpmonitors; "PcaArpMonitorStart"
0x18003ab15  mov     dword ptr [rsp+38h+dwCreationFlags], eax
0x18003ab19  mov     ecx, 1
0x18003ab1e  call    AslLogCallPrintf
0x18003ab23  mov     rcx, rbx; lpCriticalSection
0x18003ab26  call    cs:__imp_LeaveCriticalSection
0x18003ab2c  jmp     short loc_18003AB4C
0x18003ab2e  lea     r9, aNoArpMonitorin; "No arp monitoring during OOBE."
0x18003ab35  mov     r8d, 491h
0x18003ab3b  lea     rdx, aPcaarpmonitors; "PcaArpMonitorStart"
0x18003ab42  mov     ecx, 3
0x18003ab47  call    AslLogCallPrintf
0x18003ab4c  add     rsp, 30h
0x18003ab50  pop     rbx
0x18003ab51  retn
```
