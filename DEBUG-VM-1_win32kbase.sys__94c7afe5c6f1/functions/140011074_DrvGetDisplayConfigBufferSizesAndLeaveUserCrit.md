# DrvGetDisplayConfigBufferSizesAndLeaveUserCrit

- ea: `0x140011074`
- end: `0x14001129f`
- name: `DrvGetDisplayConfigBufferSizesAndLeaveUserCrit`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002b850`

## callees

- `0x140010d88`
- `0x140011074`
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

- `ntoskrnl!PsGetThreadWin32Thread` at `0x140011174`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140011174`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400111d3`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400111d3`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400111c4`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400111c4`
- `ntoskrnl!KeIsAttachedProcess` at `0x140011161`
- `ntoskrnl!KeIsAttachedProcess` at `0x140011161`
- `watchdog!WdLogSingleEntry1` at `0x1400110e2`
- `watchdog!WdLogSingleEntry1` at `0x14001112b`
- `watchdog!WdLogSingleEntry1` at `0x1400110e2`
- `watchdog!WdLogSingleEntry1` at `0x14001112b`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140011107`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140011107`
- `WIN32K!W32GetSessionState` at `0x14001109b`
- `WIN32K!W32GetSessionState` at `0x14001109b`

## pseudocode

```c
__int64 __fastcall DrvGetDisplayConfigBufferSizesAndLeaveUserCrit(__int64 a1, unsigned int *a2)
{
  __int64 v2; // rbx
  bool v4; // di
  int v5; // ecx
  int v6; // r8d
  _DWORD *v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 DxgkWin32kInterface; // rax
  int v12; // esi
  int v13; // ecx
  int v14; // r8d
  __int64 v15; // rbp
  struct _KTHREAD *CurrentThread; // r14
  __int64 v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 *ThreadWin32Thread; // rax
  __int64 v22; // rax
  __int64 v23; // rdi
  int CurrentWin32kSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  int DisplayConfig; // eax
  bool v29; // [rsp+28h] [rbp-40h]

  v2 = (unsigned int)a1;
  v4 = (a1 & 7) != 4 || (unsigned int)DispBrokerGetCurrentMode() != 3 && (unsigned int)DispBrokerGetCurrentMode() != 2;
  v7 = *(_DWORD **)(W32GetSessionState(a1) + 88);
  if ( v4 )
  {
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(
        v5,
        (unsigned int)&LockAcquireShared,
        v6,
        *v7 + 624,
        (__int64)L"DynamicModeChange");
    EngAcquireSemaphoreShared((HSEMAPHORE)(*(_QWORD *)v7 + 624LL));
    GrepAcquireLockValidate<1>();
  }
  UserSessionSwitchLeaveCritWithNonPaged();
  WdLogSingleEntry1(4, v2);
  WdLogGlobalForLineNumber = 12000;
  if ( (unsigned __int8)DrvIsQdcHandledByDispBroker((unsigned int)v2) )
  {
    if ( (unsigned int)DispBrokerGetCurrentMode() == 3 )
    {
      DisplayConfig = DispBrokerQueryDisplayConfig(v2 & 0xFFFFFFEF, v2 & 0x10, a2, 0, 0, v29);
      v12 = 0;
      if ( DisplayConfig != -1073741789 )
        v12 = DisplayConfig;
    }
    else
    {
      v12 = -1073741790;
    }
  }
  else
  {
    DxgkWin32kInterface = DxDdGetDxgkWin32kInterface(v9, v8, v10);
    v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(DxgkWin32kInterface + 208))((unsigned int)v2, a2);
  }
  WdLogSingleEntry1(4, v12);
  WdLogGlobalForLineNumber = 12031;
  if ( v4 )
  {
    v15 = *(_QWORD *)v7;
    if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceContext) && (Microsoft_Windows_Win32kEnableBits & 0x10) != 0 )
      McTemplateK0pz_EtwWriteTransfer(v13, (unsigned int)&LockRelease, v14, v15 + 624, (__int64)L"DynamicModeChange");
    CurrentThread = KeGetCurrentThread();
    v17 = 0;
    if ( !(unsigned __int8)KeIsAttachedProcess()
      || (CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v19, v18, v20),
          CurrentThreadProcess = PsGetCurrentThreadProcess(),
          CurrentWin32kSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
    {
      ThreadWin32Thread = (__int64 *)PsGetThreadWin32Thread(CurrentThread);
      if ( ThreadWin32Thread )
        v17 = *ThreadWin32Thread;
    }
    v22 = v17 + 8;
    v23 = -v17;
    if ( (v22 & -(__int64)(v23 != 0)) != 0 && (*(_BYTE *)((v22 & -(__int64)(v23 != 0)) + 9))-- == 1 )
      *(_QWORD *)(v22 & -(__int64)(v23 != 0)) &= ~2uLL;
    GreReleaseSemaphoreSharedInternal((HSEMAPHORE)(v15 + 624));
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140011074  push    rbx
0x140011076  push    rbp
0x140011077  push    rsi
0x140011078  push    rdi
0x140011079  push    r13
0x14001107b  push    r14
0x14001107d  sub     rsp, 38h
0x140011081  mov     eax, ecx
0x140011083  mov     ebx, ecx
0x140011085  and     al, 7
0x140011087  mov     ebp, 4
0x14001108c  mov     rsi, rdx
0x14001108f  cmp     al, bpl
0x140011092  jz      loc_1400111E5
0x140011098  mov     dil, 1
0x14001109b  call    cs:__imp_W32GetSessionState
0x1400110a2  nop     dword ptr [rax+rax+00h]
0x1400110a7  lea     r13, aDynamicmodecha; "DynamicModeChange"
0x1400110ae  mov     r14, [rax+58h]
0x1400110b2  test    dil, dil
0x1400110b5  jz      short loc_1400110D8
0x1400110b7  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x1400110be  jnz     loc_140011207
0x1400110c4  mov     rcx, [r14]
0x1400110c7  add     rcx, 270h; hsem
0x1400110ce  call    EngAcquireSemaphoreShared
0x1400110d3  call    ??$GrepAcquireLockValidate@$00@@YAXXZ; GrepAcquireLockValidate<1>(void)
0x1400110d8  call    UserSessionSwitchLeaveCritWithNonPaged
0x1400110dd  mov     rdx, rbx
0x1400110e0  mov     ecx, ebp
0x1400110e2  call    cs:__imp_WdLogSingleEntry1
0x1400110e9  nop     dword ptr [rax+rax+00h]
0x1400110ee  mov     ecx, ebx
0x1400110f0  mov     cs:WdLogGlobalForLineNumber, 2EE0h
0x1400110fa  call    DrvIsQdcHandledByDispBroker
0x1400110ff  test    al, al
0x140011101  jnz     loc_140011234
0x140011107  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x14001110e  nop     dword ptr [rax+rax+00h]
0x140011113  mov     rdx, rsi
0x140011116  mov     ecx, ebx
0x140011118  mov     rax, [rax+0D0h]
0x14001111f  call    _guard_dispatch_icall
0x140011124  mov     esi, eax
0x140011126  movsxd  rdx, esi
0x140011129  mov     ecx, ebp
0x14001112b  call    cs:__imp_WdLogSingleEntry1
0x140011132  nop     dword ptr [rax+rax+00h]
0x140011137  mov     cs:WdLogGlobalForLineNumber, 2EFFh
0x140011141  test    dil, dil
0x140011144  jz      short loc_1400111AD
0x140011146  cmp     dword ptr cs:WPP_MAIN_CB.Queue+20h, 0
0x14001114d  mov     rbp, [r14]
0x140011150  jnz     loc_140011275
0x140011156  mov     r14, gs:188h
0x14001115f  xor     edi, edi
0x140011161  call    cs:__imp_KeIsAttachedProcess
0x140011168  nop     dword ptr [rax+rax+00h]
0x14001116d  test    al, al
0x14001116f  jnz     short loc_1400111BD
0x140011171  mov     rcx, r14
0x140011174  call    cs:__imp_PsGetThreadWin32Thread
0x14001117b  nop     dword ptr [rax+rax+00h]
0x140011180  test    rax, rax
0x140011183  jz      short loc_140011188
0x140011185  mov     rdi, [rax]
0x140011188  lea     rax, [rdi+8]
0x14001118c  neg     rdi
0x14001118f  sbb     rdx, rdx
0x140011192  and     rdx, rax
0x140011195  jz      short loc_1400111A1
0x140011197  add     byte ptr [rdx+9], 0FFh
0x14001119b  jnz     short loc_1400111A1
0x14001119d  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFDh
0x1400111a1  lea     rcx, [rbp+270h]; HSEMAPHORE
0x1400111a8  call    ?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x1400111ad  mov     eax, esi
0x1400111af  add     rsp, 38h
0x1400111b3  pop     r14
0x1400111b5  pop     r13
0x1400111b7  pop     rdi
0x1400111b8  pop     rsi
0x1400111b9  pop     rbp
0x1400111ba  pop     rbx
0x1400111bb  retn
0x1400111bd  call    W32GetCurrentWin32kSessionId
0x1400111c2  mov     ebx, eax
0x1400111c4  call    cs:__imp_PsGetCurrentThreadProcess
0x1400111cb  nop     dword ptr [rax+rax+00h]
0x1400111d0  mov     rcx, rax
0x1400111d3  call    cs:__imp_PsGetProcessSessionIdEx
0x1400111da  nop     dword ptr [rax+rax+00h]
0x1400111df  cmp     ebx, eax
0x1400111e1  jz      short loc_140011171
0x1400111e3  jmp     short loc_140011188
0x1400111e5  call    DispBrokerGetCurrentMode
0x1400111ea  cmp     eax, 3
0x1400111ed  jnz     short loc_1400111F7
0x1400111ef  xor     dil, dil
0x1400111f2  jmp     loc_14001109B
0x1400111f7  call    DispBrokerGetCurrentMode
0x1400111fc  cmp     eax, 2
0x1400111ff  jnz     loc_140011098
0x140011205  jmp     short loc_1400111EF
0x140011207  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14001120e  jz      loc_1400110C4
0x140011214  mov     r9, [r14]
0x140011217  lea     rdx, LockAcquireShared
0x14001121e  add     r9, 270h
0x140011225  mov     [rsp+68h+var_48], r13
0x14001122a  call    McTemplateK0pz_EtwWriteTransfer
0x14001122f  jmp     loc_1400110C4
0x140011234  call    DispBrokerGetCurrentMode
0x140011239  cmp     eax, 3
0x14001123c  jnz     short loc_14001126B
0x14001123e  mov     edx, ebx
0x140011240  mov     [rsp+68h+var_48], 0; enum DISPLAYCONFIG_TOPOLOGY_ID *
0x140011249  and     ebx, 0FFFFFFEFh
0x14001124c  and     edx, 10h; unsigned int
0x14001124f  mov     ecx, ebx; unsigned int
0x140011251  xor     r9d, r9d; struct DISPLAYCONFIG_PATH_INFO_INTERNAL *
0x140011254  mov     r8, rsi; unsigned int *
0x140011257  call    ?DispBrokerQueryDisplayConfig@@YAJIIPEAIPEAUDISPLAYCONFIG_PATH_INFO_INTERNAL@@PEAW4DISPLAYCONFIG_TOPOLOGY_ID@@_N@Z; DispBrokerQueryDisplayConfig(uint,uint,uint *,DISPLAYCONFIG_PATH_INFO_INTERNAL *,DISPLAYCONFIG_TOPOLOGY_ID *,bool)
0x14001125c  xor     esi, esi
0x14001125e  cmp     eax, 0C0000023h
0x140011263  cmovnz  esi, eax
0x140011266  jmp     loc_140011126
0x14001126b  mov     esi, 0C0000022h
0x140011270  jmp     loc_140011126
0x140011275  test    byte ptr cs:Microsoft_Windows_Win32kEnableBits, 10h
0x14001127c  jz      loc_140011156
0x140011282  lea     r9, [rbp+270h]
0x140011289  mov     [rsp+68h+var_48], r13
0x14001128e  lea     rdx, LockRelease
0x140011295  call    McTemplateK0pz_EtwWriteTransfer
0x14001129a  jmp     loc_140011156
```
