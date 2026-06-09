# CallAudioRouting::_CallAudioRoutingManagerToSetEndpoint(PhoneCallAudioActiveEndpointType)

- ea: `0x180062ee0`
- end: `0x180063142`
- name: `?_CallAudioRoutingManagerToSetEndpoint@CallAudioRouting@@AEAAJW4PhoneCallAudioActiveEndpointType@@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800698c0`

## callees

- `0x1800011fc`
- `0x18000151c`
- `0x180006e94`
- `0x180025ae4`
- `0x180031f6c`
- `0x18005f9b4`
- `0x18005f9c0`
- `0x180062ee0`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062f08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062f25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062f08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062f25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800630d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800630d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800630ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800630ee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180063105`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180063105`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800630fc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800630fc`

## string_xrefs

- `0x180062f19`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180062fd3`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800630ae`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
__int64 __fastcall CallAudioRouting::_CallAudioRoutingManagerToSetEndpoint(__int64 a1, unsigned int a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rcx
  int v8; // eax
  BackTraceCollection *v9; // rcx
  unsigned int v10; // ebx
  int v12; // ebx
  struct _TP_TIMER *v13; // rbx
  unsigned int v14; // [rsp+30h] [rbp-29h] BYREF
  const char *v15; // [rsp+38h] [rbp-21h] BYREF
  __int64 v16; // [rsp+40h] [rbp-19h] BYREF
  _QWORD pv[2]; // [rsp+48h] [rbp-11h] BYREF
  PTP_TIMER pti; // [rsp+58h] [rbp-1h]
  __int64 v19; // [rsp+60h] [rbp+7h]
  HLOCAL hMem; // [rsp+68h] [rbp+Fh]
  __int64 v21; // [rsp+70h] [rbp+17h]
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+78h] [rbp+1Fh] BYREF

  if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v4, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3236);
    if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    v14 = a2;
    v15 = "CallAudioRouting: Setting audio endpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v4,
      (int)word_1800A9BE2,
      v5,
      v6,
      (const unsigned __int16 **)&v15,
      (__int64)&v14);
  }
  if ( (unsigned int)dword_1800B3200 > 5 )
    tlgWriteTransfer_EventWriteTransfer((int)&dword_1800B3200, (int)&qword_1800A9BB0, 0, 0, 2u, &v22);
  v7 = *(_QWORD *)(a1 + 304);
  v16 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 24LL))(v7, &v16);
  v10 = v8;
  if ( v8 >= 0 )
  {
    v19 = 0;
    v21 = 0;
    pv[0] = &OperationWatchdog::`vftable';
    pv[1] = 0;
    pti = 0;
    hMem = 0;
    OperationWatchdog::Start(pv, 5, 0, 1000);
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 40LL))(v16, a2);
    OperationWatchdog::End((OperationWatchdog *)pv);
    if ( (unsigned int)dword_1800B3200 > 5 )
      tlgWriteTransfer_EventWriteTransfer((int)&dword_1800B3200, (int)&unk_1800A9B80, 0, 0, 2u, &v22);
    if ( v12 < 0 )
      Log_HREvent_17(
        (unsigned int)v12,
        0,
        "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp",
        3268);
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
    BackTraceCollection::Capture(v9, v8);
    Log_HREvent_17(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 3253);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    return v10;
  }
}

```

## disassembly

```asm
0x180062ee0  mov     [rsp-8+arg_10], rbx
0x180062ee5  push    rbp
0x180062ee6  push    rdi
0x180062ee7  push    r12
0x180062ee9  lea     rbp, [rsp-47h]
0x180062eee  sub     rsp, 0A0h
0x180062ef5  mov     rax, cs:__security_cookie
0x180062efc  xor     rax, rsp
0x180062eff  mov     [rbp+57h+var_18], rax
0x180062f03  mov     edi, edx
0x180062f05  mov     rbx, rcx
0x180062f08  call    cs:__imp_GetCurrentThreadId
0x180062f0e  cmp     [rbx+68h], eax
0x180062f11  jnz     short loc_180062F35
0x180062f13  mov     r8d, 0CA4h
0x180062f19  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180062f20  call    Log_AssertionEvent_9
0x180062f25  call    cs:__imp_GetCurrentThreadId
0x180062f2b  cmp     [rbx+68h], eax
0x180062f2e  jnz     short loc_180062F35
0x180062f30  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180062f35  mov     eax, cs:dword_1800B3200
0x180062f3b  cmp     eax, 4
0x180062f3e  jbe     short loc_180062F6C
0x180062f40  lea     rax, aCallaudiorouti_25; "CallAudioRouting: Setting audio endpoin"...
0x180062f47  mov     [rbp+57h+var_80], edi
0x180062f4a  mov     [rbp+57h+var_78], rax
0x180062f4e  lea     rdx, word_1800A9BE2
0x180062f55  lea     rax, [rbp+57h+var_80]
0x180062f59  mov     [rsp+0B0h+var_88], rax
0x180062f5e  lea     rax, [rbp+57h+var_78]
0x180062f62  mov     qword ptr [rsp+0B0h+var_90], rax
0x180062f67  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180062f6c  mov     eax, cs:dword_1800B3200
0x180062f72  cmp     eax, 5
0x180062f75  jbe     short loc_180062FA1
0x180062f77  lea     rax, [rbp+57h+var_38]
0x180062f7b  xor     r9d, r9d; int
0x180062f7e  mov     [rsp+0B0h+var_88], rax; PEVENT_DATA_DESCRIPTOR
0x180062f83  lea     rdx, qword_1800A9BB0; int
0x180062f8a  xor     r8d, r8d; int
0x180062f8d  mov     [rsp+0B0h+var_90], 2; unsigned int
0x180062f95  lea     rcx, dword_1800B3200; int
0x180062f9c  call    _tlgWriteTransfer_EventWriteTransfer
0x180062fa1  mov     rcx, [rbx+130h]
0x180062fa8  lea     rdx, [rbp+57h+var_70]
0x180062fac  mov     [rbp+57h+var_70], 0
0x180062fb4  mov     rax, [rcx]
0x180062fb7  mov     rax, [rax+18h]
0x180062fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062fc0  mov     ebx, eax
0x180062fc2  test    eax, eax
0x180062fc4  jns     short loc_180063002
0x180062fc6  mov     edx, eax; int
0x180062fc8  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180062fcd  mov     r9d, 0CB5h
0x180062fd3  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180062fda  mov     edx, 1
0x180062fdf  mov     ecx, ebx
0x180062fe1  call    Log_HREvent_17
0x180062fe6  mov     rcx, [rbp+57h+var_70]
0x180062fea  test    rcx, rcx
0x180062fed  jz      short loc_180062FFB
0x180062fef  mov     rax, [rcx]
0x180062ff2  mov     rax, [rax+10h]
0x180062ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062ffb  mov     eax, ebx
0x180062ffd  jmp     loc_180063122
0x180063002  xor     r8d, r8d; char *
0x180063005  mov     [rbp+57h+var_50], 0
0x18006300d  mov     [rbp+57h+var_40], 0
0x180063015  lea     r12, ??_7OperationWatchdog@@6B@; const OperationWatchdog::`vftable'
0x18006301c  mov     [rbp+57h+pv], r12
0x180063020  lea     rcx, [rbp+57h+pv]; pv
0x180063024  mov     [rbp+57h+var_60], 0
0x18006302c  mov     r9d, 3E8h; unsigned int
0x180063032  mov     [rbp+57h+pti], 0
0x18006303a  lea     edx, [r8+5]; unsigned int
0x18006303e  mov     [rbp+57h+hMem], 0
0x180063046  mov     dword ptr [rbp+57h+var_40+4], 0
0x18006304d  call    ?Start@OperationWatchdog@@QEAAXIPEBDKK@Z; OperationWatchdog::Start(uint,char const *,ulong,ulong)
0x180063052  mov     rcx, [rbp+57h+var_70]
0x180063056  mov     edx, edi
0x180063058  mov     rax, [rcx]
0x18006305b  mov     rax, [rax+28h]
0x18006305f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063064  lea     rcx, [rbp+57h+pv]; this
0x180063068  mov     ebx, eax
0x18006306a  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x18006306f  mov     edx, cs:dword_1800B3200
0x180063075  cmp     edx, 5
0x180063078  jbe     short loc_1800630A4
0x18006307a  lea     rax, [rbp+57h+var_38]
0x18006307e  xor     r9d, r9d; int
0x180063081  mov     [rsp+0B0h+var_88], rax; PEVENT_DATA_DESCRIPTOR
0x180063086  lea     rdx, unk_1800A9B80; int
0x18006308d  xor     r8d, r8d; int
0x180063090  mov     [rsp+0B0h+var_90], 2; ULONG
0x180063098  lea     rcx, dword_1800B3200; int
0x18006309f  call    _tlgWriteTransfer_EventWriteTransfer
0x1800630a4  test    ebx, ebx
0x1800630a6  jns     short loc_1800630BE
0x1800630a8  mov     r9d, 0CC4h
0x1800630ae  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800630b5  xor     edx, edx
0x1800630b7  mov     ecx, ebx
0x1800630b9  call    Log_HREvent_17
0x1800630be  lea     rcx, [rbp+57h+pv]; this
0x1800630c2  mov     [rbp+57h+pv], r12
0x1800630c6  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x1800630cb  mov     rcx, [rbp+57h+hMem]; hMem
0x1800630cf  test    rcx, rcx
0x1800630d2  jz      short loc_1800630DA
0x1800630d4  call    cs:__imp_LocalFree
0x1800630da  mov     rbx, [rbp+57h+pti]
0x1800630de  test    rbx, rbx
0x1800630e1  jz      short loc_18006310B
0x1800630e3  xor     r9d, r9d; msWindowLength
0x1800630e6  xor     r8d, r8d; msPeriod
0x1800630e9  xor     edx, edx; pftDueTime
0x1800630eb  mov     rcx, rbx; pti
0x1800630ee  call    cs:__imp_SetThreadpoolTimer
0x1800630f4  mov     edx, 1; fCancelPendingCallbacks
0x1800630f9  mov     rcx, rbx; pti
0x1800630fc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180063102  mov     rcx, rbx; pti
0x180063105  call    cs:__imp_CloseThreadpoolTimer
0x18006310b  mov     rcx, [rbp+57h+var_70]
0x18006310f  test    rcx, rcx
0x180063112  jz      short loc_180063120
0x180063114  mov     rax, [rcx]
0x180063117  mov     rax, [rax+10h]
0x18006311b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063120  xor     eax, eax
0x180063122  mov     rcx, [rbp+57h+var_18]
0x180063126  xor     rcx, rsp; StackCookie
0x180063129  call    __security_check_cookie
0x18006312e  mov     rbx, [rsp+0B0h+arg_10]
0x180063136  add     rsp, 0A0h
0x18006313d  pop     r12
0x18006313f  pop     rdi
0x180063140  pop     rbp
0x180063141  retn
```
