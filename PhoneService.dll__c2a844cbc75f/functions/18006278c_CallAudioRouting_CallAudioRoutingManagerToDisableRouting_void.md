# CallAudioRouting::_CallAudioRoutingManagerToDisableRouting(void)

- ea: `0x18006278c`
- end: `0x1800629e9`
- name: `?_CallAudioRoutingManagerToDisableRouting@CallAudioRouting@@AEAAJXZ`
- size: `605`
- prototype: `__int64 __fastcall(CallAudioRouting *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180061650`
- `0x180064270`

## callees

- `0x1800012b8`
- `0x180006e94`
- `0x180025ae4`
- `0x180031f6c`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x18006278c`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800627b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800627cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800627b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800627cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062914`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006297a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062914`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006297a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006292e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180062994`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006292e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180062994`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180062945`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800629ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180062945`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800629ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006293c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800629a2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006293c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800629a2`

## string_xrefs

- `0x1800627c3`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x18006283c`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800628eb`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_CallAudioRoutingManagerToDisableRouting(CallAudioRouting *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rcx
  int v6; // eax
  BackTraceCollection *v7; // rcx
  unsigned int v8; // ebx
  int v10; // edi
  BackTraceCollection *v11; // rcx
  struct _TP_TIMER *v12; // rbx
  struct _TP_TIMER *v13; // rbx
  unsigned int v14; // [rsp+20h] [rbp-60h]
  unsigned int v15[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v16; // [rsp+38h] [rbp-48h] BYREF
  _QWORD pv[2]; // [rsp+40h] [rbp-40h] BYREF
  PTP_TIMER pti; // [rsp+50h] [rbp-30h]
  __int64 v19; // [rsp+58h] [rbp-28h]
  HLOCAL hMem; // [rsp+60h] [rbp-20h]
  __int64 v21; // [rsp+68h] [rbp-18h]

  if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3206);
    if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    *(_QWORD *)v15 = "CallAudioRouting: Disabling phone call audio.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v2,
      (int)&word_1800A9C16,
      v3,
      v4,
      (const unsigned __int16 **)v15);
  }
  v5 = *((_QWORD *)this + 38);
  v16 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 24LL))(v5, &v16);
  v8 = v6;
  if ( v6 >= 0 )
  {
    v19 = 0;
    v21 = 0;
    pv[0] = &OperationWatchdog::`vftable';
    pv[1] = 0;
    pti = 0;
    hMem = 0;
    OperationWatchdog::Start(pv, 4u, 0, 0x3E8u, v14);
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16);
    OperationWatchdog::End((OperationWatchdog *)pv);
    if ( v10 >= 0 )
    {
      pv[0] = &OperationWatchdog::`vftable';
      OperationWatchdog::End((OperationWatchdog *)pv);
      if ( hMem )
        LocalFree(hMem);
      v13 = pti;
      if ( pti )
      {
        SetThreadpoolTimer(pti, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v13, 1);
        CloseThreadpoolTimer(v13);
      }
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      return 0;
    }
    else
    {
      BackTraceCollection::Capture(v11, v10);
      Log_HREvent_17(
        (unsigned int)v10,
        1,
        "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp",
        3224);
      pv[0] = &OperationWatchdog::`vftable';
      OperationWatchdog::End((OperationWatchdog *)pv);
      if ( hMem )
        LocalFree(hMem);
      v12 = pti;
      if ( pti )
      {
        SetThreadpoolTimer(pti, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v12, 1);
        CloseThreadpoolTimer(v12);
      }
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      return (unsigned int)v10;
    }
  }
  else
  {
    BackTraceCollection::Capture(v7, v6);
    Log_HREvent_17(v8, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3215);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    return v8;
  }
}

```

## disassembly

```asm
0x18006278c  mov     [rsp-8+arg_8], rbx
0x180062791  mov     [rsp-8+arg_10], rdi
0x180062796  push    rbp
0x180062797  mov     rbp, rsp
0x18006279a  sub     rsp, 80h
0x1800627a1  mov     rax, cs:__security_cookie
0x1800627a8  xor     rax, rsp
0x1800627ab  mov     [rbp+var_10], rax
0x1800627af  mov     rbx, rcx
0x1800627b2  call    cs:__imp_GetCurrentThreadId
0x1800627b8  cmp     [rbx+68h], eax
0x1800627bb  jnz     short loc_1800627DF
0x1800627bd  mov     r8d, 0C86h
0x1800627c3  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800627ca  call    Log_AssertionEvent_9
0x1800627cf  call    cs:__imp_GetCurrentThreadId
0x1800627d5  cmp     [rbx+68h], eax
0x1800627d8  jnz     short loc_1800627DF
0x1800627da  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800627df  mov     eax, cs:dword_1800B3200
0x1800627e5  cmp     eax, 4
0x1800627e8  jbe     short loc_18006280A
0x1800627ea  lea     rax, aCallaudiorouti_4; "CallAudioRouting: Disabling phone call "...
0x1800627f1  mov     qword ptr [rbp+var_50], rax
0x1800627f5  lea     rdx, word_1800A9C16
0x1800627fc  lea     rax, [rbp+var_50]
0x180062800  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x180062805  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006280a  mov     rcx, [rbx+130h]
0x180062811  lea     rdx, [rbp+var_48]
0x180062815  mov     [rbp+var_48], 0
0x18006281d  mov     rax, [rcx]
0x180062820  mov     rax, [rax+18h]
0x180062824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062829  mov     ebx, eax
0x18006282b  test    eax, eax
0x18006282d  jns     short loc_18006286B
0x18006282f  mov     edx, eax; int
0x180062831  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180062836  mov     r9d, 0C8Fh
0x18006283c  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180062843  mov     edx, 1
0x180062848  mov     ecx, ebx
0x18006284a  call    Log_HREvent_17
0x18006284f  mov     rcx, [rbp+var_48]
0x180062853  test    rcx, rcx
0x180062856  jz      short loc_180062864
0x180062858  mov     rax, [rcx]
0x18006285b  mov     rax, [rax+10h]
0x18006285f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062864  mov     eax, ebx
0x180062866  jmp     loc_1800629C8
0x18006286b  xor     r8d, r8d; char *
0x18006286e  mov     [rbp+var_28], 0
0x180062876  mov     [rbp+var_18], 0
0x18006287e  lea     rbx, ??_7OperationWatchdog@@6B@; const OperationWatchdog::`vftable'
0x180062885  mov     [rbp+pv], rbx
0x180062889  lea     rcx, [rbp+pv]; pv
0x18006288d  mov     [rbp+var_38], 0
0x180062895  mov     r9d, 3E8h; unsigned int
0x18006289b  mov     [rbp+pti], 0
0x1800628a3  lea     edx, [r8+4]; unsigned int
0x1800628a7  mov     [rbp+hMem], 0
0x1800628af  mov     dword ptr [rbp+var_18+4], 0
0x1800628b6  call    ?Start@OperationWatchdog@@QEAAXIPEBDKK@Z; OperationWatchdog::Start(uint,char const *,ulong,ulong)
0x1800628bb  mov     rcx, [rbp+var_48]
0x1800628bf  mov     rax, [rcx]
0x1800628c2  mov     rax, [rax+20h]
0x1800628c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800628cb  lea     rcx, [rbp+pv]; this
0x1800628cf  mov     edi, eax
0x1800628d1  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x1800628d6  test    edi, edi
0x1800628d8  jns     loc_180062964
0x1800628de  mov     edx, edi; int
0x1800628e0  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800628e5  mov     r9d, 0C98h
0x1800628eb  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800628f2  mov     edx, 1
0x1800628f7  mov     ecx, edi
0x1800628f9  call    Log_HREvent_17
0x1800628fe  lea     rcx, [rbp+pv]; this
0x180062902  mov     [rbp+pv], rbx
0x180062906  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x18006290b  mov     rcx, [rbp+hMem]; hMem
0x18006290f  test    rcx, rcx
0x180062912  jz      short loc_18006291A
0x180062914  call    cs:__imp_LocalFree
0x18006291a  mov     rbx, [rbp+pti]
0x18006291e  test    rbx, rbx
0x180062921  jz      short loc_18006294B
0x180062923  xor     r9d, r9d; msWindowLength
0x180062926  xor     r8d, r8d; msPeriod
0x180062929  xor     edx, edx; pftDueTime
0x18006292b  mov     rcx, rbx; pti
0x18006292e  call    cs:__imp_SetThreadpoolTimer
0x180062934  mov     edx, 1; fCancelPendingCallbacks
0x180062939  mov     rcx, rbx; pti
0x18006293c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180062942  mov     rcx, rbx; pti
0x180062945  call    cs:__imp_CloseThreadpoolTimer
0x18006294b  mov     rcx, [rbp+var_48]
0x18006294f  test    rcx, rcx
0x180062952  jz      short loc_180062960
0x180062954  mov     rax, [rcx]
0x180062957  mov     rax, [rax+10h]
0x18006295b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062960  mov     eax, edi
0x180062962  jmp     short loc_1800629C8
0x180062964  lea     rcx, [rbp+pv]; this
0x180062968  mov     [rbp+pv], rbx
0x18006296c  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x180062971  mov     rcx, [rbp+hMem]; hMem
0x180062975  test    rcx, rcx
0x180062978  jz      short loc_180062980
0x18006297a  call    cs:__imp_LocalFree
0x180062980  mov     rbx, [rbp+pti]
0x180062984  test    rbx, rbx
0x180062987  jz      short loc_1800629B1
0x180062989  xor     r9d, r9d; msWindowLength
0x18006298c  xor     r8d, r8d; msPeriod
0x18006298f  xor     edx, edx; pftDueTime
0x180062991  mov     rcx, rbx; pti
0x180062994  call    cs:__imp_SetThreadpoolTimer
0x18006299a  mov     edx, 1; fCancelPendingCallbacks
0x18006299f  mov     rcx, rbx; pti
0x1800629a2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800629a8  mov     rcx, rbx; pti
0x1800629ab  call    cs:__imp_CloseThreadpoolTimer
0x1800629b1  mov     rcx, [rbp+var_48]
0x1800629b5  test    rcx, rcx
0x1800629b8  jz      short loc_1800629C6
0x1800629ba  mov     rax, [rcx]
0x1800629bd  mov     rax, [rax+10h]
0x1800629c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800629c6  xor     eax, eax
0x1800629c8  mov     rcx, [rbp+var_10]
0x1800629cc  xor     rcx, rsp; StackCookie
0x1800629cf  call    __security_check_cookie
0x1800629d4  lea     r11, [rsp+80h+var_s0]
0x1800629dc  mov     rbx, [r11+18h]
0x1800629e0  mov     rdi, [r11+20h]
0x1800629e4  mov     rsp, r11
0x1800629e7  pop     rbp
0x1800629e8  retn
```
