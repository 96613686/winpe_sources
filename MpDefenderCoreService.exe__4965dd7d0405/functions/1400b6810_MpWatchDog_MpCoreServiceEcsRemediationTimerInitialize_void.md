# MpWatchDog::MpCoreServiceEcsRemediationTimerInitialize(void)

- ea: `0x1400b6810`
- end: `0x1400b6910`
- name: `?MpCoreServiceEcsRemediationTimerInitialize@MpWatchDog@@YAJXZ`
- size: `256`
- prototype: `int(MpWatchDog *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140013394`
- `0x14007d1e0`
- `0x1400833d4`
- `0x1400b6810`
- `0x1400b7778`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1400b6892`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400b6892`

## pseudocode

```c
__int64 __fastcall MpWatchDog::MpCoreServiceEcsRemediationTimerInitialize(MpWatchDog *this)
{
  MpWatchDog *v1; // rcx
  char IsCoreSvcInDevMode; // al
  unsigned int v3; // edx
  unsigned int v4; // esi
  DWORD v5; // edi
  int TimerQueueTimer; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // ebx
  void *v11; // [rsp+28h] [rbp-10h]

  v1 = (MpWatchDog *)WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 41, &WPP_1203d082d3c634a6bc8c47067fc067ac_Traceguids);
  IsCoreSvcInDevMode = MpWatchDog::MpIsCoreSvcInDevMode(v1);
  v3 = IsCoreSvcInDevMode != 0 ? 5000 : 120000;
  v4 = v3 + (v3 >> 1);
  v5 = IsCoreSvcInDevMode != 0 ? 5000 : 600000;
  if ( MpWatchDog::gs_RemediationTimer )
  {
    DeleteTimerQueueTimer(0, MpWatchDog::gs_RemediationTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    MpWatchDog::gs_RemediationTimer = 0;
  }
  LODWORD(v11) = 0;
  TimerQueueTimer = CommonUtil::UtilCreateTimerQueueTimer(
                      (CommonUtil *)&MpWatchDog::gs_RemediationTimer,
                      (void **)v4,
                      v5,
                      (void (__stdcall *)(PVOID, BOOLEAN))MpWatchDog::RemediationTimerCallback,
                      0,
                      v11);
  v9 = TimerQueueTimer;
  if ( TimerQueueTimer < 0
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_ddd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v7, v8, v4, v5, TimerQueueTimer);
  }
  return v9;
}

```

## disassembly

```asm
0x1400b6810  mov     [rsp+arg_0], rbx
0x1400b6815  mov     [rsp+arg_8], rsi
0x1400b681a  mov     [rsp+arg_10], rdi
0x1400b681f  push    r14; unsigned int
0x1400b6821  sub     rsp, 30h
0x1400b6825  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b682c  lea     r14, WPP_GLOBAL_Control
0x1400b6833  cmp     rcx, r14
0x1400b6836  jz      short loc_1400B6853
0x1400b6838  test    byte ptr [rcx+1Ch], 4
0x1400b683c  jz      short loc_1400B6853
0x1400b683e  mov     rcx, [rcx+10h]
0x1400b6842  lea     r8, WPP_1203d082d3c634a6bc8c47067fc067ac_Traceguids
0x1400b6849  mov     edx, 29h ; ')'
0x1400b684e  call    WPP_SF_
0x1400b6853  call    ?MpIsCoreSvcInDevMode@MpWatchDog@@YA_NXZ; MpWatchDog::MpIsCoreSvcInDevMode(void)
0x1400b6858  mov     cl, al
0x1400b685a  neg     cl
0x1400b685c  sbb     edx, edx
0x1400b685e  and     edx, 0FFFE3EC8h
0x1400b6864  add     edx, 1D4C0h
0x1400b686a  neg     al
0x1400b686c  mov     esi, edx
0x1400b686e  sbb     edi, edi
0x1400b6870  shr     esi, 1
0x1400b6872  and     edi, 0FFF6EBC8h
0x1400b6878  add     esi, edx
0x1400b687a  mov     rdx, cs:?gs_RemediationTimer@MpWatchDog@@3V?$CUniqueHandle@UCAutoDeleteTimerQueueTimer@CommonUtil@@@CommonUtil@@A; Timer
0x1400b6881  add     edi, 927C0h
0x1400b6887  test    rdx, rdx
0x1400b688a  jz      short loc_1400B68A3
0x1400b688c  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1400b6890  xor     ecx, ecx; TimerQueue
0x1400b6892  call    cs:__imp_DeleteTimerQueueTimer
0x1400b6898  mov     cs:?gs_RemediationTimer@MpWatchDog@@3V?$CUniqueHandle@UCAutoDeleteTimerQueueTimer@CommonUtil@@@CommonUtil@@A, 0; CommonUtil::CUniqueHandle<CommonUtil::CAutoDeleteTimerQueueTimer> MpWatchDog::gs_RemediationTimer
0x1400b68a3  mov     dword ptr [rsp+38h+var_10], 0; void *
0x1400b68ab  lea     r9, ?RemediationTimerCallback@MpWatchDog@@YAXPEAXE@Z; unsigned int
0x1400b68b2  mov     r8d, edi; unsigned int
0x1400b68b5  mov     [rsp+38h+var_18], 0; void (*)(void *, unsigned __int8)
0x1400b68be  mov     edx, esi; void **
0x1400b68c0  lea     rcx, ?gs_RemediationTimer@MpWatchDog@@3V?$CUniqueHandle@UCAutoDeleteTimerQueueTimer@CommonUtil@@@CommonUtil@@A; this
0x1400b68c7  call    ?UtilCreateTimerQueueTimer@CommonUtil@@YAJPEAPEAXKKP6AXPEAXE@Z1K@Z; CommonUtil::UtilCreateTimerQueueTimer(void * *,ulong,ulong,void (*)(void *,uchar),void *,ulong)
0x1400b68cc  mov     ebx, eax
0x1400b68ce  test    eax, eax
0x1400b68d0  jns     short loc_1400B68F8
0x1400b68d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b68d9  cmp     rcx, r14
0x1400b68dc  jz      short loc_1400B68F8
0x1400b68de  test    byte ptr [rcx+1Ch], 2
0x1400b68e2  jz      short loc_1400B68F8
0x1400b68e4  mov     rcx, [rcx+10h]
0x1400b68e8  mov     r9d, esi
0x1400b68eb  mov     dword ptr [rsp+38h+var_10], eax
0x1400b68ef  mov     dword ptr [rsp+38h+var_18], edi
0x1400b68f3  call    WPP_SF_ddd
0x1400b68f8  mov     rsi, [rsp+38h+arg_8]
0x1400b68fd  mov     eax, ebx
0x1400b68ff  mov     rbx, [rsp+38h+arg_0]
0x1400b6904  mov     rdi, [rsp+38h+arg_10]
0x1400b6909  add     rsp, 30h
0x1400b690d  pop     r14
0x1400b690f  retn
```
