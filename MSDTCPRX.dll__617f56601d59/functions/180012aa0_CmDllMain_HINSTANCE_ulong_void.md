# CmDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x180012aa0`
- end: `0x180012b1f`
- name: `?CmDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `127`
- prototype: `__int64 __fastcall(HINSTANCE, int, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bf98`

## callees

- `0x180012aa0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012ac3`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012ac3`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180012abb`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180012abb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012ab2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180012ab2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180012b0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180012b0f`

## pseudocode

```c
__int64 __fastcall CmDllMain(HINSTANCE a1, int a2, void *a3)
{
  int v3; // edx
  HANDLE CurrentThread; // rax

  if ( a2 )
  {
    v3 = a2 - 1;
    if ( v3 )
    {
      if ( v3 == 1 )
      {
        CurrentThread = GetCurrentThread();
        GetThreadPriority(CurrentThread);
      }
    }
    else
    {
      DisableThreadLibraryCalls(a1);
      g_pCImpICmUisConn = 0;
      g_pIDtcTrace = 0;
      g_pIDtcCommStats = 0;
      g_fReportStatistics = 0;
      g_fShutDownAll = 0;
      g_fShutDownComplete = 0;
      GetSystemInfo(&g_SystemInfo);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180012aa0  sub     rsp, 28h
0x180012aa4  test    edx, edx
0x180012aa6  jz      short loc_180012B15
0x180012aa8  sub     edx, 1
0x180012aab  jz      short loc_180012AC3
0x180012aad  cmp     edx, 1
0x180012ab0  jnz     short loc_180012B15
0x180012ab2  call    cs:__imp_GetCurrentThread
0x180012ab8  mov     rcx, rax; hThread
0x180012abb  call    cs:__imp_GetThreadPriority
0x180012ac1  jmp     short loc_180012B15
0x180012ac3  call    cs:__imp_DisableThreadLibraryCalls
0x180012ac9  lea     rcx, ?g_SystemInfo@@3U_SYSTEM_INFO@@A; lpSystemInfo
0x180012ad0  mov     cs:?g_pCImpICmUisConn@@3PEAVCImpICmUisConn@@EA, 0; CImpICmUisConn * g_pCImpICmUisConn
0x180012adb  mov     cs:?g_pIDtcTrace@@3PEAUIDtcTrace@@EA, 0; IDtcTrace * g_pIDtcTrace
0x180012ae6  mov     cs:?g_pIDtcCommStats@@3PEAUIDtcCommStatistics@@EA, 0; IDtcCommStatistics * g_pIDtcCommStats
0x180012af1  mov     cs:?g_fReportStatistics@@3HA, 0; int g_fReportStatistics
0x180012afb  mov     cs:?g_fShutDownAll@@3HA, 0; int g_fShutDownAll
0x180012b05  mov     cs:?g_fShutDownComplete@@3HA, 0; int g_fShutDownComplete
0x180012b0f  call    cs:__imp_GetSystemInfo
0x180012b15  mov     eax, 1
0x180012b1a  add     rsp, 28h
0x180012b1e  retn
```
