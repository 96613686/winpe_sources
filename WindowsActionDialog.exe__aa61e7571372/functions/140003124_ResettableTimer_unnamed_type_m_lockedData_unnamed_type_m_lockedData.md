# ResettableTimer::_unnamed_type_m_lockedData_::__unnamed_type_m_lockedData_

- ea: `0x140003124`
- end: `0x140003194`
- name: `ResettableTimer::_unnamed_type_m_lockedData_::__unnamed_type_m_lockedData_`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003524`
- `0x1400094a5`

## callees

- `0x140003124`
- `0x14000a010`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x140003145`
- `KERNEL32!SetThreadpoolTimer` at `0x140003145`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000315c`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000315c`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003153`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003153`

## pseudocode

```c
void __fastcall ResettableTimer::_unnamed_type_m_lockedData_::__unnamed_type_m_lockedData_(__int64 a1, __int64 a2)
{
  struct _TP_TIMER *v2; // rbx
  __int64 v4; // rcx
  __int64 v5; // rdi

  v2 = *(struct _TP_TIMER **)(a1 + 88);
  if ( v2 )
  {
    SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 88), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
  }
  v4 = *(_QWORD *)(a1 + 64);
  v5 = a1 + 8;
  if ( v4 )
  {
    LOBYTE(a2) = v4 != v5;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, a2);
    *(_QWORD *)(v5 + 56) = 0;
  }
}

```

## disassembly

```asm
0x140003124  mov     [rsp+arg_0], rbx
0x140003129  push    rdi
0x14000312a  sub     rsp, 20h
0x14000312e  mov     rbx, [rcx+58h]
0x140003132  mov     rdi, rcx
0x140003135  test    rbx, rbx
0x140003138  jz      short loc_140003162
0x14000313a  xor     r9d, r9d; msWindowLength
0x14000313d  xor     r8d, r8d; msPeriod
0x140003140  xor     edx, edx; pftDueTime
0x140003142  mov     rcx, rbx; pti
0x140003145  call    cs:__imp_SetThreadpoolTimer
0x14000314b  mov     edx, 1; fCancelPendingCallbacks
0x140003150  mov     rcx, rbx; pti
0x140003153  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003159  mov     rcx, rbx; pti
0x14000315c  call    cs:__imp_CloseThreadpoolTimer
0x140003162  mov     rcx, [rdi+40h]
0x140003166  add     rdi, 8
0x14000316a  test    rcx, rcx
0x14000316d  jz      short loc_140003189
0x14000316f  mov     rax, [rcx]
0x140003172  cmp     rcx, rdi
0x140003175  setnz   dl
0x140003178  mov     rax, [rax+20h]
0x14000317c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003181  mov     qword ptr [rdi+38h], 0
0x140003189  mov     rbx, [rsp+28h+arg_0]
0x14000318e  add     rsp, 20h
0x140003192  pop     rdi
0x140003193  retn
```
