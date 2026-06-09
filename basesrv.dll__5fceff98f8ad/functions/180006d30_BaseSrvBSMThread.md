# BaseSrvBSMThread

- ea: `0x180006d30`
- end: `0x180006e1b`
- name: `BaseSrvBSMThread`
- size: `235`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006d30`
- `0x180006e30`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006dbd`
- `ntdll!RtlFreeHeap` at `0x180006dbd`
- `ntdll!RtlEnterCriticalSection` at `0x180006d4a`
- `ntdll!RtlEnterCriticalSection` at `0x180006dd0`
- `ntdll!RtlEnterCriticalSection` at `0x180006d4a`
- `ntdll!RtlEnterCriticalSection` at `0x180006dd0`
- `ntdll!RtlLeaveCriticalSection` at `0x180006d90`
- `ntdll!RtlLeaveCriticalSection` at `0x180006e00`
- `ntdll!RtlLeaveCriticalSection` at `0x180006d90`
- `ntdll!RtlLeaveCriticalSection` at `0x180006e00`
- `ntdll!RtlExitUserThread` at `0x180006e0e`
- `ntdll!RtlExitUserThread` at `0x180006e0e`

## pseudocode

```c
void BaseSrvBSMThread()
{
  NTSTATUS v0; // edi
  PVOID *v1; // rax
  int v2; // ecx
  unsigned int *v3; // rbx
  NTSTATUS v4; // eax
  PVOID v5; // rcx

  v0 = 0;
  RtlEnterCriticalSection(&BaseSrvDDDBSMCritSec);
  v1 = (PVOID *)BSM_Request_Queue;
  v2 = ++BaseSrvpBSMThreadCount;
  v3 = (unsigned int *)BSM_Request_Queue;
  if ( BSM_Request_Queue )
  {
    do
    {
      BSM_Request_Queue = *v1;
      if ( !BSM_Request_Queue )
        BSM_Request_Queue_End = 0;
      RtlLeaveCriticalSection(&BaseSrvDDDBSMCritSec);
      v4 = BroadcastDriveLetterChange(v3[4], *((unsigned __int8 *)v3 + 20), v3 + 2);
      v5 = BaseSrvHeap;
      *(_QWORD *)v3 = 0;
      v0 = v4;
      RtlFreeHeap(v5, 0, v3);
      RtlEnterCriticalSection(&BaseSrvDDDBSMCritSec);
      v1 = (PVOID *)BSM_Request_Queue;
      v3 = (unsigned int *)BSM_Request_Queue;
    }
    while ( BSM_Request_Queue );
    v2 = BaseSrvpBSMThreadCount;
  }
  BaseSrvpBSMThreadCount = v2 - 1;
  RtlLeaveCriticalSection(&BaseSrvDDDBSMCritSec);
  RtlExitUserThread(v0);
  __debugbreak();
  JUMPOUT(0x180006E1BLL);
}

```

## disassembly

```asm
0x180006d30  mov     [rsp+arg_0], rbx
0x180006d35  mov     [rsp+arg_8], rsi
0x180006d3a  push    rdi
0x180006d3b  sub     rsp, 20h
0x180006d3f  xor     esi, esi
0x180006d41  lea     rcx, BaseSrvDDDBSMCritSec; CriticalSection
0x180006d48  mov     edi, esi
0x180006d4a  call    cs:__imp_RtlEnterCriticalSection
0x180006d51  nop     dword ptr [rax+rax+00h]
0x180006d56  mov     ecx, cs:BaseSrvpBSMThreadCount
0x180006d5c  mov     rax, cs:BSM_Request_Queue
0x180006d63  inc     ecx
0x180006d65  mov     cs:BaseSrvpBSMThreadCount, ecx
0x180006d6b  mov     rbx, rax
0x180006d6e  test    rax, rax
0x180006d71  jz      short loc_180006DF1
0x180006d73  mov     rax, [rax]
0x180006d76  mov     cs:BSM_Request_Queue, rax
0x180006d7d  test    rax, rax
0x180006d80  jnz     short loc_180006D89
0x180006d82  mov     cs:BSM_Request_Queue_End, rsi
0x180006d89  lea     rcx, BaseSrvDDDBSMCritSec; CriticalSection
0x180006d90  call    cs:__imp_RtlLeaveCriticalSection
0x180006d97  nop     dword ptr [rax+rax+00h]
0x180006d9c  movzx   edx, byte ptr [rbx+14h]
0x180006da0  lea     r8, [rbx+8]
0x180006da4  mov     ecx, [rbx+10h]
0x180006da7  call    BroadcastDriveLetterChange
0x180006dac  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x180006db3  mov     r8, rbx; P
0x180006db6  xor     edx, edx; Flags
0x180006db8  mov     [rbx], rsi
0x180006dbb  mov     edi, eax
0x180006dbd  call    cs:__imp_RtlFreeHeap
0x180006dc4  nop     dword ptr [rax+rax+00h]
0x180006dc9  lea     rcx, BaseSrvDDDBSMCritSec; CriticalSection
0x180006dd0  call    cs:__imp_RtlEnterCriticalSection
0x180006dd7  nop     dword ptr [rax+rax+00h]
0x180006ddc  mov     rax, cs:BSM_Request_Queue
0x180006de3  mov     rbx, rax
0x180006de6  test    rax, rax
0x180006de9  jnz     short loc_180006D73
0x180006deb  mov     ecx, cs:BaseSrvpBSMThreadCount
0x180006df1  dec     ecx
0x180006df3  mov     cs:BaseSrvpBSMThreadCount, ecx
0x180006df9  lea     rcx, BaseSrvDDDBSMCritSec; CriticalSection
0x180006e00  call    cs:__imp_RtlLeaveCriticalSection
0x180006e07  nop     dword ptr [rax+rax+00h]
0x180006e0c  mov     ecx, edi; Status
0x180006e0e  call    cs:__imp_RtlExitUserThread
0x180006e15  nop     dword ptr [rax+rax+00h]
0x180006e1a  int     3; Trap to Debugger
```
