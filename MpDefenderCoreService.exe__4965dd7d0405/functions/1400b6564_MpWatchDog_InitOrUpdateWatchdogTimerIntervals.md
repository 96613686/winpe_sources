# MpWatchDog::InitOrUpdateWatchdogTimerIntervals

- ea: `0x1400b6564`
- end: `0x1400b675e`
- name: `MpWatchDog::InitOrUpdateWatchdogTimerIntervals`
- size: `506`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400b6910`
- `0x1400b7000`

## callees

- `0x140012e14`
- `0x140013394`
- `0x14007d1e0`
- `0x14007d210`
- `0x1400833d4`
- `0x14008d178`
- `0x1400b6564`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x1400b66c4`
- `KERNEL32!DeleteTimerQueueTimer` at `0x1400b66c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MpWatchDog::InitOrUpdateWatchdogTimerIntervals(MpWatchDog *a1, int a2)
{
  char v3; // r14
  MpWatchDog::WdConfigManager *v4; // rbx
  char IsCoreSvcInDevMode; // al
  MpWatchDog *v7; // rcx
  char *v8; // rsi
  unsigned int v9; // edi
  ULONG v10; // ebp
  char v11; // al
  unsigned int v12; // r9d
  const wchar_t *v13; // r9
  MpWatchDog *v14; // rcx
  const wchar_t *v15; // r9
  unsigned int v16; // esi
  int TimerQueueTimer; // eax
  void *v18; // [rsp+28h] [rbp-20h]
  unsigned int v19; // [rsp+30h] [rbp-18h]

  v3 = (char)a1;
  v4 = MpWatchDog::gMpWdConfigManager;
  if ( !MpWatchDog::gMpWdConfigManager )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, &WPP_1203d082d3c634a6bc8c47067fc067ac_Traceguids);
    return 2147500037LL;
  }
  IsCoreSvcInDevMode = MpWatchDog::MpIsCoreSvcInDevMode(a1);
  v8 = (char *)v4 + 856;
  if ( *((_BYTE *)v4 + 857) )
    IsCoreSvcInDevMode = *v8;
  v9 = 1000;
  if ( IsCoreSvcInDevMode )
    v10 = 1000;
  else
    v10 = *(_DWORD *)v4;
  v11 = MpWatchDog::MpIsCoreSvcInDevMode(v7);
  if ( *((_BYTE *)v4 + 857) )
    v11 = *v8;
  if ( !v11 )
    v9 = *((_DWORD *)v4 + 1);
  if ( v10 || v9 )
  {
    v14 = (MpWatchDog *)WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v15 = L"Initializing";
      if ( !v3 )
        v15 = L"Updating";
      WPP_SF_SLd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        36,
        (unsigned int)&WPP_1203d082d3c634a6bc8c47067fc067ac_Traceguids,
        (_DWORD)v15,
        v10,
        v9);
    }
    v16 = 0;
    if ( v3 )
    {
      if ( MpWatchDog::gs_WatchdogTimer )
      {
        DeleteTimerQueueTimer(0, MpWatchDog::gs_WatchdogTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        MpWatchDog::gs_WatchdogTimer = 0;
      }
      LODWORD(v18) = 0;
      TimerQueueTimer = CommonUtil::UtilCreateTimerQueueTimer(
                          (CommonUtil *)&MpWatchDog::gs_WatchdogTimer,
                          (void **)v10,
                          v9,
                          (unsigned int)MpWatchDog::WatchDogTimerCallback,
                          0,
                          v18,
                          v19);
    }
    else
    {
      if ( a2 == v9 && !MpWatchDog::MpIsCoreSvcInDevMode(v14) )
        return v16;
      TimerQueueTimer = CommonUtil::UtilChangeTimerQueueTimer(MpWatchDog::gs_WatchdogTimer, v10, v9, v12);
    }
    v16 = TimerQueueTimer;
    if ( TimerQueueTimer < 0
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        37,
        &WPP_1203d082d3c634a6bc8c47067fc067ac_Traceguids,
        (unsigned int)TimerQueueTimer);
    }
    return v16;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v13 = L"Initializing";
    if ( !v3 )
      v13 = L"Updating";
    WPP_SF_SLd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      35,
      (unsigned int)&WPP_1203d082d3c634a6bc8c47067fc067ac_Traceguids,
      (_DWORD)v13,
      0,
      0);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1400b6564  mov     [rsp+arg_0], rbx
0x1400b6569  mov     [rsp+arg_8], rbp
0x1400b656e  mov     [rsp+arg_10], rsi
0x1400b6573  push    rdi
0x1400b6574  push    r14
0x1400b6576  push    r15; unsigned int
0x1400b6578  sub     rsp, 30h
0x1400b657c  mov     r15d, edx
0x1400b657f  mov     r14b, cl
0x1400b6582  mov     rbx, cs:?gMpWdConfigManager@MpWatchDog@@3PEAVWdConfigManager@1@EA; MpWatchDog::WdConfigManager * MpWatchDog::gMpWdConfigManager
0x1400b6589  test    rbx, rbx
0x1400b658c  jnz     short loc_1400B65C6
0x1400b658e  lea     rbx, WPP_GLOBAL_Control
0x1400b6595  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b659c  cmp     rcx, rbx
0x1400b659f  jz      short loc_1400B65BC
0x1400b65a1  test    byte ptr [rcx+1Ch], 1
0x1400b65a5  jz      short loc_1400B65BC
0x1400b65a7  mov     edx, 22h ; '"'
0x1400b65ac  lea     r8, WPP_1203d082d3c634a6bc8c47067fc067ac_Traceguids
0x1400b65b3  mov     rcx, [rcx+10h]
0x1400b65b7  call    WPP_SF_
0x1400b65bc  mov     eax, 80004005h
0x1400b65c1  jmp     loc_1400B6745
0x1400b65c6  call    ?MpIsCoreSvcInDevMode@MpWatchDog@@YA_NXZ; MpWatchDog::MpIsCoreSvcInDevMode(void)
0x1400b65cb  lea     rsi, [rbx+358h]
0x1400b65d2  cmp     byte ptr [rbx+359h], 0
0x1400b65d9  jz      short loc_1400B65DD
0x1400b65db  mov     al, [rsi]
0x1400b65dd  mov     edi, 3E8h
0x1400b65e2  test    al, al
0x1400b65e4  jz      short loc_1400B65EA
0x1400b65e6  mov     ebp, edi
0x1400b65e8  jmp     short loc_1400B65ED
0x1400b65ea  mov     ebp, [rbx]
0x1400b65ec  nop
0x1400b65ed  call    ?MpIsCoreSvcInDevMode@MpWatchDog@@YA_NXZ; MpWatchDog::MpIsCoreSvcInDevMode(void)
0x1400b65f2  cmp     byte ptr [rbx+359h], 0
0x1400b65f9  jz      short loc_1400B65FD
0x1400b65fb  mov     al, [rsi]
0x1400b65fd  test    al, al
0x1400b65ff  jnz     short loc_1400B6605
0x1400b6601  mov     edi, [rbx+4]
0x1400b6604  nop
0x1400b6605  test    ebp, ebp
0x1400b6607  jnz     short loc_1400B6660
0x1400b6609  test    edi, edi
0x1400b660b  jnz     short loc_1400B6660
0x1400b660d  lea     rbx, WPP_GLOBAL_Control
0x1400b6614  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b661b  cmp     rcx, rbx
0x1400b661e  jz      short loc_1400B6656
0x1400b6620  test    byte ptr [rcx+1Ch], 1
0x1400b6624  jz      short loc_1400B6656
0x1400b6626  lea     rax, aUpdating; "Updating"
0x1400b662d  lea     r9, aInitializing_0; "Initializing"
0x1400b6634  test    r14b, r14b
0x1400b6637  cmovz   r9, rax
0x1400b663b  lea     edx, [rbp+23h]
0x1400b663e  mov     dword ptr [rsp+48h+var_20], edi
0x1400b6642  mov     dword ptr [rsp+48h+var_28], edi
0x1400b6646  lea     r8, WPP_1203d082d3c634a6bc8c47067fc067ac_Traceguids
0x1400b664d  mov     rcx, [rcx+10h]
0x1400b6651  call    WPP_SF_SLd
0x1400b6656  mov     eax, 80070057h
0x1400b665b  jmp     loc_1400B6745
0x1400b6660  lea     rbx, WPP_GLOBAL_Control
0x1400b6667  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b666e  cmp     rcx, rbx
0x1400b6671  jz      short loc_1400B66AB
0x1400b6673  test    byte ptr [rcx+1Ch], 4
0x1400b6677  jz      short loc_1400B66AB
0x1400b6679  lea     rax, aUpdating; "Updating"
0x1400b6680  lea     r9, aInitializing_0; "Initializing"
0x1400b6687  test    r14b, r14b
0x1400b668a  cmovz   r9, rax
0x1400b668e  mov     edx, 24h ; '$'
0x1400b6693  mov     dword ptr [rsp+48h+var_20], edi
0x1400b6697  mov     dword ptr [rsp+48h+var_28], ebp
0x1400b669b  lea     r8, WPP_1203d082d3c634a6bc8c47067fc067ac_Traceguids
0x1400b66a2  mov     rcx, [rcx+10h]
0x1400b66a6  call    WPP_SF_SLd
0x1400b66ab  xor     esi, esi
0x1400b66ad  test    r14b, r14b
0x1400b66b0  jz      short loc_1400B66F4
0x1400b66b2  mov     rdx, cs:?gs_WatchdogTimer@MpWatchDog@@3V?$CUniqueHandle@UCAutoDeleteTimerQueueTimer@CommonUtil@@@CommonUtil@@A; Timer
0x1400b66b9  test    rdx, rdx
0x1400b66bc  jz      short loc_1400B66D1
0x1400b66be  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1400b66c2  xor     ecx, ecx; TimerQueue
0x1400b66c4  call    cs:__imp_DeleteTimerQueueTimer
0x1400b66ca  mov     cs:?gs_WatchdogTimer@MpWatchDog@@3V?$CUniqueHandle@UCAutoDeleteTimerQueueTimer@CommonUtil@@@CommonUtil@@A, rsi; CommonUtil::CUniqueHandle<CommonUtil::CAutoDeleteTimerQueueTimer> MpWatchDog::gs_WatchdogTimer
0x1400b66d1  mov     dword ptr [rsp+48h+var_20], esi; void *
0x1400b66d5  mov     [rsp+48h+var_28], rsi; void (*)(void *, unsigned __int8)
0x1400b66da  lea     r9, ?WatchDogTimerCallback@MpWatchDog@@YAXPEAXE@Z; unsigned int
0x1400b66e1  mov     r8d, edi; unsigned int
0x1400b66e4  mov     edx, ebp; void **
0x1400b66e6  lea     rcx, ?gs_WatchdogTimer@MpWatchDog@@3V?$CUniqueHandle@UCAutoDeleteTimerQueueTimer@CommonUtil@@@CommonUtil@@A; this
0x1400b66ed  call    ?UtilCreateTimerQueueTimer@CommonUtil@@YAJPEAPEAXKKP6AXPEAXE@Z1K@Z; CommonUtil::UtilCreateTimerQueueTimer(void * *,ulong,ulong,void (*)(void *,uchar),void *,ulong)
0x1400b66f2  jmp     short loc_1400B6713
0x1400b66f4  cmp     r15d, edi
0x1400b66f7  jnz     short loc_1400B6702
0x1400b66f9  call    ?MpIsCoreSvcInDevMode@MpWatchDog@@YA_NXZ; MpWatchDog::MpIsCoreSvcInDevMode(void)
0x1400b66fe  test    al, al
0x1400b6700  jz      short loc_1400B6743
0x1400b6702  mov     r8d, edi; Period
0x1400b6705  mov     edx, ebp; DueTime
0x1400b6707  mov     rcx, cs:?gs_WatchdogTimer@MpWatchDog@@3V?$CUniqueHandle@UCAutoDeleteTimerQueueTimer@CommonUtil@@@CommonUtil@@A; Timer
0x1400b670e  call    ?UtilChangeTimerQueueTimer@CommonUtil@@YAJPEAXKK@Z; CommonUtil::UtilChangeTimerQueueTimer(void *,ulong,ulong)
0x1400b6713  mov     esi, eax
0x1400b6715  test    eax, eax
0x1400b6717  jns     short loc_1400B6743
0x1400b6719  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b6720  cmp     rcx, rbx
0x1400b6723  jz      short loc_1400B6743
0x1400b6725  test    byte ptr [rcx+1Ch], 1
0x1400b6729  jz      short loc_1400B6743
0x1400b672b  mov     edx, 25h ; '%'
0x1400b6730  mov     r9d, eax
0x1400b6733  lea     r8, WPP_1203d082d3c634a6bc8c47067fc067ac_Traceguids
0x1400b673a  mov     rcx, [rcx+10h]
0x1400b673e  call    WPP_SF_d
0x1400b6743  mov     eax, esi
0x1400b6745  mov     rbx, [rsp+48h+arg_0]
0x1400b674a  mov     rbp, [rsp+48h+arg_8]
0x1400b674f  mov     rsi, [rsp+48h+arg_10]
0x1400b6754  add     rsp, 30h
0x1400b6758  pop     r15
0x1400b675a  pop     r14
0x1400b675c  pop     rdi
0x1400b675d  retn
```
