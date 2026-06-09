# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x14000766c`
- end: `0x140007700`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `148`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003970`
- `0x1400160f0`

## callees

- `0x14000766c`
- `0x140007d1c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1400076ea`
- `KERNEL32!SetLastError` at `0x1400076ea`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400076d9`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400076d9`
- `KERNEL32!GetLastError` at `0x1400076b8`
- `KERNEL32!GetLastError` at `0x1400076b8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400076ad`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400076ad`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400076e2`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400076e2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140007697`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140007697`
- `KERNEL32!SetThreadpoolTimer` at `0x1400076cb`
- `KERNEL32!SetThreadpoolTimer` at `0x1400076cb`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  struct _TP_TIMER *Ptr; // rsi
  DWORD LastError; // ebx

  LODWORD(this->Ptr) = 0;
  v1 = this + 1;
  Ptr = (struct _TP_TIMER *)this[2].Ptr;
  this[2].Ptr = 0;
  AcquireSRWLockExclusive(this + 1);
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  if ( Ptr )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(Ptr, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(Ptr, 1);
    CloseThreadpoolTimer(Ptr);
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x14000766c  mov     [rsp+arg_0], rbx
0x140007671  mov     [rsp+arg_8], rsi
0x140007676  push    rdi
0x140007677  sub     rsp, 20h
0x14000767b  mov     dword ptr [rcx], 0
0x140007681  lea     rdi, [rcx+8]
0x140007685  mov     rsi, [rcx+10h]
0x140007689  mov     rbx, rcx
0x14000768c  mov     qword ptr [rcx+10h], 0
0x140007694  mov     rcx, rdi; SRWLock
0x140007697  call    cs:__imp_AcquireSRWLockExclusive
0x14000769d  mov     rcx, rbx
0x1400076a0  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x1400076a5  test    rdi, rdi
0x1400076a8  jz      short loc_1400076B3
0x1400076aa  mov     rcx, rdi; SRWLock
0x1400076ad  call    cs:__imp_ReleaseSRWLockExclusive
0x1400076b3  test    rsi, rsi
0x1400076b6  jz      short loc_1400076F0
0x1400076b8  call    cs:__imp_GetLastError
0x1400076be  xor     r9d, r9d; msWindowLength
0x1400076c1  xor     r8d, r8d; msPeriod
0x1400076c4  xor     edx, edx; pftDueTime
0x1400076c6  mov     rcx, rsi; pti
0x1400076c9  mov     ebx, eax
0x1400076cb  call    cs:__imp_SetThreadpoolTimer
0x1400076d1  mov     edx, 1; fCancelPendingCallbacks
0x1400076d6  mov     rcx, rsi; pti
0x1400076d9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400076df  mov     rcx, rsi; pti
0x1400076e2  call    cs:__imp_CloseThreadpoolTimer
0x1400076e8  mov     ecx, ebx; dwErrCode
0x1400076ea  call    cs:__imp_SetLastError
0x1400076f0  mov     rbx, [rsp+28h+arg_0]
0x1400076f5  mov     rsi, [rsp+28h+arg_8]
0x1400076fa  add     rsp, 20h
0x1400076fe  pop     rdi
0x1400076ff  retn
```
