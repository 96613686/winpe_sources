# PerfRegCleanup

- ea: `0x180022e70`
- end: `0x180022f68`
- name: `PerfRegCleanup`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180022d40`

## callees

- `0x180013f58`
- `0x180015b44`
- `0x180022e70`
- `0x180034254`
- `0x18003b57c`
- `0x18003b5fc`
- `0x18003b748`
- `0x180058cc8`

## import_xrefs

- `ntdll!RtlRunOnceBeginInitialize` at `0x180022e82`
- `ntdll!RtlRunOnceBeginInitialize` at `0x180022e82`
- `ntdll!RtlDllShutdownInProgress` at `0x180022f2c`
- `ntdll!RtlDllShutdownInProgress` at `0x180022f2c`
- `ntdll!RtlRunOnceInitialize` at `0x180022f58`
- `ntdll!RtlRunOnceInitialize` at `0x180022f58`
- `ntdll!RtlDeleteCriticalSection` at `0x180022f26`
- `ntdll!RtlDeleteCriticalSection` at `0x180022f26`
- `KERNEL32!CloseHandle` at `0x180022f02`
- `KERNEL32!CloseHandle` at `0x180022f02`

## pseudocode

```c
__int64 PerfRegCleanup()
{
  _QWORD *v0; // rcx

  if ( (int)RtlRunOnceBeginInitialize(qword_1800A3088, 1, 0) < 0 )
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
    TraceLoggingUnregister_EtwEventUnregister(&dword_18009F6E8);
    WppCleanupUm();
    RtlRunOnceInitialize(qword_1800A3088);
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
0x180022e70  sub     rsp, 28h
0x180022e74  xor     r8d, r8d
0x180022e77  lea     rcx, qword_1800A3088
0x180022e7e  lea     edx, [r8+1]
0x180022e82  call    cs:__imp_RtlRunOnceBeginInitialize
0x180022e88  test    eax, eax
0x180022e8a  js      loc_180022F5E
0x180022e90  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e97  test    byte ptr [rcx+1Ch], 1
0x180022e9b  jz      short loc_180022EBF
0x180022e9d  cmp     byte ptr [rcx+19h], 4
0x180022ea1  jb      short loc_180022EBF
0x180022ea3  mov     rcx, [rcx+10h]
0x180022ea7  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180022eae  mov     edx, 31h ; '1'
0x180022eb3  call    WPP_SF_
0x180022eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ebf  mov     rax, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x180022ec6  test    rax, rax
0x180022ec9  jz      short loc_180022F13
0x180022ecb  mov     r9d, cs:?NumberOfOpens@@3JA; long NumberOfOpens
0x180022ed2  test    r9d, r9d
0x180022ed5  jz      short loc_180022EFF
0x180022ed7  test    dword ptr [rcx+1Ch], 100h
0x180022ede  jz      short loc_180022EFB
0x180022ee0  cmp     byte ptr [rcx+19h], 3
0x180022ee4  jb      short loc_180022EFB
0x180022ee6  mov     rcx, [rcx+10h]
0x180022eea  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180022ef1  mov     edx, 32h ; '2'
0x180022ef6  call    WPP_SF_d
0x180022efb  xor     eax, eax
0x180022efd  jmp     short loc_180022F63
0x180022eff  mov     rcx, rax; hObject
0x180022f02  call    cs:__imp_CloseHandle
0x180022f08  mov     cs:?hGlobalDataMutex@@3PEAXEA, 0; void * hGlobalDataMutex
0x180022f13  lea     rcx, ?PerfpErrorLog@@3UERROR_LOG@@A; struct ERROR_LOG *
0x180022f1a  call    ?PerfpDeleteErrorLogs@@YAXPEAUERROR_LOG@@@Z; PerfpDeleteErrorLogs(ERROR_LOG *)
0x180022f1f  lea     rcx, ?PerfpCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180022f26  call    cs:__imp_RtlDeleteCriticalSection
0x180022f2c  call    cs:__imp_RtlDllShutdownInProgress
0x180022f32  test    al, al
0x180022f34  jnz     short loc_180022F3B
0x180022f36  call    ?CleanupRpcBindingHandle@@YAXXZ; CleanupRpcBindingHandle(void)
0x180022f3b  call    CleanupV2Resources
0x180022f40  lea     rcx, dword_18009F6E8
0x180022f47  call    TraceLoggingUnregister_EtwEventUnregister
0x180022f4c  call    WppCleanupUm
0x180022f51  lea     rcx, qword_1800A3088
0x180022f58  call    cs:__imp_RtlRunOnceInitialize
0x180022f5e  mov     eax, 1
0x180022f63  add     rsp, 28h
0x180022f67  retn
```
