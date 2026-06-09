# KapiUninitialize

- ea: `0x18002d00c`
- end: `0x18002d1d1`
- name: `KapiUninitialize`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18001fce0`

## callees

- `0x180011120`
- `0x180016dfc`
- `0x18001c500`
- `0x18002c504`
- `0x18002c8d8`
- `0x18002c924`
- `0x18002cae4`
- `0x18002ce88`
- `0x18002d00c`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18002d09c`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18002d09c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d0f9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d0f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d052`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d052`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d07b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d07b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d192`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d192`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d133`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d15d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d133`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d15d`

## pseudocode

```c
void KapiUninitialize()
{
  __int64 v0; // rbx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
  }
  EnterCriticalSection(&g_KapiProviderSetLock);
  v0 = g_KapiNlmSignature;
  g_KapiInitialized = 0;
  g_KapiNlmSignature = 0;
  LeaveCriticalSection(&g_KapiProviderSetLock);
  if ( v0 )
    StubNlmCacheSignatureDereference(g_KapiNlmCache);
  RtlUnsubscribeWnfStateChangeNotification(g_KapiWnfNetworkChangeNotification);
  g_KapiWnfNetworkChangeNotification = 0;
  KapiCleanupProvidersHelper();
  if ( _InterlockedExchangeAdd(&g_KapiRpcReferenceObject, 0xFFFFFFFF) != 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
    }
    WaitForSingleObject(g_KapiRpcReferenceEvent, 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
    }
  }
  CloseHandle(g_KapiRpcReferenceEvent);
  KapiStopRpcServer();
  StopWorkQueue(&g_KapiNcbWorkQueue);
  UninitializeWorkQueue(&g_KapiNcbWorkQueue);
  CloseHandle(g_KapiClientCallbackRefEvent);
  if ( g_KapiKaSampleSet )
  {
    FreeSampleSetHelper(g_KapiKaSampleSet);
    g_KapiKaSampleSet = 0;
  }
  StubNlmCacheUninitialize(g_KapiNlmCache);
  DeleteCriticalSection(&g_KapiProviderSetLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
  }
}

```

## disassembly

```asm
0x18002d00c  mov     [rsp+arg_0], rbx
0x18002d011  push    r14
0x18002d013  sub     rsp, 20h
0x18002d017  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d01e  lea     r14, WPP_GLOBAL_Control
0x18002d025  cmp     rcx, r14
0x18002d028  jz      short loc_18002D04B
0x18002d02a  test    byte ptr [rcx+1Ch], 2
0x18002d02e  jz      short loc_18002D04B
0x18002d030  cmp     byte ptr [rcx+19h], 6
0x18002d034  jb      short loc_18002D04B
0x18002d036  mov     rcx, [rcx+10h]
0x18002d03a  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x18002d041  mov     edx, 1Ch
0x18002d046  call    WPP_SF_
0x18002d04b  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18002d052  call    cs:__imp_EnterCriticalSection
0x18002d058  mov     rbx, cs:g_KapiNlmSignature
0x18002d05f  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18002d066  mov     cs:g_KapiInitialized, 0
0x18002d070  mov     cs:g_KapiNlmSignature, 0
0x18002d07b  call    cs:__imp_LeaveCriticalSection
0x18002d081  test    rbx, rbx
0x18002d084  jz      short loc_18002D095
0x18002d086  mov     rcx, cs:g_KapiNlmCache
0x18002d08d  mov     rdx, rbx
0x18002d090  call    StubNlmCacheSignatureDereference
0x18002d095  mov     rcx, cs:g_KapiWnfNetworkChangeNotification
0x18002d09c  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x18002d0a2  mov     cs:g_KapiWnfNetworkChangeNotification, 0
0x18002d0ad  call    KapiCleanupProvidersHelper
0x18002d0b2  or      eax, 0FFFFFFFFh
0x18002d0b5  lock xadd cs:g_KapiRpcReferenceObject, eax
0x18002d0bd  cmp     eax, 1
0x18002d0c0  jz      short loc_18002D12C
0x18002d0c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d0c9  cmp     rcx, r14
0x18002d0cc  jz      short loc_18002D0EF
0x18002d0ce  test    byte ptr [rcx+1Ch], 2
0x18002d0d2  jz      short loc_18002D0EF
0x18002d0d4  cmp     byte ptr [rcx+19h], 5
0x18002d0d8  jb      short loc_18002D0EF
0x18002d0da  mov     rcx, [rcx+10h]
0x18002d0de  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x18002d0e5  mov     edx, 1Dh
0x18002d0ea  call    WPP_SF_
0x18002d0ef  mov     rcx, cs:g_KapiRpcReferenceEvent; hHandle
0x18002d0f6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002d0f9  call    cs:__imp_WaitForSingleObject
0x18002d0ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d106  cmp     rcx, r14
0x18002d109  jz      short loc_18002D12C
0x18002d10b  test    byte ptr [rcx+1Ch], 2
0x18002d10f  jz      short loc_18002D12C
0x18002d111  cmp     byte ptr [rcx+19h], 5
0x18002d115  jb      short loc_18002D12C
0x18002d117  mov     rcx, [rcx+10h]
0x18002d11b  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x18002d122  mov     edx, 1Eh
0x18002d127  call    WPP_SF_
0x18002d12c  mov     rcx, cs:g_KapiRpcReferenceEvent; hObject
0x18002d133  call    cs:__imp_CloseHandle
0x18002d139  call    KapiStopRpcServer
0x18002d13e  lea     rcx, g_KapiNcbWorkQueue
0x18002d145  call    StopWorkQueue
0x18002d14a  lea     rcx, g_KapiNcbWorkQueue
0x18002d151  call    UninitializeWorkQueue
0x18002d156  mov     rcx, cs:g_KapiClientCallbackRefEvent; hObject
0x18002d15d  call    cs:__imp_CloseHandle
0x18002d163  mov     rcx, cs:g_KapiKaSampleSet; lpMem
0x18002d16a  test    rcx, rcx
0x18002d16d  jz      short loc_18002D17F
0x18002d16f  call    FreeSampleSetHelper
0x18002d174  mov     cs:g_KapiKaSampleSet, 0
0x18002d17f  mov     rcx, cs:g_KapiNlmCache; lpCriticalSection
0x18002d186  call    StubNlmCacheUninitialize
0x18002d18b  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18002d192  call    cs:__imp_DeleteCriticalSection
0x18002d198  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d19f  cmp     rcx, r14
0x18002d1a2  jz      short loc_18002D1C5
0x18002d1a4  test    byte ptr [rcx+1Ch], 2
0x18002d1a8  jz      short loc_18002D1C5
0x18002d1aa  cmp     byte ptr [rcx+19h], 6
0x18002d1ae  jb      short loc_18002D1C5
0x18002d1b0  mov     rcx, [rcx+10h]
0x18002d1b4  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x18002d1bb  mov     edx, 1Fh
0x18002d1c0  call    WPP_SF_
0x18002d1c5  mov     rbx, [rsp+28h+arg_0]
0x18002d1ca  add     rsp, 20h
0x18002d1ce  pop     r14
0x18002d1d0  retn
```
