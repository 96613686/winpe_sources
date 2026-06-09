# StopService(void *,uchar)

- ea: `0x180003450`
- end: `0x180003550`
- name: `?StopService@@YAXPEAXE@Z`
- size: `256`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180003150`

## callees

- `0x180002a88`
- `0x180003450`
- `0x180003570`
- `0x180003e00`
- `0x180015114`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800034ed`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800034ed`

## pseudocode

```c
void __fastcall StopService(void *a1)
{
  signed __int32 v1; // eax
  signed __int32 v2; // ett

  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_(1026, 16, WPP_fd30cb189484364f2633d135959507bb_Traceguids);
  if ( !_InterlockedExchange((volatile __int32 *)&g_fStopFlag, 1) )
  {
    ServiceStatus.dwCurrentState = 3;
    ServiceStatus.dwCheckPoint = 1;
    ServiceStatus.dwWaitHint = 1000;
    UpdateStatus();
    if ( (g_InitState & 4) != 0 )
      Rpc_Shutdown();
    CleanupZtdns();
    if ( g_hRegisteredStopServiceEvent )
    {
      _m_prefetchw((const void *)&g_InitState);
      v1 = g_InitState;
      do
      {
        v2 = v1;
        v1 = _InterlockedCompareExchange(&g_InitState, v1, v1);
      }
      while ( v2 != v1 );
      if ( (v1 & 2) != 0 )
        UnregisterWaitEx(g_hRegisteredStopServiceEvent, 0);
    }
    _InterlockedAnd(&g_InitState, 0xFFFFFFFD);
    g_hRegisteredStopServiceEvent = 0;
    *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
    *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
    *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    UpdateStatus();
    if ( (xmmword_18001F260 & 4) != 0 )
      WPP_SF_(1026, 17, WPP_fd30cb189484364f2633d135959507bb_Traceguids);
  }
}

```

## disassembly

```asm
0x180003450  sub     rsp, 28h
0x180003454  test    byte ptr cs:xmmword_18001F260, 4
0x18000345b  jz      short loc_180003473
0x18000345d  mov     edx, 10h
0x180003462  lea     r8, WPP_fd30cb189484364f2633d135959507bb_Traceguids
0x180003469  mov     ecx, 402h
0x18000346e  call    WPP_SF_
0x180003473  mov     eax, 1
0x180003478  xchg    eax, cs:?g_fStopFlag@@3KC; ulong volatile g_fStopFlag
0x18000347e  test    eax, eax
0x180003480  jnz     loc_18000354B
0x180003486  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS ServiceStatus ...
0x180003490  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 1; _SERVICE_STATUS ServiceStatus ...
0x18000349a  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 3E8h; _SERVICE_STATUS ServiceStatus ...
0x1800034a4  call    ?UpdateStatus@@YAKXZ; UpdateStatus(void)
0x1800034a9  mov     eax, cs:?g_InitState@@3JC; long volatile g_InitState
0x1800034af  test    al, 4
0x1800034b1  jz      short loc_1800034B8
0x1800034b3  call    ?Rpc_Shutdown@@YAXXZ; Rpc_Shutdown(void)
0x1800034b8  call    CleanupZtdns
0x1800034bd  cmp     cs:?g_hRegisteredStopServiceEvent@@3PEAXEA, 0; void * g_hRegisteredStopServiceEvent
0x1800034c5  jz      short loc_1800034F3
0x1800034c7  prefetchw byte ptr cs:?g_InitState@@3JC; long volatile g_InitState
0x1800034ce  mov     eax, cs:?g_InitState@@3JC; long volatile g_InitState
0x1800034d4  mov     ecx, eax
0x1800034d6  lock cmpxchg cs:?g_InitState@@3JC, ecx; long volatile g_InitState
0x1800034de  jnz     short loc_1800034D4
0x1800034e0  test    al, 2
0x1800034e2  jz      short loc_1800034F3
0x1800034e4  mov     rcx, cs:?g_hRegisteredStopServiceEvent@@3PEAXEA; WaitHandle
0x1800034eb  xor     edx, edx; CompletionEvent
0x1800034ed  call    cs:__imp_UnregisterWaitEx
0x1800034f3  lock and cs:?g_InitState@@3JC, 0FFFFFFFDh; long volatile g_InitState
0x1800034fb  mov     cs:?g_hRegisteredStopServiceEvent@@3PEAXEA, 0; void * g_hRegisteredStopServiceEvent
0x180003506  mov     qword ptr cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS ServiceStatus ...
0x180003511  mov     qword ptr cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS ServiceStatus ...
0x18000351c  mov     qword ptr cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS ServiceStatus ...
0x180003527  call    ?UpdateStatus@@YAKXZ; UpdateStatus(void)
0x18000352c  test    byte ptr cs:xmmword_18001F260, 4
0x180003533  jz      short loc_18000354B
0x180003535  mov     edx, 11h
0x18000353a  lea     r8, WPP_fd30cb189484364f2633d135959507bb_Traceguids
0x180003541  mov     ecx, 402h
0x180003546  call    WPP_SF_
0x18000354b  add     rsp, 28h
0x18000354f  retn
```
