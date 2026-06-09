# Concurrency::details::_ScheduleFuncWithAutoInline(std::function<void (void)> const &,Concurrency::details::_TaskInliningMode)

- ea: `0x180012924`
- end: `0x180012a1a`
- name: `?_ScheduleFuncWithAutoInline@details@Concurrency@@YAXAEBV?$function@$$A6AXXZ@std@@W4_TaskInliningMode@12@@Z`
- size: `246`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800114f0`
- `0x18001277c`

## callees

- `0x18000208c`
- `0x180011370`
- `0x180012924`
- `0x180012e78`
- `0x1800130b8`
- `0x180019010`

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
0x180012924  mov     [rsp+arg_0], rbx
0x180012929  mov     [rsp+arg_8], rsi
0x18001292e  push    rdi
0x18001292f  sub     rsp, 30h
0x180012933  mov     esi, edx
0x180012935  mov     rbx, rcx
0x180012938  mov     ecx, 40h ; '@'; Size
0x18001293d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012942  mov     rdi, rax
0x180012945  mov     [rsp+38h+arg_10], rax
0x18001294a  mov     [rsp+38h+arg_18], rax
0x18001294f  mov     qword ptr [rax+38h], 0
0x180012957  mov     rcx, [rbx+38h]
0x18001295b  test    rcx, rcx
0x18001295e  jz      short loc_180012972
0x180012960  mov     rdx, [rcx]
0x180012963  mov     rax, [rdx]
0x180012966  mov     rdx, rdi
0x180012969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001296e  mov     [rdi+38h], rax
0x180012972  cmp     esi, 0FFFFFFFFh
0x180012975  jnz     short loc_180012984
0x180012977  mov     rcx, rdi; void *
0x18001297a  call    ?_Bridge@_TaskProcThunk@details@Concurrency@@SAXPEAX@Z; Concurrency::details::_TaskProcThunk::_Bridge(void *)
0x18001297f  jmp     loc_180012A0A
0x180012984  call    ?get_ambient_scheduler@Concurrency@@YAAEBV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ; Concurrency::get_ambient_scheduler(void)
0x180012989  mov     rcx, [rax+8]
0x18001298d  test    rcx, rcx
0x180012990  jz      short loc_180012996
0x180012992  lock inc dword ptr [rcx+8]
0x180012996  mov     rcx, [rax]
0x180012999  mov     [rsp+38h+var_18], rcx
0x18001299e  mov     rbx, [rax+8]
0x1800129a2  mov     [rsp+38h+var_10], rbx
0x1800129a7  mov     r8, rdi; void *
0x1800129aa  lea     rdx, ?_Bridge@_TaskProcThunk@details@Concurrency@@SAXPEAX@Z; void (*)(void *)
0x1800129b1  test    rcx, rcx
0x1800129b4  jz      short loc_1800129C3
0x1800129b6  mov     rax, [rcx]
0x1800129b9  mov     rax, [rax]
0x1800129bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129c1  jmp     short loc_1800129CE
0x1800129c3  lea     rcx, [rsp+38h+arg_10]; this
0x1800129c8  call    ?schedule@_DefaultPPLTaskScheduler@details@Concurrency@@UEAAXP6AXPEAX@Z0@Z; Concurrency::details::_DefaultPPLTaskScheduler::schedule(void (*)(void *),void *)
0x1800129cd  nop
0x1800129ce  test    rbx, rbx
0x1800129d1  jz      short loc_180012A0A
0x1800129d3  or      eax, 0FFFFFFFFh
0x1800129d6  lock xadd [rbx+8], eax
0x1800129db  cmp     eax, 1
0x1800129de  jnz     short loc_180012A0A
0x1800129e0  mov     rax, [rbx]
0x1800129e3  mov     rcx, rbx
0x1800129e6  mov     rax, [rax]
0x1800129e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129ee  or      eax, 0FFFFFFFFh
0x1800129f1  lock xadd [rbx+0Ch], eax
0x1800129f6  cmp     eax, 1
0x1800129f9  jnz     short loc_180012A0A
0x1800129fb  mov     rax, [rbx]
0x1800129fe  mov     rcx, rbx
0x180012a01  mov     rax, [rax+8]
0x180012a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a0a  mov     rbx, [rsp+38h+arg_0]
0x180012a0f  mov     rsi, [rsp+38h+arg_8]
0x180012a14  add     rsp, 30h
0x180012a18  pop     rdi
0x180012a19  retn
```
