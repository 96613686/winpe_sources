# Windows::Compat::Inventory::Service::BasicInventoryScheduler::AdjustPriority(TelemetryProvider const *,TelemetryProvider const *)

- ea: `0x18002f720`
- end: `0x18002f846`
- name: `?AdjustPriority@BasicInventoryScheduler@Service@Inventory@Compat@Windows@@MEAAXPEBVTelemetryProvider@@0@Z`
- size: `294`
- prototype: `void __fastcall(Windows::Compat::Inventory::Service::BasicInventoryScheduler *__hidden this, const struct TelemetryProvider *, const struct TelemetryProvider *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800108d4`
- `0x18002f720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f7b6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f7c9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f7b6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002f7c9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f76b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f7d5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f76b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002f7d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f75a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f75a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f747`
- `IPHLPAPI!NotifyNetworkConnectivityHintChange` at `0x18002f79e`
- `IPHLPAPI!NotifyNetworkConnectivityHintChange` at `0x18002f79e`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18002f752`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18002f752`

## string_xrefs

- `0x18002f81d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002f834`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002f7ef`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002f806`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::Service::BasicInventoryScheduler::AdjustPriority(
        Windows::Compat::Inventory::Service::BasicInventoryScheduler *this,
        const struct TelemetryProvider *a2,
        const struct TelemetryProvider *a3)
{
  _QWORD *v3; // rsi
  const struct TelemetryProvider *v4; // r14
  char *v5; // rbp
  DWORD LastError; // ebx
  const char *v8; // r9
  const char *v9; // r9
  void *v10; // rcx
  const char *v11; // r9
  const char *v12; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = (_QWORD *)((char *)this + 120);
  v4 = a3;
  v5 = (char *)*((_QWORD *)this + 15);
  if ( a2 )
  {
    if ( ((unsigned __int64)(v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      *v3 = 0;
      LOBYTE(a3) = 1;
      NotifyNetworkConnectivityHintChange(
        &Windows::Compat::Inventory::Service::BasicInventoryScheduler::PnetworkConnectivityHintChangeCallback,
        this,
        a3,
        (char *)this + 120);
    }
    if ( ((*v3 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 && !SetEvent(*((HANDLE *)this + 6)) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
  }
  else
  {
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CancelMibChangeNotify2(v5);
      SetLastError(LastError);
    }
    *v3 = 0;
    if ( !ResetEvent(*((HANDLE *)this + 6)) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA06,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v8);
  }
  v10 = (void *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    if ( !SetEvent(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v11);
  }
  else if ( !ResetEvent(v10) )
  {
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA06,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v12);
  }
}

```

## disassembly

```asm
0x18002f720  push    rbx
0x18002f722  push    rbp
0x18002f723  push    rsi
0x18002f724  push    rdi
0x18002f725  push    r14
0x18002f727  sub     rsp, 20h
0x18002f72b  lea     rsi, [rcx+78h]
0x18002f72f  mov     r14, r8
0x18002f732  mov     rbp, [rsi]
0x18002f735  mov     rdi, rcx
0x18002f738  test    rdx, rdx
0x18002f73b  jnz     short loc_18002F77B
0x18002f73d  lea     rax, [rbp-1]
0x18002f741  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f745  ja      short loc_18002F760
0x18002f747  call    cs:__imp_GetLastError
0x18002f74d  mov     rcx, rbp; NotificationHandle
0x18002f750  mov     ebx, eax
0x18002f752  call    cs:__imp_CancelMibChangeNotify2
0x18002f758  mov     ecx, ebx; dwErrCode
0x18002f75a  call    cs:__imp_SetLastError
0x18002f760  mov     qword ptr [rsi], 0
0x18002f767  mov     rcx, [rdi+30h]; hEvent
0x18002f76b  call    cs:__imp_ResetEvent
0x18002f771  test    eax, eax
0x18002f773  jz      loc_18002F801
0x18002f779  jmp     short loc_18002F7C0
0x18002f77b  lea     rax, [rbp+1]
0x18002f77f  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f785  jnz     short loc_18002F7A4
0x18002f787  mov     r9, rsi
0x18002f78a  mov     qword ptr [rsi], 0
0x18002f791  mov     r8b, 1
0x18002f794  lea     rcx, ?PnetworkConnectivityHintChangeCallback@BasicInventoryScheduler@Service@Inventory@Compat@Windows@@CAXPEAXU_NL_NETWORK_CONNECTIVITY_HINT@@@Z; Windows::Compat::Inventory::Service::BasicInventoryScheduler::PnetworkConnectivityHintChangeCallback(void *,_NL_NETWORK_CONNECTIVITY_HINT)
0x18002f79b  mov     rdx, rdi
0x18002f79e  call    cs:__imp_NotifyNetworkConnectivityHintChange
0x18002f7a4  mov     rax, [rsi]
0x18002f7a7  inc     rax
0x18002f7aa  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f7b0  jnz     short loc_18002F7C0
0x18002f7b2  mov     rcx, [rdi+30h]; hEvent
0x18002f7b6  call    cs:__imp_SetEvent
0x18002f7bc  test    eax, eax
0x18002f7be  jz      short loc_18002F82F
0x18002f7c0  mov     rcx, [rdi+38h]; hEvent
0x18002f7c4  test    r14, r14
0x18002f7c7  jz      short loc_18002F7D5
0x18002f7c9  call    cs:__imp_SetEvent
0x18002f7cf  test    eax, eax
0x18002f7d1  jz      short loc_18002F818
0x18002f7d3  jmp     short loc_18002F7DF
0x18002f7d5  call    cs:__imp_ResetEvent
0x18002f7db  test    eax, eax
0x18002f7dd  jz      short loc_18002F7EA
0x18002f7df  add     rsp, 20h
0x18002f7e3  pop     r14
0x18002f7e5  pop     rdi
0x18002f7e6  pop     rsi
0x18002f7e7  pop     rbp
0x18002f7e8  pop     rbx
0x18002f7e9  retn
0x18002f7ea  mov     rcx, [rsp+48h]; this
0x18002f7ef  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f7f6  mov     edx, 0A06h; void *
0x18002f7fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f801  mov     rcx, [rsp+48h]; this
0x18002f806  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f80d  mov     edx, 0A06h; void *
0x18002f812  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f818  mov     rcx, [rsp+48h]; this
0x18002f81d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f824  mov     edx, 0A01h; void *
0x18002f829  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f82f  mov     rcx, [rsp+48h]; this
0x18002f834  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f83b  mov     edx, 0A01h; void *
0x18002f840  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
