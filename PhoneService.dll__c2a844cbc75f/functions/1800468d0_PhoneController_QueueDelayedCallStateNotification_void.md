# PhoneController::_QueueDelayedCallStateNotification(void)

- ea: `0x1800468d0`
- end: `0x180046a17`
- name: `?_QueueDelayedCallStateNotification@PhoneController@@MEAAJXZ`
- size: `327`
- prototype: `__int64 __fastcall(PhoneController *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006e94`
- `0x180023e94`
- `0x18002c574`
- `0x18002c580`
- `0x1800468d0`
- `0x18007f9ec`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800468e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046902`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800468e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046902`
- `PhoneUtil!OneShotTimer_CreateInstance` at `0x18004699e`
- `PhoneUtil!OneShotTimer_CreateInstance` at `0x18004699e`

## string_xrefs

- `0x1800468f6`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180046951`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800469b7`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_QueueDelayedCallStateNotification(PhoneController *this)
{
  __int64 v2; // rcx
  _QWORD *v3; // rsi
  int Instance; // eax
  BackTraceCollection *v5; // rcx
  unsigned int v6; // ebx
  __int64 v8; // rbx
  int v9; // eax
  BackTraceCollection *v10; // rcx
  unsigned int v11; // edi
  _QWORD v12[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4685);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v3 = (_QWORD *)((char *)this + 264);
  if ( *((_QWORD *)this + 33) )
    goto LABEL_15;
  v12[0] = 0;
  Instance = ControllerTimerContext::CreateInstance(3, v12);
  v6 = Instance;
  if ( Instance < 0 )
  {
    BackTraceCollection::Capture(v5, Instance);
    Log_HREvent_7(v6, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4690);
    if ( v12[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12[0] + 16LL))(v12[0]);
    return v6;
  }
  v8 = v12[0];
  v9 = OneShotTimer_CreateInstance(200, ((unsigned __int64)this + 24) & -(__int64)(this != 0), v12[0], v3);
  v11 = v9;
  if ( v9 >= 0 )
  {
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
LABEL_15:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 24LL))(*v3);
    return 0;
  }
  BackTraceCollection::Capture(v10, v9);
  Log_HREvent_7(v11, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 4692);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return v11;
}

```

## disassembly

```asm
0x1800468d0  mov     [rsp+arg_8], rbx
0x1800468d5  mov     [rsp+arg_10], rsi
0x1800468da  push    rdi
0x1800468db  sub     rsp, 40h
0x1800468df  mov     rdi, rcx
0x1800468e2  call    cs:__imp_GetCurrentThreadId
0x1800468e8  cmp     [rdi+0F0h], eax
0x1800468ee  jz      short loc_180046915
0x1800468f0  mov     r8d, 124Dh
0x1800468f6  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800468fd  call    Log_AssertionEvent_3
0x180046902  call    cs:__imp_GetCurrentThreadId
0x180046908  cmp     [rdi+0F0h], eax
0x18004690e  jz      short loc_180046915
0x180046910  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180046915  lea     rsi, [rdi+108h]
0x18004691c  cmp     qword ptr [rsi], 0
0x180046920  jnz     loc_1800469F6
0x180046926  lea     rdx, [rsp+48h+var_18]
0x18004692b  mov     [rsp+48h+var_18], 0
0x180046934  mov     ecx, 3
0x180046939  call    ?CreateInstance@ControllerTimerContext@@SAJW4TimerKind@1@PEAPEAV1@@Z; ControllerTimerContext::CreateInstance(ControllerTimerContext::TimerKind,ControllerTimerContext * *)
0x18004693e  mov     ebx, eax
0x180046940  test    eax, eax
0x180046942  jns     short loc_180046981
0x180046944  mov     edx, eax; int
0x180046946  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004694b  mov     r9d, 1252h
0x180046951  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180046958  mov     edx, 1
0x18004695d  mov     ecx, ebx
0x18004695f  call    Log_HREvent_7
0x180046964  mov     rcx, [rsp+48h+var_18]
0x180046969  test    rcx, rcx
0x18004696c  jz      short loc_18004697A
0x18004696e  mov     rax, [rcx]
0x180046971  mov     rax, [rax+10h]
0x180046975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004697a  mov     eax, ebx
0x18004697c  jmp     loc_180046A07
0x180046981  mov     rbx, [rsp+48h+var_18]
0x180046986  lea     rax, [rdi+18h]
0x18004698a  neg     rdi
0x18004698d  mov     r9, rsi
0x180046990  mov     r8, rbx
0x180046993  mov     ecx, 0C8h
0x180046998  sbb     rdx, rdx
0x18004699b  and     rdx, rax
0x18004699e  call    cs:__imp_OneShotTimer_CreateInstance
0x1800469a4  mov     edi, eax
0x1800469a6  test    eax, eax
0x1800469a8  jns     short loc_1800469E2
0x1800469aa  mov     edx, eax; int
0x1800469ac  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800469b1  mov     r9d, 1254h
0x1800469b7  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800469be  mov     edx, 1
0x1800469c3  mov     ecx, edi
0x1800469c5  call    Log_HREvent_7
0x1800469ca  test    rbx, rbx
0x1800469cd  jz      short loc_1800469DE
0x1800469cf  mov     rax, [rbx]
0x1800469d2  mov     rcx, rbx
0x1800469d5  mov     rax, [rax+10h]
0x1800469d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469de  mov     eax, edi
0x1800469e0  jmp     short loc_180046A07
0x1800469e2  test    rbx, rbx
0x1800469e5  jz      short loc_1800469F6
0x1800469e7  mov     rax, [rbx]
0x1800469ea  mov     rcx, rbx
0x1800469ed  mov     rax, [rax+10h]
0x1800469f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469f6  mov     rcx, [rsi]
0x1800469f9  mov     rax, [rcx]
0x1800469fc  mov     rax, [rax+18h]
0x180046a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a05  xor     eax, eax
0x180046a07  mov     rbx, [rsp+48h+arg_8]
0x180046a0c  mov     rsi, [rsp+48h+arg_10]
0x180046a11  add     rsp, 40h
0x180046a15  pop     rdi
0x180046a16  retn
```
