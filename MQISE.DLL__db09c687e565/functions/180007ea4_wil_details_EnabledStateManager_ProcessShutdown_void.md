# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x180007ea4`
- end: `0x180007f3e`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `154`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003a70`
- `0x180010010`

## callees

- `0x180007ea4`
- `0x180008514`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x180007f1e`
- `KERNEL32!CloseThreadpoolTimer` at `0x180007f1e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180007f14`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180007f14`
- `KERNEL32!SetThreadpoolTimer` at `0x180007f05`
- `KERNEL32!SetThreadpoolTimer` at `0x180007f05`
- `KERNEL32!SetLastError` at `0x180007f27`
- `KERNEL32!SetLastError` at `0x180007f27`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007ee6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007ee6`
- `KERNEL32!GetLastError` at `0x180007ef2`
- `KERNEL32!GetLastError` at `0x180007ef2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007ecf`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007ecf`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(RTL_SRWLOCK *this)
{
  struct _TP_TIMER *Ptr; // rsi
  RTL_SRWLOCK *v3; // rdi
  DWORD LastError; // ebx

  LODWORD(this->Ptr) = 0;
  Ptr = (struct _TP_TIMER *)this[2].Ptr;
  this[2].Ptr = 0;
  v3 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  if ( v3 )
    ReleaseSRWLockExclusive(v3);
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
0x180007ea4  mov     [rsp+arg_0], rbx
0x180007ea9  mov     [rsp+arg_8], rsi
0x180007eae  push    rdi
0x180007eaf  sub     rsp, 20h
0x180007eb3  mov     rbx, rcx
0x180007eb6  mov     dword ptr [rcx], 0
0x180007ebc  mov     rsi, [rcx+10h]
0x180007ec0  mov     qword ptr [rcx+10h], 0
0x180007ec8  lea     rdi, [rcx+8]
0x180007ecc  mov     rcx, rdi; SRWLock
0x180007ecf  call    cs:__imp_AcquireSRWLockExclusive
0x180007ed5  nop
0x180007ed6  mov     rcx, rbx
0x180007ed9  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x180007ede  test    rdi, rdi
0x180007ee1  jz      short loc_180007EED
0x180007ee3  mov     rcx, rdi; SRWLock
0x180007ee6  call    cs:__imp_ReleaseSRWLockExclusive
0x180007eec  nop
0x180007eed  test    rsi, rsi
0x180007ef0  jz      short loc_180007F2E
0x180007ef2  call    cs:__imp_GetLastError
0x180007ef8  mov     ebx, eax
0x180007efa  xor     r9d, r9d; msWindowLength
0x180007efd  xor     r8d, r8d; msPeriod
0x180007f00  xor     edx, edx; pftDueTime
0x180007f02  mov     rcx, rsi; pti
0x180007f05  call    cs:__imp_SetThreadpoolTimer
0x180007f0b  nop
0x180007f0c  mov     edx, 1; fCancelPendingCallbacks
0x180007f11  mov     rcx, rsi; pti
0x180007f14  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007f1a  nop
0x180007f1b  mov     rcx, rsi; pti
0x180007f1e  call    cs:__imp_CloseThreadpoolTimer
0x180007f24  nop
0x180007f25  mov     ecx, ebx; dwErrCode
0x180007f27  call    cs:__imp_SetLastError
0x180007f2d  nop
0x180007f2e  mov     rbx, [rsp+28h+arg_0]
0x180007f33  mov     rsi, [rsp+28h+arg_8]
0x180007f38  add     rsp, 20h
0x180007f3c  pop     rdi
0x180007f3d  retn
```
