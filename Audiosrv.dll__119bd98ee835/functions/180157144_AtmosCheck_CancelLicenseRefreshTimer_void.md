# AtmosCheck::CancelLicenseRefreshTimer(void)

- ea: `0x180157144`
- end: `0x1801571ef`
- name: `?CancelLicenseRefreshTimer@AtmosCheck@@AEAAXXZ`
- size: `171`
- prototype: `void __fastcall(AtmosCheck *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180158cb4`
- `0x180158e64`

## callees

- `0x18006808c`
- `0x180157144`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015715d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015715d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180157188`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180157188`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1801571b9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1801571b9`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180157196`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180157196`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801571ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801571ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1801571c2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1801571c2`

## pseudocode

```c
void __fastcall AtmosCheck::CancelLicenseRefreshTimer(AtmosCheck *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  struct _TP_TIMER *v3; // rdi
  __int64 v4; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 25);
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 29) = 0;
  if ( v1 )
    LeaveCriticalSection(v1);
  if ( v3 )
  {
    if ( IsThreadpoolTimerSet(v3) )
    {
      SetThreadpoolTimer(v3, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v3, 1);
    }
    CloseThreadpoolTimer(v3);
    if ( CallbackContext > 5u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v4,
        byte_1801AE5E3);
  }
}

```

## disassembly

```asm
0x180157144  mov     [rsp+arg_0], rbx
0x180157149  mov     [rsp+arg_8], rsi
0x18015714e  push    rdi
0x18015714f  sub     rsp, 20h
0x180157153  lea     rsi, [rcx+38h]
0x180157157  mov     rbx, rcx
0x18015715a  mov     rcx, rsi; lpCriticalSection
0x18015715d  call    cs:__imp_EnterCriticalSection
0x180157163  mov     rdi, [rbx+0C8h]
0x18015716a  mov     qword ptr [rbx+0C8h], 0
0x180157175  mov     qword ptr [rbx+0E8h], 0
0x180157180  test    rsi, rsi
0x180157183  jz      short loc_18015718E
0x180157185  mov     rcx, rsi; lpCriticalSection
0x180157188  call    cs:__imp_LeaveCriticalSection
0x18015718e  test    rdi, rdi
0x180157191  jz      short loc_1801571DF
0x180157193  mov     rcx, rdi; pti
0x180157196  call    cs:__imp_IsThreadpoolTimerSet
0x18015719c  test    eax, eax
0x18015719e  jz      short loc_1801571BF
0x1801571a0  xor     r9d, r9d; msWindowLength
0x1801571a3  xor     r8d, r8d; msPeriod
0x1801571a6  xor     edx, edx; pftDueTime
0x1801571a8  mov     rcx, rdi; pti
0x1801571ab  call    cs:__imp_SetThreadpoolTimer
0x1801571b1  mov     edx, 1; fCancelPendingCallbacks
0x1801571b6  mov     rcx, rdi; pti
0x1801571b9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1801571bf  mov     rcx, rdi; pti
0x1801571c2  call    cs:__imp_CloseThreadpoolTimer
0x1801571c8  mov     eax, cs:CallbackContext
0x1801571ce  cmp     eax, 5
0x1801571d1  jbe     short loc_1801571DF
0x1801571d3  lea     rdx, byte_1801AE5E3
0x1801571da  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801571df  mov     rbx, [rsp+28h+arg_0]
0x1801571e4  mov     rsi, [rsp+28h+arg_8]
0x1801571e9  add     rsp, 20h
0x1801571ed  pop     rdi
0x1801571ee  retn
```
