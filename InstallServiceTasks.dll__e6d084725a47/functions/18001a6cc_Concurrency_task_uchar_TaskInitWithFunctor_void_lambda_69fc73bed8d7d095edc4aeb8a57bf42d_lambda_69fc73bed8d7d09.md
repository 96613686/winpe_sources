# Concurrency::task<uchar>::_TaskInitWithFunctor<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_>(_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_ const &)

- ea: `0x18001a6cc`
- end: `0x18001a77e`
- name: `??$_TaskInitWithFunctor@XV_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_@@@?$task@E@Concurrency@@AEAAXAEBV_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180019990`

## callees

- `0x180003948`
- `0x18001a6cc`
- `0x18001ea4c`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001a702`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001a702`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::task<unsigned char>::_TaskInitWithFunctor<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_>(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 i; // r8
  __int64 v5; // rsi
  _QWORD *v6; // rdx
  __int64 v7; // rax

  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(*a1 + i + 12) = 0;
  Concurrency::details::_TaskEventLogger::_LogScheduleTask((Concurrency::details::_TaskEventLogger *)(*a1 + 352LL), 0);
  v5 = *a1;
  v6 = operator new(0x20u);
  *v6 = &Concurrency::details::_PPLTaskHandle<unsigned char,Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable';
  v6[1] = 0;
  v6[2] = 0;
  v7 = a1[1];
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  v6[1] = *a1;
  v6[2] = a1[1];
  *v6 = &Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>::`vftable';
  v6[3] = *a2;
  return Concurrency::details::_Task_impl_base::_ScheduleTask(v5, v6, 0);
}

```

## disassembly

```asm
0x18001a6cc  mov     [rsp+arg_8], rbx
0x18001a6d1  mov     [rsp+arg_10], rsi
0x18001a6d6  push    rdi
0x18001a6d7  sub     rsp, 20h
0x18001a6db  mov     rdi, rdx
0x18001a6de  mov     rbx, rcx
0x18001a6e1  xor     r8d, r8d
0x18001a6e4  mov     rax, [rcx]
0x18001a6e7  mov     byte ptr [rax+r8+0Ch], 0
0x18001a6ed  inc     r8
0x18001a6f0  cmp     r8, 2
0x18001a6f4  jnz     short loc_18001A6E4
0x18001a6f6  mov     rcx, [rcx]
0x18001a6f9  xor     edx, edx
0x18001a6fb  add     rcx, 160h
0x18001a702  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x18001a708  mov     rsi, [rbx]
0x18001a70b  mov     ecx, 20h ; ' '; Size
0x18001a710  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a715  mov     rdx, rax
0x18001a718  mov     [rsp+28h+arg_0], rax
0x18001a71d  lea     rax, ??_7?$_PPLTaskHandle@EU?$_InitialTaskHandle@XV_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@U_TaskProcHandle@details@3@@details@Concurrency@@6B@; const Concurrency::details::_PPLTaskHandle<uchar,Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>,Concurrency::details::_TaskProcHandle>::`vftable'
0x18001a724  mov     [rdx], rax
0x18001a727  mov     qword ptr [rdx+8], 0
0x18001a72f  mov     qword ptr [rdx+10h], 0
0x18001a737  mov     rax, [rbx+8]
0x18001a73b  test    rax, rax
0x18001a73e  jz      short loc_18001A744
0x18001a740  lock inc dword ptr [rax+8]
0x18001a744  mov     rax, [rbx]
0x18001a747  xor     r8d, r8d
0x18001a74a  mov     [rdx+8], rax
0x18001a74e  mov     rcx, rsi
0x18001a751  mov     rax, [rbx+8]
0x18001a755  mov     [rdx+10h], rax
0x18001a759  lea     rax, ??_7?$_InitialTaskHandle@XV_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@6B@; const Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_69fc73bed8d7d095edc4aeb8a57bf42d_,Concurrency::details::_TypeSelectorNoAsync>::`vftable'
0x18001a760  mov     [rdx], rax
0x18001a763  mov     rax, [rdi]
0x18001a766  mov     [rdx+18h], rax
0x18001a76a  mov     rbx, [rsp+28h+arg_8]
0x18001a76f  mov     rsi, [rsp+28h+arg_10]
0x18001a774  add     rsp, 20h
0x18001a778  pop     rdi
0x18001a779  jmp     ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
```
