# ClipboardBrokerFactory::Initialize(void)

- ea: `0x1800356a8`
- end: `0x180035789`
- name: `?Initialize@ClipboardBrokerFactory@@CAJXZ`
- size: `225`
- prototype: `HRESULT __fastcall()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180035594`

## callees

- `0x1800356a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800356d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800356f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800356d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800356f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035741`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180035741`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003577b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003577b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800356bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800356bb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180035723`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180035723`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035763`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035763`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180035756`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180035756`

## pseudocode

```c
__int64 __fastcall ClipboardBrokerFactory::Initialize()
{
  unsigned int v0; // ebx
  HRESULT hr; // [rsp+40h] [rbp+8h] BYREF

  hr = 0;
  EnterCriticalSection(&ClipboardBrokerFactory::s_initCS.cs_);
  if ( !ClipboardBrokerFactory::s_pServerBroker )
  {
    ClipboardBrokerFactory::s_hServerThreadEvent = CreateEventW(0, 0, 0, 0);
    if ( ClipboardBrokerFactory::s_hServerThreadEvent )
    {
      ClipboardBrokerFactory::s_hServerThreadStopEvent = CreateEventW(0, 0, 0, 0);
      if ( ClipboardBrokerFactory::s_hServerThreadStopEvent )
      {
        ClipboardBrokerFactory::s_hWorkerThread = CreateThread(
                                                    0,
                                                    0,
                                                    (LPTHREAD_START_ROUTINE)ClipboardBrokerFactory::serverThreadStart,
                                                    &hr,
                                                    0,
                                                    0);
        if ( ClipboardBrokerFactory::s_hWorkerThread )
        {
          if ( WaitForSingleObject(ClipboardBrokerFactory::s_hServerThreadEvent, 0x3E8u) )
          {
            hr = -2147418113;
            RoOriginateError(2147549183LL, 0);
            CloseHandle(ClipboardBrokerFactory::s_hWorkerThread);
            ClipboardBrokerFactory::s_hWorkerThread = 0;
          }
        }
      }
    }
  }
  v0 = hr;
  LeaveCriticalSection(&ClipboardBrokerFactory::s_initCS.cs_);
  return v0;
}

```

## disassembly

```asm
0x1800356a8  push    rbx
0x1800356aa  sub     rsp, 30h
0x1800356ae  xor     ebx, ebx
0x1800356b0  lea     rcx, ?s_initCS@ClipboardBrokerFactory@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x1800356b7  mov     [rsp+38h+hr], ebx
0x1800356bb  call    cs:__imp_EnterCriticalSection
0x1800356c1  cmp     cs:?s_pServerBroker@ClipboardBrokerFactory@@0PEAVCBrokerInstanceHolder@@EA, rbx; CBrokerInstanceHolder * ClipboardBrokerFactory::s_pServerBroker
0x1800356c8  jnz     loc_180035770
0x1800356ce  xor     r9d, r9d; lpName
0x1800356d1  xor     r8d, r8d; bInitialState
0x1800356d4  xor     edx, edx; bManualReset
0x1800356d6  xor     ecx, ecx; lpEventAttributes
0x1800356d8  call    cs:__imp_CreateEventW
0x1800356de  mov     cs:?s_hServerThreadEvent@ClipboardBrokerFactory@@0PEAXEA, rax; void * ClipboardBrokerFactory::s_hServerThreadEvent
0x1800356e5  test    rax, rax
0x1800356e8  jz      loc_180035770
0x1800356ee  xor     r9d, r9d; lpName
0x1800356f1  xor     r8d, r8d; bInitialState
0x1800356f4  xor     edx, edx; bManualReset
0x1800356f6  xor     ecx, ecx; lpEventAttributes
0x1800356f8  call    cs:__imp_CreateEventW
0x1800356fe  mov     cs:?s_hServerThreadStopEvent@ClipboardBrokerFactory@@0PEAXEA, rax; void * ClipboardBrokerFactory::s_hServerThreadStopEvent
0x180035705  test    rax, rax
0x180035708  jz      short loc_180035770
0x18003570a  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x18003570f  lea     r9, [rsp+38h+hr]; lpParameter
0x180035714  lea     r8, ?serverThreadStart@ClipboardBrokerFactory@@CAKPEAX@Z; lpStartAddress
0x18003571b  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x18003571f  xor     edx, edx; dwStackSize
0x180035721  xor     ecx, ecx; lpThreadAttributes
0x180035723  call    cs:__imp_CreateThread
0x180035729  mov     cs:?s_hWorkerThread@ClipboardBrokerFactory@@0PEAXEA, rax; void * ClipboardBrokerFactory::s_hWorkerThread
0x180035730  test    rax, rax
0x180035733  jz      short loc_180035770
0x180035735  mov     rcx, cs:?s_hServerThreadEvent@ClipboardBrokerFactory@@0PEAXEA; hHandle
0x18003573c  mov     edx, 3E8h; dwMilliseconds
0x180035741  call    cs:__imp_WaitForSingleObject
0x180035747  test    eax, eax
0x180035749  jz      short loc_180035770
0x18003574b  mov     ecx, 8000FFFFh
0x180035750  xor     edx, edx
0x180035752  mov     [rsp+38h+hr], ecx
0x180035756  call    cs:__imp_RoOriginateError
0x18003575c  mov     rcx, cs:?s_hWorkerThread@ClipboardBrokerFactory@@0PEAXEA; hObject
0x180035763  call    cs:__imp_CloseHandle
0x180035769  mov     cs:?s_hWorkerThread@ClipboardBrokerFactory@@0PEAXEA, rbx; void * ClipboardBrokerFactory::s_hWorkerThread
0x180035770  mov     ebx, [rsp+38h+hr]
0x180035774  lea     rcx, ?s_initCS@ClipboardBrokerFactory@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x18003577b  call    cs:__imp_LeaveCriticalSection
0x180035781  mov     eax, ebx
0x180035783  add     rsp, 30h
0x180035787  pop     rbx
0x180035788  retn
```
