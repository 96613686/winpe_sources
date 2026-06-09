# PaymentBackgroundManager::~PaymentBackgroundManager(void)

- ea: `0x18007f8a0`
- end: `0x18007f920`
- name: `??1PaymentBackgroundManager@@AEAA@XZ`
- size: `128`
- prototype: `void __fastcall(PaymentBackgroundManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18009c5d0`

## callees

- `0x1800049c4`
- `0x18007f8a0`
- `0x1800846f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007f919`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007f8ed`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007f8ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007f8df`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007f8df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007f8f6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007f8f6`
- `BrokerLib!BrDeleteBrokerInstance` at `0x18007f905`
- `BrokerLib!BrDeleteBrokerInstance` at `0x18007f905`

## pseudocode

```c
void __fastcall PaymentBackgroundManager::~PaymentBackgroundManager(PaymentBackgroundManager *this)
{
  void *v1; // rdi
  struct _TP_TIMER *v3; // rdi
  __int64 v4; // rcx

  v1 = (void *)*((_QWORD *)this + 9);
  if ( v1 )
  {
    CanMakePaymentRequestManager::~CanMakePaymentRequestManager(*((CanMakePaymentRequestManager **)this + 9));
    operator delete(v1);
  }
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 8), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v3, 1);
    CloseThreadpoolTimer(v3);
  }
  v4 = *((_QWORD *)this + 6);
  if ( v4 )
    BrDeleteBrokerInstance(v4);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18007f8a0  mov     [rsp+arg_0], rbx
0x18007f8a5  push    rdi
0x18007f8a6  sub     rsp, 20h
0x18007f8aa  mov     rdi, [rcx+48h]
0x18007f8ae  mov     rbx, rcx
0x18007f8b1  test    rdi, rdi
0x18007f8b4  jz      short loc_18007F8CB
0x18007f8b6  mov     rcx, rdi; this
0x18007f8b9  call    ??1CanMakePaymentRequestManager@@QEAA@XZ; CanMakePaymentRequestManager::~CanMakePaymentRequestManager(void)
0x18007f8be  mov     edx, 0F0h
0x18007f8c3  mov     rcx, rdi; Block
0x18007f8c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007f8cb  mov     rdi, [rbx+40h]
0x18007f8cf  test    rdi, rdi
0x18007f8d2  jz      short loc_18007F8FC
0x18007f8d4  xor     r9d, r9d; msWindowLength
0x18007f8d7  xor     r8d, r8d; msPeriod
0x18007f8da  xor     edx, edx; pftDueTime
0x18007f8dc  mov     rcx, rdi; pti
0x18007f8df  call    cs:__imp_SetThreadpoolTimer
0x18007f8e5  mov     edx, 1; fCancelPendingCallbacks
0x18007f8ea  mov     rcx, rdi; pti
0x18007f8ed  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007f8f3  mov     rcx, rdi; pti
0x18007f8f6  call    cs:__imp_CloseThreadpoolTimer
0x18007f8fc  mov     rcx, [rbx+30h]
0x18007f900  test    rcx, rcx
0x18007f903  jz      short loc_18007F90B
0x18007f905  call    cs:__imp_BrDeleteBrokerInstance
0x18007f90b  lea     rcx, [rbx+8]
0x18007f90f  mov     rbx, [rsp+28h+arg_0]
0x18007f914  add     rsp, 20h
0x18007f918  pop     rdi
0x18007f919  jmp     cs:__imp_DeleteCriticalSection
```
