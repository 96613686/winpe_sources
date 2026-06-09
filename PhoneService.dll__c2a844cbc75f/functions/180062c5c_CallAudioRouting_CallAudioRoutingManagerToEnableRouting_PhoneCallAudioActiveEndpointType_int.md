# CallAudioRouting::_CallAudioRoutingManagerToEnableRouting(PhoneCallAudioActiveEndpointType,int)

- ea: `0x180062c5c`
- end: `0x180062ed7`
- name: `?_CallAudioRoutingManagerToEnableRouting@CallAudioRouting@@AEAAJW4PhoneCallAudioActiveEndpointType@@H@Z`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180064a20`

## callees

- `0x180001348`
- `0x180006e94`
- `0x180025ae4`
- `0x180031f6c`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x180062c5c`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062c8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062ca9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062c8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062ca9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062e0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062e65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062e0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062e65`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180062e2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180062e7f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180062e2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180062e7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180062e44`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180062e96`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180062e44`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180062e96`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180062e3b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180062e8d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180062e3b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180062e8d`

## string_xrefs

- `0x180062c9d`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180062d2e`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180062de6`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_CallAudioRoutingManagerToEnableRouting(__int64 a1, unsigned int a2, int a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  int v10; // eax
  BackTraceCollection *v11; // rcx
  unsigned int v12; // ebx
  __int64 v14; // rdx
  BackTraceCollection *v15; // rcx
  struct _TP_TIMER *v16; // rdi
  struct _TP_TIMER *v17; // rbx
  unsigned int v18; // [rsp+20h] [rbp-29h]
  int v19; // [rsp+40h] [rbp-9h] BYREF
  unsigned int v20; // [rsp+44h] [rbp-5h] BYREF
  unsigned int v21[2]; // [rsp+48h] [rbp-1h] BYREF
  __int64 v22; // [rsp+50h] [rbp+7h] BYREF
  _QWORD pv[2]; // [rsp+58h] [rbp+Fh] BYREF
  PTP_TIMER pti; // [rsp+68h] [rbp+1Fh]
  __int64 v25; // [rsp+70h] [rbp+27h]
  HLOCAL hMem; // [rsp+78h] [rbp+2Fh]
  __int64 v27; // [rsp+80h] [rbp+37h]

  if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3160);
    if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    v19 = a3;
    *(_QWORD *)v21 = "CallAudioRouting: Enabling phone call audio";
    v20 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v6,
      (int)&unk_1800A9C48,
      v7,
      v8,
      (const unsigned __int16 **)v21,
      (__int64)&v20,
      (__int64)&v19);
  }
  v9 = *(_QWORD *)(a1 + 304);
  v22 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 24LL))(v9, &v22);
  v12 = v10;
  if ( v10 < 0 )
  {
    BackTraceCollection::Capture(v11, v10);
    Log_HREvent_17(v12, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3170);
LABEL_8:
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    return v12;
  }
  v25 = 0;
  v27 = 0;
  pv[0] = &OperationWatchdog::`vftable';
  pv[1] = 0;
  pti = 0;
  hMem = 0;
  OperationWatchdog::Start(pv, 3u, 0, 0x3E8u, v18);
  if ( a2 || (v14 = 7, a3) )
    v14 = a2;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 24LL))(v22, v14);
  OperationWatchdog::End((OperationWatchdog *)pv);
  if ( (v12 & 0x80000000) != 0 )
  {
    BackTraceCollection::Capture(v15, v12);
    Log_HREvent_17(v12, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3194);
    pv[0] = &OperationWatchdog::`vftable';
    OperationWatchdog::End((OperationWatchdog *)pv);
    if ( hMem )
      LocalFree(hMem);
    v16 = pti;
    if ( pti )
    {
      SetThreadpoolTimer(pti, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v16, 1);
      CloseThreadpoolTimer(v16);
    }
    goto LABEL_8;
  }
  pv[0] = &OperationWatchdog::`vftable';
  OperationWatchdog::End((OperationWatchdog *)pv);
  if ( hMem )
    LocalFree(hMem);
  v17 = pti;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v17, 1);
    CloseThreadpoolTimer(v17);
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return 0;
}

```

## disassembly

```asm
0x180062c5c  mov     [rsp-8+arg_10], rbx
0x180062c61  mov     [rsp-8+arg_18], rsi
0x180062c66  push    rbp
0x180062c67  push    rdi
0x180062c68  push    r15
0x180062c6a  lea     rbp, [rsp-47h]
0x180062c6f  sub     rsp, 90h
0x180062c76  mov     rax, cs:__security_cookie
0x180062c7d  xor     rax, rsp
0x180062c80  mov     [rbp+57h+var_18], rax
0x180062c84  mov     esi, r8d
0x180062c87  mov     edi, edx
0x180062c89  mov     rbx, rcx
0x180062c8c  call    cs:__imp_GetCurrentThreadId
0x180062c92  cmp     [rbx+68h], eax
0x180062c95  jnz     short loc_180062CB9
0x180062c97  mov     r8d, 0C58h
0x180062c9d  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180062ca4  call    Log_AssertionEvent_9
0x180062ca9  call    cs:__imp_GetCurrentThreadId
0x180062caf  cmp     [rbx+68h], eax
0x180062cb2  jnz     short loc_180062CB9
0x180062cb4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180062cb9  mov     eax, cs:dword_1800B3200
0x180062cbf  cmp     eax, 4
0x180062cc2  jbe     short loc_180062CFC
0x180062cc4  lea     rax, aCallaudiorouti_11; "CallAudioRouting: Enabling phone call a"...
0x180062ccb  mov     [rbp+57h+var_60], esi
0x180062cce  mov     qword ptr [rbp+57h+var_58], rax
0x180062cd2  lea     rdx, unk_1800A9C48
0x180062cd9  lea     rax, [rbp+57h+var_60]
0x180062cdd  mov     [rbp+57h+var_5C], edi
0x180062ce0  mov     [rsp+0A0h+var_70], rax
0x180062ce5  lea     rax, [rbp+57h+var_5C]
0x180062ce9  mov     [rsp+0A0h+var_78], rax
0x180062cee  lea     rax, [rbp+57h+var_58]
0x180062cf2  mov     qword ptr [rsp+0A0h+var_80], rax; unsigned int
0x180062cf7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180062cfc  mov     rcx, [rbx+130h]
0x180062d03  lea     rdx, [rbp+57h+var_50]
0x180062d07  mov     [rbp+57h+var_50], 0
0x180062d0f  mov     rax, [rcx]
0x180062d12  mov     rax, [rax+18h]
0x180062d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d1b  mov     ebx, eax
0x180062d1d  test    eax, eax
0x180062d1f  jns     short loc_180062D5D
0x180062d21  mov     edx, eax; int
0x180062d23  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180062d28  mov     r9d, 0C62h
0x180062d2e  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180062d35  mov     edx, 1
0x180062d3a  mov     ecx, ebx
0x180062d3c  call    Log_HREvent_17
0x180062d41  mov     rcx, [rbp+57h+var_50]
0x180062d45  test    rcx, rcx
0x180062d48  jz      short loc_180062D56
0x180062d4a  mov     rax, [rcx]
0x180062d4d  mov     rax, [rax+10h]
0x180062d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d56  mov     eax, ebx
0x180062d58  jmp     loc_180062EB3
0x180062d5d  xor     r8d, r8d; char *
0x180062d60  mov     [rbp+57h+var_30], 0
0x180062d68  mov     [rbp+57h+var_20], 0
0x180062d70  lea     r15, ??_7OperationWatchdog@@6B@; const OperationWatchdog::`vftable'
0x180062d77  mov     [rbp+57h+pv], r15
0x180062d7b  lea     rcx, [rbp+57h+pv]; pv
0x180062d7f  mov     [rbp+57h+var_40], 0
0x180062d87  mov     r9d, 3E8h; unsigned int
0x180062d8d  mov     [rbp+57h+pti], 0
0x180062d95  lea     edx, [r8+3]; unsigned int
0x180062d99  mov     [rbp+57h+hMem], 0
0x180062da1  mov     dword ptr [rbp+57h+var_20+4], 0
0x180062da8  call    ?Start@OperationWatchdog@@QEAAXIPEBDKK@Z; OperationWatchdog::Start(uint,char const *,ulong,ulong)
0x180062dad  test    edi, edi
0x180062daf  jnz     short loc_180062DB8
0x180062db1  lea     edx, [rdi+7]
0x180062db4  test    esi, esi
0x180062db6  jz      short loc_180062DBA
0x180062db8  mov     edx, edi
0x180062dba  mov     rcx, [rbp+57h+var_50]
0x180062dbe  mov     rax, [rcx]
0x180062dc1  mov     rax, [rax+18h]
0x180062dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062dca  lea     rcx, [rbp+57h+pv]; this
0x180062dce  mov     ebx, eax
0x180062dd0  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x180062dd5  test    ebx, ebx
0x180062dd7  jns     short loc_180062E4F
0x180062dd9  mov     edx, ebx; int
0x180062ddb  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180062de0  mov     r9d, 0C7Ah
0x180062de6  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180062ded  mov     edx, 1
0x180062df2  mov     ecx, ebx
0x180062df4  call    Log_HREvent_17
0x180062df9  lea     rcx, [rbp+57h+pv]; this
0x180062dfd  mov     [rbp+57h+pv], r15
0x180062e01  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x180062e06  mov     rcx, [rbp+57h+hMem]; hMem
0x180062e0a  test    rcx, rcx
0x180062e0d  jz      short loc_180062E15
0x180062e0f  call    cs:__imp_LocalFree
0x180062e15  mov     rdi, [rbp+57h+pti]
0x180062e19  test    rdi, rdi
0x180062e1c  jz      loc_180062D41
0x180062e22  xor     r9d, r9d; msWindowLength
0x180062e25  xor     r8d, r8d; msPeriod
0x180062e28  xor     edx, edx; pftDueTime
0x180062e2a  mov     rcx, rdi; pti
0x180062e2d  call    cs:__imp_SetThreadpoolTimer
0x180062e33  mov     edx, 1; fCancelPendingCallbacks
0x180062e38  mov     rcx, rdi; pti
0x180062e3b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180062e41  mov     rcx, rdi; pti
0x180062e44  call    cs:__imp_CloseThreadpoolTimer
0x180062e4a  jmp     loc_180062D41
0x180062e4f  lea     rcx, [rbp+57h+pv]; this
0x180062e53  mov     [rbp+57h+pv], r15
0x180062e57  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x180062e5c  mov     rcx, [rbp+57h+hMem]; hMem
0x180062e60  test    rcx, rcx
0x180062e63  jz      short loc_180062E6B
0x180062e65  call    cs:__imp_LocalFree
0x180062e6b  mov     rbx, [rbp+57h+pti]
0x180062e6f  test    rbx, rbx
0x180062e72  jz      short loc_180062E9C
0x180062e74  xor     r9d, r9d; msWindowLength
0x180062e77  xor     r8d, r8d; msPeriod
0x180062e7a  xor     edx, edx; pftDueTime
0x180062e7c  mov     rcx, rbx; pti
0x180062e7f  call    cs:__imp_SetThreadpoolTimer
0x180062e85  mov     edx, 1; fCancelPendingCallbacks
0x180062e8a  mov     rcx, rbx; pti
0x180062e8d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180062e93  mov     rcx, rbx; pti
0x180062e96  call    cs:__imp_CloseThreadpoolTimer
0x180062e9c  mov     rcx, [rbp+57h+var_50]
0x180062ea0  test    rcx, rcx
0x180062ea3  jz      short loc_180062EB1
0x180062ea5  mov     rax, [rcx]
0x180062ea8  mov     rax, [rax+10h]
0x180062eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062eb1  xor     eax, eax
0x180062eb3  mov     rcx, [rbp+57h+var_18]
0x180062eb7  xor     rcx, rsp; StackCookie
0x180062eba  call    __security_check_cookie
0x180062ebf  lea     r11, [rsp+0A0h+var_10]
0x180062ec7  mov     rbx, [r11+30h]
0x180062ecb  mov     rsi, [r11+38h]
0x180062ecf  mov     rsp, r11
0x180062ed2  pop     r15
0x180062ed4  pop     rdi
0x180062ed5  pop     rbp
0x180062ed6  retn
```
