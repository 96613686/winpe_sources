# Windows::Compat::Inventory::Service::WinRtHost::~WinRtHost(void)

- ea: `0x1800c4244`
- end: `0x1800c4395`
- name: `??1WinRtHost@Service@Inventory@Compat@Windows@@UEAA@XZ`
- size: `337`
- prototype: `void __fastcall(Windows::Compat::Inventory::Service::WinRtHost *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c43e0`

## callees

- `0x18000fc68`
- `0x1800108d4`
- `0x180011334`
- `0x1800152d0`
- `0x1800c4244`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800c4318`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800c4318`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c42ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c42ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4298`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c42ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c42f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c42ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c42f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c42c2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c430c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c42c2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c430c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c42b9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c4303`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c42b9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c4303`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4328`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4328`
- `RPCRT4!RpcMgmtStopServerListening` at `0x1800c427f`
- `RPCRT4!RpcMgmtStopServerListening` at `0x1800c427f`

## string_xrefs

- `0x1800c434a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800c4267`: `Windows::Compat::Inventory::Service::WinRtHost::~WinRtHost`
- `0x1800c436f`: `Windows::Compat::Inventory::Service::WinRtHost::~WinRtHost`
- `0x1800c4386`: `onecore\base\appcompat\inventory\service\winrt\lib\winrthost.cpp`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::Service::WinRtHost::~WinRtHost(
        Windows::Compat::Inventory::Service::WinRtHost *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  struct _TP_TIMER *v6; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v8; // rbx
  void *v9; // rcx
  const char *v10; // r9
  unsigned int v11; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_QWORD *)this = &Windows::Compat::Inventory::Service::WinRtHost::`vftable';
  AslLogCallPrintf(3, "Windows::Compat::Inventory::Service::WinRtHost::~WinRtHost", 42, "Shutting down");
  if ( *((_DWORD *)this + 6) )
  {
    v4 = RpcMgmtStopServerListening(0);
    v5 = v4;
    if ( v4 )
    {
      AslLogCallPrintf(1, "Windows::Compat::Inventory::Service::WinRtHost::~WinRtHost", 46, "failed [%#x]", v4);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\winrt\\lib\\winrthost.cpp",
        (const char *)v5,
        v11);
    }
    v6 = (struct _TP_TIMER *)*((_QWORD *)this + 4);
    if ( v6 )
    {
      LastError = GetLastError();
      SetThreadpoolTimer(v6, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v6, 1);
      CloseThreadpoolTimer(v6);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 4) = 0;
    std::thread::join((Windows::Compat::Inventory::Service::WinRtHost *)((char *)this + 16));
  }
  v8 = (struct _TP_TIMER *)*((_QWORD *)this + 4);
  if ( v8 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 4), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v8, 1);
    CloseThreadpoolTimer(v8);
  }
  if ( *((_DWORD *)this + 6) )
  {
    _o_terminate(v3, v2);
    __debugbreak();
  }
  v9 = (void *)*((_QWORD *)this + 1);
  if ( v9 && !CloseHandle(v9) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v10);
  *(_QWORD *)this = &Windows::Compat::Inventory::Service::InvSvcTenant::`vftable';
}

```

## disassembly

```asm
0x1800c4244  push    rbx
0x1800c4246  push    rbp
0x1800c4247  push    rsi
0x1800c4248  push    rdi
0x1800c4249  sub     rsp, 38h
0x1800c424d  mov     rdi, rcx
0x1800c4250  lea     rax, ??_7WinRtHost@Service@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Service::WinRtHost::`vftable'
0x1800c4257  mov     [rcx], rax
0x1800c425a  lea     r9, aShuttingDown; "Shutting down"
0x1800c4261  mov     r8d, 2Ah ; '*'
0x1800c4267  lea     rdx, aWindowsCompatI_79; "Windows::Compat::Inventory::Service::Wi"...
0x1800c426e  lea     ecx, [r8-27h]
0x1800c4272  call    AslLogCallPrintf
0x1800c4277  cmp     dword ptr [rdi+18h], 0
0x1800c427b  jz      short loc_1800C42E1
0x1800c427d  xor     ecx, ecx; Binding
0x1800c427f  call    cs:__imp_RpcMgmtStopServerListening
0x1800c4285  mov     ebx, eax
0x1800c4287  test    eax, eax
0x1800c4289  jnz     loc_1800C435C
0x1800c428f  mov     rsi, [rdi+20h]
0x1800c4293  test    rsi, rsi
0x1800c4296  jz      short loc_1800C42D0
0x1800c4298  call    cs:__imp_GetLastError
0x1800c429e  mov     ebx, eax
0x1800c42a0  xor     r9d, r9d; msWindowLength
0x1800c42a3  xor     r8d, r8d; msPeriod
0x1800c42a6  xor     edx, edx; pftDueTime
0x1800c42a8  mov     rcx, rsi; pti
0x1800c42ab  call    cs:__imp_SetThreadpoolTimer
0x1800c42b1  mov     edx, 1; fCancelPendingCallbacks
0x1800c42b6  mov     rcx, rsi; pti
0x1800c42b9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800c42bf  mov     rcx, rsi; pti
0x1800c42c2  call    cs:__imp_CloseThreadpoolTimer
0x1800c42c8  mov     ecx, ebx; dwErrCode
0x1800c42ca  call    cs:__imp_SetLastError
0x1800c42d0  mov     qword ptr [rdi+20h], 0
0x1800c42d8  lea     rcx, [rdi+10h]; this
0x1800c42dc  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x1800c42e1  mov     rbx, [rdi+20h]
0x1800c42e5  test    rbx, rbx
0x1800c42e8  jz      short loc_1800C4312
0x1800c42ea  xor     r9d, r9d; msWindowLength
0x1800c42ed  xor     r8d, r8d; msPeriod
0x1800c42f0  xor     edx, edx; pftDueTime
0x1800c42f2  mov     rcx, rbx; pti
0x1800c42f5  call    cs:__imp_SetThreadpoolTimer
0x1800c42fb  mov     edx, 1; fCancelPendingCallbacks
0x1800c4300  mov     rcx, rbx; pti
0x1800c4303  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800c4309  mov     rcx, rbx; pti
0x1800c430c  call    cs:__imp_CloseThreadpoolTimer
0x1800c4312  cmp     dword ptr [rdi+18h], 0
0x1800c4316  jz      short loc_1800C431F
0x1800c4318  call    cs:__imp__o_terminate
0x1800c431e  int     3; Trap to Debugger
0x1800c431f  mov     rcx, [rdi+8]; hObject
0x1800c4323  test    rcx, rcx
0x1800c4326  jz      short loc_1800C4332
0x1800c4328  call    cs:__imp_CloseHandle
0x1800c432e  test    eax, eax
0x1800c4330  jz      short loc_1800C4345
0x1800c4332  lea     rax, ??_7InvSvcTenant@Service@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::Service::InvSvcTenant::`vftable'
0x1800c4339  mov     [rdi], rax
0x1800c433c  add     rsp, 38h
0x1800c4340  pop     rdi
0x1800c4341  pop     rsi
0x1800c4342  pop     rbp
0x1800c4343  pop     rbx
0x1800c4344  retn
0x1800c4345  mov     rcx, [rsp+58h]; this
0x1800c434a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c4351  mov     edx, 0A0Bh; void *
0x1800c4356  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800c435c  mov     [rsp+58h+var_38], ebx; unsigned int
0x1800c4360  lea     r9, aFailedX; "failed [%#x]"
0x1800c4367  mov     edi, 2Eh ; '.'
0x1800c436c  mov     r8d, edi
0x1800c436f  lea     rdx, aWindowsCompatI_79; "Windows::Compat::Inventory::Service::Wi"...
0x1800c4376  lea     ecx, [rdi-2Dh]
0x1800c4379  call    AslLogCallPrintf
0x1800c437e  mov     rcx, [rsp+58h]; this
0x1800c4383  mov     r9d, ebx; char *
0x1800c4386  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\se"...
0x1800c438d  mov     edx, edi; void *
0x1800c438f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
