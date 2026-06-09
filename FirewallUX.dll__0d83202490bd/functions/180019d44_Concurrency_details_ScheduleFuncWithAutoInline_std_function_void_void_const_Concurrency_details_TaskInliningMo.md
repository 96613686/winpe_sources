# Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)

- ea: `0x180019d44`
- end: `0x180019e3a`
- name: `?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z`
- size: `246`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180018870`
- `0x180019b9c`

## callees

- `0x1800021e4`
- `0x1800186f0`
- `0x180019d44`
- `0x18001a6a8`
- `0x18001a9e8`
- `0x18002d010`

## pseudocode

```c
void __fastcall Concurrency::details::_ScheduleFuncWithAutoInline(__int64 a1, int a2)
{
  _QWORD *v4; // rdi
  __int64 (__fastcall ***v5)(_QWORD, _QWORD *); // rcx
  _QWORD *ambient_scheduler; // rax
  __int64 v7; // rcx
  volatile signed __int32 *v8; // rbx
  _QWORD *v9; // [rsp+50h] [rbp+18h] BYREF
  _QWORD *v10; // [rsp+58h] [rbp+20h]

  v4 = operator new(0x40u);
  v9 = v4;
  v10 = v4;
  v4[7] = 0;
  v5 = *(__int64 (__fastcall ****)(_QWORD, _QWORD *))(a1 + 56);
  if ( v5 )
    v4[7] = (**v5)(v5, v4);
  if ( a2 == -1 )
  {
    Concurrency::details::_TaskProcThunk::_Bridge(v4);
  }
  else
  {
    ambient_scheduler = (_QWORD *)Concurrency::get_ambient_scheduler();
    v7 = ambient_scheduler[1];
    if ( v7 )
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
    v8 = (volatile signed __int32 *)ambient_scheduler[1];
    if ( *ambient_scheduler )
      (**(void (__fastcall ***)(_QWORD, void (__fastcall *)(_QWORD *), _QWORD *))*ambient_scheduler)(
        *ambient_scheduler,
        Concurrency::details::_TaskProcThunk::_Bridge,
        v4);
    else
      Concurrency::details::_DefaultPPLTaskScheduler::schedule(
        (Concurrency::details::_DefaultPPLTaskScheduler *)&v9,
        (void (*)(void *))Concurrency::details::_TaskProcThunk::_Bridge,
        v4);
    if ( v8 && _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
}

```

## disassembly

```asm
0x180019d44  mov     [rsp+arg_0], rbx
0x180019d49  mov     [rsp+arg_8], rsi
0x180019d4e  push    rdi
0x180019d4f  sub     rsp, 30h
0x180019d53  mov     esi, edx
0x180019d55  mov     rbx, rcx
0x180019d58  mov     ecx, 40h ; '@'; Size
0x180019d5d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019d62  mov     rdi, rax
0x180019d65  mov     [rsp+38h+arg_10], rax
0x180019d6a  mov     [rsp+38h+arg_18], rax
0x180019d6f  mov     qword ptr [rax+38h], 0
0x180019d77  mov     rcx, [rbx+38h]
0x180019d7b  test    rcx, rcx
0x180019d7e  jz      short loc_180019D92
0x180019d80  mov     rdx, [rcx]
0x180019d83  mov     rax, [rdx]
0x180019d86  mov     rdx, rdi
0x180019d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d8e  mov     [rdi+38h], rax
0x180019d92  cmp     esi, 0FFFFFFFFh
0x180019d95  jnz     short loc_180019DA4
0x180019d97  mov     rcx, rdi; void *
0x180019d9a  call    ?_Bridge@_TaskProcThunk@details@Concurrency@@SAXPEAX@Z; Concurrency::details::_TaskProcThunk::_Bridge(void *)
0x180019d9f  jmp     loc_180019E2A
0x180019da4  call    ?get_ambient_scheduler@Concurrency@@YAAEBV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ; Concurrency::get_ambient_scheduler(void)
0x180019da9  mov     rcx, [rax+8]
0x180019dad  test    rcx, rcx
0x180019db0  jz      short loc_180019DB6
0x180019db2  lock inc dword ptr [rcx+8]
0x180019db6  mov     rcx, [rax]
0x180019db9  mov     [rsp+38h+var_18], rcx
0x180019dbe  mov     rbx, [rax+8]
0x180019dc2  mov     [rsp+38h+var_10], rbx
0x180019dc7  mov     r8, rdi; void *
0x180019dca  lea     rdx, ?_Bridge@_TaskProcThunk@details@Concurrency@@SAXPEAX@Z; void (*)(void *)
0x180019dd1  test    rcx, rcx
0x180019dd4  jz      short loc_180019DE3
0x180019dd6  mov     rax, [rcx]
0x180019dd9  mov     rax, [rax]
0x180019ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019de1  jmp     short loc_180019DEE
0x180019de3  lea     rcx, [rsp+38h+arg_10]; this
0x180019de8  call    ?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z; Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)
0x180019ded  nop
0x180019dee  test    rbx, rbx
0x180019df1  jz      short loc_180019E2A
0x180019df3  or      eax, 0FFFFFFFFh
0x180019df6  lock xadd [rbx+8], eax
0x180019dfb  cmp     eax, 1
0x180019dfe  jnz     short loc_180019E2A
0x180019e00  mov     rax, [rbx]
0x180019e03  mov     rcx, rbx
0x180019e06  mov     rax, [rax]
0x180019e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e0e  or      eax, 0FFFFFFFFh
0x180019e11  lock xadd [rbx+0Ch], eax
0x180019e16  cmp     eax, 1
0x180019e19  jnz     short loc_180019E2A
0x180019e1b  mov     rax, [rbx]
0x180019e1e  mov     rcx, rbx
0x180019e21  mov     rax, [rax+8]
0x180019e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e2a  mov     rbx, [rsp+38h+arg_0]
0x180019e2f  mov     rsi, [rsp+38h+arg_8]
0x180019e34  add     rsp, 30h
0x180019e38  pop     rdi
0x180019e39  retn
```
