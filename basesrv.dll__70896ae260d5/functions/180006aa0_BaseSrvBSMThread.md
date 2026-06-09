# BaseSrvBSMThread

- ea: `0x180006aa0`
- end: `0x180006b8b`
- name: `BaseSrvBSMThread`
- size: `235`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006aa0`
- `0x180006ba0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006b2d`
- `ntdll!RtlFreeHeap` at `0x180006b2d`
- `ntdll!RtlEnterCriticalSection` at `0x180006aba`
- `ntdll!RtlEnterCriticalSection` at `0x180006b40`
- `ntdll!RtlEnterCriticalSection` at `0x180006aba`
- `ntdll!RtlEnterCriticalSection` at `0x180006b40`
- `ntdll!RtlLeaveCriticalSection` at `0x180006b00`
- `ntdll!RtlLeaveCriticalSection` at `0x180006b70`
- `ntdll!RtlLeaveCriticalSection` at `0x180006b00`
- `ntdll!RtlLeaveCriticalSection` at `0x180006b70`
- `ntdll!RtlExitUserThread` at `0x180006b7e`
- `ntdll!RtlExitUserThread` at `0x180006b7e`

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
  JUMPOUT(0x180006B8BLL);
}

```

## disassembly

```asm
0x180006aa0  mov     [rsp+arg_0], rbx
0x180006aa5  mov     [rsp+arg_8], rsi
0x180006aaa  push    rdi
0x180006aab  sub     rsp, 20h
0x180006aaf  xor     esi, esi
0x180006ab1  lea     rcx, BaseSrvDDDBSMCritSec; CriticalSection
0x180006ab8  mov     edi, esi
0x180006aba  call    cs:__imp_RtlEnterCriticalSection
0x180006ac1  nop     dword ptr [rax+rax+00h]
0x180006ac6  mov     ecx, cs:BaseSrvpBSMThreadCount
0x180006acc  mov     rax, cs:BSM_Request_Queue
0x180006ad3  inc     ecx
0x180006ad5  mov     cs:BaseSrvpBSMThreadCount, ecx
0x180006adb  mov     rbx, rax
0x180006ade  test    rax, rax
0x180006ae1  jz      short loc_180006B61
0x180006ae3  mov     rax, [rax]
0x180006ae6  mov     cs:BSM_Request_Queue, rax
0x180006aed  test    rax, rax
0x180006af0  jnz     short loc_180006AF9
0x180006af2  mov     cs:BSM_Request_Queue_End, rsi
0x180006af9  lea     rcx, BaseSrvDDDBSMCritSec; CriticalSection
0x180006b00  call    cs:__imp_RtlLeaveCriticalSection
0x180006b07  nop     dword ptr [rax+rax+00h]
0x180006b0c  movzx   edx, byte ptr [rbx+14h]
0x180006b10  lea     r8, [rbx+8]
0x180006b14  mov     ecx, [rbx+10h]
0x180006b17  call    BroadcastDriveLetterChange
0x180006b1c  mov     rcx, cs:BaseSrvHeap; HeapHandle
0x180006b23  mov     r8, rbx; P
0x180006b26  xor     edx, edx; Flags
0x180006b28  mov     [rbx], rsi
0x180006b2b  mov     edi, eax
0x180006b2d  call    cs:__imp_RtlFreeHeap
0x180006b34  nop     dword ptr [rax+rax+00h]
0x180006b39  lea     rcx, BaseSrvDDDBSMCritSec; CriticalSection
0x180006b40  call    cs:__imp_RtlEnterCriticalSection
0x180006b47  nop     dword ptr [rax+rax+00h]
0x180006b4c  mov     rax, cs:BSM_Request_Queue
0x180006b53  mov     rbx, rax
0x180006b56  test    rax, rax
0x180006b59  jnz     short loc_180006AE3
0x180006b5b  mov     ecx, cs:BaseSrvpBSMThreadCount
0x180006b61  dec     ecx
0x180006b63  mov     cs:BaseSrvpBSMThreadCount, ecx
0x180006b69  lea     rcx, BaseSrvDDDBSMCritSec; CriticalSection
0x180006b70  call    cs:__imp_RtlLeaveCriticalSection
0x180006b77  nop     dword ptr [rax+rax+00h]
0x180006b7c  mov     ecx, edi; Status
0x180006b7e  call    cs:__imp_RtlExitUserThread
0x180006b85  nop     dword ptr [rax+rax+00h]
0x180006b8a  int     3; Trap to Debugger
```
