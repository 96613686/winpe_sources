# Container::Manager::Hns::NetworkManager::Start(void)

- ea: `0x180189cd8`
- end: `0x180189e62`
- name: `?Start@NetworkManager@Hns@Manager@Container@@AEAAJXZ`
- size: `394`
- prototype: `__int64 __fastcall(Container::Manager::Hns::NetworkManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180189f18`

## callees

- `0x1800491e8`
- `0x1801260f0`
- `0x18018972c`
- `0x180189cd8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180189d70`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180189d70`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180189db5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180189dea`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180189db5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180189dea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180189cf5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180189cf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180189d14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180189dff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180189d14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180189dff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180189da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180189da4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180189dc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180189dc3`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnRegisterServiceCallback` at `0x180189d35`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnRegisterServiceCallback` at `0x180189d35`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Container::Manager::Hns::NetworkManager::Start(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // r14
  __int64 result; // rax
  HRESULT v4; // eax
  int refreshed; // eax
  struct _TP_TIMER *ThreadpoolTimer; // rbx
  const char *v7; // r9
  struct _TP_TIMER *Ptr; // r15
  DWORD LastError; // edi
  struct _TP_TIMER *v10; // rax
  struct _TP_TIMER *v11; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = this + 3;
  AcquireSRWLockExclusive(this + 3);
  if ( HIDWORD(this[1].Ptr) == 1 )
  {
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return 0;
  }
  else
  {
    v4 = HcnRegisterServiceCallback(Container::Manager::Hns::NetworkManager::HcnCallback, this, &this[13].Ptr);
    try
    {
      if ( v4 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\network\\lib\\networkmanager.cpp",
          (const char *)(unsigned int)v4,
          (int)v11);
      refreshed = Container::Manager::Hns::NetworkManager::RefreshNetworkCache((Container::Manager::Hns::NetworkManager *)this);
      if ( refreshed < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x56,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\network\\lib\\networkmanager.cpp",
          (const char *)(unsigned int)refreshed,
          (int)v11);
      ThreadpoolTimer = CreateThreadpoolTimer(
                          Container::Manager::Hns::NetworkManager::RetryHcnServiceConnectionTimerCallback,
                          this,
                          0);
      v11 = ThreadpoolTimer;
      if ( !ThreadpoolTimer )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x5E,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\network\\lib\\networkmanager.cpp",
          v7);
      if ( this == (RTL_SRWLOCK *)&v11 )
      {
        v10 = ThreadpoolTimer;
      }
      else
      {
        Ptr = (struct _TP_TIMER *)this->Ptr;
        if ( this->Ptr )
        {
          LastError = GetLastError();
          CloseThreadpoolTimer(Ptr);
          SetLastError(LastError);
        }
        this->Ptr = ThreadpoolTimer;
        ThreadpoolTimer = 0;
        v10 = 0;
      }
      HIDWORD(this[1].Ptr) = 1;
      if ( v10 )
        CloseThreadpoolTimer(ThreadpoolTimer);
      if ( v2 )
        ReleaseSRWLockExclusive(v2);
      result = 0;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x65,
                             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\network\\lib\\networkmanager.cpp",
                             v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180189cd8  mov     [rsp+arg_8], rbx
0x180189cdd  mov     [rsp+arg_10], rsi
0x180189ce2  push    rdi
0x180189ce3  push    r14
0x180189ce5  push    r15
0x180189ce7  sub     rsp, 30h
0x180189ceb  mov     rsi, rcx
0x180189cee  lea     r14, [rcx+18h]
0x180189cf2  mov     rcx, r14; SRWLock
0x180189cf5  call    cs:__imp_AcquireSRWLockExclusive
0x180189cfc  nop     dword ptr [rax+rax+00h]
0x180189d01  mov     [rsp+48h+arg_0], r14
0x180189d06  cmp     dword ptr [rsi+0Ch], 1
0x180189d0a  jnz     short loc_180189D27
0x180189d0c  test    r14, r14
0x180189d0f  jz      short loc_180189D20
0x180189d11  mov     rcx, r14; SRWLock
0x180189d14  call    cs:__imp_ReleaseSRWLockExclusive
0x180189d1b  nop     dword ptr [rax+rax+00h]
0x180189d20  xor     eax, eax
0x180189d22  jmp     loc_180189E13
0x180189d27  lea     r8, [rsi+68h]; CallbackHandle
0x180189d2b  mov     rdx, rsi; Context
0x180189d2e  lea     rcx, ?HcnCallback@NetworkManager@Hns@Manager@Container@@CAXKPEAXJPEBG@Z; Callback
0x180189d35  call    cs:__imp_HcnRegisterServiceCallback
0x180189d3c  nop     dword ptr [rax+rax+00h]
0x180189d41  mov     rcx, [rsp+48h]; this
0x180189d46  test    eax, eax
0x180189d48  js      loc_180189E28
0x180189d4e  mov     rcx, rsi; this
0x180189d51  call    ?RefreshNetworkCache@NetworkManager@Hns@Manager@Container@@AEAAJXZ; Container::Manager::Hns::NetworkManager::RefreshNetworkCache(void)
0x180189d56  mov     rcx, [rsp+48h]; this
0x180189d5b  test    eax, eax
0x180189d5d  js      loc_180189E3C
0x180189d63  xor     r8d, r8d; pcbe
0x180189d66  mov     rdx, rsi; pv
0x180189d69  lea     rcx, ?RetryHcnServiceConnectionTimerCallback@NetworkManager@Hns@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180189d70  call    cs:__imp_CreateThreadpoolTimer
0x180189d77  nop     dword ptr [rax+rax+00h]
0x180189d7c  mov     rbx, rax
0x180189d7f  mov     [rsp+48h+var_28], rax
0x180189d84  mov     rcx, [rsp+48h]; this
0x180189d89  test    rax, rax
0x180189d8c  jz      loc_180189E51
0x180189d92  lea     rax, [rsp+48h+var_28]
0x180189d97  cmp     rsi, rax
0x180189d9a  jz      short loc_180189DD8
0x180189d9c  mov     r15, [rsi]
0x180189d9f  test    r15, r15
0x180189da2  jz      short loc_180189DCF
0x180189da4  call    cs:__imp_GetLastError
0x180189dab  nop     dword ptr [rax+rax+00h]
0x180189db0  mov     edi, eax
0x180189db2  mov     rcx, r15; pti
0x180189db5  call    cs:__imp_CloseThreadpoolTimer
0x180189dbc  nop     dword ptr [rax+rax+00h]
0x180189dc1  mov     ecx, edi; dwErrCode
0x180189dc3  call    cs:__imp_SetLastError
0x180189dca  nop     dword ptr [rax+rax+00h]
0x180189dcf  mov     [rsi], rbx
0x180189dd2  xor     ebx, ebx
0x180189dd4  xor     eax, eax
0x180189dd6  jmp     short loc_180189DDB
0x180189dd8  mov     rax, rbx
0x180189ddb  mov     dword ptr [rsi+0Ch], 1
0x180189de2  test    rax, rax
0x180189de5  jz      short loc_180189DF7
0x180189de7  mov     rcx, rbx; pti
0x180189dea  call    cs:__imp_CloseThreadpoolTimer
0x180189df1  nop     dword ptr [rax+rax+00h]
0x180189df6  nop
0x180189df7  test    r14, r14
0x180189dfa  jz      short loc_180189E0B
0x180189dfc  mov     rcx, r14; SRWLock
0x180189dff  call    cs:__imp_ReleaseSRWLockExclusive
0x180189e06  nop     dword ptr [rax+rax+00h]
0x180189e0b  xor     eax, eax
0x180189e0d  jmp     short loc_180189E13
0x180189e0f  mov     eax, dword ptr [rsp+48h+arg_0]
0x180189e13  mov     rbx, [rsp+48h+arg_8]
0x180189e18  mov     rsi, [rsp+48h+arg_10]
0x180189e1d  add     rsp, 30h
0x180189e21  pop     r15
0x180189e23  pop     r14
0x180189e25  pop     rdi
0x180189e26  retn
0x180189e28  mov     r9d, eax; char *
0x180189e2b  lea     r8, aOnecoreBaseGen_78; "onecore\\base\\gendrv\\silos\\clem\\net"...
0x180189e32  mov     edx, 52h ; 'R'; void *
0x180189e37  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180189e3c  mov     r9d, eax; char *
0x180189e3f  lea     r8, aOnecoreBaseGen_78; "onecore\\base\\gendrv\\silos\\clem\\net"...
0x180189e46  mov     edx, 56h ; 'V'; void *
0x180189e4b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180189e51  lea     r8, aOnecoreBaseGen_78; "onecore\\base\\gendrv\\silos\\clem\\net"...
0x180189e58  lea     edx, [rax+5Eh]; void *
0x180189e5b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
