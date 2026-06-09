# Container::Manager::Hns::NetworkManager::Start(void)

- ea: `0x180189e48`
- end: `0x180189fd2`
- name: `?Start@NetworkManager@Hns@Manager@Container@@AEAAJXZ`
- size: `394`
- prototype: `__int64 __fastcall(Container::Manager::Hns::NetworkManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18018a088`

## callees

- `0x1800491e8`
- `0x1801260f0`
- `0x18018989c`
- `0x180189e48`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180189ee0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180189ee0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180189f25`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180189f5a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180189f25`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180189f5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180189e65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180189e65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180189e84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180189f6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180189e84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180189f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180189f14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180189f14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180189f33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180189f33`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnRegisterServiceCallback` at `0x180189ea5`
- `ext-ms-win-hyperv-computenetwork-l1-1-0!HcnRegisterServiceCallback` at `0x180189ea5`

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
0x180189e48  mov     [rsp+arg_8], rbx
0x180189e4d  mov     [rsp+arg_10], rsi
0x180189e52  push    rdi
0x180189e53  push    r14
0x180189e55  push    r15
0x180189e57  sub     rsp, 30h
0x180189e5b  mov     rsi, rcx
0x180189e5e  lea     r14, [rcx+18h]
0x180189e62  mov     rcx, r14; SRWLock
0x180189e65  call    cs:__imp_AcquireSRWLockExclusive
0x180189e6c  nop     dword ptr [rax+rax+00h]
0x180189e71  mov     [rsp+48h+arg_0], r14
0x180189e76  cmp     dword ptr [rsi+0Ch], 1
0x180189e7a  jnz     short loc_180189E97
0x180189e7c  test    r14, r14
0x180189e7f  jz      short loc_180189E90
0x180189e81  mov     rcx, r14; SRWLock
0x180189e84  call    cs:__imp_ReleaseSRWLockExclusive
0x180189e8b  nop     dword ptr [rax+rax+00h]
0x180189e90  xor     eax, eax
0x180189e92  jmp     loc_180189F83
0x180189e97  lea     r8, [rsi+68h]; CallbackHandle
0x180189e9b  mov     rdx, rsi; Context
0x180189e9e  lea     rcx, ?HcnCallback@NetworkManager@Hns@Manager@Container@@CAXKPEAXJPEBG@Z; Callback
0x180189ea5  call    cs:__imp_HcnRegisterServiceCallback
0x180189eac  nop     dword ptr [rax+rax+00h]
0x180189eb1  mov     rcx, [rsp+48h]; this
0x180189eb6  test    eax, eax
0x180189eb8  js      loc_180189F98
0x180189ebe  mov     rcx, rsi; this
0x180189ec1  call    ?RefreshNetworkCache@NetworkManager@Hns@Manager@Container@@AEAAJXZ; Container::Manager::Hns::NetworkManager::RefreshNetworkCache(void)
0x180189ec6  mov     rcx, [rsp+48h]; this
0x180189ecb  test    eax, eax
0x180189ecd  js      loc_180189FAC
0x180189ed3  xor     r8d, r8d; pcbe
0x180189ed6  mov     rdx, rsi; pv
0x180189ed9  lea     rcx, ?RetryHcnServiceConnectionTimerCallback@NetworkManager@Hns@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180189ee0  call    cs:__imp_CreateThreadpoolTimer
0x180189ee7  nop     dword ptr [rax+rax+00h]
0x180189eec  mov     rbx, rax
0x180189eef  mov     [rsp+48h+var_28], rax
0x180189ef4  mov     rcx, [rsp+48h]; this
0x180189ef9  test    rax, rax
0x180189efc  jz      loc_180189FC1
0x180189f02  lea     rax, [rsp+48h+var_28]
0x180189f07  cmp     rsi, rax
0x180189f0a  jz      short loc_180189F48
0x180189f0c  mov     r15, [rsi]
0x180189f0f  test    r15, r15
0x180189f12  jz      short loc_180189F3F
0x180189f14  call    cs:__imp_GetLastError
0x180189f1b  nop     dword ptr [rax+rax+00h]
0x180189f20  mov     edi, eax
0x180189f22  mov     rcx, r15; pti
0x180189f25  call    cs:__imp_CloseThreadpoolTimer
0x180189f2c  nop     dword ptr [rax+rax+00h]
0x180189f31  mov     ecx, edi; dwErrCode
0x180189f33  call    cs:__imp_SetLastError
0x180189f3a  nop     dword ptr [rax+rax+00h]
0x180189f3f  mov     [rsi], rbx
0x180189f42  xor     ebx, ebx
0x180189f44  xor     eax, eax
0x180189f46  jmp     short loc_180189F4B
0x180189f48  mov     rax, rbx
0x180189f4b  mov     dword ptr [rsi+0Ch], 1
0x180189f52  test    rax, rax
0x180189f55  jz      short loc_180189F67
0x180189f57  mov     rcx, rbx; pti
0x180189f5a  call    cs:__imp_CloseThreadpoolTimer
0x180189f61  nop     dword ptr [rax+rax+00h]
0x180189f66  nop
0x180189f67  test    r14, r14
0x180189f6a  jz      short loc_180189F7B
0x180189f6c  mov     rcx, r14; SRWLock
0x180189f6f  call    cs:__imp_ReleaseSRWLockExclusive
0x180189f76  nop     dword ptr [rax+rax+00h]
0x180189f7b  xor     eax, eax
0x180189f7d  jmp     short loc_180189F83
0x180189f7f  mov     eax, dword ptr [rsp+48h+arg_0]
0x180189f83  mov     rbx, [rsp+48h+arg_8]
0x180189f88  mov     rsi, [rsp+48h+arg_10]
0x180189f8d  add     rsp, 30h
0x180189f91  pop     r15
0x180189f93  pop     r14
0x180189f95  pop     rdi
0x180189f96  retn
0x180189f98  mov     r9d, eax; char *
0x180189f9b  lea     r8, aOnecoreBaseGen_78; "onecore\\base\\gendrv\\silos\\clem\\net"...
0x180189fa2  mov     edx, 52h ; 'R'; void *
0x180189fa7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180189fac  mov     r9d, eax; char *
0x180189faf  lea     r8, aOnecoreBaseGen_78; "onecore\\base\\gendrv\\silos\\clem\\net"...
0x180189fb6  mov     edx, 56h ; 'V'; void *
0x180189fbb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180189fc1  lea     r8, aOnecoreBaseGen_78; "onecore\\base\\gendrv\\silos\\clem\\net"...
0x180189fc8  lea     edx, [rax+5Eh]; void *
0x180189fcb  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
