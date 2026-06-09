# KamUninitialize

- ea: `0x18001fce0`
- end: `0x18001fe21`
- name: `KamUninitialize`
- size: `321`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015690`
- `0x1800159b8`
- `0x1800230a0`

## callees

- `0x180009740`
- `0x180011120`
- `0x180016a68`
- `0x18001c500`
- `0x18001d09c`
- `0x18001fce0`
- `0x1800201fc`
- `0x180021340`
- `0x18002c504`
- `0x18002d00c`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fd43`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fd43`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fdc9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fdc9`

## pseudocode

```c
__int64 __fastcall KamUninitialize(__int64 a1, __int64 a2)
{
  __int64 v2; // rdx
  __int64 v3; // rcx

  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(a1, a2, L"Entering KamUninitialize");
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
  }
  _InterlockedExchange(&g_KamInitialized, 0);
  if ( g_KamWNFNetworkChangeNotification )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    g_KamWNFNetworkChangeNotification = 0;
  }
  if ( g_KamKapiInitialized )
  {
    KapiSetKaUpdateCallback(0);
    KapiUninitialize();
  }
  if ( g_RegistrarCallbackTable )
  {
    NcbRegistrarUninitialize();
    g_RegistrarCallbackTable = 0;
  }
  if ( g_NlmSignature )
  {
    StubNlmCacheSignatureDereference(g_NlmCache);
    g_NlmSignature = 0;
  }
  if ( g_NlmCache )
  {
    StubNlmCacheUninitialize(g_NlmCache);
    g_NlmCache = 0;
    DeleteCriticalSection(&g_NlmSignatureLock);
  }
  KampUnregisterProxyNotifications();
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v3, v2, L"Kam uninitialized");
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18001fce0  push    rsi
0x18001fce2  sub     rsp, 20h
0x18001fce6  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001fced  jz      short loc_18001FCFB
0x18001fcef  lea     r8, aEnteringKamuni; "Entering KamUninitialize"
0x18001fcf6  call    McTemplateU0z_EventWriteTransfer
0x18001fcfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd02  lea     rsi, WPP_GLOBAL_Control
0x18001fd09  cmp     rcx, rsi
0x18001fd0c  jz      short loc_18001FD2F
0x18001fd0e  test    byte ptr [rcx+1Ch], 1
0x18001fd12  jz      short loc_18001FD2F
0x18001fd14  cmp     byte ptr [rcx+19h], 6
0x18001fd18  jb      short loc_18001FD2F
0x18001fd1a  mov     rcx, [rcx+10h]
0x18001fd1e  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x18001fd25  mov     edx, 61h ; 'a'
0x18001fd2a  call    WPP_SF_
0x18001fd2f  xor     eax, eax
0x18001fd31  xchg    eax, cs:g_KamInitialized
0x18001fd37  mov     rcx, cs:g_KamWNFNetworkChangeNotification
0x18001fd3e  test    rcx, rcx
0x18001fd41  jz      short loc_18001FD54
0x18001fd43  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001fd49  mov     cs:g_KamWNFNetworkChangeNotification, 0
0x18001fd54  cmp     cs:g_KamKapiInitialized, 0
0x18001fd5b  jz      short loc_18001FD69
0x18001fd5d  xor     ecx, ecx
0x18001fd5f  call    KapiSetKaUpdateCallback
0x18001fd64  call    KapiUninitialize
0x18001fd69  cmp     cs:g_RegistrarCallbackTable, 0
0x18001fd71  jz      short loc_18001FD83
0x18001fd73  call    NcbRegistrarUninitialize
0x18001fd78  mov     cs:g_RegistrarCallbackTable, 0
0x18001fd83  mov     rdx, cs:g_NlmSignature
0x18001fd8a  test    rdx, rdx
0x18001fd8d  jz      short loc_18001FDA6
0x18001fd8f  mov     rcx, cs:g_NlmCache
0x18001fd96  call    StubNlmCacheSignatureDereference
0x18001fd9b  mov     cs:g_NlmSignature, 0
0x18001fda6  mov     rcx, cs:g_NlmCache; lpCriticalSection
0x18001fdad  test    rcx, rcx
0x18001fdb0  jz      short loc_18001FDCF
0x18001fdb2  call    StubNlmCacheUninitialize
0x18001fdb7  lea     rcx, g_NlmSignatureLock; lpCriticalSection
0x18001fdbe  mov     cs:g_NlmCache, 0
0x18001fdc9  call    cs:__imp_DeleteCriticalSection
0x18001fdcf  call    KampUnregisterProxyNotifications
0x18001fdd4  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18001fddb  jz      short loc_18001FDE9
0x18001fddd  lea     r8, aKamUninitializ; "Kam uninitialized"
0x18001fde4  call    McTemplateU0z_EventWriteTransfer
0x18001fde9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdf0  cmp     rcx, rsi
0x18001fdf3  jz      short loc_18001FE19
0x18001fdf5  test    byte ptr [rcx+1Ch], 1
0x18001fdf9  jz      short loc_18001FE19
0x18001fdfb  cmp     byte ptr [rcx+19h], 6
0x18001fdff  jb      short loc_18001FE19
0x18001fe01  mov     rcx, [rcx+10h]
0x18001fe05  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x18001fe0c  mov     edx, 62h ; 'b'
0x18001fe11  xor     r9d, r9d
0x18001fe14  call    WPP_SF_d
0x18001fe19  xor     eax, eax
0x18001fe1b  add     rsp, 20h
0x18001fe1f  pop     rsi
0x18001fe20  retn
```
