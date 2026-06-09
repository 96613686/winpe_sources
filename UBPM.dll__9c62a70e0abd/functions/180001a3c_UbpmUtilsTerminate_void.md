# UbpmUtilsTerminate(void)

- ea: `0x180001a3c`
- end: `0x180001beb`
- name: `?UbpmUtilsTerminate@@YAXXZ`
- size: `431`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180001880`

## callees

- `0x180001a3c`
- `0x180001bf4`
- `0x18000fbf0`
- `0x1800103c0`
- `0x180032acc`
- `0x180036c60`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001b22`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001b22`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180001a89`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180001a89`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180001ad3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180001ad3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180001a76`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180001a76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001bc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001bc3`

## pseudocode

```c
void UbpmUtilsTerminate(void)
{
  __int64 v0; // rdx
  __int64 v1; // r8
  __int64 v2; // r9
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int i; // ebx
  __int64 v7; // rcx

  UbpmUninitializeMaintenance();
  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_TpSubmitLock);
  if ( g_pCleanupGroup )
  {
    CloseThreadpoolCleanupGroupMembers(g_pCleanupGroup, 1, 0);
    CloseThreadpoolCleanupGroup(g_pCleanupGroup);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids);
    g_pCleanupGroup = 0;
  }
  if ( g_pThreadpool )
  {
    CloseThreadpool(g_pThreadpool);
    g_pThreadpool = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids);
  }
  dword_18004FB80 = 0;
  RtlReleaseSRWLockExclusive(&g_TpSubmitLock);
  UbpmSystemInterfaceCleanup();
  if ( g_CriticalTasks )
    UBPM_MIDL_user_free(g_CriticalTasks, v0, v1, v2);
  if ( g_CriticalMaintenanceTasks )
    UBPM_MIDL_user_free(g_CriticalMaintenanceTasks, v0, v1, v2);
  if ( g_OOBEExemptedTasks )
    UBPM_MIDL_user_free(g_OOBEExemptedTasks, v0, v1, v2);
  if ( g_CriticalMeasuredTasks )
    UBPM_MIDL_user_free(g_CriticalMeasuredTasks, v0, v1, v2);
  UBPM_MIDL_user_free(*(_QWORD *)&g_pCriticalActions.Data1, v0, v1, v2);
  for ( i = 0; i < 5; ++i )
  {
    v7 = **((_QWORD **)&g_SidData.Revision + 2 * (int)i);
    if ( v7 )
    {
      UBPM_MIDL_user_free(v7, v3, v4, v5);
      **((_QWORD **)&g_SidData.Revision + 2 * (int)i) = 0;
    }
  }
  if ( g_Globals )
  {
    CloseHandle(g_Globals);
    g_Globals = 0;
  }
}

```

## disassembly

```asm
0x180001a3c  mov     [rsp+arg_0], rbx
0x180001a41  mov     [rsp+arg_8], rbp
0x180001a46  push    rdi
0x180001a47  sub     rsp, 20h
0x180001a4b  call    UbpmUninitializeMaintenance
0x180001a50  lea     rcx, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; struct _UBPM_SRWLOCK *
0x180001a57  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180001a5c  mov     rcx, cs:?g_pCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180001a63  lea     rbx, WPP_GLOBAL_Control
0x180001a6a  test    rcx, rcx
0x180001a6d  jz      short loc_180001AC7
0x180001a6f  xor     r8d, r8d; pvCleanupContext
0x180001a72  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180001a76  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180001a7d  nop     dword ptr [rax+rax+00h]
0x180001a82  mov     rcx, cs:?g_pCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180001a89  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180001a90  nop     dword ptr [rax+rax+00h]
0x180001a95  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a9c  cmp     rcx, rbx
0x180001a9f  jz      short loc_180001ABC
0x180001aa1  test    byte ptr [rcx+1Ch], 4
0x180001aa5  jz      short loc_180001ABC
0x180001aa7  mov     rcx, [rcx+10h]
0x180001aab  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180001ab2  mov     edx, 11h
0x180001ab7  call    WPP_SF_
0x180001abc  mov     cs:?g_pCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, 0; _TP_CLEANUP_GROUP * g_pCleanupGroup
0x180001ac7  mov     rcx, cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA; ptpp
0x180001ace  test    rcx, rcx
0x180001ad1  jz      short loc_180001B11
0x180001ad3  call    cs:__imp_CloseThreadpool
0x180001ada  nop     dword ptr [rax+rax+00h]
0x180001adf  mov     cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA, 0; _TP_POOL * g_pThreadpool
0x180001aea  mov     rcx, cs:WPP_GLOBAL_Control
0x180001af1  cmp     rcx, rbx
0x180001af4  jz      short loc_180001B11
0x180001af6  test    byte ptr [rcx+1Ch], 4
0x180001afa  jz      short loc_180001B11
0x180001afc  mov     rcx, [rcx+10h]
0x180001b00  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180001b07  mov     edx, 12h
0x180001b0c  call    WPP_SF_
0x180001b11  lea     rcx, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TpSubmitLock
0x180001b18  mov     cs:dword_18004FB80, 0
0x180001b22  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001b29  nop     dword ptr [rax+rax+00h]
0x180001b2e  call    ?UbpmSystemInterfaceCleanup@@YAXXZ; UbpmSystemInterfaceCleanup(void)
0x180001b33  mov     rcx, cs:?g_CriticalTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_CriticalTasks
0x180001b3a  test    rcx, rcx
0x180001b3d  jz      short loc_180001B44
0x180001b3f  call    UBPM_MIDL_user_free
0x180001b44  mov     rcx, cs:?g_CriticalMaintenanceTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_CriticalMaintenanceTasks
0x180001b4b  test    rcx, rcx
0x180001b4e  jz      short loc_180001B55
0x180001b50  call    UBPM_MIDL_user_free
0x180001b55  mov     rcx, cs:?g_OOBEExemptedTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_OOBEExemptedTasks
0x180001b5c  test    rcx, rcx
0x180001b5f  jz      short loc_180001B66
0x180001b61  call    UBPM_MIDL_user_free
0x180001b66  mov     rcx, cs:?g_CriticalMeasuredTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_CriticalMeasuredTasks
0x180001b6d  test    rcx, rcx
0x180001b70  jz      short loc_180001B77
0x180001b72  call    UBPM_MIDL_user_free
0x180001b77  mov     rcx, qword ptr cs:?g_pCriticalActions@@3PEAU_GUID@@EA.Data1; _GUID * g_pCriticalActions ...
0x180001b7e  call    UBPM_MIDL_user_free
0x180001b83  xor     ebx, ebx
0x180001b85  movsxd  rdi, ebx
0x180001b88  lea     rbp, ?g_SidData@@3PAU_SID_DATA@@A; _SID_DATA near * g_SidData
0x180001b8f  add     rdi, rdi
0x180001b92  mov     rax, [rbp+rdi*8+0]
0x180001b97  mov     rcx, [rax]
0x180001b9a  test    rcx, rcx
0x180001b9d  jz      short loc_180001BB0
0x180001b9f  call    UBPM_MIDL_user_free
0x180001ba4  mov     rax, [rbp+rdi*8+0]
0x180001ba9  mov     qword ptr [rax], 0
0x180001bb0  inc     ebx
0x180001bb2  cmp     ebx, 5
0x180001bb5  jb      short loc_180001B85
0x180001bb7  mov     rcx, cs:?g_Globals@@3U_UBPM_GLOBAL_DATA@@A; hObject
0x180001bbe  test    rcx, rcx
0x180001bc1  jz      short loc_180001BDA
0x180001bc3  call    cs:__imp_CloseHandle
0x180001bca  nop     dword ptr [rax+rax+00h]
0x180001bcf  mov     cs:?g_Globals@@3U_UBPM_GLOBAL_DATA@@A, 0; _UBPM_GLOBAL_DATA g_Globals
0x180001bda  mov     rbx, [rsp+28h+arg_0]
0x180001bdf  mov     rbp, [rsp+28h+arg_8]
0x180001be4  add     rsp, 20h
0x180001be8  pop     rdi
0x180001be9  retn
```
