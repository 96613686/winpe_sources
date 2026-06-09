# Concurrency::details::_Task_impl_base::_ScheduleContinuation(Concurrency::details::_ContinuationTaskHandleBase *)

- ea: `0x18001d904`
- end: `0x18001da1d`
- name: `?_ScheduleContinuation@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z`
- size: `281`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *this, struct Concurrency::details::_ContinuationTaskHandleBase *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000da9c`

## callees

- `0x18001c110`
- `0x18001c400`
- `0x18001cc40`
- `0x18001d904`
- `0x18001da24`
- `0x18001e88c`
- `0x180025010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001d963`
- `msvcp_win!_Mtx_unlock` at `0x18001d963`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl_base::_ScheduleContinuation(
        Concurrency::details::_Task_impl_base *this,
        struct Concurrency::details::_ContinuationTaskHandleBase *a2)
{
  int v4; // ebx
  int v5; // ebx
  int v6; // ebx
  __int64 *v7; // rax
  __int64 v8; // r8
  Concurrency::details::_Task_impl_base **v9; // rax
  __int64 v10; // rdx
  Concurrency::details::_Task_impl_base **v11; // rax
  char v12[8]; // [rsp+20h] [rbp-38h] BYREF
  std::_Ref_count_base *v13; // [rsp+28h] [rbp-30h]

  std::_Mutex_base::lock((Concurrency::details::_Task_impl_base *)((char *)this + 32));
  if ( *((_DWORD *)this + 2) == 3 || *((_DWORD *)this + 2) == 4 && *((_BYTE *)a2 + 32) )
  {
    v4 = 1;
  }
  else if ( *((_DWORD *)this + 2) == 4 )
  {
    v4 = (*((_QWORD *)this + 2) != 0) + 2;
  }
  else
  {
    v4 = 0;
    *((_QWORD *)a2 + 1) = *((_QWORD *)this + 14);
    *((_QWORD *)this + 14) = a2;
  }
  _Mtx_unlock((Concurrency::details::_Task_impl_base *)((char *)this + 32));
  v5 = v4 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
        return;
      v7 = (__int64 *)(*(__int64 (__fastcall **)(struct Concurrency::details::_ContinuationTaskHandleBase *, char *))(*(_QWORD *)a2 + 16LL))(
                        a2,
                        v12);
      Concurrency::details::_Task_impl_base::_CancelWithExceptionHolder(*v7, (__int64)this + 16, v8);
    }
    else
    {
      v9 = (Concurrency::details::_Task_impl_base **)(*(__int64 (__fastcall **)(struct Concurrency::details::_ContinuationTaskHandleBase *, char *))(*(_QWORD *)a2 + 16LL))(
                                                       a2,
                                                       v12);
      LOBYTE(v10) = 1;
      Concurrency::details::_Task_impl_base::_Cancel(*v9, v10);
    }
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    (**(void (__fastcall ***)(struct Concurrency::details::_ContinuationTaskHandleBase *, __int64))a2)(a2, 1);
  }
  else
  {
    v11 = (Concurrency::details::_Task_impl_base **)(*(__int64 (__fastcall **)(struct Concurrency::details::_ContinuationTaskHandleBase *, char *))(*(_QWORD *)a2 + 16LL))(
                                                      a2,
                                                      v12);
    Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(*v11, a2);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
  }
}

```

## disassembly

```asm
0x18001d904  push    rbx
0x18001d906  push    rbp
0x18001d907  push    rsi
0x18001d908  push    rdi
0x18001d909  sub     rsp, 38h
0x18001d90d  mov     rdi, rdx
0x18001d910  mov     rsi, rcx
0x18001d913  add     rcx, 20h ; ' '; this
0x18001d917  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001d91c  mov     eax, [rsi+8]
0x18001d91f  cmp     eax, 3
0x18001d922  jz      short loc_18001D95A
0x18001d924  mov     eax, [rsi+8]
0x18001d927  cmp     eax, 4
0x18001d92a  jnz     short loc_18001D932
0x18001d92c  cmp     byte ptr [rdi+20h], 0
0x18001d930  jnz     short loc_18001D95A
0x18001d932  mov     eax, [rsi+8]
0x18001d935  cmp     eax, 4
0x18001d938  jnz     short loc_18001D94A
0x18001d93a  mov     rax, [rsi+10h]
0x18001d93e  neg     rax
0x18001d941  sbb     ebx, ebx
0x18001d943  neg     ebx
0x18001d945  add     ebx, 2
0x18001d948  jmp     short loc_18001D95F
0x18001d94a  xor     ebx, ebx
0x18001d94c  mov     rax, [rsi+70h]
0x18001d950  mov     [rdi+8], rax
0x18001d954  mov     [rsi+70h], rdi
0x18001d958  jmp     short loc_18001D95F
0x18001d95a  mov     ebx, 1
0x18001d95f  lea     rcx, [rsi+20h]; _Mtx_t
0x18001d963  call    cs:__imp__Mtx_unlock
0x18001d969  sub     ebx, 1
0x18001d96c  jz      short loc_18001D9E4
0x18001d96e  sub     ebx, 1
0x18001d971  jz      short loc_18001D9A0
0x18001d973  cmp     ebx, 1
0x18001d976  jnz     loc_18001DA14
0x18001d97c  mov     rax, [rdi]
0x18001d97f  lea     rdx, [rsp+58h+var_38]
0x18001d984  mov     rcx, rdi
0x18001d987  mov     rax, [rax+10h]
0x18001d98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d990  nop
0x18001d991  lea     rdx, [rsi+10h]
0x18001d995  mov     rcx, [rax]
0x18001d998  call    ?_CancelWithExceptionHolder@_Task_impl_base@details@Concurrency@@QEAA_NAEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@_N@Z; Concurrency::details::_Task_impl_base::_CancelWithExceptionHolder(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &,bool)
0x18001d99d  nop
0x18001d99e  jmp     short loc_18001D9C0
0x18001d9a0  mov     rax, [rdi]
0x18001d9a3  lea     rdx, [rsp+58h+var_38]
0x18001d9a8  mov     rcx, rdi
0x18001d9ab  mov     rax, [rax+10h]
0x18001d9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9b4  nop
0x18001d9b5  mov     dl, 1; bool
0x18001d9b7  mov     rcx, [rax]; this
0x18001d9ba  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18001d9bf  nop
0x18001d9c0  mov     rcx, [rsp+58h+var_30]; this
0x18001d9c5  test    rcx, rcx
0x18001d9c8  jz      short loc_18001D9CF
0x18001d9ca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001d9cf  mov     rax, [rdi]
0x18001d9d2  mov     edx, 1
0x18001d9d7  mov     rcx, rdi
0x18001d9da  mov     rax, [rax]
0x18001d9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9e2  jmp     short loc_18001DA14
0x18001d9e4  mov     rax, [rdi]
0x18001d9e7  lea     rdx, [rsp+58h+var_38]
0x18001d9ec  mov     rcx, rdi
0x18001d9ef  mov     rax, [rax+10h]
0x18001d9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9f8  nop
0x18001d9f9  mov     rdx, rdi; struct Concurrency::details::_ContinuationTaskHandleBase *
0x18001d9fc  mov     rcx, [rax]; this
0x18001d9ff  call    ?_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)
0x18001da04  nop
0x18001da05  mov     rcx, [rsp+58h+var_30]; this
0x18001da0a  test    rcx, rcx
0x18001da0d  jz      short loc_18001DA14
0x18001da0f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001da14  add     rsp, 38h
0x18001da18  pop     rdi
0x18001da19  pop     rsi
0x18001da1a  pop     rbp
0x18001da1b  pop     rbx
0x18001da1c  retn
```
