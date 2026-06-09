# PerfRegCleanup

- ea: `0x180025620`
- end: `0x180025737`
- name: `PerfRegCleanup`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800254c0`

## callees

- `0x18000e9c0`
- `0x180022148`
- `0x180025620`
- `0x180037ef4`
- `0x18003fb18`
- `0x18003fba0`
- `0x18003fd04`
- `0x180064e88`

## import_xrefs

- `ntdll!RtlRunOnceBeginInitialize` at `0x180025632`
- `ntdll!RtlRunOnceBeginInitialize` at `0x180025632`
- `ntdll!RtlDllShutdownInProgress` at `0x1800256ee`
- `ntdll!RtlDllShutdownInProgress` at `0x1800256ee`
- `ntdll!RtlRunOnceInitialize` at `0x180025720`
- `ntdll!RtlRunOnceInitialize` at `0x180025720`
- `ntdll!RtlDeleteCriticalSection` at `0x1800256e2`
- `ntdll!RtlDeleteCriticalSection` at `0x1800256e2`
- `KERNEL32!CloseHandle` at `0x1800256b8`
- `KERNEL32!CloseHandle` at `0x1800256b8`

## pseudocode

```c
__int64 PerfRegCleanup()
{
  _QWORD *v0; // rcx

  if ( (int)RtlRunOnceBeginInitialize(qword_1800B21D0, 1) < 0 )
    return 1;
  v0 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( !hGlobalDataMutex )
  {
LABEL_12:
    PerfpDeleteErrorLogs(&PerfpErrorLog);
    RtlDeleteCriticalSection(&PerfpCritSect);
    if ( !RtlDllShutdownInProgress() )
      CleanupRpcBindingHandle();
    CleanupV2Resources();
    TraceLoggingUnregister_EtwEventUnregister(&dword_1800AE6E8);
    WppCleanupUm();
    RtlRunOnceInitialize(qword_1800B21D0);
    return 1;
  }
  if ( !NumberOfOpens )
  {
    CloseHandle(hGlobalDataMutex);
    hGlobalDataMutex = 0;
    goto LABEL_12;
  }
  if ( (*((_DWORD *)v0 + 7) & 0x100) != 0 && *((_BYTE *)v0 + 25) >= 3u )
    WPP_SF_d(v0[2], 50, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, (unsigned int)NumberOfOpens);
  return 0;
}

```

## disassembly

```asm
0x180025620  sub     rsp, 28h
0x180025624  xor     r8d, r8d
0x180025627  lea     rcx, qword_1800B21D0
0x18002562e  lea     edx, [r8+1]
0x180025632  call    cs:__imp_RtlRunOnceBeginInitialize
0x180025639  nop     dword ptr [rax+rax+00h]
0x18002563e  test    eax, eax
0x180025640  js      loc_18002572C
0x180025646  mov     rcx, cs:WPP_GLOBAL_Control
0x18002564d  test    byte ptr [rcx+1Ch], 1
0x180025651  jz      short loc_180025675
0x180025653  cmp     byte ptr [rcx+19h], 4
0x180025657  jb      short loc_180025675
0x180025659  mov     rcx, [rcx+10h]
0x18002565d  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180025664  mov     edx, 31h ; '1'
0x180025669  call    WPP_SF_
0x18002566e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025675  mov     rax, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x18002567c  test    rax, rax
0x18002567f  jz      short loc_1800256CF
0x180025681  mov     r9d, cs:?NumberOfOpens@@3JA; long NumberOfOpens
0x180025688  test    r9d, r9d
0x18002568b  jz      short loc_1800256B5
0x18002568d  test    dword ptr [rcx+1Ch], 100h
0x180025694  jz      short loc_1800256B1
0x180025696  cmp     byte ptr [rcx+19h], 3
0x18002569a  jb      short loc_1800256B1
0x18002569c  mov     rcx, [rcx+10h]
0x1800256a0  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x1800256a7  mov     edx, 32h ; '2'
0x1800256ac  call    WPP_SF_d
0x1800256b1  xor     eax, eax
0x1800256b3  jmp     short loc_180025731
0x1800256b5  mov     rcx, rax; hObject
0x1800256b8  call    cs:__imp_CloseHandle
0x1800256bf  nop     dword ptr [rax+rax+00h]
0x1800256c4  mov     cs:?hGlobalDataMutex@@3PEAXEA, 0; void * hGlobalDataMutex
0x1800256cf  lea     rcx, ?PerfpErrorLog@@3UERROR_LOG@@A; struct ERROR_LOG *
0x1800256d6  call    ?PerfpDeleteErrorLogs@@YAXPEAUERROR_LOG@@@Z; PerfpDeleteErrorLogs(ERROR_LOG *)
0x1800256db  lea     rcx, ?PerfpCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800256e2  call    cs:__imp_RtlDeleteCriticalSection
0x1800256e9  nop     dword ptr [rax+rax+00h]
0x1800256ee  call    cs:__imp_RtlDllShutdownInProgress
0x1800256f5  nop     dword ptr [rax+rax+00h]
0x1800256fa  test    al, al
0x1800256fc  jnz     short loc_180025703
0x1800256fe  call    ?CleanupRpcBindingHandle@@YAXXZ; CleanupRpcBindingHandle(void)
0x180025703  call    CleanupV2Resources
0x180025708  lea     rcx, dword_1800AE6E8
0x18002570f  call    TraceLoggingUnregister_EtwEventUnregister
0x180025714  call    WppCleanupUm
0x180025719  lea     rcx, qword_1800B21D0
0x180025720  call    cs:__imp_RtlRunOnceInitialize
0x180025727  nop     dword ptr [rax+rax+00h]
0x18002572c  mov     eax, 1
0x180025731  add     rsp, 28h
0x180025735  retn
```
