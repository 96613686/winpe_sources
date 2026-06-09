# NcbPolicyUninitialize

- ea: `0x180022d28`
- end: `0x180022dd6`
- name: `NcbPolicyUninitialize`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021340`
- `0x18002293c`

## callees

- `0x18000a0a0`
- `0x180020ddc`
- `0x18002290c`
- `0x180022d28`
- `0x180022ddc`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180022da1`
- `ntdll!RtlDeleteHashTable` at `0x180022da1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022d7d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022d7d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022db3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022db3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022d8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022d8a`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180022d50`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180022d50`

## pseudocode

```c
void __fastcall NcbPolicyUninitialize(__int64 a1, __int64 a2)
{
  __int64 v2; // rdx
  __int64 v3; // rcx

  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(a1, a2, L"NcbPolicy: Starting uninitialization of NCB policy module - ", 0);
  if ( g_NcbPolicyCsNotification )
  {
    PowerSettingUnregisterNotification(g_NcbPolicyCsNotification);
    g_NcbPolicyCsNotification = 0;
  }
  if ( _InterlockedDecrement(&g_NcbPolicyReference) != 1 )
    WaitForSingleObject(g_NcbPolicyReferenceEvent, 0xFFFFFFFF);
  CloseHandle(g_NcbPolicyReferenceEvent);
  NcbPolicyUnsubscribeFromWnfEvents();
  NcbPolicyCleanupPolicies();
  RtlDeleteHashTable(g_NcbPolicies);
  NcbCCResetUninitialize();
  DeleteCriticalSection(&g_NcbPolicyLock);
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v3, v2, L"NcbPolicy: Finished uninitialization of NCB policy module - ", 0);
}

```

## disassembly

```asm
0x180022d28  sub     rsp, 28h
0x180022d2c  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180022d33  jz      short loc_180022D44
0x180022d35  xor     r9d, r9d
0x180022d38  lea     r8, aNcbpolicyStart_0; "NcbPolicy: Starting uninitialization of"...
0x180022d3f  call    McTemplateU0zq_EventWriteTransfer
0x180022d44  mov     rcx, cs:g_NcbPolicyCsNotification; RegistrationHandle
0x180022d4b  test    rcx, rcx
0x180022d4e  jz      short loc_180022D61
0x180022d50  call    cs:__imp_PowerSettingUnregisterNotification
0x180022d56  mov     cs:g_NcbPolicyCsNotification, 0
0x180022d61  or      eax, 0FFFFFFFFh
0x180022d64  lock xadd cs:g_NcbPolicyReference, eax
0x180022d6c  dec     eax
0x180022d6e  cmp     eax, 1
0x180022d71  jz      short loc_180022D83
0x180022d73  mov     rcx, cs:g_NcbPolicyReferenceEvent; hHandle
0x180022d7a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180022d7d  call    cs:__imp_WaitForSingleObject
0x180022d83  mov     rcx, cs:g_NcbPolicyReferenceEvent; hObject
0x180022d8a  call    cs:__imp_CloseHandle
0x180022d90  call    NcbPolicyUnsubscribeFromWnfEvents
0x180022d95  call    NcbPolicyCleanupPolicies
0x180022d9a  lea     rcx, g_NcbPolicies
0x180022da1  call    cs:__imp_RtlDeleteHashTable
0x180022da7  call    NcbCCResetUninitialize
0x180022dac  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180022db3  call    cs:__imp_DeleteCriticalSection
0x180022db9  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180022dc0  jz      short loc_180022DD1
0x180022dc2  xor     r9d, r9d
0x180022dc5  lea     r8, aNcbpolicyFinis_0; "NcbPolicy: Finished uninitialization of"...
0x180022dcc  call    McTemplateU0zq_EventWriteTransfer
0x180022dd1  add     rsp, 28h
0x180022dd5  retn
```
