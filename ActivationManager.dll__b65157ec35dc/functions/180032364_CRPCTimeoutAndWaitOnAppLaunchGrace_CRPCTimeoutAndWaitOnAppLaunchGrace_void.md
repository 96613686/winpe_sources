# CRPCTimeoutAndWaitOnAppLaunchGrace::~CRPCTimeoutAndWaitOnAppLaunchGrace(void)

- ea: `0x180032364`
- end: `0x18003245e`
- name: `??1CRPCTimeoutAndWaitOnAppLaunchGrace@@QEAA@XZ`
- size: `250`
- prototype: `void __fastcall(CRPCTimeoutAndWaitOnAppLaunchGrace *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009b520`

## callees

- `0x180032364`
- `0x180089994`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18003242f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18003242f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180032425`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180032425`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032453`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032453`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800323df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800323df`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800323be`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800323be`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180032444`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180032444`
- `api-ms-win-core-psm-rtimer-l1-1-1!PsmTimerCleanup` at `0x180032396`
- `api-ms-win-core-psm-rtimer-l1-1-1!PsmTimerCleanup` at `0x180032396`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRPCTimeoutAndWaitOnAppLaunchGrace::~CRPCTimeoutAndWaitOnAppLaunchGrace(
        CRPCTimeoutAndWaitOnAppLaunchGrace *this)
{
  struct _TP_WAIT *v2; // rcx
  void *v3; // rdx
  char *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx

  if ( *((_BYTE *)this + 26) && !*((_BYTE *)this + 27) )
  {
    *((_BYTE *)this + 27) = 1;
    if ( *((_BYTE *)this + 25) )
      AAMTraceProvider::RPCTimerDisarming<unsigned __int64 &>(this);
    if ( *((_QWORD *)this + 12) )
    {
      PsmTimerCleanup();
      *((_QWORD *)this + 12) = 0;
    }
    v2 = (struct _TP_WAIT *)*((_QWORD *)this + 5);
    if ( v2 )
    {
      WaitForThreadpoolWaitCallbacks(v2, 1);
      CloseThreadpoolWait(*((PTP_WAIT *)this + 5));
      *((_QWORD *)this + 5) = 0;
    }
    v3 = (void *)*((_QWORD *)this + 4);
    if ( v3 )
    {
      DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *((_QWORD *)this + 4) = 0;
    }
  }
  if ( *((_BYTE *)this + 26) )
  {
    CoDisableCallCancellation(0);
    *((_BYTE *)this + 26) = 0;
  }
  v4 = (char *)*((_QWORD *)this + 10);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 7) = 0;
  }
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  v6 = *((_QWORD *)this + 6);
  if ( v6 )
  {
    *((_QWORD *)this + 6) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
}

```

## disassembly

```asm
0x180032364  mov     [rsp+arg_0], rbx
0x180032369  push    rdi
0x18003236a  sub     rsp, 20h
0x18003236e  mov     rbx, rcx
0x180032371  xor     edi, edi
0x180032373  cmp     [rcx+1Ah], dil
0x180032377  jz      short loc_1800323B6
0x180032379  cmp     [rcx+1Bh], dil
0x18003237d  jnz     short loc_1800323B6
0x18003237f  mov     byte ptr [rcx+1Bh], 1
0x180032383  cmp     [rcx+19h], dil
0x180032387  jnz     loc_180032416
0x18003238d  mov     rcx, [rbx+60h]
0x180032391  test    rcx, rcx
0x180032394  jz      short loc_1800323A0
0x180032396  call    cs:__imp_PsmTimerCleanup
0x18003239c  mov     [rbx+60h], rdi
0x1800323a0  mov     rcx, [rbx+28h]; pwa
0x1800323a4  test    rcx, rcx
0x1800323a7  jnz     short loc_180032420
0x1800323a9  mov     rdx, [rbx+20h]; Timer
0x1800323ad  test    rdx, rdx
0x1800323b0  jnz     loc_18003243E
0x1800323b6  cmp     [rbx+1Ah], dil
0x1800323ba  jz      short loc_1800323C8
0x1800323bc  xor     ecx, ecx; pReserved
0x1800323be  call    cs:__imp_CoDisableCallCancellation
0x1800323c4  mov     [rbx+1Ah], dil
0x1800323c8  mov     rcx, [rbx+50h]; hObject
0x1800323cc  lea     rax, [rcx-1]
0x1800323d0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800323d4  jbe     short loc_180032453
0x1800323d6  mov     rcx, [rbx+38h]; pv
0x1800323da  test    rcx, rcx
0x1800323dd  jz      short loc_1800323E9
0x1800323df  call    cs:__imp_CoTaskMemFree
0x1800323e5  mov     [rbx+38h], rdi
0x1800323e9  mov     [rbx+40h], rdi
0x1800323ed  mov     [rbx+48h], rdi
0x1800323f1  mov     rcx, [rbx+30h]
0x1800323f5  test    rcx, rcx
0x1800323f8  jz      short loc_18003240B
0x1800323fa  mov     [rbx+30h], rdi
0x1800323fe  mov     rax, [rcx]
0x180032401  mov     rax, [rax+10h]
0x180032405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003240a  nop
0x18003240b  mov     rbx, [rsp+28h+arg_0]
0x180032410  add     rsp, 20h
0x180032414  pop     rdi
0x180032415  retn
0x180032416  call    ??$RPCTimerDisarming@AEA_K@AAMTraceProvider@@SAXAEA_K@Z; AAMTraceProvider::RPCTimerDisarming<unsigned __int64 &>(unsigned __int64 &)
0x18003241b  jmp     loc_18003238D
0x180032420  mov     edx, 1; fCancelPendingCallbacks
0x180032425  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18003242b  mov     rcx, [rbx+28h]; pwa
0x18003242f  call    cs:__imp_CloseThreadpoolWait
0x180032435  mov     [rbx+28h], rdi
0x180032439  jmp     loc_1800323A9
0x18003243e  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180032442  xor     ecx, ecx; TimerQueue
0x180032444  call    cs:__imp_DeleteTimerQueueTimer
0x18003244a  mov     [rbx+20h], rdi
0x18003244e  jmp     loc_1800323B6
0x180032453  call    cs:__imp_CloseHandle
0x180032459  jmp     loc_1800323D6
```
