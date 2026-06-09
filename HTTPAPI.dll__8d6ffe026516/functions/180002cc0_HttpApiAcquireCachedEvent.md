# HttpApiAcquireCachedEvent

- ea: `0x180002cc0`
- end: `0x180002df3`
- name: `HttpApiAcquireCachedEvent`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001e70`
- `0x180002b40`

## callees

- `0x180002cc0`

## import_xrefs

- `ntdll!NtClose` at `0x180002de3`
- `ntdll!NtClose` at `0x180002de3`
- `ntdll!RtlAllocateHeap` at `0x180002d4a`
- `ntdll!RtlAllocateHeap` at `0x180002d4a`
- `ntdll!NtCreateEvent` at `0x180002d14`
- `ntdll!NtCreateEvent` at `0x180002d14`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180002d2b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180002d73`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180002d2b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180002d73`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002cdc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002cdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002dc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002dc3`

## pseudocode

```c
__int64 __fastcall HttpApiAcquireCachedEvent(HANDLE *a1)
{
  void *Value; // rax
  NTSTATUS v3; // ebx
  _QWORD *Heap; // rsi
  _QWORD *v6; // rax
  HANDLE EventHandle; // [rsp+60h] [rbp+8h] BYREF

  *a1 = 0;
  EventHandle = 0;
  Value = TlsGetValue(g_TlsIndex);
  EventHandle = Value;
  if ( Value )
  {
    v3 = 0;
    *a1 = Value;
    return (unsigned int)v3;
  }
  v3 = NtCreateEvent(&EventHandle, 0x1F0003u, 0, SynchronizationEvent, 0);
  if ( v3 < 0 )
  {
LABEL_8:
    if ( EventHandle )
    {
      NtClose(EventHandle);
      EventHandle = 0;
    }
    TlsSetValue(g_TlsIndex, 0);
    return (unsigned int)v3;
  }
  if ( !TlsSetValue(g_TlsIndex, EventHandle) || (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x18u)) == 0 )
  {
    v3 = -1073741670;
    goto LABEL_8;
  }
  Heap[2] = EventHandle;
  EnterCriticalSection(&g_CachedEventCritSec);
  v6 = g_TlsEvents;
  if ( *((PVOID **)g_TlsEvents + 1) != &g_TlsEvents )
    __fastfail(3u);
  Heap[1] = &g_TlsEvents;
  *Heap = v6;
  v6[1] = Heap;
  g_TlsEvents = Heap;
  LeaveCriticalSection(&g_CachedEventCritSec);
  *a1 = EventHandle;
  return 0;
}

```

## disassembly

```asm
0x180002cc0  push    rbx
0x180002cc2  push    rbp
0x180002cc3  push    rsi
0x180002cc4  push    rdi
0x180002cc5  sub     rsp, 38h
0x180002cc9  xor     ebp, ebp
0x180002ccb  mov     rdi, rcx
0x180002cce  mov     [rcx], rbp
0x180002cd1  mov     ecx, cs:g_TlsIndex; dwTlsIndex
0x180002cd7  mov     [rsp+58h+EventHandle], rbp
0x180002cdc  call    cs:__imp_TlsGetValue
0x180002ce2  mov     [rsp+58h+EventHandle], rax
0x180002ce7  test    rax, rax
0x180002cea  jz      short loc_180002CFC
0x180002cec  mov     ebx, ebp
0x180002cee  mov     [rdi], rax
0x180002cf1  mov     eax, ebx
0x180002cf3  add     rsp, 38h
0x180002cf7  pop     rdi
0x180002cf8  pop     rsi
0x180002cf9  pop     rbp
0x180002cfa  pop     rbx
0x180002cfb  retn
0x180002cfc  mov     r9d, 1; EventType
0x180002d02  mov     [rsp+58h+InitialState], bpl; InitialState
0x180002d07  xor     r8d, r8d; ObjectAttributes
0x180002d0a  lea     rcx, [rsp+58h+EventHandle]; EventHandle
0x180002d0f  mov     edx, 1F0003h; DesiredAccess
0x180002d14  call    cs:__imp_NtCreateEvent
0x180002d1a  mov     ebx, eax
0x180002d1c  test    eax, eax
0x180002d1e  js      short loc_180002D5D
0x180002d20  mov     rdx, [rsp+58h+EventHandle]; lpTlsValue
0x180002d25  mov     ecx, cs:g_TlsIndex; dwTlsIndex
0x180002d2b  call    cs:__imp_TlsSetValue
0x180002d31  test    eax, eax
0x180002d33  jz      short loc_180002D58
0x180002d35  mov     rcx, gs:60h
0x180002d3e  xor     edx, edx; Flags
0x180002d40  mov     r8d, 18h; Size
0x180002d46  mov     rcx, [rcx+30h]; HeapHandle
0x180002d4a  call    cs:__imp_RtlAllocateHeap
0x180002d50  mov     rsi, rax
0x180002d53  test    rax, rax
0x180002d56  jnz     short loc_180002D7E
0x180002d58  mov     ebx, 0C000009Ah
0x180002d5d  mov     rcx, [rsp+58h+EventHandle]; Handle
0x180002d62  test    rcx, rcx
0x180002d65  jnz     short loc_180002DE3
0x180002d67  test    ebx, ebx
0x180002d69  jns     short loc_180002CF1
0x180002d6b  mov     ecx, cs:g_TlsIndex; dwTlsIndex
0x180002d71  xor     edx, edx; lpTlsValue
0x180002d73  call    cs:__imp_TlsSetValue
0x180002d79  jmp     loc_180002CF1
0x180002d7e  mov     rax, [rsp+58h+EventHandle]
0x180002d83  lea     rcx, g_CachedEventCritSec; lpCriticalSection
0x180002d8a  mov     [rsi+10h], rax
0x180002d8e  call    cs:__imp_EnterCriticalSection
0x180002d94  mov     rax, cs:g_TlsEvents
0x180002d9b  lea     rcx, g_TlsEvents
0x180002da2  cmp     [rax+8], rcx
0x180002da6  jnz     short loc_180002DDC
0x180002da8  mov     [rsi+8], rcx
0x180002dac  mov     ebx, ebp
0x180002dae  mov     [rsi], rax
0x180002db1  lea     rcx, g_CachedEventCritSec; lpCriticalSection
0x180002db8  mov     [rax+8], rsi
0x180002dbc  mov     cs:g_TlsEvents, rsi
0x180002dc3  call    cs:__imp_LeaveCriticalSection
0x180002dc9  mov     rax, [rsp+58h+EventHandle]
0x180002dce  mov     [rdi], rax
0x180002dd1  mov     eax, ebx
0x180002dd3  add     rsp, 38h
0x180002dd7  pop     rdi
0x180002dd8  pop     rsi
0x180002dd9  pop     rbp
0x180002dda  pop     rbx
0x180002ddb  retn
0x180002ddc  mov     ecx, 3
0x180002de1  int     29h; Win8: RtlFailFast(ecx)
0x180002de3  call    cs:__imp_NtClose
0x180002de9  mov     [rsp+58h+EventHandle], rbp
0x180002dee  jmp     loc_180002D67
```
