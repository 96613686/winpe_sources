# AIFabricSvcCallout::~AIFabricSvcCallout(void)

- ea: `0x180014988`
- end: `0x180014a2a`
- name: `??1AIFabricSvcCallout@@QEAA@XZ`
- size: `162`
- prototype: `void __fastcall(AIFabricSvcCallout *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018910`

## callees

- `0x18000c478`
- `0x180014988`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800149d5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800149d5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800149de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800149de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800149c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800149c7`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800149ad`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800149ad`

## pseudocode

```c
void __fastcall AIFabricSvcCallout::~AIFabricSvcCallout(AIFabricSvcCallout *this)
{
  _QWORD *v2; // rcx
  __int64 v3; // rcx
  struct _TP_TIMER *v4; // rdi
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  volatile signed __int32 *v6; // rcx

  v2 = (_QWORD *)((char *)this + 56);
  if ( *v2 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v2);
  v3 = *((_QWORD *)this + 6);
  if ( v3 )
    DevCloseObjectQuery(v3);
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 5);
  if ( v4 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 5), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
  }
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 4);
  if ( v5 )
    (**v5)(v5, 1);
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
  }
}

```

## disassembly

```asm
0x180014988  mov     [rsp+arg_0], rbx
0x18001498d  push    rdi
0x18001498e  sub     rsp, 20h
0x180014992  mov     rbx, rcx
0x180014995  add     rcx, 38h ; '8'
0x180014999  cmp     qword ptr [rcx], 0
0x18001499d  jz      short loc_1800149A4
0x18001499f  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800149a4  mov     rcx, [rbx+30h]
0x1800149a8  test    rcx, rcx
0x1800149ab  jz      short loc_1800149B3
0x1800149ad  call    cs:__imp_DevCloseObjectQuery
0x1800149b3  mov     rdi, [rbx+28h]
0x1800149b7  test    rdi, rdi
0x1800149ba  jz      short loc_1800149E4
0x1800149bc  xor     r9d, r9d; msWindowLength
0x1800149bf  xor     r8d, r8d; msPeriod
0x1800149c2  xor     edx, edx; pftDueTime
0x1800149c4  mov     rcx, rdi; pti
0x1800149c7  call    cs:__imp_SetThreadpoolTimer
0x1800149cd  mov     edx, 1; fCancelPendingCallbacks
0x1800149d2  mov     rcx, rdi; pti
0x1800149d5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800149db  mov     rcx, rdi; pti
0x1800149de  call    cs:__imp_CloseThreadpoolTimer
0x1800149e4  mov     rcx, [rbx+20h]
0x1800149e8  test    rcx, rcx
0x1800149eb  jz      short loc_1800149FD
0x1800149ed  mov     rax, [rcx]
0x1800149f0  mov     edx, 1
0x1800149f5  mov     rax, [rax]
0x1800149f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149fd  mov     rcx, [rbx+8]
0x180014a01  test    rcx, rcx
0x180014a04  jz      short loc_180014A1F
0x180014a06  or      eax, 0FFFFFFFFh
0x180014a09  lock xadd [rcx+0Ch], eax
0x180014a0e  cmp     eax, 1
0x180014a11  jnz     short loc_180014A1F
0x180014a13  mov     rax, [rcx]
0x180014a16  mov     rax, [rax+8]
0x180014a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a1f  mov     rbx, [rsp+28h+arg_0]
0x180014a24  add     rsp, 20h
0x180014a28  pop     rdi
0x180014a29  retn
```
