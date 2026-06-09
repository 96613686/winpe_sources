# DrvQueryDisplayConfigAndLeaveUserCrit

- ea: `0x140010e18`
- end: `0x14001106c`
- name: `DrvQueryDisplayConfigAndLeaveUserCrit`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002a520`

## callees

- `0x140010d88`
- `0x140010e18`
- `0x1400112a8`
- `0x140012c80`
- `0x140013ff0`
- `0x14001cb70`
- `0x140028974`
- `0x1400c8bac`
- `0x140117980`
- `0x140190650`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetThreadWin32Thread` at `0x140010f2e`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140010f2e`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010f8d`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140010f8d`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140010f7e`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140010f7e`
- `ntoskrnl!KeIsAttachedProcess` at `0x140010f1b`
- `ntoskrnl!KeIsAttachedProcess` at `0x140010f1b`
- `watchdog!WdLogSingleEntry1` at `0x140010e89`
- `watchdog!WdLogSingleEntry1` at `0x140010ee5`
- `watchdog!WdLogSingleEntry1` at `0x140010e89`
- `watchdog!WdLogSingleEntry1` at `0x140010ee5`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140010eae`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140010eae`
- `WIN32K!W32GetSessionState` at `0x140010e3f`
- `WIN32K!W32GetSessionState` at `0x140010e3f`

## pseudocode

```c
__int64 __fastcall DrvQueryDisplayConfigAndLeaveUserCrit(
        __int64 a1,
        unsigned int *a2,
        struct DISPLAYCONFIG_PATH_INFO_INTERNAL *a3,
        enum DISPLAYCONFIG_TOPOLOGY_ID *a4)
{
  __int64 v4; // rbx
  bool v8; // di
  __int64 SessionState; // rax
  int v10; // r8d
  const wchar_t *v11; // rcx
  _DWORD *v12; // r14
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 DxgkWin32kInterface; // rax
  int v17; // esi
  int v18; // ecx
  int v19; // r8d
  __int64 v20; // rbp
  struct _KTHREAD *CurrentThread; // r14
  __int64 v22; // rdi
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 *ThreadWin32Thread; // rax
  __int64 v27; // rax
  __int64 v28; // rdi
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  bool v33; // [rsp+28h] [rbp-40h]
  unsigned int v34; // [rsp+70h] [rbp+8h] BYREF

  v4 = (unsigned int)a1;
  v8 = (a1 & 7) != 4 || (unsigned int)DispBrokerGetCurrentMode() != 3 && (unsigned int)DispBrokerGetCurrentMode() != 2;
  SessionState = W32GetSessionState(a1);
  v11 = L"DynamicModeChange";
  v12 = *(_DWORD **)(SessionState + 88);
  if ( v8 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        (unsigned int)L"DynamicModeChange",
        (unsigned int)&LockAcquireShared,
        v10,
        *v12 + 624,
        (__int64)L"DynamicModeChange");
    EngAcquireSemaphoreShared((HSEMAPHORE)(*(_QWORD *)v12 + 624LL));
    GrepAcquireLockValidate<1>();
  }
  UserSessionSwitchLeaveCritWithNonPaged(v11);
  WdLogSingleEntry1(4, v4);
  WdLogGlobalForLineNumber = 12077;
  if ( (unsigned __int8)DrvIsQdcHandledByDispBroker((unsigned int)v4) )
  {
    if ( (unsigned int)DispBrokerGetCurrentMode() == 3 )
    {
      v34 = *a2;
      v17 = DispBrokerQueryDisplayConfig(v4 & 0xFFFFFFEF, v4 & 0x10, &v34, a3, a4, v33);
      if ( v17 >= 0 )
        *a2 = v34;
    }
    else
    {
      v17 = -1073741790;
    }
  }
  else
  {
    DxgkWin32kInterface = DxDdGetDxgkWin32kInterface(v14, v13, v15);
    v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *, struct DISPLAYCONFIG_PATH_INFO_INTERNAL *, enum DISPLAYCONFIG_TOPOLOGY_ID *))(DxgkWin32kInterface + 216))(
            (unsigned int)v4 & 0xFFFFFFEF,
            v4 & 0x10,
            a2,
            a3,
            a4);
  }
  WdLogSingleEntry1(4, v17);
  WdLogGlobalForLineNumber = 12114;
  if ( v8 )
  {
    v20 = *(_QWORD *)v12;
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(v18, (unsigned int)&LockRelease, v19, v20 + 624, (__int64)L"DynamicModeChange");
    CurrentThread = KeGetCurrentThread();
    v22 = 0;
    if ( !(unsigned __int8)KeIsAttachedProcess()
      || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v24, v23, v25),
          CurrentThreadProcess = PsGetCurrentThreadProcess(),
          CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
    {
      ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
      if ( ThreadWin32Thread )
        v22 = *ThreadWin32Thread;
    }
    v27 = v22 + 8;
    v28 = -v22;
    if ( (v27 & -(__int64)(v28 != 0)) != 0 && (*(_BYTE *)((v27 & -(__int64)(v28 != 0)) + 9))-- == 1 )
      *(_QWORD *)(v27 & -(__int64)(v28 != 0)) &= ~2uLL;
    GreReleaseSemaphoreSharedInternal((HSEMAPHORE)(v20 + 624));
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140010e18  push    rbx
0x140010e1a  push    rbp
0x140010e1b  push    rsi
0x140010e1c  push    rdi
0x140010e1d  push    r14
0x140010e1f  push    r15
0x140010e21  sub     rsp, 38h
0x140010e25  mov     eax, ecx
0x140010e27  mov     ebx, ecx
0x140010e29  and     al, 7
0x140010e2b  mov     rsi, r9
0x140010e2e  mov     rbp, r8
0x140010e31  mov     r15, rdx
0x140010e34  cmp     al, 4
0x140010e36  jz      loc_140010F9F
0x140010e3c  mov     dil, 1
0x140010e3f  call    cs:__imp_W32GetSessionState
0x140010e46  nop     dword ptr [rax+rax+00h]
0x140010e4b  lea     rcx, aDynamicmodecha; "DynamicModeChange"
0x140010e52  mov     r14, [rax+58h]
0x140010e56  test    dil, dil
0x140010e59  jz      short loc_140010E7C
0x140010e5b  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x140010e62  jnz     loc_140010FC1
0x140010e68  mov     rcx, [r14]
0x140010e6b  add     rcx, 270h; hsem
0x140010e72  call    EngAcquireSemaphoreShared
0x140010e77  call    ??$GrepAcquireLockValidate@$00@@YAXXZ; GrepAcquireLockValidate<1>(void)
0x140010e7c  call    UserSessionSwitchLeaveCritWithNonPaged
0x140010e81  mov     rdx, rbx
0x140010e84  mov     ecx, 4
0x140010e89  call    cs:__imp_WdLogSingleEntry1
0x140010e90  nop     dword ptr [rax+rax+00h]
0x140010e95  mov     ecx, ebx
0x140010e97  mov     cs:WdLogGlobalForLineNumber, 2F2Dh
0x140010ea1  call    DrvIsQdcHandledByDispBroker
0x140010ea6  test    al, al
0x140010ea8  jnz     loc_140010FEE
0x140010eae  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x140010eb5  nop     dword ptr [rax+rax+00h]
0x140010eba  mov     edx, ebx
0x140010ebc  mov     [rsp+68h+var_48], rsi
0x140010ec1  and     ebx, 0FFFFFFEFh
0x140010ec4  and     edx, 10h
0x140010ec7  mov     r9, rbp
0x140010eca  mov     r8, r15
0x140010ecd  mov     rax, [rax+0D8h]
0x140010ed4  mov     ecx, ebx
0x140010ed6  call    _guard_dispatch_icall
0x140010edb  mov     esi, eax
0x140010edd  movsxd  rdx, esi
0x140010ee0  mov     ecx, 4
0x140010ee5  call    cs:__imp_WdLogSingleEntry1
0x140010eec  nop     dword ptr [rax+rax+00h]
0x140010ef1  mov     cs:WdLogGlobalForLineNumber, 2F52h
0x140010efb  test    dil, dil
0x140010efe  jz      short loc_140010F67
0x140010f00  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x140010f07  mov     rbp, [r14]
0x140010f0a  jnz     loc_14001103B
0x140010f10  mov     r14, gs:188h
0x140010f19  xor     edi, edi
0x140010f1b  call    cs:__imp_KeIsAttachedProcess
0x140010f22  nop     dword ptr [rax+rax+00h]
0x140010f27  test    al, al
0x140010f29  jnz     short loc_140010F77
0x140010f2b  mov     rcx, r14
0x140010f2e  call    cs:__imp_PsGetThreadWin32Thread
0x140010f35  nop     dword ptr [rax+rax+00h]
0x140010f3a  test    rax, rax
0x140010f3d  jz      short loc_140010F42
0x140010f3f  mov     rdi, [rax]
0x140010f42  lea     rax, [rdi+8]
0x140010f46  neg     rdi
0x140010f49  sbb     rdx, rdx
0x140010f4c  and     rdx, rax
0x140010f4f  jz      short loc_140010F5B
0x140010f51  add     byte ptr [rdx+9], 0FFh
0x140010f55  jnz     short loc_140010F5B
0x140010f57  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFDh
0x140010f5b  lea     rcx, [rbp+270h]; HSEMAPHORE
0x140010f62  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140010f67  mov     eax, esi
0x140010f69  add     rsp, 38h
0x140010f6d  pop     r15
0x140010f6f  pop     r14
0x140010f71  pop     rdi
0x140010f72  pop     rsi
0x140010f73  pop     rbp
0x140010f74  pop     rbx
0x140010f75  retn
0x140010f77  call    W32GetCurrentWin32kSessionId
0x140010f7c  mov     ebx, eax
0x140010f7e  call    cs:__imp_PsGetCurrentThreadProcess
0x140010f85  nop     dword ptr [rax+rax+00h]
0x140010f8a  mov     rcx, rax
0x140010f8d  call    cs:__imp_PsGetProcessSessionIdEx
0x140010f94  nop     dword ptr [rax+rax+00h]
0x140010f99  cmp     ebx, eax
0x140010f9b  jz      short loc_140010F2B
0x140010f9d  jmp     short loc_140010F42
0x140010f9f  call    DispBrokerGetCurrentMode
0x140010fa4  cmp     eax, 3
0x140010fa7  jnz     short loc_140010FB1
0x140010fa9  xor     dil, dil
0x140010fac  jmp     loc_140010E3F
0x140010fb1  call    DispBrokerGetCurrentMode
0x140010fb6  cmp     eax, 2
0x140010fb9  jnz     loc_140010E3C
0x140010fbf  jmp     short loc_140010FA9
0x140010fc1  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x140010fc8  jz      loc_140010E68
0x140010fce  mov     r9, [r14]
0x140010fd1  lea     rdx, LockAcquireShared
0x140010fd8  add     r9, 270h
0x140010fdf  mov     [rsp+68h+var_48], rcx
0x140010fe4  call    McTemplateK0pz_EtwWriteTransfer
0x140010fe9  jmp     loc_140010E68
0x140010fee  call    DispBrokerGetCurrentMode
0x140010ff3  cmp     eax, 3
0x140010ff6  jnz     short loc_140011031
0x140010ff8  mov     eax, [r15]
0x140010ffb  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x140011000  mov     edx, ebx
0x140011002  mov     [rsp+68h+arg_0], eax
0x140011006  and     ebx, 0FFFFFFEFh
0x140011009  mov     [rsp+68h+var_48], rsi; enum DISPLAYCONFIG_TOPOLOGY_ID *
0x14001100e  mov     ecx, ebx; unsigned int
0x140011010  and     edx, 10h; unsigned int
0x140011013  mov     r9, rbp; struct DISPLAYCONFIG_PATH_INFO_INTERNAL *
0x140011016  call    ?DispBrokerQueryDisplayConfig@@YAJIIPEAIPEAUDISPLAYCONFIG_PATH_INFO_INTERNAL@@PEAW4DISPLAYCONFIG_TOPOLOGY_ID@@_N@Z; DispBrokerQueryDisplayConfig(uint,uint,uint *,DISPLAYCONFIG_PATH_INFO_INTERNAL *,DISPLAYCONFIG_TOPOLOGY_ID *,bool)
0x14001101b  mov     esi, eax
0x14001101d  test    eax, eax
0x14001101f  js      loc_140010EDD
0x140011025  mov     ecx, [rsp+68h+arg_0]
0x140011029  mov     [r15], ecx
0x14001102c  jmp     loc_140010EDD
0x140011031  mov     esi, 0C0000022h
0x140011036  jmp     loc_140010EDD
0x14001103b  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x140011042  jz      loc_140010F10
0x140011048  lea     rax, aDynamicmodecha; "DynamicModeChange"
0x14001104f  lea     r9, [rbp+270h]
0x140011056  mov     [rsp+68h+var_48], rax
0x14001105b  lea     rdx, LockRelease
0x140011062  call    McTemplateK0pz_EtwWriteTransfer
0x140011067  jmp     loc_140010F10
```
