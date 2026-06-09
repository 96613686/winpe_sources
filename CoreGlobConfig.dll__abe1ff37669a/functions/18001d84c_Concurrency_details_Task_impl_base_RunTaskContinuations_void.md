# Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)

- ea: `0x18001d84c`
- end: `0x18001d8fd`
- name: `?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ`
- size: `177`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001cf80`
- `0x18001d12c`

## callees

- `0x18001c110`
- `0x18001c400`
- `0x18001cc40`
- `0x18001d84c`
- `0x18001da24`
- `0x180025010`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl_base::_RunTaskContinuations(
        Concurrency::details::_Task_impl_base *this)
{
  _BYTE *v2; // rbx
  _BYTE *v3; // rsi
  __int64 v4; // r8
  char *v5; // rdx
  Concurrency::details::_Task_impl_base *v6; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v7; // [rsp+28h] [rbp-10h]

  v2 = (_BYTE *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v2 )
  {
    do
    {
      v3 = (_BYTE *)*((_QWORD *)v2 + 1);
      (*(void (__fastcall **)(_BYTE *, Concurrency::details::_Task_impl_base **))(*(_QWORD *)v2 + 16LL))(v2, &v6);
      if ( *((_DWORD *)this + 2) != 4 || v2[32] )
      {
        Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(
          v6,
          (struct Concurrency::details::_ContinuationTaskHandleBase *)v2);
      }
      else
      {
        v5 = (char *)this + 16;
        if ( *((_QWORD *)this + 2) )
        {
          Concurrency::details::_Task_impl_base::_CancelWithExceptionHolder((__int64)v6, (__int64)v5, v4);
        }
        else
        {
          LOBYTE(v5) = 1;
          Concurrency::details::_Task_impl_base::_Cancel(v6, (__int64)v5);
        }
        (**(void (__fastcall ***)(_BYTE *, __int64))v2)(v2, 1);
      }
      if ( v7 )
        std::_Ref_count_base::_Decref(v7);
      v2 = v3;
    }
    while ( v3 );
  }
}

```

## disassembly

```asm
0x18001d84c  mov     [rsp+arg_0], rbx
0x18001d851  mov     [rsp+arg_8], rsi
0x18001d856  push    rdi
0x18001d857  sub     rsp, 30h
0x18001d85b  mov     rdi, rcx
0x18001d85e  mov     rbx, [rcx+70h]
0x18001d862  mov     qword ptr [rcx+70h], 0
0x18001d86a  test    rbx, rbx
0x18001d86d  jz      short loc_18001D8ED
0x18001d86f  mov     rsi, [rbx+8]
0x18001d873  mov     rax, [rbx]
0x18001d876  lea     rdx, [rsp+38h+var_18]
0x18001d87b  mov     rcx, rbx
0x18001d87e  mov     rax, [rax+10h]
0x18001d882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d887  nop
0x18001d888  mov     eax, [rdi+8]
0x18001d88b  cmp     eax, 4
0x18001d88e  jnz     short loc_18001D8C8
0x18001d890  cmp     byte ptr [rbx+20h], 0
0x18001d894  jnz     short loc_18001D8C8
0x18001d896  lea     rdx, [rdi+10h]
0x18001d89a  mov     rcx, [rsp+38h+var_18]; this
0x18001d89f  cmp     qword ptr [rdx], 0
0x18001d8a3  jz      short loc_18001D8AC
0x18001d8a5  call    ?_CancelWithExceptionHolder@_Task_impl_base@details@Concurrency@@QEAA_NAEBV?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@_N@Z; Concurrency::details::_Task_impl_base::_CancelWithExceptionHolder(std::shared_ptr<Concurrency::details::_ExceptionHolder> const &,bool)
0x18001d8aa  jmp     short loc_18001D8B3
0x18001d8ac  mov     dl, 1; bool
0x18001d8ae  call    ?_Cancel@_Task_impl_base@details@Concurrency@@QEAA_N_N@Z; Concurrency::details::_Task_impl_base::_Cancel(bool)
0x18001d8b3  mov     rax, [rbx]
0x18001d8b6  mov     edx, 1
0x18001d8bb  mov     rcx, rbx
0x18001d8be  mov     rax, [rax]
0x18001d8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8c6  jmp     short loc_18001D8D6
0x18001d8c8  mov     rdx, rbx; struct Concurrency::details::_ContinuationTaskHandleBase *
0x18001d8cb  mov     rcx, [rsp+38h+var_18]; this
0x18001d8d0  call    ?_ScheduleContinuationTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleContinuationTask(Concurrency::details::_ContinuationTaskHandleBase *)
0x18001d8d5  nop
0x18001d8d6  mov     rcx, [rsp+38h+var_10]; this
0x18001d8db  test    rcx, rcx
0x18001d8de  jz      short loc_18001D8E5
0x18001d8e0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001d8e5  mov     rbx, rsi
0x18001d8e8  test    rsi, rsi
0x18001d8eb  jnz     short loc_18001D86F
0x18001d8ed  mov     rbx, [rsp+38h+arg_0]
0x18001d8f2  mov     rsi, [rsp+38h+arg_8]
0x18001d8f7  add     rsp, 30h
0x18001d8fb  pop     rdi
0x18001d8fc  retn
```
