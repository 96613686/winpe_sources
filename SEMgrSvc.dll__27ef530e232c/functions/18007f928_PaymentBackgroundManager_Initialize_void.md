# PaymentBackgroundManager::Initialize(void)

- ea: `0x18007f928`
- end: `0x18007faf3`
- name: `?Initialize@PaymentBackgroundManager@@IEAAJXZ`
- size: `459`
- prototype: `__int64 __fastcall(PaymentBackgroundManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180011a64`

## callees

- `0x18000c944`
- `0x18000c964`
- `0x18007f928`
- `0x18007fdc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fa5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007fa5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007f987`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007fa91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007f987`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007fa91`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007fa80`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007fa80`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007fa4d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007fa4d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007fa72`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007fae2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007fa72`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007fae2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007fa89`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007fa89`
- `ntdll!RtlPublishWnfStateData` at `0x18007fa29`
- `ntdll!RtlPublishWnfStateData` at `0x18007fa29`
- `BrokerLib!BrInitializeBrokerInstance2` at `0x18007f9db`
- `BrokerLib!BrInitializeBrokerInstance2` at `0x18007f9db`
- `BrokerLib!BrCreateBrokerInstance2` at `0x18007f9b2`
- `BrokerLib!BrCreateBrokerInstance2` at `0x18007f9b2`
- `BrokerLib!BrDeleteBrokerInstance` at `0x18007f97f`
- `BrokerLib!BrDeleteBrokerInstance` at `0x18007f97f`

## string_xrefs

- `0x18007f9fd`: `onecoreuap\ds\nfc\product\payment\service\lib\paymentbackgroundmanager.cpp`
- `0x18007faa8`: `onecoreuap\ds\nfc\product\payment\service\lib\paymentbackgroundmanager.cpp`

## pseudocode

```c
__int64 __fastcall PaymentBackgroundManager::Initialize(PaymentBackgroundManager *this)
{
  _QWORD *v2; // rsi
  __int64 v3; // rbp
  DWORD LastError; // ebx
  int BrokerInstance2; // eax
  int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  int v9; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v11; // r9
  struct _TP_TIMER *v12; // rbp
  struct _TP_TIMER *v13; // rsi
  DWORD v14; // ebx
  int v16; // [rsp+20h] [rbp-68h]
  _QWORD v17[11]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+90h] [rbp+8h] BYREF

  v17[0] = &PaymentBackgroundManager::OnCreateBrokerEvent;
  v2 = (_QWORD *)((char *)this + 48);
  v3 = *((_QWORD *)this + 6);
  v17[1] = &PaymentBackgroundManager::OnDeleteBrokerEvent;
  v17[2] = &PaymentBackgroundManager::OnEnableBrokerEvent;
  v17[3] = &PaymentBackgroundManager::OnDisableBrokerEvent;
  v17[4] = 0;
  if ( v3 )
  {
    LastError = GetLastError();
    BrDeleteBrokerInstance(v3);
    SetLastError(LastError);
  }
  *v2 = 0;
  v16 = (int)v2;
  BrokerInstance2 = BrCreateBrokerInstance2(v17, qword_1801155A0, 1, &dword_18011559C);
  v6 = BrokerInstance2;
  if ( BrokerInstance2 > 0 )
    v6 = (unsigned __int16)BrokerInstance2 | 0x80070000;
  if ( v6 < 0 )
  {
    v7 = 78;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\paymentbackgroundmanager.cpp",
      (const char *)(unsigned int)v6,
      v16);
LABEL_18:
    PaymentBackgroundManager::Uninitialize(this);
    return (unsigned int)v6;
  }
  v8 = BrInitializeBrokerInstance2(*v2, 0, 0);
  v6 = v8;
  if ( v8 > 0 )
    v6 = (unsigned __int16)v8 | 0x80070000;
  if ( v6 < 0 )
  {
    v7 = 81;
    goto LABEL_11;
  }
  v16 = 0;
  v9 = RtlPublishWnfStateData(WNF_PAY_CANMAKEPAYMENT_BROKER_READY, 0, 0, 0);
  v6 = v9 | 0x10000000;
  if ( v9 < 0 )
  {
    v7 = 86;
    goto LABEL_11;
  }
  ThreadpoolTimer = CreateThreadpoolTimer(
                      PaymentBackgroundManager::Initialize_::_2_::_lambda_2_::_lambda_invoker_cdecl_,
                      this,
                      0);
  v12 = (struct _TP_TIMER *)*((_QWORD *)this + 8);
  v13 = ThreadpoolTimer;
  if ( v12 )
  {
    v14 = GetLastError();
    SetThreadpoolTimer(v12, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v12, 1);
    CloseThreadpoolTimer(v12);
    SetLastError(v14);
  }
  *((_QWORD *)this + 8) = v13;
  if ( !v13 )
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x60,
           (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\paymentbackgroundmanager.cpp",
           v11);
    goto LABEL_18;
  }
  pftDueTime = (struct _FILETIME)-300000000LL;
  SetThreadpoolTimer(v13, &pftDueTime, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18007f928  mov     r11, rsp
0x18007f92b  push    rbx
0x18007f92c  push    rbp
0x18007f92d  push    rsi
0x18007f92e  push    rdi
0x18007f92f  sub     rsp, 68h
0x18007f933  lea     rax, ?OnCreateBrokerEvent@PaymentBackgroundManager@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAU_BR_EVENT_PARAMETERS@@PEBGPEAX55PEAPEAXPEAKPEAU_BR_NEW_EVENT_INFORMATION@@@Z; PaymentBackgroundManager::OnCreateBrokerEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,_BR_EVENT_PARAMETERS *,ushort const *,void *,void *,void *,void * *,ulong *,_BR_NEW_EVENT_INFORMATION *)
0x18007f93a  mov     rdi, rcx
0x18007f93d  mov     [r11-58h], rax
0x18007f941  lea     rsi, [rcx+30h]
0x18007f945  mov     rbp, [rsi]
0x18007f948  lea     rax, ?OnDeleteBrokerEvent@PaymentBackgroundManager@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; PaymentBackgroundManager::OnDeleteBrokerEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18007f94f  mov     [r11-50h], rax
0x18007f953  lea     rax, ?OnEnableBrokerEvent@PaymentBackgroundManager@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; PaymentBackgroundManager::OnEnableBrokerEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18007f95a  mov     [r11-48h], rax
0x18007f95e  lea     rax, ?OnDisableBrokerEvent@PaymentBackgroundManager@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z; PaymentBackgroundManager::OnDisableBrokerEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)
0x18007f965  mov     [r11-40h], rax
0x18007f969  xor     eax, eax
0x18007f96b  mov     [r11-38h], rax
0x18007f96f  test    rbp, rbp
0x18007f972  jz      short loc_18007F98D
0x18007f974  call    cs:__imp_GetLastError
0x18007f97a  mov     rcx, rbp
0x18007f97d  mov     ebx, eax
0x18007f97f  call    cs:__imp_BrDeleteBrokerInstance
0x18007f985  mov     ecx, ebx; dwErrCode
0x18007f987  call    cs:__imp_SetLastError
0x18007f98d  lea     r9, dword_18011559C
0x18007f994  mov     qword ptr [rsi], 0
0x18007f99b  mov     r8d, 1
0x18007f9a1  mov     qword ptr [rsp+88h+var_68], rsi; int
0x18007f9a6  lea     rdx, qword_1801155A0
0x18007f9ad  lea     rcx, [rsp+88h+var_58]
0x18007f9b2  call    cs:__imp_BrCreateBrokerInstance2
0x18007f9b8  mov     ebx, eax
0x18007f9ba  mov     ebp, 80070000h
0x18007f9bf  test    eax, eax
0x18007f9c1  jle     short loc_18007F9C8
0x18007f9c3  movzx   ebx, ax
0x18007f9c6  or      ebx, ebp
0x18007f9c8  test    ebx, ebx
0x18007f9ca  jns     short loc_18007F9D3
0x18007f9cc  mov     edx, 4Eh ; 'N'
0x18007f9d1  jmp     short loc_18007F9F5
0x18007f9d3  mov     rcx, [rsi]
0x18007f9d6  xor     r8d, r8d
0x18007f9d9  xor     edx, edx
0x18007f9db  call    cs:__imp_BrInitializeBrokerInstance2
0x18007f9e1  mov     ebx, eax
0x18007f9e3  test    eax, eax
0x18007f9e5  jle     short loc_18007F9EC
0x18007f9e7  movzx   ebx, ax
0x18007f9ea  or      ebx, ebp
0x18007f9ec  test    ebx, ebx
0x18007f9ee  jns     short loc_18007FA11
0x18007f9f0  mov     edx, 51h ; 'Q'; void *
0x18007f9f5  mov     rcx, [rsp+88h]; this
0x18007f9fd  lea     r8, aOnecoreuapDsNf_36; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x18007fa04  mov     r9d, ebx; char *
0x18007fa07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fa0c  jmp     loc_18007FAB9
0x18007fa11  mov     rcx, cs:WNF_PAY_CANMAKEPAYMENT_BROKER_READY
0x18007fa18  xor     r9d, r9d
0x18007fa1b  xor     r8d, r8d
0x18007fa1e  mov     qword ptr [rsp+88h+var_68], 0
0x18007fa27  xor     edx, edx
0x18007fa29  call    cs:__imp_RtlPublishWnfStateData
0x18007fa2f  mov     ebx, eax
0x18007fa31  or      ebx, 10000000h
0x18007fa37  jge     short loc_18007FA40
0x18007fa39  mov     edx, 56h ; 'V'
0x18007fa3e  jmp     short loc_18007F9F5
0x18007fa40  xor     r8d, r8d; pcbe
0x18007fa43  lea     rcx, _PaymentBackgroundManager__Initialize____2____lambda_2____lambda_invoker_cdecl_; pfnti
0x18007fa4a  mov     rdx, rdi; pv
0x18007fa4d  call    cs:__imp_CreateThreadpoolTimer
0x18007fa53  mov     rbp, [rdi+40h]
0x18007fa57  mov     rsi, rax
0x18007fa5a  test    rbp, rbp
0x18007fa5d  jz      short loc_18007FA97
0x18007fa5f  call    cs:__imp_GetLastError
0x18007fa65  xor     r9d, r9d; msWindowLength
0x18007fa68  xor     r8d, r8d; msPeriod
0x18007fa6b  xor     edx, edx; pftDueTime
0x18007fa6d  mov     rcx, rbp; pti
0x18007fa70  mov     ebx, eax
0x18007fa72  call    cs:__imp_SetThreadpoolTimer
0x18007fa78  mov     edx, 1; fCancelPendingCallbacks
0x18007fa7d  mov     rcx, rbp; pti
0x18007fa80  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007fa86  mov     rcx, rbp; pti
0x18007fa89  call    cs:__imp_CloseThreadpoolTimer
0x18007fa8f  mov     ecx, ebx; dwErrCode
0x18007fa91  call    cs:__imp_SetLastError
0x18007fa97  mov     [rdi+40h], rsi
0x18007fa9b  test    rsi, rsi
0x18007fa9e  jnz     short loc_18007FAC5
0x18007faa0  mov     rcx, [rsp+88h]; this
0x18007faa8  lea     r8, aOnecoreuapDsNf_36; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x18007faaf  lea     edx, [rsi+60h]; void *
0x18007fab2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007fab7  mov     ebx, eax
0x18007fab9  mov     rcx, rdi; this
0x18007fabc  call    ?Uninitialize@PaymentBackgroundManager@@IEAAXXZ; PaymentBackgroundManager::Uninitialize(void)
0x18007fac1  mov     eax, ebx
0x18007fac3  jmp     short loc_18007FAEA
0x18007fac5  xor     r9d, r9d; msWindowLength
0x18007fac8  mov     qword ptr [rsp+88h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x18007fad4  xor     r8d, r8d; msPeriod
0x18007fad7  lea     rdx, [rsp+88h+pftDueTime]; pftDueTime
0x18007fadf  mov     rcx, rsi; pti
0x18007fae2  call    cs:__imp_SetThreadpoolTimer
0x18007fae8  xor     eax, eax
0x18007faea  add     rsp, 68h
0x18007faee  pop     rdi
0x18007faef  pop     rsi
0x18007faf0  pop     rbp
0x18007faf1  pop     rbx
0x18007faf2  retn
```
