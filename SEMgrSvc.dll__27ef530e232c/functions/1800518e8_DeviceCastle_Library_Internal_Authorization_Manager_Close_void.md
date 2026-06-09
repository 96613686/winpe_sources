# DeviceCastle::Library::Internal::Authorization::Manager::Close(void)

- ea: `0x1800518e8`
- end: `0x180051958`
- name: `?Close@Manager@Authorization@Internal@Library@DeviceCastle@@QEAAXXZ`
- size: `112`
- prototype: `void __fastcall(DeviceCastle::Library::Internal::Authorization::Manager *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180042ee0`
- `0x180051608`

## callees

- `0x1800518e8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180051911`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180051911`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180051902`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180051902`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005191b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005191b`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180051932`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18005193c`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180051932`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18005193c`

## pseudocode

```c
void __fastcall DeviceCastle::Library::Internal::Authorization::Manager::Close(
        DeviceCastle::Library::Internal::Authorization::Manager *this)
{
  struct _TP_TIMER *v2; // rcx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 3), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 3));
    *((_QWORD *)this + 3) = 0;
  }
  if ( *((_QWORD *)this + 11) )
  {
    ((void (*)(void))RtlUnsubscribeWnfStateChangeNotification)();
    RtlUnsubscribeWnfStateChangeNotification(*((_QWORD *)this + 12));
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 11) = 0;
  }
}

```

## disassembly

```asm
0x1800518e8  push    rbx
0x1800518ea  sub     rsp, 20h
0x1800518ee  mov     rbx, rcx
0x1800518f1  mov     rcx, [rcx+18h]; pti
0x1800518f5  test    rcx, rcx
0x1800518f8  jz      short loc_180051929
0x1800518fa  xor     r9d, r9d; msWindowLength
0x1800518fd  xor     r8d, r8d; msPeriod
0x180051900  xor     edx, edx; pftDueTime
0x180051902  call    cs:__imp_SetThreadpoolTimer
0x180051908  mov     rcx, [rbx+18h]; pti
0x18005190c  mov     edx, 1; fCancelPendingCallbacks
0x180051911  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180051917  mov     rcx, [rbx+18h]; pti
0x18005191b  call    cs:__imp_CloseThreadpoolTimer
0x180051921  mov     qword ptr [rbx+18h], 0
0x180051929  mov     rcx, [rbx+58h]
0x18005192d  test    rcx, rcx
0x180051930  jz      short loc_180051952
0x180051932  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x180051938  mov     rcx, [rbx+60h]
0x18005193c  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x180051942  mov     qword ptr [rbx+60h], 0
0x18005194a  mov     qword ptr [rbx+58h], 0
0x180051952  add     rsp, 20h
0x180051956  pop     rbx
0x180051957  retn
```
