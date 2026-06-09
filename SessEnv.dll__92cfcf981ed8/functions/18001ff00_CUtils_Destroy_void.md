# CUtils::Destroy(void)

- ea: `0x18001ff00`
- end: `0x18002006a`
- name: `?Destroy@CUtils@@SAXXZ`
- size: `362`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800141f4`
- `0x180020acc`

## callees

- `0x180003f30`
- `0x18001a8d0`
- `0x18001ff00`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18001ff16`
- `ntdll!RtlFreeSid` at `0x18001ff33`
- `ntdll!RtlFreeSid` at `0x18001ff50`
- `ntdll!RtlFreeSid` at `0x18001ff16`
- `ntdll!RtlFreeSid` at `0x18001ff33`
- `ntdll!RtlFreeSid` at `0x18001ff50`
- `ntdll!RtlDeleteResource` at `0x18001ffeb`
- `ntdll!RtlDeleteResource` at `0x18001ffeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020025`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18002001b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18002001b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ff6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ff8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ffa7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ffc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ff6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ff8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ffa7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ffc4`

## pseudocode

```c
void CUtils::Destroy(void)
{
  _DWORD *v0; // rbx
  signed int LastError; // eax

  if ( CUtils::pSystemSid )
  {
    RtlFreeSid(CUtils::pSystemSid);
    CUtils::pSystemSid = 0;
  }
  if ( CUtils::pAdminSid )
  {
    RtlFreeSid(CUtils::pAdminSid);
    CUtils::pAdminSid = 0;
  }
  if ( CUtils::pAnonymousSid )
  {
    RtlFreeSid(CUtils::pAnonymousSid);
    CUtils::pAnonymousSid = 0;
  }
  if ( CUtils::pNetworkServiceSid )
  {
    LocalFree(CUtils::pNetworkServiceSid);
    CUtils::pNetworkServiceSid = 0;
  }
  if ( CUtils::pRdsMsSid )
  {
    LocalFree(CUtils::pRdsMsSid);
    CUtils::pRdsMsSid = 0;
  }
  if ( CUtils::pAppContainerSid )
  {
    LocalFree(CUtils::pAppContainerSid);
    CUtils::pAppContainerSid = 0;
  }
  if ( CUtils::pLPACCapabilitySid )
  {
    LocalFree(CUtils::pLPACCapabilitySid);
    CUtils::pLPACCapabilitySid = 0;
  }
  v0 = g_pObjectTracker;
  if ( g_pObjectTracker )
  {
    if ( *((_DWORD *)g_pObjectTracker + 30) )
      RtlDeleteResource((PRTL_RESOURCE)((char *)g_pObjectTracker + 24));
    v0[30] = 0;
    operator delete(v0);
    g_pObjectTracker = 0;
  }
  if ( COpsMonitorBase::g_OpsMonitorTimeQueue )
  {
    if ( !DeleteTimerQueueEx(COpsMonitorBase::g_OpsMonitorTimeQueue, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( (g_DebugTraceComponent & 0x40) != 0 )
        _DbgPrintMessage(2, "COpsMonitorBase::Destroy() failed with 0x%08x", LastError);
    }
    COpsMonitorBase::g_OpsMonitorTimeQueue = 0;
  }
}

```

## disassembly

```asm
0x18001ff00  mov     [rsp+arg_0], rbx
0x18001ff05  push    rdi
0x18001ff06  sub     rsp, 20h
0x18001ff0a  mov     rcx, cs:?pSystemSid@CUtils@@0PEAXEA; Sid
0x18001ff11  test    rcx, rcx
0x18001ff14  jz      short loc_18001FF27
0x18001ff16  call    cs:__imp_RtlFreeSid
0x18001ff1c  mov     cs:?pSystemSid@CUtils@@0PEAXEA, 0
0x18001ff27  mov     rcx, cs:?pAdminSid@CUtils@@0PEAXEA; Sid
0x18001ff2e  test    rcx, rcx
0x18001ff31  jz      short loc_18001FF44
0x18001ff33  call    cs:__imp_RtlFreeSid
0x18001ff39  mov     cs:?pAdminSid@CUtils@@0PEAXEA, 0
0x18001ff44  mov     rcx, cs:?pAnonymousSid@CUtils@@0PEAXEA; Sid
0x18001ff4b  test    rcx, rcx
0x18001ff4e  jz      short loc_18001FF61
0x18001ff50  call    cs:__imp_RtlFreeSid
0x18001ff56  mov     cs:?pAnonymousSid@CUtils@@0PEAXEA, 0
0x18001ff61  mov     rcx, cs:?pNetworkServiceSid@CUtils@@0PEAXEA; hMem
0x18001ff68  test    rcx, rcx
0x18001ff6b  jz      short loc_18001FF7E
0x18001ff6d  call    cs:__imp_LocalFree
0x18001ff73  mov     cs:?pNetworkServiceSid@CUtils@@0PEAXEA, 0
0x18001ff7e  mov     rcx, cs:?pRdsMsSid@CUtils@@0PEAXEA; hMem
0x18001ff85  test    rcx, rcx
0x18001ff88  jz      short loc_18001FF9B
0x18001ff8a  call    cs:__imp_LocalFree
0x18001ff90  mov     cs:?pRdsMsSid@CUtils@@0PEAXEA, 0
0x18001ff9b  mov     rcx, cs:?pAppContainerSid@CUtils@@0PEAXEA; hMem
0x18001ffa2  test    rcx, rcx
0x18001ffa5  jz      short loc_18001FFB8
0x18001ffa7  call    cs:__imp_LocalFree
0x18001ffad  mov     cs:?pAppContainerSid@CUtils@@0PEAXEA, 0
0x18001ffb8  mov     rcx, cs:?pLPACCapabilitySid@CUtils@@0PEAXEA; hMem
0x18001ffbf  test    rcx, rcx
0x18001ffc2  jz      short loc_18001FFD5
0x18001ffc4  call    cs:__imp_LocalFree
0x18001ffca  mov     cs:?pLPACCapabilitySid@CUtils@@0PEAXEA, 0
0x18001ffd5  mov     rbx, cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA
0x18001ffdc  test    rbx, rbx
0x18001ffdf  jz      short loc_18002000B
0x18001ffe1  cmp     dword ptr [rbx+78h], 0
0x18001ffe5  jz      short loc_18001FFF1
0x18001ffe7  lea     rcx, [rbx+18h]; Resource
0x18001ffeb  call    cs:__imp_RtlDeleteResource
0x18001fff1  mov     rcx, rbx; Block
0x18001fff4  mov     dword ptr [rbx+78h], 0
0x18001fffb  call    ??3@YAXPEAX@Z
0x180020000  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, 0
0x18002000b  mov     rcx, cs:?g_OpsMonitorTimeQueue@COpsMonitorBase@@0PEAXEA; TimerQueue
0x180020012  test    rcx, rcx
0x180020015  jz      short loc_18002005F
0x180020017  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002001b  call    cs:__imp_DeleteTimerQueueEx
0x180020021  test    eax, eax
0x180020023  jnz     short loc_180020054
0x180020025  call    cs:__imp_GetLastError
0x18002002b  test    eax, eax
0x18002002d  jle     short loc_180020037
0x18002002f  movzx   eax, ax
0x180020032  or      eax, 80070000h
0x180020037  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 40h
0x18002003e  jz      short loc_180020054
0x180020040  mov     r8d, eax
0x180020043  lea     rdx, aCopsmonitorbas_0
0x18002004a  mov     ecx, 2; int
0x18002004f  call    ?_DbgPrintMessage@@YAXHPEBDZZ
0x180020054  mov     cs:?g_OpsMonitorTimeQueue@COpsMonitorBase@@0PEAXEA, 0
0x18002005f  mov     rbx, [rsp+28h+arg_0]
0x180020064  add     rsp, 20h
0x180020068  pop     rdi
0x180020069  retn
```
