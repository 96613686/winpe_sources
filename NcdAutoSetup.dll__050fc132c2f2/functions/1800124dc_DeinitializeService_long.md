# DeinitializeService(long)

- ea: `0x1800124dc`
- end: `0x1800127b3`
- name: `?DeinitializeService@@YAXJ@Z`
- size: `727`
- prototype: `void __fastcall()`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180012c30`

## callees

- `0x1800018c4`
- `0x1800033ec`
- `0x18000a644`
- `0x18000a778`
- `0x18000c564`
- `0x1800124dc`
- `0x180012c9c`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125c4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001255a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001255a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012665`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012665`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001271e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001271e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012618`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012672`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800126b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012618`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012672`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800126b9`
- `KERNEL32!UnregisterWaitEx` at `0x1800125ba`
- `KERNEL32!UnregisterWaitEx` at `0x1800125ba`

## pseudocode

```c
void __fastcall DeinitializeService()
{
  _QWORD *v0; // rcx
  HANDLE v1; // rax
  CDeviceHandler *v2; // rbx
  int v3; // edx
  _QWORD *v4; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
      v0 = WPP_GLOBAL_Control;
    }
    if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 0x20) != 0 )
    {
      WPP_SF_(v0[2], 27, &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids);
      v0 = WPP_GLOBAL_Control;
    }
  }
  if ( hObject )
  {
    SetEvent(hObject);
    v0 = WPP_GLOBAL_Control;
  }
  if ( *(&Block + 1) )
  {
    CNetworkHandler::Stop(*(&Block + 1));
    v0 = WPP_GLOBAL_Control;
  }
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 0x20) != 0 )
  {
    WPP_SF_(v0[2], 28, &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( g_hServiceWaitObject )
  {
    if ( !UnregisterWaitEx(g_hServiceWaitObject, 0) && GetLastError() != 997 )
    {
      v0 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_21;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
    }
    v0 = WPP_GLOBAL_Control;
LABEL_21:
    g_hServiceWaitObject = 0;
  }
  if ( g_hServiceStopEvent )
  {
    CloseHandle(g_hServiceStopEvent);
    v0 = WPP_GLOBAL_Control;
    g_hServiceStopEvent = 0;
  }
  v1 = g_ThreadsCompletedEvent;
  if ( g_ThreadsCompletedEvent )
  {
    if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 8) != 0 )
    {
      WPP_SF_(v0[2], 16, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
      v1 = g_ThreadsCompletedEvent;
    }
    WaitForSingleObject(v1, 0xFFFFFFFF);
    CloseHandle(g_ThreadsCompletedEvent);
    v0 = WPP_GLOBAL_Control;
    g_ThreadsCompletedEvent = 0;
  }
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 0x20) != 0 )
    WPP_SF_(v0[2], 13, &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  v2 = Block;
  if ( Block )
  {
    CDeviceHandler::~CDeviceHandler(Block);
    operator delete(v2);
    Block = 0;
  }
  if ( *(&Block + 1) )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*(&Block + 1) + 16LL))(*(&Block + 1));
    *(&Block + 1) = 0;
  }
  DeleteCriticalSection(&g_StateMachine);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_d77279752c2730a2c88f617b9d74e821_Traceguids);
  if ( (int)UpdateServiceStatus(1u, v3) >= 0 )
    goto LABEL_45;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
LABEL_45:
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_(v4[2], 18, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
}

```

## disassembly

```asm
0x1800124dc  mov     [rsp+arg_0], rbx
0x1800124e1  mov     [rsp+arg_8], rsi
0x1800124e6  push    r14
0x1800124e8  sub     rsp, 20h
0x1800124ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124f3  lea     rsi, WPP_GLOBAL_Control
0x1800124fa  lea     r14, WPP_3f50365df99735211a88e8fb382b12e7_Traceguids
0x180012501  cmp     rcx, rsi
0x180012504  jz      short loc_18001254B
0x180012506  test    byte ptr [rcx+1Ch], 20h
0x18001250a  jz      short loc_180012524
0x18001250c  mov     rcx, [rcx+10h]
0x180012510  mov     edx, 0Eh
0x180012515  mov     r8, r14
0x180012518  call    WPP_SF_
0x18001251d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012524  cmp     rcx, rsi
0x180012527  jz      short loc_18001254B
0x180012529  test    byte ptr [rcx+1Ch], 20h
0x18001252d  jz      short loc_18001254B
0x18001252f  mov     rcx, [rcx+10h]
0x180012533  lea     r8, WPP_d77279752c2730a2c88f617b9d74e821_Traceguids
0x18001253a  mov     edx, 1Bh
0x18001253f  call    WPP_SF_
0x180012544  mov     rcx, cs:WPP_GLOBAL_Control
0x18001254b  mov     rax, cs:hObject
0x180012552  test    rax, rax
0x180012555  jz      short loc_180012567
0x180012557  mov     rcx, rax; hEvent
0x18001255a  call    cs:__imp_SetEvent
0x180012560  mov     rcx, cs:WPP_GLOBAL_Control
0x180012567  mov     rdx, qword ptr cs:Block+8
0x18001256e  test    rdx, rdx
0x180012571  jz      short loc_180012582
0x180012573  mov     rcx, rdx; this
0x180012576  call    ?Stop@CNetworkHandler@@QEAAJXZ; CNetworkHandler::Stop(void)
0x18001257b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012582  cmp     rcx, rsi
0x180012585  jz      short loc_1800125A9
0x180012587  test    byte ptr [rcx+1Ch], 20h
0x18001258b  jz      short loc_1800125A9
0x18001258d  mov     rcx, [rcx+10h]
0x180012591  lea     r8, WPP_d77279752c2730a2c88f617b9d74e821_Traceguids
0x180012598  mov     edx, 1Ch
0x18001259d  call    WPP_SF_
0x1800125a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125a9  mov     rax, cs:?g_hServiceWaitObject@@3PEAXEA; void * g_hServiceWaitObject
0x1800125b0  test    rax, rax
0x1800125b3  jz      short loc_180012609
0x1800125b5  xor     edx, edx; CompletionEvent
0x1800125b7  mov     rcx, rax; WaitHandle
0x1800125ba  call    cs:__imp_UnregisterWaitEx
0x1800125c0  test    eax, eax
0x1800125c2  jnz     short loc_1800125F7
0x1800125c4  call    cs:__imp_GetLastError
0x1800125ca  cmp     eax, 3E5h
0x1800125cf  jz      short loc_1800125F7
0x1800125d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125d8  cmp     rcx, rsi
0x1800125db  jz      short loc_1800125FE
0x1800125dd  test    byte ptr [rcx+1Ch], 4
0x1800125e1  jz      short loc_1800125FE
0x1800125e3  mov     rcx, [rcx+10h]
0x1800125e7  mov     edx, 0Fh
0x1800125ec  mov     r9d, eax
0x1800125ef  mov     r8, r14
0x1800125f2  call    WPP_SF_d
0x1800125f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125fe  mov     cs:?g_hServiceWaitObject@@3PEAXEA, 0; void * g_hServiceWaitObject
0x180012609  mov     rax, cs:?g_hServiceStopEvent@@3PEAXEA; void * g_hServiceStopEvent
0x180012610  test    rax, rax
0x180012613  jz      short loc_180012630
0x180012615  mov     rcx, rax; hObject
0x180012618  call    cs:__imp_CloseHandle
0x18001261e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012625  mov     cs:?g_hServiceStopEvent@@3PEAXEA, 0; void * g_hServiceStopEvent
0x180012630  mov     rax, cs:?g_ThreadsCompletedEvent@@3PEAXEA; void * g_ThreadsCompletedEvent
0x180012637  test    rax, rax
0x18001263a  jz      short loc_18001268A
0x18001263c  cmp     rcx, rsi
0x18001263f  jz      short loc_18001265F
0x180012641  test    byte ptr [rcx+1Ch], 8
0x180012645  jz      short loc_18001265F
0x180012647  mov     rcx, [rcx+10h]
0x18001264b  mov     edx, 10h
0x180012650  mov     r8, r14
0x180012653  call    WPP_SF_
0x180012658  mov     rax, cs:?g_ThreadsCompletedEvent@@3PEAXEA; void * g_ThreadsCompletedEvent
0x18001265f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180012662  mov     rcx, rax; hHandle
0x180012665  call    cs:__imp_WaitForSingleObject
0x18001266b  mov     rcx, cs:?g_ThreadsCompletedEvent@@3PEAXEA; hObject
0x180012672  call    cs:__imp_CloseHandle
0x180012678  mov     rcx, cs:WPP_GLOBAL_Control
0x18001267f  mov     cs:?g_ThreadsCompletedEvent@@3PEAXEA, 0; void * g_ThreadsCompletedEvent
0x18001268a  cmp     rcx, rsi
0x18001268d  jz      short loc_1800126AA
0x18001268f  test    byte ptr [rcx+1Ch], 20h
0x180012693  jz      short loc_1800126AA
0x180012695  mov     rcx, [rcx+10h]
0x180012699  lea     r8, WPP_d77279752c2730a2c88f617b9d74e821_Traceguids
0x1800126a0  mov     edx, 0Dh
0x1800126a5  call    WPP_SF_
0x1800126aa  mov     rax, cs:hObject
0x1800126b1  test    rax, rax
0x1800126b4  jz      short loc_1800126CA
0x1800126b6  mov     rcx, rax; hObject
0x1800126b9  call    cs:__imp_CloseHandle
0x1800126bf  mov     cs:hObject, 0
0x1800126ca  mov     rbx, qword ptr cs:Block
0x1800126d1  test    rbx, rbx
0x1800126d4  jz      short loc_1800126F1
0x1800126d6  mov     rcx, rbx; this
0x1800126d9  call    ??1CDeviceHandler@@QEAA@XZ; CDeviceHandler::~CDeviceHandler(void)
0x1800126de  mov     rcx, rbx; Block
0x1800126e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800126e6  mov     qword ptr cs:Block, 0
0x1800126f1  mov     rdx, qword ptr cs:Block+8
0x1800126f8  test    rdx, rdx
0x1800126fb  jz      short loc_180012717
0x1800126fd  mov     rax, [rdx]
0x180012700  mov     rcx, rdx
0x180012703  mov     rax, [rax+10h]
0x180012707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001270c  mov     qword ptr cs:Block+8, 0
0x180012717  lea     rcx, ?g_StateMachine@@3USTATE_MACHINE@@A; lpCriticalSection
0x18001271e  call    cs:__imp_DeleteCriticalSection
0x180012724  mov     rcx, cs:WPP_GLOBAL_Control
0x18001272b  cmp     rcx, rsi
0x18001272e  jz      short loc_18001274B
0x180012730  test    byte ptr [rcx+1Ch], 20h
0x180012734  jz      short loc_18001274B
0x180012736  mov     rcx, [rcx+10h]
0x18001273a  lea     r8, WPP_d77279752c2730a2c88f617b9d74e821_Traceguids
0x180012741  mov     edx, 0Eh
0x180012746  call    WPP_SF_
0x18001274b  mov     ecx, 1; unsigned int
0x180012750  call    ?UpdateServiceStatus@@YAJKJ@Z; UpdateServiceStatus(ulong,long)
0x180012755  test    eax, eax
0x180012757  jns     short loc_18001277F
0x180012759  mov     rcx, cs:WPP_GLOBAL_Control
0x180012760  cmp     rcx, rsi
0x180012763  jz      short loc_1800127A2
0x180012765  test    byte ptr [rcx+1Ch], 2
0x180012769  jz      short loc_180012786
0x18001276b  mov     rcx, [rcx+10h]
0x18001276f  mov     edx, 11h
0x180012774  mov     r9d, eax
0x180012777  mov     r8, r14
0x18001277a  call    WPP_SF_d
0x18001277f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012786  cmp     rcx, rsi
0x180012789  jz      short loc_1800127A2
0x18001278b  test    byte ptr [rcx+1Ch], 20h
0x18001278f  jz      short loc_1800127A2
0x180012791  mov     rcx, [rcx+10h]
0x180012795  mov     edx, 12h
0x18001279a  mov     r8, r14
0x18001279d  call    WPP_SF_
0x1800127a2  mov     rbx, [rsp+28h+arg_0]
0x1800127a7  mov     rsi, [rsp+28h+arg_8]
0x1800127ac  add     rsp, 20h
0x1800127b0  pop     r14
0x1800127b2  retn
```
