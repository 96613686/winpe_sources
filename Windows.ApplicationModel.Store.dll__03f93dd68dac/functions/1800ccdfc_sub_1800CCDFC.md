# sub_1800CCDFC

- ea: `0x1800ccdfc`
- end: `0x1800cd022`
- name: `sub_1800CCDFC`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800cd0f0`

## callees

- `0x180017c34`
- `0x18003dbc0`
- `0x1800ccdfc`
- `0x1800cfe24`
- `0x180159010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800cce45`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x1800cce45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ccff1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ccffb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cd005`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ccff1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ccffb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cd005`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cce60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cce60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cce80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cce80`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800cceed`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800cceed`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ccea4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ccea4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ccead`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ccead`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800cce96`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800cce96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ccfc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ccfdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ccfc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ccfdd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sub_1800CCDFC(__int64 a1)
{
  struct _TP_TIMER *v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  *(_QWORD *)a1 = off_180169910;
  *(_QWORD *)(a1 + 8) = off_1801698A8;
  *(_QWORD *)(a1 + 16) = off_180169888;
  *(_QWORD *)(a1 + 24) = off_1801698C8;
  if ( *(_QWORD *)(a1 + 472) )
  {
    RtlUnsubscribeWnfStateChangeNotification();
    *(_QWORD *)(a1 + 472) = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
  v2 = *(struct _TP_TIMER **)(a1 + 464);
  *(_QWORD *)(a1 + 464) = 0;
  if ( a1 != -152 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
  }
  if ( (unsigned __int8)sub_1800CFE24(qword_180243908) )
  {
    *(_QWORD *)(a1 + 296) = 0;
    *(_QWORD *)(a1 + 304) = 0;
  }
  InitOnceExecuteOnce(&InitOnce, InitFn, 0, 0);
  byte_1802438B8 = 1;
  (*(void (__fastcall **)(int *))(*(_QWORD *)&qword_1802438B0 + 16LL))(&qword_1802438B0);
  v3 = *(_QWORD *)(a1 + 320);
  if ( v3 )
  {
    *(_QWORD *)(a1 + 320) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = *(_QWORD *)(a1 + 312);
  if ( v4 )
  {
    *(_QWORD *)(a1 + 312) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  v5 = *(_QWORD *)(a1 + 304);
  if ( v5 )
  {
    *(_QWORD *)(a1 + 304) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *(_QWORD *)(a1 + 296);
  if ( v6 )
  {
    *(_QWORD *)(a1 + 296) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( *(_QWORD *)(a1 + 264) )
  {
    *(_QWORD *)(a1 + 264) = 0;
    sub_18003DBC0();
  }
  WindowsDeleteString(*(HSTRING *)(a1 + 232));
  *(_QWORD *)(a1 + 232) = 0;
  WindowsDeleteString(*(HSTRING *)(a1 + 224));
  *(_QWORD *)(a1 + 224) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
  return sub_180017C34(a1);
}

```

## disassembly

```asm
0x1800ccdfc  mov     [rsp+arg_0], rbx
0x1800cce01  mov     [rsp+arg_8], rsi
0x1800cce06  push    rdi
0x1800cce07  sub     rsp, 20h
0x1800cce0b  mov     rbx, rcx
0x1800cce0e  lea     rax, off_180169910
0x1800cce15  mov     [rcx], rax
0x1800cce18  lea     rax, off_1801698A8
0x1800cce1f  mov     [rcx+8], rax
0x1800cce23  lea     rax, off_180169888
0x1800cce2a  mov     [rcx+10h], rax
0x1800cce2e  lea     rax, off_1801698C8
0x1800cce35  mov     [rcx+18h], rax
0x1800cce39  mov     rcx, [rcx+1D8h]
0x1800cce40  test    rcx, rcx
0x1800cce43  jz      short loc_1800CCE56
0x1800cce45  call    cs:RtlUnsubscribeWnfStateChangeNotification
0x1800cce4b  mov     qword ptr [rbx+1D8h], 0
0x1800cce56  lea     rsi, [rbx+98h]
0x1800cce5d  mov     rcx, rsi; lpCriticalSection
0x1800cce60  call    cs:EnterCriticalSection
0x1800cce66  mov     rdi, [rbx+1D0h]
0x1800cce6d  mov     qword ptr [rbx+1D0h], 0
0x1800cce78  test    rsi, rsi
0x1800cce7b  jz      short loc_1800CCE86
0x1800cce7d  mov     rcx, rsi; lpCriticalSection
0x1800cce80  call    cs:LeaveCriticalSection
0x1800cce86  test    rdi, rdi
0x1800cce89  jz      short loc_1800CCEB3
0x1800cce8b  xor     r9d, r9d; msWindowLength
0x1800cce8e  xor     r8d, r8d; msPeriod
0x1800cce91  xor     edx, edx; pftDueTime
0x1800cce93  mov     rcx, rdi; pti
0x1800cce96  call    cs:SetThreadpoolTimer
0x1800cce9c  mov     edx, 1; fCancelPendingCallbacks
0x1800ccea1  mov     rcx, rdi; pti
0x1800ccea4  call    cs:WaitForThreadpoolTimerCallbacks
0x1800cceaa  mov     rcx, rdi; pti
0x1800ccead  call    cs:CloseThreadpoolTimer
0x1800cceb3  lea     rcx, qword_180243908
0x1800cceba  call    sub_1800CFE24
0x1800ccebf  test    al, al
0x1800ccec1  jz      short loc_1800CCED9
0x1800ccec3  mov     qword ptr [rbx+128h], 0
0x1800ccece  mov     qword ptr [rbx+130h], 0
0x1800cced9  xor     r9d, r9d; Context
0x1800ccedc  xor     r8d, r8d; Parameter
0x1800ccedf  lea     rdx, InitFn; InitFn
0x1800ccee6  lea     rcx, InitOnce; InitOnce
0x1800cceed  call    cs:InitOnceExecuteOnce
0x1800ccef3  mov     cs:byte_1802438B8, 1
0x1800ccefa  mov     rax, cs:qword_1802438B0
0x1800ccf01  lea     rcx, qword_1802438B0
0x1800ccf08  mov     rax, [rax+10h]
0x1800ccf0c  call    j__guard_dispatch_icall
0x1800ccf11  nop
0x1800ccf12  mov     rcx, [rbx+140h]
0x1800ccf19  test    rcx, rcx
0x1800ccf1c  jz      short loc_1800CCF36
0x1800ccf1e  mov     qword ptr [rbx+140h], 0
0x1800ccf29  mov     rax, [rcx]
0x1800ccf2c  mov     rax, [rax+10h]
0x1800ccf30  call    j__guard_dispatch_icall
0x1800ccf35  nop
0x1800ccf36  mov     rcx, [rbx+138h]
0x1800ccf3d  test    rcx, rcx
0x1800ccf40  jz      short loc_1800CCF5A
0x1800ccf42  mov     qword ptr [rbx+138h], 0
0x1800ccf4d  mov     rax, [rcx]
0x1800ccf50  mov     rax, [rax+10h]
0x1800ccf54  call    j__guard_dispatch_icall
0x1800ccf59  nop
0x1800ccf5a  mov     rcx, [rbx+130h]
0x1800ccf61  test    rcx, rcx
0x1800ccf64  jz      short loc_1800CCF7E
0x1800ccf66  mov     qword ptr [rbx+130h], 0
0x1800ccf71  mov     rax, [rcx]
0x1800ccf74  mov     rax, [rax+10h]
0x1800ccf78  call    j__guard_dispatch_icall
0x1800ccf7d  nop
0x1800ccf7e  mov     rcx, [rbx+128h]
0x1800ccf85  test    rcx, rcx
0x1800ccf88  jz      short loc_1800CCFA2
0x1800ccf8a  mov     qword ptr [rbx+128h], 0
0x1800ccf95  mov     rax, [rcx]
0x1800ccf98  mov     rax, [rax+10h]
0x1800ccf9c  call    j__guard_dispatch_icall
0x1800ccfa1  nop
0x1800ccfa2  mov     rcx, [rbx+108h]
0x1800ccfa9  test    rcx, rcx
0x1800ccfac  jz      short loc_1800CCFBE
0x1800ccfae  mov     qword ptr [rbx+108h], 0
0x1800ccfb9  call    sub_18003DBC0
0x1800ccfbe  mov     rcx, [rbx+0E8h]; string
0x1800ccfc5  call    cs:WindowsDeleteString
0x1800ccfcb  mov     qword ptr [rbx+0E8h], 0
0x1800ccfd6  mov     rcx, [rbx+0E0h]; string
0x1800ccfdd  call    cs:WindowsDeleteString
0x1800ccfe3  mov     qword ptr [rbx+0E0h], 0
0x1800ccfee  mov     rcx, rsi; lpCriticalSection
0x1800ccff1  call    cs:__imp_DeleteCriticalSection
0x1800ccff7  lea     rcx, [rbx+70h]; lpCriticalSection
0x1800ccffb  call    cs:__imp_DeleteCriticalSection
0x1800cd001  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800cd005  call    cs:__imp_DeleteCriticalSection
0x1800cd00b  mov     rcx, rbx
0x1800cd00e  mov     rbx, [rsp+28h+arg_0]
0x1800cd013  mov     rsi, [rsp+28h+arg_8]
0x1800cd018  add     rsp, 20h
0x1800cd01c  pop     rdi
0x1800cd01d  jmp     sub_180017C34
```
