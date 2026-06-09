# pplx::details::_Task_impl_base::_ScheduleContinuation(pplx::details::_ContinuationTaskHandleBase *)

- ea: `0x180015508`
- end: `0x180015630`
- name: `?_ScheduleContinuation@_Task_impl_base@details@pplx@@QEAAXPEAU_ContinuationTaskHandleBase@23@@Z`
- size: `296`
- prototype: `void __fastcall(pplx::details::_Task_impl_base *__hidden this, struct pplx::details::_ContinuationTaskHandleBase *)`
- caller_count: `40`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180010c94`
- `0x18001102c`
- `0x1800111b8`
- `0x1800189f0`
- `0x180018d88`
- `0x1800190e4`
- `0x180019474`
- `0x18001f5f0`
- `0x18001f770`
- `0x18001fb04`
- `0x18001fc50`
- `0x18001ffec`
- `0x180020388`
- `0x180020724`
- `0x1800208b4`
- `0x180020c48`
- `0x180020dd0`
- `0x180021164`
- `0x1800214fc`
- `0x180021894`
- `0x180021bec`
- `0x180021f80`
- `0x1800220cc`
- `0x18003201c`
- `0x1800323c8`
- `0x180032774`
- `0x180043da0`
- `0x180044134`
- `0x180044280`
- `0x180044614`
- `0x1800449b0`
- `0x180044d44`
- `0x1800450e0`
- `0x180045478`
- `0x180045814`
- `0x180045bb0`
- `0x180045f08`
- `0x1800462ac`
- `0x180046650`
- `0x1800469e4`

## callees

- `0x180013f74`
- `0x18001433c`
- `0x1800148ac`
- `0x180015508`
- `0x18001568c`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001551e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001551e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001556b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001556b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall pplx::details::_Task_impl_base::_ScheduleContinuation(
        pplx::details::_Task_impl_base *this,
        struct pplx::details::_ContinuationTaskHandleBase *a2)
{
  int v4; // ebx
  int v5; // ebx
  int v6; // ebx
  _QWORD *v7; // rax
  __int64 v8; // r8
  pplx::details::_Task_impl_base **v9; // rax
  _QWORD *v10; // rax
  char v11[8]; // [rsp+20h] [rbp-28h] BYREF
  std::_Ref_count_base *v12; // [rsp+28h] [rbp-20h]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *((_DWORD *)this + 2) == 3 || *((_DWORD *)this + 2) == 4 && *((_BYTE *)a2 + 17) )
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
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v5 = v4 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
        return;
      v7 = (_QWORD *)(*(__int64 (__fastcall **)(struct pplx::details::_ContinuationTaskHandleBase *, char *))(*(_QWORD *)a2 + 16LL))(
                       a2,
                       v11);
      LOBYTE(v8) = 1;
      pplx::details::_Task_impl_base::_CancelWithExceptionHolder(*v7, (char *)this + 16, v8);
    }
    else
    {
      v9 = (pplx::details::_Task_impl_base **)(*(__int64 (__fastcall **)(struct pplx::details::_ContinuationTaskHandleBase *, char *))(*(_QWORD *)a2 + 16LL))(
                                                a2,
                                                v11);
      pplx::details::_Task_impl_base::_Cancel(*v9, 1);
    }
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
    (**(void (__fastcall ***)(struct pplx::details::_ContinuationTaskHandleBase *, __int64))a2)(a2, 1);
  }
  else
  {
    v10 = (_QWORD *)(*(__int64 (__fastcall **)(struct pplx::details::_ContinuationTaskHandleBase *, char *))(*(_QWORD *)a2 + 16LL))(
                      a2,
                      v11);
    pplx::details::_Task_impl_base::_ScheduleTask(*v10, a2, *((unsigned int *)a2 + 5));
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
  }
}

```

## disassembly

```asm
0x180015508  mov     [rsp+arg_10], rbx
0x18001550d  push    rbp
0x18001550e  push    rsi
0x18001550f  push    rdi
0x180015510  sub     rsp, 30h
0x180015514  mov     rdi, rdx
0x180015517  mov     rsi, rcx
0x18001551a  add     rcx, 20h ; ' '; lpCriticalSection
0x18001551e  call    cs:__imp_EnterCriticalSection
0x180015524  mov     eax, [rsi+8]
0x180015527  cmp     eax, 3
0x18001552a  jz      short loc_180015562
0x18001552c  mov     eax, [rsi+8]
0x18001552f  cmp     eax, 4
0x180015532  jnz     short loc_18001553A
0x180015534  cmp     byte ptr [rdi+11h], 0
0x180015538  jnz     short loc_180015562
0x18001553a  mov     eax, [rsi+8]
0x18001553d  cmp     eax, 4
0x180015540  jnz     short loc_180015552
0x180015542  mov     rax, [rsi+10h]
0x180015546  neg     rax
0x180015549  sbb     ebx, ebx
0x18001554b  neg     ebx
0x18001554d  add     ebx, 2
0x180015550  jmp     short loc_180015567
0x180015552  xor     ebx, ebx
0x180015554  mov     rax, [rsi+70h]
0x180015558  mov     [rdi+8], rax
0x18001555c  mov     [rsi+70h], rdi
0x180015560  jmp     short loc_180015567
0x180015562  mov     ebx, 1
0x180015567  lea     rcx, [rsi+20h]; lpCriticalSection
0x18001556b  call    cs:__imp_LeaveCriticalSection
0x180015571  sub     ebx, 1
0x180015574  jz      short loc_1800155EF
0x180015576  sub     ebx, 1
0x180015579  jz      short loc_1800155AB
0x18001557b  cmp     ebx, 1
0x18001557e  jnz     loc_180015623
0x180015584  mov     rax, [rdi]
0x180015587  lea     rdx, [rsp+48h+var_28]
0x18001558c  mov     rcx, rdi
0x18001558f  mov     rax, [rax+10h]
0x180015593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015598  nop
0x180015599  lea     rdx, [rsi+10h]
0x18001559d  mov     r8b, bl
0x1800155a0  mov     rcx, [rax]
0x1800155a3  call    ?_CancelWithExceptionHolder@_Task_impl_base@details@pplx@@QEAA_NAEBV?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@_N@Z; pplx::details::_Task_impl_base::_CancelWithExceptionHolder(std::shared_ptr<pplx::details::_ExceptionHolder> const &,bool)
0x1800155a8  nop
0x1800155a9  jmp     short loc_1800155CB
0x1800155ab  mov     rax, [rdi]
0x1800155ae  lea     rdx, [rsp+48h+var_28]
0x1800155b3  mov     rcx, rdi
0x1800155b6  mov     rax, [rax+10h]
0x1800155ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155bf  nop
0x1800155c0  mov     dl, 1; bool
0x1800155c2  mov     rcx, [rax]; this
0x1800155c5  call    ?_Cancel@_Task_impl_base@details@pplx@@QEAA_N_N@Z; pplx::details::_Task_impl_base::_Cancel(bool)
0x1800155ca  nop
0x1800155cb  mov     rcx, [rsp+48h+var_20]; this
0x1800155d0  test    rcx, rcx
0x1800155d3  jz      short loc_1800155DA
0x1800155d5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800155da  mov     rax, [rdi]
0x1800155dd  mov     edx, 1
0x1800155e2  mov     rcx, rdi
0x1800155e5  mov     rax, [rax]
0x1800155e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155ed  jmp     short loc_180015623
0x1800155ef  mov     rax, [rdi]
0x1800155f2  lea     rdx, [rsp+48h+var_28]
0x1800155f7  mov     rcx, rdi
0x1800155fa  mov     rax, [rax+10h]
0x1800155fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015603  nop
0x180015604  mov     r8d, [rdi+14h]
0x180015608  mov     rdx, rdi
0x18001560b  mov     rcx, [rax]
0x18001560e  call    ?_ScheduleTask@_Task_impl_base@details@pplx@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; pplx::details::_Task_impl_base::_ScheduleTask(pplx::details::_TaskProcHandle *,pplx::details::_TaskInliningMode)
0x180015613  nop
0x180015614  mov     rcx, [rsp+48h+var_20]; this
0x180015619  test    rcx, rcx
0x18001561c  jz      short loc_180015623
0x18001561e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015623  mov     rbx, [rsp+48h+arg_10]
0x180015628  add     rsp, 30h
0x18001562c  pop     rdi
0x18001562d  pop     rsi
0x18001562e  pop     rbp
0x18001562f  retn
```
