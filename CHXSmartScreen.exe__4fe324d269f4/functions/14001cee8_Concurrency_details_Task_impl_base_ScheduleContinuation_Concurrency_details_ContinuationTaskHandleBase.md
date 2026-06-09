# Concurrency::details::_Task_impl_base::_ScheduleContinuation(Concurrency::details::_ContinuationTaskHandleBase *)

- ea: `0x14001cee8`
- end: `0x14001d0d9`
- name: `?_ScheduleContinuation@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z`
- size: `497`
- prototype: `void(Concurrency::details::_Task_impl_base *__hidden this, struct Concurrency::details::_ContinuationTaskHandleBase *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140013344`
- `0x140013784`

## callees

- `0x14001cee8`
- `0x14001d0e0`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001cf48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001cf48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001cefb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001cefb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_Task_impl_base::_ScheduleContinuation(
        struct _RTL_CRITICAL_SECTION *this,
        struct Concurrency::details::_ContinuationTaskHandleBase *a2)
{
  int v4; // ebx
  int v5; // ebx
  int v6; // ebx
  _QWORD *v7; // rax
  HANDLE *p_LockSemaphore; // rdx
  __int64 v9; // r9
  __int64 v10; // r8
  volatile signed __int32 *v11; // rsi
  _QWORD *v12; // rax
  __int64 v13; // rdx
  volatile signed __int32 *v14; // rsi
  Concurrency::details::_Task_impl_base **v15; // rax
  volatile signed __int32 *v16; // rdi
  char v17[8]; // [rsp+30h] [rbp-38h] BYREF
  volatile signed __int32 *v18; // [rsp+38h] [rbp-30h]

  EnterCriticalSection(this + 1);
  if ( LODWORD(this->OwningThread) == 3 || LODWORD(this->OwningThread) == 4 && *((_BYTE *)a2 + 40) )
  {
    v4 = 1;
  }
  else if ( LODWORD(this->OwningThread) == 4 )
  {
    v4 = (this->LockSemaphore != 0) + 2;
  }
  else
  {
    v4 = 0;
    *((_QWORD *)a2 + 3) = this[2].LockSemaphore;
    this[2].LockSemaphore = a2;
  }
  LeaveCriticalSection(this + 1);
  v5 = v4 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
        return;
      v7 = (_QWORD *)(*(__int64 (__fastcall **)(struct Concurrency::details::_ContinuationTaskHandleBase *, char *))(*(_QWORD *)a2 + 8LL))(
                       a2,
                       v17);
      p_LockSemaphore = &this->LockSemaphore;
      LOBYTE(v9) = 1;
      LOBYTE(v10) = 1;
      LOBYTE(p_LockSemaphore) = 1;
      (*(void (__fastcall **)(_QWORD, HANDLE *, __int64, __int64, HANDLE *))(*(_QWORD *)*v7 + 8LL))(
        *v7,
        p_LockSemaphore,
        v10,
        v9,
        &this->LockSemaphore);
      v11 = v18;
      if ( v18 && _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    else
    {
      v12 = (_QWORD *)(*(__int64 (__fastcall **)(struct Concurrency::details::_ContinuationTaskHandleBase *, char *))(*(_QWORD *)a2 + 8LL))(
                        a2,
                        v17);
      v13 = *v12 + 24LL;
      LOBYTE(v13) = 1;
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)*v12 + 8LL))(
        *v12,
        v13,
        0,
        0,
        *v12 + 24LL);
      v14 = v18;
      if ( v18 )
      {
        if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        }
      }
    }
    (**(void (__fastcall ***)(struct Concurrency::details::_ContinuationTaskHandleBase *, __int64))a2)(a2, 1);
  }
  else
  {
    v15 = (Concurrency::details::_Task_impl_base **)(*(__int64 (__fastcall **)(struct Concurrency::details::_ContinuationTaskHandleBase *, char *))(*(_QWORD *)a2 + 8LL))(
                                                      a2,
                                                      v17);
    Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(*v15, a2);
    v16 = v18;
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( !_InterlockedDecrement(v16 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
  }
}

```

## disassembly

```asm
0x14001cee8  push    rbx
0x14001ceea  push    rbp
0x14001ceeb  push    rsi
0x14001ceec  push    rdi
0x14001ceed  sub     rsp, 48h
0x14001cef1  mov     rdi, rdx
0x14001cef4  mov     rsi, rcx
0x14001cef7  add     rcx, 28h ; '('; lpCriticalSection
0x14001cefb  call    cs:__imp_EnterCriticalSection
0x14001cf01  mov     eax, [rsi+10h]
0x14001cf04  cmp     eax, 3
0x14001cf07  jz      short loc_14001CF3F
0x14001cf09  mov     eax, [rsi+10h]
0x14001cf0c  cmp     eax, 4
0x14001cf0f  jnz     short loc_14001CF17
0x14001cf11  cmp     byte ptr [rdi+28h], 0
0x14001cf15  jnz     short loc_14001CF3F
0x14001cf17  mov     eax, [rsi+10h]
0x14001cf1a  cmp     eax, 4
0x14001cf1d  jnz     short loc_14001CF2F
0x14001cf1f  mov     rax, [rsi+18h]
0x14001cf23  neg     rax
0x14001cf26  sbb     ebx, ebx
0x14001cf28  neg     ebx
0x14001cf2a  add     ebx, 2
0x14001cf2d  jmp     short loc_14001CF44
0x14001cf2f  xor     ebx, ebx
0x14001cf31  mov     rax, [rsi+68h]
0x14001cf35  mov     [rdi+18h], rax
0x14001cf39  mov     [rsi+68h], rdi
0x14001cf3d  jmp     short loc_14001CF44
0x14001cf3f  mov     ebx, 1
0x14001cf44  lea     rcx, [rsi+28h]; lpCriticalSection
0x14001cf48  call    cs:__imp_LeaveCriticalSection
0x14001cf4e  sub     ebx, 1
0x14001cf51  jz      loc_14001D06E
0x14001cf57  sub     ebx, 1
0x14001cf5a  jz      loc_14001CFE2
0x14001cf60  cmp     ebx, 1
0x14001cf63  jnz     loc_14001D0D0
0x14001cf69  mov     rax, [rdi]
0x14001cf6c  lea     rdx, [rsp+68h+var_38]
0x14001cf71  mov     rcx, rdi
0x14001cf74  mov     rax, [rax+8]
0x14001cf78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cf7d  nop
0x14001cf7e  mov     rcx, [rax]
0x14001cf81  mov     rax, [rcx]
0x14001cf84  lea     rdx, [rsi+18h]
0x14001cf88  mov     [rsp+68h+var_48], rdx
0x14001cf8d  mov     r9b, bl
0x14001cf90  mov     r8b, bl
0x14001cf93  mov     dl, bl
0x14001cf95  mov     rax, [rax+8]
0x14001cf99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cf9e  nop
0x14001cf9f  mov     rsi, [rsp+68h+var_30]
0x14001cfa4  test    rsi, rsi
0x14001cfa7  jz      short loc_14001CFE0
0x14001cfa9  or      ebx, 0FFFFFFFFh
0x14001cfac  mov     eax, ebx
0x14001cfae  lock xadd [rsi+8], eax
0x14001cfb3  add     eax, ebx
0x14001cfb5  jnz     short loc_14001CFE0
0x14001cfb7  mov     rax, [rsi]
0x14001cfba  mov     rcx, rsi
0x14001cfbd  mov     rax, [rax]
0x14001cfc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cfc5  mov     eax, ebx
0x14001cfc7  lock xadd [rsi+0Ch], eax
0x14001cfcc  add     eax, ebx
0x14001cfce  jnz     short loc_14001CFE0
0x14001cfd0  mov     rax, [rsi]
0x14001cfd3  mov     rcx, rsi
0x14001cfd6  mov     rax, [rax+8]
0x14001cfda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cfdf  nop
0x14001cfe0  jmp     short loc_14001D059
0x14001cfe2  mov     rax, [rdi]
0x14001cfe5  lea     rdx, [rsp+68h+var_38]
0x14001cfea  mov     rcx, rdi
0x14001cfed  mov     rax, [rax+8]
0x14001cff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cff6  nop
0x14001cff7  mov     rcx, [rax]
0x14001cffa  mov     rax, [rcx]
0x14001cffd  lea     rdx, [rcx+18h]
0x14001d001  mov     [rsp+68h+var_48], rdx
0x14001d006  xor     r9d, r9d
0x14001d009  xor     r8d, r8d
0x14001d00c  mov     dl, 1
0x14001d00e  mov     rax, [rax+8]
0x14001d012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d017  nop
0x14001d018  mov     rsi, [rsp+68h+var_30]
0x14001d01d  test    rsi, rsi
0x14001d020  jz      short loc_14001D059
0x14001d022  or      ebx, 0FFFFFFFFh
0x14001d025  mov     eax, ebx
0x14001d027  lock xadd [rsi+8], eax
0x14001d02c  add     eax, ebx
0x14001d02e  jnz     short loc_14001D059
0x14001d030  mov     rax, [rsi]
0x14001d033  mov     rcx, rsi
0x14001d036  mov     rax, [rax]
0x14001d039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d03e  mov     eax, ebx
0x14001d040  lock xadd [rsi+0Ch], eax
0x14001d045  add     eax, ebx
0x14001d047  jnz     short loc_14001D059
0x14001d049  mov     rax, [rsi]
0x14001d04c  mov     rcx, rsi
0x14001d04f  mov     rax, [rax+8]
0x14001d053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d058  nop
0x14001d059  mov     rax, [rdi]
0x14001d05c  mov     edx, 1
0x14001d061  mov     rcx, rdi
0x14001d064  mov     rax, [rax]
0x14001d067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d06c  jmp     short loc_14001D0D0
0x14001d06e  mov     rax, [rdi]
0x14001d071  lea     rdx, [rsp+68h+var_38]
0x14001d076  mov     rcx, rdi
0x14001d079  mov     rax, [rax+8]
0x14001d07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d082  nop
0x14001d083  mov     rdx, rdi; struct Concurrency::details::_ContinuationTaskHandleBase *
0x14001d086  mov     rcx, [rax]; this
0x14001d089  call    ?_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)
0x14001d08e  nop
0x14001d08f  mov     rdi, [rsp+68h+var_30]
0x14001d094  test    rdi, rdi
0x14001d097  jz      short loc_14001D0D0
0x14001d099  or      ebx, 0FFFFFFFFh
0x14001d09c  mov     eax, ebx
0x14001d09e  lock xadd [rdi+8], eax
0x14001d0a3  add     eax, ebx
0x14001d0a5  jnz     short loc_14001D0D0
0x14001d0a7  mov     rax, [rdi]
0x14001d0aa  mov     rcx, rdi
0x14001d0ad  mov     rax, [rax]
0x14001d0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d0b5  mov     eax, ebx
0x14001d0b7  lock xadd [rdi+0Ch], eax
0x14001d0bc  add     eax, ebx
0x14001d0be  jnz     short loc_14001D0D0
0x14001d0c0  mov     rax, [rdi]
0x14001d0c3  mov     rcx, rdi
0x14001d0c6  mov     rax, [rax+8]
0x14001d0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d0cf  nop
0x14001d0d0  add     rsp, 48h
0x14001d0d4  pop     rdi
0x14001d0d5  pop     rsi
0x14001d0d6  pop     rbp
0x14001d0d7  pop     rbx
0x14001d0d8  retn
```
