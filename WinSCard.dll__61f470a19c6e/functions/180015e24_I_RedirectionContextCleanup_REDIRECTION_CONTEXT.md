# I_RedirectionContextCleanup(_REDIRECTION_CONTEXT *)

- ea: `0x180015e24`
- end: `0x180016037`
- name: `?I_RedirectionContextCleanup@@YAXPEAU_REDIRECTION_CONTEXT@@@Z`
- size: `531`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180015dc0`
- `0x180016a4c`
- `0x1800176a0`

## callees

- `0x180007bc0`
- `0x180015e24`
- `0x180016040`
- `0x18001991c`
- `0x180019990`
- `0x1800239b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015fe0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015fe0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015fee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015fee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180015eeb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180015eeb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180015ede`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180015ede`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015faa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015fcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015fda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015faa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015fbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015fcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015fda`
- `ntdll!RtlDeleteCriticalSection` at `0x180015f68`
- `ntdll!RtlDeleteCriticalSection` at `0x180015f68`
- `ntdll!RtlDllShutdownInProgress` at `0x180015ec6`
- `ntdll!RtlDllShutdownInProgress` at `0x180015ec6`
- `WINSTA!WinStationUnRegisterNotificationEvent` at `0x180015f26`
- `WINSTA!WinStationUnRegisterNotificationEvent` at `0x180015f26`

## pseudocode

```c
void __fastcall I_RedirectionContextCleanup(LPCRITICAL_SECTION lpCriticalSection)
{
  PVOID v2; // rcx
  int v3; // r9d
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  void *v5; // rcx
  HANDLE OwningThread; // rcx
  HANDLE LockSemaphore; // rcx
  void *v8; // rcx
  void *v9; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v10; // rcx
  HANDLE v11; // rcx
  HANDLE ProcessHeap; // rax
  __int64 v13; // rcx

  WppTraceIndent(lpCriticalSection, 0);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
  }
  if ( lpCriticalSection )
  {
    WppTraceIndent(v2, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
        v3,
        lpCriticalSection[1].SpinCount);
    }
    I_RedirectionContextCancelAndCloseRdpdr(lpCriticalSection);
    if ( lpCriticalSection[4].SpinCount && !RtlDllShutdownInProgress() )
    {
      CloseThreadpoolCleanupGroupMembers((PTP_CLEANUP_GROUP)lpCriticalSection[4].SpinCount, 1, 0);
      CloseThreadpoolCleanupGroup((PTP_CLEANUP_GROUP)lpCriticalSection[4].SpinCount);
    }
    if ( (unsigned int)IsForceWinStationUnRegisterNotificationEventCallEnabled() )
    {
      DebugInfo = lpCriticalSection[3].DebugInfo;
      if ( !DebugInfo || NtCurrentTeb()->ClientId.UniqueThread == NtCurrentPeb()->LoaderLock->OwningThread )
      {
        WppTraceIndent(DebugInfo, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
        }
      }
      else
      {
        WinStationUnRegisterNotificationEvent();
      }
    }
    RtlDeleteCriticalSection(lpCriticalSection);
    v5 = *(void **)&lpCriticalSection[3].LockCount;
    if ( v5 )
      CloseHandle(v5);
    OwningThread = lpCriticalSection[3].OwningThread;
    if ( OwningThread )
      CloseHandle(OwningThread);
    LockSemaphore = lpCriticalSection[2].LockSemaphore;
    if ( LockSemaphore )
      CloseHandle(LockSemaphore);
    v8 = *(void **)&lpCriticalSection[2].LockCount;
    if ( v8 )
      CloseHandle(v8);
    v9 = *(void **)&lpCriticalSection[4].LockCount;
    if ( v9 )
      CloseHandle(v9);
    v10 = lpCriticalSection[2].DebugInfo;
    if ( v10 )
      CloseHandle(v10);
    v11 = lpCriticalSection[1].OwningThread;
    if ( v11 )
      CloseHandle(v11);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpCriticalSection);
    WppTraceIndent(v13, 1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x180015e24  mov     [rsp+arg_0], rbx
0x180015e29  push    r14
0x180015e2b  sub     rsp, 30h
0x180015e2f  xor     edx, edx
0x180015e31  mov     rbx, rcx
0x180015e34  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180015e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e40  lea     r14, WPP_GLOBAL_Control
0x180015e47  cmp     rcx, r14
0x180015e4a  jz      short loc_180015E6D
0x180015e4c  test    byte ptr [rcx+1Ch], 2
0x180015e50  jz      short loc_180015E6D
0x180015e52  cmp     byte ptr [rcx+19h], 5
0x180015e56  jb      short loc_180015E6D
0x180015e58  mov     rcx, [rcx+10h]
0x180015e5c  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180015e63  mov     edx, 0Dh
0x180015e68  call    WPP_SF_s
0x180015e6d  test    rbx, rbx
0x180015e70  jz      loc_18001602B
0x180015e76  mov     edx, 2
0x180015e7b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180015e80  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e87  cmp     rcx, r14
0x180015e8a  jz      short loc_180015EB4
0x180015e8c  test    byte ptr [rcx+1Ch], 4
0x180015e90  jz      short loc_180015EB4
0x180015e92  cmp     byte ptr [rcx+19h], 4
0x180015e96  jb      short loc_180015EB4
0x180015e98  mov     eax, [rbx+48h]
0x180015e9b  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180015ea2  mov     rcx, [rcx+10h]
0x180015ea6  mov     edx, 0Eh
0x180015eab  mov     [rsp+38h+var_18], eax
0x180015eaf  call    WPP_SF_sd
0x180015eb4  mov     rcx, rbx; lpCriticalSection
0x180015eb7  call    ?I_RedirectionContextCancelAndCloseRdpdr@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; I_RedirectionContextCancelAndCloseRdpdr(_REDIRECTION_CONTEXT *)
0x180015ebc  cmp     qword ptr [rbx+0C0h], 0
0x180015ec4  jz      short loc_180015EF1
0x180015ec6  call    cs:__imp_RtlDllShutdownInProgress
0x180015ecc  test    al, al
0x180015ece  jnz     short loc_180015EF1
0x180015ed0  mov     rcx, [rbx+0C0h]; ptpcg
0x180015ed7  xor     r8d, r8d; pvCleanupContext
0x180015eda  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180015ede  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180015ee4  mov     rcx, [rbx+0C0h]; ptpcg
0x180015eeb  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180015ef1  call    ?IsForceWinStationUnRegisterNotificationEventCallEnabled@@YAHXZ; IsForceWinStationUnRegisterNotificationEventCallEnabled(void)
0x180015ef6  test    eax, eax
0x180015ef8  jz      short loc_180015F65
0x180015efa  mov     rcx, [rbx+78h]
0x180015efe  test    rcx, rcx
0x180015f01  jz      short loc_180015F2E
0x180015f03  mov     rax, gs:60h
0x180015f0c  mov     rdx, gs:30h
0x180015f15  mov     rax, [rax+110h]
0x180015f1c  mov     rax, [rax+10h]
0x180015f20  cmp     [rdx+48h], rax
0x180015f24  jz      short loc_180015F2E
0x180015f26  call    cs:__imp_WinStationUnRegisterNotificationEvent
0x180015f2c  jmp     short loc_180015F65
0x180015f2e  mov     edx, 2
0x180015f33  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180015f38  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f3f  cmp     rcx, r14
0x180015f42  jz      short loc_180015F65
0x180015f44  test    byte ptr [rcx+1Ch], 4
0x180015f48  jz      short loc_180015F65
0x180015f4a  cmp     byte ptr [rcx+19h], 4
0x180015f4e  jb      short loc_180015F65
0x180015f50  mov     rcx, [rcx+10h]
0x180015f54  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180015f5b  mov     edx, 0Fh
0x180015f60  call    WPP_SF_s
0x180015f65  mov     rcx, rbx; CriticalSection
0x180015f68  call    cs:__imp_RtlDeleteCriticalSection
0x180015f6e  mov     rcx, [rbx+80h]; hObject
0x180015f75  test    rcx, rcx
0x180015f78  jz      short loc_180015F80
0x180015f7a  call    cs:__imp_CloseHandle
0x180015f80  mov     rcx, [rbx+88h]; hObject
0x180015f87  test    rcx, rcx
0x180015f8a  jz      short loc_180015F92
0x180015f8c  call    cs:__imp_CloseHandle
0x180015f92  mov     rcx, [rbx+68h]; hObject
0x180015f96  test    rcx, rcx
0x180015f99  jz      short loc_180015FA1
0x180015f9b  call    cs:__imp_CloseHandle
0x180015fa1  mov     rcx, [rbx+58h]; hObject
0x180015fa5  test    rcx, rcx
0x180015fa8  jz      short loc_180015FB0
0x180015faa  call    cs:__imp_CloseHandle
0x180015fb0  mov     rcx, [rbx+0A8h]; hObject
0x180015fb7  test    rcx, rcx
0x180015fba  jz      short loc_180015FC2
0x180015fbc  call    cs:__imp_CloseHandle
0x180015fc2  mov     rcx, [rbx+50h]; hObject
0x180015fc6  test    rcx, rcx
0x180015fc9  jz      short loc_180015FD1
0x180015fcb  call    cs:__imp_CloseHandle
0x180015fd1  mov     rcx, [rbx+38h]; hObject
0x180015fd5  test    rcx, rcx
0x180015fd8  jz      short loc_180015FE0
0x180015fda  call    cs:__imp_CloseHandle
0x180015fe0  call    cs:__imp_GetProcessHeap
0x180015fe6  mov     r8, rbx; lpMem
0x180015fe9  xor     edx, edx; dwFlags
0x180015feb  mov     rcx, rax; hHeap
0x180015fee  call    cs:__imp_HeapFree
0x180015ff4  mov     edx, 1
0x180015ff9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180015ffe  mov     rcx, cs:WPP_GLOBAL_Control
0x180016005  cmp     rcx, r14
0x180016008  jz      short loc_18001602B
0x18001600a  test    byte ptr [rcx+1Ch], 2
0x18001600e  jz      short loc_18001602B
0x180016010  cmp     byte ptr [rcx+19h], 5
0x180016014  jb      short loc_18001602B
0x180016016  mov     rcx, [rcx+10h]
0x18001601a  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180016021  mov     edx, 10h
0x180016026  call    WPP_SF_s
0x18001602b  mov     rbx, [rsp+38h+arg_0]
0x180016030  add     rsp, 30h
0x180016034  pop     r14
0x180016036  retn
```
