# KapiInitialize

- ea: `0x18001ae2c`
- end: `0x18001b272`
- name: `KapiInitialize`
- size: `1094`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x1800159b8`

## callees

- `0x1800164a4`
- `0x1800183f8`
- `0x18001ae2c`
- `0x18001b278`
- `0x18001bf40`
- `0x18001c470`
- `0x18001c500`
- `0x18001d09c`
- `0x18002c504`
- `0x18002c8d8`
- `0x18002c924`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001b0cb`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001b0cb`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18001b1a3`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18001b1a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b077`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b0de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b14e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b077`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b0de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b14e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b08b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b0f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b165`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b08b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b0f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b165`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001ae88`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001ae88`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b1f9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b1f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001af26`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b01f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001af26`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b01f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b1bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b1e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b1bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b1e0`

## pseudocode

```c
__int64 KapiInitialize()
{
  __int64 result; // rax
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  const wchar_t *v4; // rdx
  unsigned int v5; // eax
  unsigned int started; // ebx
  int v7; // edi
  __int64 v8; // [rsp+20h] [rbp-58h]
  __int64 v9; // [rsp+28h] [rbp-50h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
  }
  result = InitializeNcbRegistry();
  if ( !(_DWORD)result )
  {
    InitializeCriticalSection(&g_KapiProviderSetLock);
    qword_18004DDE8 = (__int64)&g_KapiProviderSet;
    v4 = (const wchar_t *)&xmmword_18004D980;
    if ( (unsigned __int64)qword_18004D998 > 7 )
      v4 = (const wchar_t *)xmmword_18004D980;
    g_KapiProviderSet = (__int64)&g_KapiProviderSet;
    v5 = StubNlmCacheInitialize(v1, v4, v2, v3, v8, v9, (__int64 *)&g_KapiNlmCache);
    started = v5;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, v5);
      }
      goto LABEL_50;
    }
    g_KapiClientCallbackRefObject = 1;
    g_KapiClientCallbackRefEvent = CreateEventW(0, 1, 1, 0);
    if ( !g_KapiClientCallbackRefEvent )
    {
      started = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, 8);
      }
      goto LABEL_49;
    }
    if ( !(unsigned int)InitializeWorkQueue(&g_KapiNcbWorkQueue) )
    {
      started = 31;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, 31);
      }
      goto LABEL_48;
    }
    if ( !(unsigned int)StartWorkQueue(&g_KapiNcbWorkQueue) )
    {
      started = 31;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, 31);
      }
      goto LABEL_47;
    }
    g_KapiRpcReferenceEvent = CreateEventW(0, 1, 0, 0);
    if ( !g_KapiRpcReferenceEvent )
    {
      started = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, 8);
      }
      goto LABEL_46;
    }
    EnterCriticalSection(&g_KapiProviderSetLock);
    g_KapiInitialized = 1;
    LeaveCriticalSection(&g_KapiProviderSetLock);
    v7 = RtlSubscribeWnfStateChangeNotification(
           &g_KapiWnfNetworkChangeNotification,
           WNF_SEB_NETWORK_STATE_CHANGES,
           0,
           KapiNetworkConnectivityChangeNotification,
           0,
           0,
           0,
           0);
    if ( v7 < 0 )
    {
      EnterCriticalSection(&g_KapiProviderSetLock);
      g_KapiInitialized = 0;
      LeaveCriticalSection(&g_KapiProviderSetLock);
      started = 31;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids,
          (unsigned int)v7);
      }
LABEL_45:
      CloseHandle(g_KapiRpcReferenceEvent);
LABEL_46:
      StopWorkQueue(&g_KapiNcbWorkQueue);
LABEL_47:
      UninitializeWorkQueue(&g_KapiNcbWorkQueue);
LABEL_48:
      CloseHandle(g_KapiClientCallbackRefEvent);
LABEL_49:
      StubNlmCacheUninitialize(g_KapiNlmCache);
LABEL_50:
      DeleteCriticalSection(&g_KapiProviderSetLock);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, started);
      }
      return started;
    }
    started = KapiStartRpcServer();
    if ( started )
    {
      EnterCriticalSection(&g_KapiProviderSetLock);
      g_KapiInitialized = 0;
      LeaveCriticalSection(&g_KapiProviderSetLock);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, started);
      }
      if ( g_KapiWnfNetworkChangeNotification )
      {
        RtlUnsubscribeWnfStateChangeNotification();
        g_KapiWnfNetworkChangeNotification = 0;
      }
      goto LABEL_45;
    }
    g_KapiRpcReferenceObject = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, 0);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001ae2c  push    rbx
0x18001ae2e  push    rsi
0x18001ae2f  push    rdi
0x18001ae30  push    r12
0x18001ae32  push    r14
0x18001ae34  push    r15
0x18001ae36  sub     rsp, 48h
0x18001ae3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae41  lea     r14, WPP_GLOBAL_Control
0x18001ae48  lea     r15, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x18001ae4f  mov     sil, 2
0x18001ae52  cmp     rcx, r14
0x18001ae55  jz      short loc_18001AE74
0x18001ae57  test    [rcx+1Ch], sil
0x18001ae5b  jz      short loc_18001AE74
0x18001ae5d  cmp     byte ptr [rcx+19h], 6
0x18001ae61  jb      short loc_18001AE74
0x18001ae63  mov     rcx, [rcx+10h]
0x18001ae67  mov     edx, 12h
0x18001ae6c  mov     r8, r15
0x18001ae6f  call    WPP_SF_
0x18001ae74  call    InitializeNcbRegistry
0x18001ae79  test    eax, eax
0x18001ae7b  jnz     loc_18001B264
0x18001ae81  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18001ae88  call    cs:__imp_InitializeCriticalSection
0x18001ae8e  cmp     cs:qword_18004D998, 7
0x18001ae96  lea     rax, g_KapiProviderSet
0x18001ae9d  mov     cs:qword_18004DDE8, rax
0x18001aea4  lea     rdx, xmmword_18004D980
0x18001aeab  cmova   rdx, qword ptr cs:xmmword_18004D980
0x18001aeb3  mov     cs:g_KapiProviderSet, rax
0x18001aeba  lea     rax, g_KapiNlmCache
0x18001aec1  mov     [rsp+78h+var_48], rax
0x18001aec6  call    StubNlmCacheInitialize
0x18001aecb  mov     ebx, eax
0x18001aecd  test    eax, eax
0x18001aecf  jz      short loc_18001AF0E
0x18001aed1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aed8  cmp     rcx, r14
0x18001aedb  jz      loc_18001B1F2
0x18001aee1  test    [rcx+1Ch], sil
0x18001aee5  jz      loc_18001B1F2
0x18001aeeb  cmp     [rcx+19h], sil
0x18001aeef  jb      loc_18001B1F2
0x18001aef5  mov     rcx, [rcx+10h]
0x18001aef9  mov     edx, 13h
0x18001aefe  mov     r9d, eax
0x18001af01  mov     r8, r15
0x18001af04  call    WPP_SF_d
0x18001af09  jmp     loc_18001B1F2
0x18001af0e  mov     r12d, 1
0x18001af14  xor     r9d, r9d; lpName
0x18001af17  mov     r8d, r12d; bInitialState
0x18001af1a  mov     cs:g_KapiClientCallbackRefObject, r12d
0x18001af21  mov     edx, r12d; bManualReset
0x18001af24  xor     ecx, ecx; lpEventAttributes
0x18001af26  call    cs:__imp_CreateEventW
0x18001af2c  mov     cs:g_KapiClientCallbackRefEvent, rax
0x18001af33  test    rax, rax
0x18001af36  jnz     short loc_18001AF78
0x18001af38  lea     r9d, [r12+7]
0x18001af3d  mov     ebx, r9d
0x18001af40  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af47  cmp     rcx, r14
0x18001af4a  jz      loc_18001B1E6
0x18001af50  test    [rcx+1Ch], sil
0x18001af54  jz      loc_18001B1E6
0x18001af5a  cmp     [rcx+19h], sil
0x18001af5e  jb      loc_18001B1E6
0x18001af64  mov     rcx, [rcx+10h]
0x18001af68  lea     edx, [rax+14h]
0x18001af6b  mov     r8, r15
0x18001af6e  call    WPP_SF_d
0x18001af73  jmp     loc_18001B1E6
0x18001af78  lea     rcx, g_KapiNcbWorkQueue; lpCriticalSection
0x18001af7f  call    InitializeWorkQueue
0x18001af84  test    eax, eax
0x18001af86  jnz     short loc_18001AFC6
0x18001af88  lea     ebx, [rax+1Fh]
0x18001af8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af92  cmp     rcx, r14
0x18001af95  jz      loc_18001B1D9
0x18001af9b  test    [rcx+1Ch], sil
0x18001af9f  jz      loc_18001B1D9
0x18001afa5  cmp     [rcx+19h], sil
0x18001afa9  jb      loc_18001B1D9
0x18001afaf  mov     rcx, [rcx+10h]
0x18001afb3  lea     edx, [rax+15h]
0x18001afb6  mov     r9d, ebx
0x18001afb9  mov     r8, r15
0x18001afbc  call    WPP_SF_d
0x18001afc1  jmp     loc_18001B1D9
0x18001afc6  lea     rcx, g_KapiNcbWorkQueue
0x18001afcd  call    StartWorkQueue
0x18001afd2  test    eax, eax
0x18001afd4  jnz     short loc_18001B014
0x18001afd6  lea     ebx, [rax+1Fh]
0x18001afd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afe0  cmp     rcx, r14
0x18001afe3  jz      loc_18001B1CD
0x18001afe9  test    [rcx+1Ch], sil
0x18001afed  jz      loc_18001B1CD
0x18001aff3  cmp     [rcx+19h], sil
0x18001aff7  jb      loc_18001B1CD
0x18001affd  mov     rcx, [rcx+10h]
0x18001b001  lea     edx, [rax+16h]
0x18001b004  mov     r9d, ebx
0x18001b007  mov     r8, r15
0x18001b00a  call    WPP_SF_d
0x18001b00f  jmp     loc_18001B1CD
0x18001b014  xor     r9d, r9d; lpName
0x18001b017  xor     r8d, r8d; bInitialState
0x18001b01a  mov     edx, r12d; bManualReset
0x18001b01d  xor     ecx, ecx; lpEventAttributes
0x18001b01f  call    cs:__imp_CreateEventW
0x18001b025  mov     cs:g_KapiRpcReferenceEvent, rax
0x18001b02c  test    rax, rax
0x18001b02f  jnz     short loc_18001B070
0x18001b031  lea     r9d, [rax+8]
0x18001b035  mov     ebx, r9d
0x18001b038  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b03f  cmp     rcx, r14
0x18001b042  jz      loc_18001B1C1
0x18001b048  test    [rcx+1Ch], sil
0x18001b04c  jz      loc_18001B1C1
0x18001b052  cmp     [rcx+19h], sil
0x18001b056  jb      loc_18001B1C1
0x18001b05c  mov     rcx, [rcx+10h]
0x18001b060  lea     edx, [rax+17h]
0x18001b063  mov     r8, r15
0x18001b066  call    WPP_SF_d
0x18001b06b  jmp     loc_18001B1C1
0x18001b070  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18001b077  call    cs:__imp_EnterCriticalSection
0x18001b07d  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18001b084  mov     cs:g_KapiInitialized, r12d
0x18001b08b  call    cs:__imp_LeaveCriticalSection
0x18001b091  mov     rdx, cs:WNF_SEB_NETWORK_STATE_CHANGES
0x18001b098  lea     r9, KapiNetworkConnectivityChangeNotification
0x18001b09f  mov     [rsp+78h+var_40], 0
0x18001b0a7  lea     rcx, g_KapiWnfNetworkChangeNotification
0x18001b0ae  mov     dword ptr [rsp+78h+var_48], 0
0x18001b0b6  xor     r8d, r8d
0x18001b0b9  mov     [rsp+78h+var_50], 0
0x18001b0c2  mov     [rsp+78h+var_58], 0
0x18001b0cb  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18001b0d1  mov     edi, eax
0x18001b0d3  test    eax, eax
0x18001b0d5  jns     short loc_18001B138
0x18001b0d7  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18001b0de  call    cs:__imp_EnterCriticalSection
0x18001b0e4  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18001b0eb  mov     cs:g_KapiInitialized, 0
0x18001b0f5  call    cs:__imp_LeaveCriticalSection
0x18001b0fb  mov     ebx, 1Fh
0x18001b100  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b107  cmp     rcx, r14
0x18001b10a  jz      loc_18001B1B4
0x18001b110  test    [rcx+1Ch], sil
0x18001b114  jz      loc_18001B1B4
0x18001b11a  cmp     [rcx+19h], sil
0x18001b11e  jb      loc_18001B1B4
0x18001b124  mov     rcx, [rcx+10h]
0x18001b128  lea     edx, [rbx-7]
0x18001b12b  mov     r9d, edi
0x18001b12e  mov     r8, r15
0x18001b131  call    WPP_SF_d
0x18001b136  jmp     short loc_18001B1B4
0x18001b138  call    KapiStartRpcServer
0x18001b13d  mov     ebx, eax
0x18001b13f  test    eax, eax
0x18001b141  jz      loc_18001B22F
0x18001b147  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18001b14e  call    cs:__imp_EnterCriticalSection
0x18001b154  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18001b15b  mov     cs:g_KapiInitialized, 0
0x18001b165  call    cs:__imp_LeaveCriticalSection
0x18001b16b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b172  cmp     rcx, r14
0x18001b175  jz      short loc_18001B197
0x18001b177  test    [rcx+1Ch], sil
0x18001b17b  jz      short loc_18001B197
0x18001b17d  cmp     [rcx+19h], sil
0x18001b181  jb      short loc_18001B197
0x18001b183  mov     rcx, [rcx+10h]
0x18001b187  mov     edx, 19h
0x18001b18c  mov     r9d, ebx
0x18001b18f  mov     r8, r15
0x18001b192  call    WPP_SF_d
0x18001b197  mov     rcx, cs:g_KapiWnfNetworkChangeNotification
0x18001b19e  test    rcx, rcx
0x18001b1a1  jz      short loc_18001B1B4
0x18001b1a3  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x18001b1a9  mov     cs:g_KapiWnfNetworkChangeNotification, 0
0x18001b1b4  mov     rcx, cs:g_KapiRpcReferenceEvent; hObject
0x18001b1bb  call    cs:__imp_CloseHandle
0x18001b1c1  lea     rcx, g_KapiNcbWorkQueue
0x18001b1c8  call    StopWorkQueue
0x18001b1cd  lea     rcx, g_KapiNcbWorkQueue
0x18001b1d4  call    UninitializeWorkQueue
0x18001b1d9  mov     rcx, cs:g_KapiClientCallbackRefEvent; hObject
0x18001b1e0  call    cs:__imp_CloseHandle
0x18001b1e6  mov     rcx, cs:g_KapiNlmCache; lpCriticalSection
0x18001b1ed  call    StubNlmCacheUninitialize
0x18001b1f2  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18001b1f9  call    cs:__imp_DeleteCriticalSection
0x18001b1ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b206  cmp     rcx, r14
0x18001b209  jz      short loc_18001B22B
0x18001b20b  test    [rcx+1Ch], sil
0x18001b20f  jz      short loc_18001B22B
0x18001b211  cmp     byte ptr [rcx+19h], 6
0x18001b215  jb      short loc_18001B22B
0x18001b217  mov     rcx, [rcx+10h]
0x18001b21b  mov     edx, 1Bh
0x18001b220  mov     r9d, ebx
0x18001b223  mov     r8, r15
0x18001b226  call    WPP_SF_d
0x18001b22b  mov     eax, ebx
0x18001b22d  jmp     short loc_18001B264
0x18001b22f  mov     cs:g_KapiRpcReferenceObject, r12d
0x18001b236  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b23d  cmp     rcx, r14
0x18001b240  jz      short loc_18001B262
0x18001b242  test    [rcx+1Ch], sil
0x18001b246  jz      short loc_18001B262
0x18001b248  cmp     byte ptr [rcx+19h], 6
0x18001b24c  jb      short loc_18001B262
0x18001b24e  mov     rcx, [rcx+10h]
0x18001b252  mov     edx, 1Ah
0x18001b257  xor     r9d, r9d
0x18001b25a  mov     r8, r15
0x18001b25d  call    WPP_SF_d
0x18001b262  xor     eax, eax
0x18001b264  add     rsp, 48h
0x18001b268  pop     r15
0x18001b26a  pop     r14
0x18001b26c  pop     r12
0x18001b26e  pop     rdi
0x18001b26f  pop     rsi
0x18001b270  pop     rbx
0x18001b271  retn
```
